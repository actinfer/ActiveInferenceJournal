00:05 _Daniel Friedman:_
Hello and welcome.
It's January 26, 2023.
We're here in active inference model stream number 8.1.
Today we're appreciative to have Thomas Ringstrom, who will be presenting on Reward is Not Necessary, a compositional theory of Self Preserving Agents with Empowerment gain maximization.
There will be a presentation followed by a discussion.
So Thomas, thank you for joining.
Really looking forward to this.
Off to you.

00:37 _Thomas J. Ringstrom:_
Yeah, thank you very much.
It's really nice to be here and talk to this group.
I'm a computer science PhD student at the University of Minnesota.
My interests are in what are the computational properties that we would need to have agents which flexibly plan in sort of high dimensional product spaces of variables, and also how do we get agents to perform complex tasks in an intrinsically motivated way, especially in high dimensional product spaces.
So this presentation is going to argue that reward I know I'm talking to a sort of active inference crowd, but some of the same points apply to active inference perhaps too.
But this presentation is mostly about how there's going to be some major problems.
I think using reward maximization objectives, and by moving to sort of reward free objective functions, we can get really nice factorizations that help us plan.
So let's just start off with a sort of simple, picture simplified picture of an organism.
So we have a honey badger here.
This honey badger has internal states.
It gets hungry and it gets thirsty.
And there's also an external world that the agent lives in.
And in order to sort of modify internal state spaces, the agent might have to perform some complex tasks.
It might have to get several items in order to eat an apple or things like that.
So you could see that maybe some symbolic state space sort of mediates the connection between things you do in the world and transformations that you make on some internal state space.
And of course, real world organisms and humans live in a high dimensional world.
So you could imagine that there's an encoder and a decoder and really there's a sort of high dimensional physiological or interoceptive domain that is these Y tilde with the dot or Y tilde, I should say, and Z tilde.
And then there's a high dimensional world.
You could just say that's x tilde.
And really you just need to sort of map these down to some discrete state space in which these domains can interact here's like a simple encoder and decoder.
If an agent has a kind of simple ontology like this, you can imagine that it's sort of generatively entrained to the world that it lives in, which is a notion that's probably pretty familiar to sort of active inference people.
So you have some encoder of these high dimensional states and then you have some operator PS, which is in the middle of the head here.
And that just sort of advances the latent states.
And then you decode and you'll get sort of expectations of the high dimensional world that the agent lives in.
The problem is that you can't really represent explicitly these latent space transition operators that would dictate the dynamics of all these variables.
You can't represent it as an explicit object because the more state spaces that you keep track of in the world, the larger this object PS becomes.
So in order to handle this, you'd have to represent it in a sort of factorized form.
So you just would represent its factors.
You wouldn't explicitly sort of enumerate all of the state vector transitions under this transition operator.
And so what we really need to think about is what are the sort of model based or the sort of bellman principles for decomposing hierarchical state spaces so that we can create the right representations that help us plan in a flexible way in a sort of time varying, time dependent world of lots of variables.
So this just means what is a sort of objective function l calligraphic L applied to PS or its factorization that would give us some factors here ada and these omegas that could help us plan.
And also, given the fact that the state space, the effective product space that we're working in is so large and there's many possible state vectors that describe possible states of the world, how do you know what to do?
I mean, if you're an RL theorist, you would have to say, well, there exists some kind of reward function that tells you this state of the world is worth this much reward and this state of the world is worth this much reward.
But it's not really clear how you should define reward functions on huge product spaces.
So I will address this question from sort of reward free perspective.
And just to give you a hint of what it's going to be like, what I'm going to argue is that what we really need are agents that have a kind of structured core ontology that it needs to maintain.
That is coupled state spaces that really depend on each other, in which the policies that you use maintain the sort of internal integrity or controllability of the agent.
And that's where empowerment will eventually come in.
So I'll talk about empowerment a little too.
That's the controllability metric.
So here I'm just saying what's a nice policy or what's an objective function f that takes in some intrinsic motivation function, which is this fancy V here, along with a nice factorization that allows you to plan in the world.
Okay?
So just to recap things that I already said, we're in a product space of state of variables.
We have internal and external state spaces, hunger and hydration state spaces can be dynamic.
As you do things in the world, you get hungrier.
So how do we plan?
How do we know what a good goal is?
And what I'm going to argue is that we should compute a specific representation called a state time feasibility function, which is going to be an abstraction that's going to map us from initial state times to final state times.
And this will have some really nice properties that allow us to sort of reason in this high dimensional state space.
And I'm going to talk about this from just a dynamic programming point of view.
There isn't going to be any learning.
Okay?
So let's just talk about transition operator composition, because I said, well, we have this large product space of state variables and it'd be nice if we just represented it as a factorization.
So what does that mean?
So imagine that you have PX, which is like a base state space to move around the world, and you have some internal state space or secondary state space PY.
And these are linked by some function f.
So here's your base state space.
And here's the honey badger in the state space.
And here's the secondary state space, which is just like your internal hunger space.
And so F, what F is going to be is called an availability function.
And an availability function is going to say, oh, this honey badger is in state XAT at time T.
And given that it's there, what's the probability that this goal is available from this state time, state action time.
And so this goal is formally going to be an action on the higher level state space.
So for instance, these green lines on the high level state space are going to map you to the most satiated state where you're not hungry anymore at all.
And then these black lines on the internal state space are just going to decrement you one state if you're not at the tree, so you eat apples at the tree and that's going to map you to the top.
And all other states without a tree, you're going to get hungrier over time.
Okay, so if we wanted to write a product space operator PS y prime, x prime, we can just represent this as a composition where lambda P is our composition operator, and it's just going to be defined as the product of your two state spaces with F linking them.
And then we sum over G.
So we're getting rid of the goal variable and so we can represent the product space this way.
And we can also just call the product space.
We can say that bold S here is just the state vector for yx, or if we have more variables that can be incorporated into bold S.
Okay, so what if we have more features of the world?
We can drink water, we can get warm at the house.
Well, we will need to have a bigger composition.
So we can just create an operator called we'll just call PR, where bold R is just state vector of w y and Z, and w y and Z correspond to the hydration, the hunger, and the temperature space.
And so this is just a product of the individual ones, individual operators.
And so this influence graph is connecting PX to Pwpy and PZ through F.
And so we can just define the product space operator as a composition this way.
And if we do that, you start to realize, well, this is nice because the effective state space exponentiates essentially as you add on more state spaces that you can control.
And so this influence graph is just showing what is the sort of ontology of the agent, what constitutes it as its internal and external coupling.
And you could imagine that it gets more complicated, for instance, that if you hit W zero or Y zero or whatever, these skull and crossbones indicates that you die.
So you can imagine being in a state has a bi directional influence.
So Zeta here is conditioning the possible dynamics PX can produce.
So you could imagine that once you're in one of those sort of defective bad states that it kills you and you can't move around.
So you could imagine sort of more complicated structures like this, which essentially mean that you have to go out in the world and do things in order to keep the system alive.
So you don't want to hit W zero or Z zero.
And you can imagine this gets even more complicated.
You could compose sort of larger structures where P sigma is going to be some logical state space that keeps track of multiple conditional events that need to occur for say, eat an apple or something like that.
So representing it in this form is very nice.
We just represent the factors and the links between the state spaces and that's a sort of memory efficient way of representing the space.
Okay, so if we have a homeostatic task, I'll eventually get to the sort of Bellman equations and the model based formulas.
But first I'm just going to sort of build up an intuition in the form of an example about how these state time feasibility functions are going to work.
The state time feasibility function being the representation that I'm arguing for in this talk.
So if we have a hiker and it can go out into the world and drink and eat and get warm with these goal variables, well, there's also this goal variable, G epsilon, which is going to decrement by one state.
Then as the hiker moves around, you could represent this as a function.
So imagine that the hiker starts at xg one, that's the house, and TS, which is the start time, and the hiker follows a policy pi two.
So imagine that you have a policy that is like a goal condition policy pi G two that's going to take you to xg two.
Okay?
So it's a policy, it's like a shortest path policy or whatever, then that means that there's going to be some final state time xg two TF that you achieve this goal G drink, which remember is in action on the higher level space.
So what this would look like is that you decrement two, right, because that takes two time steps to get to the lake.
And then once you get to the lake, you take the state action that's going to drink and it's going to bring you up.
So there's three total steps in this process of inducing the drink goal variable and then the step after drinking, which would look like this.
And then you can imagine the other state spaces are not involved and so they will all decrement three because there's three time steps.
And so one way to represent this is to realize that if all of these sort of goal variables on the way to the lake are sort of the null goal variables, meaning that the agent isn't affecting some other state space, then you can define that as a Markov chain.
So if you set all of the goals to be the epsilon goal, the null goal, then this PY epsilon is going to be a Markov chain matrix.
And so that means that the time difference encoded in the state time feasibility function, the TF minus TS is going to be the power that you can take this Markov chain to in order to forward evolve all the other internal state spaces.
So you can define an operator that does this in one step called Omega Y, which is just going to take some initial state.
So this green dot or this red dot, and it's going to take the time difference.
So this is going to be two to get from the house to the lake.
It's two time steps.
And so these gray arcs are just an initial to final state map under this policy.
And so what this looks like, this looks sort of complicated, but you can build a jump operator that jumps you from your initial high dimensional state.
For instance YXT.
And we're just considering Y for now.
I don't have the other state spaces W and Z in here, but this Ada over here is mapping you on the X space.
The Omega Y is mapping you forward in the Y space and then the PY and the PX are just evolving by one step to update after you hit the goal.
So after you hit the goal, you have to update by one step.
So PY and PX do that for both state spaces and then of course you can do this for all of the state spaces.
So a jump operator for all of the internal state spaces, r, where R is remember, is the vector of all your internal states w, Y and Z.
Then this is similarly defined where omega R is just the product of all of these other Omegas.
So we defined Omega Y up here, but you can just define this for all of your other state spaces.
So now that we've done that, we can continue our journey by going to the tree.
And so that's two steps away.
So all of the other things decrement two and then an additional one.
And then if we go back to the house, that's four time steps away plus the additional time step of entering the house and getting warm.
Okay, so here is another route you could take where the hiker goes to the tree to eat and then the hiker goes to the lake to drink and then goes back to the house to get warm.
And so this JS is a huge it's important to keep in mind that JS is a huge operator and we cannot explicitly form it in memory because it's unless we have a lot of memory on our computer.
But having this factorization allows us to chain policies together and evolve a high dimensional state vector in these jumps.
So we're jumping a state vector around in this object oriented fashion where each state vector is updated once you get to some key object of interest, such as the tree with the apple or the lake with the water.
So also in this example, you can see that the agent went from the lake to the house.
And technically, if z, it occupies the lowest state, z zero.
And so technically it should die at the skull and crossbones on the map, but we let it finish his journey.
And we haven't talked about this sort of bi directional coupling yet, but we'll do that in the next slide to make that concrete.
All right, so if we have these defective states, we can define mode parameters e plus and E minus, which are just going to be variables that condition our dynamics.
And we can have a mode function that takes any vector r and R is any vector of blue, green and red squares in the space, and we can map it to a mode parameter.
So we can define zeta to map to the good mode, the normal healthy mode, if it's not occupying any of the defective states.
But if one or more defective states are occupied, then we can map it to E minus.
And so that means if we have some low level transition operator that's indexed by E, that means we can split it into a normal dynamics PE plus and a defective dynamics PE minus.
And you just notice that the defective dynamics is a sort of identity operation.
It just sort of arrests your dynamics in the space so you can't move around, but the normal dynamics is just normal grid world movement.
Okay, what we can do is we can compute a set of individual feasibility functions for each object of interest in the map.
So in the previous example, we had two trees, two lakes and a house.
So we have five state time feasibility functions.
And then this Ada hat is an aggregate function of all of these functions where the pi is indexing the corresponding pi for that function.
Anyone can ask questions, by the way, if they have any questions.
All right, so the full dynamics is going to be just defined like we defined it before, where we have these two state spaces, the base state space coupled to the internal state space through F.
But then we have this zeta R here on the conditioning side.
And so this is an operator that you have to achieve goals in order to keep yourself out of these sort of absorbing defective states.
I showed this influence diagram before, but this influence diagram is capturing this coupling.
Okay, so many of you will probably be familiar with the standard Bellman equations which are formalized this way, where you have some reward function plus some discounted expectation of your future value.
And so the value function in a sort of standard Bellman equation says, how much reward am I going to get if I act here optimally over an infinite horizon?
And so the reward function is often thought to be a task.
It has that sort of semantics in RL land.
And then the optimal policy is just going to return the action that corresponds to the best action that maximizes your value, your long run sum of rewards that you're going to get.
So this is a recursive equation, but my thesis is that we need to rethink the sort of model based Bellman formalizations in order to compute these nice factorizations that move us around high dimensional space like we've been talking about on the previous slides.
So we're going to formalize some new Bellman equations called operator Bellman equations.
And these are going to be non stationary Bellman equations or they're going to be functions of time.
So instead of having a value function that says what's the accumulated reward that I get?
I'm going to have a cumulative feasibility function kappa.
And this is going to represent what is the cumulative probability that I achieve a particular goal, where a goal, remember, is an action on a higher level space.
So this has a very similar form to the infinite horizon Bellman equation that I just showed.
But you'll notice that we have this availability function here for a specific goal.
So this is a single goal G that we're picking out.
So say the eaten apple goal or the drink the water goal.
We're just choosing one.
And so F is returning the availability of G from any given state and time and action.
And then, so either the agent achieves a goal now, which is what this equation is saying, or which is the plus the agent does not achieve the goal.
So one minus the probability of achieving the goal is the probability that you don't achieve the goal times the expectation that you achieve it in the future.
So it has this similar recursive structure that the infinite horizon Bellman equation has.
Okay, so then we have the policy, and this policy equation is a little different from the last one because you can imagine that you can maximize the cumulative that you achieve a goal, but you sort of do it at the last second.
You have maximized certainty that you can get to the store right before it closes.
So you know 100% that you can achieve the goal of getting an item from the store five minutes before it closes.
Well, it might be if the store is open for some period of time, that essentially you might want to get it as soon as possible.
So what this equation is saying is that we're going to pick the action which maximizes the cumulative, but from that set of equivalent actions that maximize the cumulative, which is a star.
So we're collecting the actions that maximize the cumulative and we're going to pick the one that minimizes the time.
So this is the sort of conditional optimization that says subject to the fact that we want to maximize the cumulative, we want to get there as fast as we can normally there's just with the infinite Horizon Belmont equation, there's the value function and the policy.
Here we have a third function, which is the state time feasibility function which I've been talking about.
And the state time feasibility function says given that I start at X and T, what's the probability that I achieve a goal g at a particular state final state in time XF and TF?
And so you can compute this via dynamic programming as you're computing these other functions.
And there's a relationship between the cumulative feasibility and the state time feasibility, which is that if you can sum up the individual final states and times from your state time feasibility and that is the cumulative.
So the cumulative feasibility is just summing over the individual probabilities of a given state final state time.
And the nice property is that when you use these operator bellman equations on hierarchical state spaces, such as the product space of the agent's core ontology, it has a nice decomposition property, which is that if you're just solving to go to a particular point in the world, then you can actually compute Ada separately from the high level space.
So you just solve for Ada the state time feasibility function on the low level space, but then omega can be computed independently in the high level space and they can be combined.
So this decomposition property is really nice because we never want to work in a product space, especially as we learn tons of dynamics about how the world works, we need to be able to compute representations in a factorized way which is going to help us move around in reason.
So this means that when we compute a bunch of individual state time feasibility functions for each goal I don't know why this little hat is here, but then if we have five of these and we have an aggregate feasibility function.
Then we can use this aggregate feasibility function to move around from feature to feature in the low level world and update all of our internal and higher level states.
And so this is the object from the previous slides that sort of map us around the world.
So you can also do, and I won't talk about this much, but you can also do logical tasks where instead of eating an apple, you might want to gather an apple.
So if you go obtain an apple, then there could be a bit that corresponds to having an apple.
And you flip that bit to one once you go to the tree and then you go gather water at the lake and you flip that bit and then you go to the key and you obtain that key.
And that might be a task where you have to obtain these three items, perhaps because you wanted to compose this task with something else.
You want to bring these items to another agent or whatever.
So the point is that you can use these factorizations to move around the world, especially when things in the world have a sort of limited time period in which they are available.
I talked about how we can plan in these high dimensional state spaces using this factorization.
And now we get to the question, well, why should I plan to any particular high dimensional state?
That's the intrinsic motivation question.
Given that there's an exponential number of state vectors in a product space, why is one state vector of the world in the far off distance better than another?
So that's where empowerment comes in.
Empowerment is an intrinsic motivation metric which sort of represents controllability.
So formally, empowerment is a function of a transition operator.
It's an intrinsic measure of a transition operator and you can also condition it on the state that an agent is at.
So it takes two arguments and it also has a horizon n, which we'll talk about in a second.
So it's formally defined as the Shannon channel capacity between your actuators or sequences of actions that you take and the resulting states.
So the channel capacity, so here open loop sequence of actions would just be go up right and up again, or up left and then down.
There are a lot of possible sequences of actions.
So big a here is a random variable for your sequences of actions.
And so for a horizon n, you can ask how much information can we transmit from our actuators to the resulting state at time tau.
So tau minus T is our horizon n, which is this parameter on the empowerment.
So it's just saying what's the agent's capacity to affect the future with certainty or varying amounts of certainty?
And so the channel capacity is formally defined as the maximum mutual information given distribution over these action sequences and the mutual information decomposes into the entropy of the final states minus the conditional entropy of the final state random variable given that, you know, given the actions and your starting state.
So this means there are two sort of extremes to empowerment.
If PX is a deterministic operator, so anytime I'm at state X and I apply an action, I get a deterministic output x prime, then the conditional entropy, there's going to be no uncertainty over my future state.
So the entropy is going to be zero.
There's no uncertainty.
And so that means that the conditional entropy has to cancel out.
And so empowerment is really just the maximum possible entropy given this distribution.
And this just reduces down to the log of the number of possible reachable states.
So how much can I actually reach in the world?
And so if my horizon is two, we can see that the empowerment here is just log of 13.
So there are 13 states I can get to, and I have perfect control, so I can actually realize any of those 13 states if I want.
And the other extreme is, if PX is action independent, meaning that any sort of state that I'm in, I have an action, that maybe there's the same distribution given that action, say a uniform distribution, then my conditional entropy given the actions is just going to be the entropy.
And so the empowerment has to be zero because this term is going to cancel out.
And so there might be a lot of states you can technically reach because I can select actions and I'm just going to go random places.
So Pink is all the states I could possibly reach, but I don't have any control over which state I'm going to end up in.
And so I can't influence my future in any way, even though there are a lot of possible futures.
So empowerment in that extreme is zero.
And then there's an in between zone where you take actions and there's a bias in one direction or there's different distributions for each action.
And so there might be uncertainty, but you can sort of control how much information.
You can sort of control what state that you want to end up at.
Okay, so what I'm going to define is a function valence.
And it's important to note that there's two arguments, the states, and you can include the time too, and the conditioning side.
So you have empowerment and you can define an empowerment difference.
So say you start at S and T, and then you end up at a future state in time after you execute some sequence of policies.
So Row here appended to the S and T is a sequence of policies, and S row and T row are the resulting states.
Then you can compute an empowerment difference.
And this will be our valence function.
So Q here is a function that I'll talk about in just a second.
But we can see that our jump operator that's moving around high dimensional space is defined as this factorization.
So we don't have to represent it.
Remember, that's an important part.
And so we.
Can sample multiple policies from this or chains of policies.
So if I have policy one, policy two, then I'm going to have some resulting state r double prime, x double prime, TF two.
And so Q here can just represent the output of chains of policies.
So you can imagine a tree search of chains of policies, and Q is just summarizing the final state of those branches in a tree search of policies of chains of policies.
All right, so we can use this Q.
So notice that this Q here is in the expectation over here.
So it's linking our original state time to the final state time.
So it's the empowerment after some chain of policies.
Okay, so say we have a deterministic operator, and this should be P, then valence is an empowerment difference.
We can have a simple sort of example here where we have two hikers that are considering two different plans.
And so if this tree here is like the space of two possible chains of policies, then these hikers are just executing one sort of path through this tree.
They both have the same empowerment because they're starting at the same state and they're both two away from starving.
So if we just consider an empowerment at the beginning, that's log of 13, and if we chain together two policies here, we can advance our internal state space and the agent will end up down at the lake.
And so given that it's at the lake, you'll notice that it's one state away from dying, so that there's an effective range of where it can go.
So the final empowerment is log five, because there's five reachable states and we're assuming determinism to make this easy.
So the valence here, and this should be PS here, but I have T here, but the valence is just log five minus log 13.
And that's the difference between the final and the initial.
And so that has a negative valence.
The yellow shirt hiker is clearly in a worse position that he started off at.
But we can advance the other hiker with pi g three to the lake and then pi g four to the tree and update his internal states.
And we can see that he's three away from dying.
So there's a bigger effective range.
And so there are 25 states that he can get to.
Log of 25 minus log of 13 is zero point 94, which means that he's better off than where he started.
And so clearly, the second hiker is executing a better plan.
He has more freedom to engage with other tasks in the world.
And so if we searched over this entire tree of policy chains, we could pick the best one.
And in this example, we're just going to consider two of these branches and we'd pick policy pi g three, pi g four.
All right, so there's also another interesting so in this past example, we're just sort of changing the structure we're just changing the initial state.
But since empowerment is also a function of a transition operator, and our operator Bellman equations are producing transition operators that map us from state time to state time, then the output of those Bellman equations, the operator Bellman equations, produce transition operators so we can compute their empowerment.
So that's a deep connection between Bellman equations and these intrinsic motivation metrics.
So we can do interesting things where we can say, well, if the structure of the world were different, then the feasibility functions that I could compute in different configurations of the world would be different.
So if the Honey Badger gets a key and it opens a door in the mountain pass, then it could potentially get through to the other side.
But it's important to note that this is changing the structure of the low level state space.
So PE knot is what we'll call the original transition operator, in which we can't go through the mountain pass.
And that means that if we compute state time feasibility functions on this operator, that means PE here is going into the Bellman equation, then we're going to produce state time feasibility functions from those operator Bellman equations.
That's this object here, which means that we can use it to construct j to move us around high dimensional space.
And so there's an empowerment for this j.
But then if we get the key and the key allows us to move through the door, it changes the structure of the world, then that's a different mode of dynamics.
So that means that all of this applies on the other side, where we can compute feasibility functions off of a different mode of dynamics in which we can move to the mountain pass.
And so that means we can compute things, we can compute valence by asking is this configuration of the world more conducive to the agent's core ontology that is, the agent's internal external coupling that needs to be maintained as a sort of core object.
And so we can compute valence just by changing j the structure of the agent's abstractions that it moves to perform tasks in the world.
So by computing empowerment on j, we're sort of computing it in task space.
We don't have to consider all possible states of the product space.
We can narrow it down to operators that move us around task space, that induce dynamics on key other state spaces that we care about maintaining, such as our physiological state spaces.
Okay, so here's a simple example.
Say the Honey Badger starts at the lake and has some initial empowerment just on the low level operator.
So that's P 50 there's twelve states it can reach.
But it also has a task empowerment which is actually zero because there's only one task that it can engage in if you don't include getting the key as a task.
So the circle here is saying that there's only one sort of task that can be done.
And so if the agent goes and gets the key, it's going to reduce its physiological states because it had to travel there.
And then it gets the key and it conditions a different mode of dynamics.
So there's different feasibility functions associated with that mode which I just described on the last slide.
Then the door will open and it can travel back to the lake.
And so now that it's at the lake, it can go eat food on the other side, right?
So before getting the key, if it couldn't get the key, if there were no key, then it would just starve because while it could drink water and stay hydrated, it couldn't eat from the apple tree.
But now it can cycle back and forth between the apple tree and the lake for as long as it wants.
And so it has a higher empowerment just on the low level state spaces, but it also has a higher task empowerment because there are just over a horizon of three and we're just computing, we have to choose a horizon.
So the empowerment in task space is eight because there's eight possible branches in resolving states from where it is.
And so that's very useful.
So we can compute the valence, which is 0.5 just in the low level space, but also three in the task space.
And another interesting question which is very important is to say, well, what's the value of the key?
And you can compute this too.
You can say, well, given if I just fix the state vector that I'm at, and I just alter the state phi that encodes the object of a key, if I just alter that state and switch it between having a key and not having a key, you can say, well, this key has this much value to the internal organization, the internal integrity or controllability of the agent.
So it's a sort of agent centric judgment of how much something in the world is valuable.
And so the key can be not valuable if it doesn't do anything in the world that helps the agent control its core ontology.
So this is a way in which you can sort of bootstrap value into the world.
You can use the change in an agent's internal structure, its coupling between the internal state spaces and the external world.
You can use the changes in that structure to assign value to things.
And that's very useful.
Okay, I think we're approaching an hour.
And so I'll just conclude by saying intelligent systems operate in high dimensional product spaces, often with non stationary dynamics.
This introduces a lot of problems, especially in artificial intelligence because people normally deal with structured tasks and non stationary by training recurrent neural networks and things like this, which contribute a lot to sample complexity.
And what I'm saying is know operator Bellman equations have this different form which produces transition operators, which helps you factorize your representations for moving around the world and predicting the resulting high dimensional state vector.
And these operators are composable, they compose with themselves, but they also compose with higher level structure.
So you can remap different transition structures to them.
It's very modular and these are very nice properties that you need if you don't want to recompute things and you want to have sort of modular structure come in and remap to your representations that you've already so forward sampling.
Can you still hear me, Daniel?
OK, just checking.
So forward sampling is a good way of solving problems in high dimensional state spaces without representing the product space.
We can't really solve, we can't do dynamic programming in a huge product space that's not going to work.
We can't sample low level actions, that's not going to work, the tree is too big.
But we can work at the level of sequences of policies and we can evaluate empowerment gain to justify our goal states.
And so Valence sort of unifies a lot of distinct drives.
Like there's a different sort of subfield of RL called multi objective reinforcement learning, which says we'll have a bunch of different reward functions and then we'll have value functions for each of these reward functions for different tasks and that'll make like a high dimensional value function vector space.
And usually in multi objective RL, you have to pick a policy that that does well in that value function space, but normally you have to deal with the trade offs by some weighting function.
So what I'm saying here is that because valence is just one number and it summarizes an entire sort of control architecture, that you don't have to introduce things like weighting functions or weighting coefficients to say, oh, this objective is more important now, or this objective is more important now.
So yeah, many latent drives is not necessarily multi objective, it's multidimensional, it's multi goal.
But it doesn't have to be multi objective with empowerment.
You don't have weighted combinations of empowerment.
And valence depends on the structure of the environment.
So it's not just some static property of the world or a static property of an agent.
It incorporates agent world coupling.
And I thought I'd just end with this quote from Terrence Deakin, who wrote a great book called Incomplete Nature, which I love and I read at the beginning of Grad school, which inspired me a lot.
And Terrence Deakin wrote a lot about teleology from a sort of thermodynamic perspective and it's really compelling.
And I just liked what he had to say about teleodynamics, the idea that an organism could be, or its behavior could be organized around realizing something which is sort of virtual.
And he says Teleodynamics is the dynamical realization of final causality in which a given dynamical organization exists because of the consequences of its own continuous continuance and therefore it can be described as being self generating.
Specifically, it is the emergence of a distinctive realm of orthograde dynamics that is organized around a self realizing potential, or to be somewhat enigmatic, it is a consequence organized dynamic that is its own consequence.
And I think that's relevant to what I'm doing here because I think empowerment sort of on an internal sort of structured ontology, allows an agent to say there are multiple, there's a huge space of possible futures.
But I can evaluate a state of the world that's far off in the distant future, and I can organize all of my behavior around that because I can say I can give an explanation for why it benefits my sort of core ontology.
And so therefore, it makes me capable of acting that way in the future.
It's a consequence organized dynamic that is its own consequence.
So with that, I just want to thank the Active Inference Institute, and I will take questions.
And I'm very interested in what active inference theorists think about the sort of potential for a sort of integrated view of empowerment, because I think you all have a lot of experience thinking about generative models and things of that nature.
So I'd be very curious to know what you think.
Thank you.

