# Reinforcement Learning: An Introduction

Source: http://www.incompleteideas.net/book/the-book-2nd.html

> Richard S. Sutton and Andrew G. Barto

Systems that try to maximize something (whatever that might be) are qualitatively different from equilibrium-seeking systems, and he argued that maximizing systems hold the key to understanding important aspects of natural intelligence and for building artificial intelligences.

## Chapter 1. Introduction
The idea that we learn by interacting with our environment is probably the first to occur to us when we think about the nature of learning. Whether we are learning to drive a car or to hold a conversation, we are acutely aware of how our environment responds to what we do, and we seek to influence what happens through our behavior. __Learning from interaction__ is a foundational idea underlying nearly all theories of learning and intelligence.

Reinforcement learning is learning what to do, how to map situations to actions so as to maximize a numerical reward signal. The learner is not told which actions to take, but instead must discover which actions yield the most reward by trying them. In the most interesting and challenging cases, actions may affect not only the immediate reward but also the next situation and, through that, all subsequent rewards. These two characteristics, trial-and-error search and delayed rewards are the two most important distinguishing features of reinforcement learning.

Markov decision processes are intended to include just these three aspects: sensation, action, and goal.

One of the challenges that arise in reinforcement learning, and not in other kinds of learning, is the trade-off between __exploration and exploitation__. To obtain a lot of reward, a reinforcement learning agent must prefer actions that it has tried in the past and found to be effective in producing reward. But to discover such actions, it has to try actions that it has not selected before. The agent has to exploit what it has already experienced in order to obtain reward, but it also has to explore in order to make better action selections in the future.

Another key feature of reinforcement learning is that it explicitly considers the whole problem of a goal-directed agent interacting with an uncertain environment, starting with a complete, interactive, goal-seeking agent. All involve interaction between an active decision-making agent and its environment, within which the agent seeks to achieve a goal despite uncertainty about its environment. Correct choice requires taking into account indirect, delayed consequences of actions, and thus may require foresight or planning.

### Elements of Reinforcement Learning
Beyond the agent and the environment, one can identify four main sub-elements of a reinforcement learning system:
- Policy
    - Defines the learning agent's way of behaving at a given time.
    - Policy is a mapping from perceived states of the environment to actions to be taken when in those states.
    - Ex: When one senses danger, run away!
- Reward signal
    - A reward signal defines the goal of a reinforcement learning problem.
    - The reward signal defines what are the good and bad events for the agent.
    - The agent's sole objective is to maximize the total reward it receives over the long run.
- Value function
    - Reward signal indicates what is good in an immediate sense, a value function specifies what is good in the long run.
    - Value of a state is the total amount of reward an agent can expect to accumulate over the future, starting from that state.
    - To make a human analogy:
        - Rewards are somewhat like pleasure (if high) and pain (if low).
        - Values correspond to a more refined and farsighted judgment of how pleased or displeased we are that our environment is in a particular state.
    - Rewards are in a sense primary, whereas values, as predictions of rewards, are secondary. Without rewards there could be no values, and the only purpose of estimating values is to achieve more reward. Nevertheless, it is values with which we are most concerned when making and evaluating decisions.
    - Rewards are basically given directly by the environment, but values must be estimated and re-estimated from the sequences of observations an agent makes over its entire lifetime.
    - The most important component of almost all reinforcement learning algorithms we consider is __a method for efficiently estimating values__.
- Model
    - This is something that mimics the behavior of the environment.
    - Allows inferences to be made about how the environment will behave.
    - Models are used for planning, way of deciding on a course of action by considering possible future situations before they are actually experienced.

### Limitations and Scope
Think of the state as whatever information is available to the agent about its environment. Our concern in this book is not with designing the state signal, but with deciding what action to take as a function of whatever state signal is available. The policies that obtain the most reward, and random variations of them, are carried over to the next generation of policies, and the process repeats.

How might we construct a player that will find the imperfections in its opponent's play and learn to maximize its chances of winning? A __minimax player__ would never reach a game state from which it could lose, even if in fact it always won from that state because of incorrect play by the opponent. About the best one can do on this problem is first to learn a model of the opponent’s behavior, up to some level of confidence, and then apply dynamic programming to compute an optimal solution given the approximate opponent model.

### An Extended Example: Tic-Tac-Toe
State A has higher value than state B, or is considered "better" than state B, if the current estimate of the probability of our winning from A is higher than it is from B. How well a reinforcement learning system can work in problems with such large state sets is intimately tied to how appropriately it can generalize from past experience. Reinforcement learning can be applied in either case. A model is not required, but models can easily be used if they are available or can be learned.

> Reinforcement learning is a computational approach to understanding and automating goal-directed learning and decision making.

The early history of reinforcement learning has two main threads:
- Learning by trial and error.
- Problem of optimal control and its solution using value functions and dynamic programming.
- Temporal-difference methods.

> Law of Effect.
>
> Of several responses made to the same situation, those which are accompanied or closely followed by satisfaction to the animal will, other things being equal, be more firmly connected with the situation, so that, when it recurs, they will be more likely to recur; those which are accompanied or closely followed by discomfort to the animal will, other things being equal, have their connections with that situation weakened, so that, when it recurs, they will be less likely to occur. The greater the satisfaction or discomfort, the greater the strengthening or weakening of the bond. (Thorndike, 1911, p. 244)

To be considered a __reinforcer__, the strengthening or weakening must persist after the reinforcer is withdrawn; a stimulus that merely attracts an animal’s attention or that energizes its behavior without producing lasting changes would not be considered a reinforcer.

> In a 1948 report, Alan Turing described a design for a __pleasure-pain system__ that worked along the lines of the Law of Effect:
> >
> When a configuration is reached for which the action is undetermined, a random choice for the missing data is made and the appropriate entry is made in the description, tentatively, and is applied. When a pain stimulus occurs all tentative entries are cancelled, and when a pleasure stimulus occurs they are all made permanent. (Turing, 1948)

Networks use error information to update connection weights, but this misses the essential character of trial-and-error learning as selecting actions on the basis of evaluative feedback that does not rely on knowledge of what the correct action should be. Basic __credit-assignment problem__ for complex reinforcement learning systems: How do you distribute credit for success among the many decisions that may have been involved in producing it.

