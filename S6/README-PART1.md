# PART 1

![](https://github.com/Himank-J/ERAV2/blob/main/S6/Screenshots/Backprop.JPG)

Above screenshot highlights implementation of backpropogation by tracking each step and execution via excel.

For implementation, following steps were followed:

## Step 1: Define each variable

i1, i2 are input nodes and a_o1,a_o2 are output nodes.
- Starting from i1,i2 - we calculate h1 by adding (weight1 x input node1) and (weight2 x input node2). Similarly use weight3 and weight4 for calculating h2
- Next is a_h1,a_h2 which is calculated by taking sigmoid of h1 and h2
- Starting from a_h1,a_h2 - we calculate o1 by adding (weight5 x a_h1) and (weight6 x a_h2). Similarly use weight7 and weight8 for calculating o2
- E Total is already defined as summation of E1 and E2 which are also defined as seen in image.

## Step 2: Calculate w5, w6, w7 and w8

Calculation for w5					
- ∂E_total/∂w5 = ∂(E1 + E2)/∂w5	_(E Total is E1+E2 as defined in step1)_			
- ∂E_total/∂w5 = ∂E1/∂w5	_(w5 does not contribute to E2, hence ETotal = E1)_				
- ∂E1/∂w5 = ∂E1/∂a_01 * ∂a_o1/∂o1 * ∂o1/∂w5  _(E1 wrt w5 is equal to E1 wrt a_01, a_o1 wrt o1 and o1 wrt w5 - refered from step1)_					
- ∂E_total/∂w5 = ∂E1/∂w5 = (a_01 - t1) * a_o1 * (1 - a_o1) * a_h1	_(Final value for ETotal wrt w5)_				

Similarly we calculate w6, w7 and w8 - 

Calculation for w6					
- ∂E_total/∂w6 = ∂(E1 + E2)/∂w6					
- ∂E_total/∂w6 = ∂E1/∂w6					
- ∂E1/∂w6 = ∂E1/∂a_01 * ∂a_o1/∂o1 * ∂o1/∂w6					
- ∂E_total/∂w6 = ∂E1/∂w6 = (a_01 - t1) * a_o1 * (1 - a_o1) * a_h2					
					
Calculation for w7					
- ∂E_total/∂w7 = ∂(E1 + E2)/∂w7					
- ∂E_total/∂w7 = ∂E2/∂w7					
- ∂E2/∂w7 = ∂E2/∂a_02 * ∂a_o2/∂o2 * ∂o2/∂w7					
- ∂E_total/∂w7 = ∂E2/∂w7 = (a_02 - t2) * a_o2 * (1 - a_o2) * a_h1					
					
Calculation for w8					
- ∂E_total/∂w8 = ∂(E1 + E2)/∂w8					
- ∂E_total/∂w8 = ∂E2/∂w8					
- ∂E2/∂w8 = ∂E2/∂a_02 * ∂a_o2/∂o2 * ∂o2/∂w8					
- ∂E_total/∂w8 = ∂E2/∂w8 = (a_02 - t2) * a_o2 * (1 - a_o2) * a_h2

## Step 3: Calculating a_h1, a_h2

Calculation for a_h1					
- ∂E_total/∂a_h1 = ∂(E1 + E2) / ∂a_h1
   				
- ∂E1/∂a_h1 = ∂E1/∂a_o1 * ∂a_o1/∂o1 * ∂o1/∂a_h1		_(E1 wrt a_o1, a_o1 wrt o1 and o1 wrt a_h1)_			
- ∂E1/∂a_h1 = (a_o1 - t1) * a_o1 * (1 - a_o1) * w5					
					
- ∂E2/∂a_h1 = ∂E2/∂a_o2 * ∂a_o2/∂o2 * ∂o2/∂a_h1  _(E2 wrt a_o2, a_o2 wrt o2 and o2 wrt a_h1)_						
- ∂E2/∂a_h1 = (a_o2 - t2) * a_o2 * (1 - a_o2) * w7					
					
- ∂E_total/∂a_h1 =  (a_o1 - t1) * a_o1 * (1 - a_o1) * w5 + (a_o2 - t2) * a_o2 * (1 - a_o2) * w7					
					
Similarly Calculation for a_h2

- ∂E_total/∂a_h2 = ∂(E1 + E2) / ∂a_h2					

- ∂E1/∂a_h2 = ∂E1/∂a_o1 * ∂a_o1/∂o1 * ∂o1/∂a_h2					
- ∂E1/∂a_h2 = (a_o1 - t1) * a_o1 * (1 - a_o1) * w6					
					
- ∂E2/∂a_h2 = ∂E2/∂a_o2 * ∂a_o2/∂o2 * ∂o2/∂a_h2					
- ∂E2/∂a_h2 = (a_o2 - t2) * a_o2 * (1 - a_o2) * w8					
					
- ∂E_total/∂a_h2 =  (a_o1 - t1) * a_o1 * (1 - a_o1) * w6 + (a_o2 - t2) * a_o2 * (1 - a_o2) * w8

## Step 4: Calculating w1, w2, w3 and w4
Using everything we defined above, we can now easily calculate w1, w2, w3 and w4 - 

Calculation for w1					
- ∂E_total/∂w1 = ∂E_total/∂a_h1 * ∂a_h1/∂h1 * ∂h1/∂w1					
- ∂E_total/∂w1 = ((a_01 - t1) * a_o1 * (1 - a_o1) * w5 +  (a_02 - t2) * a_o2 * (1 - a_o2) * w7) * a_h1 * (1 - a_h1) * i1					
					
Calculation for w2					
- ∂E_total/∂w2 = ∂E_total/∂a_h1 * ∂a_h1/∂h1 * ∂h1/∂w2					
- ∂E_total/∂w2 = ((a_01 - t1) * a_o1 * (1 - a_o1) * w5 +  (a_02 - t2) * a_o2 * (1 - a_o2) * w7) * a_h1 * (1 - a_h1) * i2					
					
Calculation for w3					
- ∂E_total/∂w3 = ∂E_total/∂a_h2 * ∂a_h2/∂h2 * ∂h2/∂w3					
- ∂E_total/∂w3 = ((a_01 - t1) * a_o1 * (1 - a_o1) * w6 +  (a_02 - t2) * a_o2 * (1 - a_o2) * w8) * a_h2 * (1 - a_h2) * i1					
					
Calculation for w4					
- ∂E_total/∂w4 = ∂E_total/∂a_h2 * ∂a_h2/∂h2 * ∂h2/∂w4					
- ∂E_total/∂w4 = ((a_01 - t1) * a_o1 * (1 - a_o1) * w6 +  (a_02 - t2) * a_o2 * (1 - a_o2) * w8) * a_h2 * (1 - a_h2) * i2

## Step 5 Exceuting backpropogation using Learning rate

- Using above calculations we define excel formulas and use values for all defined variables to implement back propogation
- After getting initial values, we execute - w - LRx(∂E_total/∂w) to go further down
- Repeating above steps gives us our final Loss values which can be plotted on a graph

## Loss Visualization

### LR = 0.1
![](https://github.com/Himank-J/ERAV2/blob/main/S6/Screenshots/backprop-0.1.JPG)

### LR = 0.2
![](https://github.com/Himank-J/ERAV2/blob/main/S6/Screenshots/backprop-0.2.JPG)

### LR = 0.5
![](https://github.com/Himank-J/ERAV2/blob/main/S6/Screenshots/backprop-0.5.JPG)

### LR = 0.8
![](https://github.com/Himank-J/ERAV2/blob/main/S6/Screenshots/backprop-0.8.JPG)

### LR = 1
![](https://github.com/Himank-J/ERAV2/blob/main/S6/Screenshots/backprop-1.JPG)

### LR = 2
![](https://github.com/Himank-J/ERAV2/blob/main/S6/Screenshots/backprop-2.JPG)