57:39 _Daniel:_
Excellent.
Thanks a lot.
Great presentation.
So this will be a fun discussion.
Those who are watching live, please feel free to add questions in the live chat and you can unshare your screen and we'll begin.
I guess I'll take an empowering deep breath and ask a general question, and then I have some scattered notes that I'll love to dive into.
So how did you come to this area of research?
What brought you to control theory modeling and to the empowerment perspective specifically?

58:23 _Thomas:_
Hold on, I'm just bringing up the YouTube stream so I can see comments right now.

58:30 _Daniel:_
What brought just a general question.
Mute that one.

58:34 _Thomas:_
There we go.
Yeah, I'll mute that sounds good.

58:38 _Daniel:_
Thank you.

58:40 _Thomas:_
Yeah.
So what brought me to empowerment?
I've always been interested in how could animals interact in a world in a way that's so sample efficient, especially like, knowing that animals can, like a baby horse can get up and move around and interact with the world in a sort of fluid, flexible way.
What are the sort of core representational capacities that are needed to do that?
And I didn't really see anything from the RL world, and this is before I knew about active inference.
And so that's always been in the back of my mind.
And another big influence was a guy named Nishith Srivastava who wrote an interesting paper about how you can basically have a sort of relativistic decision theory that allowed you to make judgments between different items without recourse to sort of hedonic utility theory maximization.
And so he sort of argued that if there was something like a latent acceptability function, that you could sort of remember a history of item acceptability and you could remember the context that you made decisions and that you could actually just do Bayesian inference over those memories.
And you could explain a lot of interesting things like preference reversal phenomena in decision theory where you introduce irrelevant alternatives and it changes the fundamental choice you make.
And I thought that sort of initiated a lot of thinking into, how could you bring those kinds of intuitions into sort of embodied planning?
Like, how could it be that you have an agent assign value to things without them being sort of attributed as sort of static preferences or static utilities in the world?
So I think that was also a big inspiration.

