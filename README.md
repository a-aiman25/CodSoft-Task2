# CodSoft-Task2
This repository contains a simple calculator built using Python's Tkinter library. The calculator provides basic arithmetic operations such as addition, subtraction, multiplication, and division calculations.


from tkinter import *

root = Tk()
root.title("CALCULATOR")     # Set the name of the Window's Title
root.config(background="white")     # Set the background of Window
root.geometry("385x510")             # Set the size of the Window

equation = ""

def show(value):
    global equation
    equation+=value
    result_box.config(text=equation)

def clear():
    global equation
    equation = ""
    result_box.config(text=equation)
    
def calculate():
    global equation
    result = ""
    if equation != "":
        try:
            result = eval(equation)
            if isinstance(result, float) and "/" in equation:
                result = round(result, 5)
            equation = ""  # Clear the equation variable
            result_box.config(text=result)
        except:
            result = "Error"
            equation = ""  # Clear the equation variable
    result_box.config(text=result)
    
result_box = Label(root, width = 16, height = 2, text = "", font=("Segoe UI", 30), bg="dark grey")
result_box.pack()
result_box.place(x=14, y=3)

# Create buttons
Button(root, text="C", width=10, height=1, font=("Times New Roman", 22, "bold"), fg="white", bg="#355E3B", command = lambda: clear()).place(x=10, y=120)              
Button(root, text="%", width=4, height=1, font=("Times New Roman", 22, "bold"), fg="white", bg="#2a2d36", command = lambda: show("%")).place(x=205, y=120)
Button(root, text="/", width=4, height=1, font=("Times New Roman", 22, "bold"), fg="white", bg="#2a2d36", command = lambda: show("/")).place(x=300, y=120)

Button(root, text="7", width=4, height=1, font=("Times New Roman", 22, "bold"), fg="white", bg="#2a2d36", command = lambda: show("7")).place(x=10, y=200)
Button(root, text="8", width=4, height=1, font=("Times New Roman", 22, "bold"), fg="white", bg="#2a2d36", command = lambda: show("8")).place(x=106, y=200)
Button(root, text="9", width=4, height=1, font=("Times New Roman", 22, "bold"), fg="white", bg="#2a2d36", command = lambda: show("9")).place(x=205, y=200)
Button(root, text="*", width=4, height=1, font=("Times New Roman", 22, "bold"), fg="white", bg="#2a2d36", command = lambda: show("*")).place(x=300, y=200)

Button(root, text="4", width=4, height=1, font=("Times New Roman", 22, "bold"), fg="white", bg="#2a2d36", command = lambda: show("4")).place(x=10, y=280)
Button(root, text="5", width=4, height=1, font=("Times New Roman", 22, "bold"), fg="white", bg="#2a2d36", command = lambda: show("5")).place(x=106, y=280)
Button(root, text="6", width=4, height=1, font=("Times New Roman", 22, "bold"), fg="white", bg="#2a2d36", command = lambda: show("6")).place(x=205, y=280)
Button(root, text="-", width=4, height=1, font=("Times New Roman", 22, "bold"), fg="white", bg="#2a2d36", command = lambda: show("-")).place(x=300, y=280)

Button(root, text="1", width=4, height=1, font=("Times New Roman", 22, "bold"), fg="white", bg="#2a2d36", command = lambda: show("1")).place(x=10, y=360)
Button(root, text="2", width=4, height=1, font=("Times New Roman", 22, "bold"), fg="white", bg="#2a2d36", command = lambda: show("2")).place(x=106, y=360)
Button(root, text="3", width=4, height=1, font=("Times New Roman", 22, "bold"), fg="white", bg="#2a2d36", command = lambda: show("3")).place(x=205, y=360)
Button(root, text="+", width=4, height=1, font=("Times New Roman", 22, "bold"), fg="white", bg="#2a2d36", command = lambda: show("+")).place(x=300, y=360)

Button(root, text="00", width=4, height=1, font=("Times New Roman", 22, "bold"), fg="white", bg="#2a2d36", command = lambda: show("00")).place(x=10, y=440)
Button(root, text="0", width=4, height=1, font=("Times New Roman", 22, "bold"), fg="white", bg="#2a2d36", command = lambda: show("0")).place(x=106, y=440)
Button(root, text=".", width=4, height=1, font=("Times New Roman", 22, "bold"), fg="white", bg="#2a2d36", command = lambda: show(".")).place(x=205, y=440)
Button(root, text="=", width=4, height=1, font=("Times New Roman", 22, "bold"), fg="white", bg="#f09030", command = lambda: calculate()).place(x=300, y=440)
