# Definitions

## Inference (Reasoning)

Can refer to: [6]
1. the conclusion reached from evidence and reasoning
2. the process of reaching that conclusion

### Logical reasoning

"Steps in reasoning, moving from premises to conclusions" [6]

- May rely on a formal system of logic common to CS, math, physics, and linguistis: first-order logic / first-order predicate calculus / predicate logic. 1st order logic is distinct from the the simpler propositional logic because it allows for predicates and quantification. First order logic, as compared to propositional logic: [9]
	- "A predicate takes an entity or entities in the domain of discourse as input and outputs either True or False. Consider the two sentences "Socrates is a philosopher" and "Plato is a philosopher". In propositional logic, these sentences are viewed as being unrelated and might be denoted, for example, by variables such as p and q. The predicate "is a philosopher" occurs in both sentences, which have a common structure of "a is a philosopher". The variable a is instantiated as "Socrates" in the first sentence and is instantiated as "Plato" in the second sentence. While first-order logic allows for the use of predicates, such as "is a philosopher" in this example, propositional logic does not."
	- "PROLOG programs are sets of first-order rules" [10]

#### Deductive

- "Top-down logic" [5]
- "Proceeds from general premises to a specific conclusion" [5]
- "the premises do not guarantee the conclusion" [7]
- "Deriving logical conclusions from premises known or assumed to be true, [using] the laws of valid inference being studied in logic" [6]
- "derives the consequences of the assumed" [7]

Most famous, oldest author: Aristotle

##### Example [5]:
- (Premise 1) All men are mortal.
- (Premise 2) Socrates is a man.
- (Conclusion) Therefore, Socrates is mortal.

##### Deductive programming [11]
- predominant in "classical software engineering and algorithm design" [11]
	- "One aspires a general problem description as starting point from which a program or algorithm is developed as a particular solution." [11]
- "subsume[s] established software development methods" [11]
- power methods that "partly automatize the programming and verification process" such as (below) have a "common deductive foundation" [11]
	- automatic code generation from UML diagrams
	- (deductive) program synthesis to generate algorithmic parts
	- program transformation and refactoring to optimize programs
	- verifying programs via
		- theorem proving
		- model checking
		- static analysis

#### Inductive

- "induction is just the inverse of deduction" [10]
- "Bottom-up logic" [5]
- "The process of reaching a general conclusion from specific examples" [1]
- intrinsically unsound [11]
	- adds to but does not replace deductive methods [11]
- "Inference from particular premises to [a] universal conclusion" [6]
- conclusions are hypotheses, unprovable without additional stuff [11]
	- "the most severe objection against IP" [11]
		- "What is the use of methods whose results cannot be proven correct and possibly deviate from what was intended?" [11]
		- One answer: "all software development necessarily makes a transition from a first informal and often incomplete problem description by the
user or customer to a complete and ideally formal specification." [11] This transistion is: [11]
			-  incapable of formal proof
			- possibly based on—non-systematic inexplicit generalization
		- "There is no reason why systematically incorporating existing or easily formulated data by inductive methods should not improve efficiency and even validity of software development" [11]
- "Process by which a conclusion is inferred from multiple observations" [6]
- "philosophical (i.e. suggesting a theory to explain observed facts)" not "mathematical (i.e. proving a property for all members of a well-ordered set)"

Connection to ML:
- "in general, machine learning involves building theories that explain the observed data" [10]

##### Learning from Examples

- Examples can be all positive, or a mixture of positive and negative. Negative examples constrain the set of models that are consistent with the examples [1].
- "if the data at hand is representative then it is likely that identified patterns actually hold in the general case and that, indeed, the induced result meets the general problem" [11]

##### Inductive bias
"Explicit or implicit assumption(s) about what kind of model is wanted." [1]

##### Inductive Learning Hypothesis
- "Any hypothesis found to approximate the target function well over a sufficiently large set of training examples will also approximate the target function well over other unobserved examples." [1]
- "Given some data D and some background knowledge B, learning can be described as generating a hypothesis h that, together with B, explains D." [10]
	- "the hypothesis H together with the background theory B should cover all positive and none of the negative examples" [8]
