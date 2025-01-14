
00:06 _Daniel:_
Hello and welcome.
It's September 18, 2023, and it's active.
Guest stream 57.1 with Andy Keller.
We're going to be talking about natural neural structure for artificial intelligence.
There will be a presentation followed by a discussion.
So if you're watching live, please feel free to write questions in the live chat.
Otherwise, thank you Andy, for this.
Really looking forward to it. And to you for the presentation.

00:36 _Andy:_
Yeah, thanks so much.
Thanks for having me.
I'm super excited to be able to present this stuff with Active Inference group.
I'm a fan and very interested, so,
hopefully,
get to have a good discussion and see what you guys think about it.
So my name is Andy.
I'm finishing up my PhD, supervised by Max Welling at the University of Amsterdam, starting a postdoc at Harvard after this.
So I'll start out just talking about the goal of my work in general is to try to bring modern artificial intelligence closer to more human like generalization.
And so what we mean by this is maybe some sort of structured generalization or maybe more familiar to the active inference community, like a structured world model which we believe that humans have.
And the way that we propose to do this is by integrating natural neural structure into artificial intelligence.
So first let's define what we mean by structured generalization.
01:36 So I think it's fairly uncontroversial to say that modern machine learning generalizes beyond its training sets in the traditional sense.
So for example, even the earliest artificial neural networks, multilayer perceptrons, could be trained on data sets of images like this and achieve high accuracy.
Then, when they're presented with a held out test set of images that they've never seen before, they can still classify them relatively easily with the same level of accuracy.
And this is what we typically call generalization.
However, even fairly early on it was noticed that these systems really struggle with small shifts or deformations applied to the images.
For example, [unintelligible] if so, you think, why is this surprising?
And I argue it's really due to our innate ability to perform this type of structured generalization that this example is a failure of.
So for example, this shift is nearly imperceptible to us and we handle it automatically, whereas in these systems it's very clearly a major problem.
02:39 So in words, we can say that structure generalization is a generalization to some symmetry transformations of the input, or in this case, the symmetry transformation is a small shift that leaves the digit class unchanged.
So the obvious question then is, what precisely do we mean by this natural structure and why do we think that
this would help us with these settings?
So first, let's talk about what we mean by natural neural structure.
One way to talk about structure or any type of bias in a system is an inductive bias.
And so an inductive bias can loosely be defined as an apriori restriction of a set of realizable hypotheses.
When you're doing model selection.
More colloquially, we can call this something like before seeing any data, it's a restriction of what and how you can learn.
So very broadly, this can include anything from model class to optimization procedures or even hyperparameters.
And in some sense they really define what is possible to learn.
03:41 And it defines generalization in that you actually can't generalize beyond a training set without having some inductive biases.
And this is explained more thoroughly in.
This paper by David Wolford.
So what we mean by natural inductive biases then is biases that stem from the restrictions and limitations that are faced by natural systems, by the nature of having to live in the real world.
For example, the brain has many efficiency constraints and physical constraints by nature of its construction.
And following this logic, then these constraints are really playing some role in our generalization abilities which currently exceed modern artificial intelligence.
As we'll go into next.
So in this talk, I'll be focusing specifically on two types of structure which my work has studied.
These are topographic organization and spatiotemporal dynamics.
And before I go into my work, I'll give a short example for why I believe that natural structure may be useful to achieve the structure generalization that.
04:42 I was talking about before.
So the first example comes from Fukushima's neocognitron architecture from the 1980s, which was actually built to directly address the problem of robustness to these small shifts in deformation.
So in the paper he writes about inspiration from pupil and weasel's measurements of hierarchy and pooling in order to achieve robustness to these distortions.
And so if you look at the figure he writes u sub s one, U sub C one and these stand for simple and complex cells.
And so this is a fairly radical approach at the time, but it really served to improve robustness and shifts that were plaguing these early artificial neural networks.
And over time these ideas were simplified and abstracted and obviously yielded the convolutional neural networks that we know today, which ultimately drove the success of the Deep Learning Revolution.
So this is really an example of a natural inductive bias which achieved structured generalization.
So for our research, it's really of utmost interest to try and understand what makes these models work so well and see if this principle can potentially be generalized to cover more abstract transformations and symmetries.
05:57 So what makes a convolution achieve this structure generalization?
Intuitively, you can see this is done by applying the same filter or feature extractor at various spatial locations.
So here we see a single convolutional filter being applied at all locations of an image.
This means that no matter where your input is, whether it's kind of in the middle of the image or on the right, you'll have the exact same features, with one exception, they'll be equivalently shifted.
So mathematically, this type of a mapping is called a homomorphism.
It preserves the algebraic structure of the input space and the output space.
In this case, it's with respect to translation.
And at a simple level, something like that will be important to remember for the rest of this talk is that we can verify homomorphisms of our feature extractor if we can see that there's this commutation with the transformation, this commutative diagram.
And so we can write this also algebraically by showing that the feature extractor f commutes with the transformation operator T.
And basically what we want is there to be no difference between first extracting the features and then performing the transformation, or performing the transformation and then extracting the features.
07:07 So the challenges to date is we don't really know how to construct homomorphisms with respect to more complex transformations that we see in the real world.
For example, our brain is able to handle changes in lighting and season naturally.
So here we see lighting on a person's face or the change of seasons.
We can tell it's the same face or the same road.
But we don't know how to build models which respect these transformations.
And so it makes us hard to build systems which handle them in a robust and predictable way.
To give an even more abstract example of what I mean by this and the potential negative repercussions of models which don't handle symmetry transformations, consider modern text to image generation programs.
So in this example, I asked Dolly Two to generate image of a teddy bear on the Moon.
And it does this incredibly well, right?
Probably better than I could.
It has texture fur, incredibly detailed.
However, if I ask it to do something which I see as conceptually simpler, such as draw a blue cube on top of a red cube, it fails to do this.
08:11 And to me this seems unintuitive since the second task seems significantly easier.
But what I'm arguing is that the reason that this is surprising is precisely the same reason that the MNS translation example was surprising.
There is this symmetry transformation happening here, namely the transformation between these complex objects of a teddy bear and the Moon and these simple objects of cubes which we intuitively expect the network to be able to handle and respect.
And we see that it doesn't.
So just like how Fukushima's work showed that these natural structure of hierarchy and pooling of our visual system are effective for making generalizations to small transformations, I argue that potentially higher level structure may be necessary to fix these abstract generalization problems.
And so the question then that I'm studying and that I'm asking is what might this structure be and how do we implement this in an artificial neural network architecture that can actually be used for performing computation?
09:14 So, to begin to answer that, I'll jump into my first line of work on topographic organization.
So topographic organization is observed widely throughout the brain from primary visual cortex to higher level areas.
And it can very loosely be described as this property that neurons which are close to one another tend to respond to similar things.
For example, on the left we show the color coded preference of each neuron in the Macaque primary visual cortex as a response to oriented lines and we see this smoothly varying set of selectivities.
Another type of organization is known as retinotopic organization where nearby neurons in the visual cortex tend to respond to nearby receptive fields.
However, this organization isn't limited to these low level features.
It extends to more complex features such as those present in faces or objects or places.
And this relates to the so called functionally specific areas of the brain such as the fusiform face area FFA and the perihepocampal place area PPA.
10:15 So in this work, the main idea again is that perhaps this topographic organization in some sense which is intimately related to the convolution operation and Fukushima's architecture we can maybe generalize the benefits of this to more abstract transformations in other words, learn how to build more complex homomorphisms that we can't do analytically right now.
So just to show that we're not completely insane with this idea there is some prior work in this domain from people such as Honin Yanlaka Apohevarnan in the early ninety s and two thousand s and they studied how topographic organization may be useful for learning invariances mostly in linear models.
So the question for us when we entered this space is what is the most scalable abstract mechanism that can be leveraged from these approaches which we can integrate into modern deep neural network architectures?
And ultimately we settled on a generative modeling approach which I think might be interesting to the people in this community which then allows us to relate it more closely to topographic independent component analysis with the basic idea being that we can learn a topographic feature space by imposing a topographic prior distribution over our latent variables.
11:34 So just to give a brief background I assume most people are already familiar with this but the kind of general assumption is that the brain is a generative model and this idea in some sense can be attributed to Helmholtz from the 19th century where he said that what we see is the solution to a computational problem.
Our brains compute the most likely causes from photon absorptions within our eyes.
And so as an example, if I show you this image you immediately recognize it as a globe with some curvature.
However, it could just as equally be a disk with a distorted perspective on it.
So this is how we get optical illusions or our images.
So like this one, your brain infers that there is a cube here because of the structure but really it's just.
A flat piece of paper.
So you can think of this generative model aspect as kind of like an inverse graphics program.
In the program, the abstract properties of the sphere are known the position, the size, the lighting and these are used to project the sphere to create the 2D image that is rendered.
12:36 So in effect, what Helmholtz and others are saying is that as a generative model, the brain is actually trying to invert this generative process and doing inference and infer the underlying causes of our sensations.
So the reason I'm kind of belaboring this point is that there's a lot of talk of generative models today, and I'm not necessarily just talking about generating images or pretty pictures.
I really want to mean a framework for unsupervised learning.
So then to get a little bit more into the details, what do I mean by a topographic prior?
So generative models are typically described as a joint distribution over observations, x and latent variables, which we'll call Z.
And this is typically factorized, or one way that this is done is factorized in terms of a prior p of Z.
And this true generative model conditional generative model p of X given Z.
And so one way that we can think about this is that the prior can be seen to encode relative penalties for each type of code that is produced.
13:39 When we invert our generative model, this is called computing the posterior e of Z given X.
And so to develop a topographic latent space, we want to introduce some sort of a topographic prior, which this topographic ICA work showed is equivalent to something like a group sparsity penalty.
So people might be familiar with typical sparsity penalties from independent component analysis.
You want your activations to be sparse, meaning many of them are zero.
So that could look something like this.
You have a bunch of blue squares that are active, but most of them are not active.
But specifically, with a group sparsity penalty, we want these priors to assign lower probability to these distributed sparse activations and higher probability to these grouped, densely packed representations.
You can also think of this like a higher penalty when things are spread out, a lower penalty when things are closer together.
So again, this can be written abstractly like this.
But I want to make clear that each one of these squares here represents kind of a neuron in our model.
14:43 And they're organized in this 2D grid.
So when we're talking about grouping, we really mean grouping in that 2D topology.
So one thing that's really interesting and kind of important is that these priors don't just give us topographic organization, but they've also been noted by people or studied by people like Erosimicelli and Bruno Olshausen to actually fit the statistics of natural data better, specifically natural images.
They've shown that using this type of a prior, you actually get a sparser set of activations, meaning that the prior fits the true generative process a little bit better.
And as we're aware, the brain has a high degree of sparsity and this is believed to be very relevant for efficiency.
So to get a little bit more into the details, to implement this type of a group sparse prior, we use a hierarchical generative model and this is basically introduced by some of the topographic ICA work.
The idea is that you have a higher level latent variable U which simultaneously regulates the variance of multiple lower level variables T.
15:49 And this is how we get group sparsity.
Then to get topographic organization, you can have multiple of these latent variables U slightly overlapping with their fields of influence.
So their neighborhoods, we can call them, and this will give you this smooth correlation structure you're after.
So get the intuition for this.
You see that this variable T over down on the bottom here is not getting any input from this U on the top, but it is sharing a U variable with this T in the middle.
So it's like they're sharing variance, they're sharing some components with their neighbors, but not all components.
And that's really due to this local connectivity of these higher level variables U.
So to keep it simple about how we use this generative model, let's go back to a single U variable.
And the challenge in this type of an architecture which made it difficult for many years is how do you infer the approximate posterior over these intermediate latent variables in this hierarchical architecture?
This is not super straightforward.
16:51 So prior works have used heuristics developed for linear models.
And in our work we found that this really didn't extend to modern neural network architectures.
So really our insight is to leverage a factorization, a specific reprometerization of this distribution.
And so this reprimmatrization specifically is achieved by defining the prior to be what's known as a Gaussian scale mixture, meaning that our conditional distribution of T given U is actually a normal distribution where the variance is defined by this variable U.
And for certain choices of U, this distribution is indeed sparse and encompasses a range of distributions such as Laplacians and student T distributions.
One way of defining it is a Gaussian scale mixture admits a particular repromaturization in terms of independent gaussian random variables Z and U.
So specifically, then we see that this T variable, which was originally fairly complex, is actually just a product of a bunch of gaussian random variables which we now know how to work with much more efficiently in generative models.
17:58 And specifically what we're going to do is so that we can actually get approximate posteriors for U and Z separately and then do a deterministic combination of them in order to compute our topographic.
Variable T.
And this is much easier to do.
So, without going into too many details, the method that we decide to use is what's known as a variational auto encoder, which leverages techniques from variational inference to derive a lower bound on the likelihood, allowing us to parameterize these approximate posteriors with powerful nonlinear deep neural networks and optimize them with gradient descent.
This is going to be familiar to the active inference community.
But really what we've done is instead of having a single encoder and decoder.
As is typical Bayes, we now have two encoders, one for U and one for Z separately.
And then we combine them in this deterministic manner to construct our topographic T variable.
If you see that this is actually the construction of a student's T distribution from Gaussians and then we do this before decoding and then maximize the likelihood.
19:03 Of the data altogether.
So this is the elbow, the evidence lower bound abound on the likelihood of the data and is actually very similar to the variational free energy that is.
Used in the active inference community.
So with these details out of the way, what's really interesting is what happens when we train this generative model which has relatively simple group sparsity penalty in its latent space.
And we want to look at kind of what it's learning in terms of.
Its organization of features.
And first we start with the simplest possible data set.
We have a black background with white squares at random XY locations.
If we train our auto encoder with this group sparsity penalty on it and then we look at the weight vectors of our decoder which we're plotting in blue here, again organized in this 2D grid, we see that indeed they learn to be organized according to spatial location.
So this can be seen as similar to convolutional receptive fields where the receptive field of each neuron is really given by the kind of inputs at its location.
20:08 And this makes sense intuitively from the group sparsity perspective since for any given region, which we highlight, like in yellow here, the filters in a given group are much more highly correlated.
They have these overlapping receptive fields than other random locations.
So essentially we see that our model is learning to cluster activities together in sort of a simulated cortical sheet according to the correlations in the data set.
So instead of in convolution where you're actually doing weight tying and you're manually specifying I want to copy this weight everywhere, you can maybe think of this as like approximate weight tying.
And really we're learning this from the correlation structure of the data set itself.
And just to give a little bit more of a biological inspiration for this, we know that retinotopy is present in the brain.
This is an example of retinotopy and the Macaque visual cortex.
And you can see if you show the Macaque an image like this, it gets projected into this topology preserving space actually on the surface of the cortex.
21:13 So the idea is that topographic organization and even learn topographic organization is preserving the input correlations of our data set.
And potentially this may be beneficial for generalizing these ideas a little bit further.
So like I said at the beginning, it would be even better if we could just learn something more than just convolution, maybe more complicated equivalences.
So how do we do that?
One thing that's clear in natural intelligence is that we don't exist in this world of IID frames, right?
We exist in a world of continuous sequences of transformations.
So maybe we can extend our model to this setting to learn, observe transformations.
This is the idea of temporal coherence.
So what would happen if we just simply extended our previous framework over the time dimension, right?
So instead of just grouping, saying we want our neurons to be group sparse in terms of spatial extent on the cortex, we actually want them to be group sparse over time.
22:19 Meaning that if one set of neurons is active now, we want that same set of neurons to be active into.
The future as well.
If we kind of intuitively think about this, we see that this is actually more encouraging invariance than equivariance.
A way to understand this is we're saying we want the same neurons to be active constantly, but the input transformation is changing, right?
The feet of this little fox are moving.
So if the same neurons are coding for the same thing over and over again, but the feet are moving, those neurons are going to learn to be invariant to the motion of that leg.
Of this dog, for example.
So instead is that.
I went the wrong way here.
So instead, our insight was that this group Sarcity could instead be shifted with respect to time.
So this would mean that sequentially shifted sets of activations would be encouraged to activate together, and then our latent space would really be structured with respect to the observed transformations.
So you can see here that rather than the same set of neurons being active at all time steps, it's really a sequentially permuted set of neurons that we're grouping together in this sparse way.
23:28 And then this allows us to model different observations over time, but they're still connected in terms of learning a transformation and preserving this correlation structure of the input data set.
So if we put this together into our topographic BAE architecture, you can get something that looks like this.
You see that we have an input sequence.
We're again encoding a Z variable and then multiple U variables in the denominator here.
And then each one of these U variables is shifted kind of like we were showing before.
In order to achieve this shift equivalent.
Structure that we're looking for.
When we combine these in this student T product distribution, we get a single latent variable.
This is now our topographic latent variable T.
And now that we have this known structure in our latent space, you can think of it like a structured world model.
We know how to transform this latent space.
In this case, it's by permuting these activations around these circles, doing like a cyclic roll, a cyclic shift.
We know that this is going to correspond to our learned input transformations.
24:31 And we can verify that by saying, okay, what if I continue this input transformation, the true transformation in the data set, which is a rotation.
And then I compare that with how I've done my role in my latent space by moving my activations around in my brain.
And then we decode and we see that we get the exact same thing.
And so this is demonstrating this commutivity property that I was talking about before for verifying homomorphism.
And so to measure this a little bit more quantitatively, we can measure what's called an equivalence loss.
So this is really the quantification of this difference between our rolled capsule activation, our rolling in our head, versus watching the rolling unfold, watching the transformation unfold before us.
So we see that topographic VAE achieves significantly lower equivalent error.
This bubble VAE is what I was talking about before, where it's learning invariance, so it doesn't have the shift operation and then the traditional VAE kind of has no notion of organization or temporal.
25:35 Component, so it performs very poorly.
In addition to this, we see that the model is a better generative model of sequences.
It just gets a lower negative log likelihood on the data set.
So it's better able to model this data set because it has a notion.
Of the structure of the transformations.
We can test this on multiple different transformation types.
On the top row we're showing the true transformation, we hold out these grayed out images and then on the bottom row we encode and then we just kind of roll our activations around and we keep decoding to see what the model has learned as the current transformation that's being observed.
And we see that it can basically perfectly reconstruct these elements of the sequence that it's never seen before.
Additionally, with images that are from the test set that it's never seen before, simply because it knows what the transformation is that it's currently encoding and it.
Can generalize that to new examples.
So the takeaway from this part is really topographic organization.
26:37 We showed that it preserved input structure and now we're showing it can potentially improve efficiency and generalization as we would hope.
So, finally, something that surprised us and I thought was potentially the most interesting is that these transformations that are learned by our model actually generalize the combinations of transformations that were not seen during training.
So, for example, despite only training on color and rotation transformations in isolation, if the model is presented with a combined color rotation transformation at test time, we see that it's able to completely model and complete these transformations perfectly through the capsule role, implying that it's learned to factorize represent to these different transformations and it can flexibly combine them at inference time.
So again, maybe we also don't just get efficiency and generalization, we also get some basic compositionality.
So let's talk about the limitations and what we could do next.
27:37 The main limitation is that there's a predefined transformation that we're imposing in both space and time.
So although we freed ourselves from group transformations and specifically like translation or rotation as is currently done in the machine learning world.
We still have this hard coded latent role in our heads for everything we see.
And to make this a little bit more flexible, so hopefully we can model a greater diversity of transformations, we think maybe we can take inspiration from more structured spatiotemporal dynamics that are observed in the brain.
And so that takes us to the second part of this talk, which is spatiotemporal dynamics that we're going to try.
To integrate into artificial neural networks.
One example of that is traveling waves.
Like I show here.
So what do we mean by that?
Here's a very recent paper where they used a nine tesla fMRI operating at 36 millisecond resolution to image a single slice of a rat brain under anesthesia.
28:41 And what we see is this very clearly structured spatiotemporal activity and correlations.
And these authors of the paper go on to analyze this activity in terms of the principal modes as depicted on the right.
So our hypothesis is that perhaps some sort of a correlation structure like this may be beneficial for structuring the representations of our model with respect to observed transformations, but in a much more flexible way than simply just a cyclic shift.
Like we were doing before.
And let me say that this is not just observed in anesthesized rats.
You can see these traveling waves happen in the mt cortex of awake behaving primates.
So for example, on the left here, they show traveling waves that actually change how likely a primate is to see a low contrast stimuli based on the phase of the wave.
Furthermore, they show that a high contrast stimulus on the right can induce a traveling wave of activity that propagates outwards union primary visual cortex.
29:49 So these are really ubiquitous throughout the brain at multiple levels.
And it would be interesting to study what their implications are for structured representation learning.
In our case, or generally, there is prior work which has studied these types of dynamics and they built models.
So on the top, these are the equations which describe a spiking neural network, which they show if you implement time delays, actually exxonal time delays between neurons, you do get these structured dynamics of traveling waves as long as your network size is large enough.
However, as many people probably know, it's relatively challenging to train spiking neural networks of the same size and performance as deep neural networks.
Similarly, on the bottom, another system which is significantly simpler, but perhaps too simple, is a network of coupled oscillators.
These are known to exhibit synchrony and spatial temporal dynamics and complex patterns.
30:50 But this is called like a phase reduced system and doesn't quite capture the full complexity that we're interested in.
So we're looking at something that's potentially in between these two.
And what we settled on is this work, in this work is to parameterize a network of coupled oscillators slightly more flexibly than a Kuramoto model.
So this.
Is really built on this coupled distillatory recurrent neural network of Constantine, Rouge and Nisha, where they basically took the equation which describes a simple harmonic oscillator.
It's a second order differential equation.
The acceleration on a ball on a spring is proportional to its displacement.
You can add additional terms such as damping so that the oscillations slowly die out over time.
You can drive this oscillator with an external input to kind of counteract this damping or to give slightly more complexity to the dynamics.
And then furthermore, if you have many of these oscillators, you can couple them together with these coupling matrices W, as we demonstrate kind of in this picture here.
31:55 So you can really think of this network as a bunch of balls on springs and they're maybe connected to each other also by springs or elastic bands, whatever.
The couple, the Silatory recurrent neural network of Rush and Mishra with these various terms.
And this has been shown to be very powerful for modeling long sequences.
They also mentioned they were inspired by the brain building this.
And there's a lot of good analysis in that paper.
For example, they show that this has really beneficial properties with respect to vanishing gradient problems that typically happen in recurrent neural networks.
But if we want to look at spatiotemporal dynamics in this type of a model, it's slightly challenging because these coupling matrices here, the W's that connect each oscillator's position to one another, these are densely connected matrices like I've tried to.
Depict on the left here.
So if you try to visualize the dynamics of this network, you don't see any spatial organization.
There's no inherent topology to the latent.
Space of this model.
32:56 So you can think of this like in our previous example.
A neuron is connected to a potentially arbitrary set of other neurons.
Those neurons are connected to another arbitrary set of neurons.
And you'll just get oscillatory dynamics, certainly, but kind of fluctuations that don't make a lot of structured sense in our work.
Then we thought, okay, how can we convert this more to the types of dynamics that we're interested in, this structured propagation of activity?
And one clear way to do that is to have a more structured connectivity matrix W, which we found is easily implemented and efficiently implemented through a convolution operation, which you can think of like a locally connected layer.
So instead of having every neuron connected to every neuron, neurons are just connected to their nearby neighbors.
After training, you'll end up getting something.
That looks like a smooth spatial temporal dynamics.
So to be a little bit more clear, to train this model, we take this second order differential equation that we were describing before you discretize it into two first order equations.
You can think of this as like numerically integrating the ode.
34:00 We now have a velocity and then we update and we can train this model as something like an auto encoder or an autoregressive model.
So we take an input, we encode it to our latent space.
Really, the input is this F of x term which acts as the driving term.
So it's like driving these oscillators from the bottom and then they have their own dynamics which are defined by the coupling terms, these local couplings.
And then at each time step we take this latent state, this wave state, and we decode to try and reconstruct the input.
Maybe at the current time step or a future time step, we can do some analysis of these models during training to see what happens before training.
And after training, we can compute the phase and the velocity of the dynamics in the latent space.
Basically, we see at the beginning of training there's no waves in our model.
But after training, after 50 epochs, we see that there's these smooth structured activity propagating downwards in service of this sequence modeling task that we're doing, like rotating objects.
35:04 So what's the benefit of this?
I mean, the whole reason I motivated this was to say we wanted to have more flexibly learned structure.
Are we actually doing that or are.
We just getting pretty waves?
So what we showed in our paper is that we really are learning some sort of useful structure.
And the way we showed that is, again, with something like this commutative diagram.
If you take an input and you encode it and you get a wave state and then you propagate waves artificially in that wave state and then decode, you can observe that it's actually exactly the same as if you had just by showing a bunch of different images of different transformations.
So a lot of different digits, different features.
And we see that we get different types of wave activity in each case in order to model that different transformation.
If we train it on different data sets as well, we similarly see more complex dynamics.
In this case, maybe not even traveling waves or standing waves, which can be thought of as traveling waves in opposite directions.
So we see if we're modeling these orbital dynamics, we get these kind of smoothly moving blobs of activity in our latent space.
36:07 If we're modeling a pendulum, we similarly get kind of complex oscillatory activity so it's preserved input structure, but additionally more flexibility than we had before, which is kind of our ultimate goal.
So finally, I want to talk a bit about how I think the outcome of this research may not only improve artificial intelligence, but also how it helps us understand why our measurements of the brain look the way they do.
So to give a brief example of what I mean by this, I talked a bit about before, about these and places.
So in this fantastic work with HIE Gao, we studied if our simple topographic prior, as we discussed, may be able to reproduce these same effects.
So specifically, we plot the value of this Cohen's D selectivity metric for each of our neurons with respect to a different data set of images potentially containing just faces or just objects or bodies.
And so we measure for every neuron, is it more likely to respond to faces or the ration emerges in the brain?
37:09 But I do think that it tells us that the relative organization of selectivity may at least be partially attributable to correlation statistics in the data after being passed through a highly nonlinear future extractor.
Such as a deep neural network.
So, in a similar vein, something that's interesting, there's a known what's called tripartite, or the visual stream.
So images of or objects are selectivity with respect to objects is organized by more abstract properties, such as animacy, is this thing alive or inanimate versus also real world object size, like what is the size of a teapot versus a car?
And what we see is that in humans, this selectivity is organized in this tripartite structure.
You typically have small objects that are in between animate and inanimate objects in terms of their selectivity.
And we see the same thing kind of happens here.
So these are measuring the selectivity of the same set of neurons, but with respect to these different sets of stimuli.
38:10 We see that the small cluster is in between animate and inanimate cluster.
And again, this happens for multiple different initializations.
So this is something I hope we can explore a bit further for this community.
I think it's interesting because it's really a way of showing that we built a structured world model.
And potentially, this world model is beneficial for better representing real world data in.
A structured way, and you get lower free energy in that sense.
So by developing these models like we showed here, we may get insights into new mechanisms for how this structure emerges, including topographic organization that we never thought of before.
So, machine model, I was looking at the orientation selectivity of neurons, which I wasn't particularly expecting something to happen, but you're looking at kind of these waves propagate over this simulated vertical surface.
And I thought, okay, maybe I'm showing rotated images.
Maybe this has some effect on the orientation selectivity.
39:13 And actually, if you go in and you measure the selectivity of each neuron with respect to these differently oriented lines, what you see is that it's surprisingly reminiscent of the orient paper columns that are seen in primary visual cortex.
This is stuff going back to Hugle and Weasel.
And this is something that just kind of came out of this model and the fact that it has the spatial.
Temporal structure with respect to transformation.
So, of course, this is a really coarse analogy, but I think this is an example of how building these types of models can help us think about how the brain builds representational structure and the way it's organized in a way.
That maybe we haven't thought about before.
I think I'm not the only one who's doing this type of work.
And so I want to talk a little bit about some other people who are doing this.
So I've been talking about this equivalent structure.
People such as James Whittington and Tim Barrons and Surge Anguli have shown recently that by introducing algebraic constraints into a learning process, in this case, it was like the motion of an agent in an environment.
40:21 By saying, you need to preserve kind of this algebraic structure of if I move in a circle west, north, east, south, I end up back at the same point.
Again, by introducing these types of constraints, you get the emergence of grid, cell like representations.
So I'd be interested to see how this idea of representational structure can help us explain maybe more than our scientific findings we're finding as well and how this relates to generative models as a whole.
And then finally, I think there's something to be said about cognitive plausibility of these models as well.
Maybe we're not just going to be testing them from a neuroscience perspective, but also from a cognitive science perspective.
For example, there's these Ravens Progressive Matrices on the left where you have to say which one of these images is more likely to fit in this pattern?
Or for example, how likely is it that this Jenga Tower falls over when you pull a specific block or with a given structure?
41:21 And I think these types of tests are really testing if our world models that we're building are similar to the types of models that we innately have our own common sense as humans or as beings living in a natural world.
And I've done some preliminary work in this direction, I think very preliminary and not nearly this complicated, but trying to model visual illusions.
So if you take a really simple data set of a moving bar stimuli or a static bar frame and you move it a little bit, you can see that the model will actually infer that missing frame and then actually also infer continued motion.
So it's like overshooting the trajectory of what the actual stimuli is providing it before correcting again.
So I think modeling illusions is certainly an interesting way to study if our world models are similar to the types.
Of models that we have ourselves.
So in conclusion, yeah, I think topographic priors we could show that they effectively learn structured representations or structured world models.
42:25 This learned structure is flexible and adaptable to arbitrary transformations, unlike traditional equivariance.
And topographic riders can be induced statistically as we did in the topographic VAE or through dynamics like we were showing in these neural wave machine type models.
So to conclude, I'll leave you with this quote that I found in Fukushima's paper from 1980 I thought was pretty far ahead of its time, where he says, if we could make a neural network model which has the same capability for pattern recognition as a human being, it would give us a powerful clue to understanding the neural mechanism in the brain.
So that's kind of, I think, some.
Of the goals that we're going for here.
So I'll say thanks to my advisor Max, my co authors Patrick Yue, Emile Jinghe, and Yorn, and interested in discussion.
Thanks.

