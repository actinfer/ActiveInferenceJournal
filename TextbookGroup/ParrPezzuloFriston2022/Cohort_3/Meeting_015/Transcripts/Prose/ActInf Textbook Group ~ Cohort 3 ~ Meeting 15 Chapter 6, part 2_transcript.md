00:02 _Daniel Friedman:_
All right.
Greetings, everyone.
It's June 20, 2023.
We're in our second discussion on chapter six.
So we'll first just have any general comments or anything.
Then we'll turn to the questions table and look at what questions we didn't get to last time and just kind of revisit, maybe condense some questions or just see what we can do with what is here.
So anyone just want to make any general comments on chapter six?

00:48 _Andrew Pashea:_
I believe this is the second session on chapter six, right?

00:52 _Daniel:_
Correct.

00:53 _Andrew:_
Or maybe I lost.

00:55 _Daniel:_
Okay.
Yeah, it is.
Yeah.
There was only one onboarding needed for the welcome back here, so we started one week faster into the rhythm.
Okay.
So it looks like these were the questions I remember we left off with this one.
Let's just develop this into what was into a question, and then we'll continue on.
Okay.
Is there a common or good representation or rubric for evaluating Generative Model Generative process, which is change it to Generative Models and Generative Processes?
Anyone want to give a first thought or just some other related question?

02:26 _Andrew:_
Go on, please.
Sorry.

02:27 _Daniel:_
No, it's okay.

02:33 _Andrew:_
Yeah, I'm not sure about what's the exact criteria for evaluating generative models or generative processes, but one thing is for sure that, well, I mean, one of the main at least when evaluating generative model one of our main.
Criteria should be how closely it tracks our situation of interest and specifically how relevant it is for addressing the question we're trying to examine.
I don't think it's something clear cut or, I don't know, written in stone.
And based on the context and the situation, the Evaluation Criteria rubric should be different, I suppose, both for generative Model and generative process.

03:44 _Daniel:_
Yeah.
So again, we'll revisit this Generative Model Generative process question later, following the recent Livestream, but generative process working with generative process as the underlying process that gives rise to the observations.
This would seem to be more adequate to the extent that it can better describe the measurements.
Generative Model, similarly, is being evaluated based upon its ability to fit to the generative process as well as phenomena of interest.
So not just to fit visual data, but maybe to model something like some illusion in visual, then there's a wide range of more general statistical modeling techniques.
So first is like the ultimate grab bag, which is just how relevant is the overall modeling.
Then there are statistical evaluations of model adequacy and model selection.
Ike information criterion.
Bayesian information criterion, base factor.
Hierarchical likelihood ratio test.
If you have a parametric Model Bootstrap and non parametric statistics.
Just general modeling, and then taking that more out of the statistics into the Engineering Model Lifecycle, then that's where you can think about validation, verification, validity, quality, et cetera.
Systems engineering model lifecycle.
Any other thoughts or questions on this?
Okay.

05:46 _Speaker C:_
I'm coming from kind of an early career data scientist background here, but as far as what I find attractive about active inference and doing things as generative models is the attempt to describe or explain what's going on in the data.
And that being said, in terms of a lot of many applications of data science and machine learning, the emphasis is upon prediction.
And so are these listed statistical metrics you have here base factor, BIC, et cetera?
Are those basically like your error measurements?
Are they your, how to say, just attempt at measuring like accuracy of prediction or or is there some trade off between explainability and prediction, if that makes sense?

