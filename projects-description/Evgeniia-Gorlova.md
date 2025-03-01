# Горлова Евгения 
---

## Описание предметной области 

Администратор интернет-турагенства 
Мобильная версия админки интернет-турагенства, которая будет предоставлять возможности для просмотра каталогов туров, отелей. 
Функциональность представляемая правами администратора: сортировка, фильтрация по различным полям, добавление, удаление и редактирование.

### Стек 
TypeScript, React, Nextjs.

---

## Описание страниц 

- Главная страница это список всех туров, где каждый тур представлен краткой карточкой с основной информацией:
  - фотография;
  - длительность тура;
  - даты;
  - страна;
  - тип путешествия;
  - цена.
- Страница с добавлением деталей товара:
  - Фото (компонент для отображения изображений).
  - Форма для редактирования (форма с валидацией).
    - тип путешествия (экскурсионный тур, пляжный отдых и т.д.);
    - сезон путешествия (в зависимости от страны, например цветение сакуры, красные клёны);
    - турагенство, с которым сотрудничают;
    - название;
    - длительность;
    - варианты заселения;
    - цена;
    - описание по дням;
    - страна;
    - наличие свободных мест.
  - Аналогично страница с редактированием тура.
  - Страница удаления - подтверждение удаления.
  - Кастомные страницы ошибок:
    - 404
    - 500
  - Для навигации:
    - кнопки;
    - таббар.
### Фильтрация 

- Фильтрация по:
  - типу;
  - дате;
  - цене от и до;
  - длительности;
  - стране. 
       
### Сортировка (для каждого параметра будет реализована по возрастанию и убыванию) 

- Сортировка по:
  - цене;
  - длительности;
  - типу.
 
---

## Список ARI 

- **Эндпоинт:** `/products`

  - **Http метод:** `GET`
  - Возвращает список туров для выбранной страницы с возможно заданной сортировкой и фильтрацией.
  - **Параметры:**
  - `page: number`
  - `countPerPage: number | undefined`
  - `orderBy: SortingKey | undefined`
  - `filters: Filters | undefined`
  

  - **Http метод:** `POST`
  - Добавляет тур с указанными параметрами.
  - **Параметры**
  - Все параметры, описывающие добавляемый товар.


- **Эндпоинт:** `/products/{id}`

  - **Http метод:** `GET`
  - Возвращает информацию о туре по id.
  - **Параметры**
  - id

  - **Http метод:** `PATCH`
  - Изменяет информацию о туре по id.
  - **Параметры**
  - id
  - Параметры, которые необходимо изменить.
    
  - **Http метод:** `DELETE`
  - Удаляет информацию о товаре по id.
  - **Параметры**
  - id
