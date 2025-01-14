
00:06 _Daniel:_
Hello and welcome everyone.
It's Active Inference guest stream number 48.1 on July 19, 2023.
We're here with Arthur Giuliani and Adam Safron, also joined by Michael Edward Johnson in discussion.
We're going to have a presentation and then a conversation about deep canals, a deep learning approach to refining the cannilization theory of psychopathology.
So thank you all for joining and looking forward to this presentation and discussion.

00:40 _Arthur:_
Thanks Daniel.
I'm very happy to be here with Admin Mike to talk about this work and to discuss more broadly this general direction that's emerged over the past few years to try to utilize some of the concepts from the active inference world and computational modeling more generally to understand what's going on both in psychopathology and in psychedelic therapy.
Yeah, so I'll give a brief presentation and we'll move into a kind of more general discussion of this work.
It'll start with some kind of general considerations around psychedelic therapy, some of the neuroscience of psychedelics, and then move kind of more specifically into the model.
So there is this class of drugs, these serotonergic psychedelic drugs, which include psilocybin, DMT, LSD and others.
And the past decade has seen a resurgence of interest in psychedelic therapy, psychedelic assisted psychotherapy, where one or multiple of these drugs is used in conjunction with a kind of psychotherapeutic protocol.
And there's been a lot of investment of money and time and clinical resources into utilizing these drugs for treatments depression, anxiety disorders, substance use disorders and others.
And there seems to be quite a lot of positive signals suggesting that these kinds of therapeutic interventions can actually be quite effective.
So there's a number of studies suggesting that psilocybin assisted psychotherapy can be helpful for depression, anxiety, substance use disorder and others.
And as this work advances, there are more and more larger clinical trials comparing it for example, to the standard treatments with SSRIs, with multiple studies suggesting that pilocybin assisted psychotherapy is at least as effective as the Lexapro kind of standard of care.
All of this seems to suggest, and the timelines are kind of pointing at this idea, that psilocybin treatment for major depressive disorder may be only a couple of years away from becoming approved as an actual treatment in the United States.
Which means that it's quite important for us to understand what's going on mechanistically in the brain so that these kinds of treatments can be best optimized, best determined how to be used for which kinds of mental issues people might be having, and under what kinds of treatment protocols we might expect the most success.
I think this will also ultimately, hopefully lead to the development of even better drugs, even better treatment protocols and much more personalized care.
So some of the basics of how these drugs work on the brain for those who are unfamiliar, so these are the serotonergic psychedelics.
They are serotonergic because they act as agonists for a number of serotonin receptors in the brain and the central nervous system.
More broadly, it's thought that most specifically these drugs like psilocybin work through agonizing, the serotonin five H T two A receptor.
And this has been demonstrated multiple times by using blockers antagonists of the five H T two A receptor which seem to largely remove the effect of psilocybin or other psychedelic drugs.
And what this two A receptor does when it's agonized is it excites the neuron, making it more likely to fire.
And this is kind of essential to some of the downstream effects.
So given that it seems that this two way receptor that psychedelics are mainly targeting, the question then becomes well, where in the brain are these two A receptors?
Most widely expressed?
And research has focused on, I would say, three kind of key areas over the past decade or so.
The first being the thalamus, which is a region involved in the gating of sensory information into the cortex.
There's a lot of expression in the cortex itself, expression for example, in the visual system, which is perhaps not surprising given the prevalence of visual hallucinations and psychedelic use.
But therapeutically a lot of focus has been on the prefrontal cortex where there is also a dense expression of these receptors.
And then also more recent work has looked at the claustrom which is a small brain region responsible for coordinating the transition dynamics of cortical activation.
And this too is likely of central importance to the psychedelic effect.
So kind of moving up one level of abstraction to fMRI studies, there are a few kind of like key takeaways which have been identified from a few different fMRI studies looking at psychedelic use.
Kind of the main theme has largely been this idea of increased entropy or increased complexity of the cortical activation in the brain.
So there are various measures of this.
On the right here there's a figure of one of the common measures of complexity and looking at various different kinds of states that an individual might be in and how that relates to complexity.
So you have individuals in vegetative states or anesthesized states having relatively low brain activity complexity, you have individuals in awake states having higher complexity and then individuals who have ingested either psilocybin or LSD showing the highest brain complexity.
Now, along with this, rather than just this kind of like single unified score, there's work looking particularly at the changes in functional connectivity between different brain regions or different brain networks.
And the general trend seems to be that you have decreased within network functional connectivity and increase between network functional connectivity, which this kind of can be interpreted as different brain networks which typically don't communicate as much with each.
Other, more likely to communicate with each other undo the effects of psychedelics and the kind of like internal coherence of networks is reduced under psychedelics.
People have maybe heard of this default mode network right, which is responsible for a lot of self referential processing which is responsible, which is typically activated, for example, when individuals are off task, mind wandering, not actively engaged.
The default mode network has been kind of consistently implicated in being having less of this kind of like within network connectivity, less of this functional integration.
And this has been hypothesized to be one of the kind of key mechanisms of the therapeutic effect of psychedelics.
In addition to looking at kind of like brain network activity on a high level, you can then also zoom in much more deeply and look at what's actually going on at the neuron by neuron level or the neuron connectivity level.
Here we see kind of very certain, very consistent story around this psychoplastogenic effect or this neuroplastogenic effect, where there are a number of different markers of increased plasticity in the brain.
So one that's very common is this increased brain derived neurotropic factor which we see hours after psychedelic use for a variety of different psychedelic drugs.
And this is then accompanied a few hours later by visible increases in the dendritic spine growth in cortical parameter neurons.
So this is both the number of dendritic spines and the complexity of the spines.
You can see a very clear example of this here on the right, where you have on the top the vehicle and then the bottom the DMT treated pyramidal neuron.
And the difference is very stark.
You don't even have to do any sort of actual computational analysis for it to be clear that there's quite significant dendritic growth from a single dosing.
And the changes to functional connectivity, which I mentioned in the previous slide, tend to persist, though in a less extreme form than what we see during the acute effects.
So the question then becomes, given all of this, how can we attempt to tell a consistent computational story, what's actually going on during both the acute effects, the post acute effects, and in terms of the actual downstream therapeutic outcomes?
So what's kind of been proposed as one of the leading models of this is the relaxed belief under psychedelics model, the Rebus model of Carhartt, Harris and Tristan.
And so this builds on the kind of like active inference, hierarchical predictive processing framework where we can understand the brain as this series of predictors stacked kind of like hierarchically along brain networks.
And predictions are being made by higher level networks that are attempting to predict the errors of lower level networks.
And the process of basically doing this then produces this series of belief landscapes at different levels of spatiotemporal abstraction.
And these belief landscapes, of course, can encode beliefs with various levels of precision.
And it's the modulation of the precision of these beliefs which is believed to take place under psychedelic use.
So here's kind of like a very high level version of this Rebus model and how belief relaxation might actually happen, right?
So given that you have this series of cortical networks which are representing beliefs at different spatiotemporal scales.
We can kind of think of the thalamus as being kind of like the entry point where sensory information is being gated into this hierarchical system and the prefrontal cortex as being kind of like one of the highest level.
Networks, which is then responsible for both representing the most abstract kinds of beliefs as well as being kind of the primary inhibiting force for all of the downstream beliefs in the network, in the system.
So what is this heavy agonism of the five h T two A receptor supposed to be doing in this case?
Well, it's going to be decreasing the prefrontal cortex's ability to make coherent predictions and coherent representations of belief, which will then disrupt its ability to inhibit lower levels of the cortical hierarchy.
At the same time, by disrupt this activation of the Salamic or this disruption of the thalamic gating is going to result in additional sensory information entering the cortex that wouldn't underwise enter the cortex.
You have these kind of disruptions at these two levels which then result in beliefs being spontaneously represented in ways that they wouldn't normally be represented.
And the Rebus model at least is suggesting that this mainly is going to manifest itself as a kind of relaxation of these beliefs.
So here is a kind of like very simple diagram of what this might look like.
So you have some landscape of beliefs here and you can kind of interpret the position along the X and Y or, I guess, the X and Z belief in A as being corresponding to some particular belief that might be represented by the network at this layer or at this level of representation.
And then the Y axis, the height as being the actual precision of that belief.
Right?
So here we have this kind of very deep part on the right part of this network or on this landscape and this would be a very strongly represented belief.
Let's say what the acute effects of psychedelics are then understood to be doing right is to be flattening this landscape to be less strongly representing these strongly represented beliefs to maybe making it easier for the reversal of this landscape.
So to move from one attractor state to another tractor state, which is meant to be understood to be kind of therapeutic in various ways, and then the post acute effect being some kind of return to normalcy, but one that is not totally complete, one that still incorporates some of these newly relaxed beliefs, these newly explored beliefs.
Building on this rebus model, karin Harris and colleagues last year proposed this canal model of psychopathology, which basically kind of takes the intuition that the relaxation, if the Reevis model is correct, if the relaxation of beliefs has a therapeutic outcome.
If you kind of take that way of thinking to its logical conclusion, you might then propose something like this, which would say if relaxing overly strong beliefs therapeutic, then having overly strong beliefs in the first place is pathological in some kind of way.
And they refer to this development of these overly strongly represented beliefs as canalized beliefs and this problem generally as canalization or this process of developing them as canalization.
And this is the canal model of psych pathology.
So they kind of build on this idea, this set of previous work in the literature suggesting that there may be some primary factor of psychopathology and they suggest that this primary factor is canalization.
And in this work they discuss a number of different psychopathologies which seem to quite clearly fit this canalization type characterization.
So it's very relatively straightforward I think, to understand things like addiction, depression, anxiety disorders, obsessive compulsive disorders.
All of these involve in one way or another having some strongly held beliefs, typically negative, negative beliefs in the case of like, depression, anxiety, obsessive compulsive, body image disorder, or in the case of substance use disorder, some very strong beliefs about what kind of behaviors should be taken at any given time in any given context.
And then of course, the effect of psychedelics is to undo canalization and the better able any sort of therapeutic intervention is to undo canalization, the more likely for a positive therapeutic outcome.
So I think this work has a lot of strengths and there's a kind of elegance to it.
In our deep Pinal's work that we've worked on, we kind of identify a couple of limitations of this canal model and attempt to extend and refine the model in ways that I think ultimately make it more powerful, while kind of keeping the essential elegant insight that cannibalization is kind of like intimately tied to pathology.
So the first kind of limitation I think that we identify is that in the canal model it's very heavily implied that all forms of canalization are pathological in one way or another.
And as I mentioned just now, this is clearly the case for a large class of very common psychopathologies.
It's when we start to look more towards edge cases, I think that these exceptions start to problematize this understanding, right?
So if we consider psychopathologies such as bipolar, borderline schizophrenia, depersonalization disorder, it becomes much more difficult to kind of easily classify these as simply problems of overly strong priors.
In many cases here we have problems of priors that are not so strong or priors that seem to drift over time in ways that are problematic for both the individual and the people that the individual are close to.
And if we think about psychedelics then as being this kind of panacea to undo cannibalization and undo psychopathology, we also run into this other issue which is that there are certain kinds of psychopathologies which are typically issues for use with psychedelics, right?
So schizophrenia being a very clear one, where there's evidence of psychedelic use being a trigger for the onset of psychosis in individuals who are predisposed to schizophrenia.
There's also evidence of the development of depersonalization disorders with strong psychedelic use.
And this is not what we would expect if psychedelics were simply universally undoing or getting rid of psychopathologies.
There's also this idea, which I think Adam is going to develop quite a bit later, that the stability of beliefs is typically correlated with positive mental health outcomes, not negative ones.
And what is a stable belief if not one that is highly analyzed in some kind of meaningful sense within the system?
And a second limitation is that if you think about an actual dynamical system, one that is parameterized in some kind of meaningful way, like a brain, which is parameterized by synaptic connections and then instantiates neural activity patterns over time, and we think about what kinds of optimization landscapes are actually being induced by such a system.
We find that there's not just one kind of canalization, there's actually two kinds of canalization.
And in our deep canals work, we attempt to kind of take inspiration from deep learning literature to tease apart these two kinds of canalization and understand them a bit more clearly.
And they are just to kind of give a preview these two different things, overfitting and plasticity loss.
So overfitting is the problem of your canalized in a particular kind of way and whatever sort of policy you've learned, whatever sort of set of beliefs you have, these don't generalize to some other context.
You're in context A, you may be very well adapted, you move to context B and whatever you've learned doesn't apply there, then plasticity loss is a little bit different.
Plasticity loss has to do with not one's ability to generalize, but rather one's ability to adapt or to learn.
So imagine you're in context A, you may or may not be well adapted to context A.
If you move to context B, the question becomes are you able to adapt to context B or not?
Not.
Are you immediately already ready to deal with context B?
But given time in context B, can you learn and change?
And we use a very simple recurrent neural network model to kind of make sense of this.
And I think this is important because there can be different kinds of canalization on these different kinds of optimization landscapes and these have unique implications for the treatment of psychopathology.
And I think even more importantly, psychedelics work on these different landscapes in different ways.
And so understanding how they work is essential to developing better drugs, better treatment protocols and more personalized treatment.
Okay, so what are these two optimization landscapes?
How can we make sense of them?
This is kind of like the big overview figure of the deep canal's work.
So we kind of start with this intuition of a recurrent neural network, right?
And in a recurrent neural network there are these two sets of parameters that you have at any given time.
You have the actual weights of the network and then you have the hidden activation of the network, right?
And so the weights of the network are theta and the hidden activation is h and there's some input into the network at any given time step.
And then the output of the network is a function of both the input and the hidden state.
And the hidden state is updated at every time the hidden activation pattern.
And this gives us essentially these two different landscapes.
One, what we refer to as the inference landscape or the type A landscape.
And this is equivalent to the neural activation pattern of a brain at any time.
So what gets read off from an fMRI, what gets read off from the EEG is going to correspond to this activity landscape, but kind of like underlying or supporting this activity landscape is this other more fundamental landscape which is the actual optimization landscape that is induced by the synaptic weights themselves.
And this is what is the result of right click synaptic connectivity in the brain between all the sets of neurons in the brain.
This is what is changing when we have various forms of heavy and plasticity heavy in learning.
And this is what kind of instantiates the possible sets of neural activity patterns, right?
So this is kind of like a way we can start to understand this, which is when we think about belief landscapes, right?
As I mentioned before, here's a very simple diagram where we have a two dimensional belief landscape.
And let's say there's someone who's depressed or potentially depressed and they might have a negative self image.
I'm a terrible person, I can't do anything right.
Something like this.
This would be encoded as a particular position in this belief landscape.
When the neural activity pattern looks like this, this belief is what gets expressed, right?
And there's another set of neural activity patterns which would correspond to a positive self image, a positive self belief, I'm great, I'm wonderful, or even just, I'm okay, I'm totally acceptable as a person.
And this would be a different set of patterns.
So based on the synaptic, the actual connectivity structure of the brain, these two patterns may be more or less likely.
So here these are being represented by these two different sets of neural activation landscapes which are the result of two different positions in this synaptic weight landscape space.
And in this top space, the one that's in the middle of here that then is represented here at the top of part C of the figure, we see that there's very high precision assigned to or very high likelihood assigned to the negative self image and very low likelihood here assigned to the positive self image.
But in some other part of the synaptic weight landscape, a very different kind of neural activity landscape might be instantiated.
And this one kind of has the inverse properties where negative self image is unlikely and positive self image is much more likely.
So we can kind of then understand positions in the neural activity landscape as kind of corresponding to specific phenomenological experiential instantiations of certain kinds of beliefs, right?
So like the actual experience of holding a negative self image or holding a positive self image.
And we can understand positions in the synaptic weight landscape as being something more general.
So in the case of depression, there might be a specific set of synaptic weight connectivity which would correspond to what you might call a depressed individual, someone who might qualify as having major depressive disorder and another set of synaptic weights connectivity pattern that wouldn't qualify as that.
Okay, so before I get into the psychedelic, how psychedelics relate to this, I think Adam is going to talk a little bit about some work he's done extending the.

