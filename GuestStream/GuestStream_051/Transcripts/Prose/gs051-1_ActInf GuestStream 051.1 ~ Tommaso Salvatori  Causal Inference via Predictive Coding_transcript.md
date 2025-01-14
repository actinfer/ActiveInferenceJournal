00:19 _Daniel Friedman:_
Hello and welcome.
It's Active Inference guest stream number 51.1 on July 28, 2023.
We are here with Tommaso Salvatori and we will be having a presentation and a discussion on the recent work Causal Inference via Predictive Coding.
So thanks so much for joining.
For those who are watching Live, feel free to write questions in the live chat and off to you.
Thank you.

00:50 _Tommaso Salvatori:_
Thank you very much, Daniel, for inviting me.
Always been a big fan of the channel and I've been watching a lot of videos, so I'm quite excited to be here and be the one speaking this time.
So I'm going to talk about this recent preprint that I put out, which has been the work of the last couple of months.
And it's a collaboration with Luca Binketti, Amin, Mccarrak Berenmille and Tommaso Lukasiavic.
And it's basically a joint work between Verses, which is the company I work for, the University of Oxford and Teovien.
So during this talk, this is basically the outline of the talk, I will start talking about what predictive coding is and give an introduction of what it is, a brief historical introduction, why I think it's important to study predictive coding, even, for example, from the machine learning perspective.
I will then provide a small intro to what causal inference is.
And once we have all those informations together, I will then discuss why I wrote this paper, what was basically the research question that inspired me and the other collaborators and present the main results, which are how to perform inference so intervention and counterfactual inference, and how to learn the causal structures from a given data set using predictive coding.
And then I will of course conclude with some small summary and some discussion on why I believe this work can be impactful and some future directions.
So what is predative coding?
predative coding is in general famous for being a neuroscience inspired learning method.
So a theory of how information processing in the brain works and brain, formally speaking, the theory of creative coding can be described as basically having a hierarchical structure of neurons in the brain.
And you have two different families of neurons in the brain.
The first family is the one in charging of sending prediction information.
So neurons in a specific level of the hierarchy send information and predict the activity of the level below.
And the second family of neuron is that of error neurons.
And the error neurons, they send prediction error information up the hierarchy.
So one level predicts the activity of the level below.
This prediction has some mismatch which was actually going on in the level below, and information about the prediction error gets sent up the hierarchy.
However, predictive coding was actually not burned as a neuroscience, as a theory from the neurosciences, but it was actually initially developed as a method for signal processing and compression back in the 50s.
So the work of Oliver Elias, which are actually contemporary of Shannon they realized that once we have a predictor, a model that works that is well in predicting data, sending messages about the error in those predictions is actually much cheaper than sending the entire message every time.
And this is how predictive coding was born.
So as a signal processing and compression mechanism in information theory back in the 50s, it was actually in the 80s that exactly the same model was used in neuroscience with the work from Mumford or other works that, for example, explain how the Retina process information.
So we get prediction signals from the outside world and we need to compress this representation and have this internal representation in our neurons.
And the method is very similar, if not equivalent to the one that was developed by Elias and Oliver in the 50s.
Maybe what's the biggest paradigm shift happened in 99 thanks to the work of Rao and Ballard in which they introduced this concept that I mentioned earlier about hierarchical structures in the brain where prediction information is top down and error information is bottom up.
And something that they did that wasn't done before is that they explain and develop this theory about not only inference, but also about how learning works in the brain.
So it's also a theory of how our synapses get updated.
And the last big breakthrough that I'm going to talk about in this brief historical introduction is from 2003.
But then he kept going in the years after, thanks to Karl Friston, in which basically he took the theory of Rowan Ballard and he developed, he extended it and generalized it to the theory of generative models.
So basically the main claim that Karl Frieston did is that predictive coding is an evidence maximization scheme of a specific kind of generative model, which I'm going to introduce later as well.
So to make a brief summary, in the first two kinds of predica described so signal processing and compression and information processing in the Retina and in the brain in general, they are inference methods.
And the biggest change, the biggest revolution that we had in 1999, so let's say in the 21st century, is apparative coding was seen as a learning algorithm.
So we can first compress information and then update all the synapses or all the latent variables that we have in our generative model to improve our generative model itself.
So let's give some definitions that are a little bit more formal.
So prior coding can be seen as a hierarchical Gaussian generative model.
So here is a very simple figure in which we have this hierarchical structure which can be as deep as we want.
And prediction signals go from one latent variable XN to the following one and it gets transformed every time via function GN or GI.
This is a generative model, as I said.
And what's the marginal probability of this generative model?
Well, it's simply the probability of the last can you see my cursor?

08:26 _Daniel:_
Yes.