1:01:04 _Daniel:_
Awesome.
Okay.
And then one short general question.
Why the honey badger?

1:01:10 _Thomas:_
The honey badger?
My advisor showed me a YouTube video of a honey badger named Staffel, and in my paper, reward is not necessary.
The opening paragraph talks about Stauffel, and there's a link to this YouTube video.
But Stauffel is a honey badger in Australia, and he's at some sort of animal care center, and he's really good at escaping from things.
So the caretaker at this animal sanctuary constantly has to build elaborate structures to keep staffel in.
So he has this sort of pen called badger alcatraz.
And staffel would do interesting things, know, find objects to lean against the wall and climb over.
And if you took those away, staffel would pack mud into balls and stack them into, like, a little pyramid against the wall to climb up and things like that.
So, yeah, it got me thinking, what is a sort of good general intrinsic motivation function that doesn't just work on low level states, but also in a sort of more conceptual hierarchical space?
Like there might be objects or mating opportunities or anything sort of outside badger alcatraz?
What is the sort of way in which you could have an agent sort of think in a sort of abstract way in order to justify its motivations?
So I encourage the listeners to look up that video.
It's entertaining.

1:03:02 _Daniel:_
It's like this general escape impulse yes.
Extended into our open air context, where we also want to maintain the ability to move.
And for mobile creatures, that's quite a good proxy for what we might want to care about, like living.

