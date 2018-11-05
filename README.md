# Baies-user-guide
User guide for Baies cloud
CPSL   
(Conditional Probability Script Language) A User Guide V3
1.	Introduction Defining Bayes cloud (CPSL)	
1.	Bayes interface guide (layout explanation)	
2.	Non-script guide	
3.	Scripting guide	
4.	Node’s Name	
5.	Node’s State Name	
6.	Numeric Data	
7.	Numeric Operators	
8.	Deterministic Operator	
9.	Stochastic Operator	
10.	IF-Statement Operator	
11.	Math Functions	
12.	Random Distribution Functions	

Introduction Defining Bayes cloud (CPSL)

The rise of BN (Bayesian Network) has needed to solve a lot of problems to build BN. One of problems was to control or manipulate CPD (Conditional Probability Distribution) efficiently, because if we need to deal with a huge number of values of probability distribution, it is very hard to manipulate it manually (Koller 2009). Generally, we have used a table in which we can input or change values of CPD. We have called it as CPT (Conditional Probability Table). By depending on a situation, CPT could be a large table. For example, a node which has 5 states has three parents which have 5 states respectively. The total of the entries or cells of the node’s CPT will be 5 * 5 * 5* 5 = 625. How can we input values into the entries or cells of the CPT manually? 
To solve this problem, a script language was developed by several BN software such as Netica, GeNie, and etc. Through a representation power of a script language, CPD can be generated effectively. Our goal is to use the script language in order to generate CPD as a language used for Conditional Probability. Generally, the script language has to have a method to express conditional statements with parents’ nodes’ states. The nodes’ states can be considered in several ways. For example, states could be categorical data, continuous number, or discrete number, etc. By a character of the states and a relationship between the parents and their child, we need to consider a way to describe the conditional situation. For example, if the relationship between a child and parents is related with arithmetic, a math equation could be used. If the relationship is related with a cause and effect by context described by a language, a language could be used. If a state comes from a database dynamically, a DB language could be used.  Therefore, we can consider several ways to deal with this conditional situation.      
1.	Bayes interface guide (layout explanation)
On the right side of the screen you should see the BNS window, here is where you can input java code for models

