
00:38 _Daniel:_

Key all right, hello everyone.
Welcome.
This is active inference live stream number 51.1.
We are in the second discussion of our this paper canonical neural networks perform active inference.
Welcome to the active inference institute.

00:56 We're a participatory online institute that is communicating, learning and practicing applied active inference.
You can find us on the this slide and this is recorded in an archived Livestream.
So please provide us feedback so we can improve our work.
All backgrounds and perspectives are welcome and we'll follow good video etiquette for livestreams.
Head over to activemfirms.org to learn more about the institute and how to participate in projects and learning groups.

01:26 All right, we're in Livestream number 51 one and having our first non solo discussion on this paper, canonical Neural Networks Perform Active Inference.
And really appreciative dakuya that you've joined today.
It's going to be a great discussion.
We'll begin with introductions.
I'll say hello and then please just jump in however you'd like and we can start by setting some context.

01:58 So I'm Daniel.
I'm a researcher in California, and I was interested in this paper because we've been talking a lot about active inference from a variety of different perspectives, from the more fundamental math and physics to some applications.
Philosophy embodiment all these really interesting threads.
And this paper seems to make a really clear, meaningful contribution and connection by connecting active inference entities and this approach of modeling to neural networks which are in daily use globally.
So thought it was a fascinating connection and really appreciate that we can talk about this today.

02:46 So to you and welcome.

02:54 Go for it Tokuya however you'd like to introduce and say hello.

02:58 _Takuya:_

Yeah.
Hi.
I'm Takai Somar, neuroscientist in Lieken Brain Science Institute in Japan.
I'm particularly interested in universal characterization of neural network and brain using mathematical techniques.

03:16 So this work I believe important as a link between active coherence aspect aspect of the brain and the dynamic system aspect of the neural network.
So I'm very happy to join this discussion.
Thank you for invitation.
Nice to meet you.

03:42 _Daniel:_

Nice to meet you as well.

03:46 The first thing you added, the universal characterization of neural networks.
What is the universal characterization of neural networks?
Why is it being pursued in this area of research?

04:01 _Takuya:_

So, as a narrow sense, my main aim of this paper is that so people use active inference formularization to characterize brain activity, behavior, so on and so on, but which would be different from a conventional neural network.
So there is a crossover program which is associated with conventional neural network and it is not very clear whether all characterization of computational neural network can be explained by active infrastructure and as a principle or not.

04:50 So here universal characterization means that parameterisation of every aspect of conventional neural network which is a kind of dynamical system derived as association between biological phenomena and simple mathematical formula, typically using differential equations as the broad sense.
I think universal characterization means that well, it is a characterization of brain intelligence, but it's a big picture and what the paper particular address is only one aspect of the full picture.

05:46 _Daniel:_

All right, so it'll be great to pull back to really understand what synthesis is happening.
So I'm going to ask what makes a neural network model a neural network model and what makes an active inference model an active inference model?
Is this synthesis and connection you've made true because of what?

06:14 _Takuya:_

Because basically what we showed is the mathematical equivalence between the correlation of canonical neural networks and the correlation active inference lab in the sense that we show that a stress of neural network can be characterized by a minimization.
Of some biological plausible cost function.
And we show that that cost function can be lead as variation of Bayesian coherence and particular cross of generative model in terms of well known partially observable process.

07:06 _Daniel:_

All right, shall we perhaps walk through some of the action of the paper?
It would be awesome.
Just for each of these sections, maybe the numbered and the lettered sections, what does the section aim to show and why was it there in the paper?

07:40 _Takuya:_

It's and overview.
Right, first we introduce so the main issue, main program, our interest, which is a relationship, which is that we try to make a formal ring between neural network and active infrastructure.
That's the main problem background.
And then we first formulate the equivalent mathematical equivalence in a very broad manner.
So in the least action in result, we formulate the relationship using concrete cross theorem, which is a well known statistical theorem proposed very long time ago.

08:42 And using that, we link a general form of neural network with a general form of variational data coherence.
But a problem is that this characterization does not address a specific generative model which is crucial to characterize a specific model, specific neural network dynamics.
So in the following sections, we characterize the problem using Pomodb or partially observer Marco digital process and link that model with a particular cross of canonical neural network.
And then we simulated we used the simulation to corroborate that property in terms of some maze task.

09:55 _Daniel:_

All right, thank you for this.
Could we talk about the complete class theorem?
So what is the scope of the complete class theorem and why was it the relevant set of the neural networks to pursue or the right way to frame it?

10:15 _Takuya:_

Thank you for asking that.
So I like the slide you showed the last week's video.

10:25 The computer basically indicates the relationship between some crossover decision rule and Beijing inference.
Here a crucial keyword is admissibility or admissible decision rule, which is rule which is the same as good as other decision rules or at least at one point better than other decision rules.
So simply speaking, administrative indicate in some sense it is the best rule for some aspect.
And usually we characterize such a goodness using cost function loss function or risk function.
And here what we did is establish some association with this type of loss function or risk function with function of canonical neural network which is we call cost function or biological cost function for neural network.

11:48 So our assumptions is that neural network minimize cost function.
So if it achieved the minimization and it is validly achieved some sort of optimality so we can say it is admissible with respect to that cost function.
So the beauty of complete cross serum is that if we find some admissible decision then automatically we can say that it is based on coherence in terms of some Bayesian cost function with generative model or prior beliefs.
So this complexity theorem is crucial as abstract characterization of the relationship between conventional neural network architectures, dynamics and variational.
Beijing inference.

12:51 _Daniel:_

Right, thank you.
What does it mean when you said it was biologically plausible of a loss function?

13:02 _Takuya:_

The term is a little bit arbitrary because in this paper we Dean by prosperity in the sense that this neural network model can be derived from heuristic neural model through some approximation.

13:30 Here, biological probability suggests or means probability as a neural model or synaptic prostitution model.
And if this cost function loss function can derive such a plausible algorithm, then we can say that this cost function is vertically plausible.

