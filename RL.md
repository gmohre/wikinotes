#Reinforcement Learning

## RL Goal 
* Select actions to maximize total future reward.

## RL Agent Taxonomies
* Value Based -> has Value Function v(s) implicitly No Policy (note)
* Policy Based -> represent Policy using a data structure. no v(s) (emotion)
* Actor Critic -> P + v(s) (IDK)
* Model Free -> P and or v(s), no model, P or v(s) based on EXP
* Model Based -> P and or v(s) build dynamics model, do lookaheads.

## Learning and Planning
* Reinforcment Learning -> ENV is initially unkown, the agent interacts, the agent imporves policy.
* Planning -> ENV model is known, interacts and improves policy.

## Exploration 
* Finds for information about the env
* eg. Try a new restaurant.

## Exploitation
* Exploits known info to max reward.
* eg. Go to your favorite restaurant.

## RL Environment
* ENV State is S e/t.
* Formalism that helps us understand private State
* "Is Markov"
* This State is private. 
* Environment State is "invisible to the agent"
* Algs cannot depend on these private numbers.
* ENV state is the info used interally detemrine what Happens next.
* Initiates Ot
* Influenced solely by At
* Receives action At 
* Emits observation Ot
* Emits scalar rewards Rt
* Even if it is visible it may contain irrelevant info.
* State is used to pick the next observation / reward.

## RL Agent
* Agent State S a/t 
* S a/t = f(Ht) (any function)
* S a/t could be based on complete sequence Ht or subset therof.
* Agent execute At
* Agent receives Rt
* Agent receieves Ot
* Utilizes Algorithms
* Interacts with environment in loops
* Has own subjective representation within Env

### Notes
* Picks next action
* Behavior is based on filtered observations.
* How to pick actions given some state summary? Ht

## RL Observation
* Ot
* Agent receieves observations

## RL Prediction
* Given the policy
* How well will I do given P

## RL Control
* Optimize the policy
* Find the best policy

## RL Reward 
* R predicts the next immediate rewards
* Rt
* scalar feedback signal for decision making
* Agent receives rewards
 * State transition model, prob of next state given current state and actio 
* optimize a sequence of decisions
 * Reward transition model, prob of next reward given current state and action
* optimize rewards
* reward hypothesis
* sum of rewards can be divided into episodes

### Notes
* reward paradigms seem to be opposite meaures of different metrics, except for when it is to a constant ($, win/lose backgammon, atari score)
* once a reward is processed, future evaluations can change depending on discount factor / time scaling
 
## RL Action
* At
* Agent execute Action
* change dependon Ot

### Notes
* Decisions?
* have consequences
* give up reward to gain larger reward
* refuel in racing, save money in finance, etc
* can be a function of experimentation

## RL Policy 

* Used to predict expected future
* Agent's behavior function
* Map from state to action 
* Deterministic Policy -> a = f(s)
* Stochastic Policy -> f(a|s) = P[A = a|S = s]

### Notes
* How much total reward will you get in the future? Expected Future Total Reward

## RL Value Function 
* v(s)
* basis for optimizing behavior
* should have an output for each state s
* how good is a state or a proposed action? 

## RL Discount 
* modifies balance between recent / temporally distant rewards

## RL Model 
* How the agent thinks the env works
* predicts what the env will do next

## RL Transitions
* P predicts the next state

## Fully Observable Environment
* Agent directly observes every S e/t
* A e/t = S e/t
* In the fully observable environment you can use a markov decision process (MDP)
 
## Partially observable Environment
* A e/t != S e/t
* Agent indirectly observes env
* PartiallyObservableMDP
* Agent constructs state representation S a/t

* Complete History: S a/t = Ht
* Beliefs of env state : S a/t = (P[S e/t = s^1]... P[S e/t =  s^n]
* Recurrent neural network: S a/t = o(S a/t-1 Ws + OtWo)

## Markov State / Information State
* The future is independant of the past given the present
* H1:t -> St -> Ht+1:<><>
* Environments evolve into the future
* State is a condition of the future
* Once the state is known, history may be thrown away
* Allows you to discard history

### Notes
* State is repeatable?

Some questions require lookback, aka what is the velocity of the helicopter?

## History
* Ht
* Maps history to actions
* Time series defines the experience of the agent, comprised of At, Ot, Rt
* History State includes all rewards

# Feedback 
* Ht to decide Ot/Rt
* Decision rates measured in hz
* Is delayed.
* Retrospectives at intervals

### Notes
* Can this delay be measured in rate / magnitude ?

## State
* St = f(Ht)
* Encapsulates info used to determine what happens next

## Time Matters
* Sequential data

### Notes
* what is iid paradigm / data ?

## Actions matter
* Measurement of how much actions matter ?

## Terms / Notes
Scalar == Comparable / Can put on axis
Must be a conversion to a single metric.
The agent that gets max value is the one that trades risk and locality of reward.
Tolerance of history range for S a/t ?
Entire history "Is Markov"
Sequences of Ot, Rt, At are collected into Episodes