43:24 _Daniel:_
All right, thank you.
Great.
Very interesting presentation.
A lot of places to start.
Maybe just what brought you to this work, a little context on how you came into this work for your PhD direction.

43:43 _Andy:_
Yeah, I mean, there's been studying the group that I'm in at the university has been studying structured representations from mathematical point of view for a while, and we're some of the people to models.
Or for the variational auto encoder.
And I guess what something that had always been the model that respects rotations, 2D rotations perfectly well.
But if we want to do 3D rotations, we can't do that because that's not a group in terms of a.
Projection onto a 2D plane.
You're losing information when this thing rotates.
Around, for example.
Or just any sort of natural transformations.
Like I was trying to point out at the beginning, I think it was trying to think about how the brain models natural transformations is something that these.

44:35 _Daniel:_
Current frameworks where do you see action playing a role in terms of variational, auto encoder models that include not just external patterns, but also the consequences of action or world model structure with action.

44:55 _Andy:_
Right, yeah.
No, it's a good question.
And I think active inference is effectively I think it's a good answer to that.
I know there are reinforcement learning frameworks that do use kind of externally trained world models.
So you train a VAE or something and then you use that representation in.
Your reinforcement learning system.
But I think having a fully kind of a system that is a single.
Objective with action as part of the.
Likelihood of the data, I think that's much more elegant.
I'm a big proponent of that.
I have not gotten so far as to study how these structured world models in a VAE or I haven't worked.
On that at all.
But I think it would certainly be very interesting to see if having a.
More structured world model in a variational auto encoder would be beneficial in an.
45:56 Active setting as well.
I think that would be awesome.
I mean, I think some of these examples, like, showing before, like, emergence of.
Grid cells and things like this, maybe.
Point towards that direction of, hey, maybe the brain is doing something.
It really obviously has a lot of structure.
This clearly has to be useful for performing actions in some way.
Cool.
Yeah.

