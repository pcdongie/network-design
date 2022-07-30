# hazmat-network code

In our reseach,  we deal with a hazmat network design problem considering the uncertain choice behavior of users, and develop a branch-and-benders cut algorithm
based on Benders Decomposition idea. At the same time, in order to improve the algorithm performance, a series of acceleration strategies are proposed. 
In the part of numerical experiments, we illustrate the effectiveness of the algorithm and model, and analyze the sensitivity of important parameters. 
The code of this study is open accessible in GitHub repository.
## .xlsx file
These files contain the data used in our study, including the road network information and carrier choice utility metrics.
## Original problem.py
This file solves linearized MILP model in our paper. In this model, we do not design any algorithm and acceleration skills, but completely use
gurobi's default solution method.
## classical BD.py
This file applies the classical BD algorithm to solve the MILP model, but does not adopt any acceleration strategy, that is, iteratively solve the
master problem and sub problems, which is called BD algorithm in the paper.
## ABD.py
The file applies BD algorithm framework to solve MILP model, adopts the acceleration strategies proposed in the paper, and then iteratively solves the 
master problem and sub problems until convergence, which is called ABD algorithm in the paper.
## BBC.py
This file applies the BBC algorithm proposed in our paper to solve MILP problems, all acceleration strategies are adopted, and the algorithm is embedded
in a branch and cut computing framework. Almost all the decision-making results in this paper are calculated by using this file.
## SPP.py
In this file,  the user choice is modeled by the shortest path problem, and the optimal network design decisions are solved . The calculation results of 
this file are used to illustrate the advantages of considering uncertain route choice behavior. This model is called SPP model in the paper.
## risk_neutral carrier.py
In this file, users are considered risk neutral, that is, the expected value of route travel cost is used to calculate the choice utility. The calculation 
results of this file are used to illustrate the advantages of considering users' risk aversion. In this paper, this model is called RNM model.
## reference point mean.py and reference point upper.py
These files are used to compare the influence of different reference points on the network design solution. The solution result of this file corresponds to 
Figure 10 in the paper.

Note: we have conducted many experiments. For the solution of different model parameters in the experiment, we need to manually adjust the parameters in the
code file, and then run it again.