08:26 _Tommaso:_
Right?
Yes.
Perfect.
So it's the generative model of the last vertex is the probability distribution of the last vertex times the probability distribution of every other vertex conditioned on the activity of the vertex before or on the latent variable before.
I earlier said that it's a Gaussian generative model, which means that those probabilities, they are in Gaussian form and every and those function g in general and especially since, for example, in Rambalar paper and in all the papers that came afterwards.
Also because of the deep learning revolution, those functions are simply linear maps or nonlinear maps with activation functions or nonlinear maps with activation function and an additive bias.
So we can give an informal definition of creative coding and we can say predictive coding is an inversion scheme for such a generative model where its model evidence is maximized by minimizing a quantity that is called a variation of free energy.
In general, the goal of every generative model is to maximize model evidence, but this quantity is always intractable.
And we have some techniques that allow us to approximate this solution and the one that we use in pritef coding instead of minimizing aberration of free energy, which is a lower bound of the model evidence in this work and actually in a lot of other ones.
So it's the standard way of doing it.
This minimization is performed via gradient descent and yes, performed via gradient descent.
And there are actually other methods such as expectation maximization which is often equivalent.
Or you can use some other message passing algorithms such as belief propagation, for example, and going a little bit back in time.
So forgetting a little bit about the statistical generative models, we can see pref coding, I said already a couple of times as a hierarchical model with neural activities.
So with neurons, latent variables that represent neural activities, the sender signal down the hierarchy and with error nodes or error neurons, the sender signal up the hierarchy so they send the error information back.
What's the variation of free energy of these class operative coding models?
It's simply the sum of the mean square error of all the error neurons, so is the sum of the total error squared.
And this representation is going to be useful in the later slides and in how I'm going to explain how to use pref coding to model causal inference.
For example, why do you think pre tip coding is important and is a nice algorithm to study?
Well, first of all, as I said earlier, it optimizes the correct objective which is the model evidence or marginal likelihood.
And then it does so by optimizing a lower bound which is called the rational free energy, as I said.
And the rational free energy is interesting because it can be written as a sum of two different terms which are and each of those term optimizing.
It has important impacts, for example, in machine learning tasks or in general in learning tasks.
So one of those term forces memorization.
So the second term basically forces the model to fit a specific data set and the first term forces the model to minimize the complexity.
And as we know, for example from the Occam's razor theory, if we have two different models that perform similarly on a specific training set, the one that we have to get and the one that is expected to generalize the most is the less complex one.
So updating generative model via vibrational free energy allows us to basically converge to the optimal Occam razor model which both memorizes a data set but is also able to generalize very well on unsigned data points.
A second reason of why prioritic coding is important is that it actually doesn't have to be defined on a hierarchical structure, but it can be modeled on more complex and flexible architectures such as directed graphical model with any shape or generalized even more to networks with a lot of cycles that resemble brain region.
And the underlying reason is that you're not learning and predicting with a forward pass and then back propagating the error but you're minimizing an energy function and this allows basically every kind of hierarchy to be allows to go behind hierarchies and allow to learn cycles.
And this is actually quite important because the brain is full of cycles as we have some information from some recent papers that managed to map completely the brain of some animals such as fruit fly.
The brain is full of cycles so it makes sense to train our machine learning models or our models in general with an algorithm that allows us to train using cyclic structures.
The third reason why prior coding is interesting is that it has been formally proven that it is more robust than standard neural networks during with back propagation.
So if you have a neural network and you want to perform classification tasks, creative coding is more robust.
And this is interesting in tasks such as online learning, training of small data sets or continuous learning tasks.
And the theory basically comes from the fact that imperative coding has been proved to approximate implicit gradient descent, which is a different version of the explicit gradient descent which is the standard gradient descent used in every single model basically.
And it's a variation that is more robust I think.
Okay, I did quite a long intro to predictive coding, I think.
I'm now moving to the second topic which is causal inference.
And what's causal inference?
Causal inference is a very general theory that has been formalized the most by Judea Pearl.
He's definitely the most important person in the field of causal inference.
He wrote some very nice books.
For example, the Book of Why is highly recommended if you want to learn more about this topic and it basically tackles the following problem so let's assume we have a joint probability distribution which is associated with a Bayesian network.
This is going to be a little bit the running example through all the paper, especially with Bayesian networks of this shape.
Those Bayesian networks, the variables inside, they can represent different quantities.
So for example, a Bayesian network with this shape can represent the quantities on the right.
So, socioeconomical statue of an individual, its education level, its intelligence and its income level, something the classical statistics is very good at and its wild, most used application is to model observations or correlations.
A correlation basically answer the question what is D if we observe another variable C?
So for example, in this case, what's the income level, the expected income level of an individual if I observe his education level and of course, if that person has a higher degree of education, for example a master or PhD.
I'm expecting general that person to have a higher income level and this is a correlation.
However, sometimes there are things that are very hard to observe, but they play a huge role in determining those quantities.
So for example, it could be that the income level is much, much more defined by the intelligence of a specific person and maybe that the intelligence.
So if a person is intelligent, he's also most likely to have a higher education level.
But still the real reason why the income is high is because of the IQ.
And this cannot be studied by Simplico relations and has to be studied by a more advanced technique which is called an intervention.
An intervention basically answers the question is what is D if we change C to a specific value?
So for example, we can take an individual and check his income level and then change its education level.
So intervene on this word and change his education level without touching his intelligence and see how much its income changes.
For example, if the income changes a lot it means that the intelligence doesn't play a big role in this, but the education level does.
If the income level doesn't change much, it means that maybe there's a hidden variable in this case the intelligence that determines the income level of a person.
The third quantity important in causal inference is that of counterfactuals.
So for example, a counterfactual answers the question what would D be had we changed C to a different value in the past?
So for example, we can see that the difference between interventions and counterfactuals is that interventions act in the future.
So I'm intervening in the world now to observe a change in the future while counterfactuals allow us to go back in time and change a variable back in time and see how that change would have influenced the world we live in now.
And those are defined by Judeoperl as the three levels of causal inference.
Correlation is the first level, intervention is the second level and counterfactual is the third level.
What are interventions?
I'm going to define them more formally now that I gave an intuitive definition and I'm using this notation here, which is the same actually throughout all the presentation.
So x is always going to be a latent variable, si is always going to be a data point or an observation, and VI is always going to be a vertex.
So every time you see VI, we are only interested in the structure of the graph, for example.
So let's assume we have a Bayesian model which has the same structure as the Bayesian model we saw in the previous slide.
Given that x three is equal to s three, this is the observation we make statistics allows us to compute the probability or the expectation of x four, which is the latent variable related to this vertex.
Given that x three is equal to s three, to perform an intervention we need a new kind of notation which is called the do operation.
So in this case, x four, we want to compute the probability of x four, given the fact that we intervene in the word and change x three to x three.
And how do we do this to perform an intervention?
Judy Perl tells us that we have to have an intermediate step before computing a correlation is that first we have to remove all the incoming edges to v three.
So we have to study not this Bayesian network, but the second one.
And then at this point we are allowed to compute a correlation as we normally do.
And this is an intervention.
A counterfactual is a generalization of this that, as I said, lived in the past, and they're computing using structural causal models.
A structural causal model is a Tuplet which is conceptually similar to a Bayesian network.
But basically we have this new class of variables on top, which are the unobservable variables they use.
So we have the Bayesian network that we had before, x one, x two, x three, x four.
But we also have those unobservable or variables that depend on the environment.
You cannot control them, you can infer them, but they are there.
And F is a set of functions that depends on all the basically, F of x of x three depends on x one because you have an arrow, on x two because you have an arrow, and on the unobservable variable that also influences x three.
So yes, intuitively you can think of a structural causal model as a Bayesian network with those unobservable variables on top, and each unobservable variable only influences its own latent variable x.
So for example, IU will never touch x one as well, u three will only touch U three, u one will only influence x one, and so forth and so on.
So performing counterfactual inference answers the following question so what would x four be at x three being equal to another variable in a past situation u.
And computing this counterfactual requires three different steps.
So abduction is the computation of all the background variables.
So in this step we want to go back in time and understand how the environment, the unobservable environment was in that specific moment in time.
And we do this by fixing all the latent variables x to some specific data that we already have and performing this inference on the use.
Then we're going to use the U to keep the U that we have learned and perform an intervention.
So a counterfactual can also be seen as an intervention back in time in which we know the environment variables u one, U two and U four in that specific moment.
And what's the missing step?
So what would x four be at x three being equal to another data point in that specific situation?
Now we can compute a correlation and the correlation we do it on the graph in which we have already performed an intervention using the environment variables that we have learned in the abduction step.
And this is a counterfactual inference.
This is the last slide of the causal inference introduction and it's about structured learning.
Basically everything I've said so far relies on the fact that we know the causal dependencies among the data points.
So we know the structure of the graph, we know which variable influences which one, we know the arrows in general but in practice this is actually not always possible.
So we don't have access to the causal graph most of the times and actually learning the best causal graph from data is still an open problem.
We are improving in this, we are getting better.
But how to perform this task exactly is still an open problem.
So as I said, basically the goal is to infer causal relationships from observational data.
So given a data set we want to infer the directed icyclic graph that describes the connectivity between the system and the variables of the data set.
So for example, here we have an example that I guess we are all familiar with because of the pandemic.
So we have those four variables age, vaccine, hospitalization and city.
And we want to infer the causal dependencies among those variables.
So for example, we want to learn directly from data that the probability of a person being hospitalized depends on its age and on the fact whether it's vaccinated or not and so forth and so on.
So this is the end of the long introduction but I hope it was clear enough and I hope that I gave the basics to understand basically the results of the paper and now we can go to the research questions.
So the research questions are the following first I want to see whether predictive coding can be used to perform causal inference.
So predictive coding so far has only been used to perform to compute correlations in Bayesian networks.
And the big question is can we go beyond correlation and model intervention and counterfactual in a biological plausible way?
So in a way that it's for example, simple, intuitive and allow us to only play with the neurons and not touch, for example, the huge structure of the graph and more in practice.
More specifically, the question becomes can we define operative coding based structural causal model to perform interventions and counterfactuals?
The second question is, as I said, that having a structure causal model assumes that we know the structure of the Bayesian network, so it assumes that we have the arrows.
Can we go beyond this and use predictive coding networks to learn the causal structure of the graph?
Basically, giving positive answers to both those questions would allow us to use predictive coding as an end to end causal inference method which basically takes a data set and allow us to test interventions and counterfactual predictions directly from this data set.
So let's tackle the first problem.
So causal inference Vibrative coding which is also the section that gives the title to the paper basically.
And here I will show how to perform correlations with Abrasive coding which is already known, and how to perform interventional queries which I think is the real question of the paper.
So here is a causal graph which is the usual graph that we had and here is the corresponding priority coding model.
So the axes are the latent variables and correspond to the neurons in a neural network model.
And the black arrow pass prediction information from one neuron to the one down the hierarchy.
And every vertex also has this error neuron which passes information up the hierarchy.
So the information of every error goes to the value node up the hierarchy and basically tells it to correct itself to change the prediction.
So to perform a correlation using predictive coding, what you have to do is that you take an observation and you simply fix the value of a specific neuron.
So if you want to compute the probability of x four given x three equal to s three, we simply have to take x three and fix it to s three in a way that it doesn't change anymore and run an energy minimization.
And this model, by updating the axis via a minimization of the variational free energy allows the model to converge to a solution to this question.
So the probability or the expected value of x four given x three equals three.
But how do I perform an intervention now without acting on the structure of the graph?
Well, this is basically the first idea of the paper, this is still how to perform a correlation.
So fix s three equal to x three is the first step in the algorithm and the second one is to obtain the axis by minimizing the variation of free energy, an intervention which in theory corresponds in removing those arrows and answers to the question the probability of x four by performing an intervention.
So do x three equal s three?
Imperative coding can be performed as follows.
So I'm going to write the algorithm here.
So first, as in a correlation, you fix s three equal equal to the you fix x three equal to the observation that you get then this is the important step.
You have to intervene not on the graph anymore, but on the prediction error and fix it equal to zero.
Having a prediction error equal to zero basically sends meaningless information up the hierarchy, or actually sends no information up the hierarchy because it basically tells you that the prediction is always correct.
And the third step is to, as we did before, to update the axis, the unconstrained axis.
So x one, x two, x four.
By minimizing the variation of free energy, as I will show now experimentally, by simply doing this little trick of setting a prediction error to be equal to zero, it prevents us to actually act on the structure of the graph, as the theory of Ducalculus does, and to infer the missing the variables after an intervention.
By simply performing aberration of free energy minimization.
What about counterfactual inference?
Counterfactual inference is actually easy once we have defined how to do an intervention.
And this is because as we saw earlier, performing a counterfactual is similar to performing an intervention in a past situation after you have inferred the unobservable variables.
So, as you can see in the plot I showed earlier about the abduction action and prediction steps, the action and prediction steps, they did not have those two arrows, they were removed.
Pretty coding allows allow us to keep the arrows in the graph and perform counterfactuals by simply performing an adoption step, as it was done earlier, an action step in which we simply perform an intervention on the single node.
So we fix the value node and we set the error to zero and run the energy minimization.
So minimizing the rational free energy to compute the prediction.
So, I think this is like an easy and elegant method to perform interventions at counterfactuals.
I think the thing we have to show now is whether it works in practice or not.
And we have a couple of experiments and I'm going to show you now two different experiments.
The first one is merely proof of concept experiment that shows that the operative coding is able to perform intervention and counterfactuals.
And the second one actually shows a simple application in how interventional queries can be used to improve the performance of classification tasks on a specific kind of predictive coding networks, which is that of a fully connected model.
Let's start from the first one.
So how do we do this task?
So, given a structural causal model, we generate training data and we use it to learn the weights.
So, to learn the functions of the structural causal models, and then we generate test data for both interventional and counterfactual queries and we show whether we are able to converge to the correct test data using predictive coding.
For example, here those two plots represent intervention and counterfactual queries of this specific graph, which is the butterfly bias graph, which is a graph that is often used in in testing whether causal inference, whether intervention and counterfactual techniques work is as simple as that.
But in the paper you can find a lot of different graphs.
But in general those two plots show that the method works show that the mean absolute error between the interventional and counterfactual quantities we compute and the interventional and counterfactual quantities from the original graph are close to each other.
So the error is quite small.
The second experiment is basically an extension of an experiment I proposed in an earlier paper which is the Learning on arbitrary graph topologies that I wrote last year.
In that paper, I basically proposed this kind of network as a proof of concept, which is a fully connected network, which is, in general, the worst neural network you can have to perform machine learning experiments because given a fixed set of neurons, basically every pair of neuron is connected by two different synapses.
So is the model with the highest complexity possible in general.
The good thing is that since you have a lot of cycles, the model is extremely flexible in the sense that you can train it, for example, on a Minced image and on a data point and on its label.
But then the way you can query it, thanks to the information going back, is you can query in a lot of different ways.
So you can perform classification tasks in which you provide an image and you run the energy minimization and get the label but you can also, for example, perform generation tasks in which you give the label, run the Energy Minimization and get the image.
You can perform, for example, image completion in which you give half the image and let the model convert to the second half and so forth and so on.
So it's basically a model that learns the statistics of the data set in its entirety without being focused on classification or generation in general.
So this flexibility is great.
The problem is that because of this every single task doesn't work well so it can do a lot of different things but none of them is done well and here I want to show how using interventional queries instead of standard correlational queries or conditional queries slightly improves the results of those classification tasks.
So what are the conjecture reasons of the test accuracy on those tasks not being so high?
The two reasons are that the model is distracted in correcting every single error.
So basically you present an image and you would like to get a label but the model is actually updating itself to also predict the error in the images and the second reason, which is the one I said, is that the structure is far too complex.
So again, from an OCAM razor argumentation this is the worst model you can have.
So every time you have a model that.
Fits a data set.
That model is going to be less complex than this one that is going to be preferred, but in general just to study it, the idea is can query in this model be interventions be used to improve the performance of those fully connected models?
Well, the answer is yes.
So here is how I perform interventional queries.
So I present an image to the network, I fix the error of the pixels to be equal to zero so this error doesn't get propagated in the network.
And then I compute the label and as you can see the accuracy improves.
For example, from 89 using the standard query method of creative coding networks, to 92, which is the accuracy after the intervention.
And the same happens for fashion minced.
And I think that a very legit critique that probably everyone would think when seeing those plots is that okay, you improved on mins from 89 to 92.
It still sucks basically.
And yeah, it's true.
And actually in the later slides I'm going to show how to act on the structure of this fully connected model will improve the results even more until the point they reach a performance that is not even close to state of the art performance of course, but up to a level that becomes visually acceptable and worth investigating.
Yes.
So this was the part about causal inference using previous coding.
And I guess to summarize, I can say that the interesting part of the results I just showed is that I showed that predictive coding is able to perform interventions in a very easy and intuitive way because you don't have to act on the structure of the old graph anymore.
Sometimes those functions are not available, so forth and so on.
But you simply have to intervene on a single neuron, set its prediction error to zero and perform an energy minimization process.
And this extended allowed us to define predictive coding based structural causal models.
Now we move to the second part of the work which is about structure learning.
So structure learning, as I said, deals with the problem of learning the causal structure of the model from observational data.
This is actually an old problem that has been around for decades and has always been until a couple of years ago tackled using combinatorial search methods.
The problem with those combinatorial search methods is that their complexity grows double exponentially.
So as soon as the data becomes multidimensional and the Bayesian graph that you want to learn grows in size learning, it it's incredibly slow.
The new solution that came out actually a couple of years ago in a new research paper from 2018 showed that it's possible to actually learn this structure not using a combinatorial search method, but by using a gradient based method.
And this killed the problem in general because now you can simply have a prior on the parameters, which is the prior the proposed that I'm going to define a little bit better in this slide run gradient descent.
And even if you have a model that is double triple the size, the algorithm is still incredibly fast.
And for this reason this paper is I think it's kind of new and I think already has around 600 citations or things like that.
And every paper that I'm seeing now about causal inference and learning causal structure of the graph uses their method.
It just changes a little bit.
They find faster or slightly better inference methods, but still they all use the prior this paper defined and I do as well, and we do as well.
So here we define a new quantity which is the agency matrix.
The agency matrix is simply a matrix that encodes the connections of the model.
So it's a binary matrix and in general it's a binary matrix.
Then of course, when you do gradient based optimization you make it continuous and then you have some threshold at some point that basically kills an edge or set it to one and the entry IJ is equal to one if the Bayesian graph has an edge from vertex I to vertex j or zero otherwise.
So for example, this agency matrix here represents the connectivity structure of this Bayesian network.
And basically this method tackles two problems that we want about learning the structure of the Bayesian network.
The idea is that we start from a fully connected model, which conceptually is similar, actually is equivalent to the creative coding network I defined earlier, which is fully connected.
So you have a lot of vertices and every pair of vertices is connected by two different edges and you simply want to prune the ones that are not needed.
So it can be seen as a method that performs model reduction.
You start from a big model and you want to make it small.
So what's the first ingredient to reduce models?
Well, it's of course sparse city.
And what's the prior that everyone uses to make a model more sparse is the LaPlace prior, which in machine learning is simply known as the L one norm, which is defined here.
The solution that this paper that I mentioned earlier proposed is to add a second prior on top, which enforces what's probably the biggest characteristic of Bayesian networks on which you want to perform causal inference is that you want them to be a cyclic.
And basically they show that Acyclicity can be imposed on an agency matrix as a prior and it has this shape here.
So it's the trace of the matrix that is the exponential of a times a where A is the agency matrix again.
And basically this quantity here is equal to zero if and only if the Bayesian network or whatever graph you're considering is a cyclic.
So I'm going to use this in some experiments.
So to force those two priors on different kinds of Bayesian networks and I'm trying to merge them with the techniques we proposed earlier about performing causal inference via predictive coding.
So I'm going to present two different experiments.
So one is a proof of concept, which is the standard experiments showed in all the structural learning tasks, which is the inference of the correct Bayesian network from data.
And then I'm going to build on top of the classification experiments I showed earlier and show how actually those priors allow us to improve the classification accuracy, the test accuracy of fully connected predictive coding models.
So let's move to the first experiment, which is to infer the structure of the graph.
And the experiments, they all follow basically the same pipeline in all the papers in the field.
The first step is to generate a vision network from a random graph.
So basically, normally the two random graphs that everyone tests are erdos reni graphs and scale free graph.
So you generate those big graphs that normally have 20, 40, 80 different nodes and some edges that you sample randomly and you use this graph to generate a data set.
So you sample, for example, n, big N data points.
And what you do is that you take the graph they have generated earlier and you throw it away.
You only keep the data set.
And the task you want to solve now is to have a training algorithm that basically allows you to retrieve the structure of the graph you have thrown away.
So the way we do it here is that we train a fully connected creative coding model on this data set D using both the sparse and the acyclic priors we have defined earlier and see whether actually the graph that we converge to after pruning away.
The entries of the agency matrix that are smaller than a certain threshold is similar to that of the of the initial graph.
And the results show that this is actually the case.
So this is an example and I show many different parameterization and dimensions and things like that in the paper, but I think those two are the most representative examples with an Ernest Sharoni graph and a free scale graph with 20 nodes.
And here on the left you can see the ground truth graph, which is the one sampled randomly.
And on the right you can see the graph the predictive coding model has learned from the data set.
And as you can see, they are quite similar.
It's still not perfect, so there are some errors, but in general the structure is they work quite well.
We also have some quantitative experiments that I don't show here because they're just huge tables with a lot of numbers and I thought it was maybe a little bit too much for the presentation, but the results show that they perform similarly to contemporary methods.
Also because I have to say, like, most of the quality comes from the Acyclic prior that was introduced in 2018.
The second class of experiments are classification experiments, which as I said are the extensions of the one I shared earlier.
And the idea is to use structure learning to improve the classification on the classification results on the means and fashion means data set, starting from a fully connected graph.
So, what I did is that I divided the fully connected graph in clusters of neurons.
So one big cluster is the one related to the input and all the small.
Then we have some a specific number of hidden clusters.
And then we have the label cluster, which is the cluster of neurons that are supposed to give me the label predictions.
And I've trained them using the first time, the sparse prior only.
See, the idea is what if I, if I prune the connections I don't need from a model and learn a sparser model?
Does this work?
Well, the answer is no, it doesn't work.
And the reason why is that at the end, the graph that you converge with is actually the generate.
So basically the model learns to predict the label based on the label itself.
So it discards all the information from the input and only keeps the label.
And as you can see here, the label y predicts itself.
Or in other experiments, when you change the parameters, you have that y predicts x zero that predicts x one that predicts y again.
So what's the solution to this problem?
Well, the solution to this problem is that we have to converge to an acyclic graph and so we have to add something that prevents acyclicity.
And what is that one is of course, the one I already proposed.
And then I show a second technique.
So the first one uses the acyclic prior defined earlier.
And the second one is a novel technique that actually makes use of negative examples.
So a negative example in this case is simply a data point in which you have an image, but the label is wrong.
So here, for example, you have an image of a seven, but the label that I'm giving the model is a two.
The idea is very simple, has been used in a lot of works already.
So every time the model sees a positive example, it has to increase to minimize the variation of free energy.
And every time it sees a negative example, it has to increase it.
So we want this quantity to be minimized.
And actually, with a lot of experiments and a lot of experimentations, we saw that the two techniques basically first lead to the same results and second lead to the same graph as well.
So here are the new results on Minced and fashion Mins using the two techniques that I just proposed.
And now we move to some which are still not great, but still definitely more reasonable test accuracies.
So here we have a test error of 3.17 for Minced and a test error of 13.98 for Fashion Minced.
And actually those results can be much improved by learning the structure of the graph on Minced and then fixing the structure of the graph and do some form of fine tuning.
So if you fine tune the model on the correct hierarchical structure, at some point you reach the test accuracy, which is the one you would expect from a hierarchical model, but those ones are simply the one the fully connected model has naturally converged to.
For example, from a test error of 18.32 of the fully connected model train on fashion means by simply performing correlations or conditional queries, which is the standard way of querying Abrative coding model.
Adding interventions and the Acyclic prior together makes this test error much lower and we can observe it for Mins as well.
I'm now going a little bit into details on this last experiment and on how the Acyclic prior acts on the structure of the graph.
I perform an experiment on a new data set, which is, I mean, calling it a new data set is maybe too much.
I called it a two means data set in which you have the input point is formed of two different images and the label only depends on the second image, on the first image.
Sorry.
So the idea here is, is the structure of the model, the Acyclicity prior and things like that, able to recognize that the second half of the image is actually meaningless in learning, in performing classification, how does training behave in general?
Like, for example, we have this input node output node and only the nodes are fully connected.
Can the model converge to a hierarchical structure, which is the one that we know performs the best on classification tasks?
Well, here is an example of a training method of a training run.
So at c zero, which is the beginning of training, we have this model here.
So S zero corresponds to the seven.
So to the first image, s one corresponds to the seven image.
Again, we have the label y and all the latent variables x zero, x one, x two.
And the model is fully connected.
So the agency matrix is full of ones.
There are no zeros.
We have self loops and things like that.
We train the model for a couple of epochs until and what we note immediately is that, for example, the model immediately understands that the four is not needed to perform classification.
So every outgoing node from the second input cluster is removed.
And something that you understand is that this cluster is the one related to the output.
So we have a linear map from s zero to y directly, which is this part here.
But we know that actually a linear map is not the best map for performing classification on Minst.
So we need some hierarchy, we need some depth to improve the results.
And as you can see, this line here is the accuracy which up to this point, so up to c two is similar to is 91% which is slightly better than linear classification.
But once you go on with the training, the model understands that it needs some hierarchy to better fit the data.
So you see that this arrow starts getting stronger and stronger over time until it understands that the linear map is not actually really needed and it removes it.
So the model you converge with is a model that starts from a zero, goes to a hidden node, and then goes to the label with a very weak linear map, which actually gets removed if you set a threshold.
Of if you set a threshold of, for example, 0.10.2, at some point the linear map gets forgotten and everything you end up with is with a hierarchical network.
So it has learned the correct structure to perform classification tasks, which is hierarchy.
And it has also learned that the second image didn't play any role in defining the test accuracy.
And this is all performed, so all those jobs are simply performed by one free energy minimization process.
So you initialize the model, you define the free energy, you define the priors.
So the sparse and the cyclic prior, you run the energy minimization and you converge to a hierarchical model which is well able to perform classification on minst.
And then if you then perform some fine tuning, you reach very competitive results as you do in feed forward networks with backpropagation.
But I think that's not the interesting bit.
The interesting bit is that all this process altogether of intervention and a cyclicity allows you to take a fully connected network and converge to a hierarchical one that is able to perform classification with good results.
And yeah, that's basically it.
Wow, I've talked a lot and this is the conclusion of the talk, which is I'm basically doing a small summary and I think the important takeaway, if I have to give you in one sentence of this paper, is that predictive coding is a belief updating method that is able to perform end to end causal learning.
So it's able to perform interventions to learn a structure from data and then perform interventions and counterfactuals.
So causal inference in natural and efficiently model interventions by simply setting the prediction error to zero.
So it's a very easy technique to perform interventions and you only have to touch one neuron.
You don't have to act on the structure of the graph, you can use it to create structure causal models that are biologically plausible.
It is able to learn the structure from data, as I said, maybe a lot of times already and a couple of sentences about future works is that something that would be nice to do is to improve the performance of the model we have defined.
Because I think it performs reasonably well on a lot of tasks.
So it performs reasonably well on structured learning, on forming intervention and counterfactuals.
But actually, if you look at state of the art model, there's always like a very specific method that performs better in the single task.
So it would be interesting to see if we can reach those level of performance in specific tasks by adding some tricks or some new optimization methods and to generalize it to dynamical systems which are actually much more interesting the static systems such as dynamical causal models or other techniques that allow you to perform causal inference in systems that move.
So an action taken in a specific time step influences another node in a later time step, which is basically granger causality.
Yeah, that's it.
And thank you very much.