29:21 _Adam:_
Hello.
So, yeah, I've been thinking about this a while and then along the way I met Arthur, who also has been thinking about this a while, but in different ways.
And so like Arthur's background is in basically consciousness science and a very peculiar field of computational consciousness science in terms of actual models of what it would be to have a conscious system, even potentially an artificially conscious system.
And so I'm coming from more free energy principle and active inference, my background and Arthur's coming from more mainstream machine learning.
And so we were coming together to explore this beast from different perspectives and been finding a lot of, I think, very interesting overlap.
And so in terms of Albus, the basic idea is to take Rebus and expand on it.
I love rebus.
It's a great framework and I've been trying to make it, I guess, more flexible in terms of being able to handle a wider range of assumptions.
So not just talking about relaxed beliefs, but also potentially strengthened beliefs and in different combinations.
This was always part of the rebus framework.
And that you can have all sorts of both direct and indirect effects.
When you're dealing with a large predictive hierarchy or any complex system, you change something in one way, but then you'll get an effect elsewhere.
So if you have this hierarchy of predictions, for instance, you can potentially relax beliefs at higher levels and that can indirectly cause strengthened beliefs at lower levels.
So you can both get relaxed and strengthened beliefs and psychedelics and all sorts of different combinations.
And so with Albus the idea is so I've been calling as opposed to a belief relaxation.
When you get this sort of basically bottom right here, you might see it.
So this red would be basically something like a synchronized complex of neural activity, often involving the thalamus, which would be thought to encode your predictions, or your top down stream of priors, which then are suppressing the ascending stream of prediction errors.
And so under revis, you're seeing here relaxed predictions, a smaller complex of synchronized activity.
And the gates are down.
Just like Arthur described, more things are coming in.
Rebus will sometimes be described in terms of so when we're talking about rebus this idea of relaxing beliefs.
We're thinking at the functional or computational level, like with David Mars and analyzing the mind, you have these three, I suppose, Supervenient levels.
They're compatible and synergistic.
So computational functional, like abstractly, what is the system doing?
Something like the pseudocode of the system and then implementational mechanistically how it's realized and then in the middle, some sort of algorithmic intermediate abstraction layer.
How are these computations realized via these mechanisms?
Some bridging.
Principle description.
And so when it comes to rebus, you can adopt it in different ways and relate to it differently.
So you can relate to it at the functional level or you can relate to it at the algorithmic or implementational levels in terms of where you're taking the account.
So, for instance, you might think something like rebus effects is a very valuable model of something like what they call quantum change of psychedelics.
But you don't necessarily believe in predictive processing, but you still might be, you could say like a rebus type theorist.
Or you might be thinking in terms of rebus in a more narrow sense of thinking, of predictive processing information flows, but then when you get to the overall person and integrated organism and the agent, you might have different interpretations there.
So with the work with Albus, basically the idea would be to take predictive processing and models of psychedelic action and suggest that sometimes not only do we have these relaxation of belief landscapes, but we might have the opposite of strengthening.
And so specifically, if you're activating these five HD two A neurons, which would be at the deeper levels of the cortical sheet and also the deeper levels of the cortical hierarchy, more inwards and higher up, and these would be the units that would loop to the thalamus and thereby be able to form large synchronous integrated complexes.
But that when you excite them too much, they don't wait for each other to sync up, they fire whenever they can out of sync.
And this relaxes the belief landscape.
However, it's not clear this should happen the whole way through for any amount of increasing the gain on these neurons.
So in theory, just increasing the gain a little bit, unless that might help them to sync up, that might strengthen the belief, whether it's a situationally specific suggestion of you in this context or maybe something old coming to the surface and if you will manifesting.
So Albus basically, in a nutshell, would be saying to take rebus and keep going with it and look for different combinations of both strengthened, both directly and indirectly strengthened and relaxed beliefs.
That's basically it.
And so I'm not going to go into too many more details.
Arthur and I just submitted this for publication.
Wish us luck.
Hopefully the reviewers will be useful, maybe even kind, but preferably useful, and kick it back to Arthur.
But before work, I think it's immensely important that we get these details, right?
These are extremely powerful medicines that could revolutionize things or we could have a backlash if we do it wrong, if we're careless, if we don't see the risks, but also if we're overly beholden to a single way of viewing things prematurely, we might also miss opportunities to help, potentially enormous opportunities.
For instance, you might not think of helping people, for instance, micro dosing for cognitive decline.
You might not have thought of that and that might be a really big deal that you do think of that.
So I guess for going back to Arthur, one more thing would be just in terms of, at least for me, experientially.
The way I sometimes think of it is with relation to well being and suffering, both things matter, like the strength of your positive beliefs and the strength of your negative beliefs.
And sometimes the negative beliefs have positive aspects and vice versa.
So it's both like you might relax your beliefs and to use like a Harry Potter metaphor be somewhat so much out of the grip of the dementors that usually that under some circumstances might be pursuing you that you have room to be different, to become different, to think different things under this different state.
But additionally, and not mutually exclusively, not necessarily incompatibly maybe synergistically the strength of what beliefs you're able to have in that moment and maybe draw upon from the past could be deeply important.
Your values, the kinds of beliefs that you call upon in times of need and they give you hope.
Maybe those are just originally suggested to you right there in the session.
But maybe there's something else, another belief, and that strengthening it could be a good thing.
And even without a clinical context, like microdosers, for instance, it's not clear exactly they're trying to relax their beliefs, like the range of use cases, the way we want to relate them and how we want to be in the world.
It seems complicated to me.
So I will take it back to Arthur.