1:03:26 _Thomas:_
Right.

1:03:28 _Daniel:_
All right.
I'll go to a question in the chat from Alex Kiefer.
Fantastic work.
Maybe a naive question, and I'm sure it's clear in the formalism, which I have only begun to look at, but the idea is that actual agent environment coupling figures in computing empowerment, right?
If so, is there a fully internal proxy that can be optimized given information available internally?

1:04:00 _Thomas:_
Is there let's see.
Is there a fully internal proxy that can be computed that can be optimized given info available internally and not part of the coupling?
Does he mean, I suppose you could compute empowerment just on the internal state space, but I don't know.
Actually, I kind of want to say no, just because you do need to use actions to move around and influence other state spaces and things like this.
I don't know how I would compute just a sort of internal intrinsic motivation function that isn't a part of some coupling to some broader system.

1:04:56 _Daniel:_
What about the desire to think freely and to move in cognitive spaces broadly?

1:05:03 _Thomas:_
Yeah, I agree.
Okay, so yeah, I definitely agree.
If you have all of your sort of physiological needs met and they aren't sort of imposing themselves on you, you're sort of freed up to do other things.
Right?
So yeah, I think that this could work generally into very abstract spaces, maybe even mathematical spaces and yeah, I think that there can be higher level dependency structures in abstract thought or mathematical thought or things like this.
I mean, you think about faulty proofs that sort of like destroy an entire field or something.
There is a sort of dependency structure in which that if you're working on mathematics that assume some proof is true and it turns out to be false, then perhaps that's disempowering from a sort of abstract perspective.
I suppose so that would be yeah, good, I was just going to say but again, all that mathematics is being done by some system that has to perform computation which takes energy and stuff like that.
So it's always sort of constrained by that, constrained by some kind of external internal coupling.