59:47 _Daniel:_
Thank you.
Awesome and very comprehensive presentation.

59:52 _Tommaso:_
That was really I think you're muted.

59:57 _Daniel:_
Sorry, muted on zoom.
But yes, thanks for the awesome and very comprehensive presentation.
There was really a lot there, and there was also a lot of great questions in the live chat.
So maybe to warm into the questions, how did you come to study this topic?
Were you studying causality and found predictive coding to be useful or vice versa?
Or how did you come at this intersection?

1:00:24 _Tommaso:_
Actually, I have to say that the first person that came out with this idea was Baron, I think a year and a half ago, even more, he brought a page with this idea and then it got forgotten and no one picked it up.
And last summer I started getting curious about causality and I read, for example, the Book of Why, after listening to podcasts, the standard way in which you get interested in a topic.
And I remember this idea from Baron and proposed it to him, and I was like, why don't we expand it and actually make it a paper?
So I involved some people to help me with experiments, and this is the final result at the end.

1:01:12 _Daniel:_
Awesome.
Cool.
Yeah, a lot to say.
I'm just going to go to the live chat first and address a bunch of different questions.
And if anybody else wants to add.

1:01:21 _Tommaso:_
I'm going to turn the light on first because I think I'm getting in the dark more and more.

1:01:25 _Daniel:_
Yes.
Who said active inference can't solve the dark room issue?

