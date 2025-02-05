
00:07 _Daniel Friedman:_

Hello and welcome.
It is March 2023 and we're here in Activem Livestream 52.1.
Welcome to the active institute.
We're a participatory online institute that is communicating, learning and practicing applied active coherence.
This is a recorded and an archived Livestream, so please provide us feedback so we can improve our work.

00:36 All backgrounds and perspectives are welcome and we'll be following video etiquette for livestreams head over active coherence.org to learn more about getting involved in learning groups and projects such as live streams.
All right, we are in 52.1 and our goal today is to learn and discuss this awesome paper geometric Methods for Sampling Optimization, Inference and Adoptive Agents of Barp and Acosta at all.
And we're going to just jump right in.
Thanks a lot Lance for joining and those who have listened to 52.0 will know me.
I'm a researcher and learner with respect to this topic.

01:28 So thanks again for joining and it'll be great to have you introduce yourself and also tell a little bit of the story of how this paper came to be.

01:40 _Lancelot Da Costa:_

Sure.
Thanks Daniel for organizing.
This is really great and I'm very happy to be here.
So my name is Lance de Costa, some of you may know me, I'm a PhD student both at Imperial College of London and UCL, mostly working on active inference and the free energy principle.

02:00 Also some probabilistic machine learning.
And today we're going to be discussing geometric methods for sampling optimization, inference and adaptive agents.
So how this paper came to be where I happen to know people in who do more like statistics, machine learning and so on.
And we've always been talking about the similarities and differences between what we do in two inference and what they do in sampling optimization, which are kind of the workhorses of statistics and machine learning.
And at some point we had a paper invitation for the hamburger of statistics and we decided to team up and make a review article to see how all these Fields that come from very different places scientifically, that have very different contributors as well.

02:57 And we wanted to know how they're interconnected and also how they can help each other because we realized for all this time that we're actually doing similar things, but the communities are very different, they're dot zero much talking to each other.
And I think the main barrier is difference in Lagrange, difference in jargon.
So that was kind of an issue when we started and so I wanted to put that all as much as possible in a paper and see how these different approaches to statistics, whether it is sampling, optimization, inference or decision making, how they can benefit from each other and how they relate to each other.
Long story short, we're going to delve into this into more detail, but long story short, if you want to ensemble from a distribution, you can also view that as an optimization problem.
So optimization is kind of you can see it under the roots of sampling.

04:01 And you want to optimize sampling, make sampling as efficient as possible inference.
You can also see it as an optimization of beliefs, optimization of probability distinctions.
That's also an optimization procedure.
And if you want to do decision making, which is what we do in active inference and reinforcement learning and many different places, well, through decision making, you actually need optimization and inference.
And if you want to do decision making efficiently, you often are going to need something as well.

04:33 So decision making, an active inference is kind of like what comes at the very end and requires all of the sophisticated machinery of sampling coherence of optimization in order to work.
So this was really the idea of the paper, how does optimization come about, how do you do efficient optimization?
And of course there's many different ways to do that.
So we decided to focus on natural ways and we'll get to that.
But one way to do optimization that is very natural is through techniques from geometry.

05:11 And so same with sampling.
In sampling and inference, you have geometry that just comes up very naturally when you want to solve these problems.
And so decision making puts it all together.
So that was really the idea of the paper.
Can we put all these Fields together and have a connecting line which is based on geometry?

05:31 And so that's where we did.

05:35 _Daniel:_

Awesome, great overview.
So, so many places to jump in.

05:45 I barely even know where to sample from this distinctions.
Let's just start with sampling, though.
So what is sampling and how is it being used?
How has it been used?
And let's characterize sampling and then move on to these other Fields, right?

06:07 _Lance:_

Well, sampling, I mean, the idea of sampling is very simple and it's also a very difficult thing to do.
So first explain the idea.
The idea is, let's say you have a Bayesian in one dimension, so that's very easy to picture.
Sampling would be so, for example, the Gaussian I just mentioned describes the temperature in the room.
So in my room, it's maybe currently 18 degrees Celsius, plus or minus some variants representing my uncertainty.

06:41 Now, sampling from the distribution would be saying it is maybe 19 degrees or maybe 17 degrees, drawing a lot of different temperatures.
So that if you put them all together as a histogram with their frequency, for example, if you ask me what temperature it is in my room, I would say there's a higher chance that I say 18 degrees.
So I would say more often if you ask me this question many times, and if you put my answers, if you collect all my answers in a histogram, for example, I'd say 18 degrees more often, so that barp around 18 degrees would be higher and the other temperatures would be slightly lower.
And if you aggregate that, you would get a Gaussian.
Get the Gaussian we started with.

07:31 So sampling, in other words.
And very simply, it's like drawing a data point or an observation from an underlying probability distribution.
You have a distribution, let's say a Bayesian that represents your most likely value of what the temperature in the room is and some uncertainty.
And you just want to draw one or several observations from that distribution.
And you want to draw these observations so as to preserve the overall statistics of the distribution that you started with.

08:04 So that if you draw infinitely many data points or infinitely many observations from a distribution, then you can recover the original distribution.
So that's what we want to do.
And so why is this useful in the first place?
Well, it just happens all the time in the things that you want to computer integrals.
It just happens all the time.

08:29 So, for example, if you have a Bayesian inference problem, you observe some data in the world, it could be medical data, it could really be anything, and you have a prior and a likelihood of observing that data.
So these are two terms in, like, Bayes rule.
Then you want to know.
Then if you apply Bayes rule, you get a posterior belief about what caused that data that you observed.
So, for example, a practical use case would be some medical data of a patient that's sick, and you want to know.

09:07 So you get, for example, it's blood pressure, collection of symptoms and so on.
So that's your data, and you want to know what kind of disease or what kind of function caused that data.
So let's say typically you would have a model of, if I have this malfunction of this disease, I would have these symptoms.
If I have this other disease, I would get these other symptoms.
And so Bazrul enables you to infer in the best way possible, the disease that caused the symptoms that you just saw.

09:49 So this is like a common thing, something that people use every day in statistics all the time, and arguably everybody uses it every day because the thesis of the Franca principle, or the result that it provides, is that you can describe exteroception of humans as doing basic inference.
So basic inference is a very ubiquitous thing.
You can use it to describe perception in humans, and you can also use it to do statistics and solve all kinds of problems.
So, coming back to sampling, actually doing Bayesian inference, you have this problem of how do you compute the posterior distribution in the first place?
And it turns out that this distinctions is generally intractable because you have kind of a term in the denominator that's very hard to compute.

10:55 And so one ways to compute it is to use what's called Monte Carlo methods.
And Monte Carlo methods are based on sampling.
So, long story short, in order to do Bayesian inference, you need to compute this, like, log likelihood term, which is a high dimension integral and one way to do it is by using Monte Carlo methods.
And Monte Carlo methods are based on sampling.
So the sampling enables you to approximate the high dimensional integral they started with.

11:29 So now many listeners, or also the readers of this work will wonder, well, one thing that people do in the free hundred principle and also kind of like the red on that of the 300 principle, is you're actually not going to compute this denominator.
That's very expensive to the Bayesian inference, but you're going to approximate the posterior by minimizing free energy, which is called variational inference.
That's another method of doing Brett and coherence and it has many advantages over sampling.
Sampling also has advantages with respect to variational inference.
We can get into that.

12:15 So if that's what you're thinking, well, this is not necessarily interesting because we can do variational coherence.
There's so many other places where we need sampling in statistics.
I would say basically anytime you need to compute an integral and integral are all over the place.
But I think the Bayesian inference implication is a nice one because it just speaks to all of us.

12:50 So how does actually sampling getting to the picture of integration?
Let's say we have an integral that we need to compute.
An integral is basically, let's say you have a state space.
So to be very simple, let's say the state space is my desk.
It would be like a planner surface and we have a function that's defined on the desk.

13:12 So this would be like a landscape over the desk, right?
Like a 2D surface landscape that could be rocked or whatever.
The integral of this function is going to be the volume between the landscape and the desk.