37:38 _Arthur:_
Great.
Yeah.
Thanks so much, Adam.
OK, so with that context of Alice, I want to talk a little bit about how we might understand at a very high level what psychedelics are doing to these two belief landscapes.
So before I showed you very quickly, I guess I can go back to it.
In the Rebus model there's only one type of optimization landscape and so there's only one type of canalization and what is supposed to be happening is a relaxation of leaves which is strong during the acute effect and persists in the post acute effect.
So with albus though, we might be able to think about all of this a little bit differently.
We can, enduring the acute effects of psychedelics, interpret what's happening to the type A landscape as being less of a kind of universal relaxation and more of a kind of destabilization where under certain circumstances beliefs are being strengthened, other beliefs.
Are being relaxed.
This is changing quite rapidly over the course of time.
So a certain belief might be transiently strengthened a few minutes later, it may no longer be supported or supportable.
And this actually functionally enables a kind of exploration of a wide space of belief instantiations during the acute effects of the drug.
As far as the inference landscape is concerned, post acute effects, as Adam was saying, it could be the fact that certain positive beliefs are explored and can be strengthened, other negative beliefs might be weakened.
This is kind of like the ideal psychotherapeutic outcome.
It may be on average that something like a relaxation, a general relaxation of beliefs is what you might see.
But the way that you get there is likely going to be through a kind of much more complicated process, I think.
What's then interesting and related also to what Adam said about thinking much more broadly about how psychedelics might be used in terms of neurocognitive disorders, in addition to kind of like traditional psychopathologies is to think about what's happening to the learning landscape, the kind of like underlying synaptic weight landscape.
And what do we understand is happening here kind of quite clearly is there is neurogenesis psychoplastogenic effects, there's dendritic growth.
And what is this enabling?
Well, this is enabling greater connectivity between, within and between networks.
And so kind of from a functional learning perspective, learning theory perspective, what this means is that gradient information can flow more easily through these networks.
And what this means is that it's easier to get from one part of the network to the other part of the network.
There are fewer of these kind of optimization local minima, there are fewer of these kind of tricky saddle points.
And what this means kind of like functionally is that this plasticity loss that I discussed earlier is going to be less of an issue.
And here it seems to be kind of like regardless of the acute, the actual phenomenological effects, there are very strong downstream effects on this structural connectivity.
And I think there's some interesting work suggesting that there may actually be independent mechanisms that are affecting these two landscapes.
So there's recent work suggesting for example that psychedelics as well as ketamine is able to kind of particularly bind to receptors in the brain that produce that result in the kind of release of the brain derived neurotrophic factor and then the downstream changes in synaptic weighting and that this may be potentially totally independent of the five H C two a agonism.
Right?
And this has very interesting implications for future drug design and development.
Okay, so I'm going to, before my next slide, turn it over to Adam once more to briefly talk a bit about personality theory and the relationship between psychedelics and.

