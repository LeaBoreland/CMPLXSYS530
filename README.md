# CMPLXSYS530

### Model Proposal for Lea Boreland: Rule-Setting and Hierarchy for Incentive Compatibility 

### Lea Boreland 

#### Course ID: CMPLXSYS 530
#### Course Title: Computer Modeling of Complex Systems
#### Term: Winter, 2019
 

### Goal

This project will investigate a simple question: How can organizations create rules that work with how people work? The idea is that institutions succeed when they tap into existing incentive loops. This is true of governments, teams, start-ups, and large corporations. These organizations may have blips of incentive compatibility, but this model will investigate how we can design the system itself to select for this trait of "working with how people work." 

Incentive compatibility in our context will be defined as a circumstance in which rules match preferences. That the preferences (and thus rules) will be within the span of acceptable and productive behavior is taken for granted. The definition of "rules" will be kept intentionally vague: it comprises the idea of both norms (colloquially concocted and enforced expectations of team-member behavior) and rules (explicit policies). Likewise with our understanding of preferences, which comprises things that an individual would cogitate and express explicitly as well as more implicit personality forces. 

### Justification

ABM is a perfect fit for this project because one of the main elements of complexity it deals with is the fact of heterogeneous actors. A set of rules at any one moment in time may work great, but the second that employees churn, this compatibility may be destroyed - such is the nature of preference heterogeneity. What works well for one person does not work well for another. 

There are also a number of technical advantages. The challenge of this model is to create a system that is flexible enough to respond to the preferences of heterogeneous actors; this will allow it to attain incentive compatibility more often. On the opposite side of this, organizations want and need stability. Rules cannot change every time one employee finds them incompatible. Finally, there is the element of feedback delays. It may take an organization some time to find an instance of incentive compatibility that it would like to address, and then it may take the organization some time to figure out how to address it. Flexibility, stability, and delays are all measurable through the ABM format; they can be visualized and optimized towards. 

Additionally, it is necessary to parameterize aspects of the model to balance these competing desires. ABM permits this. Being able to modify aspects of hierarchy (number of levels, number of agents at each level) and rule-setting paradigms (does the "CEO" set all rules? Or do CEOs and local bosses co-instruct rules?) and iterate through the combinations quickly, all while illustrating the effects on a UI/UX, is extremely helpful.  

### Main Micro-level Processes and Macro-level Dynamics of Interest

The dynamic of interest is the varying emergence of incentive compatibility according to conditions such as hierarchy and rule-setting paradigms. The model needs to keep track of three levels of incentive compatibility: individual, team, and company-wide. This is because a system that selects for incentive compatibility at the bottom level may create log-jams at the top, so individual and team compatibility ratings are not sufficient. I am interested in the tradeoffs involved in selecting for compatibility at these levels. 

### Model Outline
 
#### 1) Environment

In this model, organizational rules and hierarchy structure comprise the environment. The environment will own the system incentive compatibility and any other system-level indicators I would like to track, such as delays in feedback. The environment will own two procedures: it will determine how rules are set at each level of the organization, and it will determine how individuals are "promoted" through the organization. 
 
#### 2) Agents

Agents are employees in this model. Each agent owns one variable: their personal preferences. Each agent will own a method to compute their personal rule set and their personal incentive compatibility.

#### 3) Action and Interaction

The topology is a tree. Agents or "employees" only interact with their parents and children. They interact in two concrete ways: to determine their personal rule-set (based on the rules of their parents, and possibly their parents' parents) and to promote agents through the system (based on incentive compatibility). 

No indicators of brother-sister or "team level" incentive compatibility are introduced.

Action Sequence

On a given tick: 

1. Agents derive their personal ruleset using organizational policy and compute their personal incentive compatibility. 
2. Graphics are updated to represent the incentive compatibility of actors.
3. Parent nodes (all nodes besides the leaves) dole out promotions. They pick their highest-achieving son/daughter, which then takes over their position in the event that they themselves have been promoted. 

#### 4) Model Parameters and Initialization

Parameters:
1. Hierarchy: levels and number of agents at each level
2. Length: how long is an agent's preference set string?
3. Complexity: how complex is an agent's preference set string? I.e., is it a binary or a random integer out of 5, 10, 50...
4. Rule-setting paradigm: I have yet to figure out how to parameterize this, but I would like to easily be able to switch between different rule-setting modes (CEO sets company rules vs. local bosses, etc). 

Initialization: 
1. A tree is built under the specifications of hierarchy.
2. Agents are initialized under the specifications of length and complexity. 

#### 5) Assessment and Outcome Measures

1. System incentive compatibility: how well does the whole organization achieve incentive compatibility? 
2. Team incentive compatibility: how well do particular teams achieve incentive compatibility? Do we find that particular levels of hierarchy are having more success? 
3. Local incentive compatibility: how well are individuals faring? Are there areas where individuals are faring particularly well? 
4. System delays: how quickly are instances of incentive incompatibility addressed? 

#### 6) Parameter Sweep

I would like to sweep through hierarchy and rule setting paradigms at various degrees of complexity. Hierarchy and rule-setting paradigms will be my primary explanatory variables. 