13:31 This is kind of like the geometric picture of what an integral is.

13:38 This turns out to be very hard to compute in practice because let's say you have a very rough surface and it's not clear how to compute all this volume, which is very irregular.
What sampling does is it's going to pick a few locations on the desk, as many as you wish.
So let's start by one.
And it's going to compute the height under the function and then pick another location and compute that height as well, since sampling is going to pick locations on the desk at random.
And from there it's going to build a histogram that's going to approximate the surface that you started with.

14:30 And so histogram is very simple because you get a whole bunch of skyscrapers if you wish to approximate the surface that we started with.
And computing the volume of skyscrapers is very simple because they're like squares.
It's like depth times height times width.
It's very simple to compute the volume of those things.
So this is kind of the idea we want to computer the volume under a rock surface.

15:00 And to do that, we're going to pick arbitrary locations on the desk, on the page space and build it.
And at those locations build like skyscrapers at the height of the surface.
So you get like a skyline, a histogram that approximates your original function.
And it's very simple to know the volume of the histogram, the volume of the skyline.
So from then you get an estimate of the integral that you started with.

15:36 So that's kind of like the geometric picture.
The beauty of this is that it works in the arbitrary dimensions and it doesn't suffer from the curse of dimension.
So this is why it's so powerful, if you want to know.
So there's a formula that tells you how well the volume of your skyline will approximate the volume of the volume that you initially wanted to compute the integral.
So this difference between the integral and your estimate basically decreases as a function of the number of skyscrapers that you put in.

16:21 The more skyscrapers, the more precise you get.

16:27 And this bound on the error that you have on your integral that you started with, it doesn't depend on the dimension.
So as the higher dimension on your state space.
So let's say let's imagine I had a high dimension desk, which is very hard to imagine, and I had a function on top of it, and I wanted to compute the area under the function.
If my desk was very high dimensional, the higher the dimension, the harder it would be to solve this problem numerically.
But with sampling, actually, the degree of accuracy that you get through sampling would be agnostic to the dimension.

17:17 This is why it's so powerful and just used all the time in physics and machine learning.
When you imagine practical problems that you have in machine learning, going back to medical data, you could get a whole bunch of data about a patient, which could be heart rate over time, blood oxygen levels, blood glucose levels, body temperature and whatnot.
There's so many data modalities that you would have.
So your state space would have many, many dimensions.
And also the state space of the different diseases that could have given rise to all these symptoms would be also very high.

18:08 So it could be that the patient has fever, or it could be that it has flu.
Fever is a symptom.
It could be that the disease is flu.
It could be that the disease is tuberculosis.
It could be that the disease there's so many different conditions or problems that one might want to examine.

18:34 So in this particular case of medical data, and this is just like a very simple use case, I would say you have a very high dimensional state space.
And to debate an inference, you have a very high dimensional integral to estimate.
And so one way to do that efficiently, or maybe efficiently, is disingenuous because it's just very hard.
I mean, it's just very computationally intensive to do these things.
But one way to do this, that state of the art, is through sampling just by drawing different points at random on this safe space and approximating the functional landscape and approximating the integral like that.

19:24 So, yeah, this is really why this is so important.

19:32 _Daniel:_

Awesome.
So we've made a sample where does these topics of accepting or rejecting a move amongst examples or discretizing, how do we pick that next sample?
And then what does it mean to accept or reject that sample?

19:53 _Lance:_

That's a great question.
This is basically like the heart of sampling.

19:58 If you knew how to do that in full generality, sampling would be sold, which it isn't.
So I'm going to tell you a bit like where things stand.

20:14 To do sampling, you need to pick places at random and you need to pick places at random.
So that's to preserve probability distribution.
So going back to the example of the desk, you want to pick in that case, you want to pick examples uniformly on the desk.
If we come back to the previous example of like a Gaussian distribution, you want to pick samples that preserve the Gaussian distribution.
So you ant to preserve to take a lot of samples around the mean very few samples on the tails.

20:53 So it turns out that for those very simple distributions like uniform distribution, Galveston distribution, there are ways to sample that do not require what this paper is talking about.
So there are ways to sample exactly that do not lead to any kind of error and that are very fast.
So for Gaussians and uniform and a bunch of other distributions from the exponential family, you have ways to sample.
Exactly.
So the problem is these distinctions, they're not there all the time.

21:41 And it turns out that very often you don't have these kind of very simple distributions, otherwise we would be done.
So one simple example coming back to Bayesian inference is the idea of Jeffrey's Prior.
So Jeffrey's Prior is the idea that you should take the highest entropy prior that's consistent with what you know about the system.

22:15 Why entropy maximizing?
So we know that entropy is a measure of the uncertainty present in the distribution.
And so what Jeffrey's Prior says is that you should take a prior belief about a system, the belief that is maximally uncertain, uncertain, but that is also compatible with your knowledge.
So out of all priors that are compatible with what you know about the system, you would take the one that's most uncertain.
And this seems pretty intuitive, right?

22:52 So when you take Jeffrey's Friar, what you get is often a distribution that's in the form of what people call a Gibbs measure.
So Gibbs measures or Gibbs distributions there of the form exponential minus V.
So they're like proportional to exponential minus V, and V could be an arbitrary function.
So just as an example, if V were like a parabola, a quadratic function, then the associated Gibbs distribution is a Gaussian.
So we all know what Gaussians are, right?

23:36 But v could be pretty much anything.
If you take V to be like X to the power of four minus X to the power of two, then V is kind of like a camel upside down.
So, you know, it has like two humps.
And therefore the exponential minus V distribution, the Gibbs measure, would be like a gaussian, but with two humps.
So these gibs measures, they're just there like everywhere and they come up all the time.

24:13 So one other example is in statistical mechanics.
So let's say you have a system of molecules that just interact with each other, and this system of molecules, they could also be subject to thermal fluctuations.
And whatnot this system is going to relax to what people call a steady state, often a non equilibrium steady state.
These steady states, which is kind of like the end configuration of the system, is in general a gives measure.

24:55 Now, you can see that in statistical mechanics and also in statistics, gives measures come up also in basic inference.
And it's very hard in general to sample from a gives measure.
There's ways to do it and we're going to come back to it, but we need to solve this problem.
It's a very important problem.
And so the most common way to solve from this distribution is what's called Markov Chain Monte Carlo.

25:29 The idea is to run a Markov chain.
So to run like a stochastic process.
And you could think of it as stimulating molecules that interact with each other with some thermal fluctuations and that are going to relax to this gift distribution, this steady state that you originally specified.
So coming back to the original examples, the steady state could be like a gaussian they want to sample from.
Coming back to the example of the desk.

26:03 It could be the uniform distribution on the desk that we want to sample from.
It could also be a gift measure.

26:11 So once we know the distribution that we want to examples from, we're going to design a stochastic process, some kind of random motion whose distribution is going to converge to the target distribution.
So as you run the process, think of it as simulating those molecules that interact and that converge to your target.

26:42 You're just going to simulate that.
And once your system has converged to its steady state, which is the target distribution, then each movement on the steady state density is going to give you a new sample.

27:00 Just for intuition, let's come back to the desk and say that we have this uniform measure, uniform distribution on the desk that we want to sample from.
So we're going to design like a dynamic that moves randomly around and that's going to concept to the uniform distribution, which means that if you run it long enough, you're just going to sample everywhere on the desk and it's going to examples each point equally often.
And so you're just going to run this dynamic for a very long time and then you're going to collect the samples, collect the examples and use them to approximate the integral that you started with.
So this is how sampling is done.
Now, there's two basically one big question, one big outstanding question is how do you choose this dynamics?

27:55 How do you choose this random motion to converge to your target distinctions to sample from the distribution?
So given a target distribution there's like a closed form formulas for all the possible choices of processes that you can use to sample from them.
That's a closed problem and that's also explained in the paper.
But then out of all of these processes you would like to know which one is going to sample the most efficiently and you also want to know.
And second of all, a lot of the analysis of stochastic processes is done in continuous time.