1:01:32 _Tommaso:_
Oh, yes, here we are.

1:01:34 _Daniel:_
So would you say the light switch caused it to be lighter?

1:01:39 _Tommaso:_
Yeah, I think so.

1:01:42 _Daniel:_
No issues here.
Okay.
ML.
Don wrote, since in predictive coding all distributions are usually Gaussian, the bottom up messages are precision weighted prediction errors, where precision is the inverse of the Gaussian covariance.
What if non Gaussian distributions are used?

1:02:05 _Tommaso:_
Basically, the general method stays.
The main difference is that you don't have prediction errors, which, as was correctly pointed out, is basically the derivative of the variation of free energy.
If you have Gaussian assumptions yeah.
You don't have that single quantity to set to zero and you probably will have to act on the structure of the graph to perform interventions.

1:02:33 _Daniel:_
And also, you and colleagues had a paper in 2022 predictive coding beyond gaussian distributions that looked at some of these issues, right?

1:02:43 _Tommaso:_
Yes, exactly.
So that paper was a little bit the idea behind that paper is can we model transformers?
That's the biggest motivation using predictive coding.
And the answer is no, because the attention mechanisms are softmax at the end and softmax calls not to Gaussian distribution, but to softmax distribution.
I don't get the name now, but yes.
So yes, that's a generalization.
It's a little bit tricky to call it once you remove the Gaussian assumption, it's a little bit still tricky to call it predictive coding.
For example, like talking to Karl Friedston, predictive coding is only if you have only Gaussian assumptions.
But yes, that's more a philosophical debate than.

