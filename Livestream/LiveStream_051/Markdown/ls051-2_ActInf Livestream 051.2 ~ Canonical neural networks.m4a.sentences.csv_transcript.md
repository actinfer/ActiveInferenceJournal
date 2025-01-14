
00:32 _Daniel:_

Subscribe hello and welcome everyone.
This is ActInf Livestream, number 51.28, November 9, 2022.
Welcome to the active inference institute.
We're a participatory online institute that is communicating, learning, and practicing applied active inference.
This is a recorded and an archived live stream, so please provide us feedback so we can improve our work.

01:00 All backgrounds and perspectives are welcome, and we'll be following video etiquette for live streams.
Head over to activemfronts.org to learn more about participating in different institute projects.
All right, well, we're in active states number 51.2.
We're in our third discussion on the paper.
Canonical neural networks perform active inference.

01:30 From 2022.
We had a dot zero video with some background and context and overview.
And then last week in 51.1, we had a great discussion, went over many interesting details of the paper and related topics.
So today we're going to jump in, cover some empirical details, some implications, connect some more dots, maybe look at some code.
And thanks again to Kuya for joining these discussions.

02:07 I'm Daniel, I'm a researcher in California and thought a lot over the last week about what this kind of neural network POMDP synthesis or translation really means and just want to learn more about what fundamentals or foundational aspects of these different kinds of models enable that synthesis or translation.
And then again what that means for areas where one or the other kind of model is already in use.
So thanks again for joining and I'll pass it to you if you want to say hi or give any other a second introduction.

03:02 _Takuya:_

Oh, yeah, I'm takirisomera in, lieutenant brain science institute, japan.
So I look forward to discuss another different aspects of this work.

03:23 _Daniel:_

Well, let's just remind ourselves of the fundamental parallel being made in the paper and then we'll get to these two questions about kind of the two directions that things can go.
One representation is in equation one with loss function of a neural network and the free energy on a POMDP.
And that's also seen visually in figure one, with a neural network being drawn a concordance against the variational bays of the action perception loop.
So maybe just let's begin by restating.
What is this parallel that is in equation one and figure one and how was it reached in this paper?

04:19 _Takuya:_

So basically idea here is that we derived to characterize the dynamics and plasticity of canonical neural network in terms of Bayesian inference, because arbitrary dynamics of neural network is interruptible in the sense that we don't know what is the function underlying such a dynamics and what is the coherence of the self organization or prostitution.
So once we translate that dynamics in terms of Beijing ants, we can align quantities in Beijing parents for any biological quantities.
So which enables us to lend the experiment ambiguity to the neural network dynamics and architecture.

05:24 So that's a basic idea.
And what we have done in this paper is that we consider a biological plausible cost function for this particular canonical neural network and show the equivalence between that cost function and the variation free energy and the particular partially observable process model.

05:57 _Daniel:_

Awesome.
So let's look ant the parallel between the cost function for neural networks and the variational free energy.
So one representation of that was in figure three.
So maybe could you just describe what is the structure of the variational free energy expression and what is the structure of the loss function?

06:27 _Takuya:_

Okay, so there is a clear parallel between the functional structure or those components in variation and free energy and the component in neural network cost function.

06:43 So let's say the first time in F correspond to the correspond to the expectation about hidden state s is the hidden states posterior period.
So that part basically indicates the free energy with respect to the hidden states and the second part correspond to the free energy about the decision posterior there indicates the posterior belief about agent decision or action.
And now in terms of the correspondence between the free energy and neural network function here the first time in the neural network function correspond to middle rear neuroptivity which has recurrent connection and receive sensory input from sensory layer and then project the output to the output layer.

08:02 And the second time correspond to output Dayan which receive signals from metal Dayan and send the feedback response to the environment.

08:25 _Daniel:_

So both of these expressions have the first term being more like a cognitive perceptual sensory learning term and the second term is more like a control theory action selection.
And how did you see this analogy or concordance because it looks like a zipper, like everything is totally lined up.

08:58 _Takuya:_

Well, this graph itself showed a clear correspondence.
Now we are considering a particular form of pound DP in which each element of hidden state takes either zero or one.
But there are many states so it is expressed in the form of parameterisation.
So now we consider that in terms of the s is posterior part of borders correspond to the expectation about each element of s taking one and the lower part of the border s correspond to the expectation about s taking zero.

10:00 So it is Brock vector about the expectation post Brea expectation and this s nicely correspond to the block vector shown in the bottom up this figure.

10:21 It is a vector of x and it is a vector of x and by x and here by X indicate one minus x in the element y sense which is exactly correspond to broke vector of S expectation.
This correspondence also observed in the second term here log S correspond to log x and also log A correspond to the broke matrix of W log W.
Here W hat indicates the sigmoidal function of W and its bar means sigmaidal function of W.

11:30 So actually because we now consider hidden state and boundary conversation it's likelihood mapping.
Likelihood mapping from hidden states to observation is expressed as block matrix which is exactly correspond to block matrix shown in the bottom of this figure.

12:05 Like this.
For every tab we have the exact correspondence between the upper expression and the lower expression.

12:17 So that's why we can say that this is a natural mapping from neural network correlation to computational vision formation.

12:31 It speaks to a sort of identity between those two different expressions.
So although 1 may be able to consider another mapping from neural network to Beijing infrastructure, this is a sort of just simplest mapping.

12:57 _Daniel:_

So how would it look different if it were three states categorical distribution or a continuous distribution?
What aspects would change?

13:09 _Takuya:_

Thank you for asking that.
So that's in some sense outside of this paper because only when we consider a binary hidden states, this analogy is established nicely.
Otherwise we need to consider some attention because consider that each neuron encode the probability or expectation of some value taking one.

13:54 Then the probability or expectation of taking zero can be simply computed by computing one minus neural activity.
So actually activity which is a single dimensional variable is sufficient to express the expectation.
But once we consider the three state hidden states program so this doesn't work.
So we need to consider at least two variables.
But its correlation to neural network expression is not very clear in general.

