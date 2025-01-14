
00:06 _Daniel:_
Hello and welcome.
This is ActInf Guest Stream 52.1.
On August 10, 2023, we have Ahmed ElSaid, Alexander Ororbia, and Travis Desell.
Ahmed is going to give a presentation and following we will have some reflections and discussions.
So thank you all for joining and Ahmed to you for the presentation.

00:30 _Ahmed:_
Okay, thanks so much for having me.
Today I'm going to discuss the methods that we came up to solve new art, texture, search and neuralvolution problems.
The methods that are ant colony optimization based solutions.
So as the title here is mentioning, “ant colony optimization for neural text research and neuroevolution.”
This work is collaboration between me, my previous advisor, Dr.
Travis Desell, and my co advisor Dr. Alexander Ororbia.
I'm currently an assistant professor in University of North Carolina, Wilmington.
And moving on to the next slide.
So as an overview, the things that I'm going to discuss today, I'll try to give Bird Eyes view for what is neurovolution, why we what, why we need it.
And from there, I'll just try to discuss our methods that is based on end calling optimization which is called N based neurotropology search or ants for short.
And after that I will discuss how we advanced with this idea by introducing continuous ants or cans for short, which could spread off the discrete search space and replace it with a continuous search space.
And after that I'm going to also say what we did with the three dimensions and the continuous ants to have back propagation free cans.
And later I will discuss three of the points that we are considering for future work.
So in the machine learning learn, as the neural network structures got deeper and deeper, people were trying to optimize the structures to have better performance.
And people in different realms or different problem domain used to borrow the best performing architectures or structures and try to modify a little bit to work for their problem.
And they try to tweak some of the features of the structure and compare these different tweaks.
And then they say that we found the best performing structure.
But to actually find an absolute optimum structure concerning that solution, it would be an NP hard problem because to reach that solution, they had to try all the combinations of the different structural elements, right?
Because we have massive structures in these deep neural networks, it could be an NPR problem because we don't have computational power or enough time to actually train and test all these structures, all these structures constructed from these different combinations of structure elements.
So the alternative way to do this is to actually try to apply a meteoristic method to convert to a near to upper solution that is much better than not optimizing the structure or relying on kind of like a random search, right?
A random search can get us better performing neural network, but it's not going to give us a near to optimal solution or to converge to a near to optimal solution.
So a minoristic method would give us an automated method and also would converge to optimum structure new to optimum solution to this structure problem.
So the way that people approached Nas was by trying to mimic how optimization is done in nature, right?
So the first way they thought of it was trying to mimic how living organisms evolve in nature using genetic based algorithm like the Darwinian Genetic Evolution.
It started with Neat, it's a short for Neuralution of Augmenting topologies and it relied on genetic algorithms where also that concept also applied in most of the Nas and Neural evolution methods and Exam is one of them.
Travis came up with this method and it became one of the state of the art methods in Nas.
So in such methods we tried to again mimic genetic evolution by introducing new structural elements or removing structural elements or altering the structure through the evolution process, through the evolution iterations and through the evolution generations.
So we can apply mutations by splitting edges or adding edges or disabling edges, and we disable edges or disable some structure elements so that we don't lose that component, so that we can later on use it.
Kind of like a dormant gene in a genome, right?
So that it can appear in later generations.
Not to get rid of.
Totally.
So in mutations we can disable edges, we can enable them in later generations.
If we found that we want to try this option, we can also add recurrent edges or remove or enable or disable recurrent edges.
We can split nodes, we can take some of the nodes in a previous generation and we can just split it to two nodes and then take the edges connected to that node and try to divide it between the nodes that was generated from the previous node in the previous generation.
Also we can add nodes to the structure.
So all of these are part of the mutation process.
In the genetic process we can also disable a node if we want to try to just get rid of one of the nodes and disabling a node.
Or multiple nodes will also disable the edges connected to that node beside mutations.
The other side of a genetic process is to do crossovers where we have two of the best performance population meet together to bring an offspring and the offspring will have collection of the characteristics coming from their parents.
So it will take some of the characteristics from that parent, some other characteristics from the other parent, hoping that this would give us a better performing neural network or better performing generation.
So the main problem sorry, so the main problem with genetic based algorithms is that they start with minimal structures like we can see there, meaning that inputs and outputs and starting from the optimization with this minimal search space can trap the method in a local minima through the optimization process.
So we were thinking how to get rid of this obstacle by having a bigger or larger search space to start with, and then we can sample some solutions from that large surf space.
And we were looking around and we concerned end calling optimization, and I will say why, but I'll try to introduce the method first.
So, the method was first introduced as graphic optimization method, graph optimization method, sorry.
It was introduced in mid 90s by Marco DeRego.
Marco DeRego applied this method on a travel salesman's problem.
And the problem is mainly about a travel salesman who wants to visit a number of cities in a country using the shortest staff and considering this problem.
If we have different number, if the number of cities grows, then the permutations of these numbers of these cities that we have to consider to find the optimal solution.
If this number of cities grows, then we will end up having an NPR problem because we won't have enough time or computational power to have this exclusive solution done or this exclusive search done.
So, from his observations to answer in nature, he found that he can apply how they forage to find food in nature and then take this concept, this observation, and apply it in an algorithm to find the optimum path that leads from one point and to visit all the cities in the shortest path.
So this observation, this slide and the coming slides will just try to give us a picture of how hence forage in nature to find food and then how Marcus Rigor took that concept to apply it in the travel systems problem.
So, ants observers found that ants go out from their nest to find food and they try different directions, right?
And when they find food, eventually find food, they will take some of that food and then they will go back to their nest and in the way back, they will deposit some other substance, cholophone.
So they deposit that substance so that they communicate that path to the food resource with the other ants.
So actually, other ants do exploit this other substance, and when they sense it, they follow the path that the first ant took from the food resource to the nest, hoping that they will find food at the end of that path.
When they actually find food at the end of the path, they will take some of the food and do the same thing.
They will deposit some morpher mole on the same path, making it more appealing to other ants to take it, so that they can bring more food to the nest.
So this process shows us the exploitation behavior of ants.
But again, from time to time, ants also try to exploit some other food resources, potential food resources, and they kind of resist following the hormone traces, and they try to go away and find some new food resources for the nest.
So the ants are not only exploiters, they're also explorers and these two concepts were used by Marco Derago to kind of like balance the search for the better or faster path between the cities for the travel sales management problem.
The third thing that we observed also in how I spoke in nature is that the older substance, the pheromone, also evaporates.
So whenever a path to a food resource is not appealing anymore or the food resources are excluded, no more ants will take that path or when they take it and reach their food resources that is exposed, they will not take the same path to the nest again.
They will try to wonder and to find more new food resources.
And because they not going that path again and not depositing any pheromone on that path, the pheromone will eventually evaporate and disappears and making it less and less appearing for other ants to take.
So that's what Marco DeRego was looking at when he thought of the travel salesman's problem.
He applied that for the travel salesman's problem by making one agent try these different paths and then comparing through each iteration.
So that agent will take a path between the cities, right?
And then it will compare the length of that path to the previous experience with other paths and if it's shorter, it will try to deposit hormones on the segments of that path.
And eventually he was hoping, and he was right about what he was hoping.
He was hoping that eventually the shorter path, shorter segments that give the ultimate shorter path has more and more hormone deposits making it more and more appealing for the agent to take it through the iterations.
So we thought about this concept and we thought that it's very appealing to apply it for an Nas problem because Drago's solution was applied for a graph optimization problem and neural networks are in their sense direction graphs.
So we also considered endcon optimization because it's full torrent, decentralized and scalable and it's also easily traceable going back to being decentralized.
It made this method a perfect candidate for a pal and high performance computing solution which will eventually accelerate the optimization problem.
I think.
In the next slide, after the next one, I will discuss how we exploited or use this characteristic of anonym optimization to accelerate the solution that we came up with or the method that we came up with, which is ants and cans.
So this scheme, or the scheme of ants applying ants or ant collectimization in neural architecture search is depicted or illustrated in this flowchart.
So we start off with a massive search space expressed in superstructure which expresses or embodies a neural network that is massively connected, meaning that each node in that superstructure is connected with the other nodes through edges and recurrent edges, backwards and forward and backward recurrent edges.
And then we let a number of agents swarm over the structure from an input node to an output node.
So each one of these agents will pick an input node and then it wanders from that node through the connection recurrent edges and recurrent edges and between the nodes and between the hidden layers till it gets and picks one of the output nodes.
And then we take all these paths of the different agents, and we put them together to form a structure, neural network structure.
And we take that structure and train it and test it and then compare its performance to a population of best performing neural networks, best performance structures.
And if it's better than the worst in the population, then we reward the path that the ants took, the agents took over in the superstructure, reward with hormone so that it makes these paths appealing for later iterations through the evolution process or the optimization process.
That's if the generated structure is best than the worst in the population, if not, if it actually was worse than the worst in the population, then we discard that structure or that neural network, and we don't reward Any of the path that ants took.
And also the thermo evaporation will help us get rid of the pheromones that were deposited on the edges that are not giving us better and better structures.
And again, because the M colony is decentralized we exploited this by having an asynchronous solution or asynchronous evolution.
We had a main process that took care of generating the new structures and also updating the population the best performing structures and updating the hormone on the superstructure.
So the main process will generate structures and send them to worker processes.
The worker processes will train and test the neural network on the data that we have for the problem and then send the results back or the fitness of the neural network to the main process.
And based on that fitness the main process will either discard it or we'll take this fitness and compare it to the best performing in the population.
If it's better than the worst it will reward the path that ends took on the superstructure by depositing more hormone.
Or if it's worse than the worst in the population, we'll just start it and it will keep generating new structures and sending them to processes because the training which relies on that propagation is the most computationally expensive part in this process.
If we have a number of worker processes that can work in parallel to train and evaluate these neural networks, these new structures we can speed up the process, right by training and evaluating different structures at the same time in parallel in an asynchronous evolution scheme.
This is an animation but it's not working in this version of the slides because we're using a PDF but it's mainly a structure where you'll see edges or connections between these nodes fading or having darker colors based on the pheromone values through the iterations.
So each frame in this animation is kind of an update for the pheromone value of the edges based on the performance of the version of the neural network that were generated by the agents when they swarmed from the start node taking one of the input nodes in the middle layer and then from there going to one of the hidden layers in this one hidden layer that we have here.
And from there going to the output.
So that was the concept of applying ACO and con optimization in and this now I'm going to talk about the actual method that we came up with.
So it's more generic and more powerful neural texture search method.
More comprehensive if I may say that we opted to apply the methods on recurrent neural networks because they tend to be potentially larger than other neural networks structures because of their recurrent connections.
So we thought that if we started this problem though the method or the concept applies to any neural network but applying it to recurrent neural networks made it more appealing challenge for measuring the performance of the method that we thought of.
So this slide in the common slide will discuss the different heuristics of the methods of ants.
The first heuristic is superstructure itself and as I mentioned before it's a massive search space as massive as possible to be handled with the machine or the hardware that we're working on.
The superstructure consists of a neural network that is massively connected meaning that every node in the structure is connected to the other nodes via or through edges.
Forward edges and recurrent edges.
Backward forward recurrent edges and backward recurrent edges.
This simple structure that we have here represents one of just the concept of the superstructure that we apply in ants.
Here we have three input nodes, three hidden layers each have three nodes and one output node in the output layer.
And we are just showing one node connected to the other nodes through edges which are the ones representing green forward recurrent sorry, the edges are the one in gray and then forward recurrent and backward recurrent in the green and in the red.
And the concept of recurrent edges might be a little bit confusing if we look at it in this example because how can an edge be recurrent coming in and out from the same node, the nodes in the same timestamp but this structure might make it more clear.
So here we have structure that is pretty much similar to the one we saw before.
But here we have three input nodes, two hin layers still three hin layers each have three nodes and then alpha layer have two nodes and then we have also three time steps.
The current time step t zero and the previous time step t minus one, the one before that t minus two edges here are illustrated using the solid black lines.
Of course these edges are present in the current time step that is going to propagate through the neural network.
Then the current connections.
These ones are going to bring information or provide information from the previous time steps, the previous inputs or previous data that was fired to the nodes in the previous time steps.
And these recurrent edges are depicted here in red and orange.
The forward ones are depicted in red and orange.
The reds are coming from T minus one and the oranges are coming from T minus two.
And the backward current edges are the dot lines in blue and green.
And we can see that they are going backwards.
So they go backward to backward layers.
But because they are recurrent, we can do that because they process information, they bring information that already processed.
So we don't have to worry about propagating information back through time or back through the structure.
But we can do that if it's coming from previous time step.
The second heuristic in Ash is the colony weight sharing we wanted to use.
So instead of Brandon initialized the weights or the snapped weights and generated neural networks, we wanted to use the train weights to initialize the weights of the newly generated neural networks.
We did that by saving these neural networks on the superstructure.
We used the last equation here to do this update.
So we balanced between the weights that were saved previously and the weights that are coming from the trained or evaluated neural networks.
And we also used two strategies to do this update.
We used a fixed parameter phi or we left phi.
That was the first strategy.
The second strategy was to get phi by applying these two equations which relies on the performance of the neural network that was previously generated sorry, the previously generated and trained.
So it relies on the performance of the neural network that was trained and validated or tested.
So if the performance was good, then we will let the weights of that neural network to contribute more to the initialization of the weights of the newly generated RNS.
If it's not performing that well, then this equation will not allow it to contribute that much.
The third meta heuristic is multiple memory cells.
So at each node, when an agent or an ant reach to a node in the superstructure it will do a local search to pick the type of the neuron or the type of the node from these three different types of memory cells.
So in the generated RNN, the generated structure, the nodes in the structure is not all the same.
They will be different based on the local search that the agent will do or the ant will do.
At each node they reach through their path from the input to an output in the superstructure.
The fourth mineristic is the multiple ant species.
So we applied different species or came up with different species.
For the ants, the first species was the ones that will traverse over the edges, only the edges.
So they will go only forward through the edges of the neural network of the superstructure.
And these ones are going to define the number of nodes in the generated structure.
Also define the types of the nodes in the superstructure.
And when they done with their work, then the social or the second species, the social ants, will traverse between these nodes.
But they will use the recurrent edges to move between these nodes.
So they will create the recurrent edges for the newly generated RNN.
And we have two different species for these social ants or two different subtypes subspecies.
One is the forward social ends.
These ones traverse only over the forward kind of connections.
They go from the input to the output but only over the forward recurrent edges and then the backward recurrent edges or the backward social ends.
These ones go from the output to the input and they traverse over the recurrent connections.
The reason we thought about these different species is that we wanted to control the tendency of the ants to wander around in the superstructure exploiting the convoluted mesh of recurrent connections.
So we wanted to control that.
So we came up with this strategy so that we can just define the structure using the explorer ants and then the recurrent connections can be defined after that using the social ants.
The fifth characteristic is the regularization of formal basement.
Again, we wanted to give the ants in an incentive to bring sparser and also well performing neural networks by just penalizing them if they constructed denser or bigger structures.
So we added this regularization term and formula that updated the hormone value.
And as you see, the regularization term relies on the performance.
The data here is the performance of the neural network and it also relies on the size of the structure.
The last, the 6th and last one is jumping ants which is we want to experiment with.
If we let the ants if we let the ants jump over the layers when they move through the superstructure if we let them jump over these layers to construct the neural networks compared to if we restrict their movement to jump one layer at a time.
How would this end up performance wise if they will give us parser and well performing structures?
Or this jumping will hurt the performance by giving us weaker structures, weaker neural networks.
So.
We use a timespheres data that belong to Coal Fire Power plant.
We divide the data to have 7200 records for training and testing and here the plot shows that the data and we can see that it's nonlinear and it's acyclic and non seasonal.
So it's a hard problem for a non neural network solution or a regression linear regression solution.
So the input consists of twelve parameters.
When we were trying to predict only one parameter the flame intensity experiments covered all of the heuristics of ants giving different values for these different parameters.
The superstructures consist of twelve input nodes.
Three hidden layers each have twelve nodes and one output node in the output layer.
The recurrent connection span over three times steps one, two and three times steps.
In total, the superstructure had 49 nodes, 924 edges and almost 3.5 thousand recurrent edges.
So if you unroll the structure over 72 time steps in back propagation through time will have about 352,000 nodes, about 6.5 million edges and about 26 million recurring edges.
In the experiments, we also compared performance of ants using the same data set.
We compared it to exam and neat.
So Exam is the state of the art in neural texture search which is genetic based method.
We also compared it to NEET because it's like a benchmark in the neural revolution and nas realm.
And also we compared it to fixed structures, unoptimized structures that had one and two and three hidden layers and also different types of memory based cells.
The experiments covered 1600 experiments to cover all the combinations of the meta heuristics of the heuristics of ants.
Each one of these experiments was repeated ten times for statistical analysis.
Ants generated 2000 RNNs for each experiment.
Each trained for ten epics.
In total, ants generated about generated train and evaluated 32 million RNNs.
It took a month and 1000 CPUs to finish the experiments.
The results that we got showed that of course outperformed the unoptimized structures and it also outperformed Neat and then some of the combinations of ends outperformed Exam.
So Exam here is the fourth from the left and we can see that the mean absolute error for some of the versions or the combinations of ant heuristics outperformed Exam.
So we tried to look to do some statistical study for the results we got from Ads.
So we tried to look at the top performing neural networks coming in our results.
So we tried to look at the top ten, 2522 hundred and 55 hundred results and we look at the contribution of these heuristics in these best performing neural networks or structures.
We found that these heuristics contributed effectively in most of these results.
But the thing that was really intriguing for us or surprise us is that we saw that the recurrent connections disappeared in risk results because the best performing neural networks didn't have that much of recurrent connections.
That meant for us that the memory based cells did the job for recurrent information coming from previous time steps.
But we wanted to expand on this later.
So it's on our list discussing on our future investigations.
So this is just a summary for the achievements of Ans based on the results that we got from our experiments.
So ANZ was the first meta method to involve the core of ACO and column optimization and recurring neural networks.
Nas or neural heuristics to control ants tendency to wander around superstructure.
Exploiting recurrent connection proved successful because the regularization component or the regularization heuristics give us better results.
Showing here in this table and also the jumping ants here gave us better performance compared to non jumping ants.
And the realization.
Also, the weight sharing strategy also proved effective.
If we look at it, the results here compared to if we don't apply weight sharing.
So autopromyzing strategies are generic so the strategies that we use are generic enough to apply it for any problem or solution, that is end colony optimization based.
The Vermont deposition that the method that we came up with is also Novalu, which wasn't introduced in any previous literature.
And the performance of ants compared to the other benchmark and state of the art in the realm is also remarkable.
So going forward, we thought that ant gave us a good result.
But the main drawback of Ans was the discrete search space.
So ans worked on this massively connected massively connected superstructure, but it's massive gas, but it's still discrete.
Ants can move freely between these nodes.
They are forced to move over between these nodes, over these predefined connections, whether they are forward edges or recurrent edges.
So we thought of removing that continuous discrete search space and replacing it with a continuous search space.
So we designed a 3D search space where the search space had like layers representing the lag, the time lags.
And then ants can jump over between these layers to give us the recurrent connections.
And on each of these layers, ants will just give us the nodes and the edges between the nodes.
So in this slide, in the coming slides, we'll show an example of how ants move in cans or continuous ant, or continuous ends.
So an agent or an ant will just start by picking up one of the layers that will move on.
This is done in a discrete fashion and once this is done, it will then decide if it's going to do an exploitation or exploration movement.
And in this example, it decided to do an exploration movement.
So it will decide the angle and the radius of its next allocation on that layer.
Once that's done, it's going to go forward to that location and then decides if it's going to do an exploitation or if the next move will be exploitation or exploration move.
And this example will be an exploitation move.
So it will try to exploit the pheromone traces, the hormone that was previously deposited by other ants in the search space.
So it will use its sensing radius, that's something that is previously defined for each ant.
And then it will find the center of mass of the hormone traces.
And then when it calculates that center of mass of the hormone, it will consider it as its next location and then it will move to that spot.
And then it will decide about if its next move will be an exploitation exploration move at each location before it's deciding about the type of the step.
If it's exploitation exploration, it will also decide if it's going to stay at the same level at the same time lag or jump to a next time lag.
If the jump or the movement is on the same level, if the movement is on the same level, if the ants is doing an exploitation movement it will only consider the promontory that is ahead of it because it can't move backwards on the same time lag.
Otherwise it will be doing a backwards step which is not allowed in neural networks.
But if it's going to another time lag above layer then it's going to do a recurrent edge.
Current edges can go back in time sorry, back in the structure in the previous layer.
So now the end can consider all the promote traces within radius, the ones that are ahead of it and the ones that are behind it.
So in this example he is going to consider in this step is going to consider all the promote traces within its sensing radius, calculate the center of mass and then consider it as its next position.
And it keep doing this till it reaches to the proximity of the output node.
And once this is done, it will decide which output node it will consider as its final position in its path from an input to the output.
And then other ends will do the same.
And then we'll have different paths from some input and some output.
And then Cans will take these paths and then try to condense the nodes so that we don't have so much nodes that are very close to each other.
So the nodes that are within certain proximity will be clustered together using DB scan to have less number of nodes.
And then the paths will be taken, collected and put in a structure, a neural network structure.
And then sent to a worker process to train and test and then compare it to the population, the best performing RNNs.
And the process will be almost the same from this point will be almost the same as ants once the structure is constructed.
And the training and testing process will be the same as the ones that we discussed in ants.
So this was also an animation which shows how these tasks are taken by the ants.
Look from an input to an output in the 3D space 3D search space so ants, if we look at ants, ants have only eight tunable hyperparameters compared to when comparing this to ants and XM, it's half of the number of hyperparameters in the other methods.
These hyperparameters are the number of layers of the search space, the number of time of lags, how many of them we have in search space.
Number of agents, number of ants, which is similar to what we have a similar hyperparameter in ants the sensing radius of the agents or the ants the agents probability to create a new node which presents the exploration instead of the exploitation of the parameters or the hormone back traces in the space.
Node condensation parameters or factors the variables that represent in the DB scan are considered also hyperparameters in cans for one updating parameter and for one volatility parameter and these are also present in ants and ACO based problems solutions sorry the experiments used three times years different number of parameters and different sizes.
The results showed that the results that we got from Cans were very competing with ants and Exam.
They weren't necessarily better, but they competed.
They weren't the same level, but it also did didn't do very well in one of the database, the data sets.
But that was comparing the performance as the mean absolute error, but comparing Kent's results from the sorry.
The size of the neural networks that we got from Cairns, we saw that Cain's structures were sparser, so the performance was competing with ants and exam.
But the structures compared to ants were much sparser, similar to exam.
The size of the structures that we're getting from Exam.
Remember, exam is genetic based, meaning that we start the optimization process using the minimal structure elements but it was susceptible to local minimum traps and Tense is not susceptible to this problem.
But it also gave us smaller structures with performances that were competing with other methods.
Exam and ants.
So the advantages of Cans is that it has an unbalanced space compared to ants compared the results that came out were good compared to ants and Exam.
The tunable hyperparameters are half of these in Exam and ants and also it indirectly encoded the neural topology to 3D thrash spaces.
So this is one of maybe the contributions of important contributions cans then so far ants and Cans are solutions that applied neural topology architecture search meaning that they did not optimize the synaptic parameters of the neural networks during the optimization process or during the evolution process.
So we thought of actually making ends capable of doing this as well.
So to train the neural network or optimize the synaptic weights, the weights of the structure of the neural networks during the optimization process, the structural optimization process.
So we added a fourth dimension to the search space which we embedded the weights of snapdragon parameters in that map, these parameters in that new dimension.
We also wanted the ants to be self aware and try to evolve themselves through the evolution process so that they can adapt to the changes or adapt themselves so that they can give us better performance.
We want them to change their behavior, their characteristics like the sensing radius they had before, for example, that can be a variable that can change through the iteration thing and evolve through the iterations.
Each end can change these characteristics as the evolution goes on on progress based on the performance of the neural networks that they are generating.
So the advantage of doing this was that it eliminated the back propagation process which is the most computationally expensive part in the evolution process in the methods that we use so far in exam ends and Cans.
So eliminating the back propagation gave us much faster evolution process.
The results we got I will discuss the graph on the right hand side first which discusses the fitness or the Ms main absolute error of the results we got from back propagation free cans, the four dimension cans compared to the normal cans, the back propagation cans and ants.
So the results showed us that again on a particular database that that propagation cans and that propagation free cans did quite a similar job but they were both better than ants on this particular database.
But the actually main contribution or the main advantage of applying Cans shows up in the graph on the left hand side.
Because we can see that if you compare the results based on the time of the evolution based on the evolution time, we see that it took much less time than the back propagation version of cans and the ants using these different number of ants, Also this graph shows how fast back propagation precans compared to the normal cans.
In this figure the curves and the dollar lines shows the time that back propagation free cans and cans took to prepare or generate the neural networks.
We can see that back propagation frequency took more time to prepare or generate neural networks compared to back propagation cans or the normal cans.
And that's because the fourth dimension also has to evolve the ants or the agents through the iteration, so needs more time to do that.
But the other two curves in dashed lines, here are the lines that shows the amount of time it took for the two methods to train and validate the neural networks.
So backpropagation free cans doesn't have to train the neural network doesn't do backpropagation.
So you can see that the time it took is in an order of magnitude less than the back propagation version of camps.
And these sort of lines shows the cumulative time took for both methods and of course it shows that back propagation precances took much much less time than the back propagation precance took much less time than the back propagation cans.
The future directions that we are future points that we're concerning for sorry, the points that we're concerning for future work are to turn cans to a complete continuous search space.
So as you saw, the search space for Kents is not purely continuous because the time lags are represented by discrete layers.
We want to replace this with the continuous dimension continuous layer representing the time lag in RNNs.
However, this is a little bit challenging because the time lags has to be known prior to any optimization process because other than that we will be mapping the whole time series as time lags and then picking the time lags from them which is not feasible.
So this is the first point we're considering to investigate for in future work.
The second one is to investigate this finding that we found in the results in ants where the recurrent connections disappeared from the best performing structures.
The theory that we have is that the memory based cells replace these connections, give us the information that we need from the pastime steps so that they were more effective, more efficient in doing this compared to the recycle connections.
So we have to expand on this and investigate it more.
The last thing we want to consider also, this is one of the top things that we want.
These three points are the top on our list.
The third one is to actually consider one of the concepts that was coined in a book by Dr. Deborah Gordon where she mentioned that the living organism in an ant’s world are not the ants themselves, but they are the colonies.
The colonies are the organisms that they start, and they grow, and they interact with the environment and the ecosystem.
They interact with other colonies, and they die at some point.
And the ants themselves are not organisms.
They are the cells of these organisms, this colony organisms.
So we want to take that concept and apply it in our methods to have number of colonies living together in parallel, evolving and communicating with each other.
And we want to see if this would give us a better performance, because, after all, we're trying to mimic nature in the solutions we're trying to investigate.
So with this, I'm done with my presentation, and if you have any questions.

