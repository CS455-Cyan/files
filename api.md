## Public User Requests

### List custom text sections

**Request**

GET `/catalog/textSections`

**Response**

    {
      "success": true,
      "data": [
        {
          "_id": "570ef51ced1ca29a1e60f797",
          "title": "University Information"
        },
        {
          "_id": "570ef51ced1ca29a1e60f798",
          "title": "Academic Procedures"
        }
      ]
    }

### View custom text section

**Request**

GET `/catalog/textSections/:id`

**Response**

    {
      "success": true,
      "data": {
        "_id": "570ef51ced1ca29a1e60f797",
        "title": "University Information",
        "content": "Yolo.",
        "__v": 0
      }
    }

### List general requirements

**Request**

GET `/catalog/generalRequirements`

**Response**

    {
      "success": true,
      "data": [
        {
          "_id": "570ef51ced1ca29a1e60f799",
          "__v": 0,
          "areaV": [
            {
              "name": "Additional Requirements",
              "_id": "570ef51ced1ca29a1e60f79a",
              "requirements": [
                {
                  "name": "requirement",
                  "_id": "570ef51ced1ca29a1e60f79b",
                  "items": [
                    {
                      "separator": "false",
                      "_id": "570ef51ced1ca29a1e60f79c",
                      "courses": []
                    }
                  ]
                }
              ]
            }
          ],
          "areaIV": [
            {
              "name": "History, Social and Behavioral Sciences",
              "_id": "570ef51ced1ca29a1e60f79d",
              "requirements": [
                {
                  "name": "requirement",
                  "_id": "570ef51ced1ca29a1e60f79e",
                  "items": [
                    {
                      "separator": "false",
                      "_id": "570ef51ced1ca29a1e60f79f",
                      "courses": []
                    }
                  ]
                }
              ]
            }
          ],
          "areaIII": [
            {
              "name": "Natural Sciences and Mathematics",
              "_id": "570ef51ced1ca29a1e60f7a0",
              "requirements": [
                {
                  "name": "requirement",
                  "_id": "570ef51ced1ca29a1e60f7a1",
                  "items": [
                    {
                      "separator": "false",
                      "_id": "570ef51ced1ca29a1e60f7a2",
                      "courses": []
                    }
                  ]
                }
              ]
            }
          ],
          "areaII": [
            {
              "name": "Humanities and Fine Arts",
              "_id": "570ef51ced1ca29a1e60f7a3",
              "requirements": [
                {
                  "name": "requirement",
                  "_id": "570ef51ced1ca29a1e60f7a4",
                  "items": [
                    {
                      "separator": "false",
                      "_id": "570ef51ced1ca29a1e60f7a5",
                      "courses": []
                    }
                  ]
                }
              ]
            }
          ],
          "areaI": [
            {
              "name": "Written Composition",
              "_id": "570ef51ced1ca29a1e60f7a6",
              "requirements": [
                {
                  "name": "requirement",
                  "_id": "570ef51ced1ca29a1e60f7a7",
                  "items": [
                    {
                      "separator": "true",
                      "write_in": "optional",
                      "_id": "570ef51ced1ca29a1e60f7a8",
                      "courses": []
                    }
                  ]
                }
              ]
            }
          ]
        }
      ]
    }

### View categories, departments, and programs

**Request**

GET `/catalog/programs`

**Response**

    {
      "success": true,
      "data": [
        {
          "_id": "570efd8672a74f2e22e8e59d",
          "categories": [
            {
              "name": "College of Business",
              "description": "Hr Hm Business Hum",
              "_id": "570efd8672a74f2e22e8e59f",
              "programs": [
                {
                  "type": "type",
                  "name": "name",
                  "description": "description",
                  "_id": "570efd8672a74f2e22e8e5a0",
                  "requirements": []
                }
              ],
              "departments": [
                {
                  "name": "Computer Science and Information Systems",
                  "description": "CS and CIS are not the same thing",
                  "_id": "570efd8672a74f2e22e8e5a1",
                  "programs": [
                    {
                      "type": "major",
                      "name": "Computer Science",
                      "description": "not for the faint of heart",
                      "_id": "570efd8672a74f2e22e8e5a3",
                      "requirements": [
                        {
                          "name": "Core Requirements",
                          "_id": "570efd8672a74f2e22e8e5a4",
                          "items": [
                            {
                              "separator": "AND",
                              "_id": "570efd8672a74f2e22e8e5a6",
                              "courses": [
                                "570efc799c1394fc21eb9f6b"
                              ]
                            },
                            {
                              "separator": "AND",
                              "_id": "570efd8672a74f2e22e8e5a5",
                              "courses": [
                                "570efc799c1394fc21eb9f6a"
                              ]
                            }
                          ]
                        }
                      ]
                    },
                    {
                      "type": "minor",
                      "name": "Human-Computer Interaction/User Experience",
                      "description": "emotional impact cannot be designed - only experienced",
                      "_id": "570efd8672a74f2e22e8e5a2",
                      "requirements": []
                    }
                  ]
                }
              ]
            },
            {
              "name": "College of Arts and Sciences",
              "_id": "570efd8672a74f2e22e8e59e",
              "programs": [],
              "departments": []
            }
          ]
        }
      ]
    }
    