13:59 _Daniel:_

So what is the distinction between those neural and synaptic components in the loss function or what equation to look at?

14:09 _Takuya:_

You mean distinction between dynamics and synaptic?

14:14 _Daniel:_

Yeah.
What is the distinctions between them and how is it represented in the equations?

14:20 _Takuya:_

Okay, basically neuroptivity equation means differential equation about variable that represent firing intensity or some sort of variables associated with the neural firing on the other.

14:44 And synaptic plastic creation means an update rule about the synaptic weight or synaptic strengths which is a connection between two neurons.
And beauty of this formulation in this paper is that we characterize both heuristic equation and synaptic process in terms of gradient descent on a same cost function, common Costa function.
So we can say that if we consider the partial derivative of some cost function with respect to neural activity, then it derives gradient descent rule about activity neuroptivity.

15:50 While if we consider partial generative of cost function L with respect to synaptic weight, then we derive a synaptic prosthesis rule.

16:10 _Daniel:_

Are those the only two aspects of a neural network or why are those the two key aspects?

16:24 _Takuya:_

I think it's a main body of the neural activity.
If we consider some inference running our action exhibit by neural network in the sense that neural activity correspond to fast dynamics, fast gradient dynamics mix and while synaptic prostitution indicates a slow dynamics that minimize risk function cost function.
But in general we can consider and aspect any variables associated with Urinator.
For example ant least what we show in the paper is any free parameter which may be associated with firing threshold or although we don't discuss in this paper it would be possible to add other variables related to neural network.

17:25 For example, here we ignored contribution of griar factor but it would be possible to add the grille factor in this correlation or any other aspect of virus Carnap network.

17:44 _Daniel:_

That's very interesting and it speaks also to a general separation of timescales, for example in different multi scale systems or in the renormalization group where it's describing some minimal multi times scale system where the faster time scale can be seen as perception like and the slower timescale can be seen as more learning like.
And then in some hierarchical model what's learning of one time scale can be perceptual for a slower time scale?
So it's a very nice generalization.

18:32 Are there any examples of decision rules that will help us think about the action components of what the neural network is doing?
Because it may be more familiar to think about digit characterization and image classification, some kind of classical tasks for neural networks.
But how does the decision rule play out in the context of neural networks?

19:04 _Takuya:_

Okay, so in this paper we basically assume a close group comprising a neural network part and environmental part.
So Neuron receives sensor input from environment and provides some feedback to the environment.

19:31 Even with the example of digit classification we can say that output correspond to classifier classification output which is kind of decision rule.
More relevant example would be for example controller agent like a robot control or any kind of controlling or decision making tasks.
For example, when we encounter some choice task we need to advertise, for example left or right or something, any kind of Dutch a decision can be associated with the adommissibility or atomic decision rule.

20:27 _Daniel:_

So what would and example of an inadmissible or admissible strategy be in the decision making task?

20:40 _Takuya:_

Admissibility usually characterized by loss function or risk function here in adommissibility indicate that there is another decision rule which is at least one point better than the forecast decision rule.

21:12 Simply speaking in Adobe Civility indicate that decision rule is not better, not good negatively.

21:27 _Daniel:_

Let's just say our decision rule is we always turn right.
Is that an example of a decision rule?
Because there might be settings where that is strictly effective and the simplest rule whereas there's other settings where that's going to be tragic.
So what does it mean to be admissible for an agent in light of different environmental contexts?

21:52 _Takuya:_

That's an interesting point.
So even with such a too much simplified rule it can be admissible under some particular situation, particular loss function.
For example, the ruler that always turns right, maybe the best under some situation right.
So the relationship of admissibility or in admissibility depends on both agent characteristic and the environmental characteristic.

22:39 _Daniel:_

What aspects of the environment?

22:46 _Takuya:_

For example, if that decision rule matches the structure architecture of environment then maybe that decision always turn right, achieves the shortest past right under some situation some environment.

23:11 _Daniel:_

How does this admissibility help us think about, like, overfitting?
And how does it help us think about the way that different practices are used for neural networks to prevent them from being overfit in practice?

23:30 _Takuya:_

Well, strictly, adomissibility is characterized with the patient risk.
So we cannot observe a hidden states of the environment, only we can observe Hae Park of the entire universe.
So the question is, an important question is what is the best choice under such a limited information?
Limited information.
So this basically complexity tell us that only the well known Beijing framework achieved the admissible decision.

24:49 Which means that in this aspect, beijing optimization give us a best choice strategy.
Otherwise we all buffet or find the suboptima evolution.
So it's a nice association, nice linkage between the decision what is a good decision about the decision, and the more established statistical coherence Beijing and influence framework.

25:31 _Daniel:_

Thank you, that's very helpful.
So we're reducing our uncertainty and risk about hidden states in the environment.
So in the special case where the entire environment is observable without error, like a chess game, then there's an equivalence between calculation of risk or loss on observables or on hidden states.
But they're not really hidden, but they are environmental states.
Whereas any amount of uncertainty in the mapping between observations and hidden states, which is usually shown as a in the partially observable Markov decision process, any amount of uncertainty about unobserved or partially observed environmental states enables you to fit your uncertainty optimally about that hidden states and fit that uncertainty simply with a gradient descent.

26:46 And by doing so, you don't overfit a model of observables, which might be the fallacy or the issue with simply doing descriptive statistics, you might get an infinitely small variance with a frequentist estimate because you have 100,000 data points.
So the variance from a descriptive statistics perspective might be very small.

27:21 I think it speaks very much to why neural networks are useful in practice from training with limited data sets, because that's an empirical conversation that they don't entirely overfit.
But also, I'm sure there's ways to construct them that are overfit.

27:41 _Takuya:_

Yeah, overfit would occur if we select some optimal prior beliefs.
For example.

