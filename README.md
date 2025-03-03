# my_project
import tkinter as tk
from tkinter import messagebox

def login():
    name = entry_name.get()
    username = entry_username.get()
    password = entry_password.get()
    # Here you can add your login logic
    if username == "admin" and password == "password":
        messagebox.showinfo("Login", f"Welcome, {name}!")
    else:
        messagebox.showerror("Login", "Invalid username or password.")

# Create the main window
root = tk.Tk()
root.title("Login")
root.geometry("300x250")

# Create a canvas to draw the background
canvas = tk.Canvas(root, width=300, height=250)
canvas.pack()

# Draw the tie-dye background
colors = ["#9b59b6", "#e91e63", "#3498db"]
for i in range(300):
    canvas.create_line(i, 0, i, 250, fill=colors[i % len(colors)])

# Create the login frame
frame_login = tk.Frame(root, bg="white")
frame_login.place(relx=0.5, rely=0.5, anchor="center")

# Name label and entry
label_name = tk.Label(frame_login, text="Name:")
label_name.grid(row=0, column=0, padx=10, pady=10)
entry_name = tk.Entry(frame_login)
entry_name.grid(row=0, column=1, padx=10, pady=10)

# Username label and entry
label_username = tk.Label(frame_login, text="Username:")
label_username.grid(row=1, column=0, padx=10, pady=10)
entry_username = tk.Entry(frame_login)
entry_username.grid(row=1, column=1, padx=10, pady=10)

# Password label and entry
label_password = tk.Label(frame_login, text="Password:")
label_password.grid(row=2, column=0, padx=10, pady=10)
entry_password = tk.Entry(frame_login, show="*")
entry_password.grid(row=2, column=1, padx=10, pady=10)

# Login button
button_login = tk.Button(frame_login, text="Login", command=login)
button_login.grid(row=3, columnspan=2, pady=10)

root.mainloop()