59:55 _Daniel:_
All right.
Awesome.
Wow, what a great presentation.
How about Travis and Alexander?
Either of you which want to go first, please feel free to give an introduction and any primary remarks that you have on that.

1:00:16 _Alex:_
Okay.
I can say something.
I don't have too much to add.
I think Abdul Rahman did a pretty good job going over the core bits of the work.
I'm Alex Ororbia.
I'm an assistant professor in computer science, an affiliate professor in psychology, and affiliate faculty in computational neuroscience at the Rochester Institute of Technology.
And I work on a lot of stuff, but primarily predictive coding, active inference variational, free energy, a lot of the stuff that's actually of interest to this.
Yeah, and this was a particularly interesting project for me because a branch of my own research is working in neurovolutionary methods or even just nature inspired metahuristic optimization.
And when I got the pleasure of working with Abdul Rahman when he was a PhD student at Know, we talked a lot about the ant colony based optimization approaches, and I encouraged him to look into sort of, like, the origins and also try to understand actually how physical ants behave.
So that was always fascinating to me.
I don't have too much to add in terms of the technical parts.
I think he covered all the core results.
The only thing I like to think about.
And I'm actually more fascinated, too, to hear from the active inference institute their interest in the ant colony methods and particularly what was interesting to them.
Because thinking about what does ant colony optimization how do you view it from an active inference perspective is, I think, particularly interesting and thinking.
And I even had a thought, I don't know if this was a question among the audience's mind.
Do the little ant agents or the cant agents that run and described what is there a way to start to view them as a multi agent system that's optimizing some variational free energy quantity?
Because a lot of even Carl's work I mean, I collaborate with him, sort of touches into this area of, like, well, what happens with collective intelligence and societal organization?
And you can kind of look at free energy from these very high level viewpoints all the way down to fine grained cellular activity.
And so I'm actually more curious to know Daniel and anyone else in the active inferences who can sort of explain their particular interest in ant based optimization and meta heuristic optimization.
I'm curious to know that.
But there could be some interesting viewpoints, like, what is the free energy?
I think the ants themselves are very mean.
We have made them more intelligent.
I know Abdul Raman and I talked at length about, well, what if we even made them, for example, have, like, a reinforcement learning control system?
And you could even imagine, well, now, what if the cans themselves engage in a form of active inference themselves?
What would that look like for the system?
And they are optimizing their own free energy.
Those are just fun little thought experiments.
We have obviously not worked on them.
At least Abdul Rahman was never exposed by me to that part of my world and biomimetic intelligence.
So those are my comments.
I'm not sure if they're particularly helpful, but they're very general, and I'm actually more curious to know from the active inference institute, their interest in it and where does that maybe perhaps intersect?
Or this is just like, oh, we know interesting topics and yeah.

