# Multiple server with infinite capacity - (M/M/c):(oo/FIFO)
## Aim :
To find (a) average number of materials in the system (b) average number of materials in the conveyor (c) waiting time of each material in the system (d) waiting time of each material in the conveyor, if the arrival  of materials follow poisson process with the mean interval time 10 seconds, serivice time of two lathe machine follow exponential distribution with mean serice time 1 second and average service time of robot is 7seconds.

## Software required :
Visual components and Python

## Theory:
Queuing are the most frequently encountered problems in everyday life. For example, queue at a cafeteria, library, bank, etc. Common to all of these cases are the arrivals of objects requiring service and the attendant delays when the service mechanism is busy. Waiting lines cannot be eliminated completely, but suitable techniques can be used to reduce the waiting time of an object in the system. A long waiting line may result in loss of customers to an organization. Waiting time can be reduced by providing additional service facilities, but it may result in an increase in the idle time of the service mechanism.

![image](https://user-images.githubusercontent.com/103921593/203238035-1c8109bc-cbf2-4c77-baea-c5b682a752ef.png)

## Procedure :

![image](https://user-images.githubusercontent.com/103921593/203238265-176740b0-eae2-4772-90be-5449869ac9b0.png)




## Experiment:


![{D0530A9E-D771-4D59-BD92-B5B49288FAD8}](https://github.com/user-attachments/assets/6aadf791-dfd0-4141-a1ac-a5f7e82ae0a4)


![{02BA99D2-A530-43F9-B259-101F1EB16F8F}](https://github.com/user-attachments/assets/db700c58-d64b-415e-bfc4-9fdaab4dd5a9)




## Program

Developed by :RAHUL RP
Register number : 24900488

import math

arr_time=float(input("Enter the mean inter arrival time of objects from Feeder (in secs): "))

ser_time=float(input("Enter the mean  inter service time of Lathe Machine (in secs) :  "))

Robot_time=float(input("Enter the Additional time taken for the Robot (in secs) :  "))

c=int(input("Number of service centre :  "))

lam=1/arr_time

mu=1/(ser_time+Robot_time)

print("--------------------------------------------------------------")

print("Multiple Server with Infinite Capacity - (M/M/c):(oo/FIFO)")

print("--------------------------------------------------------------")

print("The mean arrival rate per second : %0.2f "%lam)

print("The mean service rate per second : %0.2f "%mu)

rho=lam/(c*mu)

sum=(lam/mu)**c*(1/(1-rho))/math.factorial(c)

for i in range(0,c):

    sum=sum+(lam/mu)**i/math.factorial(i)

P0=1/sum

if (rho<1):

    Lq=(P0/math.factorial(c))*(1/c)*(lam/mu)**(c+1)/(1-rho)**2
    
    Ls=Lq+lam/mu
    
    Ws=Ls/lam
    
    Wq=Lq/lam
    
    print("Average number of objects in the system : %0.2f "%Ls)
    
    print("Average number of objects in the conveyor :  %0.2f "%Lq)
    
    print("Average waiting time of an object in the system : %0.2f secs"%Ws)
    
    print("Average waiting time of an object in the conveyor : %0.2f secs"%Wq)
    
    print("Probability that the system is busy : %0.2f "%(rho))
    
    print("Probability that the system is empty : %0.2f "%(1-rho))

else:

    print("Warning! Objects Over flow will happen in the conveyor")

print("--------------------------------------------------------------")


## Output :


![{D8AAF076-6A66-4BE6-B700-2BEECA039441}](https://github.com/user-attachments/assets/86df3f2c-af22-4afa-93cf-a33b476955c2)


## Result : 

Thus the average number of materials in the system and conveyor, waiting time of each material in the system and conveyor is found successfully.

