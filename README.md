# Модели данных и системы управления базами данных
## Даниленко Илья, 153502
Проект: Система управления библиотекой

### Функциональные требования:

* Авторизация пользователей (библиотекари, читатели, администраторы).
* Управление пользователями (CRUD - создание, чтение, обновление, удаление пользователей).
* Система ролей (администратор библиотеки, библиотекарь, читатель).
* Журналирование действий пользователей.
* Управление каталогом книг (CRUD - создание, чтение, обновление, удаление книг).
* Регистрация и выдача книг читателям.
* Возврат книг и штрафы за задержку.
* Поиск книг по различным критериям (например: по автору, жанру, названию).
* Управление информацией о читателях (CRUD - создание, чтение, обновление, удаление данных читателей).
* Рецензии на книги и оценки (CRUD - создание, чтение, обновление, удаление рецензий).

### Перечень сущностей БД:
 1. "User"
       * ID (int, not null, pk),
       * Name (varchar, not null),
       * Surname (varchar, not null),
       * email (varchar, not null),
       * password (varchar, not null),
       * Role_id (int, not null) -> Role, FK
 2. "Role"
       * ID (int, not null, pk),
       * Name of role (varchar, not null).
 3. "Book" 
      * ID (id, not null, pk),
      * Name (varchar, not null),
      * Author_id (int, not null) -> Author, FK
      * Genre_id (int, not null) -> Genre, FK
      * Number of copies (int, not null).
      * Publisher (int, not null) -> Publisher, FK
 4. "Reader"
      * ID (int, not null, pk),
      * User_id (int, not null) -> User, FK
      * Library card number (int, not null),
      * Date of birthday (date, not null),
      * Address (varchar, not null),
      * Number of books (int, not null).
 5. "Rent"
      * ID (int, not null, pk),
      * Book_id (int, not null) -> Book, FK
      * Reader_id (int, not null) -> Reader, FK
      * Issue date (date, not null),
      * Rent date (date, not null),
      * Fine (int, not null).
 6. "Log"
      * ID (int, not null, pk),
      * Action (varchar, not null),
      * User_id (int, not null) -> User, FK
      * Datetime (datetime, not null).
 7. "Author"
      * ID (int, not null, pk),
      * Name (varchar, not null),
      * Surname (varchar, not null).
 8. "Genre"
      * ID (int, not null, pk),
      * Name (varchar, not null).
 9. "Review"
      * ID (int, not null, pk),
      * Book_id (int, not null) -> Book, FK
      * Reader_id (int, not null) -> Reader, FK
      * Text review (varchar, not null),
      * Mark (int, not null).
        
10. "Publisher"
      * ID (int, not null, pk),
      * Name (text, not null),
      * Address (text, not null),
      * Number of telephone (varchar, not null).