27:53 Well, I'm not sure if it is overfit in the sense that you mentioned, because if we select some prior base, then the Beijing function itself changes and the neural network that try to fit to that cost function.
So cost function minimization will be achieved such a situation, but that evolution is not good for our original purpose.
That's a tricky part.
Yeah.

28:35 _Daniel:_

That is reminiscent of some discussions we've had discussing, like driving off a cliff or blowing up is also reducing free energy, like dropping off a building reduces your potential energy.

28:50 And so there are potentially decision making or strategic trajectories that do for some time horizon minimize free energy, perhaps even or maybe even guaranteed better than some longer time horizon.
Because if the short term strategies were somehow better than the long term horizon, it would be difficult to imagine because the long term horizon would be at least as good as a short term strategy.
So that speaks to the challenges of planning in action.
So how is planning addressed in Modern neural networks and how does this work help us think about that?

29:40 _Takuya:_

That's another very important aspect.

29:45 I have to say that this framework address planning aspects, but that planning is not necessarily the optimal optimal solution in the sense that what we interested in is optimization or planning under limited structure.
The structure is characterized by here birdscape prospero to a neural network.
So yes, planning occurred by an association between risk in the future and our decision in the past.
Here we model that aspects using delayed moderation of symptomatic activity mediated by some neuromodurator or neurotransmitters.

30:53 This is model as this is model as product of the risk factor and the behavior product on the neural network.

31:22 _Daniel:_

All right, I'm going to ask a great question from the chat and then we'll look at the figures a little closer.
So ML Don wrote a question stuck in my mind for a long time.
Could you please put it to rest?
Do we need to have knowledge about all states possible actions and sensory inputs for active inference?

31:50 _Takuya:_

Well, you mean if you seek the exact solution, optimized solution, then maybe more information would help you to find that.
But under some model, under some idea assumption, then the variables is not necessary to achieve the optimal evolution.
I'm not sure if I correctly answer your point.

32:35 _Daniel:_

So just to restate it.
Of course, knowing all the states possible actions and sensory inputs, it's not a bad thing.

32:45 Worst case, there's some computational complexity, trade offs, but the problem becomes fully stateable.
But I think Mldon is asking about cases where you don't know all of the state spaces or potentially even the dimensionality or the semantics of hidden states, active states, sensory inputs, and why not even and cognitive states.
So in not just partially observed but partially known state spaces, how are these addressed in neural networks and how does active inference help us think about it.

33:37 _Takuya:_

Okay, I think the function is about how can we separate those states like least active coherence external.

33:57 _Daniel:_

How can we separate, not just in principle have these states be separated, but deal with the fact that some of these states we might have good knowledge on and some states like the hidden states we might not even know.
We don't know the dimension of the cause vector in the world.

34:19 _Takuya:_

I see.

34:22 In terms of dimensionality, there is a statistical technique to estimate the dimensionality.
For example, various information criteria, information criteria based information criteria.
All of them try to inform or estimate plausible dimensionality about the environmental hidden states.
There is an analogy with those information criteria and variation free energy minimization with virtual free energy inclination we can identify the plausible model structure which in principle involved the dimension aspect.
But in terms of neural network in this paper we don't carefully consider about the dimension optimization because we first define the NABO neuron and don't change during training.

35:37 But in principle we can consider the change in the number of neuron which is associated with the, for example, neurogenesis adult neurogenesis or development during the development stage.
That would be an important extension of this direction.

36:13 _Daniel:_

That's very interesting.
Here's a remark.
Well, one note is equation one summarizes a lot of what you've been describing.
There's a parallelism or a concordance being drawn between the loss function of neural networks and the variational free energy of the parameterized model there.
So to come back to these processes that influence learning which we could think of as the neural network becoming more fit from a loss function perspective or the variational Bayesian partially observable Markov decision process entity generative model becoming better at doing what it does.

37:05 So there's the firing rate on the neural network side the synaptic plasticity at a slower time scale which we discussed a little earlier and then now there's a third time scale with the birth and death of new cells and maybe even new layers.
And that kind of multi scale temporal structuring is not intrinsic to the Bayes graph to represent multiple nested timescales in a Bayesian graph.
In the active inference literature it's more common to make a hierarchically nested model and just say that the time handling on one level is happening more rapidly with respect to clock time than deeper nested, slower models.
Whereas the neural formulation allows us to deal with multiple ongoing timescales without appealing to hierarchical nesting which is a very important feature.

38:31 _Takuya:_

Well, both direction will be possible.
So without hierarchical model motoring or with hierarchical model.
So even with hierarchical modeling the optimization of dimensionality should be possible, would be possible but in other direction.
So we can consider that a population of neural models so one has a single layer, another has two layers, three layers, four layers and consider the probability or plausibility of network architecture associated with the performance or cost function minimization under a particular environment which is in principle have the same computational architectures with the hierarchical page and model.

39:46 _Daniel:_

Very interesting.
Yes, perhaps I over generalized or speculated because I thought about how one could have a 100 time step POMDP that also performs multiscale behavior potentially extremely wastefully but at least it could in principle.
And similarly, within a neuron there could be another neural network or some other structure approximated by that.
So they almost both enable hierarchical and non hierarchical model as you described but in very different ways that lead to very different implementations.

40:44 Yeah, I think this brings us to the topic of forward and reverse engineering.
So you talked a lot about reverse engineering.
What is reverse engineering and what is forward engineering and what has been done in these areas of engineering.

41:10 _Takuya:_

Okay, I'm not an expert of divas engineering in the process, but I believe that levers here means a characterization of the blueprint of some device or machine from data observable information like activity or action behavior of some agent.
So, goal is identification of blueprint.

41:49 And the crucial here blueprint correspond to generative model.
Because once we define generative models, we can derive various energy algorithms running influence algorithm under any behavior of agent.
So, here, reverse means that we first observe some activity of agent and its mechanism is still unknown for us.
But we can estimate its mechanism using activity by identifying the most plausible gear T model which can minimize some post function or risk function when we feed the data to the model the model.
So, on the other hand, for engineering would be more mainstream way fast define model blueprint gently model then Deneve everything including Bayesian parametric functional running Paris algorithms, behavior action algorithm.