- "a logic program, i.e. a definite clause program" [8]

##### Hypothesis Correctness

There are two main types of results for inductive inference:
1. a conclusion [6]
	- Truth value:
		- may or may not be true
		- true ~X% of the time
		- may only be true when certain preconditions are met
	- Testing
		- "Conclusions inferred from multiple observations may be tested by additional observations."
2. a model: 
	- Examples are generalized into a model that is then used to make predictions on new, previously unseen inputs. 
	- Learned models may or may not capture what the human in the loop wanted. - Models could be:
		- a category
		- a pattern, like the patterns PROSE learns to extract data from large files
		- a transformation or program, like the transformations Rafazer learns over ASTs

##### Inductive Logic Programming
- "a subfield of machine learning" [12]
- "uses logic programming as a uniform representation for examples, background knowledge and hypotheses" [12]
- "designed to learn first-order rules" [10]
- "concerned with finding a hypothesis H from a set of positive and negative examples P and N" [8]
- the ability to "provide declarative background knowledge to the learning engine is viewed as one of the strengths of inductive logic programming" [8]
- "inductive machine learning in a logical setting" [12]
- "positive examples + negative examples + background knowledge ⇒ hypothesis" [12]
- "Given an encoding of the known background knowledge and a set of examples represented as a logical database of facts, an ILP system will derive a hypothesised logic program which entails all the positive and none of the negative examples." [12]

Uses
- "particularly useful in bioinformatics and natural language processing" [12]

##### Inductive programming (IP)
- "emerging field" [11]
- reasoning methods & theory for [11]
	- computer programming
	- algorithm design
	- software development

###### Inductive program synthesis (IPS)
- "major subfield" of IP [11]
	- started in the 70's [11]
- "the (semi-)automatic construction of programs from exemplary behavior" [11]
- HARD problem [13]
- "not a unified research field until today but scattered over several different established research fields" [11]
	- spans/intersects with/been a niche within many fields such as [11]
		- machine learning
		- artificial intelligence
		- programming
		- software engineering
		- algorithms research
		- inductive logic programming
		- genetic programming
		- functional programming
	- "goes beyond each of these fields in one or the other aspect[;] therefore [it] is a research field in its own right" [11]
		- e.g., goes beyond classical machine learning because
			- focused on "learn[ing] general programs including loops and recursion"
			- not just learning "(mostly nonrecursive) models or classifiers in restricted representational frameworks" such as
				- decision trees
				- neural networks
	- these disparate communities (and jargon?) "impedes an exchange of theory and techniques and ... progress of [IP]" [11]
- Inputs, Process, Outputs
	- Starting point(s) for IP methods are specific, (knownto-be-)incomplete specifications of a "target" function to be constructed: [11]
		- incomplete specifications specify behavior for only a small part of the target function's domain [11]
		- example specifications include: [11]
			- specific data of a problem—use cases
			- desirable (and undesirable) behavior of a software
			- (typical specification type) input/output examples (I/O-examples) of a function or a module interface (a subset of the graph of the function)
				- referred to as *Programming By Examples (PBE)*
				- variables in I/O examples may be allowed
				- more tractable than [general] program synthesis because [13] 
					- "[automated?] reasoning about concrete input states is much easier than dealing with properties over symbolic program states"
					[13]
					- humans--programmers and non-programmers alike--have an easier time generating examples than logical/relational/complete specifications [13]
						- but they may not be good at generating many *good* examples [Myers, private conversation]
			- test cases *TODO: how is this not an I/O example?
			- computation traces of a program for particular inputs *TODO: how is this not a more detailed I/O example?
		- congruent with many AI problems, which "elude a complete specification at all, e.g., face recognition" aka the knowledge-acquisition bottleneck [11]
	- Process:
		- construct a computer program or algorithm
	- Outputs
		- "a generalization of such an incomplete specification by identifying general patterns in the data" such as [11]
		-  a more complete specification or an actual implementation of [11]
			- function
			- module
			- other parts of a program
			- "actual, executable [synthesized] programs including recursion or loops" [11]