46:20 _Daniel:_
I thought a really nice parallel that you brought in with the talk was the locally connected units enabled your models to structurally embody the convolutional constraint and pattern, and that led to these arising patterns.
And then analogously, there was the Doral et al.
Where they had the path exploration constraint.

46:46 _Andy:_
Right.

46:47 _Daniel:_
And so then it's interesting to think about these action or policy heuristics or sparsities like a joint motor exploration.
Eventually it becomes understood that there's like two mutually opposing ways to move a joint, and then the compositionality across joints can be learned at these higher levels once it's locked in at lower levels.
So it's a very appealing and niche relevant way to generalize because it's both based upon the actual constraints of the world, but then especially through action, potentially embedding something that's quite simple.

47:31 _Andy:_
Right?
Yeah, no, I think that's definitely true.
That's a really good point.
If you do have constraints coming from.
Your actions themselves, then that would be hugely beneficial for helping to structure your latent space.
And I think yeah, I guess one thing I wanted to mention there's something made me think of, like, Stefano Fousey's work on kind of the representational geometry determines how generalizable a given understanding of a system is.
And I think if you can understand if these sets of activities are separable or highly parallel separable with a linear classifier, essentially, then you're going to be able to do generalization.
And I think by imposing these types of biases or potentially through constraints that are imposed by action, something like this, you are yielding or kind of inducing a better representational geometry.
48:33 And this has all sorts of benefits for compositionality or generalization.
It's a great point.
Cool.
Yeah.