43:20 _Daniel:_

So, by reverse engineering neural networks, we're observing some already parameterized neural network and then fitting a POMDP to it.
To what extent is it possible to take a given POMDP and create a neural network that errors that inference?

43:52 _Takuya:_

Okay, in this paper or in the following paper what we consider is strategy that we first fit empirical data whether for neural response data to bioscape plaudible canonical neural network model which is similar to a computational model fitting approach where we have differential equation and data and data to the differential equation to explain the behavior with the minimum prediction.
So, now, a virtue of this framework we establish is that we can naturally transform such a neural network architecture with the very no partially observable Markov process architecture.

45:01 Because for any kind of canonical neural network, there is a cost function.
So, we derive cost function for neurotivity question which is opposite with the computational way.
We first define cost function derived algorithm and then we use the force the formal equivalents between neural network cost function and Virginia query.

45:37 So, now transform the neural network architecture to Beijing model architectures.
And once we characterize Virginia free energy, there should be some generative model that define that Virginia free energy function.

46:05 In particular, in this example, canonical neural network necessary correspond to well known across well known Attial edition process.
So, by using this procedure, we identify a plausible homedp architecture which is correspond to obsolete data.

46:49 _Daniel:_

Well, let's stay on this last point.
So, after all those transformations, first the measurements of neurons using that data to fit the neural network and then by virtue of the relationships unpacked in the paper, transforming the neural network in the left side of figure one into a particular form of the POMDP.
So first, what are the constraints on that form of the POMDP?
Is this a little corner of model space or what are the space of acceptable POMDPs?

47:38 _Takuya:_

That totally depends on what kind of neural network model you are considering.
So for example in this paper we discuss about a particular cross of Coda that in which each state takes either zero or one.
So it's very restricted compared to the general form of OMDP but we consider a factorization.
So in the sense that although each static has a Ronen of one but we consider a vector of conversation and vector of hidden state where each element correspond to Ronen single one, whole vector but as and entire state it can represent high dimension discrete state space.

48:43 And this architectures nicely correspond to neural network architectures because usually each neuron takes either zero, one or some continuous variable between zero and one.

49:04 So we use this association to characterize a particular home DP which correspond to neural networks.
And this follows a particular Memphis approximation, approximation or approximation in generative model because we associate posterior belief in this particular homo DB with the neuropathy, which means that posterior of action also chaos, a factorization architectures in the sense that we don't fully consider about the second order statistics between neurobans activity and neurons activity, which is outside of this pulmorism.

50:07 So each neurons activity correspond to posterior expectation about the particular elements of the state and we don't consider the joint posterial property of all state.

50:40 So although this is a limitation, we see this as a Beijing imprint but otherwise for examples we can consider any recurrent network architecture which correspond to state to transition matrix.

51:05 It would be possible to extend this architectures to higher card structure in the sense that it is straightforward to consider a tree structure or any kind of higher card structure by assuming that some neuron connect to other neuron but not connect to other neuron.
So this is same as considering the higher card structure in general.

51:43 _Daniel:_

That's very interesting.
It's commonly remarked in the base graphs that they represent the connections amongst random variables and there's a relationship between their computability and their sparsity.
The sparsity structure as in which variables do or do not influence each other makes the problem tractable through factorization and just kind of conceptually like if every one of 1000 variables or an unknown number of large variables if it was all by all the number of parameters to fit on that connectivity matrix would be very high.
So statistical power would be very low for any given edge.
Whereas the more and more constrained you make the connectivity of the variables, the more statistical power you have to resolve or kind of spend on fitting those edges, like in a structural equation.

52:49 But you might be losing sight of the unknown unknowns by constraining yourself to a very limited or fallacious biology of the variables.
So there's this kind of structure learning statistical inference question in the Bayes graphs then on the neural side from the biological much of neuroscience is about understanding how the firing rate, connectivity patterns and other factors, how the structure of those neural systems and their function like form and function enable adequate coherence and coherence on action.
So it's like in both of those areas or really like in neural network, artificial and neural networks and in variational bays.

53:51 The discussion is about how the structure and the finetuning work together to generate function and about some of the statistical or biological challenges of balancing different needs while also constraining the cost in terms of materials and biometabolism.
So it's a very rich intersection that is being explored here.

54:29 If these models can really be moving back and forth.

54:38 _Takuya:_

In the sense that back and forth.

54:45 _Daniel:_

Moving back and forth, like there's imprints of the model that is implementation independent or like some interlingual or some semantics or compatibility, I don't really know.
I mean, that's something we can explore is like what is it that is such that one could forward engineer and then reverse engineer and have kind of an expectation maximization between these two areas.
So, what is it that's being sought?

55:25 _Takuya:_

Yes, important point.
So, for example, a virtue of this relationship is that we can use the knowledge of to explain neuropty neurodynamics, which is crucial because people often say that capitalizing dynamics is not straightforward.

56:00 We may obtain some solution on neural net dynamics, but the meaning of that dynamics in terms of the functional aspects is very unclear.
We don't know the meaning of connectivity strengths, matrices and what is the meaning of the threshold factor, so on and so on.
Those are derived from the moderate biological phenomena, but it is not necessary to have clear linkage to function explanation.
So, exploration of function of the brain, but once we translate these dynamics into Bayesian infrastructure, then we can explain every functional aspect of the neural net dynamics architectures in terms of well established Bayesian inference under a particular crossover Beijing model, in this case palm DB model.

57:08 So now it turns out that synaptic strengths correspond to a matrix b matrix, which are very established culture meaning.

57:21 So yeah, this is useful to explain neuro and synaptic property in terms of well established statistics.