14:52 _Daniel:_

That's very interesting why it would be so strong of a concordance in a binary case but immediately unclear for other distributions.

15:10 _Takuya:_

Yeah, generative for pond DP expression we consider the Ronen photo expression vector expression which means that we normalize the value in the sense that the sum summation of all or variable to be one.
Maybe there is some neural neural subscription that achieve that normalization.
But for classic type of neural network like canonical neural network consider in this paper what is that neuronal?
Savage street is not very clear.

16:04 So that's why we selected the boundary case because it's simple and have a clear analogy.

16:14 _Daniel:_

So what does it mean for an artificial or for a biological neuron to have activity dynamics or activity context?
That justifies it being described as playing like a belief role in a Bayesian setting.

16:41 Higher firing means more belief, higher firing means lower belief.
Like what does it really mean to have a connection between activity dynamics and belief states?

16:52 _Takuya:_

I see.
So if you assign a mapping, a particular mapping, then its meaning is also determined.
In this case, we assign that neuro activity correspond to the posterior expectation about an element of hidden state taking one.

17:17 So once we define this mapping, then higher neuropetivity indicate the higher probability of taking one.

17:32 _Daniel:_

So neural activity is the probability neural activity is on the x axis and the y axis of the sigmoid function is the probability of taking one.

17:47 _Takuya:_

Well, neural activity encodes the expectation.
So activity is sigmoidal function of something itself.

18:08 This is because once we see a fixed point of neuroptivity equation which is derived from this cost function.
It has a form of sigmaidal function.
So x equals sigmaidar function of grab drive.
So this form is exactly correspond to a softmax operation softomax function of something which is seen in the solution of posterior expectation that there is.

18:46 _Daniel:_

So that's what the neural activity encodes and what is the Bayesian interpretation or the update rules on the plasticity.

18:57 _Takuya:_

Okay, that's another important point.
So in terms of posture of parameters so in the case of Beijing Coherence, we consider update about deleted parameterisation of a matrix and B matrix which is usually expressed by the small case variable.
And its meaning is that if we compute the partial derivative of partial derivative of F with respect to small a, then its solution, its fixed point solution looks like out of product of Sno which is also known as Hebbian product because it has analogy to update through depending on the neuron activity and post synaptic neuron activity.

20:16 And according to this format equivalent, we can see again such and analogy in a formal sense here if we compute the partial derivative of neural networks function with respect to W, then we can formally derive the behavior prosthesis which depends on the activity of pre on post synaptic neuroptivity.

21:08 _Daniel:_

Okay, so Hebbian plasticity often described as neurons that fired together, wired together.
Here you're discussing it in terms of a matrix operation on the POMDP side between observables and hidden states.
So there's a Hebian plasticity happening between the perceptual layer and the cognitive layer, right?
The first half of the neural network is trained according to Hebbian plasticity rules that optimize the A in terms of the perceptual and learning like relationship between hidden states and observables.
And then the second half of the neural network has a slightly different structure.

22:13 It is optimizing based upon retroactive reanalysis of consequences of action according to the fictive causality construction.

22:33 _Takuya:_

So actually in this figure b, upper layer correspond to environment and the lower part correspond to agent.
So this structure corresponds to figure eight.
This correspond to a simpler version of palm DP.
So for Bull version of palm DP, its corresponding neural network is showing.
Figure four of this paper may start.

23:12 There we go.
This is the neural network architecture.
All right, so as you said, there is a network connection from sensory layer to coordinating layer which is expressed by W here.
And the recurrent connection which correspond to state cognition matrix is expressed by K matrix which is recurrent assignment connectivity.
And as you say, the action generative through retrospective, reward or risk evolution is done by output trailer through the synaptic connectivity expressed as V in this figure.

24:11 _Daniel:_

So V is the synaptic connectivity between cognitive states in the middle layer and the action selection states in Y.
And so in that way V is exactly analogous to W.
But why and how does gamma come into play only in this second layer?
I mean, why not have gamma one in the first layer, gamma two in the second layer.

24:39 _Takuya:_

Generally speaking, it is possible to modulate plasticity in first layer using another modulator gamma.
But for complexity we focus only on neuromodulation in the output layer.
Analogy is that for example, as you said, the first layer compute more perceptual things so perception of external world and instead on the other hand middle second layer which is mapping from cognitive layer to action layer perform the optimization of its own action.

25:43 So for example, in the story atom in the brain, action selection is optimized by moderation of dopaminersic input.
So usually that sacred receives signal from canonical neuroscience and sends signal to another neuronal nucleus in meat brain.

26:21 But the point here is that neuron in storiatum encodes some decision, for example goal or no goal.
So such a decision is encoded.
So now we consider analogy between pond EP expression in the base information and neuroscience in the brain that optimize action group some sort of conversation by another factor.
Here that factor correspond to gamma.
Andy Clark gamma gamma has a variety of function, but in this paper we focus only on the moderation of activity.

27:26 So here the heavy and prostitution is not determined by only post relationship but determined by three factors relationship in the sense that the prostitute is updated by the product of gamma and pre and postsynaptic activity.
So there are three times in one prosthesis.
This is why this gamma can modulate prosticity.

28:06 _Daniel:_

So how would a glial factor look different computational?
And where in the brain have people identified Glial or other factors as relevant for learning?

28:22 _Takuya:_

Yeah, that's and interesting point.
I'm not really sure about the equation of the free correlation of neural activity or plasticity.
There are many discussion, I'm sorry, I don't know the exact form, but one possible implementation is similar to this type of neuromodulation.

28:54 So it would be possible to model some griar modulation contribution of Glapter to activity in the form of three factor learning group, which is mathematically speaking in the same as this type of neuromodulation.

29:23 _Daniel:_

Here in table two we have another set of correspondences.
It's like a sideways figure three, right?
But a little bit more like a dictionary.

