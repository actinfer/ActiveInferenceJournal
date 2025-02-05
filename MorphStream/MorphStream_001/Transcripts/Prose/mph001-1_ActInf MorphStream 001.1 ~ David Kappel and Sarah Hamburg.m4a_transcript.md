
00:06 _Daniel:_
Hello, everybody.
Welcome.
It is September 26, 2023.
We are here kicking off a new stream series at the Active Inference Institute.
This is the morph.
Stream 1.1.
Today we have David Cappell and also this section and streams facilitated by Sarah Ham.
We're going to have a overview, first presented by Sarah.
Then David will share some work on neuromorphic computing, and then we'll have some time to discuss.
So thank you both for joining and Sarah, to you for the first presentation and also to introduce yourself, if you'd like.

00:49 _Sarah:_
Yes, that's a good idea.
Thank you very much, Daniel.
So my name is Sarah.
I'm a neuroscientist specializing intelligence, currently working in the field of neuromorphic computing at Sheffield Hallam in the UK.
So I'm going to give you a high level overview of what neuromorphic computing is before we hear David's exciting talk in the first edition of this new series.
Just to let you know, if you're watching on Double Time in the future, I talk quite fast, so you might not want to watch me on Double Time.
So this QR code I put here will take you to a paper which I thought was a really nice introduction to the field.
But neuromorphic computing can be defined as computing systems that are designed to mimic the structure and function of the nervous system.
So this doesn't have to be the human nervous system.
The field actually takes inspiration from all sorts of animals and insects, although the definitions online don't necessarily acknowledge that.
So some people are quite open with what constitutes neuromorphic, while maybe others would prefer neuromorphic was reserved for hardware instantiations of biological like neurons, which are sometimes referred to as non von Newman computers.
01:53 And I think that's what the paper that that QR code refers to it as their definition.
So what I think is really interesting is a little bit of the context.
So, like our current von Newman computer architecture was also inspired by neuroscience, particularly the McCullough and Pitts 43.
Neuromodel inspired von Newman's first draft in 1945.
So neuroscience has a long history of inspiring computer science, and this also includes reinforcement learning, which is based on theories about learning, decision making from behavioral psychology based on rewards and punishments, and also Hebian learning principles of cells that fire together, wire together from 49 became foundational for unsupervised learning.
So, first of all, hang on 1 second.
So in order to understand the why of neuromorphic computing, I really wanted to explain what's so great about the brain.
So here's some inspiration for light bulbs.
So I'm going to ask you a question.
I just want you to think about it for a second.
In terms of light bulbs, how much energy do you think the brain uses?
Do you think it's more or less energy than the bulbs lighting the room that you're in?
02:57 If you're in the future, by all means pause this.
Pause this.
If you want to do some in depth calculations.
But I'm going to skip to the answer.
The answer is here, in the pink circle.
So it's 20 watts.
So that's the equivalent of one modern day energy efficient light bulb.
So that's probably what's above me now, basically in my room here.
This QR code should take you to quite an interesting paper on power consumption in the brain, if you're interested in that.
So that works out about four bananas a day to power your brain.
And this is calculated, by the way, based on calorie intake that the brain needs.
So, for context, the fastest supercomputer in Europe, I think it's called lumi, in Finland it's been called exceptionally green, and its power consumption is 8.5 million watts.
So that's around half a million light bulbs, while your brain uses just one.
So then the question is, well, what does your brain do with that one light bulb or four bananas?
Apparently it does 1000 billion calculations per second.
03:59 So there's lots of other massive estimates out there.
This wasn't even the largest by several orders of magnitude.
Estimates are obviously very speculative, but they're all massive and they all tend to be based on the number of neurons, their connections and firing rates.
But I think it's really important for the context that supercomputers can't actually yet match our complexity of skills or the adaptability of the human brain.
So we actually excel way beyond supercomputers when it comes to things like complex decision making, learning from experience.
So how does your brain compare to AI?
So, I mentioned that modern AI is already brain inspired.
However, artificial neurons are highly simplified.
They don't capture the complexity of biological neurons or networks, like, not even close.
Individual neurons are actually more like networks themselves.
And research suggests that modeling one biological neuron requires a five to eight layer deep artificial neural network made of around 1000 artificial neurons.
This QR code should take you to the paper.
05:00 For that.
You have 86 billion neurons in your brain.
They work together to form a highly energy efficient, low latency supercomputer that works just above room temperature, off the equivalent of about four bananas a day.
So hopefully I've given you a sense of how amazing your brain is, as if you didn't know that already, and how it's already been used to inspire the, I guess, fairly basic AI that we have now compared to human intelligence.
So, next I'm going to explain how key features of the brain are being implemented to catalyze our next generation of AI and technology through the field of neuromorphic computing, which is why you're all here.
So, traditional volume and computers have physically separate computing and memory units, shown here on the left.
During computation, data must transfer backwards and forwards, like really fast.
So there's a bottleneck, essentially for speed and energy, whereas in neuromorphic architectures, which are shown here on the right, with the help of Dali, computing and memory occur in the same place.
So they're said to be colocated.
06:02 Essentially, individual neurons perform computation while memory is represented by the strength of the connections, the weights between neurons.
So the synapses.
So chips like this might be created with components like Memoristas for example, which can emulate synaptic weights.
And this architecture improves speed, it reduces energy consumption.
And what's really interesting is it enables massively parallel processing meaning that multiple problems can be worked on at the same time.
So this is particularly important, this architecture, for various use cases, but also because as we reach the end of Moore's Law, which is the number of transistors you were able to physically make tinier and tinier to fit on a chip.
And it's also important because humanity needs to massively reduce its energy consumption against the backdrop drop of creating ever more powerful AI.
So artificial neurons typically use continuous activation shown on the left, they're always on, while neuromorphic neurons, they're said to be spiking, so they're on or they're off, which is shown here on the right.
07:07 So similar to sort of an action potential.
So the benefits for this are again power, efficiency and also applications where timing is important and this is given that they're event driven.
So essentially they have the potential for spatial and temporal dimensions which then enables added spatiotemporal encoding and processing of information.
You might be wondering a bit about GPUs which also enable parallel processing.
Research suggests that GPUs are suitable architectures for deploying spiking neural networks which I think makes this a really interesting time for the field given how high end GPUs are becoming ever more pervasive.
So the brain learns strength of synapses between neurons.
This is based on pre and synaptic firing patterns.
I think David's Talk will talk a lot, we'll go into a lot more depth on this.
But there are many different types and patterns of this across the brain depending on the types of synapses such as excitatory to inhibitory, excitatory to excalitatory.
08:07 And the neuromorphic field is working to leverage these rules because of benefits for on chip learning and also applications such as pattern recognition and edge computing as well.
Edge computing being quite a huge use case for neuromorphic computing because of the sort of event driven nature and also the low energy usage.
And this QR code should take you to quite an interesting paper on STDP that I found.
So what neuromorphic solutions are available?
Now?
You might just think this is all theoretical, there are actually many different solutions out there which I'll just give you a really high level overview of.
So the Human Brain Project has created several large scale neuromorphic computers including Spinnaker, which is this one at the bottom, this board's, like maybe like the size of my face or something.
So that runs in real time and it's comprised of multiple general purpose arm microprocessors and there was also BrainScaleS which is an accelerated analog architecture and it runs 1000 times real time.
So the board next to the blue one, that's an actual credit card size version of BrainScaleS, which they've recently made, which I thought was pretty cool.
09:16 And then there's also some big players in the space.
So this blue one here is Intel's Louihi chip.
They're onto Luihi two.
Now, that's their Neuromorphic chip, and they have an open source software framework for that as well, because they really want to catalyze the open source community to get involved with it.
So neuromorphic sensors also exist?
So this little blue thing in the middle is actually a Neuromorphic camera.
It's maybe like this big.
So they aim to recreate how our nervous system senses stimuli, such as light.
So, for example, in a Neuromorphic camera, which is the one here, each pixel works independently with a microsecond resolution.
Hopefully, my GIF will work.
There we go.
So you can see each pixel working there, which is pretty cool.
So compared to traditional digital cameras, they have improved performance with motion and lower power consumption.
There was also a Neuromorphic nose recently by intel, which was pretty cool.
So it could learn the scent of a chemical after just one exposure, and then it could identify that scent even when it was masked by others.
And then finally, this is a humanoid robot called an ICup.
10:17 And what you can do is you can actually integrate Neuromorphic sensors, such as the camera, and then Neuromorphic chips maybe spinnaker or brain scales into a humanoid device like this or other devices like a drone.
And then from that, you can actually create embodied neuromorphic systems.
And this is something that we work on at the Smart Interactive Technologies Research Lab in Sheffield in the UK.
This slide just highlights some of the potential applications of Neuromorphic computing, which I thought were quite interesting when you think about it.
So the understanding of context, pattern recognition, advanced sensing, fusot, learning, generalizing across tasks, complex decision making, explainability, and brain interfaces.
So all these skills are really beneficial when you're thinking about human centered, real time applications in dynamic environments.
So things like self driving cars, for example.
And personally, I think that neuromorphic systems are also likely to be the future substrate of brain computer interfaces.
Probably a bit biased because I'm a neuroscientist, but they're low energy, they're real time, and they also have architectures which match our own hardware.
11:24 So I do think we'll soon see the BCI field being catalyzed by neuromorphic systems, particularly maybe for hybrids of hardware and wetware.
So maybe even potentially containing people's own brain cells, which you can actually grow just from a hair cell.
And a particular focus of our work is designing AI, which learns in a similar way to a human.
So it has an innate sense of curiosity, and it learns through interacting with the real world.
So in the 50s, Alan Turing said, instead of trying to produce a program to simulate the adult mind, why not rather try to produce one which simulates the child's brain.
If this were then subject to an appropriate course of education, one would obtain the adult brain.
This is very much the philosophy behind the neurodevelopmental approach to AI and neuromorphic computing, which I just wanted to highlight.
There are some challenges in the field.
These are very high level, but I'll just give you a little bit of an idea of it.
So, training spiking neural networks is more complex than traditional neural networks.
12:26 Also designing hardware which actually implements spiking neural networks STDP on a large scale is said to be fairly challenging.
And then also developing algorithms which can actually effectively leverage all these technologies.
So the hardware, the STDP, it's an ongoing active area of research.
So if you're here, you're probably interested in active inference.
So I wanted to highlight this.
Actually, someone put on the discord today one of these studies, which was pretty cool.
So a couple of recent studies have combined neuromorphic computing with principles of active inference.
So active inference comes from neuroscience, and I would argue that it lends itself very well to neuromorphic architectures.
In a recent paper on embodied neuromorphic intelligence, so it didn't really mention active inference in it.
The QR code on the top right here, it was suggested that a real breakthrough in neuromorphics will happen if the whole system design is based on biological computational principles with a tight interplay between the estimation of the surroundings and the robot's own state and decision making, planning and action.
13:30 So some of those themes might sound quite familiar to people interested in active inference, and I would suggest that active inference is well placed to meet these requirements.
And I just wanted to highlight a couple of recent studies here.
So this one on the left, Gandalfiatal, recently demonstrated plasticity and rapid unsupervised learning in a neuromorphic system using active inference principles.
The author suggested that their experiments could be adopted to implement brain like predictive capabilities in neuromorphic robotic systems.
And then there was the Dish brain paper, which some of you may be familiar with by Kaganatal.
So this was a hybrid wetware hardware neuromorphic system that the authors claimed was embodied.
The system showed rapid apparent learning of the game of Pong using the free energy principle for learning.
And the authors claimed that the system exhibited synthetic biological intelligence.
So the field implementing active inference principles in neuromorphic systems is very nascent.
And the idea behind this more stream series is to create a space and a community to share knowledge, ideas and expertise to catalyze the field.
14:37 I think some really exciting technological leaps are probably going to come from this area.
So thank you for listening to my quick run through Neuromorphic 101.
And next up, we're going to hear from David.
So David, over to you.
If you want to introduce yourself, please.

