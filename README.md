# Icequake-Location-Codes
#For icequake 27JAN - 2.1

import numpy as np
from scipy.optimize import fsolve
E=[532898.006, 532813.476, 533508.052, 533433.895, 533352.308, 532936.547, 533659.013, 532635.777, 533105.552]
N=[1592845.324, 1592522.506, 1592595.041, 1592892.487, 1593234.447, 1593242.316, 1593121.969, 1593054.889, 1593490.401]
T=[8.357, 8.068, 8.309, 8.342, 8.139, 8.096, 8.263, 7.988, 8.110]
Vp2=3800**2.0
roots=[]
for i in range (9):
    for j in range (9):
        for k in range (9):
            if i != j:
                if i != k:
                    if j != k:
                        try:
                            def f(a):
                                x=a[0]
                                y=a[1]
                                t=a[2]
                                f1=np.zeros(3)
                                f1[0]=(E[i]-x)**2.0+(N[i]-y)**2.0-Vp2*(T[i]-t)**2.0
                                f1[1]=(E[j]-x)**2.0+(N[j]-y)**2.0-Vp2*(T[j]-t)**2.0
                                f1[2]=(E[k]-x)**2.0+(N[k]-y)**2.0-Vp2*(T[k]-t)**2.0
            
                                return f1
    
                            root = fsolve(f, [532400.33, 1592721.79, 2.00])
                            vec=root
                            vec2=f(root)
                            if vec[2]<8.0:
                                if sum(vec2)<0.5:
                                    print(root)
                                    print(f(root))
                                    roots.append(root)
                                    print()
                                    #print()
                        except Exception as error:
                            print(f"Failed to make eqn combo {i}, {j}, {k}")
    
fs=[]
for j in range (len(roots)):
    a=roots[j]
    x=a[0]
    y=a[1]
    t=a[2]
    print(x)
    print(y)
    print(t)
    f1=np.zeros(9)
    f1[0]=abs((E[0]-x)**2.0+(N[0]-y)**2.0-Vp2*(T[0]-t)**2.0)
    f1[1]=abs((E[1]-x)**2.0+(N[1]-y)**2.0-Vp2*(T[1]-t)**2.0)
    f1[2]=abs((E[2]-x)**2.0+(N[2]-y)**2.0-Vp2*(T[2]-t)**2.0)
    f1[3]=abs((E[3]-x)**2.0+(N[3]-y)**2.0-Vp2*(T[3]-t)**2.0)
    f1[4]=abs((E[4]-x)**2.0+(N[4]-y)**2.0-Vp2*(T[4]-t)**2.0)
    f1[5]=abs((E[5]-x)**2.0+(N[5]-y)**2.0-Vp2*(T[5]-t)**2.0)
    f1[6]=abs((E[6]-x)**2.0+(N[6]-y)**2.0-Vp2*(T[6]-t)**2.0)
    f1[7]=abs((E[7]-x)**2.0+(N[7]-y)**2.0-Vp2*(T[7]-t)**2.0)
    f1[8]=abs((E[8]-x)**2.0+(N[8]-y)**2.0-Vp2*(T[8]-t)**2.0)
    
    print(f1)
    fs.append(f1)
    print()
    
import matplotlib.pyplot as plt
%matplotlib notebook
mean_fs=np.zeros(len(fs))
means=[]
for i in range(len(fs)):
    print(fs[i])
    mean_fs[i]=sum(fs[i])/len(fs[i])
    print(sum(fs[i])/len(fs[i]))
    means.append(mean_fs[i])
x=np.arange(len(fs))
plt.plot(x, mean_fs)
#plt.ylim(0.4*10**6, 10**6)



# function to find minimum and maximum position in list
def minimum(means, n):
 
    # inbuilt function to find the position of minimum
    minpos = means.index(min(means))
 
    # inbuilt function to find the position of maximum
    maxpos = means.index(max(means))
 
    # printing the position
    print ("The maximum is at position", maxpos, "on the graph")
    print ("The minimum is at position", minpos, "on the graph")

minimum(means, len(means))
    
