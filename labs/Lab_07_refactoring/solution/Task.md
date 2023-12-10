# Рефакторинг кода 
___________________________________________________
## Лабораторная работа 7

В данной лабораторной работе рефакторить код написанный на javascript

### Задание 1. level stone

Скрипт сравнивает две переменные и выводит равны они или нет

```js
const variableOne = prompt('Enter the first variable');
const variableTwo = prompt('Enter the second variable');

if (variableOne === variableTwo) {
    console.log('They are equal');
} else {
    console.log('They are not equal');
}

const greeting = 'world';
const combinedString = variableOne + greeting;
```

### Задание №2. level iron

Скрипт выводит названия фруктов, а затем отображает название фрукта и его цвет

```js
const fruits = ['apple', 'strawberry', 'blueberry', 'raspberry', 'lemon'];

for (let i = 0; i < fruits.length; i++) {
    console.log(fruits[i]);

    switch (fruits[i]) {
        case 'apple':
            console.log('apple green');
            break;
        case 'strawberry':
            console.log('strawberry red');
            break;
        case 'blueberry':
            console.log('blueberry blue');
            break;
        case 'raspberry':
            console.log('raspberry light red');
            break;
        case 'lemon':
            console.log('lemon yellow');
            break;
    }
}
```

### Задание 3. level gold

Скрипт выполняет подсчет затрат на зарплату сотрудникам.  
Где спрашивает у пользователя кол-во сотрудников и зарплату на одного человека

```js
let countPeople = 0;
let salary = 0;
while (countPeople === 0) {
    let inputCount = prompt('Введите кол-во человек:', undefined);
    countPeople = parseFloat(inputCount);
}
while (salary === 0) {
    let inputSalary = prompt('Введите зарплату на человека:', undefined);
    salary = parseFloat(inputSalary);
}
let totalCost = countPeople * salary;
console.log('Затраты: ' + totalCost);
```
### Задание 4

Скрипт проводит анализ имеющихся студентов в массиве.
Выводит среднюю оценку и список плохих студентов

```js
const classroom = [
    {fullName:'Петров А.А.', assessment:5},
    {fullName:'Иванов Б.Б.', assessment:3.4},
    {fullName:'Сидоров Г.Г.', assessment:9},
    {fullName:'Немолодой Д.Д', assessment:2},
    {fullName:'Молодой Е.Е', assessment:3.4}
];
let sum = 0;
let count = 0;
let badStudent = [];
for (let index = 0; index < classroom.length; index++) {
    let student = classroom[index];
    let { fullName, assessment } = student;
    if (assessment > 5 || assessment < 0) {
        console.log('Это значение учитываться не будет, оно не соответствует допустимым значениям');
        continue;
    }
    if (assessment < 4)
        badStudent.push(student);

    sum += assessment;
    count += 1;
}
let averageGrade = sum / count;
console.log('Средняя оценка: ' + averageGrade.toFixed(2));
console.log('Плохие студенты:');
if (badStudent.length === 0) {
    console.log('Неуспевающих нет');
} else {
    badStudent.forEach((student) => {
    console.log('ФИО: ' + student.fullName + '; Оценка: ' + student.assessment);
    });
}

```

### Задание 5

Необходимо просмотреть свой код из предыдущей лабораторной работе  
и провести работу над ошибками (если, конечно, ошибки есть)