14:55 _David:_
Thank you, Sarah.
I would share my screen.
Yeah.
Can you see now my screen, the presentation yeah.
Okay, perfect.
Okay.
Hello.
My name is David Kappel.
I'm a researcher and group leader at the Institute for Moyo Informatics at the Rural University Bohom.
So I'm leading the group on sustainable machine learning and we have a very strong focus on neuromorphic computing.
That's why I'm here today.
And I'm going to start with a very similar motivation than Sarah did, which was really a great inspiration for this talk, I think.
So probably most of you have seen this interesting recent result, and I don't mean Germany winning the basketball championship, but this really big leap in artificial intelligence that we have seen in the last years, especially the last two or three years.
16:08 So this is a picture generated from a prompt by a Dali network and it's really amazing.
It was considered science fiction like only two, three years ago.
And this was essentially made possible by a neuromorphic approach, which is deep neural networks.
And these deep neural networks have become huge now, but this comes also with a caveat.
So basically the flip side is that among other problems maybe these models may have, they consume huge amounts of energy.
So models like Dali or Jet GPT, as Sarah already mentioned, they would consume energy budgets that are comparable to houses or cars.
So training Chat GPT a single time is like a gigawatt hour approximately.
So that would be 300 tons of CO2 emission and many times, which comes down to many times the lifespan of a typical car.
17:12 So this comes with two problems.
Obviously, this makes training these models only accessible to a very small number of very large players.
So essentially the big tech companies.
And secondly, and maybe even more importantly, this is not compatible with a planet with limited resources.
So if the growth rate of AI continues like it did in the last years, it will consume 13% of the global energy consumption by 2030 and it will basically outrun the transportation sector in another five years or so.
So this raises the question, does sustainable machine learning exist at all?
And obviously, since I'm working in the group of sustainable machine learning, I believe it does.
And why I think it does is because we know a system that is very efficient and is still probably better than these AI models, which is the human brain, which consumes, as Sarah mentioned, around 20 watts or four bananas a day.
18:20 It's many orders of magnitude more efficient than the AI models we have today.
But so far we don't know essentially how these networks work and especially how to train them.
And basically our goal is to transfer now mechanisms from machine learning.
We have this nice picture here.
Basically we start from the machine learning side where we already know our way around.
So we have these models that are wonderful and that give us really impressive results, but they are not efficient and we want to transfer them to a new efficient AI generation.
And our idea is to use inspiration from neuroscience that make this transfer faster and possible in the first place.
Okay?
Actually, biology is a great source of inspiration and always comes around the corner with very surprising results.
19:22 And one of these results that I stumbled upon a couple of years ago is that reliability of synapses in the brain.
So, as you probably know, neurons in your brain are connected for synapses.
But if you look at this is a paper from 2019, and they could actually identify individual synapses and they could trigger them to make a synaptic release, like a single transmission.
But if you look at these measurements, you see that this is really covered in noise.
So essentially, if you basically average over this and zoom this out, you see here these typical synaptic traces, which is the average white line here.
But below that, you see this huge jitter.
So they really like go several standard deviations up and down.
And this is actually very surprising given that neurons are probably the single most costly cell type in your body in terms of energy consumption.
20:26 They are really in comparison, they consume quite a bit of energy in your body.
So you would expect that these transmissions that are communicated between neurons, which are very costly, should be highly reliable.
So this is very counterintuitive these results and has been puzzling neuroscientists for quite a while now.
And then there is a second puzzling observation, which is that the morphology of neurons looks somewhat like this.
So this would be your typical pyramidal neuron you have in your cortex.
But you see that this is actually, for a cell, quite big and elongated.
So this can be up to a millimeter in the human brain, which means that if a synapse fires somewhere here, it has a very hard time communicating with the cell body, which is down here.
21:27 So the electrical signals that are produced here may travel down here, but the synapse up here has no way of measuring the actual voltages at the cell body.
And this is actually the interesting place because here are the action potentials formed.
So if the synapse would really like to know about what is going on in the cell body so that it can make predictions about how the neuron will behave and how it interacts with the world.
And this is another very puzzling or open problem in neuroscience, how this communication actually works out in single neurons between the cell body and the SynOps.
It is known that actually the action potentials can travel back up.
So they see kind of this binary variable when the neuron spikes, but they cannot actually measure the membrane potential down here.
So only the most prominent electrical signals can actually back propagate through this.
22:29 And this suggests that the synapse actually has very sparse information about what's going on in the cell body.
And most models of synaptic plasticity don't cover this at all.
And we were wondering how does this interaction work?
How can the synapse produce useful learning signals given this sparse information about this important state of the neuron?
And our idea was that essentially these two observations, these high levels of noise and the synapse and this large distance between cell body and synapses which give these high uncertainties, these are actually the two sides of the same coin.
So our hypothesis was that actually we could use the same models that we know already from the behavioral level, how an agent can act and perform in an environment of high uncertainty.
23:31 And we just apply this to every sign ups and there is an error.
So every sign up should utilize these same models, basically.
And this model would immediately suggest that actually synaptic transmissions should be noisy and these levels of noise would express uncertainty about the environment.
And then we can use this model to derive learning rules and we can compare them side by side to biology.
And this is the first thing I want to show you.
So I just give a very quick introduction to the free energy model, because some of you might not be that familiar with it, but this is essentially a model to describe a situation like this.
You have a person that is interacting with some environment and here I assumed very simple.
So this person tries to throw a ball to some target.
And we as humans, we are good in solving such tasks.
24:34 And we are also good in solving such tasks if there is high levels of uncertainty in this.
So if the person may receive some visual feedback, but a lot of this feedback may be hidden.
So you can imagine this going on behind some wall.
And the person now still might want to predict what is the trajectory of this ball flying towards the target so that it can make an accurate action.
So we will assign some variables to these states here.
So we have essentially this feedback that this person can observe.
And we have this unobserved state of the ball flying here, which we call U, where the person doesn't have direct access to it, would only see parts of it, for example, when the ball is at the corners of the ball appearing.
And then to model this essentially, or to describe this behavior, the person would have an internal description of this trajectory.
So an internal model of this state, U.
25:38 And this model would then be updated to match the observed feedback.
And this can be described very nicely in this beautiful mathematical framework of the free energy principle.
So the idea is that you would essentially establish a model of your internal state, so essentially how the internal states and the state of the environment interact.
And you would have a model of the feedback, so how the states and the feedback you observe interact.
And essentially you can then write down a loss function that measures the distance between this model of the internal state and this model of the feedback and the external state.
And then by essentially minimizing this distance between the two, you can derive all sorts of behaviorally relevant, can solve behaviorally relevant problems, for example, learning.
26:46 But you can also use this for other things, like figuring out what are good actions, for example.
So making inference about both the internal states and the actions.
For example, and this is in a nutshell, the free energy principle.
And this object here happens to be what is known as the variation of free energy, which is also just coincides with statistical physics.
And this is where this framework has its name from.
But you see that all is probabilistic here.
So essentially you have two probability functions q for the internal model and P for this interaction between states and observations.
And you have here a distance measure between them that you want to minimize.
So now if we look at the neuron and the synapse and how they interact with each other, we find a very similar picture.
So single SynOps, which we have here in green, has an internal state which we, for simplicity, model only as the synaptic weight.
Based on this, the SynOps, when it's triggered by a presynaptic spike, it would generate a post synaptic current.
27:52 This would then propagate to the soma, which is our external state, which we cannot directly observe because it's too far away from the synapse.
But we can see a feedback, which is this back propagating action potential, which is this binary variable that tells us whether the neuron has spiked or not.
So this is exactly the same framework if we write it down like that.
And we can just use the same mathematics to solve it.
So to solve it, we only have to come up with a couple of we have to make a couple of assumptions.
So we have to write down a model for this guy here.
So this model of how the feedback and the external state interact.
But we have very good models for this.
This has been studied over many years.
So here you see how typically a model neuron behaves.
So you have here the membrane potential of a leaky integrated fire neuron.
And you see that this is just going up and down.
So this neuron would receive a lot of presynaptic input and maybe also noise.
28:56 And eventually at some point it hits a threshold, it would generate a spike.
So that would be the sets that travels to the downstream neurons and also back to the SynOps.
And then it resets, right?
So we can write this down mathematically as a very simple differential equation.
But the neuron doesn't have access to this state again.
So it's again behind this wall, it only sees these spike events.
But we can actually, for this simple case of a leaky integrated fire neuron, we can solve this analytically.
So we can write down what is the posterior distribution of membrane potentials given the spike times.
And what comes out of this is actually a so called stochastic bridge model, or in this case of a leak integrated in fire neuron.
It's an orange bridge model.
So this can be written down analytically.
It's not simple, but it's doable.
And we can then just use this directly.
29:57 So this model that we have to again write down these free energy functionals.
So we make here an assumption how the synapse actually produces post synoptic currents and how they are integrated in the neuron.
But that's also given by the leaky integrated fire neuron and actually the stochastic inputs that the synapse generates.
So for simplicity, we only assume here basically Gaussian synapses that would inject draw a Gaussian random variable and inject this to a leaky integrated fire neuron.
And then all these ingredients actually can be solved in closed form and we can derive learning rules that would minimize this free energy functional.
Now, and if we do that, this has a bunch of nice properties because this Einstein Beck bridge is completely determined by the back propagating action potentials.
So basically the times of the post synaptic spikes that arrive at the neuron, this shape that we get here only depends on two neighboring post synaptic spikes, which means that we get here automatically a learning rule that looks like this.
31:11 So a learning rule that only depends on the difference between two postal optic spikes, which we call here delta t two, and the difference between the post synoptic spike and the actual input that is triggered at some point on the presynaptic side.
And we can basically make here this lookup table and just compute what would be the update that these sign ups would need to make so that it learns optimally in terms of this free energy principle.
And this is the shape that we get out.
You see that there is a strong dependence on the post synoptic firing rate, but there is also a dependence on basically this typical STDP that Sarah mentioned before, what is the relative positioning of the pre and postsynoptic spike.
So in a nutshell, this model can now be split into essentially two pathways.
So we have this ATOC response, which basically just whenever there is a presynaptic spike that triggers an action in the synapse, we would draw from this Gaussian distribution and inject it into the neuron.
32:20 And then there is this postalk update where the synapse would look up in this onstain Woolenbeck bridge, what would have been the optimal output that it should have generated, so what would have been the optimal action.
And then it compares the actual action with this optimal action according to this free energy principle and then generates a delayed response which is an update of the synaptic weight.
Okay?
And importantly, this internal model is only implicit.
It's encoded, so to say, into this spike time dependent.
Plasticity rule.
So how do these rules then look and how do they compare to biology?
And actually the fit is quite nicely given that this is derived really from first principles without making any assumptions.
So this is the measurement in biology.
This is this B and Al rule, b and Pool, very old work where they actually did this in vitro studies where they injected pre and post synaptic spikes and then they measured what is the weight change in the synopsis.
33:32 And this is the rule that is predicted by our model.
And you see that at least in a first order approximation, it gives us very similar shapes.
And this also makes sense because the synapse wants to change the most when it's close to the pre and post synoptic spike times because this is where or the post synoptic spike times because this is where it knows the most about the state of the postynaptic neuron.
The free energy principle would actually suggest these kind of cones with almost no assumption essentially.
But we also get because we have not just the first order spike time dependent plasticity rule, but we also have this dependency on the post not of the firing rate.
We can also compare this to other results.
And this here is this old work by Kaupner and Brunel.
So this is actually a model, but that was very detailed describing the plasticity based on the pre and post synoptic firing rate in the synapse.
34:41 And this is what our model predicts.
So if we inject render and pre and post synaptic bossBack trains with different rates, our model would predict this shape, which again is not a perfect match.
But given that this is a very idealistic model, it's actually the main features that low firing rates on the postynopstic side would lead to depression and higher to potentiation are reflected in this.
Okay, I assume I still have ten minutes, right?
Okay, so I would give a quick intermediate summary and then I want to show some other work where we actually apply this now to actual machine learning model.
So what we have seen here is that synapses are actually are very stochastic and this was a big puzzle.
And B suggests that actually the synaptic noise is actually the synapses way of reporting its own uncertainty about the environment, where the environment is actually the post synaptic neuron and it really interacts in this fashion of the free energy principle with this post synaptic neuron or that's a very nice way of describing it.
36:05 And if you're interested more, there's a paper, a preprint out, you can read up on all this.
Okay, so how does this now connect to neuromorphics?
And actually so we are not actually doing neuromorphic hardware, we are doing neuromorphic algorithms.
So we try to bring these inspirations now into actual machine learning models and we thought that this might be a good attack angle to solve a problem that is well known in machine learning.
So I just drew here very simple convolutional neural networks with various convolutional layers and then maybe some dense layers that you would have in your machine learning algorithm.
And the way this is trained, as many of you know, I guess, is through end to end errorback propagation.
So the idea is that you have a training set which has inputs and targets.
So, for example, in a classification task, this could be pictures of cats and dogs.
37:08 And you would have targets which are class labels, so to say.
So there's actually artificial neurons in there, and one of these neuron may be active for cats and 1 may be active for dogs.
And in your training, that data, you have exactly these labels that were generated by humans, that were sitting down doing this by hand.
And then during training, you show these examples to the network by propagating these inputs all the way from the input layer to the output layer.
Then the output is here compared to these hand labeled targets.
And then the mismatch between the two is back propagated through all these layers back to the input.
And all the weights or the synoptic weights that are here in between inside these layers would then be updated accordingly, so that after doing this many, many times, this network becomes good in telling apart Kelvin docs.
So this has a problem, this algorithm.
38:09 It works great in practice and it's the foundation of all these models we have talked about, like Dali or Jet GPT, but it is quite inefficient.
And the problem is what is known in the literature as the locking problem.
So if you would split up this network now into blocks, which I already did before, but this is arbitrary, but for implementing this efficiently in terms of a software algorithm, it might be interesting to do that.
And now you would want these blocks ideally to run in parallel, so that you can basically show the first example on this first block and then already train it while the second block is doing something else.
But this is not really possible with end to end back propagation because of this lock in problem, because the activation of the second block depends on the activation of the first block.
So you have to propagate it all the way to the end.
Then you compute this error and you would then back propagate.
And only when this is done, you can start the next epoch where you show a new bunch of examples and you see that during all this time, here, the thread that would run this first block maybe would be idle and has to wait essentially all the time.
39:26 And this obviously makes them very inefficient.
And now our idea was that we use basically what we had learned from this earlier model on how synopsis communicate over these long distances through this free energy principle, and also apply it just to a deep neural network.
And the idea is that you have here, again, basically you have already this generation of inputs to some output.
But what is missing to make it applicable to the free energy principle is this feedback that you always need.
The idea was that we put here a very lightweight feedback network.
So essentially each of these blocks now in this deep neural network would be accompanied by a feedback block that locally generates a target.
So we used here really in the simplest case, which we have, so this is very recent work, we only used linear blocks so far.
So these are single linear layers and we would generate now these outputs here in these feedback blocks and then use the free energy principle to derive a local loss.
40:37 That allows us again to minimize both these feedback weights that we have here and also the weights in the forward network.
So it's essentially the same idea.
So we have here these outputs which we interpret now as parameters to a probability function.
So we can apply this probabilistic framework, but now all the rest basically rolls out the same way.
So we assume that these outputs are essentially the internal states of this model and we have these observations given in the inputs and the targets.
And now we try to minimize basically P would now be this feed forward network and Q would be now a function that contains features of both the feedback and the feed forward network.
And the nice thing is that if we I don't have time to go into the details now, but if you write this out, you see that this actually decomposes, this lock term here decomposes into local linear terms that give you these local losses here.
41:50 So essentially that you can minimize here block local between forward and the corresponding feedback block, a loss function.
And you can then actually do this in parallel because maybe the picture is good to see here.
So what you have to do now you have a bit of overhead because you have this feedback block.
So this would be the two execution times of the feed forward block and the feedback block.
But in principle they can run in parallel and once the forward block is done, the next forward block can start propagating through this network, but simultaneously already the forward block, because it already received a target here, can start updating the weights and when it's done, it's free to operate on the next epoch.
So there is no locking anymore in this framework.
Okay, so I'm pretty much done.
42:50 I'm also out of time, I think.
So how does this perform?
Of course we changed the learning algorithm.
Now we have to also go back and see if this is still giving us the same performance.
As I said, this is the first results we have here now and at least to mid scale data sets like cipher ten or so, this seems to actually perform very well.
So we attract it for standard architectures, fashion MNIST with ResNet 15 and ResNet 18.
We worked mostly so far for small data sets like Fashion MNIST with applying free splits to ResNet 50.
We get basically the same performance as standard backprop.
As networks get deeper, you see that our problem that we have now is actually overfitting because we have these local targets.
It seems that these smaller blocks actually overfit to some extent.
43:52 This is not so severe for still up to tasks like cipher ten.
So we get quite close already.
But if you go now for really large tasks, there's still something missing for like single splits.
We are getting there, but we are not reaching all the way up to back propagation.
But it's still interesting to see that you can apply this principle also to these standard machine learning algorithms.
Okay, this is my second summary.
So actually we found that deep neural networks are surprisingly good in generalizing over probability spaces.
This is how actually this work started.
And our idea was to exploit this and to utilize it to distribute learning in the same fashion as in the first project I showed you and to solve this credit assignment problem by generating these feedback networks.
44:53 Yeah, that's basically it.
And then I want to acknowledge my coworkers and my students.
So I have two very good PhD students, carlisle and Cabrill, who is now here in Bohom and works on this topic.
And the first project I showed was work I did together when I was in gettingham with Christian Tetlav.
And the second project is I worked closely with Christian Meyer and Anand Sutomoni and yeah, thank you.