29:41 Anything to add?
Or any variables that we haven't really mentioned.
What about the firing thresholds?
Because these are common parameters in a neural model, however, we don't really hear about the interpretation of these constructs within the variational bays.

30:06 _Takuya:_

POMDP yeah, there is an interesting story that's a very interesting point.

30:20 So when we first tried to make and arrowy between neural network and OMDP, one problem is the law of threshold factor because as you said, it is not observing pondip structure.
But there is another factor in pondip which is prior expectation about hidden state which is usually expressed by D matrix.
And what we consider is a relationship between D matrix and firing threshold.
And finally, what we found is that firing threshold is not equal to D matrix itself but it is a summation of D matrix and some function of synaptic strengths which is equal to a matrix B matrix in the Pom DP formation.

31:46 In other words, what we found is that h which is a firing threshold in NeuroNetwork architectures is actually and adaptive threshold which is not fixed by but h is a function of W synaptic strengths and h changes depending on W's value.

32:22 For example, if W is too large, then neuroptivity can be unstable.
So h behavior to reduce the activity to make neuro active states more stable.
So we can see and analogy of homeostatic mechanism here like this if we design h as the function of w and function of some another factor which is called perturbation time in this table, then we could make formal analogy between this h and some variable in Palm DP formulation which is shown in the right hand side of this table.

33:30 Although its value is not simple because it has three times, three different times.
So all of them contribute to make h or M.

33:48 But anyway, once we establish a mapping between h and this value then everything works.
So the cost function in different settings have a force correspondence.

34:13 _Daniel:_

What are the h and M firing thresholds.

34:18 _Takuya:_

So h correspond to middle rare, m indicate output rare threshold which are different variables.
And interestingly h correspond to posterior sorry, prior expectation about the hidden states because it correspond to cognitive layer and M correspond to prior belief about its own action because it is a bias in the action layer.

35:00 _Daniel:_

Yeah, it's very interesting that the perceptual firing threshold h only includes prior beliefs on hidden states, beliefs about how observations map to hidden states A and beliefs about how hidden states change through time B.
So that's like pure passive inference and then the foraging thresholds for M correspond to only beliefs about preferences and beliefs about actions or habits with C and E.

35:40 So there's like a complete division of labor or partitioning functionally between these structurally different parts of the neural network and structurally different and functionally different parts of the POMDP.
Yet they're integrated in unified loss functions or unified imperatives.

36:10 And so it's like there's extreme separability of perception and action on both sides of the figure one divide but also they're integrated, but they're separate and that's what kind of grants it the best of both worlds because if they were any more integrated you couldn't really pull them apart.
And if they were any less integrated then the imperative, the loss function or the variational free energy would be ad hoc and unprincipled.
But there's kind of a middle ground where they have a principled integration but still a distinguishment.

36:58 _Takuya:_

Right?

37:01 This is caused by network structure defined or it is because it is because the structure of Bayesian network defined in the OMDB model.
So both of them define the causal relationship between elements or quantities.
And so it's, you know, it's substrate is not important.
So it's relationship, causal relationship is crucial to to determine the Costa function or it's a fixed point in this context.
So that's why we can see the data analogy.

38:04 _Daniel:_

Well, there's a few technical points I think we can now go into and then there will be some more general points about applications and intelligence.
So, first the code availability statement.
Awesome to see that the MATLAB scripts are available and also archived on Zenoto.
So here is the GitHub repo for reverse engineering.
Do you want to give any overview descriptions of what people can expect to see in this repo?

38:41 And also what about using MATLAB?

38:50 Why did you use MATLAB?
What advantages or limitations do you see in MATLAB?

38:58 _Takuya:_

So because this is a very simple simulation, so it is so MATLAB is sufficient to encode the wall script.

39:14 We also try some visualization in the Attial here.
If you run the script, then you can see the process of an agent solving the maze task.

39:39 _Daniel:_

What did they do in the May's task here?

39:44 _Takuya:_

The aim of this agent is to reach the right hand side of this maze.
Because this is a typical example of a derived moderation task, that's why we select the maze task.
So to achieve this main task, is it required to make some plan to be able to select a good decision?
Because without planning, you may encounter the wall and cannot go further and you may fail the mace.

40:33 But with planning, it is possible to see the path to reach the right hand side of this space.

40:46 _Daniel:_

So does it know its exposition?

40:53 _Takuya:_

Yeah, it received a state from neighboring eleven times eleven cells, so which is shown in the bottom part.
Yeah, this all correct.
All most yeah, left figure see indicate the observation.
So, eleven times eleven state around the agent position.
Okay.

41:22 Now agent is on the right hand side of mace, ant the gold position and it observed our neighboring state.

41:37 _Daniel:_

Well, a few interesting things here.
It's looking off the right end.

41:43 _Takuya:_

Yeah.

41:44 _Daniel:_

And it has this kind of periodic belief in the distribution.
Why?

41:55 _Takuya:_

I think it is because when the agent is in the middle point of maze, then all neighboring state is in the maze.
So there is a path and there is war.
So this makes some periodicity because mazes may have some structure and actually have a periodic structure and only at the gold position, then righthand side becomes war.
But it is not common in the for this agent.
So because this is because this agent belief shows such a periodic patterns.

43:04 _Daniel:_

Yes, the streets are one wide and they tend to be separated by one.
So we see this periodicity.
What is the numbers in this middle bottom plot and what does the checker board represent?

43:21 _Takuya:_

Yeah, here, QS and QD correspond to posterior expectation about active states and decision.
So middle Canada indicate decision posterior and decision.

43:39 Here we characterize decision as a sequence of four step actions.
So each action corresponds to a movement to right or left or up or down.
And we consider four step sequence of that option which is expressed as D.
So it has four powerful possibility.

44:21 _Daniel:_

256.

44:23 _Takuya:_