print(roots[25])

#For icequake 27JAN - 1.1

import numpy as np
from scipy.optimize import fsolve
E=[532898.006, 532813.476, 533508.052, 533433.895, 533352.308, 532936.547, 533659.013, 532635.777, 533105.552]
N=[1592845.324, 1592522.506, 1592595.041, 1592892.487, 1593234.447, 1593242.316, 1593121.969, 1593054.889, 1593490.401]
T=[0.582, 1.38, 0.404, 0.347, 0.254, 0.293, 0.305, 0.383, 0.45]
Vp2=3800**2.0
roots=[]
for i in range (9):
    for j in range (9):
        for k in range (9):
            if i != j:
                if i != k:
                    if j != k:
                        try:
                            def f(a):
                                x=a[0]
                                y=a[1]
                                t=a[2]
                                f1=np.zeros(3)
                                f1[0]=(E[i]-x)**2.0+(N[i]-y)**2.0-Vp2*(T[i]-t)**2.0
                                f1[1]=(E[j]-x)**2.0+(N[j]-y)**2.0-Vp2*(T[j]-t)**2.0
                                f1[2]=(E[k]-x)**2.0+(N[k]-y)**2.0-Vp2*(T[k]-t)**2.0
            
                                return f1
    
                            root = fsolve(f, [533160, 1593685, 0.00])
                            vec=root
                            vec2=f(root)
                            if vec[2]<0.254:
                                if sum(vec2)<0.5:
                                    print(root)
                                    print(f(root))
                                    roots.append(root)
                                    print()
                                    #print()
                        except Exception as error:
                            print(f"Failed to make eqn combo {i}, {j}, {k}")
    
fs=[]
for j in range (len(roots)):
    a=roots[j]
    x=a[0]
    y=a[1]
    t=a[2]
    print(x)
    print(y)
    print(t)
    f1=np.zeros(9)
    f1[0]=abs((E[0]-x)**2.0+(N[0]-y)**2.0-Vp2*(T[0]-t)**2.0)
    f1[1]=abs((E[1]-x)**2.0+(N[1]-y)**2.0-Vp2*(T[1]-t)**2.0)
    f1[2]=abs((E[2]-x)**2.0+(N[2]-y)**2.0-Vp2*(T[2]-t)**2.0)
    f1[3]=abs((E[3]-x)**2.0+(N[3]-y)**2.0-Vp2*(T[3]-t)**2.0)
    f1[4]=abs((E[4]-x)**2.0+(N[4]-y)**2.0-Vp2*(T[4]-t)**2.0)
    f1[5]=abs((E[5]-x)**2.0+(N[5]-y)**2.0-Vp2*(T[5]-t)**2.0)
    f1[6]=abs((E[6]-x)**2.0+(N[6]-y)**2.0-Vp2*(T[6]-t)**2.0)
    f1[7]=abs((E[7]-x)**2.0+(N[7]-y)**2.0-Vp2*(T[7]-t)**2.0)
    f1[8]=abs((E[8]-x)**2.0+(N[8]-y)**2.0-Vp2*(T[8]-t)**2.0)
    
    print(f1)
    fs.append(f1)
    print()
    
import matplotlib.pyplot as plt
%matplotlib notebook
mean_fs=np.zeros(len(fs))
means=[]
for i in range(len(fs)):
    print(fs[i])
    mean_fs[i]=sum(fs[i])/len(fs[i])
    print(sum(fs[i])/len(fs[i]))
    means.append(mean_fs[i])
x=np.arange(len(fs))
plt.plot(x, mean_fs)
#plt.ylim(0.4*10**6, 10**6)



# function to find minimum and maximum position in list
def minimum(means, n):
 
    # inbuilt function to find the position of minimum
    minpos = means.index(min(means))
 
    # inbuilt function to find the position of maximum
    maxpos = means.index(max(means))
 
    # printing the position
    print ("The maximum is at position", maxpos, "on the graph")
    print ("The minimum is at position", minpos, "on the graph")

minimum(means, len(means))
    
