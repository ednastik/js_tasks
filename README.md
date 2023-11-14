# js_tasks
Task for UI course
## Задание 1. Custom Array.prototype.filter
```javascript
/**
 * Кастомная реализация метода Array.prototype.filter
 * 
 * @param {Array} array - массив
 * @param {Function} filterFn - фильтрующая функция
 * @param {Boolean} inplace - флаг "модифицируем исходный массив или нет"
 * @returns {Array} - отфильтрованный массив
 */

function filter(array, filterFn, inplace = false) {
  if (inplace) {
    let i = 0;
    while (i < array.length) {
      if (!filterFn(array[i])) {
        array.splice(i, 1);
      } else {
        i++;
      }
    }
    return array;
  } else {
    const resultArray = [];
    for (const item of array) {
      if (filterFn(item)) {
        resultArray.push(item);
      }
    }
    return resultArray;
  }
}

// Пример использования
const words = ['spray', 'limit', 'elite', 'exuberant', 'destruction', 'present'];

const result = filter(words, (word) => word.length > 6);

console.log(result); // ["exuberant", "destruction", "present"]
```
## Задание 2. Ключи и свойства
```javascript
const initialObj = {
    a: 'some string 1',
    b: 42,
    c: { c1: 'some string 2' },
    d: [],
    e: 123,
};

function counttypes(objTypes) {
    contentArr = Object.values(objTypes);
    let types = []
    for (let itemarr of contentArr) {
        types.push(typeof itemarr);
    }
    console.log(types);
    
    const res = types.reduce((acc, i) => {
        if (acc.hasOwnProperty(i)) {
          acc[i] += 1;
        } else {
          acc[i] = 1;
        }
        return acc;
      },{});
    return res;
}

const resultObj = counttypes(initialObj);

console.log(resultObj);
```
## Задание 3. Ключи и свойства
```javascript
a = 10
b = 3

if ((typeof a != "number")||(typeof b != "number")){
    if ((typeof a != "number")&&(typeof b != "number")) {
        console.log("Operands are not numbers");
    } else if ((typeof a != "number")) {
        console.log("The left operand is not number");
    } else {
        console.log("The right operand is not number");     
    }
} else {
    console.log(a + b);
}
```