1:03:42 _Daniel:_
Interesting.
Another, I think topic that's definitely of great interest is similarities and differences between the attention apparatus in Transformers and the way that attention is described from a neurocognitive perspective and from a predictive processing precision weighting angle.
What do you think about that?

1:04:06 _Tommaso:_
Well, the idea is that I think about it is that from a predictive processing and also vocational inference perspective, attention can be seen as a kind of structured learning problem.
I think there's a recent paper from Chris Buckley's group that shows that there should be a reprint on Archive in which basically they showed that the attention mechanism is simply learning the precision on the weight parameters specific to a data point.
So this precision is not a parameter that is in the structure of the model.
So it's not a model specific parameter, but it's a fast changing parameter like the value nodes that gets updated while minimizing the vibrational free energy.
And once you have minimized it and computed, then you throw it away and from the next data point you have to recompute it from scratch.
So yes, I think the analogy computation wise is the attention mechanism can be seen as a kind of structured learning, but a structured learning that is data point specific and not model specific.
And I think if you want to generalize a little bit and go from the attention mechanism in transformers to the attention mechanism, cognitive science, I feel they're probably too different to draw similarities.
And I think the structured learning analogy and how important one connection is with respect to another one probably does the job much better.

1:05:42 _Daniel:_
Cool.
Great answer.
Okay, ML Don asks in counterfactuals what is the difference between hidden variables X and unobserved variables U?

