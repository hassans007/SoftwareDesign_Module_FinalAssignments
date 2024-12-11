# Hassan's Book Shop - Application README

## Overview

Hassan's Book Shop is a Java-based application that provides a seamless bookshop management system. It uses object-oriented programming principles to facilitate a well-structured and efficient system for managing books, customers, and orders. The application is designed to support both admin and customer functionalities, including login, book inventory management, shopping cart operations, and checkout processes.

## Features

- **Admin functionalities:**
  - Admin login and access control.
  - Manage inventory by adding new books.
  - Display available books in the inventory.

- **Customer functionalities:**
  - Customer login and registration.
  - Browse books by title or author.
  - Add books to the shopping cart.
  - Checkout and view the total price.
  - Clear the cart after successful purchase.

## Classes Used

### 1. **Shop Class**
The entry point for the application. It manages the user login process and provides access to admin or customer functionalities. It contains:
- A static array of `Booklist` representing the book catalog.
- A dynamic `List<Booklist>` representing the book inventory.
- A dynamic `List<Customer>` for storing registered customer information.
- A static `Cart` object representing the shopping cart.

### 2. **Booklist Class**
Represents a book in the shop. It includes:
- Properties: `title`, `author`, `publisher`, `availability`, `price`, `quantity`.
- Methods: 
  - Constructor for initializing the book.
  - `getPrice()` to get the price of the book.

### 3. **Cart Class**
Represents a shopping cart for books. It includes:
- A private field `cartItems`, which is a list of `Booklist` objects.
- Methods:
  - `addToCart(Booklist book)` - Add a book to the cart.
  - `displayCart()` - Display the books in the cart.
  - `getCartItems()` - Retrieve the books in the cart.
  - `clearCart()` - Clear the cart.
  
  **Checkout Class** (Static Nested Class):
  - `calculateTotalPrice(List<Booklist> cartItems)` - Calculate the total price of books in the cart.

### 4. **Customer Class (Abstract)**
Represents a customer. It has instance variables like:
- `customerId`, `customerPassword`, `firstName`, `lastName`, `gender`, `dateOfBirth`.

### 5. **RegularCustomer Class**
A subclass of `Customer` that represents a regular customer. It provides:
- A constructor to initialize customer details by calling the superclass constructor.

## Relationship Used

- **Inheritance:**
  - `Cart` class inherits from the `Shop` class (though `Shop` class is assumed to exist).
  - `RegularCustomer` class extends `Customer` class.
  - `Checkout` is a static nested class within the `Cart` class.
  
- **Composition:**
  - `Cart` class contains a list of `Booklist` objects, indicating a shopping cart is composed of multiple books.

- **Abstract Class:**
  - `Customer` class is abstract, meaning it cannot be instantiated directly. It must be subclassed by concrete customer classes like `RegularCustomer`.

## Methods Overview

### 1. **updateInventory(Booklist book)**
- Adds a new book to the inventory and catalog.
- Parameters: `book` - The new book to be added.

### 2. **initializeBook()**
- Initializes the book catalog at the start of the application with predefined books.

### 3. **adminLoginCheck(int adminID, int password)**
- Validates admin credentials for secure access.
- Returns `true` for correct credentials, `false` for incorrect credentials.

### 4. **customerLoginCheck(int customerID, int password)**
- Validates customer credentials for login.
- Returns `true` for correct credentials, `false` for incorrect credentials.

### 5. **adminMenu()**
- Displays options to the admin after successful login, including managing the inventory.

### 6. **customerMenu()**
- Displays options to the customer after login, such as searching books, adding them to the cart, and proceeding to checkout.

### 7. **addToCart(Booklist book)** (Cart class)
- Adds a book to the cart.
  
### 8. **displayCart()** (Cart class)
- Displays the details of books in the cart.

### 9. **getCartItems()** (Cart class)
- Retrieves the list of books in the cart.

### 10. **clearCart()** (Cart class)
- Clears the shopping cart.

### 11. **display(Booklist book)** (Private Helper Method)
- Displays details of a book (title, author, price).

### 12. **calculateTotalPrice(List<Booklist> cartItems)** (Checkout class)
- Calculates the total price of all books in the cart.

### 13. **Customer(int customerId, int customerPassword, String firstName, String lastName, String gender, String dateOfBirth)** (Customer constructor)
- Initializes the customer with personal information.

### 14. **RegularCustomer(int customerId, int customerPassword, String firstName, String lastName, String gender, String dateOfBirth)** (RegularCustomer constructor)
- Initializes a regular customer by calling the superclass constructor.

### 15. **Booklist(String title, String author, String publisher, String availability, double price, int quantity)** (Booklist constructor)
- Initializes a book with provided details.

### 16. **getPrice()** (Booklist class)
- Retrieves the price of a book.

## Application Flow

1. The application welcomes users with login options (1 for Admin, 2 for Customer, 3 to Exit).
2. Admins log in by entering Admin ID and password. Upon success, the admin menu is displayed.
3. Customers can log in using their credentials or register as a new customer. New users are assigned a unique customer ID.
4. Customers can search for books, add them to the cart, and proceed to checkout.
5. At checkout, the total price is displayed, and the customer can confirm the purchase.
6. After purchase, the cart is cleared, and the customer is thanked.

## Admin Functionality

- Admin can log in with the correct admin ID and password.
- Admin can update inventory by adding new books or display all available books.
- Admin can manage the catalog and ensure books are available to customers.

## Customer Functionality

- Customers can log in with an existing customer ID and password or register as a new customer.
- Customers can search for books, add them to the cart, and proceed to checkout.
- The cart shows details of the books, and customers can view the total price at checkout.
- After a successful purchase, the cart is cleared, and the customer is redirected to the main menu.

## New User ID Generation

- When a new customer registers, their ID is generated based on the total number of customers. The new customer's ID is one greater than the last registered customer.

## Existing User and Admin Credentials

- **Admin ID**: 2335
- **Admin Password**: 1122
- **Existing Regular Customer**:
  - Customer ID: 1
  - Customer Password: 12345
  - Name: Hassan Shahid
  - Gender: Male
  - Date of Birth: 2002-07-12

## Book Information

The application is initialized with the following books:

1. **Quantum Physics** by Maaz Hassan
   - Publisher: Hassan
   - Availability: Yes
   - Price: $19.99
   - Quantity: 2

2. **To Kill a Mockingbird** by Harper Lee
   - Publisher: Lippincott
   - Availability: Yes
   - Price: $10.99
   - Quantity: 3

3. **1984** by George Orwell
   - Publisher: Warburg
   - Availability: No
   - Price: $9.99
   - Quantity: 5

4. **The Great Gatsby** by F. Scott Fitzgerald
   - Publisher: Charles Scribner's Sons
   - Availability: Yes
   - Price: $12.99
   - Quantity: 4

5. **The Catcher in the Rye** by JD Salinger
   - Publisher: Little, Brown and Company
   - Availability: No
   - Price: $8.99
   - Quantity: 9

6. **To the Lighthouse** by Virginia Woolf
   - Publisher: The Hogarth Press
   - Availability: Yes
   - Price: $11.99
   - Quantity: 6

## Conclusion

Hassan's Book Shop application is designed to provide an easy-to-use system for managing books, customer information, and shopping activities. It is a great example of object-oriented design using concepts like inheritance, composition, and abstract classes.