45:31 _Sarah:_
Thank you very much, David.
That was absolutely fascinating.
I think it's incredible how closely the sort of model matched biology.
Like considering you derived it from first principles, I think that was really cool.
I did have a question just about the last sort of the bit.
You spoke about the Convolutional network and you said traditionally it has to go all the way end to end, which is really inefficient.
And then you showed the results that you got.
Did you look at energy consumption with yours as well?

45:59 _David:_
Not yet.
So we are actually currently working on it's actually not so easy to implement these things in standard machine learning toolboxes.
So Carlisle is currently looking into this, the PhD student in Jester, he has an implementation now, and he's now evaluating how well we can make use of this parallelization in practice.
But we are actually quite confident that for parallelizing it, it should be there.
The question is how much you save in terms of energy.
Because for these smaller scale models that we use now, ResNet 18, ResNet 50, the effect might be not that huge.
So once we ramp this up to really larger models, the effect should be bigger.
But yeah, this is ongoing work.

46:56 _Sarah:_
Very cool.
Thank you.
And then I was just wondering as well, this local error back propagation, is that something that other people have tried with these convolutional neural networks or is this quite a new way of implementing it?

47:10 _David:_
There is a bunch of approaches that do this.
For example, I mean, the closest I guess is target propagation which has been proposed, which essentially uses random feedback weights to back propagate here.
So these guys would not be trained.
And this works nicely also for small scale problems.
But as far as I know, they don't perform that well.
Even for cipher ten, it already starts breaking down because these random feedback weights are just too coarse an approximation, I think.
And this is the first okay, maybe I have to be careful.
I think this is the first method that allows you to train these feedback weights.
That is not a contrastive method.
There is a bunch of methods that use a contrastive step.
So you have maybe seen this forward forward algorithm and all these things, but what they have to do always is they send in the actual input data and then they send an kind of anti input, an anti input that is usually generated artificially.
48:28 So they do some distortion to the input to make it and then they have to use both information locally to do the update.
So the network has to keep in memory the input and the anti input and the responses.
And this makes these approaches a bit harder to parallelize in this.
And the nice thing here is that we derive an upper bound to this variational free energy loss that can be spelled out completely by forward propagation.
And that I think is new.
So that is the new bit of this.

