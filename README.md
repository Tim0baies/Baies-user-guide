# Baies-user-guide
User guide for Baies cloud
CPSL   
(Conditional Probability Script Language) A User Guide V3
1.	Introduction Defining Bayes cloud (CPSL)	1
1.	Bayes interface guide (layout explanation)	2
2.	Non-script guide	3
3.	Scripting guide	4
3.1.	Node’s Name	5
3.2.	Node’s State Name	5
3.3.	Numeric Data	5
3.4.	Numeric Operators	5
3.5.	Deterministic Operator	6
3.6.	Stochastic Operator	6
3.7.	IF-Statement Operator	7
3.8.	Math Functions	8
3.9.	Random Distribution Functions	8
1.	Introduction Defining Bayes cloud (CPSL)

The rise of BN (Bayesian Network) has needed to solve a lot of problems to build BN. One of problems was to control or manipulate CPD (Conditional Probability Distribution) efficiently, because if we need to deal with a huge number of values of probability distribution, it is very hard to manipulate it manually (Koller 2009). Generally, we have used a table in which we can input or change values of CPD. We have called it as CPT (Conditional Probability Table). By depending on a situation, CPT could be a large table. For example, a node which has 5 states has three parents which have 5 states respectively. The total of the entries or cells of the node’s CPT will be 5 * 5 * 5* 5 = 625. How can we input values into the entries or cells of the CPT manually? 
To solve this problem, a script language was developed by several BN software such as Netica, GeNie, and etc. Through a representation power of a script language, CPD can be generated effectively. Our goal is to use the script language in order to generate CPD as a language used for Conditional Probability. Generally, the script language has to have a method to express conditional statements with parents’ nodes’ states. The nodes’ states can be considered in several ways. For example, states could be categorical data, continuous number, or discrete number, etc. By a character of the states and a relationship between the parents and their child, we need to consider a way to describe the conditional situation. For example, if the relationship between a child and parents is related with arithmetic, a math equation could be used. If the relationship is related with a cause and effect by context described by a language, a language could be used. If a state comes from a database dynamically, a DB language could be used.  Therefore, we can consider several ways to deal with this conditional situation.      
1.	Bayes interface guide (layout explanation)
On the right side of the screen you should see the BNS window, here is where you can input java code for models
![example 1](https://github.com/Tim0baies/Baies-user-guide/blob/master/BG1.PNG/to/BG1.png)
  
Registering models: By clicking on the registration tab located at the top right corner you can register your model into the Bayesian cloud
 
Searching: through the search bar located on the top left corner you can find other models related to a keyword by inputting that keyword into the search bar
 
Machine learning: this tab located on the top right is where you upload a csv file (setting parameters) that directly impacts the model that you are currently working on
 
Reasoning: the reasoning tab located in the top right corner is where you can easily set certain nodes in your model. 
 
2.	Non-script guide
Registration: If you have a model that you have made you can upload it to the Bayesian cloud after filling out the categorical information. After it is uploaded other people logged into the Bayesian cloud network can see or edit your model should they choose to do so. 
Searching: As mentioned before you can upload models and have them be viewed by other people likewise you may also search for other models in the Bayesian cloud by typing in a keyword that relates to that specific model.
Machine learning: This function allows you to upload datasets used to influence any model that you have open so long as the data set is in a csv file.
Reasoning: This function is a real time editor for whatever model is currently open. This is accomplished by stating the node name and then stating the node’s state (yes or no).
 Example shown above.