28:42 So you know that if you implement this process it's going to converge at this rate to the target distinctions.
And so the faster it converges, the better.
But it could be that when you simulate this on a computer, in a computer you can only have like discrete time steps or like discrete operations in discrete time.
So you cannot really simulate this dynamic in continuous time.
So every time you simulate it, it's going to introduce some error.

29:13 Now it could be that the thing that you simulate on your computer actually goes a lot slower than the original process that you wanted to simulate.
So there's these two questions.
How do you take a process that samples very efficiently, converges very fast to your target?
But in addition to that, how do you stimulate the process accurately on your computer so that's to retain all the important characteristics of that process?

29:49 So there's many different criteria and this is what we discussed essentially one method that state of the art or among the state of the art is called Hamiltonian Monte Carlo.
Now, Hamiltonian Monte Carlo, without getting Hinton too much detail, it has two advantages.
The first advantage is that it can be analyzed using mathematical methods.
So you can get guarantees based on your target distribution.
You can get guarantees of how fast you're going to converge, how accurate your samples are, gain to be and so on.

30:35 It has also many other desirable properties.
So one of them which we discuss a lot in the paper is the importance of being irreversible.
So irreversible means being irreversible means that if you run the process forward in time let's say you run the process forward in time for like 10 seconds.
Let's say you run the process backward in time.
So you kind of run the process backward.

31:10 You just take a movie and play it backward and look at how the process behaves.
Now, a process is reversible if the forward and the Ballard movies are statistically indistinguishable and a process is irreversible if you run time as time goes forward.
If you run time forward, it would look statistically different from if you run the process backward.

31:50 I think you can kind of picture what irreversibility is.
Now, irreversibility is crucial to do efficient sampling because if you're reversible, it means that you're going to backtrack.
Very often when you're sampling positions on the decks, on the desk, say you're going to start somewhere, go somewhere else, and then there's a nontrivial chance, significant chance that you're going to come back to where you started.
So it's going to be very slow to explore all the desk and build skyscrapers everywhere.

32:28 So then sampling turns out to be very slow.
Now, when you're irreversible, there's way less chances that you just come back to where you started.
So you're going to explore the desk a lot faster because you're not allowed to come back to the same place so much.
And so you're going to assemble faster and it's going to be much more efficient.
So it's actually, by going from a reversible process for sampling to an irreversible process, you can gain orders and orders of magnitude, efficiency.

33:06 It's actually pretty crazy.

33:10 The Hamiltonian monte Carlo has guarantees.
Is irreversible.
It has other desirable properties.
And the main one is that you can actually stimulate it on a computer in a way that the discretized version, which you actually simulate on the computer is going to be very close to the true Hamilton in Monte Carlo that you get by writing the equation down.
So this is like why it's so big and why people use it.

33:56 Yeah, I think this is pretty much it.
Hamiltonia Monte Carlo has an accept rejects step, which is coming back to when you simulate a process on your computer.
Every time you discreditize a process, you introduce some error.
Now you want to make that discretization error as small as possible so that the process that you actually simulate on your computer is very close to what you want to simulate.
So Hamiltonia Monte Carlo has a very important step called Metropolis Hastings, which is going to say, should I keep the sample or should I drop the sample and go to the next examples?

34:53 And by using Metropolis Hastings, it's a very clever but also simple procedure.
By using Metropolis Hastings, you guarantee that the distribution that you're going to sample is exactly the same as the distribution that you want to sample.
So just to put in other, maybe simpler terms, so you have this process that you want to simulate.
This process is going to sample your target distribution.
Now, it could be that when you discrete the process, because the discrete process is different, you're going to sample from a slightly different distinctions.

35:39 Now, by using Metropolis Hastings, you're going to guarantee that the distribution that you sample from in practice is exactly the same as what you really want to sample from.
And so that's very important because it just tells you that asymptotically as the number of examples just growth to infinity.
You're going to recover exactly what you wanted to recover, which is the adamant shrine to grow.

36:12 _Daniel:_

Awesome.
I remember the Metropolis Hastings and the Monte Carlo Markov chains in phylogenetics where you might have many, many species and many, many locations in the genome that you're doing phylogenetic inference over and you just sample, sample, sample.
And so all these techniques help accelerate what's possible with any given computational hardware.
So how would you bring this towards adaptive agents?
Are we thinking about this sampling process as being guided by an adaptive agent and or are we sampling distributions about an adaptive agent?

37:01 _Lance:_

That's a great question.
And I think it sort of brings us to the conclusion of this work.

37:11 In order to have adaptive agents and to scale adaptive agents so that they're able to solve complex problems and you're able to implement them with finite computational resources, one useful tool is sampling.
And we'll see many different places where sampling can be used and has been used in active inference.

37:37 And that's basically what you said sampling is at the heart of sampling is choosing data points intelligently so as to approximate your integral or whatever it is that you want to do with those samples.
So you could think of active agents as solving the sampling problem.
You could think of an active inference agent.
Let's say that you have a problem of sampling.
You could think of an agent, an active inference agent that's going to choose, oh, I'm going to sample here, and I'm going to sample here, and I'm going to sample here.

38:22 So active inference agent in the proper sense of the word.
They do sampling all the time.
The only I would say, slight difference with what we've just discussed is that active inference agents, they sample observations so that they comply with their preferences and they observations that also bring them new information about the world.
So the objective that active inference agents use to select new sample is the expected free energy.
Typically we select actions or policies that have the lowest expected free energy, which means that the resulting observations will be close to your preferences or goal and also bring you new information about the world.

39:18 But you could also conceivably think of an agent as selecting actions so that the resulting samples or observations accurately sample a distribution.

39:33 So how could sampling be used in the context active coherence lab and adaptive agents?
And so this is actually a great slide, if you look at the upper panel is what I just discussed.
So in the first equation that's up there, you see that the sequence of actions that you chaos in active inference is the one that minimizes this minus lot T, this probes distribution over action sequences.
So this minus lot T is actually the expected free energy.
So we choose action sequences that mean by the expected free energy, as you see on the equation just below the expected.

40:21 Free energy is a sum of risk and ambiguity.
So you're going to choose action sequences that minimize risk, but that also minimize ambiguity about the world.
And in other words, as shown below, you're going to choose action sequences that maximize extrinsic value.
So you could think of that as an expected reward and intrinsic value.
So that would be expected information gain value that's intrinsic because you're getting information.

40:52 So really the key here is that this expected free energy, as its name suggests, it's given by an expectation.
So you see this minus lock p on the left equals expectation of something.
Now, when you have a very big generative model, a very big world model, which is going to be the case all the time, when you have, like, a real world application or a complex application, because the world around us is so high dimensional, so complex, well, the expected energy then is going to be a high dimensional expectation.
What is an expectation?
It's an integral with respect to probability distribution.

41:40 So the point I want to get to is that to do decision making, you need to evaluate the expected free energy on different action sequences.
And this expected free energy is an expectation with respect to probability distribution.
It's a very high dimensional integration problem, very high dimension integration expectation.
And so how do you approximate that while you use template?
And I think the first work that actually used that in the context of active inference is the work by Fuentes et al.

42:22 2020.

42:26 I think it's called scaling active inference with Monte Carlo methods.
So this is what they did.
I think it was published in New Ritz.
It's a very big machine learning conference.
And their observation was, okay, well, we have this active inference method which theoretically is very powerful, I mean, in the sense that you have this expected free energy objectives, that puts a lot of known constructs together.

43:11 So the expected free energy, as shown in figure three here, puts together this risk.
So this is the divergence between your predicted distribution of where you're going to be in the world and your target distribution of where you want to be in the world.
And it has this ambiguity term as well, which has some nice links with phenomena in psychology, like the streetlight affect.
So when you minimize we introduce actions that minimize ambiguity.
You can recover phenomenology that's known in psychology, like the streetlight affect or the drunkard search.