1:03:52 _Daniel:_
Thank you.
Alexander.
Travis, you want to say hello and give any reflections on the talk?

1:04:00 _Travis:_
Sure, I'll come in.
Hopefully you can see me a little bit.
My jungle here.
Hi, I'm Travis is Sell.
I'm an associate professor at RIT.
I'm also the graduate program director for a master's in data science.
So if any of you are interested in any of this or data science, please shoot me an email.
No, I thought this work was really very interesting in a lot of ways while Abdul Rahman was working on it.
I think one of the coolest parts about it is a popular neuroevolution algorithm that came after neat is called hyperneet, and it transforms the discrete search space of neural architecture search into a continuous one.
And it's shown to be a pretty powerful method.
Well, this version of ant colony optimization, the new one, does the same thing.
It makes the search space continuous.
But what I found was really cool about it was that as opposed to traditional ant colony optimization where you have a graph and you just send the ants along the edges of the graph and you take the best paths and construct a graph after it.
Here the ants are actually working like ants in the real world where they'll move a continuous amount of space, not just from point A to point B and actually dropping down pheromones.
And it's more like a real simulation of how ants would move around in the real world.
And we're getting better results from it than some of the older methods.
So I think that really made me kind of happy to see that and thought it made it as very interesting work.

1:05:35 _Daniel:_
That's awesome.
Ahmed, want to add anything or I'm happy to give a thought on the answer and ask some questions from the live chat.

