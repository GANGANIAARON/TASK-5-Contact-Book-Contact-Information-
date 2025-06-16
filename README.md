# TASK-5-Contact-Book-Contact-Information-
# Store name, phone number, email, and address for each contact.  Add Contact: Allow users to add new contacts with their details.  View Contact List: Display a list of all saved contacts with names and phone numbers.  Search Contact: Implement a search function to find contacts by name or phone number.  Update and Delete

# Simple Contact Book in Python

contacts = {}

def add_contact():
    name = input("Enter name: ")
    phone = input("Enter phone number: ")
    email = input("Enter email: ")
    address = input("Enter address: ")
    contacts[name] = {'phone': phone, 'email': email, 'address': address}
    print("Contact added successfully.\n")

def view_contacts():
    if contacts:
        for name, info in contacts.items():
            print(f"Name: {name}, Phone: {info['phone']}, Email: {info['email']}, Address: {info['address']}")
    else:
        print("No contacts available.\n")

def search_contact():
    search = input("Enter name or phone to search: ")
    found = False
    for name, info in contacts.items():
        if search == name or search == info['phone']:
            print(f"Found - Name: {name}, Phone: {info['phone']}, Email: {info['email']}, Address: {info['address']}")
            found = True
            break
    if not found:
        print("Contact not found.\n")

def update_contact():
    name = input("Enter name to update: ")
    if name in contacts:
        phone = input("Enter new phone: ")
        email = input("Enter new email: ")
        address = input("Enter new address: ")
        contacts[name] = {'phone': phone, 'email': email, 'address': address}
        print("Contact updated.\n")
    else:
        print("Contact not found.\n")

def delete_contact():
    name = input("Enter name to delete: ")
    if name in contacts:
        del contacts[name]
        print("Contact deleted.\n")
    else:
        print("Contact not found.\n")

def main():
    while True:
        print("\n--- Contact Book Menu ---")
        print("1. Add Contact")
        print("2. View Contacts")
        print("3. Search Contact")
        print("4. Update Contact")
        print("5. Delete Contact")
        print("6. Exit")

        choice = input("Choose an option: ")

        if choice == '1':
            add_contact()
        elif choice == '2':
            view_contacts()
        elif choice == '3':
            search_contact()
        elif choice == '4':
            update_contact()
        elif choice == '5':
            delete_contact()
        elif choice == '6':
            print("Exiting Contact Book. Goodbye!")
            break
        else:
            print("Invalid choice. Try again.\n")


    main()