06:51 _Daniel:_
Yeah, just to kind of summarize these.
So when you have nested parametric models, then you can evaluate whether two models are better in terms of including or not some parametric factor and then testing for their likelihood ratios.
So this is a pretty straightforward test, but it's pretty limited to just strictly nested parametric models.
So just getting that out of the way.
In general, we're in the Bayesian setting.
And so one of the advantages of the Bayesian setting is that you can compare two different models that have totally different architectures on the same data set.
So one way that that's done is with this Ike information criterion or the Bayesian information criterion.
Both of them do something very similar, which is they reward model fit and they penalize the number of parameters.
So actually in that way it's a lot like equation 2.5.
You want to reward the fit but penalize the complexity of the model.
Base factor is kind of like the Hlrt, but it doesn't have to be ratios of nested models.
You can just compare the relative evidence in favor of one model or another.
So this is used in structure modeling and structure learning, but this is all kind of like testing amongst a portfolio of models, which ones are better?
Then how do you really get into the space of like, well, how effective is this model?
You could test on a new data set, you could do all the regular techniques like cross validation, leave one out, et cetera, or test on a new data set.
But then the very interesting question is how do you establish the efficacy of an action model?
Because it's not just a passive inference model.
So there you would need to get into like benchmarks like the OpenAI gym and other other settings where you can actually test the efficacy of an action model against some test input, rather than just a recognition model in some input.
But that gets so situational that there's not like general there's not as many general considerations there.
Another strategy is actually to even if it seems like a passive inference problem, like the MNIST digit data set, you could frame that in terms of the labeling is an action.
So sometimes you can then take what seems to be a passive inference problem and then frame it as an active inference problem.
So then you don't need to worry about these kind of like out of sample novel context action models, you can just kind of use standard benchmarks.

10:05 _Andrew:_
Also, as far as I know, probably the only serious work on benchmarking the performance of active inference models is the work of Theofi Champion and his colleagues branching time active inference, which is they have proposed several different variants of branching time active inference, each of which with increasing performance in terms of their benchmarks.
And aside from that, I'm not aware of any other work that takes this benchmarking study seriously enough to be reliable.

10:51 _Daniel:_
I guess, yeah, surely there's a lot of proprietary work in this area.
The paper discussed in live stream eight scaling active inference.
So here they used like the kind of several standard testing environments I forget the pendulum, the hopper, and then I think like the mountain car or maybe that's not this one, but they test the standard AI tests.
All right, just looking just going through the ones.
All right.
Are the transitions be independent from the emissions?
So for context, we're talking about Figure 7.3, discrete time active inference.
Are the transitions independent from the emissions?
And what does the next observation depend on?
Short answer yes, they're independent.
That's the sparsity of the Bayes graph.
So we can clarify and give it a cleaner textual answer.
But yes, the conditional independencies, which is the sparsity of the base graph which allows us to do factorized variational inference and get all of these advantages.
That's exactly what we're looking at.
So this visual graphical model is the sparsity architecture of the conditional independencies.
So yes, A and B are conditionally independent.
Conditionally independent based on what?
Hidden state.
That's how Markov blanket works.
Conditionally dependent on the blanket.
A and B are independent.
That's true of all Bayesian graphs.
So without worrying about the Markov blanket and the interface and the cybernetic agent and all of that, just any node that intervenes between two other nodes is the Markov blanket in that setting.
And then some other node, something else is blanketing it from something else.
But yes, they're conditionally independent.
What does the next observation depend on?
Well, a matrix is the emission matrix tail of two densities.
It can emit from a hidden state or it can recognize from an observation.
So any given observation is only dependent upon the hidden state at that time and the hidden state at the next time is only dependent upon the transition matrix.
The transition matrix has a slice for every action that can be taken.
Every policy makes a slice in the B tensor.
So it's like temperature in the room, hidden state, thermometer observation turn on the heater or not?
And there's some B matrix for the heater is on.
And there's some B matrix for the heater is not on.
Those are two slices in the same object.
And then policy selection means which submatrix of B, which slice of B?
Should we multiply this to get to the next time step.
And then what observation would I expect there?
Good kind of standard question.
Okay, what is the relevance of thinking about good regulator theorem for thinking about the generative model?
So, from Cybernetics, good regulator theorem originally stated every good regulator of a system must be a model of that system.
Or more accurately, every good regulator must contain a model of that system.
Here's a few quotes from the textbook.
One way to approach this.
Again, these are all kind of vague questions, but we can just see them many times.
What happens to bad regulators?
Well, information processing, sense making, decision making has a non zero informational cost land hour limit.
There's a certain amount of actual jewels it takes to write and erase a bit.
It from bit Chris Fields, everything that is in that area.
So information processing is never free.
So in a dissipative and even adversarial universe, to fail to regulate is to fail to exist.
How do we operationalize regulation in this setting?
That's going to be revisiting some non equilibrium steady state.
So if we're an observer looking at a system, in order for us to measure it as signal relative to noise, it has to be persistently remeasurable over the background.
So we have to repeatedly measure it or an organism, let's just say, can remeasure itself.
So minimizing surprise about its homeostatic temperature is being adaptive.
Now, if temperature were just flat and so you could be unsurprised at homeostasis by doing nothing, you'd get lazy agents.
But if temperature was really variable and contextual and there was kind of these nonlinear cues in the environment and all of that, then in order to reduce surprise about temperature, you'd end up coming to effectively have a model of the causal nexus that gives rise to observations.
So the structure of the generative model doesn't have to be the structure of the generative process.
However, they may come to have certain isomorphisms with each other or at least statistical regularities.
If there's actually a 24 hours cycle in temperature, then you're going to see some kind of oscillatory model in the generative model.
So there's more to say there.
But this is one good note.
Perhaps rather than good or bad regulator, the language of morality or preference, the language should be accurate and inaccurate, effective, ineffective, viable inviable skillful, unskillful.
So there's always many ways to see it.
But basically, if the generative model in the limit case, it just totally knows the causal architecture of the world, that's the easiest way to be absolutely unsurprised and to have things as you expect prefer is literally know how they're going to play out.
That's not plausible.
We use course grading and approximations and heuristics like variational inference.
So the best we can do is just iteratively optimize towards bounding surprisal.
So it's kind of like an empirical optimizable heuristic for being a good regulator without getting too bogged down into the philosophy and the exactitude the point is the ones that do well enough to live, live ones that don't do well enough, don't.
But active inference is in the lineage of cybernetics.
So it's unsurprising that good.
Regulator theorem requisite diversity.
Viable systems models.
A lot of things in the Cybernetics ontology have a natural home.
In the active ontology, they're talking about the same territory adaptive agents.
So it's not surprising that they don't invalidate each other or anything like that.

