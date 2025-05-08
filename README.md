# petstore

Recommendation regarding running the collection in Postman: set delay between requests 1000 ms (as DB works slowly and some tests or even requests may fail)

Task 2: Test cases for POST create user endpoint

ID: 1

Summary: It is possible to create a new user

Precondition: API key is added into Authorization header

Steps:
    
    1. Create POST request to 'https://petstore.swagger.io/v2/user'
    
    2. Fill in all fields in the body with correct values
    
    3. Send the request

Expected result:
   
    1. Status code 201
    
    2. User with new ID is created
    
    3. All values are correct

ID: 2

Summary: It is NOT possible to assign the ID to a new user

Precondition: API key is added into Authorization header

Steps:

    1. Create POST request to 'https://petstore.swagger.io/v2/user'
    
    2. Fill in all fields in the body with correct values
    
    3. Add "id" field with some integer value
    
    4. Send the request

Expected result:

    1. Status code 400
    
    2. Message: "id must be null"

ID: 3

Summary: It's NOT possible to create a new user without authorization

Precondition: API key is NOT added into Authorization header

Steps:

    1. Create POST request to 'https://petstore.swagger.io/v2/user'
    
    2. Fill in all fields in the body with correct values
    
    3. Send the request

Expected result:

    1. Status code 401
    
    2. Message: "Unauthorized"

ID: 4

Summary: All fields in the request must correspond to scheme

Precondition: API key is added into Authorization header

Steps:

    1. Create POST request to 'https://petstore.swagger.io/v2/user'
    
    2. Fill in all fields in the body with correct values
    
    3. Change some field name
    
    4. Send the request
    
    5. Repeat step 3 with all fields in order

Expected result:

    1. Status code 400
    
    2. Message: "Failed to read request"

ID: 5

Summary: All values types in the request must correspond to scheme

Precondition: API key is added into Authorization header

Steps:

    1. Create POST request to 'https://petstore.swagger.io/v2/user'
    
    2. Fill in all fields in the body with correct values
    
    3. Change value type in some field
    
    4. Send the request
    
    5. Repeat step 3 with all values in order

Expected result:

    1. Status code 400
    
    2. Message: "Failed to read request"

ID: 6

Summary: All fields are required

Precondition: API key is added into Authorization header

Steps:

    1. Create POST request to 'https://petstore.swagger.io/v2/user'
    
    2. Fill in all fields in the body with correct values
    
    3. Delete some field
    
    4. Send the request
    
    5. Repeat step 3 with all fields in order

Expected result:

    1. Status code 400
    
    2. Message: "Field *deleted field* must not be null"

ID: 7

Summary: It's NOT possible to create a user with already existing username

Precondition: API key is added into Authorization header

Steps:

    1. Create POST request to 'https://petstore.swagger.io/v2/user'
    
    2. Fill in all fields in the body with correct values
    
    3. Send the request
    
    4. Change values in all fields except username
    
    5. Send the request again

Expected result:

    1. Status code 400
    
    2. Message: "User with such a user name already exists"

ID: 8

Summary: It's NOT possible to create a user with already existing email

Precondition: API key is added into Authorization header

Steps:

    1. Create POST request to 'https://petstore.swagger.io/v2/user'
    
    2. Fill in all fields in the body with correct values
    
    3. Send the request
    
    4. Change values in all fields except email
    
    5. Send the request again

Expected result:

    1. Status code 400
    
    2. Message: "Failed to read request"

ID: 9

Summary: It's NOT possible to create a user with already existing phone number

Precondition: API key is added into Authorization header

Steps:

    1. Create POST request to 'https://petstore.swagger.io/v2/user'
    
    2. Fill in all fields in the body with correct values
    
    3. Send the request
    
    4. Change values in all fields except phone
    
    5. Send the request again

Expected result:

    1. Status code 400
    
    2. Message: "Failed to read request"

ID: 10

Summary: It's NOT possible to create a user with password < 8 characters

Precondition: API key is added into Authorization header

Steps:

    1. Create POST request to 'https://petstore.swagger.io/v2/user'
    
    2. Fill in all fields in the body with correct values
    
    3. Set password value < 8 characters
    
    4. Send the request

Expected result:

    1. Status code 400
    
    2. Message: "Password must contain at least 8 characters"