48:41 _Daniel:_
Very interesting area.
All right, I'll read some questions from the live chat love Evolve wrote any practical or observed limitations on modeling illusions?

48:58 _Andy:_
Deep learning, community uses.
They're not foveated.
You don't have a center of gaze, and you also don't have most convolutional neural networks.
I'm using these kind of recurrent neural networks, but time is not as clearly defined in these models as it is.
In a continuous time setting for human undergoing an illusion trial.
And I think the combination of these two, of the fact that as a human, for most things, you're shifting locations and your gaze are dependent on you looking to a particular area, a lot.
Of cognitive science tests.
And so I think it would be really helpful if we had models that you can think of this as a type of action of learning where to move your gaze.
One of the simplest possible that would help a lot for being able to model illusions.
And just I mean, for me, it's like I read a paper of some cognitive science experiments or about some illusion, and I think of, okay, can I put this data set into my model and test it?
50:07 And most of the time the answer is no, because I don't have a.
Model that looks around or has a restricted field of view, something like that.
So, yeah, I think that's one of the limitations.
Another one is makes the experiment much more complicated.
So that's one of the practical limitations.
Wow.

50:28 _Daniel:_
Great answer.
Makes me think of a paper with letters rotating on a table.
That's the digit rotation.
Great points about the Foveation and the dynamics of the illusion.
I think you actually did mention an illusion, which is however, you mentioned in the generalization context, which is rotating on the two dimensional screen doesn't generalize to three dimensions, and that dimensional collapse or reduction is the basis of the cube projection illusions and cube and figure rotation illusions.
It's on your screen and there's a silhouette or there's some ambiguous stimuli that it's near a criticality or a bifurcation in the generative model.
So it could represent it one way or another way.
And so a lot of the switching illusions are just based upon the flatness of images and the limitations in generalization that are revealed by.

