import tkinter as tk
from tkinter import messagebox
import datetime

def log_data():
    name = name_entry.get().lower()
    task = task_var.get()
    file_name = f"{name}'s {task}.txt"
    info = data_entry.get()

    with open(file_name, 'a') as f:
        f.write(f"[{get_date()}] {info}\n")

    messagebox.showinfo("Success", "Data logged successfully!")

def retrieve_data():
    name = name_entry.get().lower()
    task = task_var.get()
    file_name = f"{name}'s {task}.txt"

    try:
        with open(file_name) as f:
            data = f.read()
            data_text.delete(1.0, tk.END)
            data_text.insert(tk.END, data)
    except FileNotFoundError:
        messagebox.showerror("Error", "File not found.")

def get_date():
    return datetime.datetime.now()

# Create the main window
root = tk.Tk()
root.title("HEALTH MANAGEMENT SYSTEM")
root.configure(bg="#4169E1")  # Royal blue background color

# Create and configure widgets
name_label = tk.Label(root, text="Enter Your Name:", bg="#4169E1", fg="white")  # White text on royal blue
name_label.pack()
name_entry = tk.Entry(root, bg="#87CEEB")  # Lighter blue entry background
name_entry.pack()

task_label = tk.Label(root, text="Select Task:", bg="#4169E1", fg="white")
task_label.pack()
task_var = tk.StringVar(value="Food")
task_option_menu = tk.OptionMenu(root, task_var, "Food", "Exercise", "Drugs")
task_option_menu.config(bg="#87CEEB")  # Lighter blue menu background
task_option_menu.pack()

data_label = tk.Label(root, text="Enter Data:", bg="#4169E1", fg="white")
data_label.pack()
data_entry = tk.Entry(root, bg="#87CEEB")  # Lighter blue entry background
data_entry.pack()

log_button = tk.Button(root, text="Log Data", command=log_data, bg="#FFD700", fg="black")  # Gold button
log_button.pack()

retrieve_button = tk.Button(root, text="Retrieve Data", command=retrieve_data, bg="#FFD700", fg="black")
retrieve_button.pack()

data_text = tk.Text(root, height=10, width=40, bg="#87CEEB")  # Lighter blue text area background
data_text.pack()

# Start the GUI main loop
root.mainloop()