1:05:43 _Ahmed:_
I'm good.
Travis, I think, covered all the things that I wanted to say about, I think just one thing that Alex mentioned that we give higher intelligence to the agent.
This is something that we discussed and I'm pretty much open to that.
I started actually to think about it, but I didn't implement anything yet.
However, the last thing that I discussed in the future directions is something that I actually started working on, but I didn't start the experimentations yet.
So hopefully we will see something out of that.

1:06:18 _Daniel:_
Awesome.
Well, there's a ton of ways to go and isn't that kind of one of the fundamental questions like in an interactive setting, either pure agent stigma g interaction or multi agent, but ultimately mediated through multiple stigma g's with like reading and writing and error correcting code.
So in that communication setting, I felt like the work generalizes along multiple dimensions that previously approaches to multi agent just didn't have those kinds of flexibilities like the continuous time feature and several other features.
And I guess with respect to the ants themselves, I did five summers of field work with ants in the USA Southwest in Arizona and observed a lot of foraging activity.
So that problem or that context or setting is really a fun one and a pervasive one across any kind of living system, anything that's going to be active and living.
So why did you pursue foraging type algorithms overall?
And does this class include the interaction based methods with direct agent contacts that Professor Gordon highlights in the Ant Encounters book?

1:07:50 _Ahmed:_
Yeah, I will try to respond to this, but I just want to mention that the first thought about this actually Travis started this idea about using N colon optimization and neural sector search by applying this method in simpler neural networks.
Elman and Gordon neural networks required neural networks and I took the leap from there and started working on my thesis, my PhD thesis.
So we thought about this idea.
I think I mentioned a little bit about why we used an optimization in previous slide, but just repeating that for the audience to make sure that they got we thought about this idea because Nko optimization was applied as a graphic solution, and we thought that why not neural networks since they are investments?
Neural networks, they are directed graphs.
Neural networks are directed graphs because the flow of information goes from one direction to another direction.
So they are directed, but they also graph because they are nodes connected with edges.
And our ultimate aim or goal was to optimize the structure by removing and adding elements to it so that it gives us better.

