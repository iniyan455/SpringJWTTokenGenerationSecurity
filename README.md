# SpringJWTTokenGenerationSecurity


#Signup Url -To store in a database - POST METHOD
http://localhost:8091/signup
Body 
{"firstName":"hello","lastName":"bai","username":"iniyan","password":"12345","age":28,"salary":2000}
Response : 
{
    "id": 2,
    "firstName": "hello",
    "lastName": "bai",
    "username": "iniyan",
    "salary": 2000,
    "age": 28
}

# Generate Token -POST METHOD
http://localhost:8091/token/generate-token
body 
{"username":"iniyan","password":"12345"}
Response :
{
    "status": 200,
    "message": "success",
    "result": {
        "token": "eyJhbGciOiJIUzI1NiJ9.eyJzdWIiOiJpbml5YW4iLCJzY29wZXMiOlt7ImF1dGhvcml0eSI6IlJPTEVfQURNSU4ifV0sImlzcyI6Imh0dHA6Ly9kZXZnbGFuLmNvbSIsImlhdCI6MTU1MzA4NzEyNCwiZXhwIjoxNTUzMTA1MTI0fQ.G2Hp2n9OT0IehbGYC9vspRkwzL9YDg7CndRgwbQrDlk",
        "username": "iniyan"
    }
}


#To Get All User Records -GET METHOD
http://localhost:8091/users/4

Header Pass: 
Content-Type:application/json
Authorization:Bearer eyJhbGciOiJIUzI1NiJ9.eyJzdWIiOiJhc2hvayIsInNjb3BlcyI6W3siYXV0aG9yaXR5IjoiUk9MRV9BRE1JTiJ9XSwiaXNzIjoiaHR0cDovL2RldmdsYW4uY29tIiwiaWF0IjoxNTU0NDU5MDE0LCJleHAiOjE1NTQ0NzcwMTR9.6CP1pH9_6XbaLL9oB7UpEjZ3awrZWLAUs1XZ-GQY0Qs

Response :
{
    "status": 200,
    "message": "User fetched successfully.",
    "result": {
        "id": 4,
        "firstName": "hello",
        "lastName": "bai",
        "username": "iniyan",
        "salary": 2000,
        "age": 28
    }
}



#Note Every Five Second need to update token  
Constant Class 

    public static final long ACCESS_TOKEN_VALIDITY_SECONDS = 5*60*60;
    public static final String SIGNING_KEY = "iniyanarul";
    public static final String TOKEN_PREFIX = "Bearer ";
    public static final String HEADER_STRING = "Authorization";
    
    