Yeah, 256.
So this is a protein on XY coordinate because in the middle panel, middle point correspond to the current cognition of agent.
And with four step movement, agent can go one of any current position and the current brightness correspond to the expectation about the agent decision.

45:05 _Daniel:_

Well, this is very interesting.
If we just were to think about you're in a point and you can go up, down, left, right, you have four moves.

45:16 Naively it sounds like, well, it should look like a gaussian blur.
Most of those should cancel out and then it should become rare and rare monotonically.
But actually if you start in the middle you can't end up on these white squares because it's like one, two, three and then you have to leave.

45:44 _Takuya:_

Right?

45:45 _Daniel:_

So it's kind of like horses in chess or other pieces where actually their embodiment, it's very unexpected that you can't in four moves, end up next to where you began when you can be so much further.

46:06 And then we see this kind of like embodied differentiate prior with QS that embodies regularity beliefs about the width of the road and the separation of the roads.
And then there's these embodied action priors and real consequences that have to do with the structure of movement.
So what it's doing?
It's thinking about policies of length four.
There's 256 policies of length four.

46:45 There's some degeneracy because there's obviously not 256 squares here.
So while only one policy is going to take you up, down, down, other squares are reachable, like the center square is probably the mode because it can be reached at least a handful of ways.

47:11 And then at each time point it's basically saying, okay, I know where my X position is.
And given my local eleven by eleven view, I'm trying to plan to go right.

47:34 And then here through time, in the simulation here it starts at 30 something.
It quickly figures out how to get to about 40 and then it's kind of going up and down on 40.
But it can't really break out because all of these bottom four routes are closed.
It has a breakout and then very quickly it hits another plateau around 60.

48:04 _Takuya:_

Right.

48:05 _Daniel:_

Then it kind of has a very nice breakout and in just a few steps goes very far.

48:15 So what is dopamine doing?
Or how is Dopamine helping it in the plateau and then to break out of the plateau?

48:23 _Takuya:_

Yes.
So this agent learned this particular mate structure through many trials.
So before training it failed to reach the goal, but after training it achieved such a nice behavior.

48:52 So to achieve this, the rule of domain is that we design gamma function such that if the agent can move rightward with some distance during some time limit, then risk becomes small.
So like say comma equals zero, so no risk situation in that sense.
In that case, this agent updates synaptic weights through hebium prosthesis.
But if the agent failed to go lightward with some distance during a limited time frame, then gamma become rush like 0.6, which is larger than the average 0.5.

49:53 Then we design that during such action, anti Hebbian ergodicity occurred instead of heavy prostitution.

50:07 So antihibian prostitute indicates the works as the disassociation between the current state and current decisions.
Because the current decision doesn't work, it's not good decisions.
So we try to make the agent who get that particular decision rules through the moderation of heavy and prosticity done by dharma factor.
So this can be a narrow to the dopam natural conversation and heavier prosthesity.

50:52 _Daniel:_

So if the policy is resulting in the expected outcome, gamma stays at 0.5, the policy is as risky or consequential as expected.

51:04 And then the policy can either go better than expected, which facilitates learning to support that decision to be made more, or the outcome of the policy can be worse than expected, which disassociates previous conceptions to discourage that kind of behavior.

51:27 _Takuya:_

Exactly.
Crucial point is that this association with a exafferent time forage in the sense that we consider multiplication of current risk and past decisions to average over past to present Hebbian product.
This makes an association between past decision secrets and the current risk, which enables to optimize decision to minimize the future risk.
Right.

52:06 It is just a sift or time frame.

52:11 _Daniel:_

So here risk is being used in a formal sense similar to how it's used in economics, which is the associated uncertainty of outcomes with respect to a policy.
Where does Daniel come into play?
Like what if there was an adversary in the maze or something that was dangerous?
How does this kind of model accommodate or hunger or different kinds of competition?
Because right now it's basically just trying to diffuse right word with a bias.

52:53 _Takuya:_

Right?

52:54 _Daniel:_

But how do different kind of situational elements become integrated into the generative model and generative process?

53:05 _Takuya:_

Okay, any of those factors can be involved in risk factor, a single risk factor.
So you can actually design risk factor because risk factor modulate moderate generative model.
So that's why agent try to minimize risk through Beijing brain updating.

53:40 But the risk itself is in some sense outside of such a Bayesian framework.
So we can design arbitrary risk.
So it may involve some danger after any other factor.

54:03 _Daniel:_

And this simulation is a POMDP or it is a neural network.
And what scripts might we look at to understand the structure of the maze agent?

54:22 _Takuya:_

Okay, it is basically expressed using the quantity in OMDP for tractability.
But for examples, if you see the MDP MTP learning, probably okay, there is a variable in the definition of same type correspond to the type of simulation.
So if it's one or two it becomes fomodp or neural network to my understanding.

55:21 Well, in this particular examples we use, let's say maybe it's not good example that DeForest is creating the well said no exafferent in this script as well.
So maybe another, let's see.

56:10 _Daniel:_

MDP and it is initiating the Markov decision process.

56:15 _Takuya:_

Exactly.
It's just determining the initial state of the home TD simulation and Fe computer variation of free energy or risk MDP risk computer risk function.
So basically we use the neural network structure computation in this particular setup.
So when you free maze m, then in the line gain one line gain one we determined that cinematypo is two this correspond to neural network architecture.

57:14 So there is a very slight difference between home DP architecture and neural network architectures because assuming neural network architectures correspond to considering well, if you choose the palm DP architecture then we sometimes use d gamma function to compute the posterior expectation about parameters.
But in the neural network modeling the gamma function does appear but it is replaced with the logarithm of some function and asymmetry speaking active coherence between the gamma function of something and logarithm function of something is asymmetry saying.

58:40 So that's why we can transform on TP two neural network architectures.
When the number of samples is sufficiently large.

58:57 _Daniel:_

Which form do you expect performs better under small or large amounts of data?

59:07 _Takuya:_