51:32 _Andy:_
Some work sorry, there's some work where they can argue people have a kind of three dimensional.
Image in their heads.
Like even Nancy Kenwich had her library on this recently and showing yeah, I don't know.
Do our models have that?
It's not super clear anyway.

51:51 _Daniel:_
Yeah, that's pretty interesting.
All right.
From Upcycle club in the chat, they wrote Kudos.

51:58 _Andy:_
You're able to learn nearly as effectively.
If you imagine you only want a single neuron to be active for every example.
Your model is going to be trying to memorize the data set to some.
Extent or something like this, and you're not going to have enough capacity.
So, yeah, I think tuning that level.
Of sparsity is certainly an important factor.
And when you look at the likelihood, if you're calling framework, typically this is balanced automatically with the likelihood itself.
If you're not doing generative modeling, you just have a sparsity penalty.
You're going to want to tune that parameter.

52:38 _Daniel:_
Okay.
They added just to clarify runaway behavior in Armina, where the network becomes unstable or chaotic due to various factors such as feedback loops, noise, or adversarial inputs.

52:52 _Andy:_
Yeah, I guess I haven't looked at this in a recurrent setting where you would get feedback loops, but I could see adversarial examples being potentially affected by your level of sparsity.
The interesting point is, would you be more susceptible or less susceptible to adversary examples?
I don't know.