42:12 _Adam:_
Hello again.
So for the past few years I've been doing some work with a personality researcher, Colin de Jung, on intersections between the way agency is modeled in the free energy principle and active inference framework and the way that persons are considered in different situations in personality science and looking for points of intersection.
Personality is actually an extremely deep concept.
And if you think of it, I guess we call it like the normal form of a system in terms of what is the way you can describe the most of the system with like the minimal message length, the account for the most of the least.
And what we're trying to account for is the states that people tend to occupy, people aren't always happy, people aren't always sad, people aren't always friendly, they're not always angry.
It's all sorts of things that there's a range that people are encountering but they tend to occupy some states more than others.
And you might call that their personality and you might call it many systems would have their own personalities in terms of trying to describe something like their essence and so they're attracting states.
And so with Colin de Jung's work, he interprets personality and these major domains of personality that people have discovered a reliable factor structure ways you can chunk the variance, the big five as a trait hierarchy but where these different traits are interpreted as cybernetic control parameters.
Specifically cybernetics in terms of the study of goal seeking systems governed by various forms of feedback that different stages of the process of pursuing goals, evaluating outcomes updating understanding that basically the personality as different modes of being in the world.
For cybernetic systems, interpreting them as parameters for goal pursuit because we are goal seeking systems trying to pursue the goals we value.
And so I guess moving to this with relation to what we're talking about now, both in terms of personality formation, reformation and the structure of personality.

44:39 _Arthur:_
To.

44:40 _Adam:_
Get to the P factor within personality theory, this big five traits, the set of big five traits, there's a richer or more detailed factor structure, a hierarchical structure for personality that's been discovered.
So above the Big Five, neuroticism, agreeableness, conscientiousness, you'll have a metatrate of their shared various that's observed called stability.
It's also been called alpha by, I think, Digman.
And then above the traits of extroversion and openness intellect, you have this MetaTrade of plasticity and are called beta and the shared variants of these two.
So what's interesting is that within this field of within high top, which is this effort to try to characterize psychopathology using the same kind of data driven methods in personality science.
A principled account of the structure of psychopathology, the way that personality has a structure and trying to account for this, there seems to be a common factor across many forms of psychopathology that's referred to as the P factor and it tends to be the inverse of stability.
It's high neuroticism, low agreeableness and low conscientiousness.
And this is actually what's referred to in the article as this P factor, thinking of it as a lack of flexibility.
You could make a case for it.
But more straightforwardly it seems to be a lack of stability.
For something to be a lack of flexibility you would maybe be thinking of something more like plasticity, like someone having low plasticity.
But empirically that's not what's observed.
And so if empirically that's not what's observed, that's a very important detail we should stop and take note of.
So you might say that rather than emphasizing the first principal component of psychopathology, it's possible that this Canal model is actually focusing on the second factor.
It's not a contest.
It's still enormously a big factor like the work of Stephen Hayes and others showing that a lack of flexibility is transdiagnostic.
But just empirically speaking, the first principal component of psychopathology might be more closely related to a lack of stability rather than insufficient plasticity.
I guess one more thing to think of in terms of stability and like as it's not exactly a contest, they're both important, both need to be considered and they're deeply interrelated.
So Colin describes them as being in a state of something like dynamic tension.
Like if you're insufficiently plastic and inflexible, you're not going to stay stable for long in a changing world, but if you don't have a stable base to move from, it's going to be hard to be plastic and reconfigure yourself in a sustainable way either.
However, you could also see someone being overly rigid and excessive stability in a way that undermines their plasticity or overly flexible in a way that basically is destabilizing.
So a dynamic tension but involving synergies also.
And I think in terms of the structure of personality and well being, this is what we need to keep in mind that both are needed, stability and plasticity.
And this is also just within it's actually what this was inspired, I think in Colin's thinking to consider these metatrades this way from machine learning, I think actually reading Grossberg and Stability plasticity trade offs and that's why he interpreted these metatrades in those terms.
So I guess one more thing is there is a Petersonian backstory here that I don't know if I want to get into, but we can discuss it later if there's yeah, back to Arthur.

48:46 _Arthur:_
That was great.
Thanks.
Adams yeah, very, very helpful context which should hopefully make this slide here much more clear to everyone.
So given these kind of, like, two meta traits, stability and plasticity, which, as Adam beautifully described you're in this kind of dynamic tension with one another, we can kind of go back to these two optimization landscapes and these machine learning concepts that I discussed earlier and couldn't try to understand how these things might all relate and ultimately relate to psychopathology.
So I had hinted before that there were these kind of two types of cannibalization.
We might say one being overfitting and another being plasticity loss.
And we can interpret these as kind of like being extremes, the kind of like canalized end of how these two optimization landscapes might manifest.
So in the type A inference landscape, this looks like overfitting on one end, heavy canalization and underfitting on the other end in the machine learning context, right?
So overfitting being having very strong rigid beliefs that are in a particular environmental context, adaptive, but are very unlikely to be adapted in any other context, underfitting being having a set of beliefs which are not adapted to the current context and also unlikely to be adapted to any other context.
As far as stability is concerned, I think we can understand stability, this MetaTrade, as kind of representing the balance of these two things, right?
You have high stability when you are either overfit to a particular context or underfit.
So this means you're well fit to this context that you're in now and you're also likely to be well fit to other future contacts.
I think this is also in complexity science, sometimes described as metastability, right?
So you're at a stable point that will also likely be able to take you to other stable points in the future.
And this kind of like ability to stay stable over time is then stability MetaTrade.
We can then look at the type B, the learning landscape, where the kind of extreme version of canalization is this plasticity loss where it's very difficult to adapt to new contexts.
The inverse of this is then catastrophic forgetting, where the problem is not one of adapting to new contexts, the problem is one of meaningfully retaining adaptive strategies and beliefs from previous contexts.
And so obviously neither of these are desirable.
What is desirable is some kind of balance between these two or one is able to adapt just enough to new context without forgetting previously learned things.
But here the relationship to the Mediterranean plasticity is a bit different than stability, right?
So as is being represented on this graph, the more plastic you are, basically the less canalized you are in the space, the more easy it is to move around.
But actually extreme versions of this end up manifesting as catastrophic forgetting, at least in the machine learning context.
And I think this in particular has relevance for psychopathology and relevance for this idea, maybe complicates this idea, right, that psychedelic therapy is in and of itself likely to always lead to positive outcomes.
Okay?
And we can attempt to understand this by making an effort at trying to map or understand various forms of psychology in the context of these two different learning landscapes.
And so before I get into this too much, I think it's important to say that this is very much a kind of like preliminary and provisional attempt at making sense of these things.
I hope that this is kind of the start of a much more fleshed out dialogue looking at how we can kind of understand psychopathology with respect to machine learning concepts.
But I think this at least gives a good starting point for maybe trying to understand where and why psychedelic therapy is useful, isn't useful, which is a bit more nuanced than this simple idea of like psychopathology means cannibalization and psychedelic therapy means reducing cannibalization.
Right?
Okay, so let's try to make sense of this a little bit.
So for the kind of classic set of psychopathologies for which there has been a lot of great research done with psychedelic therapy and a lot of clear benefit has been seen.
I think we can kind of class these within this upper left hand corner here, where these are disorders of both overfitting, which means in the moment overly strong beliefs get represented.
These are strong attractor points in the neural activation landscape and plasticity loss in the type B landscape.
Which means that not only is a certain kind of dynamics instantiated, which make, for example, in the case of major depressive disorder, extremely negative self evaluations very common, but it's the case that even given the correct changes in environmental context.
Even given in the case of psychedelic cystotherapy, a lot of the work with major depressive disorder is being done with treatment resistant depression, right?
And what is treatment resistant depression but a kind of a set of beliefs, a set of neural activity patterns which are resistant to adaptation, to new environmental contexts being whatever sort of psychotherapy or previous drug was used.
So this is high plasticity loss, high overhead and rate and these are kind of fortunately for psychedelic therapy and I think maybe for psychiatry in general, these are all very common and very, very costly psychopathologies.
Right?
So if it is the case that psychedelic therapy can treat these effectively, that's fantastic.
But I think we can maybe look at a more complicated if we start to expand to other psychopathologies, the story becomes a little bit more complicated.
Right?
So we can look at the bottom left hand corner here where we have cases of in the inference landscape still overfitting, but in the learning landscape something else happening, form of kind of catastrophic forgetting or a form of kind of drift of the belief landscape that's being instantiated here.
Right?
So I think two kind of representative pathologies here typically referred to as some form of bipolar disorder or some form of borderline personality disorder.
So in both of these cases, in the moment to moment neural activity as it unfolds, there are very strong sets of beliefs being instantiated at any given time and these are very difficult to change.
Right?
But the key differentiating point here being that over longer timescales, over the timescales of days or weeks, the kinds of beliefs that are instantiated change quite a lot.
Right?
So someone who's bipolar, if they're in a manic episode or in a depressive episode, the nature of the belief landscape being instantiated is very different for borderline individuals from a daily or weekly basis, the nature of one's beliefs about the people that are close to them can change very rapidly, very extremely in certain cases.
And so here the benefit of psychedelic therapy is a bit more mixed where there is likely the case that to the extent to which the kind of overt type A beliefs can be updated and changed to be more positive, be hopefully more relaxed, that's positive.
But to the extent to which plasticity may be being increased when it's not actually needed, when there's not actually meaningful therapeutic benefits of that, it's a bit questionable.
I think there's clear borderline, or rather bipolar for example, is often individuals with bipolar are often excluded from psychedelic trials under the assumption for example, that psychedelics may trigger a manic episode or may trigger psychosis.
And I think that is a valid concern.
So on kind of that topic then, this bottom right hand corner would be cases of both underfooting and catastrophic forgetting with I think schizophrenia being kind of like the most clear manifestation of this.
And here there's very little work currently looking at trying to treat schizophrenia with psychedelic therapy.
I think for pretty good reasons though I would say to the extent to which there are secondary manifestations, secondary issues like depression, anxiety that people with schizophrenia might have, these actually may be treatable with some form of psychedelic therapy.
And then lastly, this upper right hand corner here would correspond to underfitting in the type A landscape along with plasticity loss.
So I think a good example of this is something like ADHD, where there are not very particularly strong beliefs that are being instantiated at any given time, but it's difficult to change these set of beliefs.
Nonetheless, I think here there's a case where it's not totally clear how the benefit will actually play out in both of these cases.
I've heard interesting work around like microdosing may be of interest.
I think yeah, more research has to be done to be seen.
Right, and then what would microdosing be doing?
Right, microdosing would be very slowly kind of like decreasing plasticity loss just a little bit, potentially also decreasing underfitting, as Adam has kind of suggested in the Albus model.
And here we have just kind of like a brief overview of more or less everything I've described about how these two landscapes are different.
I think most of these things I've said before pretty clearly right so the type A landscape corresponds to the neural activity pattern.
This is the hidden state of the RNN.
Overcannilization is going to be stereotyped mental circuits, very strongly held beliefs.
Under canalization is going to be these inconsistently deployed circuits.
It looks like overfitting in the canalized case, underfitting in the non canalized case going to correspond to stability, the metatrate.
I hadn't discussed this before, but I think there's a relationship between cognitive flexibility and this inference landscape psychedelics are mainly going to affect the work at the acute level care.
And this is by directly exciting the neurons or inducing forms of hadavian plasticity and the outcome is going to be a mixture of relaxation and strengthening of the kind that Adam described in the Albus case.
The type B landscape then is working on the synaptic weights and these are the actual network parameters in our RNN model.
Over canalization is this inability to learn or adapt over time.
Under canalization is the inability to retain information right?
And those correspond to plasticity loss and catastrophic forgetting.
This also is kind of the traditional plasticity metatrate, which I think corresponds to this longer term constructed psychological flexibility.
The effects are going to mainly be mediated post acutely with psychedelics and these are the more downstream metaplastic effects, the psychoplastogenic effects.
And I think on the whole the effect here is a relaxation of canalization.
And yeah, these are just the references.
So those are the slides I have that's kind of the overview of the Deep canals model, I think.
Now I'll turn it over to Mike who's going to share some thoughts both about this work and some of his own work and kind of this approach to understanding psychedelics more broadly.

