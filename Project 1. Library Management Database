library = []

def add_book(title, author, year, copies_available):
    """Adds a new book to the library."""
    book = {
        "title": title,
        "author": author,
        "year": year,
        "copies_available": copies_available
    }
    library.append(book)
    print(f"Book '{title}' by {author} added to the library.")

def borrow_book(title):
    """Decreases the copies available for a book when borrowed."""
    for book in library:
        if book["title"].lower() == title.lower():
            if book["copies_available"] > 0:
                book["copies_available"] -= 1
                print(f"You have successfully borrowed '{title}'. Copies remaining: {book['copies_available']}")
                return
            else:
                print(f"Sorry, no copies of '{title}' are available.")
                return
    print(f"Book '{title}' not found in the library.")

def search_books(query):
    """Searches for books by title or author."""
    results = []
    for book in library:
        if query.lower() in book["title"].lower() or query.lower() in book["author"].lower():
            results.append(book)
    return results

def list_books_sorted():
    """Lists all available books sorted by the year of publication."""
    available_books = [book for book in library if book["copies_available"] > 0]
    sorted_books = sorted(available_books, key=lambda x: x["year"])
    print("\nAvailable books sorted by year of publication:")
    for book in sorted_books:
        print(f"Title: {book['title']}, Author: {book['author']}, Year: {book['year']}, Copies Available: {book['copies_available']}")

# Main interaction loop
def library_system():
    while True:
        print("\nLibrary Management System")
        print("1. Add a new book")
        print("2. Borrow a book")
        print("3. Search books by title or author")
        print("4. List all available books (sorted by year)")
        print("5. Exit")
        
        choice = input("Enter your choice: ")
        
        if choice == '1':
            title = input("Enter book title: ")
            author = input("Enter book author: ")
            year = int(input("Enter publication year: "))
            copies = int(input("Enter number of copies available: "))
            add_book(title, author, year, copies)
        
        elif choice == '2':
            title = input("Enter the title of the book you want to borrow: ")
            borrow_book(title)
        
        elif choice == '3':
            query = input("Enter the title or author to search for: ")
            results = search_books(query)
            if results:
                print("\nSearch results:")
                for book in results:
                    print(f"Title: {book['title']}, Author: {book['author']}, Year: {book['year']}, Copies Available: {book['copies_available']}")
            else:
                print(f"No books found matching '{query}'.")

        elif choice == '4':
            list_books_sorted()

        elif choice == '5':
            print("Exiting the library management system. Goodbye!")
            break
        
        else:
            print("Invalid choice, please try again.")

# Run the system
library_system()