53:16 _Daniel:_
Well, sparsification projecting from a fully connected, higher dimensional model just into progressively smaller it's pretty well understood in general what the trade offs are.
It's easier computations, a smaller model, sparser.
The Bayes graph is going to be clearer to represent and then also it will have all of the other trade offs with false positive and negatives of generalizing.
But that's why it's an iterative fit process.
So I guess how does your sparsification approach balance?
Does it use AIC or BIC or some other model fitting approach to determine the relevant sparsification for a given input?
How do you determine in Lasso regression, how do you threshold how many how sparse you want it to be?

54:17 _Andy:_
Right, yeah, I think there's a lot of good literature on this, and even so, some people like DembaBa at Harvard.
And some people I'm working with now have done these kind of unrolled iterative sparsification networks where it's like a recurrent neural network and iteratively sparsifies.
And you can show that this yields.
Something like relus or.
Group sparse activations like we're using here in this setting.
It's really just by having this construction of this T variable where we have Z on top and then it's in some effect gated by the sum of U variables in the bottom.
So, w maybe I wasn't super clear about this is a matrix that is connecting.
That's what defines the groups when I'm defining the group sparsity, that connects all of these U's together.
55:21 And so the idea is like here.
If all of one of the other.
Examples, if all of your U's are not active for a given T, or if all of your U's are active for a given T, that T variable is going to be very small, right?
Because your denominator is going to be very big, and that induces sparsity.
So it's like constraint satisfaction.
If you have a set of U's that are all small, then that that constraint is satisfied.
And now Z is allowed to kind of express itself and that's what then kind of achieves the sparse activation.
So this is induced by these two KL divergence terms here.
These are saying like, how far is each U and each Z from a gaussian?
And then through this construction of the student T variable, we're effectively constructing a sparse prior distribution just from these Gaussians.
56:23 But in terms of the actual objective, the terms and the objective that we're optimizing are just these two KL terms.
That are pushing it towards sparsity to some extent.
And this is balanced automatically with the.
Likelihood term here through the decoder.
So we don't have terms that we're tuning, but we're learning the parameters of.
These different encoders and then analyzing the failed urgencies.

56:48 _Daniel:_
Cool.

56:49 _Andy:_
All right.

56:50 _Daniel:_
Another question from Dave Douglas, who wrote speaking of gaze and illusion.
Can the studies on constancies in infants be separated into lower level illusion, relative, perhaps higher level conceptual constancy?
Can you read the current kind of architecture?
Might the studies on constancies in infants cognitive constancies, be separated?

