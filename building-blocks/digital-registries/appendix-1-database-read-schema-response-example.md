# Appendix 1- Database Read-Schema Response Example

```
{
  "id": 353,
  "version": "2.7",
  "name": null,
  "description": null,
  "institution": null,
  "number_format": "{code}{indexNoByCode}",
  "schema": {
    "type": "object",
    "properties": {
      "ID": {
        "type": "string",
        "triggers": [
          {
            "conditions": [
              {
                "logic": "==",
                "value": "",
                "gate": "&&"
              }
            ],
            "actions": [
              {
                "type": "set-value",
                "value": "MCTS{indexNoByCode}",
                "field_id": 1
              },
              {
                "type": "upper-case",
                "field_id": 1
              }
            ]
          }
        ],
        "primaryKey": true,
        "readOnly": true,
        "description": "Registration ID",
        "example": "MCTS31",
        "$id": 1
      },
      "Child": {
        "type": "object",
        "properties": {
          "ID": {
            "type": "string",
            "description": "Child ID",
            "example": "ID2",
            "$id": 13
          },
          "Firstname": {
            "type": "string",
            "description": "Child first name",
            "example": "Usha",
            "$id": 3
          },
          "Lastname": {
            "type": "string",
            "description": "Child last name",
            "example": "Bajaj",
            "$id": 4
          },
          "Birthdate": {
            "type": "string",
            "format": "date",
            "description": "Child data of birth",
            "example": "2021-10-03T07:03:36Z",
            "$id": 5
          },
          "Address": {
            "type": "string",
            "description": "Child's address",
            "example": "Longroad 123, Welltown, Ethiopia",
            "$id": 7
          },
          "Birth_certificate": {
            "type": "file",
            "consumes": [
              "application/pdf",
              "image/jpeg",
              "image/png",
              "image/gif",
              "image/tiff",
              "image/bmp",
              "image/x-ms-bmp",
              "application/rtf",
              "text/rtf",
              "application/vnd.openxmlformats-officedocument.wordprocessingml.document",
              "application/vnd.oasis.opendocument.text"
            ],
            "antivirus": true,
            "description": "Child's birth certificate data. ISO8601/UTC",
            "example": "2021-10-03T07:03:36Z",
            "$id": 6
          },
          "Citizenship": {
            "type": "string",
            "description": "Child is a citizen of this country. ISO 3166-1 encoding list",
            "example": "ET",
            "$id": 20
          }
        },
        "description": "Child object data that is queried from database",
        "$id": 2
      },
      "Registration date": {
        "type": "string",
        "format": "date",
        "description": "Record registration date",
        "example": "2021-10-03T07:03:36Z",
        "$id": 14
      },
      "Expiry date": {
        "type": "string",
        "format": "date",
        "description": "Record expiry date",
        "example": "2021-10-03T07:03:36Z",
        "$id": 15
      },
      "Caretaker": {
        "type": "object",
        "properties": {
          "ID": {
            "type": "string",
            "description": "Caretaker's ID",
            "example": "ID1",
            "$id": 12
          },
          "Firstname": {
            "type": "string",
            "description": "Caretaker's first name",
            "example": "Sowmya",
            "$id": 9
          },
          "Lastname": {
            "type": "string",
            "description": "Caretaker's last name",
            "example": "Bajaj",
            "$id": 10
          },
          "Birthdate": {
            "type": "string",
            "format": "date",
            "description": "Caretaker's birth date",
            "example": "2021-10-03T07:03:36Z",
            "$id": 16
          },
          "Phone": {
            "type": "string",
            "description": "Caretaker's phone number",
            "example": "+3725278511",
            "$id": 11
          },
          "Email": {
            "type": "string",
            "description": "Caretaker's email",
            "example": "test@test.et",
            "$id": 17
          },
          "Picture": {
            "type": "file",
            "consumes": [
              "application/pdf",
              "image/jpeg",
              "image/png",
              "image/gif",
              "image/tiff",
              "image/bmp",
              "image/x-ms-bmp",
              "application/rtf",
              "text/rtf",
              "application/vnd.openxmlformats-officedocument.wordprocessingml.document",
              "application/vnd.oasis.opendocument.text"
            ],
            "antivirus": true,
            "description": "Caretaker's picture.",
            "$id": 18
          },
          "Document ID": {
            "type": "file",
            "consumes": [
              "application/pdf",
              "image/jpeg",
              "image/png",
              "image/gif",
              "image/tiff",
              "image/bmp",
              "image/x-ms-bmp",
              "application/rtf",
              "text/rtf",
              "application/vnd.openxmlformats-officedocument.wordprocessingml.document",
              "application/vnd.oasis.opendocument.text"
            ],
            "antivirus": true,
            "description": "Caretaker's document",
            "$id": 19
          }
        },
        "description": "Caretaker's information",
        "$id": 8
      }
    },
    "$incrementIndex": 20,
    "required": [
      "ID"
    ]
  },
  "schema_tags": [
    {
      "name": "",
      "path": "/Child/Citizenship",
      "is_fulltext": true
    },
    {
      "name": "",
      "path": "/Child/Lastname",
      "is_fulltext": true
    },
    {
      "name": "",
      "path": "/Child/Firstname",
      "is_fulltext": true
    },
    {
      "name": "",
      "path": "/ID",
      "is_fulltext": true
    }
  ],
  "schema_flags": [
    {
      "name": "mandatory",
      "path": "/ID"
    },
    {
      "name": "unique",
      "path": "/ID"
    }
  ],
  "fields_uniques": [
    []
  ],
  "is_draft": false,
  "is_disabled": false,
  "is_archived": false,
  "modified_at": "2021-10-03T08:35:01.775915Z",
  "by_user_name": "ingmar.dev",
  "by_user_auth_id": 1,
  "by_on_behalf_of_user_auth_id": null,
  "by_on_behalf_of_user_name": null,
  "generic_services": [
    {
      "service_id": 1,
      "name": "data-create",
      "is_visible": true,
      "used_count": 0
    },
    {
      "service_id": 2,
      "name": "data-read",
      "is_visible": true,
      "used_count": 0
    },
    {
      "service_id": 9,
      "name": "data-read-value",
      "is_visible": true,
      "used_count": 0
    },
    {
      "service_id": 3,
      "name": "data-list",
      "is_visible": true,
      "used_count": 0
    },
    {
      "service_id": 4,
      "name": "data-update",
      "is_visible": true,
      "used_count": 0
    },
    {
      "service_id": 6,
      "name": "data-delete",
      "is_visible": true,
      "used_count": 0
    },
    {
      "service_id": 7,
      "name": "data-exists",
      "is_visible": true,
      "used_count": 0
    },
    {
      "service_id": 10,
      "name": "data-update-or-create",
      "is_visible": true,
      "used_count": 0
    },
    {
      "service_id": 11,
      "name": "data-update-entries",
      "is_visible": true,
      "used_count": 0
    },
    {
      "service_id": 12,
      "name": "data-create-entries",
      "is_visible": true,
      "used_count": 0
    },
    {
      "service_id": 13,
      "name": "data-update-or-create-entries",
      "is_visible": true,
      "used_count": 0
    }
  ],
  "data_index_increment": 0,
  "has_logo": false
}

```
