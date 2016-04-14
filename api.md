## Public User Requests

### List custom text sections

GET `/catalog/textSections`

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
GET `/catalog/textSections/:id`

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
GET `/catalog/generalRequirements`

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

### Update general requirement
PUT `/catalog/generalRequirements/:area


### View categories, departments, and programs
GET `/catalog/programs`

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

### Add program category
POST `/catalog/programCategories`

### Update program category
PUT `/catalog/programCategories/:id`

### Remove program category
DELETE `/catalog/programCategories/:id`
