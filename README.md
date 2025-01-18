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
