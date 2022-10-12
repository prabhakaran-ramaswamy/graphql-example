# graphql-example
URL
http://localhost:9000/graphiql


Sample Requests

{
  test
}
-----------------
{
  test,
  greeting 
}
-------------------
{
  test,
  greeting,
  students{
    id,
    firstName,
    lastName
  }
}
------------------
{
  test,
  greeting,
  students{
    id,
    firstName,
    lastName
  },
  studentById(id:"S1002"){
    firstName,
    lastName
  }
}

----------------------
{
   students{
      id
      fullName
   }
}

------------------------
{
  students {
    id
    fullName
    college {
      id
      name
      location
      rating
    }
  }
}
-------------------------
{
  sayHello(name:"Prabhakaran")
}

-------------------------

{
  setFavouriteColor(color:RED)
}

or

query{
  setFavouriteColor(color:RED)
}

--------------------------
mutation {
   createStudent(collegeId:"col-2",firstName:"Tim",lastName:"George")
}
--------------------------
mutation {
   addStudent_returns_object(collegeId:"col-101",firstName:"Susan",lastName:"George") {
      id
      firstName
      college{
         id
         name
      }
   }
}

-------------------------------
mutation doSignUp($input:SignUpInput) {
   signUp(input:$input)
}

The following query variable must be entered in query variables tab of graphiql


{
   "input":{
      "email": "abc@abc.com",
      "firstName": "kannan",
      "password": "pass@1234"
   }
}