49:08 _Sarah:_
Very cool.

49:12 _Daniel:_
That's awesome.
Well, yeah, few comments, one piece that kind of between the two of your talks.
That was at least a new distinction to me, which was the difference between the Neuromorphic hardware and the Neuromorphic algorithms.
So it's not just about new hardware or Wetware, though that would be great to see.
It's almost like there's this intermediate or a bridge step with using the algorithms on the hardware we have today that like Sarah mentioned, the Spiking neural networks which are amenable to GPUs or just using standardized CPU multicore scheduling approaches.
You can already do more with what we have using the Neuromorphic algorithms.
50:13 So it's not just a material science topic, but also there's a lot at the really micro scale that we can learn related to noise processing scheduling and then also even at higher levels of abstraction, probably learning from biomimicry and cognitive systems more generally.
But that was a distinction for me.

50:38 _David:_
Yeah.
So maybe to add yeah.
So I think that the problem becomes really now more pressing as these Neuromorphic devices become so the hardware devices become more mature and they usually cannot really shine on these standard machine learning algorithms because they are really optimized for GPUs.
So you need to think a little bit.
So you have to take one step back and think again about the algorithmic side to really use them to full capacity.
And as you have seen now, we collaborate with Professor Meyer, who is doing this spinnaker chip in Dresden, but there's also other approaches like the Louis chip that Sarah mentioned from intel and so on, and they are really looking into this.
Now, also from the algorithmic side.