1:06:40 _Daniel:_
Many ways to go let's swerve towards active inference and then see if we can come back to some other areas.
You mentioned the generative model of active inference but you took a different approach there's, different model ontology.
So just broadly, how would you structurally contrast the coupling of the agent and the environment in active inference and in what you've proposed?
Because the representations that we see in active inference often feature the particular partitioning where a Markov blanket of a Bayesian graph is intermediating between internal and external states and then there's a mapping function between those internal and external.
States such that they can engage in an adaptive coupling, again mediated through the blanket, which is interpreted as providing incoming sensory observations and outgoing actions.
So structurally, is that compatible, incompatible or some other secret third thing with what you proposed?

1:07:51 _Thomas:_
Yeah, so I would start off by saying that I think the thing that makes my work different is that it's the structure of the latent sort of discrete state space.
It's that structure that's under consideration and I think that in active inference usually encode things like homeostatic drives.
Right?
You encode them in a generative model right, correct.

1:08:23 _Daniel:_
They are encoded as a preference over sensory observations so that the entity seeks out and selects ultimately policies that reduce or bound their surprise about those observations.
Like I expect and prefer myself to be at a homeostatic temperature.
I'm not surprised when I'm in that range and I'm going to undergo actions so that I find myself in that range.

1:08:49 _Thomas:_
Yeah, so I would say that that is a major difference because the state space in my case has this sort of self undermining quality where it's like bad starvation states.
It's not really a surprise, an expectation of receiving a particular signal or having a preference over some state of the world.
It has a sort of self undermining quality that affects your ability to control everything else.
So I think I would contrast it that way that usually the preferences or the quality of the states are sort of encoded in a generative model in the active inference setting.
And here I'm saying that there's a sort of structural coupling that's giving rise to these valence signals.

