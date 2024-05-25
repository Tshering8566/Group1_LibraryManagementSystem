# Library Management System - Design Pattern Project

## Overview

The Library Management System is a project developed to manage a library's operations including book cataloging, user management, and borrowing/returning books. This system utilizes various design patterns to ensure code reusability, scalability, and maintainability.

## Features

- **Book Management**: Add, remove, and search for books.
- **User Management**: Register, update, and delete user profiles.
- **Borrowing System**: Issue and return books.
- **Notifications**: Notify users about due dates and overdue books.
- **Reporting**: Generate reports for book inventory and user activity.

## Design Patterns Used

1. **Singleton Pattern**: Ensures a class has only one instance and provides a global point of access to it. Used for managing the database connection.
2. **Factory Pattern**: Creates objects without specifying the exact class of the object that will be created. Used for creating different types of notifications.
3. **Observer Pattern**: Defines a one-to-many dependency between objects so that when one object changes state, all its dependents are notified. Used for implementing the notification system.
4. **Decorator Pattern**: Adds behavior to objects dynamically. Used for enhancing the functionalities of book objects.
5. **Strategy Pattern**: Defines a family of algorithms, encapsulates each one, and makes them interchangeable. Used for different search strategies in the book catalog.

## Installation

To run this project, ensure you have the following installed:

- Python 3.8+
- SQLite (or any other database you prefer)

### Steps

1. **Clone the repository**:

   ```bash
   git clone https://github.com/yourusername/library-management-system.git
   cd library-management-system
   ```

2. **Create a virtual environment and activate it**:

   ```bash
   python -m venv venv
   source venv/bin/activate  # On Windows use `venv\Scripts\activate`
   ```

3. **Install dependencies**:

   ```bash
   pip install -r requirements.txt
   ```

4. **Setup the database**:

   ```bash
   python setup_database.py
   ```

5. **Run the application**:
   ```bash
   python app.py
   ```

## Usage

Once the application is running, you can perform the following operations:

### Book Management

- **Add a book**:

  ```python
  from library import Library

  library = Library.get_instance()
  library.add_book('The Great Gatsby', 'F. Scott Fitzgerald', '9780743273565')
  ```

- **Search for a book**:
  ```python
  results = library.search_books('gatsby', strategy='title')
  for book in results:
      print(book)
  ```

### User Management

- **Register a user**:

  ```python
  from user import User

  user = User('john_doe', 'John Doe', 'john@example.com')
  user.register()
  ```

### Borrowing System

- **Issue a book**:

  ```python
  user.borrow_book('9780743273565')
  ```

- **Return a book**:
  ```python
  user.return_book('9780743273565')
  ```

## Contributing

1. **Fork the repository**.
2. **Create a new branch**:
   ```bash
   git checkout -b feature/your-feature-name
   ```
3. **Commit your changes**:
   ```bash
   git commit -m 'Add some feature'
   ```
4. **Push to the branch**:
   ```bash
   git push origin feature/your-feature-name
   ```
5. **Create a new Pull Request**.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

## Contact

For any inquiries or feedback, please contact [your-email@example.com](mailto:your-email@example.com).