1:09:11 _Daniel:_
Awesome.
And one way that Professor Gordon and others have talked about that bi directional learning relationship between the computer science and the math and the analytical formulations and then the field work and the actual behavior is because the thousands of species of ants.
They're working amidst a huge range of ecologies with all these different patterns of regularities, all these different resource distributions and foraging.
It's amazing how general it is.
Yet it's also just one of the functionalities that need to occur in terms of these even slower processes, like allocation of tissue to faster processes, even of response to alarm pheromone.
So it's like this one class of algorithms clearly scales across from few.
Ultimately one some of these foraging algorithms are lone foragers they don't leave pheromone trails.
So it's like even the idea of leaving a single positive pheromone or leaving but also there's things models can do that ants can't do, like the time travel, pheromone, lossless perception, high dimensional signaling profiles that can't occur just with like finite amounts of molecules.
Now they are just persisting on their path as active agents within one generation with a variational free energy at the behavioral scale, then across generations with that evolutionary layer.
And the relationships between the neural network implementation and the active inference model.
They're kind of like two ways of describing, implementing.
Yeah.
I'd be curious to hear any of your thoughts on where you see active inference coming into play or how do you see ultimately similarities and differences between neural network based approaches and active inference based approaches.
Are they the same complementary, overlapping.

1:11:12 _Ahmed:_
Guys?
Want to take this one?

1:11:16 _Travis:_
I think this might be more of an Alex question, to be honest.

1:11:20 _Ahmed:_
That's the test.

1:11:22 _Alex:_
Well, yeah, I mean, if you want to keep it on active inference.
But I think, Travis, you're going to need to tag in when you want to get into the very specifics of the actual ant colony details because, again, I kind of see the ant colony optimization from a more global point of view.
I would say so to be mean this particular work.
So that way Abdul Rahman is not also completely blindsided by your question, Daniel, even though the name is in the institute itself, this isn't an active inference.
You know, again, while there are obviously, as you pointed out, lots of interesting elements like, for example, the fact that the ants when they conduct their exploration along let's just think about the recurrent networks and they're figuring out what nodes and what as Abdul Rahman explained the superstructure, right as they iterate across with their pheromone trails and figure out what nodes I want to recurrently, connect, feed, forward, connect, skip, connect, so on and so forth.
You.
Would say.
Well, okay.
What these ants are doing is they're engaging in epistemic foraging, which is a key concept in active inference or idid.
So that way Abdulrahman and Travis are not also left behind by a jargon epistemic foraging and active inference.
It's a big general framework.
It's like a neurobiological process to RL.
And epistemic just refers to kind of like the uncertainty Travis that you and I work on.
And the idea is it's saying, well, OK, I want to understand my world.
And the more that I explore my world, right, there will be things that surprise me less.
But if I encounter some information that is really weird when I build a generative world model or a predictive world model, that's very surprising, I should probably explore that.
And so, of course, I'm condensing the concept down into sort of like the exploration part of the explore exploit trade off that I know, you know, but that characterizes reinforcement learning.
So that's just what we mean when we say epistemic or epistemic foraging.
And obviously, Abdul Rahman foraging can be likened to what the ants are doing, right?
They're exploring their environment.
And so I guess with that in mind.
So that way everyone's sort of on the same page here to get to your question about the differences, about how does this work versus your typical neural based approaches to active inference.
And I would fall into that category of, oh, I build neural models, biological process models.
Those are very much focused, you could say, at the individual level, at least the ones that I am aware of.
When you're building, for example, even a back propagation based, partially observable Markov decision process in active inference, that's like a single agent, right?
You're trying to build this construct that is trying to balance the epistemic quantity with its instrumental term, which, by the way, another jargon term for you, Abdul Rahman and Travis, that's just like your reward signal or your prior preference or a prior distribution over goal states.
And so these agents sort of like deal with that trade off, but at an individual agent level.
Now, again, I'm sure that there's interpretations of these from other perspectives, the ant based approach, even though I would not argue per se that this has at least an explicit form or a connection, at least that Abdul Rahman has made clear to active inference.
But the idea is that this is like a multi agent approach to active inference.
And so the ants, when they conduct their epistemic foraging, which arguably is a very simple model, each ant and of themselves is essentially a bunch of coefficients and some hard coded rules because their job is essentially to work together with their pheromone trails to figure out oh, what parts of the superstructure are useful.
So I'd say that that's different and it lends itself in some ways.
Of course, you can make the ants more complicated and lose the benefit of I'm just about to say you could massively paralyze this.
And this is one of the key strengths that I think is natural.
In, for example, a lot of actually nature inspired optimization algorithms and ant colony optimization is one of them.
Is Abdul Rahman has been using hundreds of CPUs, and you can put these ants on their own individual processor, and the communication that's occurring across them as they exchange information is through the pheromone trails.
There's an indirect mechanism, it's not terribly complex to facilitate.
And I'm sure that there's even better ways to go about doing asynchronous forms of communication and further, further optimize this.
I know Travis and Travis can add to this has done things on like, citizen science and distributed computing through volunteer computing and how you can distribute this through a massive global Asynchronous network.
So you can imagine adapting the ant form sorry, the ant colony optimization approach to some distributed, massively distributed version of active inference, where you essentially have to write down that the variational free energy.
And I'm putting quotes around this because, again, there is no concrete term written in Raman's work because at least we haven't viewed this from the active inference perspective directly.
Each ant is optimizing its own variational free energy, but then there's probably a global quantity that sort of is related as a function of those pheromone trails in the individual ant agents.
And then of course with the exploitation term or the instrumental or what is the reward signal to give an RL term that's sort of driven by the performance of the actual agent on each candidate agent on the task right of the ram.
And you compute like mean squared error when you're doing time series prediction.
So in some sense we have built in a reward function that we use and again, for those in the active inference group here, you can use the complete class theorem and look at the prior preference of saying, oh, well, the reward is actually technically a prior preference, right?
It's like a log probability.
So with that in mind, you could squint at ant colony optimization.
And I guess the big benefit comes from that massive parallelization that you wouldn't actually very easily, if at all, get with our single agent neural based approaches.
And that might be an interesting place to build on and I'll stop rambling at this point.
I'm not sure if that was helpful.