1:05:55 _Tommaso:_
The difference is that I think the main one is that you cannot observe the use.
You can use them because you can compute them and fix them, but the idea is that you have no control over them.
So the use should be seen as environment specific variables that they are there, they influence your process because for example, when you go back in time, the environment is different.
So the idea is, for example, if you like going back to the example before of the expected income of a person with a specific intelligence of education degree.
The idea is that if I want to see how much I will earn today with a master degree is different with respect to how much I would earn 20 years ago with a master degree is different.
For example, here in Italy with respect to other countries and all those variables that are not under your control.
You cannot model them using your Bayesian network, but they are there.
Okay.
So you cannot ignore them when you want to draw conclusions.
So, yeah, it's basically everything that you cannot control, you can infer them.
So you can perform a counterfactual inference back in time and say, oh, 20 years ago, I would have earned this much if I was this intelligent at this degree, on average, of course.
But it's not that I can change the government policies towards jobs or things like that.

1:07:32 _Daniel:_
It's a deeper counterfactual.

1:07:35 _Tommaso:_
Yes, exactly.
So those are the use.

1:07:38 _Daniel:_
Awesome.
All right.
Have you implemented generalized coordinates in predictive coding?

1:07:45 _Tommaso:_
No, I've never done it.
I've studied it, but I've never implemented it.
I know they tend to be unstable, and it's very hard to make them stable.
I think that's the takeaway that I got from talking to people that have implemented them.
But yeah, I'm aware of some papers that came out, actually recently about them that tested on some bracelet, encoder style, actually, I think still from Baron.
There's a paper out there that came out last summer.
But no, I've never played them with them myself.

