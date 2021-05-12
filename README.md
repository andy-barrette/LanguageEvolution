Language Evolution Project

Controls:
+/-			Zoom in/out of simulation.
[space]		Toggle visual depiction of simulation.
P 			Toggle pause

What I've Learned.

Thoughts:

The ultimate goal of this project was to determine whether or not language can emerge from evolution of a linear life-form.  What do I mean by "linear"?  In this sense, a life-form is linear if each of its outputs can be expressed as a linear combination of its inputs.  i.e. For some set of inputs I and outputs O (each expressed as vectors), there is some matrix M such that O=MI.  The matrix M represents an algorithm which determines how the life-form interacts with its environment. M and initial conditions together completely determine the behaviors of a given life-form.  

I want this simulation to be as general and as abstract as possible so that the life-form can easily be expanded by, for example, incrementing some parameter which effectively adds an element to its input or output vectors.  This means that the types of inputs and outputs should be abstracted down to the most basic interactions that can occur between a life-form and its environment. We want a life-form that is at heart very simple, but which can grow to interact with its environment in very complex ways.  For example, we would want it to be able to search for and pick up resources, but we might also want it to be able to carry these resources and use them as extensions of its own body.  The problem is that if the life-form is too abstract, we probably won’t be able to identify it as life.  So, if we want a particular type of life to emerge (e.g. life as we know it) then we must sacrifice the generality which would make the evolution process more simple and elegant for the type of specificity of function that we are used to. 

There is no way to express the inputs in a completely symmetric way and, in fact, the environment as well as the inputs I choose will end up dictating the vocabulary of the life-forms.  For example, if they can pick things up, move about, and climb over things, then their vocabulary will contain words like "grab", "move", and "climb" and otherwise there will be no basis for these words to emerge from evolution. If I want to be able to read out a conversation, between to life-forms, such as "X needs Y to turn right and eat the blue thing", then there must be some physical basis for each of the words used. "turn right", "eat": These require certain outputs to exist. "blue thing": This requires certain inputs to exist. "X needs Y": This requires life-forms to have names and be able to distinguish between different life-forms similar to how humans can distinguish different faces.

Ultimately, the inputs and outputs of the life-forms in the simulation are not arbitrary for a given type of environment, but reflect the physics of the environment. For example, the life-form will evolve differently if its sight is limited in distance and/or FOV as opposed to being visually omniscient or if it can hear but cannot distinguish the direction of a sound as opposed to hearing where a sound came from.  Perhaps the life-forms have to move around like ants, or maybe they can manipulate objects from afar.  Do they eat?  Do they run out of breath?  Do they lose health from moving faster?  All of these sorts of questions define some physical property of the environment which will ultimately shape the life-form that evolves within it.

Life cannot exist without needs.  In this simulation, the need will be resources.  The complexity of the resources will determine the extent of ingenuity that evolves.  For example, if a particular food is required periodically, does that food grow in clusters? Does it migrate? Does it fight back? Everything that the life-forms do - be it moving, using tools, or communicating – will have the purpose of improving resource collection, so the nature of the resources determines the evolved habits.  For this reason, designing the food source is important.  It should be something that is hard to find but that is also predictable in location and behavior (ideally the life-forms will evolve habits best suited for these patterns). In essence, the food source has to be a life-form of its own. To avoid having to engineer or evolve an entirely separate life-form as a food source alone, I decided to use the primary life-forms of the simulation as their own food source. This way, the complexity of the life-forms always matches the complexity of their food source, and thus evolution is not limited by an uninteresting basic resource.  So the primary life-forms are carnivores (perhaps cannibals).

