## Задача 1.   
### Изменения фона  
Создайте элемент `<div>`, который изменяет цвет фона при наведении курсора мыши на него и возвращает исходный цвет при уходе курсора мыши.  
`<div id="myDiv">Наведите курсор мыши на этот элемент</div>`  

## Задача 2.   
### Модальное окно  
Создайте элемент` <div>`, который при нажатии на него появляется окно с сообщением "Вы нажали на элемент" и кнопкой "OK". При нажатии на кнопку "OK" окно с сообщением исчезает.  

![image](https://user-images.githubusercontent.com/113675674/221542044-138b134d-985b-4f65-86ad-5dd64d9043a4.png)  
![image](https://user-images.githubusercontent.com/113675674/221542115-60341653-8e0f-4d2f-b400-718fef3b2952.png)  


 ` <div id="myDiv">Нажмите на этот элемент</div>`  

`<!-- Элемент для отображения сообщения -->`  
`<div id="myModal" class="modal">`  
  `<div class="modal-content">`  
    `<p>Вы нажали на элемент</p>`  
    `<button id="closeBtn">OK</button>`  
  `</div>`  
`</div>`  

`/* Стили для модального окна */`  
.modal {  
  display: none; /* скрыть окно по умолчанию */  
  position: fixed; /* фиксированная позиция на экране */  
  z-index: 1; /* установить поверх других элементов */  
  left: 0;  
  top: 0;  
  width: 100%;  
  height: 100%;  
  overflow: auto;  
  background-color: rgba(0,0,0,0.5); /* затемнить фон */  
}  

`/* Стили для содержимого модального окна */`  
.modal-content {  
  background-color: #fefefe;  
  margin: 15% auto;  
  padding: 20px;  
  border: 1px solid #888;  
  width: 80%;  
  text-align: center;  
}  

`/* Стили для кнопки закрытия */`  
#closeBtn {  
  background-color: #4CAF50;  
  color: white;  
  padding: 10px;  
  border: none;  
  border-radius: 5px;  
  cursor: pointer;  
}  

## Задача 3.   
### Кнопки показывающие\скрывающие текст  
Создайте страницу с двумя кнопками. При **нажатии** на одну из кнопок, на странице должен появиться текст. При **наведении** на другую кнопку, текст должен исчезнуть.  
`<button id="showTextButton">Показать текст</button>`  
`<button id="hideTextButton">Скрыть текст</button>`  
`<p id="text" style="display:none">Это текст, который нужно показать и скрыть</p>`   

![image](https://user-images.githubusercontent.com/113675674/221579873-1b9cec38-b7b6-48e4-82af-947a2f956a30.png)  


## Задача 3.1     
### event.target имеет значение  
![image](https://github.com/schoolteacherMP/lecture_46_JS_Interface_Events_Mouse_movement/assets/113675674/3ce13c6a-8f58-4598-99df-2a68b36e8489)  
 
Условия задачи:  

1. На странице есть три блока (div) с классом "box" и разными фоновыми цветами: красный, синий и зеленый.  
2. Когда курсор мыши заходит на первый блок, его фоновый цвет должен изменяться на желтый, независимо от того, с какого блока пришел курсор.  
![image](https://github.com/schoolteacherMP/lecture_46_JS_Interface_Events_Mouse_movement/assets/113675674/b0c821ed-6b9f-4cce-8a47-c6d361f21b83)  
3. При переходе курсора мыши с первого блока на второй блок, цвет второго блока не должен изменяться.  
4. Однако, если курсор мыши переходит с второго блока на третий блок, фоновый цвет третьего блока должен измениться на желтый.  PS: цвет должен изменяться на желтый, независимо от того, с какого блока пришел курсор.  
![image](https://github.com/schoolteacherMP/lecture_46_JS_Interface_Events_Mouse_movement/assets/113675674/974b6fc3-bc91-444b-94bd-0742e1cd04e3)  
5. При захоже на второй блок с `BODY` или `HTML` цвет должен измениться на `red` у второго блока,  а у первого и третьего стать `azure`   Учтите, что  свойство `relatedTarget` может быть `null`.  
Это нормально и означает, что указатель мыши перешёл не с другого элемента, а из-за пределов окна браузера.  
   ![image](https://github.com/schoolteacherMP/lecture_46_JS_Interface_Events_Mouse_movement/assets/113675674/8d7f4366-a71d-496a-ad41-80aef57c1f2e)  

Инструкции:  

1. Создайте HTML-страницу с тремя блоками (div) с классом "box" и разными идентификаторами (id), соответствующими цветам фона.  
2. найдите каждый блок по его идентификатору и добавьте обработчики событий.   
3. Используйте события mouseenter и mouseleave для реализации заданного поведения.  
4. В обработчиках событий проверяйте id целевого элемента, чтобы определить, какой блок должен изменять свой фоновый цвет.  
Примечание:  
Убедитесь, что блоки не имеют отступов между собой, чтобы предотвратить нежелательное изменение цвета при переходе курсора между блоками.
HTML/CSS:    
`<style>`  
     `.box {`  
      `width: 80%;`  
      `height: 100px;`  
      `border: 1px solid black;`  
      `margin: 0 auto;`  
    `}`  
    `#box1 {`  
      `background-color: red;`  
    `}`  
    `#box2 {`  
      `background-color: blue;`  
    `}`  
    `#box3 {`  
      `background-color: green;`   
    `}`  
  `</style>`  
  `<div class="box" id="box1"></div>`  
  `<div class="box" id="box2"></div>`  
  `<div class="box" id="box3"></div>`  

## Задача 4.   
### Создание страницы с формой и отображение введенного текста   
Создайте страницу с формой, содержащей поле ввода и кнопку. При нажатии на кнопку, на странице должен появиться текст, введенный пользователем в поле ввода.  
![image](https://user-images.githubusercontent.com/113675674/221581953-bd2335d5-7ee9-4581-a3f9-33ce1ebd91c6.png)  

`<form>`  
 `<label for="textInput">Введите текст:</label>`  
  `<input type="text" id="textInput">`  
  `<button type="submit" id="submitButton">Показать текст</button>`  
`</form>`  
`<p id="result" style="display:none"></p>`  

Шаги выполнения задачи "Создание страницы с формой и отображение введенного текста":

1. Создать HTML разметку страницы с формой, содержащей поле ввода и кнопку, а также элемент, в котором будет отображаться введенный текст. Добавить стили для элементов на странице.  
2. Получить ссылки на элементы формы с помощью методов document.querySelector и document.getElementById.  
3. Добавить обработчик события на отправку формы с помощью метода addEventListener.  
4. В обработчике события на отправку формы выполнить следующие действия:  
- Отменить действие по умолчанию (отправку формы) с помощью метода event.preventDefault().  
- Получить текст из поля ввода с помощью свойства value и метода trim(), который удаляет лишние пробелы в начале и конце строки.  
- Проверить, что текст не пустой. Если текст не пустой, выполнить следующие действия:  
-- Установить текст в элемент, в котором будет отображаться введенный текст, с помощью свойства textContent.  
-- Показать элемент, в котором будет отображаться введенный текст, установив его свойство display равным "block".  
5. Добавить обработчик события на изменение текста в поле ввода с помощью метода addEventListener.  
6. В обработчике события на изменение текста в поле ввода выполнить следующие действия:  
- Скрыть элемент, в котором будет отображаться введенный текст, установив его свойство display равным "none".  
7. Протестировать страницу, вводя текст в поле ввода и нажимая на кнопку. Проверить, что введенный текст отображается на странице.    


## Задача 5.   
Допустим, у вас есть изображение, которое должно меняться при наведении курсора мыши на него.   
Задача заключается в том, чтобы при наведении курсора мыши на изображение оно становилось ярче, а при уходе курсора мыши из области изображения - возвращалось в исходное состояние.  
`<img id="myImage" src="image.jpg" style='width: 200px; height: 200px;'>`  

PS:img  взять произвольное. Почитать про CSS свойство [brightness](https://developer.mozilla.org/ru/docs/Web/CSS/filter).   

## Задача 6.   
Допустим, у вас есть набор кнопок, каждая из которых представляет собой фрагмент текста, и когда пользователь наводит курсор мыши на кнопку, соответствующий фрагмент текста должен появляться под кнопками.  
`<div id="buttons">`  
 `<button data-text="Привет!">Кнопка 1</button>`   
`<button data-text="Как дела?">Кнопка 2</button>`   
`<button data-text="Что нового?">Кнопка 3</button>`   
`</div>`  
![image](https://user-images.githubusercontent.com/113675674/231223353-b2a35406-ec07-49d2-b844-ad1d726b3c23.png)  
![image](https://user-images.githubusercontent.com/113675674/231223371-dc679d46-43fd-4e68-84b5-e98c9bb52165.png)  
![image](https://user-images.githubusercontent.com/113675674/231223392-201e2032-d35d-4c7d-b649-48ae7f77f3b1.png)  