19:47 _Andrew:_
And actually, I think it's one of the reasons cybernetics has experienced kind of revitalization in recent years, especially in the past couple of years.

20:04 _Daniel:_
All right, how can organs other than the brain be making inferences?
So there's a few angles on this.
The first angle or Ali or anyone else want to give a thought?

20:23 _Andrew:_
One thing to point is this sense of kind of semi PANC computationalism that if not pan computationalism, but something that bestows inference not only to complex self organizing systems such as the brain, but even to very simple linear systems, even a system as simple as an inert rock.
So basically, it covers a spectrum from the point of view of FEP.
There isn't anything specifically unique about the brain.
In other words, the same mathematical technology can be applied both to inert rocks as well as the brain.
So in my opinion, this question should be turned on its head.
And it's not that how does inference can be seen in other systems, other simpler systems, but rather, the relevant question should be how does active inference or the notion of inference, inactive inference literature applies to all of those situations.
So one way to do that is to define a kind of sparse coupling between the environment and the agent and define variational density as the internal states of the system.
And also, obviously, the external states of the environment would be the states that needs to be tracked by those variational densities.
And in this case, there isn't anything inherently different between the way the brains or, I don't know, even sentient agents somehow undertake inference from the way that the inert rocks can partition their states into internal and external states.
But the main difference would be the way the Markov blanket in those simpler systems can act as a kind of statistical boundary that allows for non causal relationships I'm sorry, nonlinear causal relationships as opposed to linear causal relationships as opposed to nonlinear causal relationships as observed in complex agents or systems.
That's some of the main distinctions between those.