1:18:03 _Daniel:_
That was awesome.
Even earlier today, Chris Fields in the Physics as information processing course was talking about the classical information inscribed on the blanket, which is like the pheromone perception and deposition, pheromone modification and perception sense making an action which we can associate with the nest mate cognitive system.
So then there could be as simple as a pass through for the nest mate, could be any arbitrary relationship described with a blanket, simple nest mate, sophisticated nest mate, like another level of time series modeling, whereas there's the environmental time series modeling and that's just in the ants.
And then the fourth dimension is like that quantum rotation which goes from the lower dimensional classical stigmagic screen into the quantum informational space.
And so that's one of the discussions ongoing in Actimf right now is about well, previous approaches to connect quantum formalisms to macro, let's just say neural phenomena based it upon the plausibility of like a molecular electronic bubbling up.
Whereas just with research from decision making and statistics and just multiperspectival modeling and all the issues associated with the physicality of information transfer, the finiteness of it, the quantum formalism becomes useful just by itself with or without reliance on some other electronic phenomena.
So it's just a lot of very interesting connections like having the degrees of freedom on the blanket which could be noiseless and four bits or it could be noisy with this really specific thing.
But in Silico you get to play it from both sides and scale things up and down and do these meta heuristics on top of that arbitrary space could be really simple for learning, or it could be however much.
And then just like the ant colony algorithm is ultimately federated through embodiment, that property makes it a really useful candidate for biomimicry.
So a lot of times when people think about collective behavior, they're thinking about like the flock of birds and the school of fish and those are of course collective systems and collective behavioral and all these kinds of complex systems properties can be studied in that type of system.
But it is also neglecting at least an analytical degree of freedom with the stigma g.
So that really opens up both the quantum and the classical information or both niche modification and behavioral and cognitive modeling.
So just to add on because I think and then also what the node is could even be heterogeneous or unknown or fit in different ways or fix through design processes.
So just like the ant colonies are flexible, enabling them to live in all kinds of places, make all these kinds of nested decisions that interact with each other, that flexibility is just like the tip of the iceberg, of what we could even just describe, because there would always be real environments we hadn't yet tried with ant colonies.
So we really would never know the full extent of all the repertoire and the dynamics of the ant system.
But then we can just abduct into new mathematical statistical distributional frameworks, pull back to different levels of the learning and the meta learning process and just start there.
And then almost ironically, or maybe the opposite of that, it.
Could be applied to ant colony video data or movement data or foraging activity itself.
But it kind of takes inspiration and develops in parallel or in conversation.
So it's not like bound to what real ants can do.
Or you could constrain it so that there are properties that real ants have, like they can only interact within this certain way or there really are only this many pheromones do model comparison.
So it's a lot of degrees of freedom.
I feel like you all are opening up with the ant collie modeling.
And also one of the challenging pieces of multi agent simulation is kind of like the open endedness with the design space.
So then it's very hard for even creative ideas like sometimes to find the right compute resources that obviously are still even needed for what he discovered with the analysis.
Here I'll ask a question from Bert.

1:22:47 _Alex:_
In the to before we move on to that, I just want to clarify just so make sure that I got the right term and certainly Abdul Rahman and Travis might want to look it up is when you were saying blanket, you were referring to a Markov blanket, correct?

1:23:01 _Daniel:_
Yes.
So the technical definition of Markov blanket is when you have a Bayesian graph where nodes are the variables and edges are relationships amongst these variables.
For any given node of interest, we'll just call it internal states.
So these are not features of the world.
It's not tagged onto some tissue of a real nest mate in the world.
This is something that's tagged onto or like a perspective we could take on any node in a Bayes graph and then all the nodes that insulate it and the co parents are known as the blanket in the sense that it's like one layer insulator.
And there's a lot of more discussion on it and the philosophical implications and all these generalizations of that.
But broadly, the Markov blanket is just the inbound dependencies which we associate with sense making and perception learning attention; and then the outgoing dependencies for the agent which we associate with action influence in some downstream pointing way.

1:24:00 _Alex:_
Thank you.
I just wanted to clarify that because I don't think Abdul Rahman and Travis might be familiar just with that terminology.
It's very know, very active inferenc-y kind of jargon.
So I wanted to make sure that they got that from the physics point of thanks.

1:24:16 _Daniel:_
Yeah, totally great point.
And ask a question now from Bert.
So Bert says.
Very impressive.
Solving generative models with more generative models sounds very promising.
What about replacing ants with convolutions?

1:24:37 _Ahmed:_
Talking about like a meta learning algorithm, like having a neural network that learns how to optimize other neural networks?
Yeah, this concept, I think is introduced at some point in machine learning learn.
But we wanted to apply for nature based method that mimics like the Mother Nature, which is… nature is the most efficient optimization evolution system.
So looking at the results that are there in nature applying nature based methods they were superior to any other method.
And the results we got also which just pointed that out that we saw good performance coming out from these results from our results and the previous results from other methods as well.

1:25:34 _Travis:_
Hop in here a little bit too.
In the case of neural architecture search there's kind of a couple of classes of approaches.
One is constructive, so kind of like where you build larger and larger networks and try and keep your network size minimal to try and find your optimal solution.
Other types of neural architecture search approaches use like a superstructure and this is kind of how the earlier iterations of this were where you have a bound of your search space and you try and find the optimal network within that bound.
So one is like trying to build things from the ground up and the other one is trying to trim down a big network to a small network.
As to your question about convolutions, there's been a fair bit of research lately in what's called graph based neural networks which can use convolutions over like a discrete graph search space and can potentially produce other graphs.
And I believe there's been some neural architecture search work using this.
But one of the main and I think cool things about the approach here, which is different from those is if even if you have a graph based neural network and you have your search base defined as some kind of matrix where things are off and on depending on which nodes are connected to each other.
You have a fixed search space which may not be big enough or it might not be the correct search space for this neural architecture search problem where this method here is all continuous.
Right?
So within this continuous search space it gives the algorithm a lot of freedom, maybe too much freedom but a really open ended way of generating a wide variety of neural architectures which if you preconstrain your algorithm to work within a fixed discrete superstructure you may not even find them because they're not even a possibility.
So that's one of the reasons we didn't go that route.
But there are graph based neural architecture search algorithms out there where basically you take the architecture as a graph, you train a neural network to spit out another graph that it might think is better and those use convolutions.
Sometimes that helps.

1:27:44 _Daniel:_
That's awesome.
So convolution sounds like yes.
And one thought on that is yes, the ants solve all these incredible patterns and kind of do amazing things amidst informational and physical limitations like we all do having the ants be able to just make trade offs within a task space and then have a dial as modelers to make that task space.
Kind of like touching the pheromone distribution or metacognitive ants or something emulating essentially that.
And for example, the active inference forward looking and thinking through other minds that there could be a kind of cognitive colony.
So then that enables in silico total thought, experiment colonies and through data driven processes also kind of keep continuity with that model, perhaps literally continuity with the model and then connect it to empirical, which is something that is very hard for agent based modeling which, as you kind of pointed to, often sets certain fixed axes, performs like asweep looks at one mechanism, doesn't look at all these possible mechanisms of learning and intra and intergenerational and all these time effects.
So how do you see this being used in different research or application domains?

1:29:38 _Ahmed:_
Well, the main use case that we're thinking of was neural architecture search to apply it for other domains other than neural architecture.
We didn't figure out that yet.
I think Alex can explain on that.

1:30:00 _Travis:_
I can hop in a little bit mean.
So basically this type of algorithm, if you need to generate graphs and you don't necessarily have a fixed structure for that graph and when I say graph, I mean like a computer science graph where you have nodes in a different so pretty much anything involving graph construction.
I think these types of methods work.
Neural networks kind of under the hood can be represented as graphs and usually are.
So I think we're using it for neural networks because it's really popular but there's other algorithms out there like the traditional traveling salesman, there's like routing problems, all that, any type of stuff where you might need to generate a graph in a smart way to do that.
To your other point though, I think what's really cool here and I don't want to steal Alto Robin's thunder, but his last point on future direction is while a particular version of this ant colony optimization search is running to find an optimal neural network, a colony has fixed parameters that it operates within.
But if you think of the colony as an organism as opposed to the ants being an organism, you can evolve colonies that optimize how the ants themselves act.
So you can have evolving colonies that in a smaller sense also evolve or optimize what they're doing within their prescripted parameters for the agents they're generating.
So you can have like a meta meta.