43:51 Risk is also an objective that's used in engineering, in controller inference.
So you can see it on the left panel.
So there are a few methods for doing adaptive agents that use this KL term.
One would be controlled coherence, which is also known as maximum entropy reinforcement learning and KL control.
And also, I think, although it needs to be investigated further, it hasn't been formally, I think, so far, but with the KL turn there, you can recover predictions that are made by prospect theory which is a big theory from the end of the 20th century about decision making in human agents.

44:39 So this is, I think, worthwhile to look into further but I think there's some very clear links between that theory and the scale term in the expected franca.
Anyway, so you have this expected free energy objective that's very powerful.
Chaos puts a lot of things together.
So I think theoretically it's very nice.
In the last line of the upper panel you can also see that you can view expected PNG as weighing expected reward and expected information gain, extrinsic value, intrinsic value and extrinsic value.

45:18 It's used in expected utility theory, basic decision theory, RL, optimal control.
So these are all like equivalent names for maximizing this extrinsic value and intrinsic value, expected information gain.
It's also used in different places and for example in Bayesian experimental design which is in statistics.
It was a seminal paper by Lindley in 1956 and Lindley basically said, okay, well, suppose that you you can do two experiments or many different experiments.
How should you choose between them?

46:02 What's the best experiment that you should do?
And the answer that he came up with is you should do the experiment that gives you the most information about the world.
So you have to keep in mind that in that paper there was no extrinsic goal.
It was not like we're going to do an experiment to solve this problem or achieve these results.
It was only doing an experiment for the sake of it.

46:31 And so he came to the conclusion that the best experiment was the one that maximized the expected information gain.
Now suppose that you have a goal in mind target, target result or whatnot then you would weigh reasonably and one thing you could do is weigh the expected information gain with your expected reward or expected utility or expected how close you're going to get to your goal.
And so this is exactly what the expected free energy does.
It puts these two things on the same footing.

47:08 So you have this expected free energy which is very nice and which is what active inference brings to the table and what Fuentes et al did in their paper is, okay, well, we have this cool method, active inference, let's use it to solve nontrivial machine learning, slash reinforcement learning problems.
And so when you actually want to solve those problems you have some high dimensional generative models, high dimensional state spaces that just come up and you need time plane to evaluate to approximate the expected principle.
So this is what they did and they also put together a lot of other cool tricks based on neural networks and so on.
So a very cool paper, totally recommend.
But I think the point it suggests, and this is also the point that we make, although in a very different way in this paper is that to actually do decision making efficiently in practice efficiently.

48:14 But also you want to do take good decisions.
You actually need sampling.

48:25 And this is not a new point, by the way.
I think many people would agree with this.
But I think the active inference approach is nice because you have this explicit characterization of expected PNG as an expectation of something.
So it becomes pretty clear that you want to do sampling because this is what sampling is made for.
So I initially introduction sampling as you know, wanting to approximate integral, but expectations are integral.

49:02 So yes, sampling is really what you want.
It just comes up like extremely directly when you want to do these kind of things.
Awesome.

49:12 _Daniel:_

Thanks.
And one sensory example of information driven sampling is the eye circade the movement of the eyes, which also has been modeled in many works from the active inference perspective.

49:28 And it's even below our level of conscious awareness with the eyes darting around to reduce their uncertainty such that our visual generative model can have high resolution and color throughout the visual field, even though that doesn't reflect the anatomy of the retina, which has a blind spot and differential resolution and color attention in the periphery.
So I kind of see that as slam dunk evidence that our visual experience and by extension other sensory modalities are coming from the generative model.
They're not just received and processed in an inward bound fashion and that adaptive sampling is vital to maintain the coherence of that generative model.

50:24 _Lance:_

Absolutely.
You want to do adaptive sampling in order to preserve the structure.

50:31 I mean, you have this beautiful structure in the expected free energy of expected information gain.
So let's say we're just like wanting we're just like looking at stuff, so we don't have any direct goal.
The expected energy reduces to expect information gain or approximates that and you just want to sample sampling is the key to approximate this expected information gain term while preserving the statistics of the generative model.
So it's very central to scaling active coherence.
I wouldn't say it's central, active inference lab proper just the theory because in the theory you get these expectations and you know how to select actions.

51:22 But anytime you want to scale active coherence, deploy active inference to solve a problem you want to, sampling is going to come into play inevitably.

51:39 There's other ways to scale active inference.
One other way could be what's called amortizing.
Amortization.
So with deep neural networks.
So one thing you could do is train a neural network to predict the expected free energy based on your genital model and near sensory data.

52:00 But this amortization procedure, as does any training of neural networks, it's going to require a lot of data.
So it's going to be slow.
It's not something that you can deploy right away.
So this is very nice way of I mean, amortization is a very nice way of doing things, but it's not something that you can use like the first time you active inference lab to solve a new task.
So a nice way of scaling active coherence and it's not the only way, or it's not going to solve all the problems, but it would be to use sampling to approximate the expected free energy to make decisions in real time as you accumulate data, then you can train a neural network to predict the expected free energy.

52:51 I think this is exactly what Fuentes et al.
Did in their paper, by the way.
So if you're interested, make sure to check it out.

53:02 _Daniel:_

Figure three.
It's something that Vaughn can just look ant for so long, because the imperative, what is being utilized in action selection by an active inference agent is something like a generalization of all the words that we see written lower.
And unless we knew about that generalization or that unified imperative, it seems like these are quite literally orthogonal or disparate from each other.
I mean, what could be more different than maximum information, gain oriented strategies and maximum reward driven strategies?
And sometimes to get both those flavors in the same model, people might try to coerce one into the other.

53:55 Usually we see that in terms of a novelty bonus or an exploratory impulse bolted on to a reward or a pragmatic value driven agent.
And so once you start modifying the models and just adding in these arbitrarily constructed components, you may get adaptive behavior.
It's never been a claim in the active space that other models don't have efficacy.
Rather that by thinking about all of these special cases as being situationally arising from a more general imperative with expected free energy for future oriented policy selection, we might gain the ability to do what?
What will we gain conceptually or in practice by taking situations where today people are using maybe just one of these terms as an imperative for what their models are doing and what do we gain or what might we expect from potentially generalizing those imperatives?

55:08 _Lance:_

That's a brilliant and very difficult question.
It's also a question that I would say everybody active coherence lab gets asked at some point because, let's say people doing reinforcement learning, they use many different objectives that would be tailored to solving one particular task or a different task, and they would have these ad hoc novelty bonuses that would work very well in certain tasks.

55:46 It's a different approach.

55:50 This approach that I was just mentioning with reinforcement learning tests to be it's much more bottom up.
It's like we want to have an agent that solves this problem, makes this work, and so on.
So we're going to start building and test it until it works.
Active inference lab approach is top down.
So it starts from the furniture principle and it's very theoretical.

56:21 And the approach is like, okay, well, let's model how an agent interacts with its environment, the force generic kind of agent, and let's impose constraints that an agent has to satisfy.
So the basic constraint that we have in this paper is that you have three sets of variables.
You have variables in the external world that you cannot directly have access to.
So this would be maybe the temperature in the room.
Then you have sensory variables or observations.

57:03 So by the way, the environmental variables that are denoted as S, the sensory observations, are the observatory or the observations that are denoted as O.
So this is what belongs to the world and you have direct access to this would be like your sensations, what you see and so on.
And then you have the action denoted in the paper by A, which is basically what you can do, and the different things, the different options that you can choose from at any point in time.
And this is what will enable you to influence the world S and influence your observations.
O.

57:45 So we start from a very generic model of an agent and how it interacts with the world, these three sets of variables that evolve in time and just by adding a few other, I would say, constraints that agents satisfy, or intelligent agents hopefully satisfy, that these agents can be described as taking decisions that minimize expected free energy.
So the expected free energy just comes up from this general theory of how agents behave.
So to answer your question, what does this actually bring in practice?
Well, first of all, there's many methods out there that are similar to active inference.
In some cases, they're almost the same.

58:48 The first difference, which is not necessarily an advantage or a disadvantage, but it's the approach.
These are the methods that you see out there that come very close to active inference.
They have been designed from a bottom up approach of like, we want to model this system or we want to solve this task, so we're going to add all the components that are needed until our agent does what we want it to do.
And it turns out that sometimes all these ingredients turn out to be exactly what we get.
Active Inference lab or very similar.