Well, for large amount of data they books in the same manner, same cycle, same manner or small amount of examples?
I'm not truly sure, but it's correspond to assumption about the posterability distribution.
So if you assume the Richard distribution, then your resulting function form is something that use the function in terms of basic robbery which is optimal.

1:00:00 _Daniel:_

All right, let's return to the earliest questions from today.
So in your script, which people can reference, there's basically a toggle between having it in simtype one or simtype two corresponding to the POMDP and the neural network.
What about if there's a published neural network or POMDP?
How can we use this architecture to create a translation?

1:00:48 Is there any difference in this?
Kind of like translating models in the wild different than the full construction of a special script that can speak both languages?

1:01:10 _Takuya:_

Well, in terms of script there's no difference, sympathetic difference, right?
They works in the same manner.
So only a translation or variable you can see the same source code in the two exafferent ways.
So if you see that this is a neural network implication, then it is translated as a neural network or if you see that this is a Pomodp, then it's Pomodp.

1:02:03 _Daniel:_

So for some neural network being used in an industrial setting, how would we get from the neural network to a POMDP?
And where or how would that representation be valuable?

1:02:21 _Takuya:_

Right?

1:02:24 Neural network in the different architecture important point is that we consider a particular.
Form of neural network which is called canonical neural network architectures.
So only when we assume this class of neural network, then you can find the exact correspondence to a particular homo DB.
Otherwise you need to establish another equivalence between another form of neural network architecture and some sort of model.

1:03:12 This may be expressed by Pomodp, but maybe not so straightforward to be expressed as the computational bomb DP architecture.

1:03:29 _Daniel:_

So what is it about the canonical neural network architectures that facilitates its translation into the POMDP form?

1:03:39 _Takuya:_

Yeah, first of all, it assumes sigmoid inclination function.
It is nicely correspond to enthalpy time in the force DP equations POMDP formulations.
So that's why we can create a marking.

1:04:01 In other words, simply speaking, they have the same nonlinearity.
That's why this translation is very easy with another nonlinearity or neural network equation.
Then we need to find another type of entropy equation or another type of prior distribution.
It is very nontrivial.

1:04:38 _Daniel:_

How does one even go about doing that research?

1:04:50 _Takuya:_

If you want to go that direction, then I think the first step is to find the prior brief.

1:05:07 Find the prior brief and find the equivalent between a particular neural network texture and particular Beijing model.

1:05:25 _Daniel:_

This sigmoidal activation is interesting.
It corresponds to general patterns seen in psychophysics to objects that are the same weight.
You're going to have a 50% chance of saying that one is heavier.
And then initially the difference has the most returns on that decision being made accurately.
And then as it crosses some threshold where it just is beyond a noticeable difference, the decision becomes essentially probabilistic, like the firing curve becomes saturated.

1:06:15 The neuron has a very low belief about zero or very high belief about zero or one flipped at.

1:06:26 So there is a nice grounding of that kind of a sigmoidal response curve with respect to stimuli differences and it has of course tractable analytical properties, but it also just happens to be a good response summarizer.

1:06:51 _Takuya:_

Yeah, you're right.
So sigmoidal function is also known as a psychometric function.
As you said, we observe that characteristic in many ecological experiments.
And the previous work also said that even at the single neuron level, neuronal level the same behavior were observed.

1:07:19 Which means that for each neural activity we can leo absorbed similar property, which is sometimes called as neurometric function, which have the form of sigmoidal inclination function.

1:07:43 So it is nice reason to design neural network architecture using a sigmoidal function.

1:07:58 _Daniel:_

All right, let's cover a few questions in the chat from Dave and then in the end turn to some general thoughts.
Okay, this was when we were looking at figure three.
So you described these vectors or matrices.
What kind of matrix or vector did you describe?
The mass block matrix.

1:08:34 _Takuya:_

Block, matrix.

1:08:39 _Daniel:_

Block rock meaning what?

1:08:44 _Takuya:_

Okay, brock matrix or broke vector is vector.
Vector or matrix of matrix.
Imagine that.

1:09:03 _Daniel:_

Sorry, just zoom glitch.
Just repeat the last piece okay.

1:09:10 _Takuya:_

Well, broke matrix means that the element of matrix is a matrix.
So let's say two by two matrix like matrix in pointing.
So this here W one hat is a matrix, and W zero hat is another matrix.

1:09:37 And combining four matrices, we define a single block matrix.

1:09:46 _Daniel:_

All right, thank you.
So Dave then asks the hosts of machine learning Street Talk number 67 with Karl Friston.
Another podcast where Friston has spoken.
Pressed Karl Friston on.
Why is it so important that most of the values in a generative model matrix assume values of exactly zero?

1:10:17 Why is it important that generative model matrices are sparse?

1:10:23 _Takuya:_

Why the tangential matrix sparse?
I'm not really sure.
I think there is some context before that point.
I think on that particular situation, then, as you say, many elements in the matrix of gentle model should be zero, but I'm not sure if it's a general statement or not.

1:10:54 _Daniel:_

What do you think about compressed analyses on sparse matrices?

1:11:08 Is that a useful technique or direction?

1:11:15 _Takuya:_

You can use that knowledge to construct model, so you can use that knowledge to make more accuracy inference.
So in that sense, generally speaking, such assumption should be useful.
For example, as you said, it would be possible to use some sparse prior to restrict the value parameter.
Like it is in principle same as assuming some ruby norm to design the distribution, to design the prior distinctions, which is, massmarket speaking, exactly same as considering Lasso regression.

1:12:14 _Daniel:_

Yes.

1:12:17 So we've explored a little bit how from a canonical neural network to a particular form of a POMDP, gives us some semantics and interpretability around the dynamics and plasticity of the neural network.
What do we gain by taking a stated POMDP generative model and deriving an analogous neural network?

1:12:52 Do we gain access to efficient computation, new software packages, different applications?

1:13:04 _Takuya:_