1:02:06 _Mike:_
Ah, great.
Yeah, thank you for that overview.
That was great.
So I guess I'm just in general very optimistic about this corner of neuroscience, that there are these very intuitive models that are very sort of clinically significant and I also think there is a lot of responsibility to sort of get things right here as well.
As Adam noted.
I have just a few comments and for the viewers, I'm not speaking for Arthur and Adam, I'm just grateful for the invitation to join the discussion.
So I wanted to note quickly three research themes dealing with the implementation of this class of model.
So just broadly kind of pointing at both Deep Canals and Andrebus and Albus.
So in 2019 I wrote Neural Annealing and that was sort of developing the canalization frame within the context of energy buildup in the eigen modes of a system.
So you have the nice annealing metaphor, you have a temperature parameter and entropic disintegration.
Robin Carter said a beautiful paper on that dantropic brain and then you sort of have a post heating result where the microstructure of your system is sort of a result of how hot and how long the heating was.
So it's an alternative take on belief relaxation.
And I do think that there are some pluses in terms of sort of explicitly making the annealing metaphor.
And I think that two things that I'd point out.
One, top down models or top down predictive models as energy sinks and eigen modes as the places where energy can build up or almost sort of hide from top down models.
So you get this phenomenon of semantically neutral energy or semantically illegible energy we can say, which is sort of kind of how perhaps psychedelics music and meditation all sort of allow energy building.
The energy that they contribute to the system can evade the top tone models.
And yeah, just to note, one item that I'm looking at now is what is Deep Canals?
Has the inference landscape versus learning landscape distinction?
And how would one sort of build that distinction within the neural Annealing framework?
And guess one metaphor that I'm considering is the self as sort of a magnet to sort of apply a constraint, a uniform focusing constraint on the system as it's cooling.
The second item that I wanted to mention, so I have this piece, autism as a disorder of dimensionality.
And this brings in the concept of network density that it may very well be that people on the spectrum have literally more neurons and or more synapses.
And there's this great Michelangelo quote, I saw the angel in the stone, and I set him free.
And sort of the thicker networks you have, the more stone you have to work with, but you actually have to do the work.
So you sort of have to do sort of well, normally you sort of inherit these highly pretrained optimized circuits, almost like asics application specific integrated circuit.
And then this is kind of more an untrained network, and you have to train it yourself.
And within the Deep Canals framework, this would show up as both underfitting and higher capacity for plasticity.
So I think that's going to be an interesting thread to pull.
Finally.
So I just posted that last week, principles of Vaso Computation and as an implementation level account of active inference.
And this is a big rabbit hole.
I don't think we have time to go down it today.
But I just comment that I really like the way Deep Canals explicitly splits out the learning landscape and the inference landscape, that I think that making this distinction is increasingly going to make sense.
Back to Arthur.

1:07:52 _Daniel:_
Yeah, awesome.
Well, thank you all for the presentations.
Arthur and Adam, feel free to pick up where Michael left off, or I can bring in some questions from the chat or from what I've written down.

1:08:22 _Mike:_
Just a quick comment.
I do think that in the Deep Canals framework, it's going to be interesting to sort of look into metabolic demands, and sort of different metabolic disorders are pretty hot in brain science right now.
And I do think that it'll be interesting to look at sort of what the metabolic profile is in terms of each of the four items in the quadrant, if one quadrant or another quadrant is particularly associated with more metabolic demands in the system.

1:09:09 _Daniel:_
Arthur yeah.

1:09:12 _Arthur:_
No, that's fascinating.
I'd love to kind of hear a little bit more about this comment you made about the salt as a magnet that's applying these constraints.

1:09:24 _Mike:_
Oh, yeah.
So there's the, like, psychedelics the the effects are not or sort of the you sort of get pulled back into position after after some time.
And I can't say that this is a full theory at this point, but in the neuroscience notation 2018, I talked about the self as kind of the god of the gaps in terms of aligning different scales.
You have circuits which kind of pull in different ways and you have the mesoscale systems which pull in different ways and you have the overall brain wide systems that pull in different ways.
And kind of the self is sort of the thing that tries to make everything work together.
And an alternate frame would be sort of this alpha is just kind of this slow gravity toward disalignment.
Yeah, I don't have anything particularly more to share.