59:25 Other times, maybe the task would be simpler and you would get less ingredients.
The disadvantage of that, I would say, is that it can turn out to be very messy.
So you get a new task or a new thing to model, maybe a new paradigm that some subject would do, and you end up using a very different model, a very different objective to describe the behavior at hand.
So it's harder to have like a unified perspective of what's going on.
Active Inference I would say the key contribution is that you get this unified perspective from it.

1:00:09 You get this objective that puts together a lot of other constructs that we know and love and puts them together.
And you know that with this objective you can do a lot of things, which is, for example, decision making that weighs exploration and exploration.
Now, there are some challenges with active inference and anybody using active inference would be familiar with them.
The first one is the scaling up because you have this approach, active inference, which is so complex in a way.
I mean, you need to have a generative model of the world.

1:00:52 You need to have to be able to compute all these expectations.
First of all, you need to be able to compute all these posterior distributions using bayes rule or variational inference.
Then once you have those posterior or approximate posterior distributions based on your high dimensional model of the world, then you need to compute some expectations, very high dimensional expectation using sampling or whatnot, to then get the expected free energy.
So the expected free energy doesn't come up for free.
It's actually a very I would say it's a quite sophisticated thing.

1:01:30 It puts all these things together, but it doesn't come for free.
It's hard to implement on a practical problem that's nontrivial beyond toys and nations and people have done it, but it's a challenge.
So the problem that active coherence has is, okay, well, we have this night theory, we have this very nice objective that theoretically works very well, and theoretically it's like or it's similar to what you would like to have for any kind of agenda.
But we need to find ways of scaling this up.

1:02:16 Here comes the beauty of this, is that in scaling up active inference, you're going to use sampling, you're going to use techniques from optimization, from coherence, and so you're going to get something that's slightly different from the active inference scheme that you started with.
So you had the active inference scheme proper, which was in the picture in the previous slide.

1:02:49 This is active inference as you would like to implement it if you could.
But because the problem is complicated and you have a high dimension state, space and so on, you have many things that are computationally intensive, you're going to use something, you're going to use optimization, you're gain to use inference, and so you're going to get something.
Active inference lab algorithm that scales, but that's slightly different from what you started because it has all these other steps.
Now, in doing so, the active coherence agent becomes engineered.
So it becomes closer to these reinforcement learning and bottom up agents that are built in a bottom up way to solve certain tasks.

1:03:39 Because you want to engineer the active impress algorithm to be able to work to solve a certain problem, to scale it in a certain way.
So in doing so, active imprint becomes closer to reinforcement learning.
Now, conversely, in reinforcement learning, the amount of compute is increasing.
People want to build reinforcement learning agents that are increasingly learn in an unsupervised manner just because this scale is better.

1:04:18 You can't always design all the components of your reinforcement learning agent to solve any single tax.
It's just too impractical, especially when tasks become more and more complicated.
You just would like general solutions that are going to work and are going to handle a lot of different types of situations.
So reinforcement learning is adding or subtracting ingredients to their algorithms.
All these algorithms are evolving.

1:04:55 But in some sense you can see this is debatable, I suppose, but you can see a general tendency towards moving to world models and generative models, moving to intrinsic motivation, which is another word for expected information gain or variants thereof, and an intrinsic motivation or intrinsic value that's added onto extrinsic value which is your expected reward.
So you see many I mean, I think we're seeing reinforcement learning evolve in a direction also that is closer active inference lab because everybody wants algorithms that stole different tasks and not to have to change the algorithms for changing environments and so on.
So in my view, even though we started with two different approaches, a bottom up approach and a top down approach, these are converging.

1:06:05 Now to come back to the contribution of active inference, if one reads through the paper and one looks at the derivation active inference lab, the point is that it's very agnostic.
It's agnostic to the environment that we're in.

1:06:25 It's an agnostic to many things.
So it's very general.
And so if you take many practical reinforcement learning agent, you will see that they interact with their environment in a way that's compatible with the assumptions of the free hundred principle.
In other words, the reinforcement learning agents can be recast as specific active inference agents with specific giant models.
So this is really the key thing.

1:07:02 It's this unifying perspective.
I'm not saying it unifies everything, but I'm saying that many different reinforcement learning algorithms can be recast as active inference agents.
And so this is not to say that active inference lab implementation of those reinforcement algorithms is going to be better, but it's more like a theoretical contribution of like this set of equations given by the expected primary is a complete recipe or almost complete recipe to generate adaptive agents.
So in some sense you don't have to go any further than that.
And so you can view all these reinforcement learning algorithms that comply with the assumptions so that can be recast as active inference algorithms as ways of scaling active inference and making active inference work.

1:07:59 So it's not like I don't see any kind of conflict between active inference and reinforcement learning, but it's more like the reinforcement learning algorithms that work well and that can be recast as active inference algorithms.
And there are many, I would say more algorithms that can be recast and algorithm that can help when you look at the assumptions of the free energy principle that are super generic.
So you can view all these algorithms as specific implementations of active inference in a way that active inference is meant to scale well.
So this is kind of like the thing.
And so I think ultimately, again, these two Fields are going to converge, but I do not see any tension between them.

1:08:55 It's more like the tools from one can be used in the other.

1:09:02 I see great work going forward.
And this is kind of like what we want to do with this paper.
Put this active coherence where it comes from very succinctly, and also make it accessible for people who don't know the jargon from the fringe principal and active coherence community.
And yes, see the exciting developments that will follow.

1:09:30 _Daniel:_

Wow.

1:09:31 Great comments.
Two things that reflects to me the constraints that you mentioned, which we sometimes call the particular partition essentially cleaving the particle, which you show in figure two, cleaving the particle off from the environment.
This is something that's widely applied in agent based modeling.
Just anytime you're talking about some field of action and a player, we're basically at least qualitatively within the space of partitioning agents from environments and then further saying, well, there's no edge between the internal and the external states, so there's no telepathy and there's no telekinesis and incoming information.
We're going to call sense outgoing.

1:10:20 We're going to call action that qualitatively and formally is basically consistent with almost any cybernetics formulation of adaptive action.
So Axel constant are really quite minimal and seemingly being generalized year after year with the work so many colleagues are involved in.
So Axel Costa are not onerous.
And I think it's a really interesting question which reinforcement learnings are compatible?
And then coming from the other side, in a lot of active modeling contexts, we find ourselves sometimes proposing like auxiliary variables.

1:11:03 Like, let's just do a parameter sweep over this.
And then we'll look back to the textbook or to the paper.
We think, well, where was that in expected free energy?
We just proposed this random thing.
Where was that in the equation?

1:11:16 Or we'll look at step by step guide to active inference where it's all written in terms of matrices.
It's all very read.
It like a sentence.
And all of a sudden it's like, wait a could be a neural network.
It doesn't just have to be a matrix.

1:11:31 So it's kind of like we bring in these methods and ingredients that are being used widely, empirically.
And these are the two approaches.
Do we build the bottom up mosaic of approaches stopping when it works?
And or do we start with this most general agent based cybernetic formulation and then kind of build the castle in the sky and meet in the middle again with something that works?
It's just incredibly laid out.

1:12:10 And this paper is at that saddle point because it has one hand or antenna or whatever in this smooth information geometry conceptual area.
But the motivator of all of the conceptual moves that are made, which honestly are extensive, like page after page, it was just like, where's it going?
It's going somewhere that can be simulated on everyday hardware.
So many of the moves were about reshaping or reframing what was to be done in a way that could be simulated.
And so those two paths are connecting and like you said, there's not necessarily attention, but it'll be quite interesting to see how this develops on the theory, practice and social frontiers as more and more of these threads start to combine.

1:13:17 _Lance:_

