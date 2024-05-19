# NotesApp backend

This Flask application proveides a backend to frontend React application, to work with Mongo database where all data is stored
The whole application is also available by this link: https://davidbakalov21.github.io/NotesAppFront
## Table of Contents

- [Installation](#installation)
- [Usage](#usage)

## Installation

Instructions on how to set up the project locally. 

```bash
# Clone the repository
git clone https://github.com/DavidBakalov21/FlaskBackendShow

#Navigate to the root of the project and run these two commands They will run app in docker:
docker build -t notes-app-backend .
docker run -p 5000:5000 notes-app-backend
```
## Usage
To interact with the backend, you can use the following API endpoints. The backend server will run on `http://localhost:5000`.

#### Sign Up
This endpoint is used to create a new user account if account already exists it will return failure.
- **URL**: `/signUp`
- **Method**: `POST`
- **Data Params**:
    - `email`: User's email
    - `password`: User's password
    - `first_name`: User's first name
    - `last_name`: User's last name
- **Success Response**:
    - **Content**: `{ status: "success" }`
- **Error Response**:
    - **Content**: `{ status: failure that happened }`


#### Create Category
This endpoint is used to create a new category for certain account, if category already exists it will return failure.
- **URL**: `/createCategory`
- **Method**: `POST`
- **Data Params**:
    - `email`: User's email
    - `name`: name of the category
    - `color`: color of the category
- **Success Response**:
    - **Content**: `{ status: "success" }`
- **Error Response**:
    - **Content**: `{ status: failure that happened }`

#### Get Categories
This endpoint is used to get all category objects for certain account from the database.
- **URL**: `/getCategory`
- **Method**: `POST`
- **Data Params**:
    - `email`: User's email
- **Success Response**:
    - **Content**: list with all cotegory objects
- **Error Response**:
    - **Content**: None


#### Get Notes
This endpoint is used to get all notes objects for certain account from the database.
- **URL**: `/getNotes`
- **Method**: `POST`
- **Data Params**:
    - `email`: User's email
- **Success Response**:
    - **Content**: list with all Notes objects
- **Error Response**:
    - **Content**: None


#### Create Note
This endpoint is used to create a new note for certain account, if exactly same note already exists then note won't be created.
- **URL**: `/CreateNote`
- **Method**: `POST`
- **Data Params**:
    - `email`: User's email
    - `note`: text of note
    - `category`: category object
    - `date`: date of creation
- **Success Response**:
    - **Content**: `{ status: "success" }`
- **Error Response**:
    - **Content**: `{ status: failure that happened }`

#### Sign in
This endpoint is used to confirm if person is registered in the database.
- **URL**: `/signIn`
- **Method**: `POST`
- **Data Params**:
    - `email`: User's email
    - `password`: User's password
- **Success Response**:
    - **Content**: `{ status: "success" }`
- **Error Response**:
    - **Content**: `{ status: "failure" }`

#### Delete Note
This endpoint is used to delete notes from database.
- **URL**: `/deleteNote`
- **Method**: `DELETE`
- **Data Params**:
    - `email`: User's email
    - `note`: text of note
    - `category`: category object
    - `date`: date of creation/modification
    - `status`: status of the note
- **Success Response**:
    - **Content**: `{ status: "success" }`
- **Error Response**:
    - **Content**: `{ status: failure that happened }`

#### Update Note
This endpoint is used to update note.
- **URL**: `/UpdateNote`
- **Method**: `PATCH`
- **Data Params**:
    - `emailEdit`: User's email
    - `note`: text of note
    - `category`: category object
    - `date`: date of creation/modification
    - `status`: status of the note
    - `noteEdit`:new text of note 
    - `categoryEdit`:new category object
    - `dateEdit`:new date of creation/modification
    - `statusEdit`:new status of the note
- **Success Response**:
    - **Content**: `{ status: "success" }`
- **Error Response**:
    - **Content**: `{ status: failure that happened }`