#### Postman HW_2

`http://162.55.220.72:5005/first`
1. Отправить запрос.
2. Статус код 200
```
pm.test("Status code is 200", function () {
    pm.response.to.have.status(200);
});
```

3. Проверить, что в body приходит правильный string.
```
pm.test("Body matches string", function () {
    pm.expect(pm.response.text()).to.include("This is the first responce from server!");
});
```

`http://162.55.220.72:5005/user_info_3`
1. Отправить запрос.
2. Статус код 200
```
pm.test("Status code is 200", function () {
    pm.response.to.have.status(200);
});
```

3. Спарсить response body в json.
`var respData = pm.response.json();`

4. Проверить, что name в ответе равно name s request (name вбить руками.)
```
pm.test("Test_name_resp", function () {
    pm.expect(respData.name).to.eql('Joe');
});
```

5. Проверить, что age в ответе равно age s request (age вбить руками.)
```
pm.test("Test_age_resp", function () {
    pm.expect(respData.age).to.eql('30');
});
```

6. Проверить, что salary в ответе равно salary s request (salary вбить руками.)
```
pm.test("Test_salary_resp", function () {
    pm.expect(respData.salary).to.eql(1000);
});
```

7. Спарсить request.
```
var reqData = request.data;
var req_salary = +reqData.salary
```

8. Проверить, что name в ответе равно name s request (name забрать из request.)
```
pm.test("Test_name_req", function () {
    pm.expect(respData.name).to.eql(reqData.name);
});
```

9. Проверить, что age в ответе равно age s request (age забрать из request.)
```
pm.test("Test_age_req", function () {
    pm.expect(respData.age).to.eql(reqData.age);
});
```

10. Проверить, что salary в ответе равно salary s request (salary забрать из request.)
```
pm.test("Test_salary_req", function () {
    pm.expect(respData.salary).to.eql(req_salary);
});
```

11. Вывести в консоль параметр family из response.
`console.log(respData.family)`

12. Проверить что u_salary_1_5_year в ответе равно salary*4 (salary забрать из request)
```
pm.test("Test_salary_1,5y_req", function () {
    pm.expect(respData.family.u_salary_1_5_year).to.eql(req_salary*4);
});
```

`http://162.55.220.72:5005/object_info_3`
1. Отправить запрос.
2. Статус код 200
```
pm.test("Status code is 200", function () {
    pm.response.to.have.status(200);
});
```

3. Спарсить response body в json.
`var respData = pm.response.json();`

4. Спарсить request.
```
var reqData = pm.request.url.query.toObject();
// создадим для будущих проверок переменную req_salary и присвоем ей преобразованное в int значение reqData.salary
var req_salary = +reqData.salary
```

5. Проверить, что name в ответе равно name s request (name забрать из request.)
```
pm.test("Test_name_req", function () {
    pm.expect(respData.name).to.eql(reqData.name);
});
```

6. Проверить, что age в ответе равно age s request (age забрать из request.)
```
pm.test("Test_age_req", function () {
    pm.expect(respData.age).to.eql(reqData.age);
});
```

7. Проверить, что salary в ответе равно salary s request (salary забрать из request.)
```
pm.test("Test_salary_req", function () {
    pm.expect(respData.salary).to.eql(req_salary);
});
```

8. Вывести в консоль параметр family из response.
`console.log(respData.family)`

9. Проверить, что у параметра dog есть параметры name.
```
pm.test("Test_dog_2have_name", function () {
    pm.expect(respData.family.pets.dog).to.have.property('name');
});
```

10. Проверить, что у параметра dog есть параметры age.
```
pm.test("Test_dog_2have_age", function () {
    pm.expect(respData.family.pets.dog).to.have.property('age');
});
```

11. Проверить, что параметр name имеет значение Luky.
```
pm.test("Test_dog_name_Luky", function () {
    pm.expect(respData.family.pets.dog.name).to.eql('Luky');
});
```

12. Проверить, что параметр age имеет значение 4.
```
pm.test("Test_dog_age_4", function () {
    pm.expect(respData.family.pets.dog.age).to.eql(4);
});
```

`http://162.55.220.72:5005/object_info_4`
1. Отправить запрос.
2. Статус код 200
```
pm.test("Status code is 200", function () {
    pm.response.to.have.status(200);
});
```

3. Спарсить response body в json.
`var respData = pm.response.json();`
 
4. Спарсить request.
```
var reqData = pm.request.url.query.toObject();
// создадим для будущих проверок переменную req_salary и присвоем ей преобразованное в int значение reqData.salary
var req_salary = +reqData.salary
```

5. Проверить, что name в ответе равно name s request (name забрать из request.)
```
pm.test("respData.name eql reqData.name", function () {
    pm.expect(respData.name).to.eql(reqData.name);
});
```

6. Проверить, что age в ответе равно age из request (age забрать из request.)
`var req_age = +reqData.age`
```
pm.test("respData.age eql req_age ", function () {
    pm.expect(respData.age).to.eql(req_age);
});
```

7. Вывести в консоль параметр salary из request.
`console.log("Request salary =", reqData.salary);`

8. Вывести в консоль параметр salary из response.
`console.log("Response salary =", respData.salary);`

9. Вывести в консоль 0-й элемент параметра salary из response.
`console.log('0-й элемент параметра salary =',respData.salary[0])`

10. Вывести в консоль 1-й элемент параметра salary параметр salary из response.
`console.log('1-й элемент параметра salary =',respData.salary[1])`

11. Вывести в консоль 2-й элемент параметра salary параметр salary из response.
`console.log('2-й элемент параметра salary =',respData.salary[2])`

