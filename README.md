# HTML & CSS knowledge
an summary from course

## HTML
Начинать каждый док с `<!DOCTYPE html>` - говорит браузеру что мы вообще используем

`<html></html> `- Елемент для содержания в себе `<head> & <body>`. Хоть пустые, но они должны быть прописаны.

Атрибуты k нему:

lang - язык. EN, DE, UA.
	
#### head  - контент, что не рендериться, невидемый на странице. Как имя в закладке, описание сайта в его ссылке и тд.

Именно сюда вводится Internal CSS, или подключаеться External CSS. Подробнее - ниже.

`<title></title>` - Текст на вкладке сверху.

`<meta charset="UTF-8" />` - описывает данные. So metadata means data about the data. 

Атрибут charset - описывает кодировку символов (указанная - стандарнтая). 
	
#### body - имеет в себе основное наполнение сайта, контент

`<h1></h1>` - Заголовок, имеет 6 уровней. // Лучше использовать h1 один раз в одной странице на практике

`<p></p>` - Параграф
  
`<b></b>` - Жирный текст. Но это старая функция.
  
`<strong></strong>`  - Тоже жирный, но с html 5 имеет особое значение в коде, больше рекомендуеться к использованию чем `<b>`
  
`<i></i>` - курсив, но старый
  
`<em></em>` - курсив html 5, рекомендуеться к использованию
	
### СПИСКИ
`<ol></ol>` - order list. Список с цифрами. В него входит `<li>`

`<il></ul>` - unordered list. Список с точками. В него входит `<li>`

`<li></li>` - list item. Елемент списка

Пример: 	

	 <ol>
   
      <li>The opening tag</li>
      
      <li>The closing tag</li>
      
      <li>The actual element</li>
      
    </ol>
	
	
### ФОТО
`<img  />` - вывод фото. Не требует отдельного закрытия. Вызываеться в паре с атрибутами.

Атрибуты:

Используються для описания елементов. Находяться внутри вызова функции.

src (sourse) - указывает расположения файла

alt (alternative text) - описывает картинку, что бы гугл понимал что там, для SEO. Так же помогает слепым людям. Нельзя 
пропускать, всегда важно писать хорошее описание.

width - Количество пикселей ширины картинки. Полезно для уменьшения размера.

height - Количество пикселей высоты картинки. // лучше использовать зная разрешение картинки. Что бы не исказить её.

Пример вызова фото с атрибутами:

	 <img
      src="post-img.jpg"
      alt="HTML code on a screen"
      width="500"
      height="200"
    />

### Ссылки
`<a></a>` (anchor) - Функция призыва гмперссылки. Внутри кликабельный текст для перехода

href - атрибут для подкрепления ссылки, на которую идёт переход. # - вверх к текущей странице.

target - Указывает где открыть гиперссылку. Без указания функции - вместо текущей страницы. 

`target="_blank"` - на новой вкладке. 

Пример использования: 

    <a href="https://developer.mozilla.org/ru/docs/Web/HTML" target="_blank">MDN Web Docs</a>
<a href="https://developer.mozilla.org/ru/docs/Web/HTML" target="_blank">MDN Web Docs</a>

### Semantic HTML

Итак, в HTML, когда мы говорим о семантике, мы имеем в виду, что некоторые элементы на самом деле смысл или цель, связанная с ними.

Поэтому, когда мы думаем об определенном HTML-элементе, на самом деле нам не следует думать о том, как этот элемент выглядит при отображении на странице. Но вместо этого мы должны подумать о том, что на самом деле означает этот элемент и для чего он тут. Таково в основном определение семантического HTML.

`<strong>` - So again, by using the strong element here, the text will still look bold here in the browser, but what really matters here is that we now assign some meaning to this content here. We now say that is a strong content, which means basically a very important piece of content and the same here for this piece. So this fundamental word here.

Тоже самое для курсива - `<em>`

#### <strong>Box. Коробки с контеном.</strong>

