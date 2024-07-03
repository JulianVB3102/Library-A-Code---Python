import os

# ======================= CLASS DEFINITION =======================
class Book:
    """Class to represent a Book with a title and author."""
    
    def __init__(self, title, author):
        self.title = title
        self.author = author

    def __str__(self):
        return f"'{self.title}' by {self.author}"

# ======================= FUNCTIONS =======================
def load_books_from_file(filename="books.txt"):
    """Load books from a file and return a list of Book objects."""
    books = []
    if not os.path.exists(filename):
        return books
    
    with open(filename, 'r') as file:
        for line in file:
            title, author = line.strip().split(',')
            books.append(Book(title, author))
    
    return books

def save_books_to_file(books, filename="books.txt"):
    """Save list of books to a file in CSV format."""
    with open(filename, 'w') as file:
        for book in books:
            file.write(f"{book.title},{book.author}\n")

def display_books(books):
    """Display the list of books in a formatted way."""
    for index, book in enumerate(books, start=1):
        print(f"{index}. {book}")

def add_book(books):
    """Add new books to the list until the user decides to stop."""
    while True:
        title = input("Enter the title of the book (or 'quit' to stop): ")
        if title.lower() == 'quit':
            break
        author = input("Enter the author of the book: ")
        books.append(Book(title, author))
        print(f"'{title}' by {author} has been added!")

        another = input("Do you want to add another book? (yes/no): ").lower()
        if another != 'yes':
            break

def delete_book(books):
    """Delete a book from the list based on user input."""
    display_books(books)
    book_num = int(input("Enter the number of the book you wish to delete: "))
    if 1 <= book_num <= len(books):
        removed_book = books.pop(book_num - 1)
        print(f"Removed {removed_book}!")
    else:
        print("Invalid book number. Please try again.")

# ======================= MAIN PROGRAM =======================
def main(): 
    books = load_books_from_file()
    while True:
        print("\nLibrary Management System")
        print("1. Display books")
        print("2. Add book")
        print("3. Delete book")
        print("4. Save and Exit")
        
        choice = input("Enter your choice: ")
        if choice == '1':
            display_books(books)
        elif choice == '2':
            add_book(books)
        elif choice == '3':
            delete_book(books)
        elif choice == '4':
            save_books_to_file(books)
            print("Books saved. Exiting...")
            break
        else:
            print("Invalid choice!")

if __name__ == "__main__":
    main()