1:09:48 _Daniel:_
MMM.
You mentioned the key being obtained as inducing this change in the agent's ontology and one that was ultimately reflected by increase in empowerment, hence increase in valence.
So how does it come to understand that this shiny object unlocks that door?

1:10:15 _Thomas:_
Yeah, I think that throughout my career I will try to make steps towards actually figuring that out because a lot of this comes down to dynamics learning.
If an agent doesn't know what a key does, right, it's not going to know that it opens a door and therefore that it can move through the door and things like this.
I think there are a lot of sort of maybe like Dyna like algorithms in which you sort of alternate between learning things about dynamics or things like this.
But that is a sort of outstanding question for me, is like, yeah, how would you take a key and learn exactly how it's changing the dynamics?
But yeah, what I am saying is that given that you can do that, if you can do that, then you can really sort of make these value judgments to things in the world.
So I think that's really important too, because consider money, right?
Like, if I find a $20 bill on the ground, I'm just going to pick it up.
I don't think I'm doing a fancy computation, right, of like, oh, now my bank account is $20 greater and so therefore I have all this new capacity or things like this.
I think these sort of preferences for various objects like a key or a dollar bill or things like this can sort of be stored and maybe models with utility theory, who knows?

1:11:56 _Daniel:_
Okay, jumping around to some different questions.
I hope I'm accurate in saying you described empowerment as a Shannon information theoretic channel capacity between the actuators and the realization of the state.
We might be familiar with hearing Shannon channel capacity in the context of bandwidth of information transfer or upload and download, for example.
But this is kind of an action oriented Shannon channel capacity.
So what does it mean to get an intuition on that capacity between the actuators and the state?

1:12:38 _Thomas:_
Yeah, so the channel capacity is the maximum possible mutual information between the actions you choose and the resulting states.
So the channel capacity is sort of the maximum information that you can transmit from your actuators to possible states of the world.
It's a form of optionality that says I can affect this many sort of possible futures.
So, yeah, it's a sort of intrinsic property of an agent.
And so in a product space, this is going to be affected by a lot of different state spaces.
If they're interacting, like physiological, state spaces can kill you if they get too low.
So I think the interesting thing about this is that it sort of encourages you to think about cognition in this sort of interrogative way because you're essentially trying to figure out what you can do.
But there are a lot of, you know, different state spaces that are hindering that information transfer from your actuators to your state spaces.
So I think it's very useful because it also sort of leads to explainable AI, right?
You can sort of explain your intentions in terms of concrete state spaces which which have structure and explanation, things like that.
I think I got off topic from your question, but anything else on Shannon channel capacity that I should talk about?

1:14:29 _Daniel:_
I think, before we loop it back to potentially expected free energy.
You mentioned the AI topic, and is there any risk of an imperative that features its own empowerment in terms of an AI being able to then select action policies that might not be what anyone else expects or prefers, may not even be concordant with their own encoded explainable AI priors, but rather something that takes an unbounding approach?

1:15:10 _Thomas:_
Yeah, I do think that that is a fear.
I haven't thought that much about the alignment question, so I'd be very interested in what alignment researchers think of this perspective.
I think that there's a lot of interesting work to do on sort of multi agent empowerment, especially with these sort of abstract transition operators that work on long time scales and you can see that how sort of socialization matters and things like this.
If you're in a world with multiple agents, do you have to learn to respect all of the agents empowerment?
I mean, they can also act against you, right?
So?
Yeah.
I don't know.
I do think it's a fear to take seriously.
I don't know how I would do it though, because it's an outstanding research question to me.

1:16:12 _Daniel:_
Coming from an ant colony background, you mentioned the socialization and I immediately thought, well, let's just say that the seeds take two or three nest mates to carry home.
So in order to have one nest mate achieve the maximum empowerment, they must also engage in a pro social environment.
Because if anyone else, even if their model is smaller and less empowered, if they just decide not to play, then that individual until it figures out how to carry the seed home alone is going to actually be kind of tethered to a social fabric that helps it actually obtain those goals.
So it puts the social imperative as a screen in front of potentially any other imperative.

1:17:06 _Thomas:_
Just a thought.
Yeah, that's a great thought.

1:17:11 _Daniel:_
You mentioned the decomposition of some function.
I'll let you unpack exactly what function was being decomposed and you justified that by saying we never want to work in the product space from a computational complexity perspective or however makes sense.
What are the dangers or what are the scaling features of that product space and then what is the decomposition that facilitates a more tractable form?

1:17:48 _Thomas:_
Yeah, I'll share my screen again.
We can go back to that slide.
Thank you.
Let's see, here it is.
You can see my screen.
Yep.

1:18:32 _Daniel:_
And maybe even a brief summary of what is a Bellman equation and how did you move from the standard formalization of Bellman equations into this operator space?