57:44 Also, for the people in active inference lab site, it would be helpful to understand the neuronounce rate about particular active coherence modeling model.
So I think it related to forward modeling, but finally to discuss with discuss about the biotcar substrate of that forward model, we need to address the neural network architectures substrate property.
So, in that case, we can transform a particular pond Beijing modeling to a neural network architectures using this relationship and then get prediction about the substrate.

58:49 So, if we have ant least Beijing model, this particular quantity in this model should be possible.

59:15 _Daniel:_

It's all good.
Can you just repeat the last like 20 seconds?

59:18 _Takuya:_

Yes.
So in the last part I mentioned about first we define the Beijing model and then can predict what is the neuronal substrate that correspond to that particular Beijing model.
So this will be useful to identify the biological quantities.

59:50 That correspond to a quantity in Beijing.

59:58 _Daniel:_

Wow.
Well, there's a lot there.
It makes me think about the differences of implementation and heuristics in the computational setting, which is often in the extreme disembodied, and the biological setting, which is in the extreme, entirely embodied.
And for a given generative model, the kinds of computational heuristics that can be applied include a whole host of different strategies, ranging from sampling to tree exploration and branching to paralyzing the data architecture and all these other kinds of disparate strategies and software packages and implementations.

1:01:04 But on the biological side, what is needed is something that's very simple but also very inscrutable, which is a given pattern of interactions must embody that correlation.

1:01:28 So that might mean that it can add three digit numbers, but it can't add two digit numbers under some constraints.
But what isn't accessible to that kind of morphological, biological, or like form and functional computing?
What's not accessible are the tree branching, the database decentralization, like they're a different set of heuristics, but they're both very useful when we're thinking about making sentience artifacts or benefiting simply from the explainability across both sides of this figure.

1:02:18 _Takuya:_

Yeah.
So now there is an important point.
So, Hornetry, it is very known to bear whether there is a corresponding vertical architecture for any given Bayesian architecture.
I believe it is impossible to design biascar architectures to correspond to arbitrary Bayesian architectures.
So only a limited aspect of Bijan model can be implemented in a vertical, plausible manner.

1:02:55 And that point is crucial as a characterization of biological brain.

1:03:09 Yeah.
Wow.

1:03:10 _Daniel:_

Well, just to kind of touch again on this forward in reverse engineering.

1:03:18 _Takuya:_

For.

1:03:18 _Daniel:_

A given POMDP, if we're willing to compose it within a certain class, which might be quite general still, but some class of POMDP as written.
On the paper.
We may be able to have a neural network architectures that would be very amenable to deep learning, low energy computing, pretraining various features.
And then on the other side, for a given artificial neural network that we come across in the wild, or a model of neural dynamics that we fit using a neural network model.

1:04:08 So something in a neuroscience laboratory that model can have interpretability corresponding to the variables of a given POMDP.
And just to kind of give one more point on how that's going deeper than, for example, statistical parametric mapping SPM.
So let's just assume that the neural network we're dealing with is fit from brain data from some lucky ant right?
Now, what would be possible or prior to this line of work or without this line of work, one could fit a neural dynamics model and then do all kinds of analyses, like power analyses on the different frequency spectra and say, look at the average firing rate or the correlation coefficients of firing rate.
So fit the firing rates and the synaptic Plasticities and store all that data.

1:05:14 And then we could just pick a POMDP that we've seen in the literature without any reference to the neural network and optimize the POMDP.
And then we could say well, it turns out that when the Pomdpo is high there's increased theta power in this firing pattern.
So it's like comparing the descriptive statistics from the neural model to the descriptive summary statistics of the POMDP decision making model.
However, with this formal connection there is actually an interpretability to the unobserved neural states which are what are being inferred from the fMRI measurement, from the EEG measurements and so on.
Those underlying variables have a specific interpretability in relationship to the structure of the POMDP.

1:06:21 _Takuya:_

Right, that's also very interesting, important aspect what you said is I think more conventional strategy and it is also commonly related to model comparison aspect.
So we usually think bias Bayesian modeling and identify or select what is the best model to explain a given data.
And this robust engineering idea involves such a model comparison aspect in the sense that we try to find the model with the best experiment ambiguity which should be have the identical function right directory addresses the exact same Costa function architectures using the transformation natural transformation.

1:07:31 So it should be up to explain the neural data in the Bayesian sense.

1:07:42 _Daniel:_

Yeah, one can imagine how that would transform the way that current neuroimaging studies and technologies describe what it is about the measurement that provides information about the cognitive model.
So to give another related example, let's just say a person was wearing an EEG headset and a previous study had shown that increased alphaband activity was associated with this behavior.
That's comparing a descriptive statistic of the observations of the sensor and correlating the summarized observable to some other variable like anxiety or performance on a behavior.

1:08:47 In contrast, an unobserved variable in this setting the actual underlying neural state is being correlated to some semantic generative model component.
So it's no longer necessarily that any single frequency band would be associated more or less with a given outcome but it's actually some hidden states variability which gains the interpretability across this transformation.
Which is a subtle point but it speaks to how broadly the equivalence would reinterpret empirical neuroimaging results as well as a variety of artificial neural network experiments and diagnostics where people do lesion studies and double knockouts on artificial neural networks.

1:10:11 So anywhere where somebody with awareness sees that a neural network, artificial or biological is having summary features described and correlation to something that's more semantic in a quest for meaning may now have a different approach that involves foraging.
The model explicitly in terms of unobserved hidden states with a cost function akin to a variational free energy, minimizing risk or bounding surprise on the unobservables.
So even though the unobservables were modeled in a sense in the other conventional strategy like neural activity is a variable in fMRI experiments, it's underlying the bold signal.

1:11:17 Yet this formalism concordance is a more coherent and powerful connection.

1:11:34 _Takuya:_

I believe so.

1:11:40 Very important point to address that.
So we need to clarify about what is a program.
Consider here.
So this is a program so called metabasian problem in the sense that researchers try to infer or estimate neuro activity or brain activity which infer the external world dynamics, right.
So neuron brain info environment and the researcher info brain activity.

