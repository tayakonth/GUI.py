# GUI.py
BML
from tkinter import *
import math
from tkinter import  messagebox
def show():
    messagebox.showerror("Error","กรุณากรอกตัวเลข")
def Bmi(event):
    try:
        bmi = (float(textBoxweight.get())/math.pow(float(TaxtBoxHight.get())/100,2))
        if a < 18.5:
            labelresult.configure(text="น้ำหนักต่ำกว่าเกณฑ์")
        elif bmi >= 18.5 and a < 23:
            labelresult.configure(text="สมส่วน")
        elif bmi >= 23 and a < 25:
            labelresult.configure(text="น้ำหนักเกิน")
        elif bmi >= 25 and a < 30:
            labelresult.configure(text="โรคอ้วน")
        elif bmi >= 30:
            labelresult.configure(text="โรคอ้วนอันตราย")
    except:
        show()

Mainwindow = Tk()
labelHight = Label(Mainwindow,text="ส่วนสูง (Cm.)")
labelHight.grid(row=0,column=0)
TaxtBoxHight = Entry(Mainwindow)
TaxtBoxHight.grid(row=0,column=1)
labelWeight = Label(Mainwindow,text="น้ำหนัก (Kg.)")
labelWeight.grid(row=1,column=0)
textBoxweight = Entry(Mainwindow)
textBoxweight.grid(row=1,column=1)
calculteButton = Button(Mainwindow,text="คำนวณ")
calculteButton.bind('<Button-1>',Bmi)
calculteButton.grid(row=2,column=0)
labelresult = Label(Mainwindow,text="ผลลัพธ์")
labelresult.grid(row=2,column=1)
Mainwindow.mainloop()