1:31:34 _Daniel:_
It's awesome.
I mean the evolutionary account of a why question for ant behavior today, one part of that answer is like because colonies that couldn't under that regularity or constraint survive.
We've had a long, long time to wipe those off the table.
And so every biological system has to have that kind of multiscale ordering.
In 2021 we made the active imper ants paper which was modified from an epistemic foraging visual attention task about scanning around and then learning a cicade policy that had to do with epistemic foraging but not leaving a trace.
And then the main modification to bring that active inference epistemic visual foraging model into the active inference ant setting was to add a pheromone rule, just like you described, even though, of course, again, that's not the only pheromone rule, but that's just the most simple pheromone rule that we can generalize from, as you definitely have.
And there are just many emerging ways of modeling those multiscale active inference models.
So composing across layers, which we might associate more with the kind of laterality of things that happen through interactions.
And then also, as Mike Levin shows, with kind of the time diamond systems that have a memory retention component of some shape, cognitive shape, and then a protention awareness or agency or other attributes you can use to describe that.
And that's a statistically amenable way to describe things.
And then there's a variety of implementations on a given statistical problem, or like Federated Compute architecture, it might be the case that you're not running the pure matrix multiplications that are shown in the early MATLAB code of active inference.
Different components of machine learning systems might be kind of composed together, also ways kind of abiding by those patterns of communication.
But then there's a level of abstraction that we can still describe, but it doesn't mean active inference is going to be kind of causing it.
So that's what gives a lot of flexibility.
And it's really cool that through your background, Alexander and work and these kinds of collaborations that like the active inference perspective on multi agent modeling with all these other views can at least come together comparatively.
And then that is going to, I think, be quite an interesting interchange to apply this entire tissue type or colony type thinking above and within the models.
Just a lot of degrees of freedom, like you said, could be too.

1:34:33 _Alex:_
And I think there's different ways too, I think depends on how you want to take the ant metaphor.
And again, it's kind of interesting, some of the questions or comments that you're making, Daniel, and some from the audience about how does this think about it from a cognitive point of view.
I mean, I do work in cognitive architectures, of course, again, kind of from the whole single agent or single entity and modeling a single brain in its different regions.
But I think if you take a nature inspired optimization approach like the ant metaphor that Abdel Rahman latched onto, and that's sort of like the way in which he formalizes how takes a principle of how ants interact with their world, interact with each other, and then mathematically model those particular concepts step by step.
And I think if you bend the metaphor and say, well, okay, could the ant colony metaphor apply to multi human agent systems, right, or other entities?
Does the ant necessarily can it be generalized beyond the physical creature upon which Abdul Rahman based his initial metaphor?
And that's an interesting philosophical kind of take to it.
And then how do you apply that to, let's say, building a multi agent cognitive system.
And then, of course, as Travis was discussing with you and you were mentioning metacognition know, you could think of ant colonies, of ant colonies, but you could even replace the word ant and just say, well, we have clusters of intelligent agents, or whatever degree of modeling we're doing.
Because again, I do want to emphasize that at least the cans and ants agents that I have worked with in the context of the Raman, they are not each and of themselves, even, I would argue, if nothing else, a very extremely simplified generative model or a very simple control system.
There's no neural network under each one because then you'd have to simulate computationally each one of these ants within the framework.
So I think there's always that practical machine learning kind of viewpoint of, well, there's always how do you simulate that?
And Alderam is working with CPUs.
It's not like he has an army of GPUs to replace them with convolutional networks.
Again, if you had the resources, this would be awesome.
But expense and money is another constraint on this planet.
But I think there's interesting views and interesting directions one could go by taking inspiration from the ant metaphor and the concept of pheromones and translate them to other real world signals and how, for example, communication patterns among other animal entities or other human agents.
And I think that that opens up an interesting perspective.
And if you're constantly trying to connect it back to free energy minimization and trying to say, well, how are we balancing the terms that you can decompose it into an epistemic and an instrumental, and how are these balancing out and how are these physical processes that we specify balancing those terms?
That's just a very interesting place to be.
And you mentioned active inference versions of Hans, and that's fascinating and of itself.
Last comment I have is, again, the degree of modeling and what you are modeling.
Like, if you're modeling a society or organization, that's one way.
You could use the ant colony framework, if you will, or metaheuristic optimization frameworks to then cast a system, any type of complex multi agent system, as an active inference kind of engaging process.
Or you could go really low level and think about cells in a body or units that make up organs or organelles and trying to say, well, can we use this to model that level of granularity within, like a human or an animal entity?

1:38:38 _Travis:_
Right?

1:38:39 _Alex:_
And I think there's some fascinating questions about how does this metaphor manifest itself at different timescales and different degrees of perspective about how you're modeling?
What are you looking at?
What's the picture that you want to emulate?
And of course, there's always under the hood, this practical consideration of, well, okay, the computational expense that you allocate, and are you able to actually run that simulation long enough?
Because I think Abdul Rahman, you can correct me if I'm wrong.
You mentioned one of the experiments I think was for the bigger systems took a month.
Right.
Of course this was on CPUs.
That can get pretty prohibitive if you want to go even bigger than that.
But again, I think it just depends on what hardware you have to simulate this on.

1:39:24 _Ahmed:_
Yeah.
And also using high performance computing, it is not always feasible for smaller.
So if we try to model the brain of Aims like small neural network, using a GPU might not be feasible solution.
And Travis is a high performance computing specialist here, expert tell you that sending data to a GPU and getting it back is very time consuming and resources consuming.
So it will worsen the time consumption rather than solving it, because communicating between the main memory and the GPU had an overhead.
So it has to be a big enough problem to actually utilize this GPU in such solutions.

1:40:16 _Travis:_
Sorry, go ahead.
When you have the super large language models, or large models for computer vision, they do a lot of just massive operations on Tensors, which are basically multidimensional matrices, right?
And when you have really big wide Tensors, you can parallelize the operation really nicely across the GPU.
A lot of this work is based on doing time series forecasting, time series classification on sensor data, stuff from like power systems.
So the input to a large language model might be 1000 or more length of a word embedding, which is actually not huge.
But if you go up to a computer vision model, the input image may be 1000 by 1000 pixels and that gives you actually a million inputs.
Right.
When you're working with sensor systems, off of aircraft, power plants, that type of thing, you may have 50 to 100 inputs.
And when you're working with this type of time series data, you don't need a massive super wide neural network.
And then if you add in recurrency where you have to do backprop over time and other things like this, you actually can't really parallelize it nicely on a GPU.
So for us, the CPU is actually more efficient.
We tried Abdul Rahman wrote a bunch of code a long time ago to put this stuff on GPUs and we found it was quite a bit slower.
So, depending on what you're doing with a neural network, a GPU actually isn't the right answer.
But the other cool thing about this, which I think does have maybe even potential for there, is that one of the big not talked about problems in machine learning is that back propagation is the fastest thing we know, but it's inherently not scalable.
You can get a bigger, better GPU to do your bits of your network in parallel to speed things up, but that only gets better if you have a bigger network.
If you want to speed up the training process, you can't just add another CPU or another GPU and make back prop go faster.
You can make the forward and backward pass through your neural network faster.
But you still have to do every epoch of backprop.
Iteratively a method like this where we're generating one, it's backprop free.
So it's not using backprop.
We can use a nature inspired or other method to use hundreds of computers and you can throw twice as many computers at it and get a result twice as back, twice as fast, whereas backprop you can't do that.
So if you think about actually being able to train a neural network backprop, actually it's got a pretty low speed limit for what we need to do.
And it's kind of a big problem with the machine learning community that people don't like to talk about because they're like oh, I'll just buy the next big Nvidia GPU and that'll do things faster.