Yeah, I agree.
I think it's particularly beautiful when theory meets practice.
You oftentimes have practice that works, but you have no theory or you have a theory that's beautiful but that doesn't work in practice.
And this just happens all the time.
Typically you would have active that works and then you would try to build a theory out of it, but then often the theory turns out to be too hard, so you make some extra assumptions and so on.

1:13:53 You end up with a theory, but the theory turns out to be quite removed from the practice.
So you kind of get that gap.
It's very beautiful and quite unique and also quite rare when the theory meets the practice.
And I would say when the theory meets the practice and in particular meets the state of the art, then you kind of have a complete theory.

1:14:16 So what we wanted to do in this paper is review these different Fields in a way that we could show how far the community has gone between making a theory that meets the state of the art.
And every section was started with theoretical considerations about what should be when you need to solve a particular problem, let's say adaptive agents or sampling or optimization.
And then from there, and from logical steps about, okay, well, it should be like this and not like that, because there is whatever kind of geometric argument or other arguments.
And so from there, logically arriving at state of the art methods that are used in practice.
The other kind of like sequence of logical steps was, okay, well, we're going to start with optimization which is in my view, at the root of everything.

1:15:26 So sampling could be about optimizing samples to obtain the best approximation to your integral inferences about optimizing beliefs and decision making.
It's about optimizing decisions based on their counterfactuals consequences.
So we started up with optimization because it's the simplest thing both conceptually and also in terms of use case you need optimization to do everything else.
We then went to sampling and to inference and finally to decision making because it just brings all these three ingredients together.
We didn't go as far as showing, okay, well, this is how you should scale active inference in order to solve all the problems in the world because this just hasn't been done right.

1:16:14 But we listed a few ingredients that have gone into the literature and also a few ingredients that this perspective offers to how to scale active inference and make it more effective.
So it's actually future work and open problem to use the techniques that have been developed in the sampling section and the sampling literature to make active inference even more scalable and same with optimization and same with coherence.
So there's many things that have been put forward in this article and also elsewhere that can be used to scale active imprints but ant least.
Yeah, the goal was to be as comprehensive as possible without sacrificing too much of actually understanding what's really going on and show how the theory means to practice throughout and really where the field stands.

1:17:12 _Daniel:_

So one kind of reflection on this, again, is if we start with reward as our basal imperative pragmatism.

1:17:22 I mean, after all, don't we want to get things done, achieve results in the world, realize our preferences?
We start with pragmatism and then it is empirically ad hoc how people introduce these novelty bonus or intrinsic motivations.
In contrast, we can start with this information gain approach and then the thumb is put on the scale to bring more and more emphasis onto the alignment with preference.
So it's like two roads, two paths.
And maybe this is our bias or corner of the information space that starting with a broader epistemic imperative allows the careful introduction of pragmatic value whereas a pragmatic foundation that it's hard to then recast epistemic value in terms of pragmatic value.

1:18:37 That's kind of like the question of valuing basic research.
And the approach taken here is develop an imperative that can look entirely like one or the other or mixtures.
But what's always so perplexing is that it has this extrinsic and intrinsic value phrasing but there are other ways to decompose the function.
So even intrinsic and extrinsic value are not necessarily the ingredients that were put in.
It's more like they were two ingredients that were split out of something else that is much more integrated.

1:19:28 It wasn't like the free energy was constructed by composition of any given decomposition of which there are multiple for variational free energy and expected free energy.
So then a question that I've often wondered is there might be two policies that are very close or have essentially identical expected free energy but they could be radically different.
For example, one could be having a good expected free energy because it realizes a lot of preferences.
Another might because it provides a lot of information gain.
So is it really as simple asterisk asterisk as a unified imperative or how do we make sense of the fact that one value could rank policies that might have, for example, extremely different danger profiles or envelopes of outcomes?

1:20:46 How can that seemingly multidimensional space be projected into essentially a ranking?

1:20:59 _Lance:_

Yeah, it's a complicated question.
As we can see, the expected free energy does this in some way.
It provides an answer to this question based on your preferences and how much you would gain by observing this new data, how much information you would gain.
You can put these two things on the same.

1:21:21 Footing.
This is what expected PNG does, and it gives you a ranking.

1:21:29 You're right to say that two very different courses of action could have the same expected free energy.
And so how do you choose between them?
Well, the standard formulation that you would see in textbooks or papers has, okay, well, G of Action Sequence equals this and G of Sequence equals that.
So these two Action sequences have the same G and you don't know what to do.
But here, this theoretical development in this paper makes it very clear that the expected PNG is a minus lock probability.

1:22:03 And this is why.
So to make it more transparent, instead of using the letter G that's commonly used in the literature, we kept the minus log P throughout.
So we never used the letter G.
And so the expected free energy is this minus log P of Action Sequence.
And so it says, okay, well, if two Action Sequences have the same expected free energy, well, then you have, let's say you just have two of them with the same expected force energy, the lowest one, well, then you choose probabilistically.

1:22:34 Like half of the time you choose one, and half of the time you use the other.
Actually, it's even a bit more complicated because since it's a minus lot P, you could have an Action Sequence with a very high expected free energy.
And so this means that you can still take it.
But if you would take it, like, not very often.
So you have an exponentially low chance of taking that Action Sequence.

1:23:05 So it's a probabilistic description.

1:23:10 It says that the most likely Action Sequence would be the argument, the minimum of the expected free energy.
So this is like the top line in the figure.
And so if you have two most likely Action Sequences, well, then you choose like half of the time you choose one, half of the time you choose the other.
But then in general, if you didn't want to simulate the most likely Action Sequence, then you choose probabilistically between all of them.
And the Action Sequences that have the lowest expected reality has an exponentially higher chance of being selected and the others don't.

1:23:54 One last thing.
Another very nice perspective is that the probability over Action sequences, so these P of a greater than equal to T is then the exponential of minus the expected free energy.
Because if you take exponential minus of what you get in the equality on the left, then you recover this probability distribution of our Action Sequences.
So this distribution of our Action Sequences is exponential minus expected free energy, exponential minus what's in there.
And we saw before, that gives measures, they arise everywhere.

1:24:39 And so this is an example of a gives measure.
You have exponential minus something basically, based on the formalism of the free free energy principle comes up that the probability distribution over Actions is a gives measure.
It is the gives measure where what's inside is the expected free energy.
So, yeah, it's kind of like a full circle thing and this is basically this sort of like connectivity.
They just happen all the time when we were writing this paper and discussing because there's so many things that just there's so many crossovers at so many different levels.

1:25:25 Like on the sort of object level that you're studying, but also on the ecological level, like methodologies that are used in some field, they're used in a different field to do something else.
So there's so many crossovers.
And so this is, I would say, an interesting example of why gives measures, gives distinctions, they just arise everywhere.
They arise active inference Lab and as we saw before, they're hard to sample from.
So if you wanted to so let's say you have your gives distribution that says, okay, well, this is my distribution of our action sequences that I get from the expected free energy.

1:26:09 Then you have two choices.
Either you sample from it to sample like an average, I would say not a typical action sequence, or you could optimize the distribution or optimize the expected free energy to sample the most likely action sequence.
In the two cases after you've done your planning with the expected free energy, you have a choice between sampling and optimization.
So you kind of go back full circle of like if I want to select my action gain, I either select the most likely action by optimizing the expected free energy or the gives measure by optimizing this minus lot P by taking the action sequence with the minimal expected free energy.
Or I have my gives measure and it will sample from it to like get a typical action sequence.

1:27:07 So it's all like super interrelated.

1:27:13 _Daniel:_

Very interesting in the Par et al.
Textbook from 2022, that dialectic is mapped onto the mammalian nervous system where policies can be selected by essentially passing through habit proportionally or expected free energy can be applied to sharpen or optimize the posterior on action.

1:27:49 Does this influence how you select micro meso or macro actions?

1:27:59 _Lance:_

Do you mean for human being like actions at the cellular level, actions at the Global level?
Or is it something different like at.

1:28:08 _Daniel:_

The personal, grasping a coffee cup at the micro, larger scale decisions, attention allocation, communication emissions.

1:28:23 _Lance:_

