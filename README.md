# Python-projects
Simple calculator 

from tkinter import *

root = Tk()
root.title("simple calculator")

entry = Entry(root, width=60, borderwidth=5)
entry.grid(row=0, column=0, columnspan=23, pady=5, padx=5)

global operator
global s_num


def click(number):
    entry.insert(END, number)


def clear():
    entry.delete(0, END)


def subtract():
    global operator
    operator = "-"
    global f_num
    first = entry.get()
    f_num = int(first)
    entry.delete(0, END)


def divide():
    global operator
    operator = "/"
    global f_num
    first = entry.get()
    f_num = int(first)
    entry.delete(0, END)


def multiply():
    global operator
    operator = "*"
    global f_num
    first = entry.get()
    f_num = int(first)
    entry.delete(0, END)


def add():
    global operator
    operator = "+"
    global f_num
    first = entry.get()
    f_num = int(first)
    entry.delete(0, END)


def equal():
    second = entry.get()
    s_num = int(second)
    entry.delete(0, END)
    if operator == "+":
        result = s_num + f_num
        entry.insert(0, str(result))
    elif operator == "-":
        result = s_num - f_num
        entry.insert(0, str(result))
    elif operator == "*":
        result = s_num * f_num
        entry.insert(0, str(result))
    elif operator == "/":
        result = s_num / f_num
        entry.insert(0, str(result))


b1 = Button(root, text="1", pady=30, padx=40, borderwidth=3, command=lambda: click(1))
b2 = Button(root, text="2", pady=30, padx=40, borderwidth=3, command=lambda: click(2))
b3 = Button(root, text="3", pady=30, padx=40, borderwidth=3, command=lambda: click(3))
b4 = Button(root, text="4", pady=30, padx=40, borderwidth=3, command=lambda: click(4))
b5 = Button(root, text="5", pady=30, padx=40, borderwidth=3, command=lambda: click(5))
b6 = Button(root, text="6", pady=30, padx=40, borderwidth=3, command=lambda: click(6))
b7 = Button(root, text="7", pady=30, padx=40, borderwidth=3, command=lambda: click(7))
b8 = Button(root, text="8", pady=30, padx=40, borderwidth=3, command=lambda: click(8))
b9 = Button(root, text="9", pady=30, padx=40, borderwidth=3, command=lambda: click(9))
b0 = Button(root, text="0", pady=30, padx=40, borderwidth=3, command=lambda: click(0))
b_dot = Button(root, text=".", pady=30, padx=41, borderwidth=3)
b_add = Button(root, text="+", pady=30, padx=40, borderwidth=3, command=add)
b_subtract = Button(root, text="-", pady=30, padx=40, borderwidth=3, command=subtract)
b_divide = Button(root, text="/", pady=30, padx=40, borderwidth=3, command=divide)
b_multiply = Button(root, text="x", pady=30, padx=40, borderwidth=3, command=multiply)
b_clear = Button(root, text="C", width=54, borderwidth=3, pady=40, command=clear)
b_equal = Button(root, text="=", pady=30, padx=40, borderwidth=3, command=equal)

b1.grid(row=3, column=0)
b2.grid(row=3, column=1)
b3.grid(row=3, column=2)
b_subtract.grid(row=3, column=3)

b4.grid(row=2, column=0)
b5.grid(row=2, column=1)
b6.grid(row=2, column=2)
b_multiply.grid(row=2, column=3)

b7.grid(row=1, column=0)
b8.grid(row=1, column=1)
b9.grid(row=1, column=2)
b_divide.grid(row=1, column=3)

b0.grid(row=4, column=1)
b_dot.grid(row=4, column=0)
b_equal.grid(row=4, column=2)
b_add.grid(row=4, column=3)

b_clear.grid(row=5, column=0, columnspan=22, pady=1, padx=5)

root.mainloop()