![Example](https://github.com/Tim0baies/Baies-user-guide/blob/master/BG1.PNG)

Registering models: By clicking on the registration tab located at the top right corner you can register your model into the Bayesian cloud
![Example](https://github.com/Tim0baies/Baies-user-guide/blob/master/BG2.PNG)
 
Searching: through the search bar located on the top left corner you can find other models related to a keyword by inputting that keyword into the search bar
 ![Example](https://github.com/Tim0baies/Baies-user-guide/blob/master/BG3.PNG)
 
Machine learning: this tab located on the top right is where you upload a csv file (setting parameters) that directly impacts the model that you are currently working on
![Example](https://github.com/Tim0baies/Baies-user-guide/blob/master/BG4.PNG)
 
Reasoning: the reasoning tab located in the top right corner is where you can easily set certain nodes in your model. 
 ![Example](https://github.com/Tim0baies/Baies-user-guide/blob/master/BG5.PNG)
 
2.	Non-script guide
Registration: If you have a model that you have made you can upload it to the Bayesian cloud after filling out the categorical information. After it is uploaded other people logged into the Bayesian cloud network can see or edit your model should they choose to do so. 
Searching: As mentioned before you can upload models and have them be viewed by other people likewise you may also search for other models in the Bayesian cloud by typing in a keyword that relates to that specific model.
Machine learning: This function allows you to upload datasets used to influence any model that you have open so long as the data set is in a csv file.
Reasoning: This function is a real time editor for whatever model is currently open. This is accomplished by stating the node name and then stating the node’s state (yes or no).
![Example](https://github.com/Tim0baies/Baies-user-guide/blob/master/BG6.PNG)

3.	Scripting guide
Operators are composed of three parts (Deterministic, Stochastic, and IF-Statement Operator). This is main part of CSPL, so we will look at it minutely. 


4.	Node’s Name 
Before making a script, a node might be used. Node’s name in the script has to be same with predefined node’s name and it is case sensitive. And it does not allow that node’s name to have space such as “Node 1“.

5.	Node’s State Name
By defineState function, node’s state name will be generated. Node’s state name could be “String” or “Number”. It is also case sensitive. And it does not allow space to be used such as “State Name “. 

6.	Numeric Data 
CPSL uses real numbers for every equation such as “double” in JAVA, because CSPL is based on JAVA, so we can use double style of numeric data. 
 [Double’s Range] -1.79769313486231570E + 308 to +1.79769313486231570E + 308

7.	Numeric Operators
Version 2 of CPSL provides the usual arithmetic operators “+ – * /” which are used in CPSL for addition, subtraction, multiplication, and division. 
![Example](https://github.com/Tim0baies/Baies-user-guide/blob/master/BG7.PNG)

8.	Deterministic Operator

p ( C1 | P1, P2 ) = P1*6 + P2;
Deterministic operator must begin with “p” function which has the current node’s name, bar “|”, and its parent’s name with comma. If there is no parents nodes, bar “|” should not be used. To operate this, the parents’ nodes’ states must be numbers, but not string such as “red, blue, and yellow”. Those numbers will be calculated an internal procedure. For example, P1 could have states numbers “1, 2” and P2 could have the states numbers “3, 4”, so there are 2*2 = 4 combinations. And they will be 1*6 + 3 = 9, 2*6 + 3 = 15, 1*6 + 4 = 10, and 2*6 + 4 = 16. These numbers (9, 10, 15, and 16) will be the state’s number of the current node. 
	![Example](https://github.com/Tim0baies/Baies-user-guide/blob/master/BG8.PNG)

 
9.	Stochastic Operator

p ( C1 | P1, P2 ) = P1 + P2 + NormalDist( mean,  variance );
Stochastic operator must begin with “p” function which has the current node’s name, bar “|”, and its parent’s name with comma. If there is no parents nodes, bar “|” should not be used. To operate this, the parents’ nodes’ states must be numbers, but not string such as “red, blue, and yellow”. 
If we want to use discretization for the continuous node, the current node’s state numbers must be predefined before using the operator. Those numbers will be fixed, but the states’ values will be generated by an internal procedure using “createCPT( node_name1, node_name2, … );” function. For example, P1 could have the states numbers “1, 2” and P2 could have the states numbers “3, 4”, so there are 2*2 = 4 combinations. And the current states are defined by “defineState(Continuous, 1, 2, 3, 4, 5, 6)”. The first parameter of the “NormalDist()” function is a mean and second is a variance. Internally, Random sampling, Discretization, and Normalization are implemented. As a result, below picture shows the result of the operation. 
![Example](https://github.com/Tim0baies/Baies-user-guide/blob/master/BG9.PNG)


10.	IF-Statement Operator

This operator has the following form.

if (condition) { statement; }
else if (condition) { statement; } 

The condition must be surrounded by parentheses “()” and should be several conditions such as “if ( p1 == red && p2 == sour )”. Version 2 of CPSL allows following rules for the condition. 

1.	First parameter of the condition part is for first parent’s states, and so on. 
2.	A symbol “&&” is used for the meaning of “and”.
3.	There is no a symbol for “or”. 


The statement must be surrounded by a brace “{}”. It could have Deterministic Operator, Stochastic Operator, and Assignment Operator. Assignment Operator has following form.

	stateName : stateValue				(EX: red : 0.5)

When we use this operator, all states and their values have to be described. For example, below sentence shows Assignment Operators.

if ( p1 == salty && p2 == 1 ) { red : 0.5; blue : 0.4; green : 0.1; gray : 0.0; }

All states of current node (red, blue, green, and gray) are described and their values are also. Sum of the values must be 1. On the other hand, the Deterministic Operator has following form. 


11.	Math Functions
Version 3 of CPSL has just arithmetic functions as “+, -, /, *“. In the future or by users needs, more math functions will be added.

12.	Random Distribution Functions
Version 3 of CPSL provides following Random Distribution Functions. In the future or by users needs, more functions will be added.
![Example](https://github.com/Tim0baies/Baies-user-guide/blob/master/BG10.PNG)
![Example](https://github.com/Tim0baies/Baies-user-guide/blob/master/BG11.PNG)