Yeah, I think all of these things can be formulated in this treatment.
So, for example, attention would be where you choose to place your focus or your mental eye, so to speak.

1:28:40 So that's and internal action, it could be unconscious, it could be undirected, but still happening.

1:28:48 I'm not an expert, but there's a lot of talking consciousness research of like, you being conscious.
There's a very low amount of processes that are conscious and these change according to where you're inner eye or your conscious eye, whatever you want to call it, like moves.
This could be thought of a mental action or an inner action that you may or may not control, but still and action.
So all these, all other action, whether it is planning at the short time scale, taking a coffee cup standing, or planning at the longer time scale, like what am I going to do after my PhD and so on, all of these things are action.
So typically, as you know, of course, we we model that by using hierarchical models where you have different levels in your giant model.

1:29:55 So in your model of the world and the higher levels are represent more abstract representations and also longer time scales.
So it could be, let's say at some higher level I'm going to take the plane to go to Amsterdam, for example, and at the lower level, okay, well, once in Amsterdam, I'm going to do this, this and this.
It's like this action at the higher level of taking the plane predates everything that you're going to do at the lower level.
And so factorizing these different decisions into different levels of a model allow you to be completionally, practical, practically implementable when you make those decisions.
And presumably this is why we do in our everyday life factorize decisions and representations into low level and high level things.

1:30:59 The beauty of the free energy principle and of the treatment here.
But the treatment here is again, just the free energy principle in its most bare bones and general form is that the expected free energy is formulated for any kind of gentle model.
The gentle models that you have in the figure on the bottom right there, they could be arbitrary.
So you could use this form of expected Lagrange for hierarchical generative models that have all these like high level, low level decisions and representations, but you could also use it for any other kind of generative model.
The only difference is that with some world models, it would be very hard to implement this in practice and with other world models, and in particular those that are highly factorised and distributed like hierarchical models, like the wounds we just talked about.

1:32:03 With these it would typically Dean much simpler to take decisions that minimize expected frequency when it comes to practical computation, just because when you action oriented representation things, just computations just factor out a lot and it's just like way simpler to do.
But the formulation here is like entirely generic and it could apply to all kinds of models and all kinds of situations.

1:32:39 _Daniel:_

Very interesting.
Well, in our last little segment on the dot one, let's hear your perspective or overview on the roadmap.
Just walk through what the sections are and you mentioned some related topics, but what do the subjects broadly cover?
Why are they structured in that order?

1:33:08 _Lance:_

Right, well, first of all, the introduction just puts like everything in context, the conducting line or one of the common points between all of these sections is that there's a lot of geometry.

1:33:27 So this was not purely because the journal is like the handbook of statistics, it was called Geometry and Statistics.
So this is not just for that, but it's because geometry just comes up naturally in all these places.
So this is what we explained in the introduction, like how geometry comes up, the different branches of geometry that come up in this different field and how they're interrelated.
And so just from there you kind of get a picture of, okay, well, this branch, let's say symplectic geometry, for example, it comes up in accelerated optimization and it also comes up in sampling.
And so you can already see from there what is going to be discussed, of course, but also which branches of geometry occur where and what kind of parallels there are already.

1:34:30 So going from the introduction to accelerated optimization.
So optimization is conceptually, it's a very simple thing.
It's like, okay, we have a function.
So coming back to, let's say that my Dean state space come back to where we started with and you have a function and a landscape over it, let's say like a mountain.
And so the goal is to find the minimum of the mountain.

1:34:58 I go from where you start to the minimum.
There's so many different ways of solving this problem, practically speaking.
The main challenge, of course, is that you don't know, you cannot speak anywhere else except where you have been.
So you start somewhere and you're completely blind and you need to find a minimum.
So how do you do that?

1:35:25 There's so many ways, so many approaches to optimization.
I mean, it's a whole field and it's in my opinion, a very messy one.
And this is understandable because there's no free lunch theorems that are very well known that say that under some hypotheses, two ways of doing optimization will behave the same on average if you test them again, all possible sorts of problems.
So this is to say that if you have a given problem, then you need to give then the optimization methods that will work well are those that implicitly use the prior information that you have about the problem.
In other words, according to the theorems, there's no optimization methods that will beat everything, it just doesn't exist because they're all on average the same.

1:36:27 But this is not to say that you cannot make any practical, meaningful steps by doing optimization because not all optimization problems are the optimization problems that we have in life.
They're not completely random, they're not completely random landscapes that we need to optimize, but they actually have some structure.
So we can actually explore that in algorithms and have things that just behave, that just work a lot better for the type of problems that we're interested in than others.
So this is what kind of like the starting point for all optimization.

1:37:10 The type of optimization that we considered here is optimization of smooth functions.
This is already like a big restriction there's.
So many methods that are designed to optimize functions that are rugged or non smooth or have discontinuities and so on.
When you actually get rugged or discontinuous landscapes, it's a whole different problem.
Here we chose to focus on smooth functions.

1:37:46 The idea is that you have a smooth landscape, you want to find the minimum.
And one way to do so, and to do so well, is through the use of a tool called geometric inclination.
So I'll walk through the main ideas of this section.
The idea, first of all, is that you may design a method that theoretically works very well, but when you implement it in practice on your computer, your discretion errors, because you can only implement it in discrete time, what you actually end up implementing ends up deferring significantly from what you initially wanted to implement.
This is a problem that we discussed previously in sampling and it just comes up everywhere in applied mathematics and numerical mathematics.

1:38:51 The fact that you can only do discrete computations on your computer is a big implication and it's something that needs to be looked into.
It's maybe even the most important thing that needs to be looked into.
When building a numerical method, you want to be able to implement numerical methods that are very close from what you theoretically would like to implement.
So typically you would have some theoretical algorithm that would have some convergence guarantees or performance guarantees.
And so you would like to wait a way to implement it on your computer so as to preserve those guarantees.

1:39:36 And this turns out to be very hard in general.
One way to do it, I would say maybe the most powerful way out there to do this is through procedures from the field of geometric inclination.
And so geometric integration is a set of techniques that allow you under certain cognition to discretize your theoretical, dynamic or theoretical optimization procedure like dynamical system, and make it into an algorithm that you can practically implement on a computer.
And that's going to respect the performance guarantees that you already have.
So now the tricky part, geometric inclination is based on geometry.

1:40:32 So you need to find it's not as simple as like, okay, well, I have my landscape, my function landscape, and I'd like to just go down and find the minimum.
One way to do that is just by doing grain in descent in continuous time.
And you know that that's going to go down until it reaches a local minimum at the very least.
So it's not too bad.
If you were to implement gradient descent numerically, it wouldn't be exactly the same as like the continuous time dynamic.

1:41:07 It could be that actually by implementing gradient descent numerically, you get all sorts of numerical problems or whatnot maybe grade and send.
It's so simple it's not actually a good example.
But the point I want to make is that it's not as simple as like, okay, well, I have this dynamic that works really well, and that gets to the minimum.
And I know that it's going to get to the minimum this fast.
And so geometric integration will give me an algorithm that I can implement on my computer, and that's going to get to the minimum this fast as well.

1:41:48 It's not as simple as this.
Geometric integration works by preserving geometric structures in the dynamic that you started with.
So in order to be able to apply geometric integration, to have algorithms that work for optimization, you need to design a dynamical system that converges to the minimum and that has some important geometric features that can be preserved in this way.
And so this is basically the goal of the whole section, and it goes into the following steps.
So one thing that can be discretized or implemented on a computer in a way that is close to the true dynamical system is what's called Hamiltonian flows.

1:42:45 So if you specify a Hamiltonian, which is a kinetic energy and potential energy, then you get the Hamilton Jacobi equations of motion that gives you the behavior of the system that has the prescribed Hamiltonian.
So for those who've taken a course in physics, you probably know or may have seen that all of Newtonian mechanics can be reformulated as Hamiltonian mechanics.
So all of that can be described as with Newton, lows of motion can be described through Hamiltonian mechanics.
It's a very general framework or a very general way to look at physics, because it's such a general point of view on physics and such a, and just Hamiltonians, they come up everywhere, this mixture of kinetic and potential energy, to concisely summarize the behavior of a system.