1:12:23 So there is a two step coherence processes.
So this sort of metabasion program is quite tricky intractable because sometimes probability, sometimes random variable becomes posterior about other aspect.
So I think there is some established approach about metabasium.
But this paper provides some alternative in the sense that we separate two program by saying that here what we infer is simply neural network model or neural network dynamics which is shown in the left hand side of this figure.

1:13:25 So we feed data to conventional neural network model which is a simple differential equation.

1:13:34 But thanks to this formal equivalence between neural network dynamics and behavior, we can transform the resulting neural network architecture or dynamics into the page and infrastina in some sense post hook manner.

1:14:00 So we nicely avoid the directory addressing the metabasium problem but obtain the same kind of solution in that sense.
Yes, with combining with brain activity recording like IEG or imaging.
Yeah, we can estimate a plausible neural network model in the left hand side and we can transform that to OMDP in the right hand side.

1:14:40 Great.

1:14:40 _Daniel:_

Awesome.
I'm going to show an image and ask a question from Dave in the chat.
So Dave made this image, it's the right side of figure one that we've just been looking at with the variational Bayesian correlation and he wrote the arc shown as impinging on the S self arc.
Is this intentional?

1:15:08 If so, it could represent tuning or modulation of the feedback of S into itself.

1:15:17 Do you have a thought on this?

1:15:20 _Takuya:_

It's attention?
Yes, I think it's related to the usual formulation of Pom DB architecture and active coherence context in the sense that our decision or policy in the usual setting modify active states transition matrix b matrix here delta is alternative of policy of agent.
So basically the director indicates stated transition matrix under a particular decision which agent made.
In that sense what the agent changes is state transition matrix not state itself directory.

1:16:22 That's why we use this exploration.

1:16:29 _Daniel:_

Awesome.
Very subtle but important point which is when we look at the classical POMDP formulation.
So here we'll look at a version shown in figure two.
I'll just bring just figure two in.

1:16:49 Could you describe what you just did about the role of the B matrix in influencing how hidden states change and how that is where our policies have impact?
And also please, how do the top and the bottom of figure two differ?

1:17:13 _Takuya:_

Okay, so in the usual formulation under active infrastructure with a palm DP structure.
So for us to consider the prior free for us and depending on the prior free for us, we compute the expected free energy and its minimization provides the policy and the policy modulate active states transition.
So now in the upper array we instead use the Pirator which is the option of the agent.
So here computational decision was made for each time step.

1:18:16 So that unlike the computational formulation, we have a sequence of generative and for each time step derita moderate active states transition matrix B.

1:18:32 So B is a matrix that transform hidden state in the previous step to the S in the current time step.
And it's moderation indicate that under a specific decision rule, for example, if this indicates our position in the battery environment with the goal decision our position moved forward, or if we choose no go decision, then it's unchanged.
So such a conversation of state transition was made by choosing EBITDA and the lower part correspond to Beijing influence made by Beijing agent.
So basically there is a symmetry between apart part and lower part because we assume that this Beijing agent has a plausible gentle model which nicely correspond to a given environment defined in the above in this figure.

1:20:02 But one interesting thing so asymmetry is that to model this particular canonical neural network, we don't consider an arrow or link from Derek posterior to the posterior which is in the environment data moderate S in the next step through B matrix correlation.

1:20:45 In this particular Beijing engine which formally correspond to canonical neural network, we don't consider that it is correspond to and absence of the projection from output layer to the middle layer.

1:21:19 Okay.

1:21:26 _Daniel:_

This is from the 2020 paper, but it shows the neural network architecture, the two layer architectures.
So could you restate the top and the bottom of figure two in the 22 paper and connect it to why it's important that you're studying two layer neural network models?

1:21:55 _Takuya:_

I miss you.

1:21:57 _Daniel:_

Oh yeah.
Can you just connect the asymmetry between the top and the bottom on figure two with the two layer neural network architecture?

1:22:15 You said that the asymmetry there's no direct link between.

1:22:25 _Takuya:_

Yes, this is another story.
So in the previous paper, in the previous paper there is only output rate perceptual layer because we basically consider a single layer free toward network.
So my apologies for some confusion about the network architecture in the 2020 paper.
So now upper part of this network architectures correspond to environmental generative process and only a lower part correspond to single feed forward neural network architecture.
So now this part is identical to a map from Syria in the 2022 papers.

1:23:43 _Daniel:_

Okay?
So on the top of figure two is the actual generative process.
It's the true structure of causation in the environment, which is to say that actions delta active coherence how states change through time via b delta.

1:24:08 _Takuya:_

Right.

1:24:09 _Daniel:_

The generative process through the A matrix emits observations, sequences of observations.

1:24:18 And here on the bottom with a mirrored structure is the generative model of the entity.
So what's the relevance of the arrows and the more force factor graph structure on the bottom?

1:24:40 _Takuya:_

The arrow indicates active inference.

1:24:51 It's a flow of the information in the sense that to calculate in the step two, we use the information of step two's observation and step one's posterior expectation of our hidden states.
So those two determine the s two's expectation.
Usually in the phony graph we consider retrospective arrow.
So in the sense that s three also affect the s two influence.
But this correspond to a Beijing smooth in the sense that we update every time step simultaneously to better inference.

1:25:51 However, what we consider here is a more filtering approach in the sense that for each step we compute the latest hidden states and then we don't change any other states in the past.
So that's why we don't consider the arrow from future to the past.

1:26:22 _Daniel:_

Awesome.
Yeah, just to highlight that in the Bayesian smoothing approach, it's kind of like fitting a spline because it takes the whole time series and it fits the smoothest possible line, or the line whose smoothness is on the AIC BIC frontier.
But here on the bottom with the almost pseudo code implementation provided by the 40 factor graph, which was demonstrated to be equivalent with the Bayesian graph in the 2017 work with Friston, Par and DeVries.
This architecture is reflecting a filtering scheme like a Coleman filter or just generalized Bayesian filtering through time, where estimates are being carried forward and changed time point to time point, such that the decision rules, or the updates perhaps more accurately, are defined between time points.

