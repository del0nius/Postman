#### Postman HW_1

##### Создать запросы в Postman.

`Protocol: http` `IP: 162.55.220.72` `Port: 5005`

EP_1 `Method: GET` `EndPoint: /get_method`
request url params: `name: str` `age: int`

Response:
``` 
[
    "Joe",
    "30"
]
```

EP_2 `Method: POST` `EndPoint: /user_info_3`
request form data: `name: str` `age: int` `salary: int`

Response: 
```
{
    "age": "30",
    "family": {
        "children": [
            ["Alex", 24],
            ["Kate", 12]
        ],
        "u_salary_1_5_year": 4000
    },
    "name": "Joe",
    "salary": 1000
}
```

EP_3 `Method: GET` `EndPoint: /object_info_1`
request url params: `name: str` `age: int` `weight: int`

Response:
```
{
    "age": 30,
    "daily_food": 0.96,
    "daily_sleep": 200.0,
    "name": "Joe"
}
```

EP_4 `Method: GET` `EndPoint: /object_info_2`
request url params: `name: str` `age: int` `salary: int`

Response:
```
{
    "person": {
        "u_age": 30,
        "u_name": [
            "Joe",
            1000,
            30
        ],
        "u_salary_5_years": 4200.0
    },
    "qa_salary_after_1.5_year": 3300.0,
    "qa_salary_after_12_months": 2700.0,
    "qa_salary_after_3.5_years": 3800.0,
    "qa_salary_after_6_months": 2000,
    "start_qa_salary": 1000
}
```

EP_5 `Method: GET` `EndPoint: /object_info_3`
request url params: `name: str` `age: int` `salary: int`

Response:
```
{
    "age": "30",
    "family": {
        "children": [
            ["Alex", 24],
            ["Kate", 12]
        ],
        "pets": {
            "cat": {
                "age": 3,
                "name": "Sunny"
            },
            "dog": {
                "age": 4,
                "name": "Luky"
            }
        },
        "u_salary_1_5_year": 4000
    },
    "name": "Joe",
    "salary": 1000
}
```

EP_6 `Method: GET` `EndPoint: /object_info_4`
request url params: `name: str` `age: int` `salary: int`

Response:
```
{
    "age": 30,
    "name": "Joe",
    "salary": [
        1000,
        "2000",
        "3000"
    ]
}
```

EP_7 `Method: POST` `EndPoint: /user_info_2`
request form data: `name: str` `age: int` `salary: int`

Response: 
```
{
    "person": {
        "u_age": 30,
        "u_name": [
            "Joe",
            1000,
            30
        ],
        "u_salary_5_years": 4200.0
    },
    "qa_salary_after_1.5_year": 3300.0,
    "qa_salary_after_12_months": 2700.0,
    "qa_salary_after_3.5_years": 3800.0,
    "qa_salary_after_6_months": 2000,
    "start_qa_salary": 1000
}
```