Well, if one use palmdp under one's goal is to design an efficient Bay Zion model, then I think palm DP expression is sufficient.
So you don't need to consider neural network architectures, probably because designed to achieve give some sort of mathematically optimal inference and decision making, right?
So it itself is optimal scheme.
But if one need to consider link between Bayesian coherence and biological substrate, then this mapping is crucial.

1:14:17 Simply speaking, we consider that we assume that a brain perform Beijing inference, but its substrate is still unclear.
So we need to link the Beijing quantity to biological quantities.
So this mapping, this equivalence, helps us to its transformation.
So when you start from OMDB model, then this translation facilitates the process of finding its neuronal substrate.
So once you translate that to neural network quantities, then it help us facilitate the experimental implication application to real data.

1:15:16 So if its modeling is up for a particular neural network neural circuit architecture, then it should provide some prediction about the architecture or dynamics of the empirical data.
Right?
So first we start from Pasium model, which is not necessary to be equal to empirical data.
So there is some mapping, but it's mapping is not straightforward.
We may have multiple mappings, but once you translate Asia model to a particular neural network architectures then mapping or relationship between empirical data to such a particular neural network model is straightforward.

1:16:20 So it helps us to apply phase to an explanation of Mpcard data.
That's my soul.

1:16:36 _Daniel:_

Is it fair to say that neural networks have found wide recent application because they facilitate statistical learning in cases where the inference problem has not been a priori well specified, one can just have a folder of images and a list of labels and just say here's the data, run it through this architecture or this Architecture Explorer.
And so with this concordance we gain new interpretability into those settings that kind of arose from ill specified inference problems.
And then on the other hand, for problems that we already have well specified in terms of a POMDP generative model of a particular form, we gain the connection to actually implement it with empirical data and bring it into relevant ancestral settings.

1:17:56 What systems or phenomena are promising to continue research on the maze example obviously is a simple case, but are you continuing research into more advanced computational agents, robotic animal?

1:18:25 _Takuya:_

Well, one can design a more sophisticated agent which performs some difficult task based on canonical network neural network but there is some clear limitation on that direction, right?
Yeah, I should emphasize that across canonical neural network which correspond to a particular Pom DP is much smaller than general OMDP framework.
So there are some limitations, a list of limitations.
So if one's goal is designed and sophisticated Beijing to perform some task or control robot, then what direction is just forget such limitation and seek the mathematical optimality right?

1:19:38 And another direction is biascalic possibility.

1:19:41 So if one want to make some agent which is biological possible then this correspondence is crucial because it it tells us some limitation, vertical limitation through the existence or no existence of such a mapping between Pom DPN particular neural network architectures.
So yeah.
So it would be useful to consider substrate to achieve difficult task.

1:20:30 And that task would be related to large dimensional image processing.
Image recognition or sound recognition, such as multimodality can be involved or decision can be higher dimension.
In the main task, we just considered the four direction of movement, but it can be extended to higher dimensionality like arm movement, body movement, so on and so on.
So in Prince Boom it can be extended in that direction.

1:21:19 _Daniel:_

Which directions or questions are you excited about or what areas of studying the basis of biological and computational intelligence are relevant?

1:21:35 _Takuya:_

Yes.
So in terms of the importance of canonical network, as you said, virtue is a vertical probability.
So it would be nice that if we model some task which is conducted by lear animal and one already recorded some neuroptive activity then we design a task which is exactly the same as the task which is done.
By the animal and then compare the simulated agent and MP card data to discuss about the similarity or difference between the simulated agent and riyadh animal.

1:22:38 That would be very interesting dimension of research.

1:22:45 _Daniel:_

Yeah and if there could be some unexpected prediction or explanation in the computational agent that would bolster the relationship.
And then one other aspect is it would help with the reproducibility and the documentation around behavioral studies if the computational agent were preregistered.
And someone said, we've already done the statistical power analyses and we've already explored with parameter sweeps how many observations we need to make of the two armed bandit how many observations of the three armed bandit should we do?
Three mice 100 times or 100 mice three times?
Those are the total substance of designing research programs.

1:23:51 And so having a formal representation of behavioral tasks that are being studied will help us design behavior observations and experiments that aren't simply ad hoc.

1:24:08 _Takuya:_

All right, that's an interesting application.

1:24:15 This framework helps to design the experimental setup itself and what we often consider is the prediction ability of these modeling canonical neural networks to predict the steroidization or dynamics of the VR neural network in the animal during the learning process.
So impressed for it possible to predict the behavior after learning based only on data in the initial stage because once we obtain some empirical data, then we can fit that data to design a particular canonical network.
And canonical neural network makes some serialization through a minimization of cost function which is exactly the same as the Bayesian belief updating under a particular generative models.

1:25:26 So which means that its dynamics goes through the shortest path on the free energy landscape which means that we can make some quantitative prediction about the synaptic trajectory or neural activity or any kind of parameters.
So we demonstrated that using in virtual neural network and uploaded some blueprint recently.

1:26:00 So at least at the stage, at least at the level of individual network which is much simpler than VR brain, we could predict the self urbanization of individual network using this canonical network architecture.
This support the probability of free energy principle because this canonical network predict the self organization through the variation of free energy minimization and its solution, its result chaos type correlation between.

1:26:56 _Daniel:_

That'S a very interesting experiment.
So what animal were the neurons from and what was measured about these neurons?

1:27:08 _Takuya:_

Yes, so that in vitro network is obtained from blood embryo, we use cortical cells to make that individual network and task is a sort of causal coherence task which can be designed in the form of OMDB.
So imagine that we usually simulate agent that receive signals generated by OMD generative process and process some Bayesian task.
So we just replace that Beijing agent to a real in virtual neural network.

1:27:56 So we stimulate neuron with some signal which is made by some hidden sources through likelihood mapping.
And question is whether in vitro network can in for the hidden states through some expectation.
And they can, they could infer the hidden causes.

