# spring_project

https://dbdiagram.io/d/Disciplines-Catalogue-6550e5077d8bbd6465041175

![Disciplines Catalogue (5)](https://github.com/guava0/spring_project/assets/150153871/4094d820-d822-4afd-84fa-b2d5655e9354)

### Functional Requirements

1. **Create a Subject**
   - The system should allow creating a new subject entry with all required attributes (name, teacher_id, faculty_id, program_id, course, semester, lecture_hours, practical_hours, lab_hours, independent_hours, degree, control_type).

2. **Retrieve a Subject**
   - The system should allow retrieving a specific subject by its ID.

3. **Update a Subject**
   - The system should allow updating details of an existing subject.

4. **Delete a Subject**
   - The system should allow deleting a subject by its ID.

5. **List All Subjects**
   - The system should allow retrieving a list of all subjects with optional filtering by faculty, program, course, and semester.

6. **Create a Program**
   - The system should allow creating a new program with a name and a reference to a specialty.

7. **Retrieve a Program**
   - The system should allow retrieving details of a specific program by its ID.

8. **List All Programs**
   - The system should allow retrieving a list of all programs with their associated specialties.

9. **Create a Teacher**
   - The system should allow creating a new teacher entry with name, email, and phone number.

10. **Retrieve a Teacher**
    - The system should allow retrieving details of a specific teacher by their ID.

11. **Update a Teacher**
    - The system should allow updating the details of an existing teacher.

12. **List All Teachers**
    - The system should allow retrieving a list of all teachers.

13. **Create a Faculty**
    - The system should allow creating a new faculty with a name.

14. **Retrieve a Faculty**
    - The system should allow retrieving details of a specific faculty by its ID.

15. **List All Faculties**
    - The system should allow retrieving a list of all faculties.

16. **Create a Specialty**
    - The system should allow creating a new specialty with a name and a reference to a branch.

17. **Retrieve a Specialty**
    - The system should allow retrieving details of a specific specialty by its ID.

18. **List All Specialties**
    - The system should allow retrieving a list of all specialties with their associated branches.

19. **Create a Branch**
    - The system should allow creating a new branch with a name.

20. **Retrieve a Branch**
    - The system should allow retrieving details of a specific branch by its ID.

21. **List All Branches**
    - The system should allow retrieving a list of all branches.

### REST Endpoints and System Behaviors

#### Subjects

1. **Create a Subject**
   - **Endpoint:** `POST /subjects`
   - **Request Body:**
     ```json
     {
       "name": "Physics 101",
       "teacher_id": 1,
       "faculty_id": 1,
       "program_id": 1,
       "course": 1,
       "semester": 1,
       "lecture_hours": 30,
       "practical_hours": 20,
       "lab_hours": 10,
       "independent_hours": 40,
       "degree": "bachelor",
       "control_type": "exam"
     }
     ```
   - **Response:** `201 Created`

2. **Retrieve a Subject**
   - **Endpoint:** `GET /subjects/{id}`
   - **Response:**
     ```json
     {
       "id": 1,
       "name": "Physics 101",
       "teacher_id": 1,
       "faculty_id": 1,
       "program_id": 1,
       "course": 1,
       "semester": 1,
       "lecture_hours": 30,
       "practical_hours": 20,
       "lab_hours": 10,
       "independent_hours": 40,
       "degree": "bachelor",
       "control_type": "exam"
     }
     ```

3. **Update a Subject**
   - **Endpoint:** `PUT /subjects/{id}`
   - **Request Body:**
     ```json
     {
       "name": "Physics 102",
       "teacher_id": 2,
       "faculty_id": 2,
       "program_id": 2,
       "course": 2,
       "semester": 2,
       "lecture_hours": 40,
       "practical_hours": 30,
       "lab_hours": 20,
       "independent_hours": 50,
       "degree": "master",
       "control_type": "assessment"
     }
     ```
   - **Response:** `200 OK`

4. **Delete a Subject**
   - **Endpoint:** `DELETE /subjects/{id}`
   - **Response:** `204 No Content`

5. **List All Subjects**
   - **Endpoint:** `GET /subjects`
   - **Response:**
     ```json
     [
       {
         "id": 1,
         "name": "Physics 101",
         "teacher_id": 1,
         "faculty_id": 1,
         "program_id": 1,
         "course": 1,
         "semester": 1,
         "lecture_hours": 30,
         "practical_hours": 20,
         "lab_hours": 10,
         "independent_hours": 40,
         "degree": "bachelor",
         "control_type": "exam"
       },
       ...
     ]
     ```

#### Programs

6. **Create a Program**
   - **Endpoint:** `POST /programs`
   - **Request Body:**
     ```json
     {
       "name": "Computer Science",
       "specialty_id": 1
     }
     ```
   - **Response:** `201 Created`

7. **Retrieve a Program**
   - **Endpoint:** `GET /programs/{id}`
   - **Response:**
     ```json
     {
       "id": 1,
       "name": "Computer Science",
       "specialty_id": 1
     }
     ```

8. **List All Programs**
   - **Endpoint:** `GET /programs`
   - **Response:**
     ```json
     [
       {
         "id": 1,
         "name": "Computer Science",
         "specialty_id": 1
       },
       ...
     ]
     ```

#### Teachers

9. **Create a Teacher**
   - **Endpoint:** `POST /teachers`
   - **Request Body:**
     ```json
     {
       "name": "John Doe",
       "email": "john.doe@example.com",
       "phone": "1234567890"
     }
     ```
   - **Response:** `201 Created`

10. **Retrieve a Teacher**
    - **Endpoint:** `GET /teachers/{id}`
    - **Response:**
      ```json
      {
        "id": 1,
        "name": "John Doe",
        "email": "john.doe@example.com",
        "phone": "1234567890"
      }
      ```

11. **Update a Teacher**
    - **Endpoint:** `PUT /teachers/{id}`
    - **Request Body:**
      ```json
      {
        "name": "Jane Doe",
        "email": "jane.doe@example.com",
        "phone": "0987654321"
      }
      ```
    - **Response:** `200 OK`

12. **List All Teachers**
    - **Endpoint:** `GET /teachers`
    - **Response:**
      ```json
      [
        {
          "id": 1,
          "name": "John Doe",
          "email": "john.doe@example.com",
          "phone": "1234567890"
        },
        ...
      ]
      ```

#### Faculties

13. **Create a Faculty**
    - **Endpoint:** `POST /faculties`
    - **Request Body:**
      ```json
      {
        "name": "Engineering"
      }
      ```
    - **Response:** `201 Created`

14. **Retrieve a Faculty**
    - **Endpoint:** `GET /faculties/{id}`
    - **Response:**
      ```json
      {
        "id": 1,
        "name": "Engineering"
      }
      ```

15. **List All Faculties**
    - **Endpoint:** `GET /faculties`
    - **Response:**
      ```json
      [
        {
          "id": 1,
          "name": "Engineering"
        },
        ...
      ]
      ```

#### Specialties

16. **Create a Specialty**
    - **Endpoint:** `POST /specialties`
    - **Request Body:**
      ```json
      {
        "name": "Software Engineering",
        "branch_id": 1
      }
      ```
    - **Response:** `201 Created`

17. **Retrieve a Specialty**
    - **Endpoint:** `GET /specialties/{id}`
    - **Response:**
      ```json
      {
        "id": 1,
        "name": "Software Engineering",
        "branch_id": 1
      }
      ```

18. **List All Specialties**
    - **Endpoint:** `GET /specialties`
    - **Response:**
      ```json
      [
        {
          "id": 1,
          "name": "Software Engineering",
          "branch_id": 1
        },
        ...
      ]
      ```

#### Branches

19. **Create a Branch**
    - **Endpoint:** `POST /branches`
    - **Request Body:**
      ```json
      {
        "name": "Science and Technology"
      }
      ```
    - **Response:** `201 Created`

20. **Retrieve a Branch**
    - **Endpoint:** `GET /branches/{id}`
    -

 **Response:**
      ```json
      {
        "id": 1,
        "name": "Science and Technology"
      }
      ```

21. **List All Branches**
    - **Endpoint:** `GET /branches`
    - **Response:**
      ```json
      [
        {
          "id": 1,
          "name": "Science and Technology"
        },
        ...
      ]
      ```