- Uses [11]
	- "generate candidate solutions subject to further inspection"
	- combine "with deductive methods to tackle a problem from the general description as well as from concrete (counter-)instances"
	- systematize occurring generalizations
	- check representativeness of example cases provided by the user *TODO: FIND OUT MORE
	- end-user programming
	- learning of recursive policies in intelligent agents

### Statistical

- Mathematical methods for drawing "conclusions in the presence of uncertainty" [6]
- A generalization of deterministic reasoning [6]

#### Probabilistic inductive logic programming / probabilistic logic learning / statistical relational learning 

"addresses one of the central questions of artificial intelligence: the integration of probabilistic reasoning with first order logic representations and machine learning" [8]

### Human

"how humans draw conclusions" [6]

#### Fields where primary and secondary research occur [6]
1. Primary: Studied in cognitive psychology
2. Secondary: Automated inference systems that *emulate* human inference are studied/composed in AI

#### Informal and Incorrect Logic (Fallacies)

Catalogued by: [6]
	- cognitive psychologists
	- philosophers
since humans have biases that favor certain types of fallacies

##### abductive

*"formally equivalent to the logical fallacy of affirming the consequent"* [7]

- "starts with an observation then seeks to find the simplest and most likely explanation" [7]
- "inference to the best explanation" [7]
- "the use of a known rule to explain an observation [but] can lead to false conclusions if other rules explaining the observation are not taken into account" [7]

###### Examples

1. Qualified success:

	- (Known rule) if it rains, the grass is wet
	- (Observation) the grass is wet
	- (Explanation by abduction) it has rained
	- (Failure mode 1: not taking other rules into account)
		- (Other rule) if the sprinklers were recently on, the grass is wet
		- (Alternative explanation) the sprinklers were recently on

2. Failure: affirming the consequent fallacy

	- (Known rule) if someone owns Fort Knox, then they are rich
	- (Observation) Bill Gates is rich
	- (Explanation by abduction) Bill Gates owns Fort Knox [clearly false]

###### Uses
- Employed frequently by diagnostic expert systems

## Machine Learning

### Category Learning

#### Classical view (philosophy)
"a process of abstraction, data compression, simplification, and summarization" [2]

#### Rules
- Most have been powered by heuristics, not statistics [2].

### Prototype
Assumptions [2]:
- "people abstract out the central tendency (or prototype) of the examples experienced and use this as a basis for their categorization decisions." 
- "people categorize based on one or more central examples of a given category followed by a penumbra of decreasingly typical examples."
	- "people do not categorize based on a list of things that all correspond to a definition, but rather on a hierarchical inventory based on semantic similarity to the central example(s)."

#### Prototypical networks

See "Prototypical Networks for Few-shot Learning" https://arxiv.org/pdf/1703.05175.pdf

### Exemplar
Assumptions [2]:
- people "store examples verbatim."

Exemplar models require two measures [2]:
- similarity between exemplars
- rules to determine group membership

### Explanation-based generalization

### Bayesian

### Induction (Inductive programming)

- "goes beyond classical machine learning in that the focus lies on learning general programs including loops and recursion, instead of merely (mostly nonrecursive) models or classifiers in restricted representational frameworks, such as decision trees or neural networks." [11]

## Grammar

- for human languages [3]: 
	- "The grammars of human languages produce hierarchical tree structures." 
	- "Some linguists argue that human languages are also capable of infinite recursion (see context-free grammar)."
		- *many indistinguishable possible grammars for producing a finite set of observations*: "For any given set of sentences generated by a hierarchical grammar capable of infinite recursion, there are an indefinite number of grammars that could have produced the same data."
			- In theory, the correct grammar is unlearnable
				- Proof by E. Mark Gold "showed that any formal language that has hierarchical structure capable of infinite recursion is unlearnable from positive evidence alone."
				- "it is impossible to formulate a procedure that will discover with certainty the correct grammar given any arbitrary sequence of positive data in which each utterance occurs at least once."
			- In practice, the correct grammar, or a good approximation, is learnable
				- Gold's proof "does not preclude arriving at the correct grammar using typical input sequences rather than particularly malicious sequences or arrive at an almost perfect approximation to the correct grammar."
				- Proposition: "under very mild assumptions (ergodicity and stationarity), the probability of producing a sequence that renders language learning impossible is in fact zero."