1:27:33 And the total time series does not have to be loaded into memory or remembered at once.

1:27:41 And then the Bayesian filtering approach has the asymmetry with a different consideration of action.
So why again is it that action is considered differentiate in the Bayesian filtering approach on the bottom of the generative models than the consideration of action in the generative process?

1:28:10 _Takuya:_

This that corresponds to lack of connection from Y to X in the figure one, or probably a figure four is helpful to that relationship.

1:28:39 This is an example network architectures comprising input Dayan, middle Brea and output Dayan.
What we consider is information flow from sensory to middle Dayan and middle area have self connection, recurrent connection and middle area project to output tray.
So there is no connection from old output Dayan to middle Dayan.
Right.
So that's why we don't consider the link from derita in the bottom layer of the figure to two s posterior.

1:29:27 So this is different from true generative process in the environment.

1:29:38 This is a kind of simplification because our purpose is identifying the plausible Bayesian model which correspond to this typo to a neural network.

1:29:56 So in other words, this neural network is and approximation about that point or use limited form of palm DP scheme.

1:30:23 _Daniel:_

Thanks.
So could you describe W VK and comma just what is the biological or functional interpretation of those variables and what brain regions or what processes or pathologies do they map to?

1:30:47 _Takuya:_

Okay, so basically WVK synaptic strengths in the form of Atreides and they represent synaptic connection in a different layer or different architecture in the sense that W means forward connectivity from sensory layer to metal area, k correspond to recurrent network recurrent connectivity and V correspond to projection from metal Brea to output Brea.
So in this paper, we don't discuss the correlation to brain anatomy in detail, but one can consider analogy.

1:31:50 For example, say x correspond to cerebral cortex activity and yellow brain in the sense that it determined the action.

1:32:14 So it is considered that in the cerebral there is signal that represent choice.
This is Journey, for example gold, this is Journal or no Gold discogn made in Serbia.

1:32:31 It's analogous to this particular architectures.
On the other hand, in the several cortex we compute the accessory information to generate some inference, prediction and planning so on, which is computed by this recurrent network.
In this particular modeling, although we don't separate brain rhythm in detail, but this recurrent network is sufficient this graph of recurrent network is sufficient to characterize any type brain architectures in the sense that we can design and higher car or mutually connected architectures using generic crossover recurrent network by weight Attial.

1:33:55 _Daniel:_

So the middle layer we can think of as like the cognitive stuff, it's the internal states when we talk about perception, cognition, action in the active scheme or even in the sandwich model of cognition, perception, cognition action.
So W is describing how those sensory inputs either in one step or composably in multiple steps become processed to these x representations of hidden external causes inferred external states.
And so these are the states that have that sigma relationship and a generalized synchrony with external states.
The sigma and the generalized synchrony are not discussed in your paper, but it connects to other work and the recurrent connections are facilitating attention or weighting of the stimuli.

1:35:08 This is the recurrent learning loop and the relationship of the A between observations and hidden state estimates.

1:35:18 And then a different kind of modulation comes into play between the hidden state estimate of the external states and the action selection.
So what is gamma corresponding to?
And why is the gamma modulation between layers two and three differing functionally from the k synaptic modulation of one and two?

1:35:47 _Takuya:_

Yeah, so K matrix basically formally correspond to B matrix in the Bayesian progression.
So which locate the information about the prediction, right?

1:36:05 Our generative, our expectation about the next state based on the previous state.
On the other hand, Laura gamma is quite different from such a competition.
Gamma basically means risk factor risk function, which is in principle we can, we can use arbitrary risk function.
This is a part of generative model we designed and the rule of risk function in generative model formulation is alternation form of generative models depending on that value of gamma which examples postdictive or retrospective modulation of and Markov decision given an outcome in the future.

1:37:15 In terms of neural network, of course it corresponds to some neuromodulation.

1:37:21 For example, Dopaminergic moderation is famous in the literature which modulates the activity and activity of various brain reason.
But we particularly focus on Dopaminergic or any kind of neuromoduration of synaptic prosthesis in the output brain, which may correspond to cerebral.
So you're in the cerebral neural activity or prosthesis moderated by domain input from it is used as the optimization rule, decision rule or sometimes attention Bijan.

1:38:29 _Daniel:_

Awesome.
Very interesting because in some previous papers and models that we've looked at, attention is dealt with as policy selection on mental states.
So internal action selection, it's an action like variable describing attention and awareness and even metacognition.
And so that connects the role of Dopamine in motor decisionmaking seen in many Dyskinesias, but also with the role of Dopamine in seemingly non motor based decision making like gambling or investing, where it doesn't seem to immediately translate to a given motor sequence.
Yet it has analogous computational characteristics and the comorbidities and the side effects of different drugs that affect the Dopamine neurophysiology are known to have carryover in terms of the rigidity or excessivity of motor and decision making aspects.

1:39:51 So it's like interesting that Dopamine has long been understood to have that parallel role in attention as cognitive action and motor action and that was established empirically through modifications of Dopamine signaling and also had been modeled analogously with computational neuroscience.
And this is providing again a slightly different interpretation of that very well studied Dopaminergic modulation of attention and policy.

1:40:41 _Takuya:_

Yes.
And in addition to that, I believe another important aspects is the modulation of scientific ergodicity by Dopamine.
Well.

1:41:15 _Daniel:_

Do you want to show something?

1:41:18 _Takuya:_

Yeah.
Can you see this paper?
It send you PDF.

1:41:37 _Daniel:_

Okay, let me see.

1:41:40 I'll get it up now.

1:41:47 All right.
The paper is a critical time window for Dopamine actions on the structural plasticity of Dendrite expines from 2014 by Yagoshita.
So what is interesting about this paper.

1:42:06 _Takuya:_