1:18:45 _Thomas:_
Sure, yeah.
The standard Bellman equation, I don't know the button for one slide forward.
Okay, so the standard Bellman equation just has this recursive form and it's just the value of a state that you're at.
The optimal value of that state is the maximum value that you can get by choosing an action that rewards you and takes you to a state from which you can act in the future to get more reward.
So the Bellman equation can be solved by dynamic programming in order to maximize this function V.
So it'll result in a policy that moves you around the world in a way that accumulates a reward that you'll find in your environment.
So it has this recursive form.
You can sort of unroll it into a sequence and then the operator Bellman equation has this similar recursive form where now you'll notice that there isn't a reward function.
There's this availability function and it returns a number between zero and one.
It returns a probability.
And so that's significant because it means that you can maximize the cumulative feasibility.
And so F here is just saying this goal is available.
Either you achieve the goal now or you take an action.
You don't achieve it now, but you take an action in which you'll achieve it in the future.
So it has the same form where you can sort of think of an availability function as a reward, but it's maintaining a probabilistic form.
And that probabilistic form is important because it's what allows you to compute the state time feasibility as a transition operator, as an operator that maps you from where you are now, the state time you're at now, which is XT, to the final state time and goal that you achieve.
So under the policy, so it says if I start at XT and I follow this policy and I'm choosing actions that move me through this state space, then I'm eventually going to get to the goal and I want to know the final state in time, the probability that I achieved this at any given state in time.
And so the state time feasibility function is here.
As it's expressed is a transition operator with one action, which is the policy.
But when we aggregate it I'll bring this up.
When we aggregate it into multiple possible feasibility functions that are centered around multiple sort of objects in the world, then all of the policies associated with each one of those these are goal condition policies that are going to terminate on achieving the goal of going to one of these features and getting the apple, for instance.
Then each of those policies is an action for this transition operator.
So there's five possible policies that are going to take you around the space.
So these operator Bellman equations have this probabilistic form which retain this probabilistic structure.
And you can sort of compare this with I don't know if you're familiar, but there's this concept in RL called the successor representation which is often a hot topic in computational neuroscience.
And the successor representation is sort of talked about like it's this predictive operator.
But really what it represents is expected state Occupancies under a policy and those expected state Occupancies are weighted by the discount factor.
So a successor representation is really a sort of weighted statistic and it doesn't map from like an initial state to the state of inducing an event of achieving a goal where successor representations aren't compositional.
You can't multiply two successor representations and get another successor representation.
Well, you can multiply matrices that represent state time feasibility functions because they're mapping their probabilities of events.
So you can combine them just by multiplying matrices that represent the state time feasibility function for a given policy with another one for a different policy.
So that will retain the form of a probabilistic function and that's what makes them reusable composable, et cetera.
And I think you asked me about the decomposition and this decomposition.
Yeah, I might have glossed over this.
But the decomposition result is that if you were to compute a state time feasibility function in a product space which has lots of state vectors which are each states, then you don't want to do that because product spaces are very large and take a lot of memory to represent the operator.
So if this was not PX and this was PS, and PS was the full product space operator that moves you around this high dimensional space, well, you can't really represent that and you don't really want to.
But if you did and you computed a state time feasibility function in a product space, then you can under certain conditions and I can say what those conditions are, but under certain conditions you can decompose this into a prediction of all of the higher level state spaces computed independently.
So you evolve the hunger space separately and you evolve the thirst space separately and you evolve the temperature space separately.
You can do all of those computations locally on those spaces and you can combine them with a state time feasibility function that's only computed on the low level space.
So this hierarchical state time feasibility function is an intractable object for most reasonably sized problems, but you can implicitly form it by this product of these things individually.
And so this works when your goal for the hierarchical state time feasibility function, when you just have a single goal at arriving at a particular feature of the world like a tree, that's one of the conditions in which this decomposition holds.
So I think that answered your question about the burden of a product space.
Well, you need to overcome it by doing local computations on individual state spaces in a sort of network of interconnected state spaces that implicitly form a product space.
But you want to compute all of the representations separately in this network of state spaces so that you can sort of move around this high dimensional state space under successive policies.
And so that's what allows you to handle forward sampling in this high dimensional state space.
And that's important because I think just to recall the sort of presentation, I think it was aval A-V-E-L yes, the French.
Gwen Carlo yeah, just to echo that sort of sentiment, that if you're creating new state spaces or you're composing, you're not computing policies in a fixed world, you're composing things together, that's of course, going to expand the product space implicitly of all the state vectors of the system.
And the act of composing or bringing new information in is expanding the implicit product space that you are in.
And so from an RL standpoint, it's not so clear what a reward function on that product space is even supposed to be.
I don't think that anyone will answer that question.
But it's also not clear what a generative model should look like on that product space either.
And I think given that humans at least are so skilled at this sort of dialectical process of proposing theories and composing structure as hypotheses and interrogating what that means, I think that value comes from interrogating what it means for the structure of the world to be a certain way.
So if I learn new dynamics of the world and I want to control dynamics on some new space, it might affect other state spaces.
But from a normative perspective, it's not really clear.
Once you compose something and you're expanding the implicit product space, it's not so clear where any sort of source of normativity should come from.
But I think the sort of flexible human reasoning that we sort of know humans to engage in, I think, is in this sort of regime of composition and interrogation where you're always sort of saying, oh, if the world were this way, then I could see how this state space affects these other state spaces in a way that I didn't anticipate.
And so I think normativity in a creative way has to come from controllability.
That would be my argument.

1:29:51 _Daniel:_
There's a lot there.
So a few directions first to our colleagues in reinforcement learning.
RL, the paper is provocative in that it includes reward is not necessary.
So is reward sufficient and or what is necessary for what?

1:30:18 _Thomas:_
Yeah, it's a good question.
Is reward sufficient?
I would argue this I think that the reward enough hypothesis, which just to remind some of the viewers is the hypothesis that reward maximization can account for all sort of artificial and sort of natural intelligence.
That all of the sort of features of intelligence, the sort of capabilities, the structure, learning and stuff can all sort of arise out of some need to some process of maximizing reward.
And from my standpoint that's a frustrating statement because one, it doesn't one it doesn't really address where your preferences for specific reward functions come from.
And in the paper they will say well, we acknowledge that there could be multiple sources of reward but the process of deciding on what reward you should attend to or care about that I think deciding what signals you should care about is an important part of intelligence itself and I think that reward is enough.
Hypothesis as a hypothesis is sort of under constrained in that whatever that mechanism is to that perspective it's going to be maximizing reward under their paradigm.
And so therefore whatever shapes what that mechanism is that an agent should attend to this or an agent should stop attending to the things that's always cared about and attend to some new signal.
I think that that forces you to sort of take the position that maybe there's, like, a meta reward that directs this process because all sort of attendant processes of intelligent systems sort of underlie the process of reward.
Maximization and also the reward is enough.
Hypothesis is not being specific about it doesn't tell you what necessarily to compute.
It just says that if you try to maximize reward, you will compute the right representations.
And so I think that there's just a lot of nuts and bolts about what it takes to be able to reason in a flexible human way.
And what I'm proposing here with the operator Bellman equations is to say hey, look, there's these reward free Bellman equations that help you deal with the complexity of the world, there's no reward in them.
And you could make the case, well, maybe you could just use these operator Bellman equations to occupy states that are rewarding.
But I would argue that since the effective product space that we all live in is so vast and we reason about it in such a flexible way, I very much doubt that RL will rise to the challenge of being able to justify motivations in real time in a way that humans can.
And so to get to the question of is it sufficient, my hunch is no, I don't have a proof of reward is not sufficient.
But I also think that the information that a reward function is supposed to carry about what is good.
I don't think that is noble or computable on the timescales that we understand human intelligence to work at, to work on.
And so, yeah, in order to answer your question about what is necessary, I don't know what is necessary, but I would just sort of make the point I already made of that.
I think that we have to get to a point in which we sort of acknowledge the problems of product spaces and sort of reasoning dialectically in a product space that we can't explicitly represent.
And so I don't know what is necessary, but I can say that it's not necessary for simple self preserving agents.
And that's the claim of the paper.

