from pydoc import text
import tkinter as tk
from tkinter import *
from tkinter import ttk

def show_multiply():
  number = int(number_input.get())

  snumber1 = int(number_site1.get())

  snumber2t = int(number_site2.get())

  snumber2 = (snumber2t+1)

  if number == 0:
    output_label.configure(text='ผิดที่ไว้ใจ')
    return

  output = ''
  for i in range(snumber1, snumber2):
    output += str(number) + ' x ' + str(i)
    output += ' = ' + str(number * i) + '\n'

  output_label.configure(text=output)

window1 = tk.Tk()

window1.title('สูตรคูณ')
window1.minsize(width=300, height=500)


title_label = tk.Label(master=window1, text='สูตรคูณแม่')
title_label.pack(pady=(20, 5))

number_input = tk.Entry(master=window1)
number_input.pack(pady=(5, 5))

output_button = tk.Button(
  master=window1, text='ได้แก่', command=show_multiply,
  width=20, height=2
)
output_button.pack(pady=(5, 5))

title_label2 = tk.Label(master=window1, text='ตั้งแต่แม่(ขั้นต่ำ 1)')
title_label2.pack(pady=(20, 5))

number_site1 = r = Scale(window1, from_=1, to=500, orient=HORIZONTAL, length=200, width=30, fg="red")
number_site1.pack(pady=(5, 5))

title_label3 = tk.Label(master=window1, text='ตั้งแต่แม่สุดท้าย(แนะนำ ขั้นต่ำ 12)')
title_label3.pack(pady=(20, 5))

number_site2 = r = Scale(window1, from_=12, to=500, orient=HORIZONTAL, length=200, width=30, fg="green")
number_site2.pack(pady=(5, 5))

output_label = tk.Label(master=window1)
output_label.pack(pady=(5, 5))

window1.mainloop()