1:08:26 _Daniel:_
Cool.
From Bert.
Does adding more levels in the hierarchy reduce the distraction problem of predicting input?

1:08:39 _Tommaso:_
Adding more level, in which sense because the distraction problem is given by cycles.
So basically you provide an image, and the fact that you have edges going out of the image going in the neurons, and then other edges going back, this basically creates the fact that basically these ingoing edges to the pixels of the image, they create some prediction errors.
So you have some prediction errors that get spread inside the model.
And this problem, I think, is general of cycles, and it's probably not related to hierarchy in general, is the two incoming edges to the pixels.
If you don't have incoming edges, you have no destruction problem anymore.

1:09:30 _Daniel:_
Cool.
And the specification of the asyclic network through the trace operator, that's a very interesting technique.
And when was that brought into play?

1:09:46 _Tommaso:_
As far as I know, I think it came out with a paper I cited in 2018.
I don't know, at least in the causal inference literature.
I'm not aware of any previous methods.
I would say no, because that's the highly cited paper.
So I would say they came out with that idea.

1:10:05 _Daniel:_
Wow.

1:10:05 _Tommaso:_
But yeah, that's quite nice that you can do gradient descent and learn the structure.
I think that's a very powerful technique.

1:10:13 _Daniel:_
Yeah, sometimes it's like when you look at when different features of Bayesian inference and causal inference became available.
It's really remarkable.
Why hasn't this been done under a Bayesian causal modeling framework?
It's like because there's only been like five to 25 years of this happening, and so that's very short.
And also it's relatively technical, so there's relatively few research groups engaging in it.
And it's just really cool what it's enabling.

1:10:50 _Tommaso:_
Yes, exactly.
I mean, that's also, I think, the exciting part of this field a little bit that is, I mean, there are definitely breakthroughs out there that still have to be discovered and probably because, for example, for as much as a breakthrough that paper was, they simply found the right prior for acyclic structures.
Okay, yeah, I don't know exactly, but it may be an idea that you have in one afternoon.
I don't know about the story of how the authors came up with that, but could potentially be that they're there at the whiteboard.
You're like, oh, that actually works.
That's a huge breakthrough.
And I simply defined the prior.

1:11:34 _Daniel:_
And also, a lot of these breakthroughs, they don't just stack.
It's not like a tower of blocks.
They layer and they compose.
So then something will be generalized to generalized coordinates or generalized synchrony, or arbitrarily large graphs or sensor fusion with multimodal inputs.
And it's like those all blend in really satisfying and effective ways.
So even little things that, again, someone can just come up with in a moment can really have impact.
Okay, ML.
Don says, thanks a lot for asking my questions, and thanks a million to Tommaso for the inspiring presentation.
So nice.

1:12:19 _Tommaso:_
Thank you very much.

1:12:20 _Daniel:_
And then Bert asks, how would language models using predictive coding differ from those using transformers?

1:12:32 _Tommaso:_
Okay, I think that actually, if I would have to build today a language model using predictive coding, I would still use transformers.
So the idea is that, for example, if you have, let's say, this hierarchical graphical model or this hierarchical Bayesian network, I've defined in the very first slides one arrow to encode a function, which is the linear map.
Okay?
So one arrow was simply the multiplication of the vector encoded in the latent variables times this weight matrix that you can then make nonlinear and things like that.
But that can be actually something much more complex.
The function encoded in the arrow can be a convolution, can be an attention.
So actually, how I would do it, I will still use the which is actually the way we did it in the Oxford group last year, is that we had exactly the structure.
Every arrow is a transformer now.
So one is the attention mechanism and the next one is the feed forward network.
As transformers.
Basically, the only difference that you have is that those variables, you want to compute the posterior and you make those posteriors independent via minfield approximation.
So basically, you follow all the steps that allow you to converge to the variation of.
Free energy of creative coding.
But the way you compute predictions and the way you send signals back is done via transformer.
So I will still use transformers in general.
I mean, they work so well that I don't think that we can be arrogant and say, oh no, I'm going to do it better via a purely predictive coding way.
Structure learning is a way, but will still approximate transformers anyway.

1:14:22 _Daniel:_
Sorry, you said structured learning would approximate the transformer approach.

1:14:27 _Tommaso:_
Yes, the structure learning I mentioned earlier when someone asked the similarities between creative coding and the attention mechanism.

1:14:39 _Daniel:_
Yeah, very interesting.
One thing I am wondering from ML Don, I could not see the concept of depth in the predictive coding networks you mentioned.
Most likely I missed it.
The definition provided for predictive coding involved the concept of depth.
What did you mean by depth?

1:14:59 _Tommaso:_
No.
Yes, it's true because the standard definition, as I said multiple times, is hierarchical.
You have predictions going one direction and prediction error going the opposite direction.
Basically, what we did in this paper and also in the last one, which is called learning on arbitrary graph topologies via rated coding, is that we can consider depth as independent, basically pair of latent variable, latent variable and arrow.
And you have predictions going that direction and prediction arrow going the other.
But then you can compose these in a lot of ways.
So basically this composition doesn't have to be hierarchical in the end, can have cycles.
So then you can, for example, plug in another latent variable to the first one and then connect the other two.
And you can have a structure that is as entangled as you want.
So, for example, in the other paper, we trained a network that has the shape of a brain structure.
So we have a lot of brain regions that are sparsely connected inside and sparsely connected among each other.
And there's nothing hierarchical there at the end.
But you can still train it by minimizing abbreviation of free energy and by minimizing the total prediction error of the network.

