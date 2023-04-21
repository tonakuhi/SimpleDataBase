# SimpleDataBase
Это моя первая программа написаная с помощью языка rust. Использует библиотеку rusqlite и базу данных sqlite. База данных (БД) 'data/test.db' являеться шаблоном для произвольного заполнения.

## Функции программы
 - Реализует запрос(-ы) к БД скрытый от пользователя по возможности

## БД
Очередность заполнения данных
    1. Факультет, Должность
    2. Направления, Кадры
    3. Студенты, Предметы
    4. Посещаемость, План\_обучения, Ведомость

Удалять данные желательно в обратном порядке

### Режим "Ведомость"
Выведет данные, которые имеются в таблице `Ведомость`. В данный момент без сортировки.
______

### Режим "Посещаемость"
Выведет данные, которые имеются в таблице `Посещаемость`. Также без сортировки.
______

### Режим "Замена"
    - Принимает файл формата .txt, или любой другой файл в кодировке UTF-8 (другие не проверял)
    - Редактирует файл
    - Выдает результат в файле result.txt
______

#### API режима "Замена"
В исходном файле, который подается программе для преобразования в result.txt имеются следующие ключеые слова:
    - BD.Студенты.Фамилия
    - BD.Студенты.Имя
    - BD.Студенты.Отчество
    - BD.Направления.Дата\_начала
    - BD.Направления.Описание
    - BD.Факультет.Наименование

Используйте их в своем файле для получения данных в любом удобном для вас формате. 

#### Пример
Исходный файл
```
    Студент BD.Студенты.Фамилия отчислен
```

При корректном вводе id студента (Номер зачетки), result.txt будет содержать похожее на
```
    Студент Митюхляев отчислен
```

## Баг
В режиме "Посещаемость" не выводит данные в котором одно из полей рано NULL.