23:35 _Daniel:_
Awesome.
Yeah.
And then the classic paper that we often return to, like Ollie mentioned, the inert rock.
So this paper has the kind of visual taxonomy from simpler to more sophisticated agents that's by sometimes the papers are in white, sometimes they're in black.
Here inert systems, active, classical conservative systems, strange systems with world models of their own and all of this.
But this is a great response, which is in a pan computationalist or pan cognitive pan inferentialist world, then how does active inference apply?
One other angle is like, let's just think about the liver or the pancreas and blood sugar.
That's our system of interest.
Realism is like, is the pancreas actually doing inference on blood sugar?
And people can have a range of opinions, but in a pan cognitiveist world, the answer is yes.
Or one can kind of pull back and just say, we're going to model the pancreas as doing inference on blood sugar.
So it is no different.
It's just an interpretation of the same statistical apparatus, basically.
But there might be a setting where scientific realism is more justified.
There's multiple lines of converging evidence.
The model is comprehensive and being used to generate unique explanations and predictions versus, like, we're just going to do a linear relationship between these two things in the public health.
And so then we're not going to confuse the linear model with those with the actual causal architecture.
But there are situations that you can design or analyze where the sparsity structure of the system, which as early points to is what grants it all these interesting properties.
It is becoming known to an extent that within two or three or four sigma, it's like we're starting to talk about how it is not mistaking the map for the territory, that's the map territory fallacy, but also not doing some kind of map denialism, which is the map territory fallacy, fallacy.
And that's the paper which I'll add into by Maxwell et al.

26:36 _Andrew:_
And also, if I may add another point with regard to the distinction between realism and instrumentalism.
I believe, at least in the realism school, probably the most relevant or well situated stance to reframe active inference.
I mean, reframe its ontological status is structural realism, as argued by Majid.
Benny and others in several papers.

27:15 _Daniel:_
Nice.
Yes.
He's joined several discussions and it's great to okay, so there's some quotes from the book, but yes, basically, forget organs other than the brain, how could anything be doing inference?
And then another angle to take is just like the way that a baseball computes a parabola.
You don't need to think that it's doing it like a calculator, but that's kind of like naturalizing the computation.
That's a path of least action in a spatial space.
But also you could have a path of least action in a cognitive space.
That's Bayesian Mechanics.
And then you could have more of a realist or more of an instrumentalist angle.
Yeah, please.

28:14 _Andrew:_
Sorry.
Just one thing that somehow I mean, gets confused is some sometimes people think FEP's claim is that, okay, so if a self organizing if FEP formalism applies to a self organizing system, then it should persist through time by preserving its markup blankets intact.
But actually the claim of the FEP is the other way around.
So its main assertion is that if anything persists through time, how does FEP applies to it?
So in other sense, FEP doesn't provide any justification per se for describing the way that the system persists through time.
But we take the persistence of the system through time as the premise and then apply FEP to somehow investigate the implications of that premise through Bayesian mechanics and FEP formalism.

29:33 _Daniel:_
Yeah, without the implicit or explicit acknowledgment of the persistent existence of what you're measuring or yourself, you don't even have something to discuss.
And a lot of times when people just start to specify what they mean by the nouns and the verbs and the adjectives they use, that's a deflationary approach.
What if there's something that comes into being so fast in between moments and it's not being measured and you can't detect it?
It's like, well, then how do you know it's there?
That's not within that statistical sensing apparatus.
So you have to take the existence of the thing to be primary in modeling some thing.
And Axle Constant has a lot of work in that area.

30:35 _Andrew:_
Daniel, could you please pull up the path integral paper on page four, if I may?
Sorry.

30:51 _Daniel:_
Yep, here we nice.

30:53 _Andrew:_
Thank you.
Exactly right there.
The FTP addresses the following question.