51:32 _Sarah:_
I find it really useful.
It's kind of like a mindset or a mental framework when I'm thinking about computers or AI, and this is probably because I'm a neuroscientist, but I also have to translate it to, well, how does the brain work, how does the information processing work, et cetera, in the brain?
And when I came to sort of computer science and AI after neuroscience, I found myself naturally translating it.
But I feel like the framework is just a really useful way of understanding computation at the end of the day because our brains, as I said, are just these massive supercomputers.
And I'm constantly reading papers on computer science or whatever.
And then once you can conceptualize anything really as well, how neuromorphic is this?
And then if you start thinking about, well, how could you tweak it so it's slightly more neuromorphic?
And is that then going to give you these gains that we get with the brain?
Is it going to give you some extra parallel computation or is it going to give you some energy efficiency?
So, yeah, I find it the definitions when I was looking at the definition is I think it really depends who writes the definition.
And because it's such a dynamic area at the moment as well, I think it has been changing and it will be changing, but for me, I feel like neuromorphic is more of like a mental framework where I look at things through conceptualize, through yeah, I think it's.

52:44 _David:_
It'S also not very well defined.
You also mentioned that actually artificial neural networks are a neuromorphic concept, if you want, and they were from the first day.
And it's a big success story, right, if you look into the 90s or so when these support vector machines and these alternative models came up, but none of them have outlived the neuromorphic approaches.
So it's actually very nice.
But still there is this community that thinks that there is more features from the brain that you need to put in to get to the real thing.
So I think this is a bit of a it's not a very well defined term, actually, and I think with.

