# Correlation and regression for data analysis
# Aim : 

To analyse given data using coeffificient of correlation and regression line
![image](https://user-images.githubusercontent.com/104613195/168224136-d6b64e64-7d3d-4775-9337-c8f96fe41f2d.png)


# Software required :  

Python

# Theory:

Correlation describes the strength of an association between two variables, and is completely symmetrical, the correlation between A and B is the same as the correlation between B and A. However, if the two variables are related it means that when one changes by a certain amount the other changes on an average by a certain amount.  

If y represents the dependent variable and x the independent variable, this relationship is described as the regression of y on x. The relationship can be represented by a simple equation called the regression equation. The regression equation representing how much y changes with any given change of x can be used to construct a regression line on a scatter diagram, and in the simplest case this is assumed to be a straight line.

# Procedure :

![image](https://user-images.githubusercontent.com/104613195/168225866-ac8f6610-bdc3-4ac2-a24e-2b24ba08e189.png)

# Program :
```
import numpy as np
import math
import matplotlib.pyplot as plt
print("Enter Virat's last 10 T20 Scores:")
Virat=[int(i) for i in input().split()]
print("Enter Rohith's last 10 T20 Scores:")
Rohith=[int(i) for i in input().split()]
N=len(Virat)
SVirat=0
SRohith=0
SViratRohith=0
SVirat2=0
SRohith2=0
for i in range(0,N):
    SVirat=SVirat+Virat[i]
    SRohith=SRohith+Rohith[i]
    SViratRohith=SViratRohith+Virat[i]*Rohith[i]
    SVirat2=SVirat2+Virat[i]**2
    SRohith2=SRohith2+Rohith[i]**2
r=(N*SViratRohith-SVirat*SRohith)/(math.sqrt(N*SVirat2-SVirat**2)*math.sqrt(N*SRohith2-SRohith**2))
print("The correlation coefficient is %0.3f"%r)
bRohithVirat=(N*SViratRohith-SVirat*SRohith)/(N*SVirat2-SVirat**2)
Viratmean=SVirat/N
Rohithmean=SRohith/N
print("The Regression line Rohith on Virat is ::: Rohith = %0.3f %0.3f (Virat-%0.3f)"%(Rohithmean,bRohithVirat,Viratmean))
plt.scatter(Virat,Rohith)
def Reg(Virat):
    return Rohithmean+bRohithVirat*(Virat-Viratmean)
Virat=np.linspace(0,130,51)
Rohith1=Reg(Virat)
plt.plot(Virat,Rohith1,'r')
plt.xlabel('Virat-data')
plt.ylabel('Rohith-data')
plt.legend(['Regression Line','Data points'])

```

# Results and Output : 
![image](https://github.com/Rohith-AIDS/Correlation_Regression/blob/main/probability.png)