31:00 _Daniel:_
And it's like, well, if we're talking about something that exists even in a mental geometry, that's what we want.
We want to start with if it exists, even hypothetically.
So people say, can it really describe all things?
It's like, well, all the things that exist or could exist.
We could use this modeling approach to model and talk about what properties it must possess.
But if you're willing to open the door to things that don't or can't exist, then of course the sky's the limit on what properties they do or don't possess, because they might.
It's like the non elephant animals.
Things might not exist for a huge variety of reasons.
However, things that exist, either from an external measure measurement or from self measurement, they must be acting as if they're self evidencing, reducing surprise relative to a generative model path of least action through an information geometric space.
If it isn't doing that, you're not going to observe it.
And that's where we get the particular partition and the particular partition in the particular physics.
Bayesian mechanics since Karl Friston's 2019 monograph, free Energy Principle for a Particular Physics, that was like a big inflection point in this line of research.
Whereas in the 2016 to 2018, there's a lot of qualitative work and the philosophical work applying to multiscale and nested systems and self organization amidst other empirical simulations happening continually in all of this reading works of different times, like different pieces are kind of going to be made clear or not.
What is the role of precision in nested models?
Well, here and also by way of demonstrating the transferability of active inference generative models, these three figures are discussed in live stream 28 from the original paper.
Smith et al.
Computational phenomenology.
So this is a static perceptual Bayesian model.
We have hidden state observations and we hear as a modulator, literally a neuromodulator on the A matrix Taylor two densities recognition matrix generative model.
You have the precision.
So precision is one over the temperature.
So whether you think of it as like higher temperature is lower precision or lower or vice versa, they're the same.
When your precision is low, your temperature is high, a gets blurred out.
The high temperature limit is like A becomes flattened, whereas in the low temperature limit, A becomes sharpened.
And so this is a common method in recognition modeling.
Okay?
Now they move into adding action in.
So here there's the policy.
Figure 4.3, figure 7.3, everything we've looked at.
And then they move to this nested model.
Now, in the Sandbed Smith paper, it was being mobilized in terms of basically phenomenology meditative experiences, direct sensory perception, visual perception and isocades attention, unreportable attention and then awareness at a third level, observing that.
And so you can add an uncertainty, like a precision on any variable.
You could have an uncertainty on your prior d.
You could have uncertainty on all kinds of things.
But sometimes uncertainties on specific variables become associated with certain cognitive phenomena.
In this case, they're using it to describe introspective and explainable AI systems, taking the exact same figures, exact same formalisms, just moving them into the AI setting.
So precision on A and here's that live stream 28 and the slides and everything.
Precision on A is like sensory ambiguity, precision on G.
So how precise are you on the free energy that is associated with the affect in this sophisticated affect?
Here's some discussion on Embodiment and the Alexander technique.
So, suffice to say, precision and nested modeling is basically like the general precision concept, which is basically used everywhere.
This is how we fit Bayesian models.
We have some hyper prior distribution on a parameter.
And if that prior distribution is too sharp, then it's a pathology of the prior.
It's too precise.
If it was too imprecise, you have an underfit model.
So it's like that.
And especially in nested models, precision plays a role in kind of gating.
Just in this case, it's a general question.
So you could make it do anything, basically.
But here the precision on A is like gating, let's just say the first and the third level.
So if there's no attention being paid to sensory input, don't be surprised that they don't come up to attention.
But if this gating can be like super direct and forceful, then you'll have propagation of informational causality on this network up to the higher level.
Page 113 in the textbook.
All right, the decision this is about planning as inference.
Which one of these questions was also about the decision whether to model alternative futures, counterfactual futures conditioned upon policy selection.
How would the world change if I did this or that?
Is largely tied up with the choice between discrete and continuous models because the idea of selecting between alternative futures defined by sequences of actions is more simply articulated using discrete time models.
All right, so figure 4.3.
Figure 4.3 is like the rosetta stone.
It juxtaposes the discrete time continuous discrete time generative model and the continuous time generative model.
So I'll just copy this.
In the discrete time model, you have st minus one s of t, s of t plus one.
So futures and pasts, if it's sophisticated, active inference, are being explicitly modeled.
So it's like what would happen at 07:00 if I did this?
That is explicitly addressable with a discrete time model of the correct time horizon.
So you have to explicitly say, I'm talking about an hourly model and seven depth.
And so then in branching time active inference, just like a chess algorithm, it's dealing with the branching structure because if you have a lot of affordances and you have a lot of time depth, you can imagine this is a combinatorial explosion.
In contrast, though these two generative models are shown here to emphasize their structural similarity, the continuous time generative model is actually not explicitly modeling past, present, future time steps.
Rather, it's modeling the generalized coordinates of motion x hidden state x prime rate of change, x double prime second derivative.
So in that way, it's a lot more like a Taylor series expansion.
So a Taylor series expansion, technically even a Taylor series expansion of depth one, it has an answer for every single point in the number line, but that doesn't mean it's a good one.
And so continuous time models kind of trivially have something to say about all possible time steps just by analytic continuation of the Taylor series expansion in the generalized coordinates of motion way.
However, you don't necessarily know how accurate it is for any given point.
It also doesn't have explicit counterfactuals.
So if you do some Taylor series expansion, it says yeah, at x equals three over y is five.
But then if you say, well, what if it were different?
The only way you could do that would be change the parameters of the Taylor series and recalculate it at that point.
So the model itself is not exactly doing these.
Like what would happen if I did that?
So futures are explicit in discrete time models and interpretable explicitly, whereas in continuous time models, pasts and futures are kind of trivially predicted such that it doesn't really make sense to talk about counterfactuals in the same exact way.
And these models can be hybridized and fused, which is in chapter eight.
Can we generate a code of template?
Looks like yes, but there's of course more information.
But it's an important question.
How is temporal depth specific to planning?
Does temporal depth in perception make any sense?
What is temporal depth?
So temporal depth is how many timesteps the model is considered in the discrete time case.
Does temporal depth make sense in perception?
Well, perception is always modeled as instantaneous.
However, depending on the temporal scale of a model, that perception may be instantaneous over a certain temporal thickness power.
Why is temporal depth specific to planning?
So in planning as inference, policy selection as inference, you're selecting or sampling from policies based upon their expected free energy.
In order to plan over a given time horizon and actually evaluate the playouts, you need to have a temporal depth of that amount.
Thomas Parr in his bookstream so early implementations were coming from the generalized filtering approach.
Maybe it wasn't generalized at that point, but particle filtering approach.
And then quipped these models with action.
Then people started thinking about how to get sequential dynamics.
Predator prey lock of voltera models winnerless competition neural Darwinism in these situations, there's an emergence of sequential recurrent continuous dynamics, like a limit cycle of more than two.
Then people wanted to model explicit long term planning.
And so from around 2014 or something, there was a lot more development in the discrete state space model, which enabled the well understood, partially observed Markov decision process and a lot of the characterization of planning as inference explore exploit.
Then later developments supported nested models.
Here there's a discrete time on top and a discrete time on the bottom.
But also it could be continuous time on the bottom.
Oh yes.
Then continuous state models were reintroduced as the lower levels of higher level discrete time models.
And that is kind of like the folk psychology Livestream 46 active inference does not contradict folk psychology.
Discrete time decision making up top, discrete time and discrete decisions and then more in the sensory motor.
It's more like continuous time, continuous action.
Okay, new question, figure 6.1.
All right, particular partition.
How is the mutual interaction between active states and sensory states meant in six one?
So the bi directional line here, can they mutually change their states without impacting neither internal nor external states?
Yes, they could.
You could have nodes that these nodes are in communication with each other.
In general, this image, it's more important what it doesn't show.
So there's no backwards arrow from external to active or from internal to sensory.
You can't have your thumb on the scale and the symmetry of whatever that is from the outside.
And the only other constraint is no telepathy.
No telekinesis.
The only way to receive information about external states is through sensory states.
The only way to act on costly intervene on external states is through active states.
So no thumb on the scale and the mirror, no telepathy.
No telekinesis.
That doesn't mean that for any given model, these arrows are like all important or all relative or relatively of the same importance.
So if you want to design a computer system where the sensory states comes in one computer, and this is a second computer and this is the third computer, so like there's no direct edge between sensory and active states, you can create that causal architecture.
What is it supposed.
To model nothing.
Modeling of supposed things is done in chapter six and beyond.
But in general, this is not trying to model any specific situation despite the brain in the world.
Could they circle mutually modifying their states and then eventually arrive at a state where they change the external internal states?
Yeah, maybe they have a faster timescale or something.
Or maybe they're in communication with each other and then active states, like sensory states ends up influencing internal states via active influencing it.
And so yes, it could happen.
Would that mean that we can model with this trick, any arbitrary behavior?
It's not necessarily a trick, it's just a particular partition.
Would that allow us to model Turing equivalents?
I'm not sure if there's an understanding of what formally demonstrates Turing equivalents then, but I believe it's possible.
I think as a Turing architecture, as far as I understand it, abstracted from the von Neumann architecture is basically just saying, like, you can do a Turing tape.
So I don't see why not.
Why would we need that?
512k ought to be enough for anyone, right?
I don't know why we need it.
We expect it.
But yeah, these graphs in general are more like the space of the possible with the important caveats that were mentioned with the no thumb on the scale and the mirror and the no telepathy and no telkinesis.
But how relevant these edges are or what systems have what behavior or what cognitive phenomena are granted by what dynamics on graphs.
There's just no general answer to those things because if you do a graph for one setting, it's going to be different.
What did you mean when you said that any entree could be ordered with any side dish like that in this recipe theme that we're in models that include continuous or discrete variables or both, what is meant by variable states or observations?
How can states be continuous, as those here are probably familiar with?
States or observations could be like discrete, like zero or one or any integer.
Or it could be a continuous number.
Computers discretize continuous functions to approximate them.
But there's so many exciting directions with unconventional computing, analog computing, mem computing, et cetera, that there's more to it.
But just simply it could be any type of variable.
This new question, let's maybe look at this one in closing, if the external state is unknowable, how can we set up a generative process so that's what's generating the observations when our experience is based solely on the process of producing variational free energy based on predictions and sensory inputs across the markup blanket?
This person has just described the challenge of life.
I don't think that there is a specific answer to that.
I think this is literally a restatement of the particular partition.
If this was just said, the challenge is to given the unknowability, direct unknowability of internal states.
The challenge and the opportunity is to set up a generative model based solely on the process of reducing free energy, based on predictions and sensory inputs across the blanket and adaptive action.
I'm not sure if they meant process or model here because setting up a generative process is something that the human modeler does when they're designing a simulation, but not like what the animal has to do.
What I'm trying to get at here is we are making an assumption about the generator of sensory input when making the model.
Yes, but that model can never be accurate.
Well, it absolutely can be accurate.
It's never going to be a one to one map is the territory, but of course it can be accurate.
We don't need to understand have an atomic simulation of the sun to have a generative process of how many photons are going to hit my window tomorrow at 07:00 a.m..
So there's a core invalidity in the notion that we set up a generative process model.
Not sure what ontology mixing is happening, but almost by definition we're introducing an error in the model by setting up the parameters for the generative process.
The generative model, we remove the fundamental aspect of actin, which is the dynamical system has only one thing it can do and that's to reduce free energy.
So there's some good points and some mixed things.
What it does is the action it takes in the world variational.
Free energy is just a tractable computational heuristic.
Yes, if you set up the generative process to be a number continuous number between one and ten and then the generative model to do the exact same, to kind of have pre structurally learnt the problem, then it's going to be a simple simulation.
Whereas you could have a more sophisticated simulation that involves structured learning as part of the agent's generative model.
Are we not introducing information to the model that would not be available in the real world if we actually defined the generative process?
Yeah, you can give any model too much information, essentially.
So if the model actually knows what is really happening, then if you were doing a video game and you had an agent with supervisory access to the other players inferences or even control their actions, yeah, that's not going to work in a tournament.
But here with a particular partition, we can actually know the information encapsulation.
And Majid Benny explores that in terms of the partial information encapsulation.
So are we not introducing information to the model that would not be available?
It's your restaurant, do whatever you got to do with the recipe.
If you want a pedagogical example that just makes some clean graphs and is very straightforward and doesn't engage the complexities of like sophisticated cognitive structure learning, that model is not going to complain.
If you want to do strange loop reflexive structure modeling for ambiguous inputs of unstructured multimodal data, et cetera, then that is your challenge.
So for many people it's just one closing comment.
In many people.
This is the first time they've been exposed to statistical modeling, and iterative modeling formally.
So that's why there are often questions that are, like, less about active inference, but sometimes crop up about basically using statistical modeling overall, which is a great thing because these are challenging and areas with a lot of implicit and tacit knowledge.
Thank you, fellows.
Looking forward to next discussions and into heading into chapter seven next week.
Ali, maybe we'll do a maybe we'll do our zero for chapter seven and eight, but not in a hurry.
But we'll figure it out.

56:13 _Andrew:_
Sure.
Thank you so much.

56:16 _Daniel:_
Thank you.

56:17 _Speaker C:_
Thank you.

56:18 _Daniel:_
Bye.
