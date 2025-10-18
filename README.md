# OOP-Activity-6
Activity 6 of OOP

Programming Activity: Library Management System with User Login
 
System Overview
Your program simulates a small Library Management System where registered users can log in, borrow books, return books, and view available books.
All information is stored in three text files:
users.txt – user login details
books.txt – book records
transactions.txt – borrow and return logs
All data will be stored in text files, and your project must be tracked and submitted through a GitHub repository.
 
1. System Flow
Step 1:
 When the program starts, the system prompts the user to log in using a username and password stored in users.txt.
Step 2:
 If the credentials are valid, the user is granted access to the library menu.
 If invalid, display an error message and allow up to 3 attempts before exiting.
Step 3:
 Once logged in, users can:
View all books
Borrow a book
Return a book
Users (optional for admin-type users)(Add, Update, Delete, Display, Exit)
Catalogue (optional for admin-type users)( Add, Update, Delete, Display, Exit)
Transactions (optional for admin-type users) (View all Transactions, View By – User, Book, Exit)
Exit the system
Step 4:
 When exiting, all data updates should be saved to the text files.
 
2. File Requirements
A. users.txt
Stores user information in this format:
U001,John Doe,pass123,user
U002,Jane Smith,abc123,user
A001,Admin,admin123,admin
Fields:
 UserID,Name,Password,Role
Roles:
admin – can add users and books, and can access transactions
user – can only borrow, return, and view books
 
B. books.txt
Stores book records:
B001,The Great Gatsby,F. Scott Fitzgerald,true
B002,To Kill a Mockingbird,Harper Lee,true
B003,1984,George Orwell,false
Fields:
 BookID,Title,Author,Availability
 
C. transactions.txt
Logs all borrowing and returning activities:
T001,U001,B002,2025-10-14,null
T002,U002,B003,2025-10-10,2025-10-13
Fields:
 TransactionID,UserID,BookID,DateBorrowed,DateReturned
 
3. Class Structure
1. Person (Base Class)
Attributes: id, name
Method: displayInfo()
2. User (Subclass of Person)
Attributes: password, role, borrowedBooks (use ArrayList<String>)
Override displayInfo() to show user details
Method: Add, Update, Delete, Display
3. Book
Attributes: bookId, title, author, available
Method: displayBookDetails(), Add, Update, Delete
4. Transaction
Attributes: transactionId, userId, bookId, dateBorrowed, dateReturned
Method: displayTransaction(), displayBy(transaction - User/Book)
5. LibrarySystem (Main Controller)
Attributes:
List<Book> books
List<User> users
List<Transaction> transactions
User loggedInUser
Methods:
displayMenu()
 
4. Exception Handling Requirements
Use appropriate exceptions with try-catch blocks:
FileNotFoundException – if .txt files are missing
IOException – for file read/write errors
NullPointerException – if user or book data is missing
Custom Exception (optional) – for invalid login or unavailable books
 
5. Polymorphism
Show polymorphism by:
Overriding displayInfo() in both Person and User, Books
Using a Person reference to refer to a User object, e.g.:
Person p = new User("U001", "John Doe", "pass123", "user");
p.displayInfo();
 
6. Sample Program Flow
Welcome to the Library Management System
----------------------------------------
Please log in to continue.
 
Username: John Doe
Password: pass123
 
Login successful! Welcome, John Doe.
 
1. View All Books
2. Borrow Book
3. Return Book
4. Exit
Enter choice: 2
 
Enter Book ID: B001
Book borrowed successfully!
 
----------------------------------------
Returning to main menu...
If login fails:
Invalid username or password. Try again.
(Attempts left: 2)
 

Bonus Challenge (Optional)
Add one or more of these features:
Create a search function for books by title or author.
Automatically generate transaction IDs (e.g., T001, T002, etc.).
Add a feature that prevents borrowing more than 3 books at once.


to start the program just press Main.java then run it