It basically explained conversation of activity by Dopamine, which is common but crucial point of this paper is that it shows that it's proved that Dopaminezic input can modulate Hebbian prostate ebin after Hebbian prosthesis is established.
So this paper showed that they had open magic input, for example, two second after or several seconds after the HEPIA ergodicity is established.

1:42:50 But such a post hoc moderation, post hoc introduction of Dopamine input is sufficient to change the past plasticity which may be associated with the post hoc evolution of our past decisions.
So by decision making, we of course changes the weight matrix through activity.
But to evaluate the goodness or badness of our decision, we need to see observe the future outcome which is propagated by, for example, Dopamine.
This paper nicely show empirically that Dopamine actually can change the past evaluation even after such a psychic level, very local level.

1:44:12 _Daniel:_

So there's a short term window, the critical time window that they're describing but there's some window, some window by which dopamine potentially unrelated to the initial heavy and plasticity event where secondary domain signaling or not secondary just after the initial fact potentially of a different valence or the same valence can synergize or cancel the plasticity formed in the moment.

1:45:03 _Takuya:_

Exactly.
And this is not limited to Dopamine, but other neuromoderators can also do this.

1:45:18 _Daniel:_

Well, on one hand, how does this change our understanding of animal neurophysiology?
And then, I guess on the other hand, how does this influence how we would design sentient artifacts.

1:45:36 _Takuya:_

When for both animals and artificial agent?

1:45:53 One important message, I believe, is that this tells us possible simple architecture to make.
Planning this is and association between past decision and future labor any risk factors which is otherwise computed by computing forward prediction by iterating some computational I believe this is a usual way to predict the future event and then select option.
But using this property, biological property which is observed in Attial experiment, we can design, we can imagine other simpler architectures to make a planning.

1:46:57 So for both animal and generative Beijing agent, it provides an alternative explanation about the association between our past decision and the future based on the optimization of our decision to maximize the reward or minimize the risk.

1:47:25 _Daniel:_

Well, one interesting note is we spoke earlier about the difference between the Bayesian smoothing all at once approach and the Bayesian filtering step by step approach.
Now, if one had infinite knowledge and computational resources, the Bayesian smoothing approach is the way to go.
Like, you don't want the decision rule for investment.
You want to look at the whole time series past, present and future and know the best moments to have made the trades.
I mean, there's no comparison.

1:47:58 You're going to do better with a Bayesian smoothing.
However, it's just implausible computationally and because it requires total memory of the past and knowledge of the future.
So that's what motivates the development of Bayesian filtering approaches which are tractable and calculable through time.
Yet with this time delayed modulation.

1:48:27 _Takuya:_

Part.

1:48:28 _Daniel:_

Of the Bayesian smoothing strength comes back into play.
It doesn't enable true anticipation of future states, but that's what the expected free energy does.
However, the delayed neuromodulation allows for reconsideration of a window of past states.
And so in that way it corresponds to like a slightly deeper filter, not just a filter of a time step of one, but a filter of like a rolling window of five or with some decay.
And you don't want that window to be too big because if the window were ten minutes, then too many contrasting stimuli would get piled together.

1:49:23 The Dopamine level would just converge to a meanfield average.
But there's some time decay or time constant on the post hoc modulation where that neuromodulatory signal is actually a parameter of interest and that's not an infinitely long or infinitely short window, but it's some niche dependent amount of time.
And that's a very interpretable and first principles interpretation of the computational role of neuromodulators in a way that is also consistent with all these other concordances we've been exploring.
So it's quite an interesting connection back I guess in our final minutes of this discussion.

1:50:27 What are you well, maybe go to the beginning at the and which I meant to ask earlier, but it's a good way that we can sort of close today and look forward, which is how did you come to this line of research specifically studying neural networks in this way with Karl Friston and your colleagues?

1:50:58 _Takuya:_

So yes, my interest was the characterization of biological network.
So my first motivation is to make biological plausible artificial intelligence, but to active that we need to know about biological brain or biological neural network.

1:51:40 In these February years, I collaborated with the doctor professor Karl Friston to study about his Calgary real as a principal after doing for us and then what my question during that period, was everything about the verdict neural network or is there any other aspects that can characterize the Barriscar neural network?
So it is non trivial.
It was non trivial.
So that's why I tried to start from characterizing the neural network first.

1:52:47 So our strategy is not considering the way of implementing any Bayesian agreement as the brain architecture, but my interest is rather characterization of a given vertical network in terms of something, some other things.

1:53:17 One possible way is of course based on inference free energy coherence.
So that's why I first start from characterizing bioscon network.
But just defining neural network architectures is insufficient, it is not trackable, it is far beyond the computational tractability as the mathematical analysis.
And we need some assumption, some trick to increase the tractability.
And one day I came up with an idea that in which we considered that both neuron activity and prosthetic flow the same cost function gradient.

1:54:25 This is very much analogy with physical system like Lagrangian correlation or Habilitonian formulation.
So usually we consider some energy landscape and design plausible trajectory as the solution of some principle of minimum action or risk action.
So we imagine that what if we apply such idea to conventional neural network or voucher neural network to characterize the dynamics in the fast principle.

1:55:23 That's a fast motivation fast step to come up with this framework.
And finally we noticed that it is not easy to connect the Newtonian dynamics with this type of neural activity study because neural activity are not necessary to be a second order differential equation, but rather it is first order and considering many things.
Then we finally used a cost function proposed in the papers which is not necessary have a formal identity with the Socalled ravalanjian in the Newtonian physics.

1:56:29 But it is rather plausible as the rule or underlying mechanism of such type of network.

1:56:51 _Daniel:_

Awesome.
Well, it has been quite an interesting one.
I really appreciate everything you've shared today.
Is there anything else you want to add at this point?
Otherwise we'll talk again.

1:57:13 _Takuya:_

I already speak a Ronen, thank you.

1:57:18 _Daniel:_

All right, talk to you later.
Bye.

1:57:22 _Takuya:_

Thank you very much for the nice discussion.
