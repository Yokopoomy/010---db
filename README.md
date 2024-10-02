## Запросы для вставки данных о двух книгах в коллекцию books:

```
db.books.insertOne({
 title: "Время для звёзд",
 description: "Нестандартная концепция перемещения в пространстве и принципа работы звездолета, новый взгляд на пространство-время.",
 authors: "Роберт Хайнлайн"
})
```

```
db.books.insertOne({
 title: "Ночной Дозор",
 description: "История вечного противостояния Светлых и Темных магов. Тайные боевые операции, жестокие интриги и высокая политика, белое пламя любви и ненависти, где плавятся судьбы людей и Иных, отстаивающих свою истину...",
 authors: "Сергей Лукьяненко"
})
```

## Запрос для поиска полей документов коллекции books по полю title:

```
db.books.find(
 { title: "Ночной Дозор" },
 { title: 1, description: 1, authors: 1}
)
```

## Запрос для редактирования полей description и authors коллекции books по _id записи:

```
db.books.updateOne(
{_id: 1 }
 { $set: { authors: "Сергей Лукьяненко, Владимир Васильев", description: "«Ночные охотники» городских улиц. Вампиры и оборотни, колдуньи и ведьмаки. Те, что живут в часы, когда опускается на землю мгла. Те, что веками противостоят силам белых магов. Потому что понимают — равновесие должно быть соблюдено. Потому что понимают — Тьма для этого мира не менее важна, чем Свет." } }
)
```