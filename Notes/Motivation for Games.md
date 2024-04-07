---
tags:
  - Note
  - Incomplete
---
202403061403

Tags : [[Games on Graphs]], [[Logic]]
# Motivation for Games
---
>[!question] Coffee Machine 
> The goal is to model a coffee machine with the following specifications:
> - When we press the start button, the coffee machine starts producing coffee in the next instant.
> - When the stop button is pressed and coffee is being dispensed, the coffee machine stops making coffee in the next instant.

We work with the assumption that the machine runs on a clock, so "next instant" is well defined. The goal is to make a [[Büchi Automata]] to model the machine.

>[!error] What doesn't work
>The most obvious step here is to model the above conditions as an [[Linear Temporal Logic|LTL]] formula and make a [[Büchi Automata]] that satisfies it.
>
>We can write the specifications as follow
>- $\varphi_{1} := \mathbf{G}(\text B_{b}\to \mathbf{X}\text{C})$
>- $\varphi_{2} := \mathbf{G}(\text{B}_{e}\to \mathbf{X}(\lnot \text{C}))$
>- 
>And we want to make an automata for $\varphi:=\varphi_{1}\land \varphi_{2}$
>
>At this point, we could have figured out if it was possible to make the machine by checking for emptiness of the language of the automata. But here is the problem, the language of this automata is not empty, because there exits the following model
>>[!example]
>>$$
>>\begin{array}{c|cc}
>>\text{B}_{b}  &\bot  & \bot  &\bot  & \cdots\\
>>\text{B}_{e}  &\bot  & \bot  &\bot  &  \cdots\\
>>\text{C}      &*     & *     &*     & \cdots\\
>>\end{array}
>>$$
>
>But $\varphi$ is obviously not satisfiable, if someone pressed both the start and stop button, the specifications would then be violated no matter what the machine does.
>Hence Satisfiablility does not work, we need a stronger condition.

The problem is that we failed to address the fact that there are parts of the external environment that cannot be controller and affect the system. (here, pressing both the buttons at the same time)

We fix that by constructing a scenario where there are 2 agents, player(the system) and the opponent(the environment) and they play a game together that models the given systems in a way that a run of the game is accepting iff it corresponds to the model satisfying some logical sentence.

---
# References
[[Games (on graphs)]]