1:43:46 Because they occur so much, they have been studied extensively, and it turns out that Hamiltonians and specifically the motion they entail.

1:43:55 So the Hamilton Jacobi equations of motion, they can be discretized or implemented accurately on a computer using Symplectic integration, which is a part of geometric integration.
So in short, you can use Symplectic integration to accurately simulate a Hamiltonian dynamical system.
Now, the problem is, these dynamics are conservative, so they preserve the Hamiltonian.
So if you're at some point hidden states, space with a certain kinetic energy, potential energy, and you run the dynamics forward, your overall energy is not going to change.
So that standard physics.

1:44:43 Energy is always conserved when there's no friction, all kind of like ideal physical systems with no friction, the energy is conserved.
So when you're going to run this Symplectic optimization scheme to simulate these Hamilton and Jacobi equations of motion, the energy is going to be conserved.
Now, we're in trouble if we want to do optimization, because in optimization, if you think of the function as the energy, you want to dissipate energy as much as possible to reach the minimum.
So you want to lose energy.
So what the section does so this section, by the Way, is a review of more technical papers what these papers do, it's a very clever trick is they say, okay, well, we want to minimize a function.

1:45:36 We're going to say the function is potential energy and also we're going to add a kinetic energy on top of that to get a Hamiltonian.

1:45:46 Now this Hamiltonian, we could simulate it through symplectic integration, but actually, if we did, we wouldn't dissipate the function.
So now what the section does is it introduces a higher dimensional state space with the Hamiltonian that if you simulate those dynamics, it actually optimizes the function.

1:46:19 So this is what was a convoluted way to say it reformulates optimization as a conservative system with a different Hamiltonian.
And so by and because we know how to simulate dynamics with Hamiltonian so well, a good way of doing optimization is by finding a Hamiltonian so that when you discretize it, you get the optimization process that you wanted.
If you do that, you get a numerical method that's stable, that works well, that has good coherence guarantees.
And it turns out the numerical methods that are developed, they work for optimization on any kind of smooth manifold, for function, on any smooth functions, on any smooth manifold.
They work well.

1:47:03 They are generalized gradient descent in the sense that you recover gradient descent in a certain limit.
And they can be seen as accelerated because they have this notion of acceleration in the sense that, let's say the function that you want to optimize, it like a hill and you want to go down.
If you just did great, in the sense you're like blindingly going down at the same speed, or your speed is like proportional to the slope of the landscape.
But when you actually let a Bull rolling down, this is not really what happens.
The Bull is going to roll faster and faster and it's going to accelerate, it's going to go down, it's going to overshoot the minimum and then it's going to like oscillate until it converges to a minimum.

1:47:52 So these are the kind of optimization methods that are developed here.
They're optimization methods that are accelerated in a physical sense, that has physical sense acceleration and physical meaning because they're going to accelerate as they go down, overshoot and then stabilize.
So this is the whole point of this section.
Now briefly, because I think we're running out of time, but we can of course, revisit these sections later.

1:48:25 In the third action.
We have sampling.
So we talked extensively about sampling.
The sampling, as we discussed, can be seen as an optimization of probability distributions.
So we have the distribution that we want to sample from, and we just run a process that is random so it can be described by its own distribution and want the process to concept as fast as possible to the target.

1:48:53 So we want that distribution of the process to concept as fast as possible to the target distinctions.
So in a way that can be seen as I guess complicated for many people.
I think it's pretty abstract.
But it's been known for a long time that you can reformulate sampling as just optimization of distributions.
Now it turns out that when you use the accelerated optimization method of the second section to sampling so when you use, when you do accelerated optimization on the space of probability distributions in order to solve the sampling problem, you get a process that's called under damp launch one dynamics.

1:49:49 So if you solve that process, you're basically going to get good samples, very good samples of your target distribution because that process can be seen as doing an accelerated optimization on the space of probability distributions.
In other words, the distribution describing the process is going to accelerate towards the target.
So you're going to get there very fast and your symbols are going to be very good.
So this is 2.6 where this is kind of derived.
In 3.1, we basically talk about the the good properties of samplers in general.

1:50:33 So sampling is not like a complete field, but there's a lot of work showing that certain processes have certain characteristics of processes make them better samplers and others make them worse.
So this is what we discuss.
And then in free .2, we put this all together in Hamiltonian Monte Carlo, which is a state of the art method for sampling.

1:51:03 Hamiltonian Monte Carlo is a way of using, if you use symplectic integration under Downplantromodynamics, which is your accelerated sampling method, that you cannot stimulate directly, again, you get the same problem.
If you use symplectic integration to simulate that, then you get HamiltonI Monte Carlo.
So Hamiltonian Monte Carlo is attributes Google way of doing accelerated sampling that's based on ideas of symplectic integration.

1:51:35 Now, very briefly, the section four is on inference.
The inference in its most general form is variational inference.
So what we typically do know and love from active inference.
And I have a target probability distribution that I'm not able to compute directly.
So I'm going to approximate it as best as I can.

1:52:04 Now, these distributions, they're often used to compute expectations, or in other words, in statistics and machine learning, we often need to compute expectations with respect to some probability distribution.
What this section does is it derives a whole bunch of divergences.
Like the Kel divergence.
I mean, the Kale divergence is not discussed so much in this action.
I'll explain why, but it derives a whole bunch of divergences that can be used to approximate this unknown distribution with some other distributions that are tractable.

1:52:55 So to put in a different way, you have this abstract variational inference problem where you have this target distribution and then you have this family of distribution that you know, and you want to select the distribution in your family that best approximates your target distribution.
Now, in order to do this, you first need to derive a measure of similarity between distributions to know, okay, well, what is the best distribution.
Like, how can you quantify being the best distribution, being the best approximation to your target distribution?
And to do that, you need to specify a emergence, like the KL divergence.
But the problem is, the KL divergence is not always practically applicable.

1:53:52 One example is when the target distribution is just given by samples.
So maybe you don't even know the target distribution.
Maybe it's a gaussian, but you don't know it.
You just have samples from the gaussian.
So you cannot just have, like, a histogram, and you need to best approximate the histogram with the distribution in some family.

1:54:13 So when you have a problem like this, which just happens all the time, you cannot use the KL divergence.
So you need to think about other divergences.
And so what this section does is deriving other classes of divergences that are more generally applicable than the KL divergence, and they have also some very nice properties and then showing, okay, well, how is it that I can minimize these divergences to solve a variation of inference problem?
So I think there's a lot of things to be done there in the sense that in active inference, we always use the Kale divergence to do variational inference and minimize free energy.
And this Kale divergence is available because we typically have adjuncted models that are nice and they're expressed graphical models.

1:55:13 But there's this whole other plethora of divergences and algorithms to minimize the divergences that's out there.
And it could be the case that there's very interesting recipes and methods that can be either brought back to the KL case that we use or just used altogether in our setting.
In particular, when, for example, let's say they wanted to approximate the expected free energy in active coherence, the expected free energy is an expectation and want to approximate that expectation.
It could be the case.
Well, I think these methods that are summarizing section four could be very useful because they basically develop divergences that quantify how far the expectations are going to be if you choose a different distribution.

1:56:10 So it's all like, very natural in that computational sense.
And then finally ant activation through active coherence.
Well, I think we've discussed that already extensively, but I won't spoil it more today and we can come back to it next time.

1:56:35 _Daniel:_

Thanks a lot for that overview.
That was very powerful.
Incredible dot one very informative.
Looking forward to starting with some questions from the live chaos and people's comments on the video between now and next week.
If anybody else of your colleagues or anyone in the institute wants to join, we'll be here next week for 52.2.

1:57:04 So thank you, Lance, for the time.
Really appreciate it.

1:57:08 _Lance:_

Thanks, Daniel.

1:57:10 _Daniel:_

Farewell.

1:57:12 _Lance:_

See you next week.

1:57:13 Bye.
