## to do list

Програма “to do list” – предназначена для создания списка задач. Програма помогает управлять списками дел, 
реализовать запланированые задачи и ничего не забыть.
Пользователь имеет возможность создавать список задач, в процессе их  выполнения, может изменять удалять, 
завершать, сортировать, искать по названию.
 Програма реализована на языке программирования javascript (ES6) c использованием:
1)	Препроцессора  SCSS;
2)	модульный сборщик Webpack;
3)	Transpiler Balel.
### Описание интерфейса програмы:
При клике на кнопку  “Create” обработчиком события addEventListener вызывается модальное окно  для создания 
задачи Рисунок 1. Окно содержит поля названия, описания, выбора приоритета, сохранения и закрытия. На поле для ввода названия
и описания стоит ограничение на количество символов, если количество введенных символов совпадает с максимальным количеством,
вызываются  функции checkDescLength(),checkNameLength() соответственно. В модальном окне у пользователя появляется предупреждающая 
надписить на максимальное количество символов ввода.                                                 
                           ![1images](https://user-images.githubusercontent.com/25788005/67792408-c38c7c80-fa81-11e9-87dd-9fe366b6c836.png)

                           #### Рисунок 1 – Модальное окно для создания задачи.

 Кнопка “Close” закрывает, без сохранения, модальное окно.
Кнопка “Save”, если все поля заполнены, вызывает функцию make() в которой генерируется разметка задачи со
всеми введенными значениями  и выбором смены состояния задачи Рисунок 2.  

![2](https://user-images.githubusercontent.com/25788005/67792492-e74fc280-fa81-11e9-9f2a-fe1f9af06f61.png)
   #### Рисунок 2 – сгенерированный блок с задачей.
Работа с блоком задачи.
В блоке каждой задачи представленна информация :
1 Название;
2 Описание;
3 Приоритет;
4 Меню смены состояния задачи.

![3](https://user-images.githubusercontent.com/25788005/67792502-ee76d080-fa81-11e9-9758-81dac89c3d76.png)
 #### Рисунок 3 – Выпадающее меню для работы с задачей.

Опция  “Done” – завершает работу над задачей, делает ее меню не активным.
 Опция “Edit” – вызывает генерацию модального окна для редактирования. Пользователь может изменить: название, 
 описание, приоритет, сохнанить или отказаться от изменений.

![4](https://user-images.githubusercontent.com/25788005/67792510-f2a2ee00-fa81-11e9-9df5-2f17772cc250.png)
 #### Рисунок 4 – Окно редактирования задачи.
Опция  “Delete”  -  скрывает блок с задачей из области видимости.
Поиск товара по названию с обработчиком oninput в режиме реального времени методом .search() ищет введенные буквы
или символы в названиях задач. Если введенные буквы есть в названии задачи, она остается на экране, все остальные
пропадают, если полу для поиска пустое, все элементы возвращаются на экран.
Фильтровать todo-item по статусу с помощью обработчика событий  onchange на  выпадающее меню, вызывает функцию 
фильтрации блоков задач по статусу выполнения.
Статус “All” – Выводит на экран весь список задач, открытых и выполненных (кроме   удаленных).
Статус “Open” – Оставляет на экране только открытые задачи, которые не имеют статус Done. 
Статус “Done” – Выводит на экран завершённые задачи, остальные скрывает.
Фильтры можно комбинировать, выбирая определённые статусы в выпадающих списках. 
