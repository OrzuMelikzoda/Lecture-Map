## Объект Map или словарь представляет структуру данных, где каждый элемент имеет ключ и значение. Ключи в рамках словаря являются уникальными, то есть с одним ключом может быть сопоставлен только один элемент. Для создания словаря применяется конструктор объекта

## Map:

```
const myMap = new Map();
```

### Также можно инициализировать словарь начальными значениями. Для этого в конструктор передается массив, элементы которого представляют массивы из двух элементов - первый элемент будет выступать в качестве ключа, а второй - в качестве значения:

```
const myMap = new Map([[1, "a"], [2, "b"], [3, "c"]]);
console.log(myMap);     // Map(3){1 => "a", 2 => "b", 3 => "c"}
```

### В данном случае числа 1, 2, 3 являются ключами, а строки "a", "b", "c" - значениями.

### При этом ключи и значения необзательно должны быть одного типа. Тип ключей и значений может совпадать::

```
const map = new Map([["red", "красный"], ["green", "зеленый"], ["blue", "синий"]]);
console.log(map);  // Map(3) {"red" =>"красный", "green"=> "зеленый", "blue"=>"синий"}
```

## Размер словаря

### С помощью свойства size можно проверить количество элементов в Map:

```
const dict = new Map([["red", "красный"], ["green", "зеленый"], ["blue", "синий"]]);
console.log(dict.size);     // 3
```

## Добавление и изменение элементов

### Для установки значения применяется метод set():

```
const dict = new Map([["red", "красный"], ["green", "зеленый"], ["blue", "синий"]]);
dict.set("yello", "желтый");        // добавление элемента
dict.set("red", "червонный");       // изменение элемента
console.log(dict);      // Map(4) {"red" => "червонный", "green" => "зеленый", "blue" => "синий", "yello" => "желтый"}
```

### Первый параметр метода set() представляет ключ, а второй параметр - значение элемента. Если по такому ключу нет элементов, то добавляется новый элемент. Если ключ уже есть, то уже имеющийся элемент изменяет свое значение.

## Получение элементов

### Для получения элемента по ключу применяется метод get(), в который передается ключ элемента:

```
const dict = new Map([["red", "красный"], ["green", "зеленый"], ["blue", "синий"]]);
console.log(dict.get("red"));  // красный
console.log(dict.get("violet"));  // undefined
```

### Если map не содержит элемента по заданному ключу, то метод возвращает undefined.

### Чтобы избежать возвращения undefined мы можем проверить наличие элемента по ключу с помощью метода has(). Если элемент по ключу имеется, то метод возвращает true, иначе возвращается false:

```
const dict = new Map([["red", "красный"], ["green", "зеленый"], ["blue", "синий"]]);
console.log(dict.has("red"));  // true
console.log(dict.has("violet"));  //  false
 
if(dict.has("red")) console.log(dict.get("red"));   // красный
```

## Удаление элементов

### Для удаления одного элемента по ключу применяется метод delete():

```
const dict = new Map([["red", "красный"], ["green", "зеленый"], ["blue", "синий"]]);
dict.delete("red");  
console.log(dict);  // Map(2){"green" => "зеленый", "blue" => "синий"}
```

### Для удаления всех элементов используется метод clear():

```
const dict = new Map([["red", "красный"], ["green", "зеленый"], ["blue", "синий"]]);
dict.clear(); 
console.log(dict);  // Map(0){}
```

## Перебор элементов

### Для перебора элементов используется метод forEach:

```
const dict = new Map([["red", "красный"], ["green", "зеленый"], ["blue", "синий"]]);
dict.forEach(function(value, key, map){
    console.log(key, ":", value);
})
```

### Метод forEach в качестве параметра получает функцию обратного вызова, которая имеет три параметра. Первый и второй параметры - это соответственно значение и ключ текущего перебираемого элемента, а третий параметр - перебираемый объект Map.

### Консольный вывод данного примера:

```
red : красный
green : зеленый
blue : синий
```

### Также для перебора объекта Map можно использовать циклы, например, цикл for...of:

```
const dict = new Map([["red", "красный"], ["green", "зеленый"], ["blue", "синий"]]);
 
for(item of dict){
    console.log(item[0], ":", item[1]);
}
```

### Каждый элемент из Map помещается в переменную item, которая в свою очередь представляет массив. Первый элемент этого массива - ключ, а второй элемент - значение элемента.

### Также объект Map имеет два дополнительных метода: keys() позволяет перебрать только ключи и values() позволяет перебирать значения элементов. Оба метода возвращают итераторы, поэтому для перебора ключей и значений по отдельности также можно использовать цикл for...of:

```
const map = new Map([["red", "красный"], ["green", "зеленый"], ["blue", "синий"]]);
 
for(item of map.keys()){
    console.log(item);
}
// Консольный вывод:
// red
// green
// blue
for(item of map.values()){
    console.log(item);
}
// Консольный вывод:
// красный
// зеленый
// синий
```


