53:32 _Sarah:_
Your research, yours is almost like the smallest level that I've seen people look at it on.
I don't know if you've seen anything else, but we're not just talking about a cell level of free energy and active inference.
We're actually talking about a cell structure.
So then you think, well, how small does it go?
Are we going to talk about cell subcellular structures eventually, like Mitochondria using free energy in a similar way with compartments, I guess actually it'd be interesting to get your thoughts, david on, you talked at the start about how synapses are compartmentalized.
Do you see different sort of instantiations of this in different compartments just within one synapse, almost like are you wanting to sort of look at that granular level or is it more now taking what you've learned from this and putting it back into how can we sort of make the AI more efficient?

54:20 _David:_
Yeah, we are going much more in this direction now that we see how we can build this back into AI models.
One has to be a bit careful when using the free energy principle because it's such a powerful general framework that you can apply it to basically anything and it's not necessarily you will come up with a useful result in the end.
Just putting this this started actually as a side project.
This was my kind of COVID pandemic lockdown project.
And I was just curious about this and whether you can actually solve this, because I thought the synopsis is maybe simple enough.
Because when you go into the papers, they have at some point to go into some approximations.
They do some mean field, usually, so they go for first modes, and then you can solve these guys for more complex, even for neurons, it's hard, actually, if you go to the neuron or network level, it's hard.
55:30 It's very involved math, but for a sinus is simple enough, actually.
So you can actually do this and spell everything out if you make the right assumptions and really just derive these things.
And that was kind of just kind of a game I went into and then it turned out to work quite nicely, I think, in the end.

