<!-- 
<details> <summary>  HTML </summary>  </details> 
-->

# JavaScript Fundamentals 
###  Черновик с курса The Complete JavaScript Course 2022: From Zero to Expert! 

<details> <summary>  переменные </summary> 

  Обьявление переменной. Есть несколько операторов для этого: 
  
  `let` -  создание переменной с возможностью изменить в будщем. <strong>Can be mutated. </strong>
  
  `const` - создание переменной без возможности давать новое значение. <strong>Immutable variable.</strong>
  
  `var` - полностью как let
  
  <strong>Как их использовать?</strong> Для чистоты кода: обычно const, и let только когда уверены, что её нужно будет менять. Например: год рождения - конст, возраст - лет. Одно - не меняется, второе - да.
  
`let & const` - с обновления ES6, so they are modern JavaScript. const нельзя давать undefined. `var`- старый вариант обьявление переменных, лучше его избегать.
  
 Пример обьявления переменной
  
    let fistname='Jonas';

  #
</details> 

<details> <summary>  types of data </summary> 
  
Есть два вида значений - обьекты и примитивные, все остальные.
  
Примитивные:
  
<strong>`Number`</strong> -Число с плавающей точкой. 23 = 23.0 в js.

<strong>`String`</strong> - просто текст.


<strong>`Boolean`</strong> - логический вид, принимает True/False

  
`Undefined` - Обьявленная переменная без значения, но позже может получить его.

`Null` - Обьявленная переменная но без значения, и дать значение ей его нельзя.

`Symbo` (ES2015)- Переменная с значением, что нельзя изменить. Подробности будут в конце курса.

`BigInt` (ES2020) - Может хранить огромные целые числа.

Пять значений что будут значить в false, когда мы пытаемся преобразовать их boolean. 

`0, '', undefined, NaN, null` except of `falce` of course

<strong>JavaScript has dynamic typing: </strong>В JS в первых трёх типах нет необходимости обозначать тип данных в переменной, как в других языках. Он определяется сам. <strong>И тип данных хранит Само Значение, а не переменная. То есть бокс хранит значениe, что имеет тип данных</strong> Это значит, что можно без проблем менять тип данных в переменной.

Можно менять типы данных между собой - только первые три. Функции для этого - в отдельной вкладке. <strong>Type Coersion:</strong>Так же js меняет типы данных автоматически: для операторов, использующих цифры, как `* ** / -` преобразует тип в намбер. `console.log('23'-'10'*3);` при компиляции выдаст число, а не ошибку. А оператор `+` наоборот - с намберов делает стринги, что бы скомпилировать код и соеденить разные типы данных: `const jonas = "i'm " + 45 + "and another im " + 23;`. В другом языке нужно было бы писать ` + String(23);`, так как плюсование разных типов данных невозможно - будет ошибка. Но не в джаве. 

Классный пример, нужно угадать ответ: 
  
    let n = "1" + 1;
    n = n - 1;
    console.log(n);

  <details><summary>  answer </summary> 10 </details>
  
 #

</details> 

<details> <summary>  операторы </summary> 
  
So an <strong>operator</strong> basically allows us to transform values or combine multiple values and really do all kinds of work with values. Есть много видов операторов, по порядку:
<details> <summary>  mathematical or arihmetic operators </summary> 
  
`+` `-` `/` `*` - очевидные операторы. `console.log(ageJonas * 2, ageJonas / 10);`

`**` - возвести в степень. `2 ** 3;` = 8

`+=` `-=` `*=` `/=`- операция к текущему значению. Пример: `x *= 10;` равно `x = x * 10;`
  
 `++` `--` - Прибавляет/отнимает к текущему значению 1. Example: `x++;` равно `x=x+1;`
  
 Операторы сравнения

`>` `<` `>=` `<=` - сравнивают значения, и возвращают результат в типе boolean. Example: `console.log(200>100)` return: `true`.

`===` & `==` - приравнивают значения. Но тройной - строгий. Двойной - делает коррекцию типов. То есть двойной оператор покажет одно чилсло в двух видах - string & number равными, вернёт `true`. А строгий - вернёт `falce`, так как он не корректирует типы.

