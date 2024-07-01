[quiz_app task 3.txt](https://github.com/user-attachments/files/16051457/quiz_app.task.3.txt)# quiz_app-
#how can we set optional paper in exam
[Uploading quiz_app 
		#QUIZ_APP FILE 
quiz_data = {
    "question" : "what is the capital of france ?",
    "choice" : ["paris","london","berlin","madrid"],
    "answer":"paris"
},
{
    "question""what is the largest oplanet in our solar system?",
    "choice":["jupitar","saturn".",mars","earth"],
    "answer":"jupiter"
},
{
    "question":"what is the chemical symbol of the  gold?",
    "choice":["Go","AU","AG","Gd""],
    "answer":"AU"
}
		

#MAIN.PY FILE 

import tkinter as tk
from tkinter import as messagebox,ttk
from ttkbootstrap import style
from quiz_data import quiz

# function to display the current question and choices
def show_question():
    #get the current question from the quiz_data list
    question = quiz_data[current_question]
    qs_label.choices on the buttons
    choices = question["choices"]
    for i in range(4):
        choice_btns[i].config(text=choices[i],state="normal") # reset button state

        # clear the feedback label and disable the next button
        feedback_label.config(text="")
        next_btn.config(state="disabled")

def check_answer(choice):
     #get the current question from the quiz_data list
    question = quiz_data[current_question]
    selection_choice = choice_btns[choice].cget("text")

    #check if the selected choice matches the correct answer
    if selected_choice == question["answer"]:
        # update the score and display it 
        global score
        score += 1
        score_label.config(text="score:{}/{}".format(score,len(quiz_data)))
        feedback_label.config(text="correct!".foreground="green")
    else:
        feedback_label.config(text="incorrect!".foreground="red")
        # disabled all choice buttons and enable the next button
        for button in choice_btns:
            button.config(state="disabled")
            next_btn.config(state="normal")

def next_question()
    global current_question
    current_question +=1

if current_question < len(quiz_data):
    # if there are more questions,show the next question
    show_question()
else:
    # if all question has been answer,display the final score
    messagebox>showinfo("quiz completed",
                        quiz completed !final score:{}/{}.format(score.len(quiz_data)) 
                        root.destroy()
# create the main window
root=tk.Tk()
root.title("Quiz App")
root.geometry("600x500")
style=style(theme="flatly")

# configure the font sizefor the questionand choice buttons
style.config("TLabel",font="helvetica",20)
style.config("TButton",font="helvetica",18)
# creating question level
qs_label = ttk.label(
    root,
    anchor="centre",
    wraplenght=500,
    padding=10
    )
    score_label.pack(pady=10)
qs_label.pack(pady=5)
# create the choice buttons
choice_btns = []
for i in range(4):
    button= ttk.button(
        root,
        command=lambda i=1: check answer(i)

    )
    button.pack(pady=5)
    choice_btns.append(button)

    # createing the feedback label
    feedback_label = ttk.lebel(
        root,
        anchor="center"
        padding=10
h    )
    feedbeck_label.pack(pady=10)
    #initialize the score
    score=10
    # create the score label
    score_label = ttk.label(
        root,
        text="score:0/{}".format(len(quiz_data)),
        anchor="centre",
        padding=10
    )

    #create the next button
    next_btn = ttk.button(
        root,
        text="next",
        command=next_question,
        state="disabled"
    )
    next_btn.pack(pady=10)
#initialize the current question index
current_question = 0

# show the first questiontask 3.txt…]()