57:26 _Andy:_
Yeah, probably.
I'm not an expert or actually even very familiar with object permanency studies and.
Infants and constancy stuff, but I think.
That would be incredibly interesting to study in neural network architectures.
And that was kind of some of the idea with this illusion that I was trying to model down here with this line.
I don't know if I was super clear about this, but the top row is the input, and we're effectively like blocking the input for a single frame.
And I wanted to see, does the network kind of encode that the thing is still there when that frame is gone?
Can I still decode the presence of.
The object from the neural activity?
And then what is it also inferring about the motion because of the fact that it saw the bars at a.
Slightly different location than from before after the frame is gone.
So, yeah, I think there's definitely multiple levels to it where some would probably be much lower level and maybe long term object permanency, I would guess would.
58:36 Be significantly higher level.
It just makes me think of those.
Experiments with cats back in the day.
Where it's like they raised them in darkness except for an hour a day.
They put them in vertical world or horizontal world where they only saw horizontal lines or vertical lines, and you can see the organization of their cortex changes, like they have less receptivity to horizontal lines if they've never seen horizontal lines before.
And then you take a stick and you wave it in front of their face, and if the stick is horizontal, they do nothing.
If it's vertical, they're swatting at it.
They'Re trying to hit it, it's like.
They just literally don't hunzle bar in.
Front of their face.
So I think in that case, then, this is evidence of a low level efficiency in vision contributing to some sort of an illusion.
So I think, yeah, there could certainly.
Be some aspect to that in infants as well.

59:33 _Daniel:_
One very curious point you brought up was the animate and inanimate manifold with small things being intermediate, right?
What does that represent?
Or is it because they're handleable or it might be an insect or it might be something that might move away just with wind or what does that say?

1:00:01 _Andy:_
Right, yeah, so this is work by Talia Konkel, I think was the one who discovered this organization and they tried to figure it out.
I might be getting this wrong, so I recommend people to read her work on that.
They call it Tripartite organization.
But if I remember correctly, they did a lot of follow up work on why there's this organization and some evidence of curvature of these objects and kind of like the distance that you see objects from or like animate objects are maybe more curvy or regardless of what the actual answer is, there were a lot of different hypotheses that were stemming from properties of these objects.
Maybe mid level or low level properties, more so than higher level properties.
I still don't know if it's exactly been solved of whether it's like, interaction, like you said, with the objects causes the separation or the general shapes of these objects.
1:01:10 I would bet, as with most things, it's like some combination of all of the above.
But I think the interesting thing from this modeling point of view is that this is only trained on correlation statistics from the image data sets itself.
This has no interaction, this has no notion of animacy.
I mean, this is really just training a model on ImageNet, just images of dogs, cats, boats, whatever, and yet it still achieves this type of organization.
So there's some sort of it could be semantic characteristics, right?
We have a network that can classify boats versus dogs versus 20 other breeds of dogs, but it might also have.
Some correspondence with lower level image statistics as well.
So?
Yeah.
I don't know.
I guess he's my answer.
Yeah.

1:02:04 _Daniel:_
Provocative analogy was the translational shift in the MNIST in the handwriting recognition setting.
What are the translational shifts that exist today?
What's the three pixel example?
Is that some prompt engineered attack on an Lom or something?
Or something.
A special character being inserted, or some overlay on an image that we can't even detect.
So what do you think those challenges are and what are ways that we can pursue that?

1:02:44 _Andy:_
Yeah, absolutely.
I mean, I think kind of the way I was thinking about it is like these symmetry transformations.
If you're thinking about language models, you can imagine a symmetry transformation is just like replacing a word with a synonym or something.
You have the sentence to us means the exact same thing, but now suddenly.
The model is going to respond very differently.
Or like translation between languages, this can.
Be seen as a type of transformation.
It preserves the underlying meaning of the input to us, but to the model.
It looks completely different.
And we would like to have models which behave in a predictable way with respect to these types of transformations, because I think humans behave very predictably with the type of these transformations.
And when we're dealing with AI systems, we expect them to also behave that way.
And I think that's part of what causes a lot of challenges interacting with these systems.
1:03:47 And I kind of tried to do a rough cheeky demonstration of that with.
This bear and squares and stuff.
We expect it to be able to do something simple like this because we think most humans could, and yet it doesn't.
And if you imagine this is a.
Critical scenario where you expect this, then that's a big problem.
How do we handle that?
I think that's kind of what I'm searching for.
I think.
My direction I'm taking it is look more simple, kind of like bottom up building blocks of neural network architectures or algorithms that kind of yield these emergent structural properties.
And I think that's a much more generalizable way.
Rather than building something on top of.
What we already have, I think that's.
Something that would scale much better and.
Also matches more what the brain does.

1:04:50 _Daniel:_
Very cool.
One kind of implementational question.
What are the computational requirements of just running this, or what's the day to day like of being a student or researcher running variants of these?
Like, do they use terabytes of data and you're using large computation?
Or is this something that people can run on their own laptops?

1:05:11 _Andy:_
I think almost everything I presented today can be run locally.
So this stuff is super simple.
You can run you can run it on.
Your laptop.
If you want to train and experiment with different things, it's going to be pretty slow.
So I'd recommend some commercial GPU.
I run pretty much everything on like Nvidia 1080s, pretty old, pretty cheap, but they have twelve gigs of Ram or whatever, and it's kind of more than enough for these models.
Gigabytes of Ram I think one thing that some people think is weird is I do most of my experiments on stuff like MNIST.
So it's 32 x 32 pixel images because I can train it small.
And locally, if you want to do.
Stuff, my experiments are on mnists.
If you want to do stuff like this, these are much more complicated.
This Hamiltonian Dynamic suite here, you're getting into bigger models that are running across multiple GPUs.
And so here I was using a cluster to run these types of models.
1:06:14 But I say most of the single machine with the GPU is more than enough.
Or even just like in a collab.
Notebook, something like that.
If you want to train something on ImageNet, it gets more complicated and you need at least one GPU, ideally more.
But yeah, I don't do a whole lot of big scale stuff yet.
I think it's certainly interesting and there's definitely a lot more you can do there.
But for some of these kind of simpler or more fundamental questions, I don't.
Know what you want to call it.
A smaller machine is nice and fast.

1:06:52 _Daniel:_
Cool, useful.
All right.
I'll read a comment from Dave recalling Bert Devries'comment during the Applied Active Inference Symposium about the desirability of spending less effort or ATP on foraging or control situations where we don't need much precision.
I don't know if you listen to this, but Professor DeVries mentioned about variable precision models and how they could be used to enable different features of generalization and actual structural course training as well as reduced computational requirements.
Does he have any suggestions on how to introduce this distinction into active inference theory?
What kinds of experiments could winkle this out?