1:35:12 _Daniel:_
Awesome.
All right.
In our closing segments, I'd like to take a journey to philosophy and then connect this back to potentially relationships between the models that you've presented here and active inference and maybe even walk to the edge of that cliff of the hybrid model.
So Aristotle proposed four causes material cause, what something is made of the efficient cause, which is the source of change.
The formal cause is the essence, and the final cause is the teleology, the end goal of the object.
And your presentations TeLEOS was Deacon's analysis of these different forms of teleology.
And indeed, within the model proposed empowerment was that type of self referential teleology.
When juxtaposing with active inference, and specifically the expected free energy functional, which has a lot of analogies with an operator, it's a function of other functions.
The expected free energy functional is predicated around helping the agent select policies that over expected futures, reduce their uncertainty the most about which sensations they receive.
And that's what ties active inference closely with perceptual control theory that that expected free energy is ultimately looking at a divergence between preferences over observations and incoming observations.
So that's kind of the sense side of the coin.
It's like, I want to stay in the game to be able to align observations with my preferences.
And I'm wondering if empowerment is the action side of the game.

1:37:30 _Thomas:_
I agree.

1:37:30 _Daniel:_
Saying you'll be involved with, yes, repeatedly sensing yourself to not be starving, not be dying of thirst, not be dying of cold.
You'll be in your preference vector by way of this single value, which is the empowerment.
Whereas active inference kind of comes from the other side saying, you're going to end up having a lot of squares to move around in, but first you need to make sure that you're reducing divergence between your preferences and your expected observations.

1:38:06 _Thomas:_
Mmhmm.

1:38:11 _Daniel:_
What do you think about that map?
Or where would that take these intertwined models?

1:38:19 _Thomas:_
Well, I think that there could be, like, an interface between the two concepts.
If we consider that models of how things work, like composed models of how things work, could induce particular generative models that you would want to use in a sort of active inference setting.
And that would be the sort of dual nature between the two that there's a cross talk between the proposal of some kind of generative model that would be conducive to the agent.
And if it is, then it could be a good state encoding which feeds back in on controllability or empowerment and things like this.
So, I mean, there's a lot to think about on this topic, but I guess I would just put it that way, that we still need to justify where generative models come from in new situations, for new theories of how things work and things like that.
And there could be a dual process in which the action side, the internal controllability side is dictating what kinds of generative models that should be considered.

1:39:47 _Daniel:_
Very interesting.
And the reason I brought up Aristotle's causes was because active inference as a process theory seems to be describing that efficient cause.
It's just especially with a variational free energy, which is kind of the real time version of the expected free energy.
It's like one step at a time ball going downhill.
And so variational inference is enabling incremental, unfolding optimization, again oriented around reducing that sensory preference and outcome.
It does everything but specify a final cause.
In a sense, one might say that there's a local final cause within the active inference generative model, which is like to reduce the divergence between the preferences and the observations.
But the generative model also from the action selection side, which is what makes active inference active inference.
It also needs a final cause in that self referential teleodynamic way.
And so there could be some very interesting architectures where active inference picks up, where empowerment leads, like through a needle, because it's such a small representation with valence.
And then one other kind of connection or maybe mapping between them is we've seen models of valence in active inference, such as the affective inference work, where valence was associated broadly with whether things are going better or worse than expected.
In terms of statistical uncertainty, if you're reducing your uncertainty more than you expected, things are going better than expected and vice versa.
So that is a very variance oriented valence concept where broader uncertainties are associated with inferior valence and tighter uncertainties are associated with positive valence.
And it's just interesting that that's kind of like an orthogonal valence concept from how much you can actually do that's the actionable valence.
Would you rather have a high precision around not being able to do anything, or high uncertainty about being able to do a lot or a huge amount?
And so it almost seems like when we contrast those two, the direction that dominates is, in the final analysis, the ability to have empowerment, not necessarily to just have tight control over your observations.

1:43:20 _Thomas:_
Yeah, I agree.
Lots of interesting avenues for hybrid theories.

1:43:32 _Daniel:_
Well, what a very interesting talk.
I guess one more question on the model and then we'll close, which is the time horizon is it an infinite time horizon, or what is the treatment of time?
And can time be continuous, or is time always discrete, and is it finite or infinite?

1:43:58 _Thomas:_
A so the operator Bellman equations are formalized as a finite horizon.
I suppose they could be extended to infinite horizon and infinite or continuous time.
I suppose that's possible too.
But as they're formalized now, it's discrete state, discrete time, finite horizon.
But yeah, I think that there's alternative forms that could be made.
Was there another question too, in it?
Can't remember.

1:44:38 _Daniel:_
Let us close with your time horizon.
What are your next steps with the research, and how would you imagine an ecosystem of continuation of the work?

1:44:54 _Thomas:_
Yeah, I'm interested in getting this work into computational neuroscience problem, because there's a lot of, I think, alternative models that need to be considered, especially given some of the themes that I've touched on in terms of justifying what to do in a product space, how do you represent control in a distributed system, et cetera.
And so I think that there's a lot to do there in computational neuroscience.
On the AI side, I want to put this in a world model.
I want to get good auto encoders, kind of like how I had on the first slide, where you have a high dimensional agent in a high dimensional multimodal world, how do you have nice world models and put this in something like that?
So that's the AI future direction, and I'd like to do both of them.
So I have a lot of work to do.

1:45:58 _Daniel:_
Awesome.
Well, in closing, I'm just going to read some of the more statement like comments from the live chat, just so that they're included in the Active inference journal.
So Dave Douglas wrote with regards to Deacon's consequence, galileo may have gotten in trouble less from insisting on a heliocentric universe than from insisting that purpose, value, and meaning be banished from science as connecting explanatory principles.
The Galileo tolerated remaining connecting principle, causation may have reached the limits of its explanatory power sometime between Newton's and Fourier's day, where all respectable principles of explanation must ultimately rest on invocation of either rigid rods or on elastic bands.
The Galilean program of Sola Casa attained its absurdity in Carnap's insistence that meaning, value, counterfactuals must be judged as strictly and literally as meaningless.
Have we passed the point when the Galilean program must be simply abandoned, and meaning, value, and purpose must be restored to science as irreducible explanatory principles?
Alongside Causation, I find the mysticisms of both Bohm and Heisenberg's quantum completeness and of Powelly and Jung's synchronicity to just be too fluffy to be very useful.
In a word, it has become a tradition of science as funded to insist that Causation, and Causation alone, must found our enterprise.
This is a tradition of men, not a feature of ultimate reality.
Meaning and value also have their place not reducible to cause.

1:47:51 _Thomas:_
I like it.
Yeah.

1:47:53 _Daniel:_
Excellent.
Well, Thomas, thank you again for joining.
You're always welcome back and really looking forward to seeing how this all continues.

1:48:03 _Thomas:_
Me too.
And thanks again for having me.
I've been very impressed with how much work you do for the discord, and it's a great community.
Everyone's very nice and enthusiastic, so I was excited to see it.
I just sort of randomly stumbled across it.
So I'm glad I introduced myself to the discord.
So thank you.

1:48:24 _Daniel:_
Excellent.
All right, till next time.
Thank you.

1:48:28 _Thomas:_
Great.
Thank you.
Bye.
