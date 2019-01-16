# Data-analysis
#ASSIGNING PHONE NUMBERS TO CUSTOMERS USING PYTHON PROGRAMING 
#UPTO 362280 NUMBERS OF UNIQUE TEN DIGIT PHONE NUMBERS CAN BE CREATED



import random
import pickle

#GENERATION OF NEW NUMBER

print("1.GENERATE NUMBER","2.ACCESS DATABASE")
cha=eval(input("ENTER CHOICE: "))
if cha==1:
    i=0
    list1=[]
    for i in range(10):
        r=random.randint(0,9)
        list1.append(r)
    print(list1)
    
#UPDATING DATABASE CHECKING AVAILABILITY

if cha==2:
    class check:
        def __init__(self,number,name):
            self.number=number
            self.name=name
    print("1.ASSIGN TO CUSTOMER: ","2.CHECK AVAILABILITY: ","3.EXIT")
    ch=eval(input("ENTER CHOICE: "))
    if ch==1:
        while True:
            n=eval(input("Enter number: "))
            na=input("ENTER CUSTOMER NAME: ")
            e1=check(n,na)                
            with open("NUMBER.txt","wb") as f:
                pickle.dump(e1,f)
            c1=input("want to add more?(y/n) ")
            if c1== "y":
                continue
            else:
                break
    if ch==2:
        c=eval(input("enter number: "))
        with open("NUMBER.txt","rb") as f:
            d=pickle.load(f)
        if c== d.number:
            print("your entered number is: ",d.number)
            print("Number has been assigned to",d.name)
            quit
        else:
            print("number is available")
            quit
            
    if ch==3:
        quit
                    
    