1:10:50 _Arthur:_
Yeah, that makes sense.
It's interesting.

1:10:52 _Daniel:_
Well to combine the heating up and the magnetism, different metals and connections there to alchemy and everything different metals when heated up and cooled down in specific ways change their magnetic profile.
So of course this is all just concordances but they're very interesting.
And then also to the metabolic angle that reminded me of the trilogy by Dale Pendel with Pharmaconosis and the other two books where treated alongside traditional psychoactives we could say like caffeine and nicotine and some of the other substances that were mentioned here.
Also there's tea, sugar and these are treated as psychedelic or at least as in the same pantheon of neurocognitive modifying in the sense that the destinies of individuals and of empires ride on the sense making and decision making influence of sugar, for example.
So it definitely broadens our perspective to include the so called classical molecules like LSD.
But also maybe we could think more broadly about antioxidants or about different lipids or about different metabolic connections.

1:12:25 _Adam:_
Michael Pollan's recent book this is Your Mind on plants I think it kind of has that what you're saying in mind because it includes caffeine, not introduces a psychedelic but just discussed among also psychedelics.
I think I remember he focuses on masculine but it is a different way of being in the world, potentially radically different like if caffeine is in your life or it is not, it's a different life world.

1:12:57 _Daniel:_
And different extended niche.
I'll go to a question in the live chat so anyone can give a thought.
So Matt asks is there any way how to approach the individual reactions to psychedelics in terms of positive or negative results of treatment using the ideas of deep canals?
So how can we approach predictions and explanations at the individual scale with what you're sharing today?

1:13:36 _Adam:_
One thing for this is kind of like a meta comment, but if we're actually going to do computational psychiatry and we actually are going to and precision medicine so the goal being to create models of sufficient detail that they could actually guide our practice and guide our practice in a way where we know for an individual what they might need in any given context.
So precision medicine with respect to standard antidepressants people, sometimes they'll go for a long time before they find ones that work, and sometimes things are made worse, and then they might deal with antidepressant withdrawal if they're looking for the right one, and if they're in a state of acute distress, that could be a hard lot.
And so if you can help to speed up that process of finding what works and what might hurt also to avoid that, the ability to help people is immense.
And so for that so the meta comment is I have to just say I'm not convinced that an act of inference.
We're doing the job.
I think we're not acknowledging our uncertainty and I think the models are under specified with respect to the complexity of the effects we would expect on different scales and in characterizing the systems and we need to be more patient and modest.
But what we don't know before we go on rushing in headlong into telling the rest of psychiatry how they should comport themselves and what models they should use based on psychedelic science.
And plausible models, hopeful models, but very early days.
And with the reality being complex in the ways we're seeing here, this was not an easy set of lectures or a set of talks like what we were going through.
And, yeah, if we're actually going to be able to handle these powerful medicines responsibly, we got to go into the weeds.
The one more meta comment was like I think I saw someone say how can something like help everything?
I don't know if this is right but it's almost like a violation of no free lunch theorems or something.
It's like how could something just be good across the board without something is off?
You've calculated wrong somewhere you had to pay the price either in some trade off that wasn't acknowledged.
But that being said there are some things which are generally good for a lot of things like being more flexible.
If you can get something like metastability I think I'm a church member of the I'm a faithful member of the church of criticality.
I think Mark Miller might have indoctrinated me with optimal grips but basically like the ability to have an optimal grip on existence in your soul, not too tight, not too loose and being able to move around and be flexible in itinerants.
Something kind of like mindfulness is just like sriracha for the soul.
It's good for everything almost you just put on this, put it on, that makes it better.
I buy that there might be some things that are good across the board but I wouldn't call though psychedelics necessarily putting you in this state of optimal criticality or anything in general.
The rhetoric I'm uncomfortable with of saying psychedelics do X.
I would prefer to say which psychedelic.
Psychedelics tend to do x but just a little more qualifier like not weasel words but just like a little bit more like this psychedelic might do x in this context with this dose in this sentence setting but that being said there do also though seem to be across.
The board, broad, sweeping, not super, but overarching statements that we can make that express a lot with a little.
And so I don't want to be so much of a splitter and a prickly person finding all the details that these powerful things we can basically give to people to guide our research.
I don't want to leave that on table either.
I guess that's a bunch of meta level commentary that did not address the thing.

1:17:49 _Arthur:_
I think that's useful.
That's very helpful.
I think to have all that context.
With respect to the question itself, I would maybe offer this, which might be helpful, which know, I think you mentioned it, Adam, and it's very frequently mentioned this idea of set and setting, right.
As being heavily predictive of the quality of the acute psychedelic experience, and often also, to some extent, the quality of the post acute experience.
And I think we can understand this in the deep canals model, quite straightforwardly.
So I'll just quickly pull back up one of these slides here.
Yeah.
Right.
So what is set and setting?
So set is mindset, which would basically be some combination of your current position in the synaptic weight landscape and the current state of your neural activation landscape.
Right.
So your place in both landscapes is your mindset, and the setting is what is generating this input.
Right.
What is generating the x into the network.
And that's some complicated function of the environment.
And then we can understand the evolution of movement through the inference landscape during the acute effects of the drug as then kind of like very directly and straightforwardly being a function of these two things.
Right.
Because both of these things are basically what's affecting how this landscape evolves over time and how you move through the landscape.
And so with this in mind, I guess we can then start to characterize and think about, okay, well, what kinds of we can maybe be a little bit more mechanistic about how does input from the environment, the setting, actually, given that we relatively fix the actual synaptic weight landscape, how is that changing the dynamics over time or the other way around?
Right?
Like, how is fixing the input, the environmental context relatively stable and looking at individuals who are at different fixed points, at different points of time, going to change the dynamics of the event?
Right.
And I think given that this is a highly stochastic process, given that these dynamics of albus are at play right.
Where certain beliefs are being strengthened, other beliefs are being relaxed, I think at least having this hold on, okay, well, set and setting is really important.
And it's important because these are explicitly conditioning the way in which both the landscape, the inference landscape is shaped and how you move around it and how it's being dynamically perturbed.
Yeah, hopefully that answers a little bit the question.

1:20:49 _Mike:_
Nice.
I just want to jump in there, just thinking about biomarkers if we're looking for something that's of high clinical specificity, we want to sort of be able to measure what's going on in a very careful way.
So first of all, what is temperature parameter?
We talk about, okay, psychedelics increase the temperature parameter.
But how high?
And do different substances and dosages sort of differ in interesting ways?
Probably, yes.
And then also sort of measuring temperature parameter, measuring the temperature parameter in different parts of the body.
So you might have a different temperature, like not literal temperature, but computational entropic integration in different parts of your body and also the plasticity status in different networks throughout your body.
So I guess I see a big frontier here as thinking some doing some careful thinking around biomarkers and proxies and inferring these sort of things that we are talking about as core and I think they are core and we should be able to find good marks for them.

1:22:32 _Arthur:_
Yeah, that's totally correct.
And yeah, I just want to repeat it for my own sake even.
Right, which is that these two things which I think were maybe one is I think already a core part of the deep canals work right.
Which is that I was showing these single images of these toy optimization landscapes.
But of course, the human being, the nervous system has multiple many of these landscapes hierarchically organized, right?
And they influence each other in a complicated way.
And the project forward is to understand where these landscapes are, what they look like and how we can find biomarkers to them and begin.
If these two kinds of characterizations are true, this overfitting underfitting plasticity loss and catastrophic forgetting, then it's a very meaningful project to be able to quantify that objectively somehow an individual.
And that's when you can start to get to this point that Ada was talking about of precision medicine and understanding like okay, well, actually it turns out like these networks are catalyzed in this kind of way.
And because of that we can say with much more certainty that this kind of psychedelic intervention is going to likely be helpful.