1:43:02 _Daniel:_
That's super interesting.
Does this maybe even bring up a kind of relationship where things like a graphics visualization of course a GPU does well and that's like the screen changing through time with a classical process that can be massively unfolded.
And then the cognitive models, ultimately, of the nest mates, which again, can be nested.
But the thing that's more quantum, more cognitive model, like you can do in parallel, because the minds are not influencing each other except through stigma g.
So then that is CPU bound, the size of the colony.
And then you could use different graphics techniques, like there are colonies, organisms.
So one ant being or it's a philosophical question.
What is the scale at which A exists?
But all throughout California with the Argentine ant, for example.
And so how do we deal with those kinds of meshwork cognitive systems all the way on through 50 in an Acorn?
There's just all these different trade offs that are being made and like in the featureless deserts there's different wayfinding pathfinding sensor integration, polarization of light, like different cognitive strategies because they might be going out long distance and dragging something home, not leaving any pheromone because it's not any more likely to have food there.
So in that case, the stigma g is basically minimal to essentially none.
And then in other situations you could have something that's very adherent to distributions to the point of being fit to a very kind of normative path.
But that's happening at a level that allows the different compute architectures, different information architectures and ultimately different biological embodiments to really engage fruitfully.
Again looking at the variability, the diversity of biological algorithms for collective behavior which have been studied by Professor Gordon and others in so many different angles.
Yet sometimes it can feel like multi agent models always start kind of like at square one, demonstrate some proof of concept phenomena, and then that is utilized as part of a bigger perspective.
But it's not like that model was ever claimed to have been tuned to maximum performance.
It's like well, we got decision making behavior.
You could transfer this to group decision making with Honeybee decision making or something like that, but there's still a big gap there.
But I think what you're describing with the Kant, which is funny because it could be cannot, but also the Kant is the dialect which is spoken.

1:46:00 _Travis:_
It was very funny when we came up with it.

1:46:04 _Daniel:_
Great choice.
And it's just like yeah, because there's multiple perspectives to swap from on the classical screen because the meaning of the word is something that's happening.
That fourth dimension, cognitively, the meaning of the word isn't to be found just on the blanket, just on the interface itself.
That's just the communication.
And that's like a bounded system.
Then if you model a cognitive system that doesn't have that kind of a constraint, so represented by a map that has some kind of blanket index, some kind of blanketing if you don't embody that constraint in the statistical model, the map, you're ignoring one of the fundamental constraints of modeling the way that things happen in an embodied fashion.
Maybe there's some abstract space for a certain problem that's just like a total slam dunk.
However, for full generality, at least to the space that we know of, biological life forms and their engagements and ecological engagements, not just like within one behavior, that space is so vast and there's so much to learn across different systems within two.
Again, to abduce away into different information architectures and active inference being some subset or type of those.
So it's awesome work.
Do you have any last comments?

1:47:37 _Ahmed:_
Well, giving ability for brands to be self aware and aware about its environment is actually something that we implemented in our last work with the BP free camps.
They are indirectly aware about their environment and they are adapting to the changes in their clinical environment by indirectly meaning that they are evolving using a genetic based algorithm to just change their behavior, like how they sense the hormones when they take the steps and some other times or some other characteristics they have.
So they are adapting, but kind of like not in an intelligent way, but through evolution.
If you want to say, actually, we considered putting a brain in each one of these agents.
But then again, as Travis and Alex mentioned, we found that it won't be practical.
Actually, it would hinder our Asynchronous design because we couldn't prolize that it will take time to train each one of these brains as we evolve the neural networks.

1:48:58 _Daniel:_
Awesome.
Alexander or Travis, any last thoughts?

1:49:12 _Travis:_
Okay, I'm just really happy.
I mean, I think this work is really interesting and it opens up a lot of pretty cool avenues.
Again, if we can get to the point where we're evolving colonies that are producing ants and can see where that can go.
So one of the big issues in neural architecture search is the whole question of what is an optimal neural network and what an optimal neural network is.
Could be different for what will be different for different tasks.
But not only that, even if it's the same data set, how you're using that neural network could lead to a lesser, more optimal neural network, right?
Depending on what you're doing with it, maybe you need one that's more energy efficient.
Maybe you don't care about energy efficiency or performance, and you'll take a slower neural network, but you need more accuracy.
So being able to have algorithms which can automate this whole process for us and tune them to what we actually want to use the neural network for is really important.
And I think, one, just having ant colony optimization be able to optimize a network for a problem is great.
But two, if we can make it such that the algorithm itself is self optimizing, it really can streamline this whole process where right now, if you're doing machine learning, it can be kind of miserable.
You make a neural network architecture, you try it out, see how well it does.
Oh no, that didn't do so well.
Let me tweak a couple of knobs automating that process.
My whole life as a computer scientist is about being lazy, but being smart about it.
So whatever I can optimize so that I don't have to do it over and over again seems like a good use of my time.
So I'll be smart about having to do as little as possible in the future.

1:50:59 _Alex:_
I don't have too much to add to that.
I think a lot of the good discussion has happened already, and we talked about various implications and ways of viewing ant colony optimization from other perspectives, including an active inference point of view.
So I guess really more from a closing thought on my end, is that it will be interesting, or it is an interesting direction to think about, like I said earlier or suggested, about the adaptation of the metaphor to other systems.
And what are you trying to model and what's your goals from a scientific and philosophical point of view?
What are questions you seek to answer?
And I think it might be very interesting, again, given other developments and computing technology and ways in which you implement.
The parallelization that, I think, is that's what attracted me the most to a lot of these meta heuristic algorithms, even things like particle swarm.
And when I worked with Travis many years ago on the exam algorithms, you saw our names on that and working on that type of stuff.
The part that always caught my attention is, again, that ability to say, I can put these entities on different processing, computing, processing resources or devices, and then they will interact and exchange their results in some way to try to optimize some often complex multi objective cost function.
And so I think the part that we'll see or that would encourage the wider spread adoption of even like meta heuristic algorithms in general, not to say that they aren't used a lot in, for example, the engineering domains is again the development of parallel computing processing systems and I think exploiting things like asynchronous computing.
That was again another angle that caught my attention from Travis.
He's done a lot of work on genetic optimization and neurovolution from an asynchronous point of view.
And how can we allocate, whatever resources are available and distributing them across global networks?
I think that might be the best shot to scaling up, let's say, with what we got right now.
There might be again, you've mentioned, Daniel, quantum technology.
Quantum computing is another interesting place that sort of like changes the barring technologies that we don't necessarily have exactly at their best at this moment.
How can we take advantage of citizen science or distributed computing or peer to peer type of communication and building massive active inference systems that embody like the multi agent metaphor of ant colony optimization or other nature inspired frameworks?
And can this system evolve over very long spans of time, just like evolution really worked?
Another piece, my final comp and is that why I'm interested sometimes in evolution is that to me it is the inductive bias that provided us with structures that allow, for example, a human agent.
Babies can to operate already.
Babies can already recognize faces, right?
And we have certain instinctual reactions and certain mechanisms that evolution has endowed us with.
And so a fascinating question is what is the interplay of the idea of simulating an artificial form of evolution?
Maybe building DNA structures or very simplified computational structures?
Which would answer Abdel Rahman's concern about, well, maybe we don't want the agents to be too smart in of themselves because I can't really simulate that unless you give me like a decade to run the simulator.
But you could maybe come up with a more fundamental primitive and then use that as a starting point for your neural network.
Let's say, Daniel, you want to do some task in image segmentation and like okay, but what can your evolutionary framework give me?
Well, I'll say here here's a template to start from.
This is a kernel on which you build your framework and it's like a DNA structure.
And this has evolved across many years of distributed peer to peer computing.
And you could imagine building this mammoth evolving, continual learning style evolutionary algorithm, whether it is based on genetic algorithms or ant colony.
And you could imagine that might be an interesting way to think about.
And by the way, I am spitballing and generating an idea of how I could envision a scalable form without inventing a new computing system that I don't know will or will not exist because quantum has a lot of problems still to solve too, like superconducting or super temperatures or trapping photons, as I have learned.
So that might be an interesting direction.
I think the scaling of this, especially from the practical end, is going to be the most important.

1:56:03 _Travis:_
We're going to.

1:56:03 _Alex:_
Need to pull together all the tools that we have, as I mentioned before.
So I'll stop there, too, because I'll let Abraham blame more, so hopefully that made sense.

1:56:13 _Daniel:_
Well, this was very epic and inspiring, so good luck with the work.
You're all welcome to suggest another piece that we might focus on or continue the discussion however you see fit, because it's super interesting direction.
So thank you.
Till next time.

1:56:34 _Alex:_
Thank you.

1:56:34 _Travis:_
Thank you so much.

1:56:36 _Ahmed:_
Bye.
