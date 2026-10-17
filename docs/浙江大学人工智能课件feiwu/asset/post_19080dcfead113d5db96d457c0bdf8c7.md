

## Well-defined problems and solutions

### Problem definition:

- **Initial state**: The initial state that the agent starts in. For example, the initial state for our agent in Romania might be described as _In(Arad)_.

- **Actions**: A description of the possible actions available to the agent. Given a particular state _s_, _ACTIONS(s)_ returns the set of actions that can be executed in _s_. We say that each of these actions is applicable in _s_. For example, from the state _In(Arad)_, the applicable actions are {_Go(Sibiu), Go(Timisoara), Go(Zerind)_}.

![](img/c69bfdf1f6addd09d49cae0440fcc5c7_834_0.png)

### Problem definition:

- **Transition model**: A description of what each action does; the formal name for this is the transition model, specified by a function RESULT(s, a) that returns the state that results from doing action a in state s. We also use the term successor to refer to any state reachable from a given state by a single action. For example, we have RESULT(In(Arad), Go(Zerind)) = In(Zerind)

State Space, Directed network (Graph) and Path: The initial state, actions, and transition model implicitly define the state space of the problem—the set of all states reachable from the initial state by any sequence of actions. The state space forms a directed network or graph in which the nodes are states and the links between nodes are actions. (The map of Romania can be interpreted as a state-space graph if we view each road as standing for two driving actions, one in each direction.) A path in the state space is a sequence of states connected by a sequence of actions.

### Problem definition:

- **Goal test**: The goal test, which determines whether a given state is a goal state. Sometimes there is an explicit set of possible goal states, and the test simply checks whether the given state is one of them. The agent's goal in Romania is the singleton set {_In_(_Bucharest_)}. Sometimes the goal is specified by an abstract property rather than an explicitly enumerated set of states. E.g. 8-queens problem, or reach a state called “checkmate” in chess game

- **Path cost**: a function that assigns a numeric cost to each path. The problem-solving agent chooses a cost function that reflects its own performance measure. E.g. the cost of a path might be its length in kilometers in Romania problem, described as the sum of the costs of the individual actions along the path. The **step cost** of taking action _a_ in state _s_ to reach state _s_’ is denoted by _c_(_s_,_a_,_s_’).

- **Goal test**: state. Some simply check whether the current state is the goal state. Romania is an example of a problem defined by an abstract goal test. E.g. 8-queens.

- **Path cost**: The cost of solving an agent's problem, a measure of the path. The path cost is given by c(s, a, s′).

![](img/c69bfdf1f6addd09d49cae0440fcc5c7_837_0.png)

**Figure 3.2** A simplified road map of part of Romania.

## Example problem: vacuum world

- A vacuum-cleaner world with just two locations

![](img/c69bfdf1f6addd09d49cae0440fcc5c7_838_0.png)

Three kinds of actions: Right, Left, Suck

| Percept sequence | Action |
|---|---|
| [A, Clean] | Right |
| [A, Dirty] | Suck |
| [B, Clean] | Left |
| [B, Dirty] | Suck |
| [A, Clean], [A, Clean] | Right |
| [A, Clean], [A, Dirty] | Suck |
| ... | ... |
| [A, Clean], [A, Clean], [A, Clean] | Right |
| [A, Clean], [A, Clean], [A, Dirty] | Suck |
| ... | ... |

Figure 2.3 Partial tabulation of a simple agent function for the vacuum-cleaner world shown in Figure 2.2.

## Example problem: vacuum world

- **States**: The state is determined by both the agent location and the dirt locations. The agent is in one of two locations, each of which might or might not contain dirt. Thus, there are \( 2 \times 2^2 = 8 \) possible world states. A larger environment with n locations has \( n \times 2^n \) states.

- **Initial state**: Any state can be designated as the initial state.

- **Actions**: In this simple environment, each state has just three actions: Left, Right, and Suck. Larger environments might also include Up and Down.

- **Transition model**: The actions have their expected effects, except that moving Left in the leftmost square, moving Right in the rightmost square, and Sucking in a clean square have no effect. The complete state space is shown in Figure 3.3.

- **Goal test**: This checks whether all the squares are clean.

- **Path cost**: Each step costs 1, so the path cost is the number of steps in the path.

![](img/c69bfdf1f6addd09d49cae0440fcc5c7_839_0.png)