1:07:38 _Andy:_
Oh, wow.
Yeah, that's something I don't think I have too much intelligence to say about, to be completely honest.
Hmm.
It's super interesting question because I think the intuition makes a lot of sense to me that you're talking about, if I understand correctly, variable rates of vision when you're encoding or in your model in general, doing computation that somehow has an impact on your future performance as a relation to some energy store.
I think if you wanted to build this into an active inference system, you would need to have really an embodied system where the agent has some notion.
Of energy, like an internal energy store, and.
Something that is trying to conserve while it's performing its actions and running out of energy would need to mean.
1:08:42 Something bad for the agent.
And then maybe you could observe kind.
Of an emergent reduction in encoding precision or something like this as the agent is trying to learn to act more.
Effectively, you might have to give it.
An ability to control its precision.
Yeah, like I say, out of my thoughts.

1:09:09 _Daniel:_
Okay.
On this slide right here, first, very cool image.
It's kind of like a digital Jackson Pollock.
If it were a simpler input data size or just reduced complexity of patterns, or if it were an increased complexity, how would this image look different?

1:09:31 _Andy:_
Yeah, so I did some experiments trying to change these orientation columns and basically changing the parameters of the model.
You can get these columns to be bigger.
You can get them to not have very similar structure to what we see in the humans, where you can get them to have more bands of activity.
And it also, like you said, it depends on the data set that you're using.
If I use really simple sinusoidal gradings as input, I get something like this.
I get something that's a little bit more rotational, curvy, higher entropy.
So I think these are all interesting things if you want to study the emergence of this type of organization in a natural system.
If you have a model that now yields different organization for different settings that see, okay, then what settings best match our observed data?
1:10:34 I can send those around if you're interested.
But I think one other interesting point there is that the different animals and types of orientation selectivity and different numbers of pinwheels.
Some animals don't have it at all.
I think maybe mice, if I'm correct, have this kind of they call it salt and pepper selectivity.
So it's basically random.
You don't have any sort of, like, topographic orientation selectivity.
So there is evidence that different systems.
Do this differently, and it's interesting to figure out why.

1:11:14 _Daniel:_
Yeah, this very cool.
It reminds me of, first, the reaction diffusion, space and time.
So it's actually possible that a region might have no activity from a given granularity, like if it was being looked at at fMRI spatial and temporal timescale.
But if the pockets of activity are slower, faster, then that measurement is going to not be different than noise.
It'll all have been averaged out.
So then there might be some interesting data sets that do actually have a lot of richness, but then for one reason or another, it just was averaged out over because it wasn't being connected.

1:12:10 _Andy:_
To you or something like this.
You really need to go at the single trial level.
You need to have high enough spatial resolution such that it satisfies Nyquist frequencies.
And this just is something that people didn't do for a long time, especially if you're doing single electrode recordings.
You're not going to see a traveling wave.
You're going to see oscillations.
You need, like, multi electrode arrays.
And basically they're saying, okay, yeah, now that we have the technology to do.
This, it's much resists that we didn't see before.
And potentially, this is an explanation for a lot of the noise that we were seeing before.
Maybe it really is just traveling waves.
So yeah, I think there's a lot to be done in the future with.
Increased abilities for recording.

1:12:56 _Daniel:_
That's very cool.
Well, any final thoughts or questions or where are you going to take this work?

1:13:06 _Andy:_
Yeah, no.
Thanks for having me.
Hopefully in the active infrastructure direction.
I would love to.
I think it'll be super fun.
So yeah, I'm not really sure.
I'm looking at maybe music right now, looking at other kind of crazy directions.
I don't want to sound too crazy, but I'll go down.
Yeah, a lot of things.
So one thing that's coming up, something we submitted to Neurops is studying memory with traveling waves.
So that paper just came out on.
Archive today of how waves are really good at encoding long term memories, which.
I think is super interesting.
So I might go a little more in that direction.

1:13:55 _Daniel:_
Sounds good.
And yes, would be very exciting to see action come into play when there was the neurons that stayed active even as the dog's feet were moving.
There's a lot of action sequences, like throwing a baseball, and then it goes, and it's like there's something about that action that's continuing to influence it's to having, like, a deep temporal representation of alternative actions.
And then the variational auto encoder is already basically the right anything like that.

1:14:35 _Andy:_
Really appreciate it.

1:14:36 _Daniel:_
All right, thank you.
Till next time.

1:14:39 _Andy:_
Thanks so much.
Bye.
ven granularity, like if it was being looked at at fMRI spatial and temporal timescale.
But if the pockets of activity are slower, faster, then that measurement is going to not be different than noise.
It'll all have been averaged out.
So then there might be some interesting data sets that do actually have a lot of richness, but then for one reason or another, it just was averaged out over because it wasn't being connected.

1:12:10 _Andy:_
To you or something like this.
You really need to go at the single trial level.
You need to have high enough spatial resolution such that it satisfies Nyquist frequencies.
And this just is something that people didn't do for a long time, especially if you're doing single electrode recordings.
You're not going to see a traveling wave.

1:12:28 _Andy:_
You're going to see oscillations.

1:12:30 _Andy:_
You need, like, multi electrode arrays.
And basically they're saying, okay, yeah, now that we have the technology to do.

1:12:35 _Andy:_
This, it's much resists that we didn't see before.

1:12:39 _Andy:_
And potentially, this is an explanation for a lot of the noise that we were seeing before.
Maybe it really is just traveling waves.
So yeah, I think there's a lot to be done in the future with.

1:12:52 _Andy:_
Increased abilities for recording.

1:12:56 _Daniel:_
That's very cool.
Well, any final thoughts or questions or where are you going to take this work?

1:13:06 _Andy:_
Yeah, no.
Thanks for having me.
Hopefully in the active infrastructure direction.
I would love to.
I think it'll be super fun.
So yeah, I'm not really sure.
I'm looking at maybe music right now, looking at other kind of crazy directions.
I don't want to sound too crazy, but I'll go down.
Yeah, a lot of things.
So one thing that's coming up, something we submitted to Neurops is studying memory with traveling waves.

1:13:43 _Andy:_
So that paper just came out on.

1:13:44 _Andy:_
Archive today of how waves are really good at encoding long term memories, which.

1:13:50 _Andy:_
I think is super interesting.
So I might go a little more in that direction.

1:13:55 _Daniel:_
Sounds good.
And yes, would be very exciting to see action come into play when there was the neurons that stayed active even as the dog's feet were moving.
There's a lot of action sequences, like throwing a baseball, and then it goes, and it's like there's something about that action that's continuing to influence it's to having, like, a deep temporal representation of alternative actions.
And then the variational auto encoder is already basically the right anything like that.

1:14:35 _Andy:_
Really appreciate it.

1:14:36 _Daniel:_
All right, thank you.
Till next time.

1:14:39 _Andy:_
Thanks so much.
Bye.