`!==` & `!=` - Такой же прикол как и свехру, только знак неравенства

  <strong>Лучше юзать строгий - так как с коррекцией полон тайн и загадок, и может быть причиной неожиданных багов. Негласное правило для чистоты кода.</strong>

##
  </details> 

<details> <summary>  and, or & not operators </summary> 

<img src="https://i.ibb.co/2PKDrXR/image.png" alt="image" width="65%">

Логика работы их с булеаном на картинке. Пример использования всех трех: 
  
    console.log(driversLicense && goodVision);
    console.log(driversLicense || goodVision);
    console.log(!goodVision);
  
##
  </details> 

<details> <summary> Condition operator </summary> 

Он похож на if else, но не находиться в одном разделе с ним потому чтоэто оператор. То есть он даёт после себя значение. Condition operator - is expression. Синтаксис: 

    условие ? если true : если false;
  
Из нюансов - в него можно поместить только одну строку. Пример использования 

    const drink = age >= 18 ? "wine" : "water";

В зависимости от значения переменной `age` присваивает разные значения переменной `drink`. Как короткий if else. Но что важнее - он возвращает значение: 

    console.log(`I like to drink ${age >= 18 ? "wine" : "water"}`);

Сюда бы запихать if else не вышло - это statement, будет ошибка. А для таких мелких решений идеально подойдёт Condition operator.


 ##
  </details>
  
  У разных операторов есть разный приоритет. Это обьясняет, почему в сравхениях двух примеров перед сравнением он считает эти примеры - у операторов сравнения низкий приоритет. Их список можно глянуть на mdn. Так же у разных операторов разный порядок начала считывания - с левой стороны примера или правой. Мб пригодится в дебагинге.
  
  Другие операторы:

`typeof` - выдаёт тип данных переменной или текста после оператора. ! багует при попытке определить тип значения null.
  
#
</details> 

<details> <summary>  Не большие разделы </summary> 

##
  
<details> <summary>  Template literals </summary> 
  С ES6 новый путь вывода strings вместе с переменными. Как было раньше: 
  
  
    const jonas =
    "i'm " + firstName + ", a " + (now - birthYear) + " years old " + job + "!";

  А вот новый путь

    const jonasNew = `I'm ${firstName}, a ${now - birthYear} years old ${job}!`;
  
  То есть для вставки переменных и кода не нужно использовать операторы. Ахуенно! Так же для пепреноса на другую строку достаточно перенести на другую строку в коде, операторы не нужны
  
 I'm Jonas, a 46 years old teacher!
  
##

  </details> 
  
<details> <summary>  IF ELSE </summary> 
  
  Data structure. Состоит из блоков кода.  И любая переменная, которую мы объявляем внутри одного из этих блоков не будет доступа снаружи блока.
  
    if (оцентиаветься) {
    Если положительное - этот код испольняется
    } else {
    если falce в оценке - этот
    }

  Так же можно писать действие без скобок - если оно не большое, в одну строку с функцией
  
    if (age === 18) console.log("YAY");

  Есть ещё разширенная функция - `else if` - идёт после иф перед елсе. Создаёт дополнительное условие, их может быть неограниченное количество

Так же что бы вывести значение с иф елс - нужно его задекларировать снаружи. Ведь все переменные, что мы создадим внутри блоков - не будут доступны снаружи

  ##
  </details> 

<details> <summary> SWITCH </summary> 

`switch` заменяет иф елсе, если нужно в зависимости от разных значений одной переменной выдадть разный результат. То есть тут только одна переменная проверяется. Вот пример:  

    switch (day) {
     case "monday": // day === 'monday'
       console.log("plan course structure");
        console.log("go to coding meetup");
        break;
     case "tuesday":
       console.log("prepare videos");
        break;
     case "wednesday":
      case "thursday":
       console.log("write code exapmles");
       break;
     case "friday":
      console.log("record videos");
      break;
    case "saturday":
    case "sunday":
       console.log("Enjoy the weekend :D");
       break;
    default:
      console.log("not a valid day");
   }

Тут после кейса указываем значение, и после код который он выполнит. После закрыть этот блок кода - бреак, и в конце `default`- в случаэ если все кейсы получат false. Простая и удобная функция



 ##
  </details> 
  

<details> <summary> Expressions & Statements </summary> 