1:16:25 _Daniel:_
So you could have for a given motif in an entangled graph, you might see three successive layers that when you looked at them alone, you'd say, oh, that's a three story building.
That's a three layer model that has a depth of three.
But then when you take a bigger picture, there isn't like an explicit top or an explicit bottom to that network.

1:16:52 _Tommaso:_
Yes, exactly.
And this is basically given by the fact that every operation in predictive coding networks is strictly local.
So basically every message passing, every prediction and every prediction error that you send, you only send it to the very nearby neurons.
Okay?
And whether the global structure is actually hierarchical or not, the single message passing doesn't even see that.

1:17:17 _Daniel:_
I guess that's sort of the hope for learning.
New model architectures is the space of what is designed.
Top down is very small and a lot of models in use today, albeit super effective models, although you could ask effective per unit of compute or not, that's a second level question.
But a lot of effective models today do not have some of these properties of predictive coding networks like their capacity to use only local computations which gives biological realism or just spatiotemporal realism, but also may provide a lot of advantages in federated compute or distributed computing settings.

1:18:10 _Tommaso:_
No?
Yes, exactly.
I completely agree.
I think the idea in general is that and I don't know if that's going to be an advantage, I think it's very promising exactly for the reasons you said.
And the reason is that today's models trained with backpropagation, you can basically summarize them as a model train with backpropagation is a function because basically you have a map from input to output and backpropagation basically spreads information back from its computational graph.
So every neural network model used today is a function while predictive coding and other liberative coding, like the old class of functions, class of methods that train using local computations and actually work by minimizing a global energy function.
They're not limited to model functions from input to output.
They actually model something that kind of resembles physical systems.
So you have a physical system, you fix some values to whatever input you have and you let the system converge and then you read some other neurons or variables that are supposed to be output.
But this physical system doesn't have to be a fit forward map, doesn't have to be a function that has an input space and an output space and that's it.
So the class of models that you can learn so basically you can see like feed forward models and functions and then a much bigger class which is that of physical systems.
Whether there's something interesting out here, I don't know yet because the functions are working extremely well.
We are seeing those days with back propagation.
They work crazy well.
I don't know if there's anything interesting in the big part, but the big part is quite big.
Okay.
There are a lot of models that you cannot train with back propagation and you can train with creative coding or.

1:20:05 _Daniel:_
Evidence propagation or other methods that is super interesting.
Certainly biological systems, physical systems solve all kinds of interesting problems, but there's still no free lunch.
An ant species that does really well in this environment might not do very well in another environment.
And so out there in the hinterlands there might be some really unique special algorithms that are not well described by being a function yet still provide like a procedural way to implement Heuristics which might be extremely, extremely effective.

1:20:51 _Tommaso:_
No?
Yes, exactly.
And I think this has been most of my focus of research during my PhD.
For example, like finding this application that is like out here and not inside the functions.
Cool.

1:21:07 _Daniel:_
Well, where does this work go from here, like what directions are you excited about and how do you see people in the octave inference ecosystem getting involved in this type of work.

1:21:22 _Tommaso:_
I think probably the most promising direction, which is something maybe I would like to explore a little bit, is to, as I said earlier, is to go behind statical models.
So everything I've shown so far is about static data.
So the data don't change over time.
There's no time inside the definition of creative coding as it is, as I presented it here.
However, you can, for example, generalize creative coding to work with temporal data using generalized coordinates, as you mentioned earlier, by presenting it as a Kalman filter generative model.
And that's where, for example, the causal inference direction could be very useful because at that point maybe you can be able to model greater causality and more complex and useful dynamical causal models, basically because in general, the Ducalculus and interventional and counterfactual branch of science is mostly developed on small models.
You don't do interventions on gigantic models in general.
So if you look at medical data, they use relatively small Bayesian networks.
But of course, if you want to have a dynamical causal model that models a specific environment or a specific reality, you have a lot of neurons inside, you have a lot of latent variables, they change over time and an intervention at some moment creates an effect in a different time step.
So maybe in the next time step in ten different time steps later.
And I think that would be very interesting to develop like a biologically plausible way of passing information that is also able to model grandeur causality.
Basically.

1:23:24 _Daniel:_
Where do you see action in these models?

1:23:30 _Tommaso:_
Where do I see action?
I didn't think of that.
I think I see actions in those models maybe in the same way as you see in other models because creative coding is basically a model of perception.
So an action is you can see it as a consequence of what you are experiencing.
So by changing the way you're experiencing something, then you can compute, maybe you can simply perform as smarter actions now that you have more information.
But yeah, I don't think action is very I don't see any explicit consequence of actions besides the fact that this can allow you to basically maybe to simply draw better conclusions to then perform actions in the future.

1:24:21 _Daniel:_
I'll add on to that a few ways that people have talked about predictive coding and action.
First off, internal action or covert action is attention.
So we can think about perception as an internal action.
That's one approach.
Another approach, pretty micro, is the outputs of a given node.
We could understand that node as a particular thing with its own sensory, cognitive and action states.
And so in that sense, the output of a node.
And then lastly, which we explored a little bit in Live Stream 43 on the theoretical review on predictive coding.
We were reading all the way through, and it was all about perception.
All about perception.
And then it was like Section 5.3 if you have expectations about action, then action is just another variable in this architecture.
And that's really aligned with inactive inference, where instead of having, like, a reward or utility function that we maximize, we select action based upon it being the, likeliest, course of action, the path of least action.
That's Bayesian Mechanics.
And so it's actually very natural to bring in an action variable and utilize it essentially as if it were a prediction about something else exterceptibly in the world.
Because we're also expecting action.

1:25:48 _Tommaso:_
No.
Yes, exactly.
No.
I like the way of defining actions a lot, actually.
And I still think it has been, like, for example, there are not so many papers that apply this method.
I think there are a couple from Alexander Orobria does something similar, but in, like, outside of the pure active inference, like, applying predictive coding and actions to solve practical problems hasn't been explored a lot.

1:26:19 _Daniel:_
Cool.
Well, thank you for this excellent presentation and discussion.
Is there anything else that you want to say or point people towards?

1:26:30 _Tommaso:_
No, just a big thank you for inviting me, and it was really fun, and I hope to come back at some point for some future.

1:26:41 _Daniel:_
Anytime.
Anytime.
Thank you, Tommaso.

1:26:44 _Tommaso:_
Thank you.
Daniel.

1:26:46 _Daniel:_
See you.
Bye.

1:26:47 _Tommaso:_
Right.