print(roots[54])

#For icequake 27JAN - 1.1 - CORRECTED

import numpy as np
from scipy.optimize import fsolve
E=[532898.006, 532813.476, 533508.052, 533433.895, 533352.308, 532936.547, 533659.013, 532635.777, 533105.552]
N=[1592845.324, 1592522.506, 1592595.041, 1592892.487, 1593234.447, 1593242.316, 1593121.969, 1593054.889, 1593490.401]
T=[0.582, 1.38, 0.404, 0.347, 0.254, 0.293, 0.305, 0.383, 0.45]
Vp2=3800**2.0
roots=[]
for i in range (9):
    for j in range (9):
        for k in range (9):
            if i != j:
                if i != k:
                    if j != k:
                        try:
                            def f(a):
                                x=a[0]
                                y=a[1]
                                t=a[2]
                                f1=np.zeros(3)
                                f1[0]=(E[i]-x)**2.0+(N[i]-y)**2.0-Vp2*(T[i]-t)**2.0
                                f1[1]=(E[j]-x)**2.0+(N[j]-y)**2.0-Vp2*(T[j]-t)**2.0
                                f1[2]=(E[k]-x)**2.0+(N[k]-y)**2.0-Vp2*(T[k]-t)**2.0
            
                                return f1
    
                            root = fsolve(f, [533080, 1593701, 0.00])
                            vec=root
                            vec2=f(root)
                            if vec[2]<0.254:
                                if sum(vec2)<0.5:
                                    print(root)
                                    print(f(root))
                                    roots.append(root)
                                    print()
                                    #print()
                        except Exception as error:
                            print(f"Failed to make eqn combo {i}, {j}, {k}")
    
fs=[]
for j in range (len(roots)):
    a=roots[j]
    x=a[0]
    y=a[1]
    t=a[2]
    print(x)
    print(y)
    print(t)
    f1=np.zeros(5)
    #f1[0]=abs((E[0]-x)**2.0+(N[0]-y)**2.0-Vp2*(T[0]-t)**2.0)
    #f1[1]=abs((E[1]-x)**2.0+(N[1]-y)**2.0-Vp2*(T[1]-t)**2.0)
    #f1[2]=abs((E[2]-x)**2.0+(N[2]-y)**2.0-Vp2*(T[2]-t)**2.0)
    #f1[3]=abs((E[3]-x)**2.0+(N[3]-y)**2.0-Vp2*(T[3]-t)**2.0)
    f1[0]=abs((E[4]-x)**2.0+(N[4]-y)**2.0-Vp2*(T[4]-t)**2.0)
    f1[1]=abs((E[5]-x)**2.0+(N[5]-y)**2.0-Vp2*(T[5]-t)**2.0)
    f1[2]=abs((E[6]-x)**2.0+(N[6]-y)**2.0-Vp2*(T[6]-t)**2.0)
    f1[3]=abs((E[7]-x)**2.0+(N[7]-y)**2.0-Vp2*(T[7]-t)**2.0)
    f1[4]=abs((E[8]-x)**2.0+(N[8]-y)**2.0-Vp2*(T[8]-t)**2.0)
    
    print(f1)
    fs.append(f1)
    print()
    
import matplotlib.pyplot as plt
%matplotlib notebook
mean_fs=np.zeros(len(fs))
means=[]
for i in range(len(fs)):
    print(fs[i])
    mean_fs[i]=sum(fs[i])/len(fs[i])
    print(sum(fs[i])/len(fs[i]))
    means.append(mean_fs[i])
x=np.arange(len(fs))
plt.plot(x, mean_fs)
#plt.ylim(0.4*10**6, 10**6)



# function to find minimum and maximum position in list
def minimum(means, n):
 
    # inbuilt function to find the position of minimum
    minpos = means.index(min(means))
 
    # inbuilt function to find the position of maximum
    maxpos = means.index(max(means))
 
    # printing the position
    print ("The maximum is at position", maxpos, "on the graph")
    print ("The minimum is at position", minpos, "on the graph")

minimum(means, len(means))
    
