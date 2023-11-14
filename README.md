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
## Задание 4. CVS на минималках
```javascript
function getMinimalCVS(arr) {
    let history = [arr.slice()+""];
    return {
      head: function() {
        return history[history.length - 1];
      },
      history: function() {
        return history.map(item => item.split(","));
      },
      push: function(item) {
        arr.push(item);
        history.push(arr.slice()+"");
      },
      pop: function() {
        let lastItem = arr.pop();
        history.push(arr.slice()+"");
        return lastItem;
      }
    };
}

const cvs = getMinimalCVS(['a', 'b', 'c']);

console.log(cvs.head());    // ['a', 'b', 'c']
console.log(cvs.pop());     // 'c'

cvs.push('d');
cvs.push('e');

console.log(cvs.head());    // ['a', 'b', 'd', 'e']
console.log(cvs.history());
```
## Задание 5. Глобальный переключатель
```javascript
function globalToggle(className) {
  const elements = document.getElementsByClassName(className);
  
  if (elements.length === 0) {
    return;
  }
  
  if (className.endsWith('_active')) {
    for (let i = 0; i < elements.length; i++) {
      elements[i].classList.remove(className);
      elements[i].classList.add(className.replace('_active', ''));
    }
  } else {
    for (let i = 0; i < elements.length; i++) {
      elements[i].classList.remove(className);
      elements[i].classList.add(className + '_active');
    }
  }
}
```
## Задание 6. Hit Or Run