1:24:00 _Adam:_
I don't know if this potentially brings in some of the work with vascular and neurovascular and visceral integration that you're doing.
So there's like a sense in the free energy principle where the overall phenotype and extended phenotype in terms of its constructing and coupling within constructing its Econiche, its success in manifesting this phenotype there is one free energy functional for this overall effort as a kind of prediction that's enacted through the dynamics.
But you could also break it down in terms of subsystems with local gradients and local autopoietic processes that are in like they're brought together into an overall system, hopefully with synergies and they have to be to be an organism and an agent.
And we call this like a thing to the extent it has thingness.
It's coming together.
I guess think of maybe like energy landscape, something like let's just say right now, in this moment, my explicitly felt beliefs.
But my body also though might have a different opinion, different parts of it, in terms of what it's implicitly optimizing its revealed preference from its inaction that may or may not correspond to how I feel about it.
It might be difference of opinion.
I might not even be tuning in.
I might be ignoring it maybe because I don't want to.
And so it's kind of like the score kept by the body might have its own be describable as its own information geometry which is being tracked to degrees and is in different degrees of alignment with different ones at different levels of a control hierarchy.
So plausible?

1:25:51 _Mike:_
Absolutely, I think so, yeah.
I think of the body as sort of a parliament of different networks.
And alignment is the scarce resource.
Coordination is always the scarce resource.
And how does the body keep alignment and when does it go wrong too?
And I guess I see this as sort of harmonically mediated.
Each part of the body has some choice of what else in the body to listen to.
And depending on the particular sort of location in the information topology, different parts of the body have different carrots and sticks by which to try to control other parts of the body.
So if your stomach is very unhappy, it's going to start grumbling and then it'll let the body know, okay, I need some food, I really seriously need some food.
And then the rest of the body, they can sort of turn away from it and then it'll just get louder and then you have to turn it away from it more and it'll get louder.
And that's of course a negative dynamic.
If it gets what it wants, maybe it sort of gives a very harmonious uh and sort of tries to give carriage the rest of the I just uh there's an ecosystem there.

1:27:28 _Daniel:_
I'll go to another question in the live chat.
So Bert asks what do you think of the average of solving within a generative hierarchy and the impact of temporary openness moving it upwards?
And then I asked to clarify what do you mean the average of solving?
And Bert wrote where predictions meet incoming signals like discussed in Rebus, where top down predictions are softened in precision and thus solved.
For.

1:28:02 _Adam:_
I think Arthur will be able to get into the details of that better than I would.
But one thing I'm wondering there is sometimes I love the entropic brain, but sometimes I wonder in terms of the connections, whether I don't how we're having more or less entropy and whether that matters the how.
So for instance, you can think of a free energy landscape that's been flattened or you can think of one where you're better able and you have more energy for the manifold activity is better of climbing up or down the peaks that are there for the more enduring belief landscape.
So it's like, in the moment, it could be that my previous way of thinking is unavailable to me and I no longer believe those things at any level.
Or I can support more novel inferences that I wouldn't.
Otherwise I can kind of move into an area of mind space that would otherwise be difficult, potentially because of a greater energy into the system, greater thoroughput noise.

1:29:24 _Arthur:_
Yeah.
So as I think I understand the question, right, it's basically asking about trying to optimize for this free energy variable and in the context of deep canals, right?
Like this is the loss function that's driving the optimization of the learning landscape, the synaptic weight landscape.
Right.
The entire connectivity structure of the nervous system is trying to get to this point of low free energy.
And I think there's lots of for any given individual in a given environment, assuming the environment is relatively fixed, right?
There's like an optimal, there's a global optimal.
And it's very likely that the individual is in some local optima that is maybe close to it, maybe far from it, but that's just inherently what within the context of the active inputs.
That's what we're assuming that the nervous system is doing, is doing this gradientism in the space and openness then is going to correspond to this plasticity MetaTrade or be one of the components of it.
And it is in the deep canals model then going to correspond to an ability to move around this optimization landscape more easily.
Right?
It's going to be a flattening of the landscape, or more precisely, I guess, a smoothing of the landscape such that it's less likely that the individual, the nervous system will get stuck in these local optima.
So maybe it won't mean that the individual will arrive at the global optima.
I think it's difficult to say what that even might be or how individuals might get to such a place at all.
But I think it is likely that the individual will be more likely to find a more global optima and more easily move from one optimal to another.
And I think that's kind of what this openness is corresponding to.
Yeah.
Okay.

1:31:41 _Mike:_
In neural kneeling, I mentioned the idea of psychedelic extrapolated volition, kind of a play on a coherent extrapolated volition from the AI safety crowd.
And it's this sort of sense that if temporarily you have more control over sort of low level shaping of your cognition, your emotion, and maybe sort of based on this attractor that we call the self, or I guess based on what is a good question, then what are good signs?
That you should be trusted with that power or you should trust yourself with that power rather.
And what are telltale signs that you shouldn't trust yourself with that power?
And I don't have an answer, but I think it's an interesting question.

1:32:40 _Daniel:_
Yes, I am normal and can be trusted with the key to the doors of perception.

1:32:45 _Mike:_
Let me in exactly.

1:32:48 _Daniel:_
I have a short question.
Where is action in this model?

1:32:58 _Adam:_
So imagine many places Arthur will get into that.
But for what I was thinking with Albus is that actually the five HD two A system.
I talk about two regimes, potentially.
One is more towards overt inaction and modifying the world and strengthened beliefs potentially of that variety.
And the other might be more of adapting to the world.
Robin has a really excellent paper called A Tale of Two Receptors where he talks about five H T, one A receptors.
The ones that antidepressants tend to act on because they tend to reduce this excitatory signaling, talking about them as a kind of passive coping.
And so this would correspond in there's some machine learning models of this by Diane and colleagues where they talk about opponency between dopamine and serotonin.
And they're focusing on the one A as a kind of like patients promoting parameter, keeping you from confidently charging into your policy.
So that would tend to inhibit, I guess, patterns of either overt inaction or potentially even some kinds of mental stimulation too.
You could maybe even think of like even if you're not overtly inactive enacting something externally, there might be more or less brave type styles of thoughts that you might be willing to entertain, going places you might not otherwise be willing to go, and being able to handle the swings in expected free energy.
That might happen as you try to pursue a given path of policies.
But the idea would be that there might be something more like a micro dosing mesodosing regime which might be more of what initially sculpted the five H two A system which evolved with a gene duplication event around the time of the Cambrian Explosion with the advent of jawed fishes.
I'm personally interpreting this as having the significance of evolving in the context of predator prey arms races.
I suspect I could be wrong, but that basically it's locally trying to strengthen patterns of policy pursuit to pursue particular goals in a given context.
And to come back to what I was mentioning earlier with that work by Robin of like a kind of act of coping.
But it seems with rebus there's almost like not that kind of story, and that it's more you're adjusting to the world and actually, if under a very alter state, you are overtly enacting, that's actually kind of a dangerous thing.
I don't know how much to make of this that the five Http receptors are less expressed on, like, motor cortex.
I don't think we know enough to make too much of it.
But it's like some dreams you might not want to act out as they're happening, but they still might powerfully impact you.
So I'm currently actually wondering whether this other rebus like regime might have been specifically sculpted in the context of bonding and actually opening the self to include others.
And that might have been some of the primary selective pressures.
I don't know how to think of that in terms of inaction.
And one more detail that might kind of like not sure what to make of it that kind of goes through both of those excuse the phone would be anthropologically, I believe like psychedelics are oftentimes used in ways that would be both like creating a kind of group solidarity and might be used in the context of pursuing goals together in the world.
So for instance, like a hunting party, they might all do psychedelics together or something that looks a lot like breath work before going out, maybe going to war.
So that's a very different type that kind of includes both a relaxation of the normal boundaries of the self and a kind of gearing you up for pursuing goals in the you know, there's got to be another story of like, so Arthur's expertise is machine learning.
And so it's like you want these systems to act intelligently and not act in other times.
And so basically now we're in the language of policies, and when you deploy them and how and so complicated.