55:56 _Sarah:_
Yeah.

55:59 _David:_
I'm not sure if you like Mitochondria or so I'm sure you could apply the same principles but I'm not sure if the results you get would be any meaningful or would help you in any way.
That's always the risk.
You invest so much time and then in the end you get some results and you don't know.

56:21 _Daniel:_
That was also something that I thought was quite interesting, which was the synapse was the agent.
It's really easy to think, oh, we'll make an agent based model of a neural system.
First off, that tends to not include Glia or non neural cell types, but it's almost like a doubly unquestioned assumption that the cell would be the agent.
But then it was a great transition from the person throwing the ball over the wall.
That's an action centric approach where you only have partial visibility of the consequences and then that is the exact scenario that the synapse finds itself in in a different way.
Or it could have been set up so that a neuron is the agent.
We're building maps, not territories.
And so then, just like you said, free energy principle, it's a principle for everything.
And so just making principled statements about things is table stakes.
57:28 And then I guess my question for you is then what does make it useful or in your learning and tinkering around with these models?
What differentiated situations where you applied free energy principle or active inference and you felt like it was providing a contribution to your research direction versus where you played around and it was like, well, that was tautological.

57:51 _David:_
I think the free energy principle makes sense in a context where you have incomplete information.
So for example, in the synapse case, right, the question we started with was this problem that the synapse has to solve, that it has incomplete information about the state in the cell body because it only sees this kind of or that's the assumption, at least of the model.
And also what we get from the experimentalists, that it essentially only sees this back propagating action potential.
So it sees a single binary variable about the state of the soma.
So essentially this is a problem of incomplete information and also the second ingredient that you need some form of agency.
I think if you apply the free energy principle to a system without agency, so if something is not interacting with an environment in a closed loop, then it becomes really sketchy.
58:57 And I think already this model is on the edge when it comes because these models don't really have an agency, but they at least produce an output, right?
So you can still think of this as an interaction with an environment.
But as soon as you lose that, I think then there would be simpler models that can just give you the same.
Actually, in the synapse case, the agency is only this adding noise actually in the model because the synapse is triggered presynaptically and then it uses its internal state to add the right amount of noise, which is probably already the minimal agency you could imagine.

59:49 _Daniel:_
Sir, you want to ask a question or I can ask a question?

59:53 _Sarah:_
Yeah, it was more just a comment.
I think it's quite interesting people talk about biology.
Some people say it's not a real science because it's all messy and noisy.
But I think it works really interesting because it's like you say, the synaptic noise is actually a reporting of uncertainty.
So in that essence, it's actually probably quite accurately reporting the messy world rather than the biology itself just being all messy.
But that's just what I was thinking about.
Yeah, I think I was curious as well.
Like you said, this was like your Lockdown project, but I'm just interested in how you sort of came to use the free energy principle, how you came across it.
Was it something you were quite familiar with already or some of your network or peers were talking about it?
Or did you just stumble across it in a.

