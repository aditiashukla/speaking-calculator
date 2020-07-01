import pyttsx3 # pip install pyttsx3
import datetime #access date time of pc
engine = pyttsx3.init('sapi5')
voices = engine.getProperty('voices')
engine.setProperty('voice', voices[0].id)
#speak function used to convert text to speech
def speak(audio):
    engine.say(audio)
    engine.runAndWait()
    #wait for completion of speech
def wishMe():
    hour = int(datetime.datetime.now().hour)
    if hour>=0 and hour<12:
        speak("Good Morning user")
    elif hour>=12 and hour<=18:
        speak("Good Afternoon user")
    else:
        speak("Good Evening user")

wishMe()

x=0
num1=0
num2=0
speak('Select required operation with respected serial number ')
engine.setProperty('voice', voices[1].id)
# This function adds two numbers 
def add(x, y):
   return x + y
# This function subtracts two numbers 
def subtract(x, y):
   return x - y
# This function multiplies two numbers
def multiply(x, y):
   return x * y
# This function divides two numbers
def divide(x, y):
   return x / y
# Take input from the user 
def getData():
    global num1
    global num2
    speak("Enter first number: ")
    num1 = int(input())
    speak("Enter second number: ")
    num2 = int(input())
speak("1. ")
speak("Add")
speak("2.Subtract")
speak("3.Multiply")
speak("4.Divide")

speak("Select choice")
speak("enter selcted operation serial number")
choice = input()

#switch case
if choice == '1':
    getData()
    print(num1,"+",num2,"=", add(num1,num2))
    x=add(num1,num2)
elif choice == '2':
    getData()
    print(num1,"-",num2,"=", subtract(num1,num2))
    x=subtract(num1,num2)
elif choice == '3':
    getData()
    print(num1,"*",num2,"=", multiply(num1,num2))
    x=multiply(num1,num2)
elif choice == '4':
    getData()
    print(num1,"/",num2,"=", divide(num1,num2))
    x=divide(num1,num2)
else:
    speak("Invalid Input")
speak("the output is") 
speak(x)
speak("thank you")