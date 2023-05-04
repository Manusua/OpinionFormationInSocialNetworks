# Opinion Formation in Social Networks

This repository summarises the work done by Manuel Suárez and is part of the final degree project he presented on may 2022 and was directed by professor Simone Santini.
It presents a series of simulations that aim to predict the way a population in a certain social network interact between themselves and change their opinion while more and more iterations among them happen.
The model only considers interactions between two nodes (i speaks with j and vice versa) and the opinion exchange follows, as stated in[https://doi.org/10.48550/arXiv.1007.1790](Mehdi Lallouache et al.) by the following equation
$O_i(t+1) = \lambda(O_i(t) + \epsilon_{i,j,t} O_j(t)) \\
O_j(t+1) = \lambda(O_j(t) + \epsilon_{j,i,t} O_i(t))$
where $O_j(t)$ and $O_i(t)$ are the opinion of nodes $j$ and $i$ at a certain time $t$ and are included between -1 and 1. All the iterations are charactereized by a saving parameter $\lambda, 0 \leq \lambda \leq 1$ and a stochastic variable $\epsilon_{a,b,t}, 0 \leq \epsilon_{a,b,t} \leq 1$ that represents the influence power a certain node, $a$, has over the other one, $b$, at a certain interaction $t$.

All the simulations follow the same proccedure, a graph (social network) with a certain number of nodes - users - (it's been seen that for popuations bigger than 600 the behaviour is the same) is designed and multiple iterations are run. In every iteration, each user makes a single interaction with each of the users it is linked to (an edge in the graph is drawn between the two nodes) and their opinion vary according to the previous equation. After several iterations, it's been seen that there are two main posibilities:
* The whole population reach a consensus (typically on the centered opinion, 0). This is called the consensus state.
* The whole population is completely polarized and the final opinion of the population, represented on a 2D segment taht goes from -1 to 1, is on the extremes of that segment. This is called the polarized state.

The main results are divided in two parts. Firstly, to obtain a value of $\lambda$ for which the whole population tends to polarize or to reach the consensus. Secondly, and after having obtained that $\lambda$, we introduce a new type of user of the social netork, the media, who do not vary its opinion as long as different interactions happen and we analyze how does this new type of user affects the previous results.

## Obtaining lambda critical value
In this chapter we analyze how different factors affect to the opinion the population (I) reachs at the end of all the iterations (N iterations). For doing so, we design a new metric as follows:
$\frac{\sum_{i\in I} \abs{O_i(N)}}{|I|}$
where $|I|$ represents the size of the set $I$, the number of users of the social network.
The factor $\lambda$ is charactereistic of each social network and keeps constant among all the interactions, there it is the importance of obtaining the $\lambda$ critical. Knowing it can be predicted the long-term behaviour of the people of that social network.