12. Проверить, что 0-й элемент параметра salary равен salary из request (salary забрать из request.)
```
pm.test("Test resp_salary[0] eql req_salary", function () {
    pm.expect(respData.salary[0]).to.eql(req_salary);
});
```

13. Проверить, что 1-й элемент параметра salary равен salary*2 из request (salary забрать из request.)
```
pm.test("Test resp_salary[1] eql req_salary*2", function () {
    pm.expect(parseInt(respData.salary[1])).to.eql(req_salary*2);
});
```

14. Проверить, что 2-й элемент параметра salary равен salary*3 из request (salary забрать из request.)
```
pm.test("Test resp_salary[2] eql req_salary*3", function () {
    pm.expect(parseInt(respData.salary[2])).to.eql(req_salary*3);
});
```

15. Создать в окружении переменную name
16. Создать в окружении переменную age
17. Создать в окружении переменную salary

18. Передать в окружение переменную name
`pm.environment.set("name", respData.name);`

19. Передать в окружение переменную age
`pm.environment.set("age", respData.age);`

20. Передать в окружение переменную salary
`pm.environment.set("salary", respData.salary[0]);`

21. Написать цикл который выведет в консоль по порядку элементы списка из параметра salary.
```
for (var i = 0; i < respData.salary.length; i++){
console.log('salary', i+1, respData.salary[i]);
}
```

`http://162.55.220.72:5005/user_info_2`
1. Вставить параметр salary из окружения в request
2. Вставить параметр age из окружения в age
3. Вставить параметр name из окружения в name
4. Отправить запрос.
5. Статус код 200
```
pm.test("Status code is 200", function () {
    pm.response.to.have.status(200);
});
```

6. Спарсить response body в json.
`var respData = pm.response.json();`

7. Спарсить request.
```
var reqData = request.data;
// создадим для будущих проверок переменную req_salary и присвоем ей преобразованное в int значение reqData.salary
var req_salary = +reqData.salary
```

8. Проверить, что json response имеет параметр start_qa_salary
```
pm.test("jsresp has start_qa_salary", function () {
    pm.expect(respData).to.have.property("start_qa_salary")
});
```

9. Проверить, что json response имеет параметр qa_salary_after_6_months
```
pm.test("jsresp has qa_salary_after_6_months", function () {
    pm.expect(respData).to.have.property("qa_salary_after_6_months")
});
```

10. Проверить, что json response имеет параметр qa_salary_after_12_months
```
pm.test("jsresp has qa_salary_after_12_months", function () {
    pm.expect(respData).to.have.property("qa_salary_after_12_months")
});
```

11. Проверить, что json response имеет параметр qa_salary_after_1.5_year
```
pm.test("jsresp has qa_salary_after_1.5_year", function () {
    pm.expect(respData).to.have.property("qa_salary_after_1.5_year")
});
```

12. Проверить, что json response имеет параметр qa_salary_after_3.5_years
```
pm.test("jsresp has qa_salary_after_3.5_years", function () {
    pm.expect(respData).to.have.property("qa_salary_after_3.5_years")
});
```

13. Проверить, что json response имеет параметр person
```
pm.test("jsresp has person", function () {
    pm.expect(respData).to.have.property("person")
});
```

14. Проверить, что параметр start_qa_salary равен salary из request (salary забрать из request.)
```
pm.test("start_qa_salary eql req_salary", function () {
    pm.expect(respData.start_qa_salary).to.eql(req_salary);
});
```

15. Проверить, что параметр qa_salary_after_6_months равен salary*2 из request (salary забрать из request.)
```
pm.test("qa_salary_after_6_months eql req_salary*2", function () {
    pm.expect(respData.qa_salary_after_6_months).to.eql(req_salary*2);
});
```

16. Проверить, что параметр qa_salary_after_12_months равен salary*2.7 из request (salary забрать из request.)
```
pm.test("qa_salary_after_12_months eql req_salary*2.7", function () {
    pm.expect(respData.qa_salary_after_12_months).to.eql(req_salary*2.7);
});
```

17. Проверить, что параметр qa_salary_after_1.5_year равен salary*3.3 из request (salary забрать из request.)
```
pm.test("qa_salary_after_1.5_year eql req_salary*3.3", function () {
    pm.expect(respData['qa_salary_after_1.5_year']).to.eql(req_salary*3.3);
});
```

18. Проверить, что параметр qa_salary_after_3.5_years равен salary*3.8 из request (salary забрать из request.)
```
pm.test("qa_salary_after_3.5_years eql req_salary*3.8", function () {
    pm.expect(respData['qa_salary_after_3.5_years']).to.eql(req_salary*3.8);
});
```

19. Проверить, что в параметре person, 1-й элемент из u_name равен salary из request (salary забрать из request.)
```
pm.test("respData.person.u_name[1] eql req_salary", function () {
    pm.expect(respData.person.u_name[1]).to.eql(req_salary);
});
```

20. Проверить, что что параметр u_age равен age из request (age забрать из request.)
```
pm.test("respData.u_age eql reqData.age", function () {
    pm.expect(respData.person.u_age).to.eql(+reqData.age);
});
```

21. Проверить, что параметр u_salary_5_years равен salary*4.2 из request (salary забрать из request.)
```
pm.test("respData.person.u_salary_5_years eql req_salary*4.2", function () {
    pm.expect(respData.person.u_salary_5_years).to.eql(req_salary*4.2);
});
```

22. ***Написать цикл который выведет в консоль по порядку элементы списка из параметра person.
```
for (var key in respData.person) {
console.log(respData.person[key]);
}
```
