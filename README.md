# Blank template using Knock and JWT

This application is a blank project for create other apps using simple token authentication (JWT).

### Getting Started
<pre>
  git clone https://github.com/acmesquita/blank-api-with-knock/ api
  cd api/
  bunble install
  rails s
</pre>

### Steps to creation and authtication an new user

#### 1. Create a new User

<pre>
  POST http://localhost:3000/users/create
  Header 
    Content-Type: application/json
  Body
    {
      "user": {
        "email": "your-email@email.com",
        "password": "your-password",
        "username": "your-username"
      }
    }
    
    
  Response:
  {
    "status": 200,
    "msg": "User was created."
  }
</pre>

#### 2. Getting Token

<pre>
  POST http://localhost:3000/user_token
  Header 
    Content-Type: application/json
  Body
    {
      "auth": {
        "email": "catharina@email.com",
        "password": "12345678"
      }
    }
    
  Response:
  {
    "jwt": "[token]"
  }
</pre>

#### 3. Test to loged

<pre>
  GET http://localhost:3000/auth
  Header 
    Content-Type: application/json
    Authorization: Bearer [token]
  Body
    {}
    
  Response:
  {
    "status": 200,
    "msg": "You are currently Logged-in as [your-username]"
  }
</pre>

#### 4. Access to home system

<pre>
  GET http://localhost:3000
  Header 
    Content-Type: application/json
    Authorization: Bearer [token]
  Body
    {}
    
  Response:
  {
    "service": "auth-api",
    "status": 200
  }
</pre>


### Next steps

  Create your system