### Search programs

**Request**

GET `/catalog/search/programs`

**Response**

### View courses

**Request**

GET `/catalog/courses`

**Response**

    {
      "success": true,
      "data": [
        {
          "_id": "570efd8672a74f2e22e8e5a8",
          "subjects": [
            {
              "name": "Computer Science",
              "abbreviation": "CS",
              "_id": "570efd8672a74f2e22e8e5a9",
              "courses": [
                {
                  "title": "Artificial Intelligence",
                  "number": "470",
                  "description": "Robots and stuff...",
                  "_id": "570efd8672a74f2e22e8e5ab",
                  "offerings": []
                },
                {
                  "title": "Programming Languages",
                  "number": "410W",
                  "description": "Fortran...",
                  "_id": "570efd8672a74f2e22e8e5aa",
                  "offerings": []
                }
              ]
            }
          ]
        }
      ]
    }

### View faculty and staff section

**Request**

GET `/catalog/facultyAndStaff`

**Response**

    {
      "success": true,
      "data": "Dr. Roden..."
    }
    
## Primary Admin Actions

### Login

### Change password

### Add text section

**Request**

POST `/admin/catalog/textSections`

    {
      "title": "Expenses",
      "content": "This sh*t ain't cheap"
    }
    
**Response**

    {
      "success": true
    }
    
### Update text section

**Request**

PUT `/admin/catalog/textSections/:id`

    {
      "title": "STUDENT AFFAIRS",
      "content": "Who's doing who"
    }
    
**Response**

    {
      "success": true
    }

### Remove text section

**Request**

DELETE `/admin/catalog/textSections/:id`
    
**Response**

    {
      "success": true
    }

### Update general requirement

**Request**

PUT `/catalog/generalRequirements/:area`

**Response**

### Add program category

**Request**

POST `/catalog/programCategories`

**Response**

### Update program category

**Request**

PUT `/catalog/programCategories/:id`

**Response**

### Remove program category

**Request**

DELETE `/catalog/programCategories/:id`

**Response**

### Add department

**Request**

POST `/catalog/departments/:categoryId`

    {
      "name": "History and Political Science",
      "description": "Controversial sh*t",
      "programs": []
    }

**Response**

    {
      "success": true
    }

### Update department

**Request**

PUT `/catalog/departments/:categoryId/:departmentId`

    {
      "name": "History and Political Science",
      "description": "More controversial sh*t",
      "programs": []
    }

**Response**

    {
      "success": true
    }

### Remove department

**Request**

DELETE `/catalog/departments/:categoryId/:departmentId`

**Response**

    {
      "success": true
    }

### Add program to category

**Request**

POST `/catalog/programs/:categoryId`

    {
      "name": "Political Science",
      "description": "Controversial sh*t",
      "type": "minor",
      "requirements": []
    }

**Response**

    {
      "success": true
    }

### Add program to department

**Request**

POST `/catalog/programs/:categoryId/:departmentId`

    {
      "name": "Computer Information Systems",
      "description": "We're more well-rounded",
      "type": "major",
      "requirements": []
    }

**Response**

    {
      "success": true
    }

### Update program in category

**Request**

PUT `/catalog/programs/:categoryId/:programId`

    {
      "name": "Secondary Education",
      "description": "Teach people sh*t",
      "type": "major"
    }

**Response**

    {
      "success": true
    }

### Update program in department

**Request**

PUT `/catalog/programs/:categoryId/:departmentId/:programId`

    {
      "name": "Secondary Education",
      "description": "Teach people sh*t",
      "type": "major"
    }

**Response**

    {
      "success": true
    }

### Remove program from category

**Request**

DELETE `/catalog/programs/:categoryId/:programId`

**Response**

    {
      "success": true
    }

### Remove program from department

**Request**

DELETE `/catalog/programs/:categoryId/:departmentId/:programId`

**Response**

    {
      "success": true
    }

### Update faculty and staff section

**Request**

PUT `/admin/catalog/facultyAndStaff`

    {
      "content": "Dr. Roden Yeah. Dr. Jerkins yeah. Dr. Jenkins yeah."
    }

**Response**

    {
      "success": true
    }
