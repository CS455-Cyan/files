# Notes

* PUT requests of course specify updating a record. The way they will work in our application is that they will change the *specified fields*, but fields not specified will remain as they were. In other words, it is an change rather than a replacement of the record. So say we sent the following JSON with a PUT request: `{"name": "new name"}`. This would result in a name change only; all the other fields of that record would remain as they were.

# Requests Overview

## Public
- [List custom text sections](#list-custom-text-sections)
- [View custom text section](#view-custom-text-section)
- [List general requirements](#list-general-requirements)
- [List program categories](#list-program-categories)
- [View category/department/program details](#view-categorydepartmentprogram-details)
    - Program details along with detials of department and/or category it is in
- [View department](#view-department)
    - returns department and category
- [Search programs](#search-programs)
- [View program in category](#view-program-in-category)
- [View program in department](#view-program-in-department)
- [List courses](#list-courses)
- [View course](#view-course)
- [Search courses](#search-courses)
- [List subjects](#list-subjects)
- [View subject and list courses for subject](#view-subject-and-list-courses-for-subject)
- [View faculty and staff section](#view-faculty-and-staff-section)
- [List archived PDFs](#list-archived-pdfs)

## Primary Admin
- [Change password](#change-password)
- [Add text section](#add-text-section)
- [Update text section](#update-text-section)
- [Remove text section](#remove-text-section)
- [Reorder text sections](#reorder-text-sections)
- [Add general requirement](#add-general-requirement)
- [Update general requirement](#update-general-requirement)
- [Remove general requirement](#remove-general-requirement)
- [Add program category](#add-program-category)
- [Update program category](#update-program-category)
- [Remove program category](#remove-program-category)
- [Add department](#add-department)
- [Update departmet](#update-department)
- [Remove department](#remove-department)
- [Add program to category](#add-program-to-category)
- [Add program to department](#add-program-to-department)
- [Update program in category](#update-program-in-category)
- [Update program in department](#update-program-in-department)
- [Remove program from category](#remove-program-from-category)
- [Remove program from department](#remove-program-from-department)
- [Add course subject](#add-course-subject)
- [Update course subject](#update-course-subject)
- [Remove course subject](#remove-course-subject)]
- [Add course](#add-course)
- [Update course](#update-course)
- [Remove course](#remove-course)
- [Upate faculty and staff section](#update-faculty-and-staff-section)
- [Publish catalog](#publish-catalog)
    - Copy the database
    - Generate pdf
    - Add pdf to archives
    - "lock" that version of the catalog?
- [Preview catalog PDF](#preview-catalog-pdf)
    - Allow admin to see what pdf of catalog would look like when published
    - Generate a pdf
    - Don't add pdf to archives
    - Don't copy the database
- [View change request queue](#view-change-request-queue)
- [Approve change request](#approve-change-request)
- [Deny change request](#deny-change-request)
- [View all admins](#view-admins)
    - both primary and secondary
- [Add secondary admin](#add-secondary-admin)
- [Change password of admin](#change-password-of-admin)
    - Change password of primary admin
- [Remove secondary admin](#remove-secondary-admin)

##Secondary Admin
- [View change requests](#view-change-requests)
    - (created by that admin)
- [Create change request](#create-change-request)
    -  also available to primary admin
- [Edit change request](#edit-change-request)
    - that hasn't been approved/denied
- [Remove change request](#remove-change-request)
    - that hasn't been approved/denied
- [View change log](#view-change-log)
    - also available to primary admin


# Request Details

## Public User Actions

### List custom text sections

**Request**

GET `/catalog/textSections`

**Response**

    {
      "success": true,
      "data": [
        {
          "title": "University Information",
          "_id": "570f27cab1dd956211defce1"
        },
        {
          "title": "Academic Procedures",
          "_id": "570f27cab1dd956211defce0"
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
        "title": "University Information",
        "content": "Yolo.",
        "_id": "570f27cab1dd956211defce1"
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
          "_id": "57132502d42d9221654fe8fc",
          "area": "I",
          "name": "Written Composition",
          "__v": 4,
          "requirements": [
            {
              "name": "requirement",
              "_id": "57132502d42d9221654fe8fd",
              "separator": "OR",
              "items": [
                {
                  "separator": "AND",
                  "isWriteIn": true,
                  "writeIn": {
                    "content": "hello world",
                    "hours": {
                      "min": 3,
                      "max": 3
                    }
                  },
                  "_id": "57132502d42d9221654fe8fe",
                  "courses": []
                }
              ]
            },
            {
              "name": "other requirements",
              "_id": "571330f91c7afbdb679c6171",
              "separator": "AND",
              "items": [
                {
                  "separator": "AND",
                  "_id": "571330f91c7afbdb679c6172",
                  "isWriteIn": false,
                  "courses": [
                    {
                      "_id": "57132502d42d9221654fe904",
                      "title": "Artificial Intelligence",
                      "number": "470",
                      "description": "Robots and stuff...",
                      "subject": {
                        "_id": "57132502d42d9221654fe900",
                        "name": "Computer Science",
                        "abbreviation": "CS",
                        "__v": 0
                      },
                      "__v": 0,
                      "offerings": []
                    }
                  ]
                }
              ]
            }
          ]
        },
        {
          "_id": "57132505d42d9221654fe906",
          "area": "II",
          "name": "Humanities and Fine Arts",
          "__v": 0,
          "requirements": [
            {
              "name": "requirement",
              "_id": "57132505d42d9221654fe907",
              "separator": "AND",
              "items": [
                {
                  "separator": "OR",
                  "_id": "57132505d42d9221654fe908",
                  "isWriteIn": false,
                  "courses": []
                }
              ]
            }
          ]
        },
        {
          "_id": "57132505d42d9221654fe912",
          "area": "III",
          "name": "Natural Sciences and Mathematics",
          "__v": 0,
          "requirements": [
            {
              "name": "requirement",
              "_id": "57132505d42d9221654fe913",
              "separator": "AND",
              "items": [
                {
                  "separator": "OR",
                  "_id": "57132505d42d9221654fe914",
                  "isWriteIn": false,
                  "courses": []
                }
              ]
            }
          ]
        },
        {
          "_id": "57132505d42d9221654fe915",
          "area": "IV",
          "name": "History, Social and Behavioral Sciences",
          "__v": 0,
          "requirements": [
            {
              "name": "requirement",
              "_id": "57132505d42d9221654fe916",
              "separator": "AND",
              "items": [
                {
                  "separator": "OR",
                  "_id": "57132505d42d9221654fe917",
                  "isWriteIn": false,
                  "courses": []
                }
              ]
            }
          ]
        },
        {
          "_id": "57132506d42d9221654fe918",
          "area": "V",
          "name": "Additional Requirements",
          "__v": 0,
          "requirements": [
            {
              "name": "requirement",
              "_id": "57132506d42d9221654fe919",
              "separator": "AND",
              "items": [
                {
                  "separator": "OR",
                  "_id": "57132506d42d9221654fe91a",
                  "isWriteIn": false,
                  "courses": []
                }
              ]
            }
          ]
        }
      ]
    }

### List program categories

**Request**

GET `/catalog/programs/categories`

**Response**

    {
      "success": true,
      "data": [
        {
          "_id": "57132505d42d9221654fe911",
          "name": "College of Arts and Sciences"
        },
        {
          "_id": "57132505d42d9221654fe909",
          "name": "College of Business"
        }
      ]
    }

### View category/department/program details

**Request**

GET `/catalog/programs/categories/:id`

**Response**

    {
      "success": true,
      "data": [
        {
          "_id": "57132505d42d9221654fe909",
          "name": "College of Business",
          "description": "Hr Hm Business Hum",
          "__v": 6,
          "programs": [
            {
              "type": "type",
              "name": "name",
              "description": "description",
              "_id": "57132505d42d9221654fe90a",
              "requirements": []
            }
          ],
          "departments": [
            {
              "name": "Computer Science and Information Systems",
              "description": "CS and CIS are not the same thing",
              "_id": "57132505d42d9221654fe90b",
              "programs": [
                {
                  "type": "major",
                  "name": "Computer Science",
                  "description": "not for the faint of heart",
                  "_id": "57132505d42d9221654fe90d",
                  "requirements": [
                    {
                      "name": "Core Requirements",
                      "_id": "57132505d42d9221654fe90e",
                      "items": [
                        {
                          "separator": "AND",
                          "_id": "57132505d42d9221654fe910",
                          "isWriteIn": false,
                          "courses": [
                            {
                              "_id": "57132502d42d9221654fe904",
                              "title": "Artificial Intelligence",
                              "number": "470",
                              "description": "Robots and stuff...",
                              "subject": {
                                "_id": "57132502d42d9221654fe900",
                                "name": "Computer Science",
                                "abbreviation": "CS",
                                "__v": 0
                              },
                              "__v": 0,
                              "offerings": []
                            }
                          ]
                        },
                        {
                          "separator": "AND",
                          "_id": "57132505d42d9221654fe90f",
                          "courses": [
                            {
                              "_id": "57132502d42d9221654fe905",
                              "title": "Artificial Intelligence",
                              "number": "470",
                              "description": "Robots and stuff...",
                              "subject": {
                                "_id": "57132502d42d9221654fe900",
                                "name": "Computer Science",
                                "abbreviation": "CS",
                                "__v": 0
                              },
                              "__v": 0,
                              "offerings": []
                            }
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
                  "_id": "57132505d42d9221654fe90c",
                  "requirements": []
                }
              ]
            }
          ]
        }
      ]
    }
    
### View department

**Request**

GET `/catalog/programs/categories/:categoryId/departments/:departmentId`

**Response**

    {
      "success": true,
      "data": {
        "department": {
          "name": "Computer Science and Information Systems",
          "description": "CS and CIS are not the same thing",
          "_id": "5714799c0d1ca57305e7ede0",
          "programs": [
            {
              "type": "minor",
              "name": "Economics",
              "description": "money money money",
              "_id": "5714799c0d1ca57305e7ede6",
              "requirements": []
            },
            {
              "type": "major",
              "name": "Computer Science",
              "description": "not for the faint of heart",
              "_id": "5714799c0d1ca57305e7ede2",
              "requirements": [
                {
                  "name": "Core Requirements",
                  "_id": "5714799c0d1ca57305e7ede3",
                  "items": [
                    {
                      "separator": "AND",
                      "_id": "5714799c0d1ca57305e7ede5",
                      "isWriteIn": false,
                      "courses": [
                        "5714799b0d1ca57305e7edd9"
                      ]
                    },
                    {
                      "separator": "AND",
                      "_id": "5714799c0d1ca57305e7ede4",
                      "courses": [
                        "5714799b0d1ca57305e7edda"
                      ]
                    }
                  ]
                }
              ]
            }
          ]
        },
        "category": {
          "_id": "5714799c0d1ca57305e7edde",
          "name": "College of Business"
        }
      }
    }
    
### Search programs

**Request**

POST `/catalog/search/programs`

    {
      "term": "computer"
    }

**Response**

    {
      "success": true,
      "data": [
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
                  "isWriteIn": false,
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

### View program in category

**Request**

GET `/catalog/programs/categories/:categoryId/programs/:programId`

**Response**

    {
      "success": true,
      "data": {
        {
          "program": {
            "_id": "12345",
            "type": "major",
            "name": "Computer Science"
            "description": "program description",
            "requirements": []
          },
          "category": {
            "_id": "67890",
            "name": "College of Business"
          }
        }
      }
    }
    
### View program in department

**Request**

GET `/catalog/programs/categories/:categoryId/departments/:departmentId/programs/:programId`

**Response**

    {
      "success": true,
      "data": {
        {
          "program": {
            "_id": "12345",
            "type": "major",
            "name": "Computer Science"
            "description": "program description",
            "requirements": []
          },
          "category": {
            "_id": "67890",
            "name": "College of Business"
          },
          "department": {
            "_id": "34567",
            "name": "Computer Science and Information Systems"
          }
        }
      }
    }

### List courses

**Request**

GET `/catalog/courses`

**Response**

    {
      "success": true,
      "data": [
        {
          "_id": "57132502d42d9221654fe904",
          "title": "Artificial Intelligence",
          "number": "470",
          "description": "Robots and stuff...",
          "subject": {
            "_id": "57132502d42d9221654fe900",
            "name": "Computer Science",
            "abbreviation": "CS",
            "__v": 0
          },
          "__v": 0,
          "offerings": []
        },
        {
          "_id": "57132502d42d9221654fe905",
          "title": "Artificial Intelligence",
          "number": "470",
          "description": "Robots and stuff...",
          "subject": {
            "_id": "57132502d42d9221654fe900",
            "name": "Computer Science",
            "abbreviation": "CS",
            "__v": 0
          },
          "__v": 0,
          "offerings": []
        }
      ]
    }
    
### View course

**Request**

GET `/catalog/courses/:id`

**Response**

    {
      "success": true,
      "data": {
        "_id": "57132502d42d9221654fe904",
        "title": "Artificial Intelligence",
        "number": "470",
        "description": "Robots and stuff...",
        "subject": {
          "_id": "57132502d42d9221654fe900",
          "name": "Computer Science",
          "abbreviation": "CS",
          "__v": 0
        },
        "__v": 0,
        "offerings": []
      }
    }

### Search courses

**Request**

POST `/catalog/search/courses`

    {
      "term": "programming"
    }

**Response**

    {
      "success": true,
      "data": [
        {
          "_id": "5710575696a0b8d03b455453",
          "title": "Programming for the Web",
          "number": "325",
          "description": "Javascript. Not Java.",
          "offerings": ["Spring"]
        },
        {
          "_id": "5710575696a0b8d03b455452",
          "title": "Programming Languages",
          "number": "410W",
          "description": "Fortran...",
          "offerings": ["Fall", "Spring"]
        }
      ]
    }
    
### List subjects

**Request**

GET `/catalog/subjects`

**Response**

    {
      "success": true,
      "data": [
        {
          "_id": "57132502d42d9221654fe900",
          "name": "Computer Science",
          "abbreviation": "CS"
        },
        {
          "_id": "57132502d42d9221654fe901",
          "name": "Psychology",
          "abbreviation": "PY"
        }
      ]
    }
    
### View subject and list courses for subject

**Request**

GET `/catalog/subjects/:id`

**Response**

    {
      "success": true,
      "data": {
        subject: {
          "_id": "57132502d42d9221654fe900",
          "name": "Computer Science",
          "abbreviation": "CS"
        },
        "courses": [
          {
            "_id": "57132502d42d9221654fe904",
            "title": "Artificial Intelligence",
            "number": "470",
            "description": "Robots and stuff...",
            "offerings": [],
            "hours": {
              "min": 3,
              "max": 3
            }
          },
          {
            "_id": "57132502d42d9221654fe905",
            "title": "Artificial Intelligence",
            "number": "470",
            "description": "Robots and stuff...",
            "offerings": [],
            "hours": {
              "min": 3,
              "max": 3
            }
          }
        ]
      }
    }

### View faculty and staff section

**Request**

GET `/catalog/facultyAndStaff`

**Response**

    {
      "success": true,
      "data": "Dr. Roden..."
    }
    
### List archived PDFs

**Request**

GET `/catalog/archives`

**Response**

    {
      "success": true,
      "data": [
        {
            "beginYear": "2011",
            "endYear": "2012"
        },
        {
            "beginYear": "2012",
            "endYear": "2013"
        },
        {
            "beginYear": "2013",
            "endYear": "2014"
        }
      ]
    }
    
## Primary Admin Actions

### Login

**Request**

POST `/admin/login`

    {
      "username": "lanel52",
      "password": "punchcards_rock"
    }

**Response**

    {
      "success": true,
      "apps": [
        {
          "id": "catalog",
          "name": "Catalog",
          "url": "/catalog"
        }
      ]
    }

---
---

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

### Remove text section

**Request**

DELETE `/admin/catalog/textSections/:id`
    
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

### Reorder text sections

This should just be a list of id's of textSections. On the backend textSections will be rearranged in this specified order.

**Request**

PUT `/admin/catalog/textSectionsOrder`

    [
      "idOfTextSection1",
      "idOfTextSection2",
      "idOfTextSection3",
      "idOfTextSection4"
    ]
    
**Response**

    {
      "success": true
    }

---
---

### Add general requirement

**Request**

POST `/admin/catalog/generalRequirements/:area`

    {
      "name": "other requirements",
      "separator": "OR",
      "items": [
        {
          "separator": "AND",
          "isWriteIn": false,
          "courses": []
        }
      ]
    }

**Response**

    {
      "success": true
    }

### Remove general requirement

**Request**

DELETE `/admin/catalog/generalRequirements/:area/:requirementId`

**Response**

    {
      "success": true
    }

### Update general requirement

**Request**

PUT `/admin/catalog/generalRequirements/:area/:requirementId`

    {
      "name": "Updated requirements"
    }

**Response**

    {
      "success": true
    }

---
---

### Add program category

**Request**

POST `/admin/catalog/programs/categories`

    {
      "name": "College of Nursing",
      "description": "scrubs"
    }

**Response**

    {
      "success": true
    }

### Remove program category

**Request**

DELETE `/admin/catalog/programs/categories/:id`

**Response**

    {
      "success": true
    }

### Update program category

**Request**

PUT `/admin/catalog/programs/categories/:id`

    {
      "name": "College of Nursing",
      "description": "Taking care of people"
    }

**Response**

    {
      "success": true
    }

---
---

### Add department

**Request**

POST `/admin/catalog/programs/categories/:categoryId/departments`

    {
      "name": "History and Political Science",
      "description": "Controversial sh*t",
      "programs": []
    }

**Response**

    {
      "success": true
    }

### Remove department

**Request**

DELETE `/admin/catalog/programs/categories/:categoryId/departments/:departmentId`

**Response**

    {
      "success": true
    }

### Update department

**Request**

PUT `/admin/catalog/programs/categories/:categoryId/departments/:departmentId`

    {
      "name": "History and Political Science",
      "description": "More controversial sh*t",
      "programs": []
    }

**Response**

    {
      "success": true
    }

---
---

### Add program to category

**Request**

POST `/admin/catalog/programs/categories/:categoryId/programs`

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

POST `/admin/catalog/programs/categories/:categoryId/departments/:departmentId/programs`

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

### Remove program from category

**Request**

DELETE `/admin/catalog/programs/categoies/:categoryId/programs/:programI`

**Response**

    {
      "success": true
    }

### Remove program from department

**Request**

DELETE `/admin/catalog/programs/categories/:categoryId/departments/:departmentId/programs/:programId`

**Response**

    {
      "success": true
    }

### Update program in category

**Request**

PUT `/admin/catalog/programs/categories/:categoryId/programs/:programId`

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

PUT `/admin/catalog/programs/categories/:categoryId/departments/:departmentId/programs/:programId`

    {
      "name": "Secondary Education",
      "description": "Teach people sh*t",
      "type": "major"
    }

**Response**

    {
      "success": true
    }

---
---

### Add course subject

**Request**

POST `/admin/catalog/subjects`

    {
      "name": "Psychology",
      "abbreviation": "PY"
    }

**Response**

    {
      "success": true
    }

### Remove course subject

**Request**

DELETE `/admin/catalog/subjects/:id`

**Response**

    {
      "success": true
    }

### Update course subject

**Request**

PUT `/admin/catalog/subjects/:id`

    {
      "name": "Sociology",
      "abbreviation": "SO"
    }

**Response**

    {
      "success": true
    }

### Add course

**Request**

POST `/admin/catalog/courses`

    {
      "title": "Cognitive Psychology",
      "number": 385,
      "description": "How your brain works",
      "offerings": ["Fall"]
    }

**Response**

    {
      "success": true
    }

### Remove course

**Request**

DELETE `/admin/catalog/courses/:courseId`

**Response**

    {
      "success": true
    }

### Update course

**Request**

POST `/admin/catalog/courses/:courseId`

    {
      "offerings": ["Fall", "Spring"]
    }

**Response**

    {
      "success": true
    }

---
---

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

---
---

### Publish catalog

**Request**

POST `/admin/catalog/publish`

    {
      "beginYear": "2016",
      "endYear": "2017"
    }
    
### Preview catalog

**Request**

POST `/admin/catalog/preview`

    {
      "beginYear": "2016",
      "endYear": "2017"
    }

**Response**

    {
      "success": true
    }

### Preview catalog PDF

**Request**

POST `/admin/catalog/previewPDF`

    {
      "semester": "Fall",
      "year": "2016"
    }

**Response**

    {
      "success": true,
      "data": "http://link-to-file.pdf"
    }
    
### Check preview status

**Request**

GET `/admin/catalog/previewStatus`

**Response**

    {
      "success": true,
      "data": {
        "preview": true
      }
    }

---
---

### View change request queue

**Request**

GET `/admin/changeRequests/queue`

**Response**

    {
      "success": true,
      "data": [
    		{
    		  "_id": "571052e8ad4a865d3a18d454",
    			"author": "Sean Connery",
    			"username": "sean_connery",
    		 	"timeOfRequest": 1460687978978,
    			"timeOfApproval": null,
    			"status": "pending",
    			"requestTypes": [
    				"Change in Course Description",
    			],
    			"revisedFacultyCredentials": {
    				"needed": false,
    				"content": null
    			},
    			"courseListChange": {
    				"needed": false,
    				"content": null
    			},
    			"effective": {
    				"semester": "Fall",
    				"year": "2016"
    			},
    			"courseFeeChange": null,
    			"affectedDepartmentsPrograms": "Computer Science and Information Systems",
    			"approvedBy": "Renee Vandiver",
    			"description": "Change course description for CS310 to 'learning how to write assembly for a computer nobody uses any more'"
    		},
    		{
    		  "_id": "571052e8ad4a865d3a18d458",
    			"author": "Captain America",
    			"username": "captain_america",
    		 	"timeOfRequest": 1460687997358,
    			"timeOfApproval": null,
    			"status": "pending",
    			"requestTypes": [
    				"Addition of/Change in Course Fee",
    			],
    			"revisedFacultyCredentials": {
    				"needed": false,
    				"content": null
    			},
    			"courseListChange": {
    				"needed": false,
    				"content": null
    			},
    			"effective": {
    				"semester": "Fall",
    				"year": "2016"
    			},
    			"courseFeeChange": null,
    			"affectedDepartmentsPrograms": "Computer Science and Information Systems",
    			"approvedBy": "Renee Vandiver",
    			"description": "Change course fee for CS455 to $3000 so nobody can graduate. hehe"
    		}
      ]
    }

### Approve change request

**Request**

PUT `/admin/changeRequests/approve/:id`

    {
      "comment": "OK"
    }

**Response**

    {
      "success": true
    }

### Deny change request

**Request**

PUT `/admin/changeRequests/deny/:id`

    {
      "comment": "Yeah... No."
    }

**Response**

    {
      "success": true
    }

---
---

### Add secondary admin

**Request**

POST `/admin/admins`

    {
      "username": "spiderman",
      "password": "underoos"
    }

**Response**

    {
      "success": true
    }

### Remove secondary admin

**Request**

DELETE `/admin/admins/:id`

**Response**

    {
      "success": true
    }
    
### Change password of admin

**Request**

PUT `/admin/password/:id`

    {
        "password": "punchcards_rock"
    }

**Response**

    {
        "success": true
    }

### View admins

**Request**

GET `/admin/admins`

**Response**

    {
      "success": true,
      "data": [
        {
          "_id": "571052e8ad4a865d3a18d465"
          "username": "captain_america",
          "privilege": 5,
          "apps": ["catalog"],
          "password": "c0a6012970d27f714cdcee6dac4da264"
        },
        {
          "_id": "5710575696a0b8d03b455456",
          "username": "sean_connery",
          "privilege": 2,
          "apps": ["catalog"],
          "password": "c0a6012970d27f714cdcee6dac4da264"
        }
      ]
    }
    
## Secondary Admin Actions

### Change password

**Request**

PUT `/admin/password`

    {
        "password": "punchcards_rock"
    }

**Response**

    {
        "success": true
    }

---
---

### View change requests

**Request**

GET `/admin/changeRequests/userRequests`

**Response**

    {
      "success": true,
      "data": [
    		{
    		  "_id": "571052e8ad4a865d3a18d454",
    			"author": "Sean Connery",
    			"username": "sean_connery",
    		 	"timeOfRequest": 1460687978978,
    			"timeOfApproval": null,
    			"status": "pending",
    			"requestTypes": [
    				"Change in Course Description",
    			],
    			"revisedFacultyCredentials": {
    				"needed": false,
    				"content": null
    			},
    			"courseListChange": {
    				"needed": false,
    				"content": null
    			},
    			"effective": {
    				"semester": "Fall",
    				"year": "2016"
    			},
    			"courseFeeChange": null,
    			"affectedDepartmentsPrograms": "Computer Science and Information Systems",
    			"approvedBy": "Renee Vandiver",
    			"description": "Change course description for CS310 to 'learning how to write assembly for a computer nobody uses any more'"
    		},
    		{
    		  "_id": "571052e8ad4a865d3a18d458",
    			"author": "Sean Connery",
    			"sean_connery",
    		 	"timeOfRequest": 1460687978978,
    			"timeOfApproval": 1460687997358,
    			"status": "denied",
    			"requestTypes": [
    				"Addition of/Change in Course Fee",
    			],
    			"revisedFacultyCredentials": {
    				"needed": false,
    				"content": null
    			},
    			"courseListChange": {
    				"needed": false,
    				"content": null
    			},
    			"effective": {
    				"semester": "Fall",
    				"year": "2016"
    			},
    			"courseFeeChange": null,
    			"affectedDepartmentsPrograms": "Computer Science and Information Systems",
    			"approvedBy": "Renee Vandiver",
    			"description": "Change course fee for CS455 to $3000 so nobody can graduate. hehe",
    			"comment": "WTF??"
    		}
      ]
    }

### Create change request

**Request**

POST `/admin/changeRequests/userRequests`

    {
    	"requestTypes": [
    		"Addition of/Change in Course Fee",
    	],
    	"revisedFacultyCredentials": {
    		"needed": false,
    		"content": null
    	},
    	"courseListChange": {
    		"needed": false,
    		"content": null
    	},
    	"effective": {
    		"semester": "Fall",
    		"year": "2016"
    	},
    	"courseFeeChange": null,
    	"affectedDepartmentsPrograms": "Computer Science and Information Systems",
    	"approvedBy": "Renee Vandiver",
    	"description": "Change course fee for CS455 to $3000 so nobody can graduate. hehe"
    }

**Response**

    {
      "success": true
    }

### Edit change request

**Request**

PUT `/admin/changeRequests/userRequests/:id`

    {
    	"effective": {
    		"semester": "Spring",
    		"year": "2017"
    	}
    }

**Response**

    {
      "success": true
    }

### Remove change request

**Request**

DELETE `/admin/changeRequests/userRequests/:id`

**Response**

    {
      "success": true
    }

### View change log

**Request**

GET `/admin/changeRequests/log`

**Response**

    {
      "success": true,
      "data": [
    		{
    		  "_id": "571052e8ad4a865d3a18d454",
    			"author": "Sean Connery",
    			"username": "sean_connery",
    		 	"timeOfRequest": 1460687978978,
    			"timeOfApproval": 1460687997358,
    			"status": "approved",
    			"requestTypes": [
    				"Change in Course Description",
    			],
    			"revisedFacultyCredentials": {
    				"needed": false,
    				"content": null
    			},
    			"courseListChange": {
    				"needed": false,
    				"content": null
    			},
    			"effective": {
    				"semester": "Fall",
    				"year": "2016"
    			},
    			"courseFeeChange": null,
    			"affectedDepartmentsPrograms": "Computer Science and Information Systems",
    			"approvedBy": "Renee Vandiver",
    			"description": "Change course description for CS310 to 'learning how to write assembly for a computer nobody uses any more'",
    			comment: "Works for me"
    		},
    		{
    		  "_id": "571052e8ad4a865d3a18d458",
    		    "author": "Sean Connery",
    			"username": "sean_connery",
    		 	"timeOfRequest": 1460687997358,
    			"timeOfApproval": 1460688026114,
    			"status": "approved",
    			"requestTypes": [
    				"Addition of/Change in Course Fee",
    			],
    			"revisedFacultyCredentials": {
    				"needed": false,
    				"content": null
    			},
    			"courseListChange": {
    				"needed": false,
    				"content": null
    			},
    			"effective": {
    				"semester": "Fall",
    				"year": "2016"
    			},
    			"courseFeeChange": null,
    			"affectedDepartmentsPrograms": "Computer Science and Information Systems",
    			"approvedBy": "Renee Vandiver",
    			"description": "Change course fee for CS455 to $3000 so nobody can graduate. hehe",
    			comment: "I like the way you think"
    		}
      ]
    }
