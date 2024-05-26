---
tags:
  - MOC
sticker: lucide//map-pin
---
# Conformance Checking
---
>[!idea] Why Conformance Checking
>The main motivation behind this branch of work is Process Mining, which involves extracting meaningful models for underlying process of systems of a given set of observed behaviour in order to better understand them. But methods like ML or anything else that is used naturally raise a question on how reasonably does the output models match the processes. Especially with un-explainable black box approaches of methods like ML.
>
>Conformance Checking is the art of judging the performance of a process model by trying to match it with the observed behaviour of the model, without depending on the origin of the model. Observed behaviour comes in the form of traces in event logs while process models are blueprints that are a possible description of the underlying process.
>
>The measure of how the model reflects the system is usually talked about based on the following factors
>- *Fitness*, which is how well the model is able to talk about what is there in the logs.
>- *Precision*, which is how much the model deviates from the given log.
>- *Generalisation*, which is how much of the system can the model talk about, outside of the log.
>- *Simplicity*, Occam's Razor, I guess.

--- 
## Notes
- [[Alignments (Conformance Checking)]]
- [[Anti-Alignments (Conformance Checking)]]

--- 
## MOCs

---
# References