Есть два вида кода - те что дают значение, и те что нет. Зачем это - в разных местах джс ожидает одно из двух - либо expression, либо statement(declaration). <string>Пример:</strong>

    if(23>10) {
        const str = "23 is bigger";
    }

Где можно считать весь код - statement, а вот `"23 is bigger"` в нём - expression. Так же код завершаюшийся на `;` - точно statement. а `120-338` или `true && false && !false` - expression, он даёт после себя значение. А вот сам if else блок в примере - просто прогоняет комманды последовательно, что-то делает но ничего не возвращает.


 ##
  </details> 
  
#
  </details> 

<details> <summary>  Функции </summary>  

Блоки кода, что можно вызвать. Так же есть заготовленные уже, выполняют какую-либо функцию
  
У функций есть несколько типов. Это - декларирующая. Из разницы - декларирующую можно вызвать ещё до ее обьявления. Фцию выражения - нет.

    function calcAge1(birthYear) {
     return 2022 - birthYear;
    }

Это функция - выражение, Expression. Из разницы - функция без имени, и то что возвращает сразу записывает в переменную

    const calcAge2 = function (birthYear) {
      return 2022 - birthYear;
    };

Arrow function. короткая. Если в одну строку - можно без {} и без return  - они уже вшиты и будут работать автоматом. Разница - тут нет кейворда её вызова, подробнее - позже в курсе.

    const calcAge3 = (birthYear) => 2022 - birthYear;
  
Переоброзование String to Number: `console.log(Number(inputYear));` Если приобразовать не цифры - выдаст NaN - Not a Number.(Технически это неправильная цифра)
  
  В обратно направлении тоже работает: `console.log(String(23));` <string>Важно: необходимо писать с большой буквы, иначе не сработает.</string>

  `prompt("What do u want to know about Jonas?");` - функция вывода всплывающего окна. В переменной возвращает введённый текст

  #
  
  </details> 
  
  <details> <summary>  Array </summary>  

### Базовые операции:

Обьявление:

    const friends = ["Michael", "Steven", "Peter"];
    const y = new Array(1991, 1984, 2008, 2020, 2018);
    
Изменение:`friends[2] = "Jay";`, `years[years.length - 1]`, `years.length`

### Методы - встроенные функции для работы с массивами. Как операторы для массивов
    
 `friends.push("Jay", 1552);` - изменяет массив, добавляя к нему новые значения в конец. `friends.unshift("John");`Добавляет в начало.  Так же сама по себе функция являеться Expression - возвращает длину нового массива: `const newLength = friends.push("Jay", 1552);` - Переменная будет хранить длину обновлённого массива.

`friends.pop();` - Убирает последний елемент массива. Так же и возвращает его. `friends.shift("John");` - убирает первый.

`friends.indexOf("Peter")` - Возвращает номер указанного елемента. Если елемента нет - вернёт -1.

`friends.includes("Peter")` - ES6, более современная версия предыдущего, проверяет на наличие елемент и возвращает буллиан. Проверяет без type coersion, как `===`. Можно круто сочетать с if else.
    

  #
  
  </details> 
  
  <details> <summary>  Objects </summary>  

Обьект имеющий 5 свойств

    const jonasObject = {
      firstname: "Jonas",
      lastname: "Schmedtmann",
      age: 2022 - 1991,
      job: "teacher",
    friends: ["Michael", "Steven", "Peter"],
    };

Два пути получения данных с обьекта: 

`console.log(jonasObject.lastname);` //Первый - через точку. Тут можно указывать ТОЛЬКО имя свойства
`console.log(jonasObject["firstname"]);` // Второй - как с массива, но его плюс: можно вставлять expression's

`    this.bmi = this.mass / this.height ** 2;` - добавление нового свойства в обьект



  #
  
  </details> 
  
  <details> <summary>  For loop </summary>  

Loops - data structure

    for (let ex = 1; ex <= 4; ex++) {
      console.log(`-----Starting exercise ${ex}-----`);

      for (let rep = 1; rep < 6; rep++) {
        console.log(`Lifting weigths repetition ${rep} 🏋️`);
      }
    }

(`let rep = 1`; `rep < 6`;` rep++`) где первая часть - обьявление переменной, вторая - проверка, и третья - смена после прохождения цикла


  #
  
  </details> 