1:28:23 _Daniel:_

What does it look like functionally when the neural network has succeeded at inferring the hidden causes?

1:28:32 _Takuya:_

Yeah, the director conversation is done by their response number of response spikes to a particular pattern of sensory input.
So again, we can see a clear correspondence between neuro activity level and posterior about hidden states.
So here we see Brea book response to electrocastimary.
We see the response from ten to 13 millisecond after each estimation and we computer the number of spikes and that spikes changes their preference in the sense that some neuron learn to preferentially respond to source one but not source two.

1:29:30 So which is not a response to input itself, but it looks like a response to particular source.
So it is inference and which is evidence that neural network actually perform some sort of causal coherence in a manner consistent with variation and Beijing inference.
And then we compute another quantity in Bayesian coherence in the real bird card data, we show that firing stressful factor is consistent with the prior belief about hidden states.
And we also compute the cyanpic weight statistically through some connection strength estimation method and show that estimated synaptic strengths is consistent with something encoding posterior belief about parameters as expected by the Salary.

1:30:49 _Daniel:_

Well, we looked at table two earlier and this is almost like the next step after the theoretical concordance is all right, well, let's measure the release of a neurotransmitter or the empirical synaptic strength or the firing threshold or all these different features in different empirical systems.

1:31:17 So what experimental systems does your group work in?

1:31:30 _Takuya:_

That invitral system was made when I was a PhD student.
So that is the experiment we done in my previous route.
And now I COVID to the Rican Institute and I'm a principal investigator of Salary unit.
So now actually, we don't use any experimental setup.
Any experimental variation is down with some correlation.

1:32:09 So although I cannot say a detail about that corroboration.
But yeah, we learned some corroborating work about the implication of celery using various animals.
Yes.
So we hope we can show some interesting results following results using animal data.

1:32:38 _Daniel:_

Very interesting.
Yes, well, it speaks a lot to the stage that our field is in in certain ways where we've seen a lot of graphics that are suggestive.
This paper and the building on the previous 2020 paper made a suggestive possibility much closer to an analytically demonstrated translation and then took the next step incrementally into the in silica agent.
And so it's only natural to then explore different embodied systems as well.

1:33:39 Are there any other sections that you wanted to look at or highlight or any other topics about the paper or adjacencies or active inference that you think are interesting to go into?

1:34:01 _Takuya:_

Okay, we would like to mention about some limitation of these papers which is not directly discussed in the papers.
So for example, well, we focus on a discrete state space model.
So we avoid to assume some sabo street that encoding the covariance of the distribution.
So once you assume pole DP, then it is categorical distribution.
So it is different from assuming Gaussian distribution characterized by me and variance.

1:34:45 So the neuronal substrate of variance is still unclear and we now try to figure out that.
So this is one dimension of limitation.
And another limitation is that thanks to a simple ODP structure in this paper, we don't care about the hierarchical optimization.
But generally it is crucial to update parameters through hierarchical optimization through some back propagation like competition.
Although it is unclear whether back propagation itself occurs in the real brain, but we still have some alternative that active such optimization and its neuronal substrate still unclear and this paper does address that direction.

1:36:14 _Daniel:_

Another area I'm wondering about is like where in neural structures is the learning reflected?
Where is the function and learning reflected?
Well, sometimes it has to do with not just structural Tweaking, but the presence or absence of synapses.
So obviously this model does not expand into synaptogenesis synaptic pruning, let alone neurogenesis and neuro allostasis which we mentioned in the previous dimension.
But understanding how these larger scale structural changes which are certainly important in biological systems become reflected in artificial neural networks and then how that translates all the way back to POMDP and then whether we could go the other way what kinds of POMDP structures in their neural network realization would have structural modification.

1:37:24 Like you could imagine a POMDP that does structure learning but the neural network doesn't have structural change.
Or there's a POMDP that doesn't do structural learning but it's manifested by a neural network that does have a structural change element.
So structure is doing something very different in these two different categories of model.
And then also even within neural firing, which is different amongst different species and so on, there's different aspects of what that firing is that would have different implications for the actual biological substrate of cognition.
Like the simple connection is firing rate to posterior belief, average firing rate, no change in posterior.

1:38:23 Reduce the firing rate if the posterior should be going down.
Increase it if it should be going up.
Or maybe there are neurons that have a flipped valence but the same type of relationship.
But there's other firing patterns like spike time dependent plasticity synchronization amongst different brain regions.
There's a lot of things that don't change the rate overall.

1:38:53 That, again, from the biological systems, we know that those phenomena and mechanism are important for different cognitive processes, right?

1:39:06 So there will be many years of a fruitful relationship.

1:39:14 I'm going to bring in this picture that Alexandra had taken.
Maybe we need a third panel in figure one because these three systems moving between them is going to be the substance of the field for a long time and there's maybe other edges to build.
But understanding how artificial neural networks intermediate between the empirical measurements and manipulations that we can make of real neural systems and the interpretability and factorizability of POMDPs, it might be a bridge too far to go from the POMDP to the neuron.

1:40:19 You could always use this technique, but it would be a purely descriptive statistic type approach.

1:40:31 But it's so interesting that by intermediating through a formal connection established in figure one, I mean in equation one, but also shown here, then we can kind of extend the chain of explanation, prediction, control, design all the way on through.
And that just unlocks an incredible amount of neuroscience that hasn't been formalised mathematically and an incredible amount of generative models that have been specified for different learning settings, sometimes even by analogy to biological settings.
But the metaphor remains just a metaphor until it's possible to intermediate with this type of neural network development.

1:41:37 _Takuya:_

Yeah, that's a crucial point.

1:41:45 It is easy to imagine that Liar data or lear phenomena can be modeled using very realistic neuro model or Glia model, synaptic model, right.