Пока не совсем понимаю их пользу. Когда узнаю опишу тут.

`<nav></nav>` - Контейнер для навигации. //The nav element represents a section of a page that links to other pages or to parts within the page: a section with navigation links.

`<div></div>` - Тоже контейнер, но без предназначения. //And so now we should only use the div element when we don't want to attach a certain meaning to a certain container.

`<article></article>` - Тоже контейнер

`<header></header>` - Тоже контейнер, для заголовка контента. Примеры: Для страницы - заголовок, имя сайта. Для поста - тема поста, фото и имя автора.

`<footer></footer>` - Тоже контейнер, для ниженого артикула

`<p></p>` - тоже сюда относиться, контент с значением.

`<aside></aside>` - элемент aside обычно используется для дополнительной информации, дополняющей основную часть страницы. Так что в данном случае основная часть страницы — это article. А затем в стороне, которая является вторичной информацией, в основном это некоторые связанные посты, которые относятся к статье, то есть к основной части.
 
 <strong>Это всё помогает SEO</strong>


# CSS 
### Cascading Style Sheets

Три места, где можно писать CSS:
<ul>
	<li>inline CSS</li>
	<li>internal CSS</li>
	<li>external CSS</li>
</ul>

### Inline - прописываеться внутри елемента.

Пример:
 ` <h1 style="color: blue">📘 The Code Magazine</h1>`
 
 На больших сайтах использовать Inline для каждого текста и указывать стилистику будет слишком долго, текст будет раздувать, и редактировать крайне неудобно. Лучше никогда не использовать эту хуйню.
 
 
 ### Internal & External.
 `<style></style>` - Функция для Internal, в которой прописываются все исменения CSS Для страницы. Сувать в `<head>`
 
 CSS - Язык для стилистики кода хтмл. Ещё лучше  использовать external, то есть в отдельном файле. B нём будет удобнее редактировать: не одну длинейшую страницу, а две средних. По этому external - оптимальный. Да и лектор его использует. Дальше о нём.
 
 
Но если комманды CSS находяться не в доке хтмл, без подключения он не будет знать о его существовании. Пример подключения External, прописывается в `<head>`:

    `<link href="style.css" rel="stylesheet" />`
    
Где link - функция подключения, href - путь, rel - указывает, что мы подключаем StyleSheet(ебу что это, препод сказал).    

### С подключением всё. Как он устроен:

 Для начала нужно указать, какой именно елемент мы будем украшать.  В примере - все заголовки `<h1>`.
 
 `h1 {`
 
  `color: blue;`
  
`}`
   
Это - одно правило. Rule. В CSS Их будет много. Из чего оно состоит:

<img src="https://i.ibb.co/nCvWHN0/Screenshot-1.png" alt="Screenshot-1" border="0">

<ul> 
	<li>Всегда начинаеться с селектора. Указываем, что именно менять.</li> 
	<li>Дальше открываем блок деклараций, куда их и вписываем.</li> 
	<li>Деклараций может быть много, у каждей своё свойство и значение. Перечислять их через `;` .</li> 
</ul>

### Propetries to style text

---

### color

Цвет:

`color: blue;`

Тут blue - keyword. Обычно нужно указать цвет его кодом.

---

### font-size

Размер:

`font-size: 26px;`

26 - колово пикселей, что будет занимать текст на екране.

---

### font-family

Шрифт:
	
`font-family: sans-serif;`

Нужно выбрать один из предустановленных шрифтов. Иначе на других пк не загрузит. Как это исправить потом обновлю здесь.

---

### text-transform

Смена размеров(капс, прописные) текста
	
`text-transform: uppercase;`

Выбранный - весь текст капсом. Много вариантов. 

---

### font-style

Вид текста.
Курсив, жирный.

`font-style: italic;`

Указан - курсив.

---

### line-height

Межстрочный интервал

`line-height: 1,5;`

Тут все очевидно, хули уточнять.

---

### text-align

Выравнивание текста на странице

`text-align: center;`

Указан - в центре	