1:00:36 _David:_
Was during my PhD, I was interested in variational methods and probabilistic methods.
And then I started reading about this.
And so I read a bunch of Karl Friston's papers and I found this interesting.
And actually, my PhD supervisor always encouraged me not to go in that direction.
And then after I finished my PhD and thought, okay, now I can do what I want, I try it out.

1:01:10 _Sarah:_
And then, I guess, do you think it would be worthwhile, like, next steps for you or for the field actually trying to implement this on maybe some of the more analog chips that are being built in the space?
Like the analog neuromorphic chips, which I know you can have some dynamic synapses and things like do you think it would be worthwhile trying to implement it on hardware?
Or what are your thoughts on that?

1:01:35 _David:_
I mean, the triplet rule that comes out from this first work I showed, I think that would be interesting to implement it.
The nice feature is that it should, in principle, should have this self stabilizing feature because it's really mimicking the dynamics of the membrane, of the cell membrane.
So if the neuromorphic hardware would so if the model in the synapse and the neuron model match up very well, the model should give you this nice self stabilizing feature so that neurons really not go into some epileptic states or so.
And you get this for free from this model.
That's what we saw in the simulations, at least.
But in the simulations, of course, we had full control over this dynamics matching up in the right way.
So that is probably a bit more tricky for hardware, but it's probably solvable.
1:02:39 So it would be interesting.
What you get for it is that you have these purely event based tools which only use pre post spikes, which is nice.

1:02:50 _Sarah:_
Very cool.
Thank you.
Yeah.
Daniel, if you had a question?

1:02:55 _Daniel:_
Well, that's a great principle there, which is like, if you can design the neuromorphic algorithm so that it harnesses a material feature like the actual leaky permeability of a membrane or actual spatial proximity, if you can leverage a material feature, analog feature that isn't virtualized, then it's already an adjacency into future hardware.
So that's one great point.
And then to Sarah's point about almost biology not being a science, which there is a famous quotation, there will never be a Newton for a blade of grass.
Because some people say, yeah, it's a different biology is more like history.
Because whether you approach this from a development or ecology or evolution perspective, biology is a historical science.
It's not like a real science.
And then that reminded me of the cross country shirt that says, our sport is your punishment.
So it's like, well, no, your noise is biology's signal.
1:04:01 And that's how it happens.
My question was about this tension between, I guess, neural and computational ways of looking at the resources associated with computation.
So from the von Neumann paradigm.
We have a lot of shared reference points, CPU cycles, Ram capacity, and all these kinds of and like, even in your introductions, you conveyed like, well, this is how many CPU cycles it's going through, or this is how many parameters would have to be stored, or something like that.
However, that's referencing another paradigm.
So what do resource descriptors or capacity descriptors look like when we're outside the space of okay, yeah, power consumption.
1:05:05 That's something that you can put into a box and just use a bomb calorimeter that's kind of like a low hanging fruit.
But now okay, beyond just the sheer energy or caloric requirements, what can we say that is, like, analogous to the way that we talk about the processor or the Ram or the hard drive on a computer?

1:05:31 _Sarah:_
Yeah, I'd have to think about that one some more.
I do think there was some interesting comments in the paper on that slide I showed that talks about the brain and energy.
There was a paper I linked to.
I'll have to get the reference and let you know what it is because QR code is gone now.
But that had some interesting ideas, I think, on what you're getting at there.
But I'd have to defer to the paper.

1:05:55 _Daniel:_
How do they describe what is being designed?
So they say it has this many of this type of component, and then that might do nothing though.
So how do they describe or evaluate these different designs or algorithms?

1:06:12 _Sarah:_
I think it's all different depending on the use case.
That's what I've found.
Really?
Like, the language is different depending on if it's written by someone maybe with more of a neuroscience background or an engineering background.
And then you kind of get used to some terms that are more interchangeable than others.
But I do think the terminology is something which needs to be looked at a lot more closely in this space, because then I think that will help everybody working in it to be on the same page a little bit closer.

1:06:42 _David:_
Cool.

1:06:43 _Daniel:_
Well, any other thoughts or questions?
David first and then Sarah.
Also, I'm very curious, what direction will this series go?
But first, David, what are any other kind of closing comments or directions you want to.

1:07:05 _David:_
Really?
I mean, I would say thanks for having me today.
It was really a pleasure to discuss with you.

1:07:14 _Sarah:_
Thank you.
David, it was amazing to have you on.
I think your work is absolutely fascinating, and I think it's going to have lots of benefits in the future for implementation, which is always nice to see as well.
Yeah.
So what was the question?
Where do I see the series going?
Hopefully we can have a new guest each month.
I think it'd be kind of cool maybe next month to have someone who's building hardware, so, like, maybe someone from the BrainScaleS team or spinnaker team or something like that would be.
Pretty cool, but yeah, really, I just want to have a space for people who are interested in this intersection to meet people and see talks and reach out to people who are also working in the space, because it's pretty niche, but I think it's pretty important, actually.
Having said that, David, could you let everybody know if they wanted to reach out to you, what's the best way for them to do that?

1:08:12 _David:_
I'm not very active on this discord channel, so maybe email is still the best to reach out to me, I guess.

1:08:20 _Sarah:_
Cool.
Do you want to give your oh.

1:08:24 _David:_
I think my email should be easy enough to find.
But you can also give the email out there.
Sure.
Cool.

1:08:31 _Daniel:_
People can check the papers, and then in the active inference institute discord, there's the neuromorphic channel.

1:08:41 _David:_
All right.

1:08:42 _Daniel:_
Thank you, David and Sarah.
Really cool to see morphstream kick off its developmental trajectory this way.
So till next time.

1:08:51 _Sarah:_
Thank you.

1:08:52 _David:_
Bye.