- for programming languages [4]:
	- Lets us transform a sequence of characters into a syntax tree, if the program is syntactically valid
		1. lexing/tokenizing sequence of characters into a sequence of tokens
		2. parsing the sequence of tokens into a tree

### Notation [4]

Most common form is Backus-Naur Form (BNF), which is defined by tuple of four elements: (T, N, P, S).
- T: a set of tokens, the vocabulary of the language, the smallest unit of syntax, e.g., *while*, *for*, +, (
- N: set of nonterminals, which are not part of the language, can be replaced with other nonterminals or tokens, depending on the production rules, enclosed in <> to distinguish them from terminals
- P: production rules, define what non-terminals can be turned into, e.g.
```
<exp> ::= <exp> "+" <exp> | <exp> "*" <exp> | "(" <exp> ")" | "a" | "b" | "c"
```
- S: start symbol, a special nonterminal from which all syntactically valid programs are produced from

Example grammar for all sums and products of names a, b, and c:
```
<exp> ::= <exp> "+" <exp>
<exp> ::= <exp> "*" <exp>
<exp> ::= "(" <exp> ")"
<exp> ::= "a"
<exp> ::= "b"
<exp> ::= "c"
```

### Context-free grammar

The predominant 'technology' for describing programming syntax; can describe more programming languages than the more limited regular grammars [4].

Context-free grammars "require no looking back or ahead, or backtracking, which allows a simple, clean, and efficient implementation." [4]

#### Lexical grammars [4]
Lexers (also called tokenizers) use lexical grammars to convert a sequence of characters into a sequence of tokens with identified meanings.

Relationship with parsers: "A lexer is generally combined with a parser, which together analyze the syntax of programming languages, web pages, and so forth."

Most rules of lexical grammars are context-free, with a few exceptions, e.g., "concatenation of consecutive string literals in Python, which requires holding one token in a buffer before emitting it (to see if the next token is another string literal)."

### Grammar induction

### Unsupervised parsing

## Version space

### Learning

### Algebra

## Poverty of the Stimulus

This is an argument for innate human knowledge of grammatical rules, since we learn correct grammar from what linguists & cognitive psychologists believe is a poverty of examples.

# References

1. http://www2.cs.uregina.ca/~dbd/cs831/notes/ml/2_inference.html
2. https://en.wikipedia.org/wiki/Concept_learning#Modern_psychological_theories
3. https://en.wikipedia.org/wiki/Poverty_of_the_stimulus
4. https://en.wikibooks.org/wiki/Introduction_to_Programming_Languages/Grammars
5. http://whatis.techtarget.com/definition/deductive-reasoning
6. https://en.wikipedia.org/wiki/Inference
7. https://en.wikipedia.org/wiki/Abductive_reasoning
8. https://people.csail.mit.edu/kersting/ecmlpkdd05_pilp/pilp.pdf
9. https://en.wikipedia.org/wiki/First-order_logic
10. http://www.cogsys.wiai.uni-bamberg.de/teaching/ss05/ml/slides/cogsysII-6.pdf
11. https://link.springer.com/chapter/10.1007/978-3-642-11931-6_3
12. https://en.wikipedia.org/wiki/Inductive_logic_programming
13. http://pldi16.sigplan.org/event/tutorials-prose-programming-using-examples

# Other Helpful Resources Uncited Above

#### Unsupervised Parsing and Grammar Induction
https://nlp.stanford.edu/projects/up-gi.shtml

# Removed sections

## Inference

### Logical