1:37:23 _Arthur:_
Yeah.
I would say that action manifests itself at a few different places.
It's true, I didn't mention it here.
Yeah, I think it's very important, obviously.
I think what the kind of most implicit place where it exists right, is that these belief landscapes are being instantiated ultimately for the sake of adaptive behavior.
Adaptive behavior, adaptive action right, in some sort of environmental context.
And that's the kind of like framework, the deep learning framework that we're using or like the artificial agent framework, right.
Is that the assumption is that the system is supporting some sort of agent that's embodied in some sort of environment which is changing over time such that it can either be adaptive or not adaptive.
I think then the question of how action actually plays into the evolution of these belief landscapes during psychedelics or not acting in the world is a very clear way to modify one's setting, right?
So acting is a way of modifying the function that's providing the sensory input into the system which is going to change how the activity patterns are evolving over time, right, which are going to affect the acute quality of the trip, affect how beliefs are either being strengthened or relaxed.
And I think it's already clear that there's a kind of whole set of folk psychology that's been built around what is or isn't a good way to cultivate a helpful setting and that of course all is a function of action in the world.
I think then there's also this kind of more subtler form of action which is how one thinks, how one deploys attention essentially during this experience.
And I think this deployment of attention has a huge effect on whether there end up being rebus or CBIS like effects.
Right?
So whether one allows oneself to go down certain thought rabbit holes, whether one allows oneself to get kind of stuck in certain kinds of thought patterns.
I think this form of mental action has a very big downstream effect and I think a lot of I'd love to see much more work on this.
I think it's very important, I think it's kind of essential and I think this is kind of one of the most interesting things about these psychedelic experiences is that in some sense, like the most extreme rebus model and the most extreme thebis model could be true for two different individuals, right?
Someone could say I went to hell and I was there for 8 hours straight, or say I had a completely selfless experience, I let go of all beliefs and experienced nothing for 8 hours straight and it was great.
Right?
And clearly those involve two very different neural regimes and I think the nature of that and obviously, given that they involve the same drug and they involve not such a different setting, it's obvious that they have something very important to do with how attention is deployed during this experience.

1:40:50 _Mike:_
Yeah, I do think that this frame of attention, I mean, attention is so important for everything.
And I do think that there's something interesting kind of digging into the Attention and Albus framework that yeah, I'm really curious to see how that'll develop.
I would also say that in terms of active inference and action, there is a cost to holding an intention and then once you discharge your intention, you can release that cost.
So I guess I would have to think about how to apply that to the Canals framework.

1:41:38 _Adam:_
Fred Barrett, I don't know if he's published it yet, but this is kind of like a follow up to a Klaus truly central model that Arthur alluded to is emphasizing basically a lack of executive control and placing that as central to the psychedelic spirits.
Like not controlling your mental action in directed ways as much and then trying to counter more of the types of cognition and phenomenology sort of psychedelics based on just releasing of the normal more agentic modes of policy selection around attention as mental action, although not using active inference.

1:42:20 _Daniel:_
Yeah, very interesting.
Adam, your introduction there of course, attention as covert action, which was echoed by Arthur and Michael, both of you said it really introduces a case where we can use active inference to find continuity between what's happening inside the agent and outside the agent.
Because on one hand we could kind of take a belief oriented frame and we could say, well, what's happening inside the agent are beliefs about things, beliefs about hidden states, beliefs about observations, beliefs about policy.
So that's kind of a belief oriented view where everything is framed basically cognitively.
Or we could take a very action oriented view and then we could think about the interface in a more inactive way and then also even the realm of where many active entities dare not tread in mental action with attention as covert action.
And so then we have, like, a total active account that is mathematically isomorphic with the total belief based account.
They're both just maps.
They're not the territory.
The territory is the person in the room.
So all of this is just talking about the formalism and how we choose to interpret the formalism in terms of it being more inferential or it being more active.
And so there's a lot of ways to go, I guess, in our closing minutes, I would love to hear what are the next moves or what are some areas that you would hope that people look into?
Michael and then the.

1:44:12 _Mike:_
Know is, I think my favorite mental move is to try to drop down on my level of abstraction.
Okay, how is this implemented?
What's going on here?
And then I do think that details of implementation are really generative to look into and, like, the biomarkers and the proxies for figuring out how to parameterize okay, exactly how hot are we talking about with this temperature parameter and so on in different parts of the body.
I have kind of my niche that I'm working on in the Vasomuscular system, which is a rabbit hole.
But, yeah, I do think that the deep canals framework specifically and the canalization paradigm in general, it's good enough that we should be able to dig into mechanism.
So I'm looking forward to that.

1:45:23 _Arthur:_
Great.

1:45:25 _Daniel:_
Adam or Arthur.

1:45:33 _Adam:_
You can go first.
Doesn't matter.

1:45:36 _Arthur:_
Okay.
Yeah, I'll go.
Sure.
Yeah.
I mean, first I want to echo this idea.
I think Mexicans is very important.
This is one of the people we've talked to about talked with about deep canals.
This idea of, like, well, this is great.
We have these two axes.
It'd be wonderful if there were some biological correlates you could look for.
I think that's incredibly important.
My background is also in machine learning, in deep learning.
So I'm currently doing some work around simulating some of these things.
I think especially for these albus dynamics, being able to kind of study under what circumstances you get these different kinds of effects, even in kind of, like, simple Tory models, is kind of important to see how they unfold.
And then we brought it up at the end.
I think it's really important.
It's very interesting to me is the role of the deployment of attention in this.
And there's lines of work where people are trying various researchers are trying to connect, for example, meditation to psychedelic research.
And kind of certain people are trying to tell unified stories about what's going on in the brain when people meditate, what's going on under psychedelics, some of them using these active inference models.
But I think in all of these cases, the deployment of attention and how the deployment of tension changes over time is kind of a key aspect of this.
And it's not as present in the deep canals model right now.
But I think any really robust future kind of like model of these things is going to have to talk about attention quite a bit.

1:47:26 _Adam:_
Well, I guess next steps would be seeing how the review process goes, but also I guess helping Arthur to establish a field of psychedelic machine learning.
Psychedelic inspired machine learning where we try to make systems more flexible and capable, better.
They can handle edge cases better, imagine better in terms of real time policy selection, learn in ways that not too much, not too little, and then maybe so that's useful, potentially earlier.
Like you have a driverless vehicle, do I change lanes or don't I?
You send it back to the Tesla, dojo what do you want it to learn, what do you not want it to learn?
But then down the line well before we even get there, as you're going into this you could see the capacity for a rich bi directional flow between machine learning and psychedelic inspired machine learning.
So it's like you get a bunch of machine learners together and a bunch of people who know a lot about the cognitive science and biology and maybe phenomenology of psychedelics.
And in addition to designing better machine learning systems, they could probably tell you more about how psychedelics act.
And so you can have this kind of virtuous cycle between the biology and the field, but you keep going with that before we get there.
We'll keep going, but before we get there.
Very interested in the implications for best practices.
So for instance, oftentimes you might want semantically neutral energy to kind of get them.
You're just turning up the heat, you're just maybe at first breaking up, I call them defenses, but the usual structure.
But then the question is at what point do you try to direct the canalization process?
Do you wait till after or maybe when the metal is hot, is that a really good time to do it?
And maybe there's no one single question.
This might depend on the substance, the set, the setting, the dose, the person.
So getting clarity on that could be fateful for many people in terms of the outcomes they have.
And specifically what I'm gunning for is I'm on a mission to make compassion meditation treatment as usual for all psychedelic psychotherapy and preferably all therapy.
And so the question is if you're in a state of enhanced imaginative capacity, maybe you're having more ability to tune into your interceptive system, whether you've just increased the channels or maybe you're better capable of because maybe your inflammation went down a bit and you can tune in better because it feels better to do so.
Some combination that might be a really good opportunity to do certain meditations that might update you in particular ways like try to direct the re Annealing process, maybe not just like afterwards integration, but during the session.
And so if we could get clarity on something like how to canalize and recanalyze, like Annealing schedules.
It's going to be complicated, but that's, I think, where we need to head.
And then finally for all this, that would be enough.
But recentering the conversation on psychedelics, on basically meaning and connection would be enough.
But I'm wondering down the line, when we talk of alignment, we're talking about our alignment with our values and maybe the alignments of machines with our values.
And so does this actually end up going to some of the conversations that are happening now about increasingly advanced AI and our relationships to it?
Could there be a story of cannibalization and recalyzation?
You want some things to hold fast and you want some things to be more fluid.
This might be it's always been a timely conversation.
We've always been dealing with this with us, the alignment problem of us, which we often fail, but the alignment problem with these technologies we're developing.

1:51:21 _Daniel:_
Okay, wow.
Well, so many great topics.
Thank you all.
All I have in closing, turn on, tune in, act in, first serve.
Thank you.
See you all next time.

1:51:38 _Mike:_
Bye.