With communication, the physics that we choose is even more telling of the type of language that will result.  For example, do life-forms of the same species communicate one letter at a time over an extended time period or are messages transmitted instantly?  Can enemies eavesdrop on messages or are they transmitted telepathically? Do life-forms speak continuously or are they allowed to stay silent depending on some mental switch? Can life-forms distinguish between each other based on voice?  The answers to these sorts of questions will ultimately determine the language, what can be communicated via this language, and the actions that can result from communication. If we want life-forms that can command each other or plan strategies, then these commands must also be able to be carried out over an extended period of time. The current input-to-output process is instantaneous, but collective planning would require some sort of memory.  This can be in the form of a memory bank which is written to or read from depending on inputs and outputs or it can simply be a feedback loop in the input-to-output process that allows information to propagate from cycle to cycle (this is the method I've decided to use in the future).

I think it’s important to define the mechanics of the simulated reality rather than the bahaviors of the life-forms.  For example, I could hardwire life-forms to behave defensively when being attacked, and this would require me to define a certain type of head-on charge as being an “attack” as well as a “defensive” mode, but the more general approach is to simply cause damage to be done upon fast contact (a physically reasonable result) and leave it to evolution to determine how life-forms respond to the damage, if at all.  In this case, I define only the most physical aspects of the environment/interaction in expectation that the optimal responsive characteristics will evolve as a result.

Further generality means making inputs from aspects previously reserved as user controls.  For example, I can add memory/feedback/soundIO variables to the life-forms’ input sequence, but the more general approach would be to leave the quantity of such variables up to the evolution process.  This would undoubtedly make evolution take longer, but it would have the benefit of removing the limitations on intelligence evolution that are inherent when the algorithms of life-forms have a fixed size.

To help the evolution process in a reasonably short manner, evolution has been subdivided into three phases:

Phase 1: Free-for-all evolution without language.

Overview
This phase allows for the creation of several good interaction algorithms.  A life-form with a randomly generated algorithm will, in general, not be able to survive.  It will probably do something like move aimlessly in circles or in a straight line, or it might just stay in one place and make randomly erratic motions when stimulation occurs. We can imagine how a good interaction algorithm allows a life-form to avoid these things.  It might steer it toward food and subsequently cause it to stop or follow closely when it has reached the food source.
Inputs available are:

Sight – Up to a specified distance, life-forms can see the type, health, distance, and direction (one of a specified number of angles taken relative to forward) of another life-form (alive or dead) within a 90 degree field of view.

*It would be advantageous to be able to determine what direction a life-form is facing by sight.

Hearing – phrases by only one life-form within a given radius.  If only life-forms of the same type can be heard, then the life-forms are “telepathic”.  If health is used to determine which life-form is heard, this could result in a species led by either the hungriest or fullest members (an interesting dichotomy).
Health – The health of the life-form in question.

Mental state – These inputs/outputs provide feedback functionality that can result in something resembling thought. 
*Age – This is not currently used but it would result in gerontocracy. It might be interesting to add a feature causing the randomly generated life-forms to partially imitate elder life-forms that they come into contact with. This would allow for evolution during the lifespan of life-forms.

Outputs available are:

Eating – If >0, life-form eats from whatever is in front of it (if anything).

Translation – In the forward or backward direction and at some rate depending on a number from –Inf to +Inf.  The maximum forward velocity is larger than the maximum backward velocity (contradictory to generality).

Rotation – To left or right and at some rate depending on a number from –Inf to +Inf. 
Speech – Some phrase queued for the hearing pleasure of other life-forms (not implemented in this Phase).
Particular specifications and considerations:

The life-forms are carnivores.  They eat only each other. 

When they die, their remains remain for a certain amount of time, after which they disappear and a new life-form is created.

Health is lost at a constant rate.  Being eaten causes health to decrease at a constant rate for the life-form being eaten and increase at the same rate for the life-form which is eating. Life-forms can only eat things that are directly in front of them. Health is capped at the birth value, however I suppose this is arbitrary. 

Currently, the lifespan (without eating) is 3 times larger than the time required for a life-form’s body to completely decay after dying.  I.e. dead matter doesn’t remain for very long.  The result is that life-forms must rely more so on hunting of live food rather than scavenging dead food. This means that life-forms will have a tendency to move constantly and will not be able to efficiently eat from still food-sources.  This uneven hunting-gathering balance might be tilted the other way in future studies.

¼ of newly-created life forms are mutations of the current eldest life-form and the others have random algorithms.

Certain actions like turning should be symmetric with respect to vision.  For example, if an algorithm dictates that a life-form veers to the right when approaching an object on the right, then we would think that this life-form should veer to the left if the object were instead on the left.  i.e. The life-form should not have a preferred direction.  While this makes sense to implement, it would require fundamental hardwiring of the algorithm which I’m not sure would actually be possible in nature.  For example, when I do an activity that requires my hands to work symmetrically, is that possible because my hands are then controlled by the same part of the brain which learned the activity once, or is it possible because I have learned the activity separately with both hands? This functionality has been implemented. An obvious example where this functionality fails:  Imagine you have two enemies the same distance in front of you, but one is 30 degrees to your right while the other is 30 degrees to your left.  Visual symmetry would dictate that your only action can be to move either straight forward or straight back, when in reality you would probably turn in an arbitrary direction and run backward.

Life-forms are continually created within a 2 by 2 area, and life-forms that venture out too far from the spawn area will surely die.  Therefore adventurousness is discouraged in this environmental regime.  This spawn area defines the range of interaction that life-forms will evolve to work with best.  However, the spawn area can only really be defined with respect to other parameters of the simulation such ax maximum velocity and sight range.  If all of these things are scaled up by a factor of 2, then the environment is essentially the same.  Therefore there is a delicate interplay between these environmental parameters which should be considered carefully when deciding them.

While life-forms are an experiment, they cannot perform experiments: A life-form cannot modify its algorithm based on tests of algorithm effectiveness.
Life-forms should be able to do more with resources than simply eat them.  Dead life-forms should eventually become inedible fossils which can be moved around or used for things.  See Thought B.

Inputs determine an incremental change in position in the current setup, but it might provide more advanced control if either (a) inputs determined higher order time derivatives of motion or equivalently (b) a feedback loop of motion inputs is implemented.
Phase 2: Evolution of multiple species without language.

Overview
This phase simply allows the previous algorithms to further evolve to distinguish between food sources, because a colony based on an algorithm that eats itself will not survive for very long.

Phase 3: Evolution of multiple species with language.

Overview
This phase adds language to the previous algorithms.  This language is simply the ability to receive messages as inputs and send a message based on inputs.  This functionality may never prove useful, but if it evolves to be useful, it will give communicating algorithms an advantage over non-communicating algorithms.  The simplest test of language is to pit an evolved communicating algorithm against an evolved noncommunicating one (from phase 2).  If the communicating algorithm usually wins, then a practical language has formed and further study of its syntax is merited.