1:42:03 We believe that it is possible and then model is not necessary tractable, not necessarily useful because it is too much complicated to analyze something.
So we use some reduction, usually mathematically speaking, which correspond to topological transformation to make the model simpler.
And then we need to consider the translation of that simplified neural network model because neural network model itself is not explainable, which just represents some dynamics and its functional meaning is not clear.
But thanks to the Bayesian framework, we have a very nice framework to lens the experiment ability and this translation, this correspondence helped us to link such phenomena base equation modeling and functional based equations.

1:43:20 _Daniel:_

Yeah, one paper from 2017 that was much discussed by some could a neuroscientist understand a microprocessor?

1:43:33 And this group with Jonas and Cording, they had a simulation of a microprocessor from earlier video game console, I believe.
And then using the analogy of the transistors and their connections as neural firing and structural connectivity, they were able to simulate experimental settings, input and action and then make measurements from every neuron including doing lesions and loss of functions and so on.
And it turns out that a lot of the techniques that are used to derive scientific explanation from analogous data collected from a biological system, those techniques which ostensibly should be isolating functional explanations in fact did not isolate effective explanations.

1:44:35 You could have a deletion over here that induces some statistical change all the way over here and that may or may not be a useful cue towards the function of even sub circuits.
And so I think that was a wake up call with respect to the interpretability of simply this connection between the biological and the neural network.

1:45:16 This connection alone is of limited applicability, even when the neural network model becomes so complex as to recapitulate the biological phenomena, you're never under any guarantee that you're going to recover interpretability.
You may have just created an atomic level simulation of the phenomena, but of course, a map that is the same scale as the phenomena isn't a map.
It's just a copy that has no more interpretability.

1:45:55 And it's almost like what is now extended again, as we kind of just summarize this and think about how we move forward, is that connection can now be extended into the space of interpretable causal models and the generalized Bayesian graphical computational frameworks and all the heuristics that we can then use like variational, Bayesian and all these other methods.
So it'd be interesting to look back at different data sets of in vitro and in vivo and in silico neural activation, especially if the task was of this constrained set of POMDPs and it was already amenable.
Because, as you brought up, other settings would require a little bit more theory development before we understand what POMDP family would be applicable.

1:47:08 _Takuya:_

Cool.

1:47:09 _Daniel:_

Well, do you have any final thoughts or questions?

1:47:16 _Takuya:_

Well, do you have.

1:47:23 _Daniel:_

I want to download the MATLAB scripts and generate the figures, play around with a few of these parameters.
Like, I see that you can change how far the entity can see.
And then with these models, I'm also always curious about the computational complexity.
Like if you extended the planning horizon from four to five or you dropped it down to three, what is the runtime consequences and what is the performance consequences?
And where might we be able to use single or swarms of really simple agents, maybe even making binary decisions and achieve high performance?

1:48:21 And where do we really need to move into these large combinatoric spaces in order to solve problems and the kinds of complex planning problems that we solve, whether it's planning our day or planning our week, are those more like true Deep Horizon planning problems with extensive consideration of counterfactuals and calculation of alternatives?
Or are those actually composite decisions that are made up of smaller, simpler, sub decisions that we may or may not have flexibility to restructure?

1:49:20 So that a decision, a complex chess maneuver, a sacrifice in chess or another game.
It may be possible to model that as a Deep Horizon scan or a kind of intuitive heuristic for an appropriate skilled entity.

1:49:50 _Takuya:_

For this particular Tour structure, there is a clear limitation about the horizon of the forward search because it doesn't use forward prediction.
It used post action approach.
So it's a career limitation, but still, it may have some performance ability to achieve some revenue performance.

1:50:27 _Daniel:_

That provides even another way to look at planning.
So the the two ways I was describing planning, as it's often described in the PMDP literature, is again, is it a true Deep Horizon consideration or is it just short term heuristic or nested models that are short and I think that this paper says maybe neither.

1:50:56 Maybe it's purely the fictive causality on the past that leads to the emergence of sentient and maybe even teleological planning like behavior through the ongoing reconsideration of the consequences of past action.
But it's neither a short nor a long term planning challenge.
It's actually like a memory and learning challenge.
And no planning occurs.

1:51:29 _Takuya:_

Right?

1:51:30 But indirect to planning planning element is involving C matricing.

1:51:38 _Daniel:_

Planning as a phenomena occurs and derisking through time occurs.

1:51:46 But it says something quite interesting and deep that that phenotype or function could be enacted by a system that explicitly looks a long way ahead, explicitly looks a short way ahead or moves forward and looks backwards only, which is what they sometimes say about the past and the future.
So that may be a very biological plausible form of learning and it's already intimately connected with the dynamics and the plasticity in terms of an integrated loss function.
So these are all excellent directions to keep learning on, right?

1:52:43 _Takuya:_

And I'm also interested in the barsky implication of such a short term or long term force, the prediction and planning.
And I hope to find some nice connectivity to such implementation of Bayesian mode and implementation VR brain network.

1:53:09 Cool.

1:53:10 _Daniel:_

And also I'm always curious about the invertebrate brain as an ant researcher.
And so many of the brain architectures as well as the regional architectures that people discuss are mammalian centric, which makes sense.
The mammalian cortical column and the relationship with Dopaminergic brain and the cortical regions and the spinal reflux arc, those are all important systems of interest.
Yet the micro and meso anatomy of the invertebrate nervous system is pretty distinct.

1:53:56 So our model should be able to describe neural and cognitive systems, of course across invertebrates and vertebrates.
So I look forward to also seeing like what those models of the invertebrate nervous system and cognitive behavior where you could have some type of backwards looking risk coherence of the swarm.
Who knows?

1:54:32 _Takuya:_

Well.

1:54:35 _Daniel:_

We really appreciate the time that you took for these discussions.
I think they are immensely important and we wish you the best of luck in these cognition continuum directions.

1:54:55 Okay, that's it.
Thank you.

1:54:58 _Takuya:_

Thank you very much.

1:54:59 _Daniel:_

See you next time.
Bye.