print(roots[11])

#For icequake 27JAN - 2.2

import numpy as np
from scipy.optimize import fsolve
E=[532898.006, 532813.476, 533508.052, 533433.895, 533352.308, 532936.547, 533659.013, 532635.777, 533105.552]
N=[1592845.324, 1592522.506, 1592595.041, 1592892.487, 1593234.447, 1593242.316, 1593121.969, 1593054.889, 1593490.401]
T=[9.077, 8.889, 9.042, 9.076, 8.931, 8.934, 8.972, 8.89, 8.933]
Vp2=3800**2.0
roots=[]
for i in range (9):
    for j in range (9):
        for k in range (9):
            if i != j:
                if i != k:
                    if j != k:
                        try:
                            def f(a):
                                x=a[0]
                                y=a[1]
                                t=a[2]
                                f1=np.zeros(3)
                                f1[0]=(E[i]-x)**2.0+(N[i]-y)**2.0-Vp2*(T[i]-t)**2.0
                                f1[1]=(E[j]-x)**2.0+(N[j]-y)**2.0-Vp2*(T[j]-t)**2.0
                                f1[2]=(E[k]-x)**2.0+(N[k]-y)**2.0-Vp2*(T[k]-t)**2.0
            
                                return f1
    
                            root = fsolve(f, [532400.33, 1592721.79, 2.00])
                            vec=root
                            vec2=f(root)
                            if vec[2]<8.7:
                                if sum(vec2)<0.5:
                                    print(root)
                                    print(f(root))
                                    roots.append(root)
                                    print()
                                    #print()
                        except Exception as error:
                            print(f"Failed to make eqn combo {i}, {j}, {k}")
    

fs=[]
for j in range (len(roots)):
    a=roots[j]
    x=a[0]
    y=a[1]
    t=a[2]
    print(x)
    print(y)
    print(t)
    f1=np.zeros(9)
    f1[0]=abs((E[0]-x)**2.0+(N[0]-y)**2.0-Vp2*(T[0]-t)**2.0)
    f1[1]=abs((E[1]-x)**2.0+(N[1]-y)**2.0-Vp2*(T[1]-t)**2.0)
    f1[2]=abs((E[2]-x)**2.0+(N[2]-y)**2.0-Vp2*(T[2]-t)**2.0)
    f1[3]=abs((E[3]-x)**2.0+(N[3]-y)**2.0-Vp2*(T[3]-t)**2.0)
    f1[4]=abs((E[4]-x)**2.0+(N[4]-y)**2.0-Vp2*(T[4]-t)**2.0)
    f1[5]=abs((E[5]-x)**2.0+(N[5]-y)**2.0-Vp2*(T[5]-t)**2.0)
    f1[6]=abs((E[6]-x)**2.0+(N[6]-y)**2.0-Vp2*(T[6]-t)**2.0)
    f1[7]=abs((E[7]-x)**2.0+(N[7]-y)**2.0-Vp2*(T[7]-t)**2.0)
    f1[8]=abs((E[8]-x)**2.0+(N[8]-y)**2.0-Vp2*(T[8]-t)**2.0)
    
    print(f1)
    fs.append(f1)
    print()
    
import matplotlib.pyplot as plt
%matplotlib notebook
mean_fs=np.zeros(len(fs))
means=[]
for i in range(len(fs)):
    print(fs[i])
    mean_fs[i]=sum(fs[i])/len(fs[i])
    print(sum(fs[i])/len(fs[i]))
    means.append(mean_fs[i])
x=np.arange(len(fs))
plt.plot(x, mean_fs)
#plt.ylim(0.4*10**6, 10**6)



# function to find minimum and maximum position in list
def minimum(means, n):
 
    # inbuilt function to find the position of minimum
    minpos = means.index(min(means))
 
    # inbuilt function to find the position of maximum
    maxpos = means.index(max(means))
 
    # printing the position
    print ("The maximum is at position", maxpos, "on the graph")
    print ("The minimum is at position", minpos, "on the graph")

minimum(means, len(means))
    

print(roots[8])
