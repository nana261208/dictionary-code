# dictionary-code
from tkinter import *
import tkinter.messagebox as messagebox

# Dictionary of languages and their translations
languages = {
    "hausa": {
        "hello": "ina kwana",
        "goodbye": "sai anjima",
        "please": "don allah",
        "thank you": "nagode",
        "yes": "ee",
        "no": "bai",
        "cat": "biri",
        "dog": "kare",
        "house": "gida",
        "food": "abinchin",
        "water": "ruwa",
        "friend": "aboki",
        "family": "iyali",
        "love": "soyeya",
        "school": "makaranta",
        "book": "takada",
        "car": "motar",
        "city": "gari",
        "happy": "murna",
        }
}
yoruba_dictionary = {
    "ile": "house",
    "ounje": "food",
    "ile-iwe": "school",
    "omi": "water",
    "aago": "clock",
    "owo": "money",
    "aja": "dog",
    "omo": "child",
    "ara": "body",
    "iye": "mother",
    "baba": "father",
    "oju": "eye",
    "eti": "ear",
    "ori": "head",
    "ese": "leg",
    "apa": "arm",
    "ogun": "war",
    "ewa": "beauty",
    "iwe": "book",
    "wa": "come"
}
# Function to display menu
def display_menu():
    print("\nWelcome to the Yoruba Dictionary")
    print("1. Search for a word")
    print("2. Add a new word")
    print("3. View all words")
    print("4. Exit")

# Function to search for a word
def search_word():
    word = input("Enter the Yoruba word to search: ").strip()
    meaning = yoruba_dictionary.get(word)
    if meaning:
        print(f"{word}: {meaning}")
    else:
        print(f"The word '{word}' is not in the dictionary.")

# Function to add a new word
def add_word():
    word = input("Enter the Yoruba word: ").strip()
    meaning = input("Enter the meaning in English: ").strip()
    if word in yoruba_dictionary:
        print(f"The word '{word}' already exists in the dictionary.")
    else:
        yoruba_dictionary[word] = meaning
        print(f"The word '{word}' has been added successfully.")

# Function to view all words
def view_words():
    if yoruba_dictionary:
        print("\nYoruba Dictionary:")
        for word, meaning in sorted(yoruba_dictionary.items()):
            print(f"{word}: {meaning}")
    else:
        print("The dictionary is empty.")

# Main program loop
def main():
    while True:
        display_menu()
        choice = input("\nEnter your choice (1-4): ").strip()

        if choice == "1":
            search_word()
        elif choice == "2":
            add_word()
        elif choice == "3":
            view_words()
        elif choice == "4":
            print("Thank you for using the Yoruba Dictionary. Goodbye!")
            break
        else:
            print("Invalid choice. Please select a valid option.")

if __name__ == "__main__":
    main()
yoruba_dictionary = {
    "ile": "house",
    "ounje": "food",
    "ile-iwe": "school",
    "omi": "water",
    "aago": "clock",
    "owo": "money",
    "aja": "dog",
    "omo": "child",
    "ara": "body",
    "iye": "mother",
    "baba": "father",
    "oju": "eye",
    "eti": "ear",
    "ori": "head",
    "ese": "leg",
    "apa": "arm",
    "ogun": "war",
    "ewa": "beauty",
    "iwe": "book",
    "wa": "come"
}
# Function to display menu
def display_menu():
    print("\nWelcome to the Yoruba Dictionary")
    print("1. Search for a word")
    print("2. Add a new word")
    print("3. View all words")
    print("4. Exit")

# Function to search for a word
def search_word():
    word = input("Enter the Yoruba word to search: ").strip()
    meaning = yoruba_dictionary.get(word)
    if meaning:
        print(f"{word}: {meaning}")
    else:
        print(f"The word '{word}' is not in the dictionary.")

# Function to add a new word
def add_word():
    word = input("Enter the Yoruba word: ").strip()
    meaning = input("Enter the meaning in English: ").strip()
    if word in yoruba_dictionary:
        print(f"The word '{word}' already exists in the dictionary.")
    else:
        yoruba_dictionary[word] = meaning
        print(f"The word '{word}' has been added successfully.")

# Function to view all words
def view_words():
    if yoruba_dictionary:
        print("\nYoruba Dictionary:")
        for word, meaning in sorted(yoruba_dictionary.items()):
            print(f"{word}: {meaning}")
    else:
        print("The dictionary is empty.")

# Main program loop
def main():
    while True:
        display_menu()
        choice = input("\nEnter your choice (1-4): ").strip()

        if choice == "1":
            search_word()
        elif choice == "2":
            add_word()
        elif choice == "3":
            view_words()
        elif choice == "4":
            print("Thank you for using the Yoruba Dictionary. Goodbye!")
            break
        else:
            print("Invalid choice. Please select a valid option.")

if __name__ == "__main__":
    main()

def translate():
    selected_language = languages_var.get()
    word = word_entry.get().strip().lower()

    if selected_language in languages and word in languages[selected_language]:
        translation = languages[selected_language][word]
        messagebox.showinfo("Translation", f"{word} in {selected_language}: {translation}")
    else:
        messagebox.showwarning("Warning", "Word not found or language not supported.")

# Create the main window
root = Tk()
root.title("Multi-Language Translator")

# Create and pack widgets
Label(root, text="Enter an English word:").pack(pady=10)
word_entry = Entry(root, width=30)
word_entry.pack(pady=10)

# Dropdown for language selection
languages_var = StringVar(value="Select Language")
OptionMenu(root, languages_var, *languages.keys()).pack(pady=10)

# Button to trigger translation
Button(root, text="Translate", command=translate).pack(pady=20)

# Run the application
root.mainloop()
