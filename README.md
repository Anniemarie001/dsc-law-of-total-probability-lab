
# Partitioning and Law of Total Probability - Lab

## Introduction 
In this lab, you'll practice your knowledge of the law of total probability. In probability theory, the law (or formula) of total probability is a fundamental rule relating **marginal probabilities** to **conditional probabilities**.

## Objectives

You will be able to:

* Differentiate between independent and dependent events
* Perform partitioning based on known and unknown probabilities to solve a problem

## Exercise 1
Imagine you have two hats: one has 4 red balls and 6 green balls, the other has 6 red and 4 green. We toss a fair coin, if heads, you will pick a random ball from the first hat, if tails you will pick one from the second hat. 

What is the probability of getting a red ball?


```python
# Your code here
p_red = (4/10 * 1/2) + (6/10 * 1/2)
p_red
```

## Exercise 2
In games where at least one goal is made, a soccer team wins 60% of its games when it scores the first goal, and 10% of its games when the opposing team 
scores first. 

If the team scores the first goal about 30% of the time, what fraction of the games does it win?


```python
# Your code here
p_red = (4/10 * 1/2) + (6/10 * 1/2)
p_red
```

## Exercise 3

In Europe, except for regular gas, cars often run on diesel as well. At a gas station in Paris; 


* 40% of the customers fill up with diesel (event G1) 
* 35% with gas "Super 95" (event G2)
* 25% with gas "Super 98" (event G3). 


* 30% of the customers who buy diesel fill their tank completely (event F). 
* For "Super 95" and "Super 98", these numbers are  60% and 50%, respectively.


- Compute the probability that the next customer completely fills their tank and buys Super 95. 
- Compute the probability that the next customer completely fills their tank
- Given that the next customer fills their tank completely, compute the probability that they bought diesel. 

Hint: Consult the theorems for conditional probability, check for dependence or independence of events


```python
# Your code here
full_super_95 = 0.35*0.6
full_super_95

full_diesel = 0.4*0.3
full_super_98 = 0.25*0.5

p_full = full_super_95 + full_diesel + full_super_98
p_full

p_diesel_given_full = (0.4*0.3)/p_full
p_diesel_given_full
```

## Exercise 4

United Airlines operates flights from JFK to Amsterdam, to Brussels, and to Copenhagen. As you may know, flights are overbooked fairly often. Let's denote the probability of the flight to Amsterdam being overbooked equal to 40%, the probability of the flight to Brussels being overbooked equal to 25%, and the probability of the flight to Copenhagen being overbooked equal to 35%. You can assume that these events of overbooking are independent events.

- Compute the probability that all the flights are overbooked.
- Compute the probability of having at least one flight which is not overbooked.
- Compute the probability that exactly one flight is overbooked.


```python
# Your code here
p_all_overbooked = 0.25*0.40*0.35
p_all_overbooked

at_least_one_not = 1-p_all_overbooked
at_least_one_not

p_amsterdam_just_one = 0.4*0.75*0.65 # (1-p for other flights)
p_brussels_just_one = 0.6*0.25*0.65
p_copenhagen_just_one = 0.6*0.75*0.35

# When two events, A and B, are mutually exclusive, there is no overlap between these events. 
# The probability that A and B is the sum of the probability of each event
p_just_one = p_amsterdam_just_one + p_brussels_just_one + p_copenhagen_just_one


p_just_one
```

## Exercise 5
You have three bags that each contain 100 marbles:

- Bag 1 has 75 red and 25 blue marbles;
- Bag 2 has 60 red and 40 blue marbles;
- Bag 3 has 45 red and 55 blue marbles.

You choose one of the bags at random and then pick a marble from the chosen bag, also at random. 

What is the probability that the chosen marble is red?



```python
# Your code here
P_R_given_B1=0.75
P_R_given_B2=0.60
P_R_given_B3=0.45

#We choose our partitions as B1,B2,B3. 
#Note that this is a valid partition because, firstly, the Bi's are disjoint (only one of them can happen), 
# and secondly, because their union is the entire sample space as one the bags will be chosen for sure.
# i.e., P(B1∪B2∪B3)=1. Using the law of total probability, we can write

# P(R)=P(R|B1)P(B1)+P(R|B2)P(B2)+P(R|B3)P(B3)

P_R=(0.75*1/3) +(0.60* 1/3)+(0.45* 1/3)
P_R
```

## Summary 

In this lab, you practiced conditional probability and its theorem with some simple problems. The key takeaway from this lab is to be able to identify random events as dependent or independent and calculating the probability of their occurrence using appropriate methods. Next, you'll take this knowledge a step further and run simulations with conditional and total probability. 
