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

Validity across different reasoning methods
- "An inference is deductively valid if and only if there is no possible situation in which all the premises are true but the conclusion false." [15]
- "An inference is inductively strong if and only if its premises give some degree of probability to its conclusion." [15]

#### Types [22]

- Formal logic: inference with purely formal content, i.e., expressed as a particular application of a wholly abstract rule that is not about any particular thing or property 
- Symbolic logic: symbolic abstractions that capture formal logic
	- propositional logic
	- predicate/first-order logic (extension of propositional logic) [23]
		- unlike propositional logic, uses quantifiers or relations, e.g., "there exists"
		- cannot describe structures with an infinite domain, e.g., natural numbers or the real line, which requires second-order logic
	- second-order logic (extension of first order logic) [24]
		- quantifies over relations
- Mathematical logic: extenstion of symbolic logic for mathematical domain
	- Boolean algebra
		- variables are true or false
		- 'and' is conjunction
		- 'or' is disjunction
		- common forms
			- general boolean formulas (more concise, perhaps more interpretable [25])
			- disjunctive normal form (sum of products)


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
- "generalize a rule from a number of similar observations" [14]
- intrinsically unsound [11]
	- adds to but does not replace deductive methods [11]
- "Inference from particular premises to [a] universal conclusion" [6]
- "Process by which a conclusion is inferred from multiple observations" [6]
- "philosophical (i.e. suggesting a theory to explain observed facts)" not "mathematical (i.e. proving a property for all members of a well-ordered set)"

Connection to ML:
- "in general, machine learning involves building theories that explain the observed data" [10]

##### Example [14]
1. (number of similar observations) see dark clouds produce rain many times
2. (new observation) see dark clouds
3. (hypothesis) it will rain

##### Learning from Examples

- Examples can be all positive, or a mixture of positive and negative. Negative examples constrain the set of models that are consistent with the examples [1].
- "if the data at hand is representative then it is likely that identified patterns actually hold in the general case and that, indeed, the induced result meets the general problem" [11]

##### Inductive bias
"Explicit or implicit assumption(s) about what kind of model is wanted." [1]

##### Inductive Learning Hypothesis

- hypothesis types
	- functions
        - "approximate the target function well over a sufficiently large set of training examples will also approximate the target function well over other unobserved examples." [1]
    - logic programs or concepts (?)
    	- a definite clause program [8]
    	- "a suitable concept in a description space where descriptions are related via generalization/specialization relationships. Examples are at the 'bottom' of the generalization hierarchy." [14]
    	- "Given some data D and some background knowledge B, learning can be described as generating a hypothesis h that, together with B, explains D." [10]
    	- Coverage of examples
	        - "the hypothesis H together with the background theory B should cover all positive and none of the negative examples" [8]
	        - a suitable concept "covers (generalizes) all positive and none of the negative examples" [14]
		- [logic] concepts			

##### Hypothesis Correctness

Conclusions of inductive reasoning process are hypotheses. There are two main types of hypotheses:
1. a conclusion that results in a boolean value, can be tested on additional observations
	- may or may not be true
	- true ~X% of the time
	- may only be true when certain preconditions are met
2. a model: 
	- Examples are generalized into a model that is then used to make predictions on new, previously unseen inputs. 
	- Learned models may or may not capture what the human in the loop wanted. - Models could be:
		- a category
		- a pattern, like the patterns PROSE learns to extract data from large files
		- a transformation or program, like the transformations Rafazer learns over ASTs

Hypotheses are unprovable without additional stuff [11]
- "the most severe objection against IP" [11]
	- "What is the use of methods whose results cannot be proven correct and possibly deviate from what was intended?" [11]
	- One answer: "all software development necessarily makes a transition from a first informal and often incomplete problem description by the
user or customer to a complete and ideally formal specification." [11] This transistion is: [11]
		-  incapable of formal proof
		- possibly based on—non-systematic inexplicit generalization
	- "There is no reason why systematically incorporating existing or easily formulated data by inductive methods should not improve efficiency and even validity of software development" [11]

##### Hypothesis testing & Reducing uncertainty

Testing strategies:
- positive testing strategy (PTS)
- negative testing strategy (NTS)

"PTS is more likely to yield falsification and optimally reduces uncertainty provided the world is inherently deterministic (i.e., given the rule is true, there is only one possible next outcome)." [19]

##### Inductive programming (IP)
- "emerging field" [11]
- reasoning methods & theory for [11]
	- computer programming
	- algorithm design
	- software development

###### Inductive Logic Programming
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

###### Inductive program synthesis (IPS)
- "major subfield" of IP started in the 70's [11]
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
			- (typical specification type) input/output examples (I/O-examples) of a function or a module interface
				- referred to as *Programming By Examples (PBE)* or *Programming By Demonstration (PBD)*
				- variables in I/O examples may be allowed
				- more tractable than [general] program synthesis because [13] 
					- "[automated?] reasoning about concrete input states is much easier than dealing with properties over symbolic program states"
					[13]
					- humans--programmers and non-programmers alike--have an easier time generating examples than logical/relational/complete specifications [13]
						- but they may not be good at generating many *good* examples [Myers, private conversation]
						- a great opportunity for HCI to empower the 99% of the billions of users of computational devices who don't know how to program them and struggle with repetitive tasks that could be automated with small scripts [13]
				- requires [13]
					- designing a DSL for the application domain
					- building a synthesis algorithm for it
					- disambiguating among learned programs using ranking or user interaction
			- test cases *TODO: how is this not an I/O example?
			- computation traces of a program for particular inputs *TODO: how is this not a more detailed I/O example?
		- congruent with many AI problems, which "elude a complete specification at all, e.g., face recognition" aka the knowledge-acquisition bottleneck [11]
	- Process:
		- construct a computer program or algorithm out of function primitives [11]
			- Primitives may be [11]
				- fixed, predefined functions known to the IPS system
				- dynamically given as an extra, problem-specific, input
					- aka 'background knowledge' *TODO: WEIRD NAME. WHY?
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

#### Transductive

- reasoning from observed, specific (training) cases to specific (test) cases [17]
	- not reasoning from observed training cases to general rules, which are then applied to the test cases [17]

### Statistical

- Mathematical methods for drawing "conclusions in the presence of uncertainty" [6]
- A generalization of deterministic reasoning [6]

#### Probabilistic Modeling

- Models describe data that could be observed from a system [28]

Strengths: [28]
- Knows when it doesn't know
- "automatic model complexity control and structure learning (Bayesian Occam's Razor)"


- inverse probability rule (Bayes Rule):
	- P(hypothesis | data) = [ P(hypothesis)*P(data|hypothesis) ] / [ Sum of P(hypothesis)*P(data|hypothesis) for all hypotheses ]
	- dictates inferences, specifically inferences about "hypotheses (uncertain quantities) from data (measured quantities)" [28]
		- about hypotheses (which hypothesis is more likely, given the data)
		- how to update the model itself, where the model parameters are the hypothesis
			- P(model parameters | data, model) = [ P(data | model parameters, model) * P(model parameters | model) ] / P(data | model)
		- make predictions
			- P(x|data, model) = Sum of P(x|data, model, model parameters)*P(model paramters|data, model) for all model parameters
			- question: how do you get all those terms?
		- learn from data
			- P(model | data) = P(data | model)P(model) / P(data)
			- Question: what if you don't know P(data)? How do people reasonably approximate that?

#### Probabilistic Programming

- aims to "export" powerful PL concepts like abstraction and reuse to statistical modeling [16]

##### Probabilistic inductive logic programming / probabilistic logic learning / statistical relational learning 

"addresses one of the central questions of artificial intelligence: the integration of probabilistic reasoning with first order logic representations and machine learning" [8]

### Human

TODO: See Brenden Lake's work

"how humans draw conclusions" [6]

#### Fields where primary and secondary research occur [6]
1. Primary: Studied in cognitive psychology
2. Secondary: Automated inference systems that *emulate* human inference are studied/composed in AI

#### Things humans learn

- attributes (features)
- grammars (rules for parsing input)
- categories
- programs
	- concepts: defined by [27] as "simple probabilistic programs", i.e., "probabilistic generative models epxressed as structured procedures in an abstract description language"

#### Feature learning

"Experts identify parts of objects in their domain of expertise vastly differently than novices (e.g., [3]), and evidence for flexible feature sets has been found in many laboratory experiments (see [2] for a review)." [20]

#### Concept learning

- "How do people learn new concepts from just one or a few examples?" [27]
- "How do people learn such abstract, rich, and flexible representations?" [27]

"For any theory of learning [27's 4, 27's 14–16], fitting a more complicated model requires more data, not less, in order to achieve some measure of good generalization... Nonetheless, people seem to navigate this trade-off with remarkable agility, learning rich concepts that generalize well from sparse data." [27]

"People learning new concepts can often generalize successfully from just a single example" [27]

1. "people may only need to see one example of a novel two-wheeled vehicle in order to grasp the boundaries of the new concept" [27]
2. "people learn richer representations than machines... even for simple concepts" which are used by people to [27]
	- create new exemplars [27's 10]
	- parse objects into parts and relations
	- create new abstract categories of objects based on existing categories [27's 12, 27's 13]

todo: keep reading [27]

#### Learning of similarity functions and rules

"abstracting rules and computing similarity to exemplars ... should both be seen as special cases of a more general Bayesian learning framework" [29]

"In domains ranging from reasoning to language acquisition, a broad view is emerging of
cognition as a hybrid of two distinct modes of computation, one based on applying abstract
rules and the other based on assessing similarity to stored exemplars [7]." [29]

##### Bayesian program [concept] learning (BPL)

"capable of learning a large class of visual concepts from just a single example and generalizing in ways that are mostly indistinguishable from people"

#### Order matters

"It is a common finding that the order in which people receive information has an effect on their subsequent judgments and inferences (Dennis & Ahn, 2001;
Collins & Shanks, 2002). This poses a problem for rational models based on Bayesian inference as the process of updating hypotheses in these models is typically invariant to the order in which the data are presented." [18]

##### primacy effects

"initial observations have an overly strong influence on people’s conclusions" [18]

##### recency effects

"being more influenced by more recent observations" [18]

#### Known Characteristics

##### Testing hypotheses

Using PTS to test hypotheses is optimal if "the world is deterministic" and humans use PTS "as the result of an assumption of determinism on the part of human learners, consistent with recent results showing that children assume that many causal relationships are deterministic (e.g., Schulz & Sommerville, 2006; Gelman, Coley, & Gottfried, 1994)" [19].

###### Confirmation Bias

Defined as "the general human tendency to interpret and seek evidence fitting their current theory differently from evidence against it (Klayman & Ha, 1987)." [19]

"Classic analyses of hypothesis testing assume that people should pick the test with the largest probability of falsifying their current hypothesis, while experiments have shown that people tend to select tests consistent with that hypothesis." [19]

##### Informal and Incorrect Logic (Fallacies)

TODO: FINISH READING BAD ARGUMENTS

Catalogued by: [6]
	- cognitive psychologists
	- philosophers
since humans have biases that favor certain types of fallacies

###### abductive

*"formally equivalent to the logical fallacy of affirming the consequent"* [7]

- "starts with an observation then seeks to find the simplest and most likely explanation" [7]
- "inference to the best explanation" [7]
- "the use of a known rule to explain an observation [but] can lead to false conclusions if other rules explaining the observation are not taken into account" [7]
- "choose between several explanations that explain an observation" [14]

*Examples*
1. Qualified succes
	- Example 1:
		- (Known rule) if it rains, the grass is wet
		- (Observation) the grass is wet
		- (Explanation by abduction) it has rained
		- (Failure mode 1: not taking other rules into account)
			- (Other rule) if the sprinklers were recently on, the grass is wet
			- (Alternative explanation) the sprinklers were recently on
	- Example 2:
		- (Known rule 1) a broken bulb won't turn on [common]
		- (Known rule 2) a bulb in a socket that is not receiving any electricity will not turn on [uncommon]
	    - (Observation) “I flipped the switch, but the light doesn’t turn on."
	    - (Explanation by abduction) "The bulb must be broken." [the more likely of the two explanations]

2. Failure: affirming the consequent fallacy

	- (Known rule) if someone owns Fort Knox, then they are rich
	- (Observation) Bill Gates is rich
	- (Explanation by abduction) Bill Gates owns Fort Knox [clearly false]

*Uses*
- Employed frequently by diagnostic expert systems

## Machine Learning

### Feature learning

#### Representation is nearly everything
- "Almost all successful machine learning algorithms and cognitive models require powerful representations capturing the features that are relevant to a particular problem." [20]
- "forming an appropriate representation is a fundamental issue for applying machine learning algorithms." [20]
    - "early work demonstrating XOR is only learnable by a linear classifier with the right representation [4]"
    - the kernel trick in support vector machines [20's 5]

#### Fixed features

"Most accounts of the processes underlying human learning, decision-making, and perception assume that stimuli have fixed sets of features. For example, traditional accounts of category learning start with a set of features (e.g., is furry and barks), which are used to learn categories (e.g., dogs). In a sense, features are the basic atoms for these processes." [20]

#### Non-fixed features

Can "use distributional and category information to infer feature representations" [20]

##### nonparametric Bayesian statistics

Assumes "that the observed data manifest a subset of an unbounded amount of latent structure" [21]

##### Indian Buffett Process

"objects are represented using an unknown number of latent features" [21]

"The Indian buffet process can also be used to define a prior distribution in any setting where the latent structure expressed in data can be expressed in the form of a binary matrix with a finite number of rows and infinite number of columns, such as the adjacency matrix of a bipartite graph where one class of nodes is of unknown size, or the adjacency matrix for a Markov process with an unbounded set of states." [21]
- Research question: can this representation represent code?

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

#### Exemplar
Assumptions [2]:
- people "store examples verbatim."

Exemplar models require two measures [2]:
- similarity between exemplars
- rules to determine group membership

### Explanation-based generalization

### Bayesian

#### Monte Carlo methods
"The basic principle underlying Monte Carlo methods is to approximate a probability distribution using only a finite set of samples from that distribution." [18]

##### Importance Sampling

##### Particle Filtering

### Program Induction

"goes beyond classical machine learning in that the focus lies on learning general programs including loops and recursion, instead of merely (mostly nonrecursive) models or classifiers in restricted representational frameworks, such as decision trees or neural networks." [11]

Approaches [26]
- Connectionist
	- Neural Turing Machine
- Symbolic
	- Hierarchical Bayesian Program Learning
		- Lake et al.'s Science paper
		- Percy Liang's Learning Programs [30]
			- 

## Grammars

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

From [31]:
A context-free grammar (CFG) is a 4-tuple G = (N, Σ, R, S) where:

• N is a finite set of non-terminal symbols.
	- In English, N specifies basic syntactic categories: for example NP for “noun phrase”, VP for “verb phrase”, and includes the start symbol S which stands for “sentence” 
• Σ is a finite set of terminal symbols.
	- The set Σ contains the set of words in the vocabulary.
• R is a finite set of rules of the form X → Y1Y2 . . . Yn, where X ∈ N, n ≥ 0,
and Yi ∈ (N ∪ Σ) for i = 1 . . . n.
	- In English, these might be
		- S → NP VP
		- NN → man
	- There are unary rules
		- NN → man
		- S → VP
	- There are rules with mixtures of terminals and non-terminals: 
		- VP → John Vt Mary
		- NP → the NN
	- Rules that end in terminals, like the empty string
		- VP → e
• S ∈ N is a distinguished start symbol.
	- In English, this would be a sentence. Every parse tree has S as its root.

#### Probabilistic

"a natural generalization of context-free grammars" [31]

"The key idea in probabilistic context-free grammars is to extend our definition
to give a probability distribution over possible derivations." [31]

From [31]:
Given a context-free grammar G, we will use the following definitions:
• TG is the set of all possible left-most derivations (parse trees) under the grammar
G.
• For any derivation t ∈ TG, yield(t) is the sequence of words in t: s ∈ Σ∗
• For a given sentence s ∈ Σ∗, TG(s) is the set of possible parse trees for s. Mathematically, TG(s) is {t : t ∈ TG, yield(t) = s}
• We say that a sentence s is ambiguous if it has more than one parse tree, i.e.,
|TG(s)| > 1.
• We say that a sentence s is grammatical if it has at least one parse tree, i.e.,
|TG(s)| > 0.

#### Lexical grammars [4]
Lexers (also called tokenizers) use lexical grammars to convert a sequence of characters into a sequence of tokens with identified meanings.

Relationship with parsers: "A lexer is generally combined with a parser, which together analyze the syntax of programming languages, web pages, and so forth."

Most rules of lexical grammars are context-free, with a few exceptions, e.g., "concatenation of consecutive string literals in Python, which requires holding one token in a buffer before emitting it (to see if the next token is another string literal)."

[31]: "We will find a way to define a distribution over parse trees, p(t), such that for any t ∈ TG:"
• p(t) ≥ 0 such that 
• the p(t) of all t in TG sum to 1

That means the probability of each branch in a set of branches from a common root must sum to 1.

##### Learning PCFG from corpuses [31]

training data: a set of parse trees t1, t2, . . . , tm. The induced PCFG (N, Σ, S, R, q) is:
• N: the set of all non-terminals seen in the trees t1-tm.
• Σ: the set of all words seen in the trees t1-tm.
• S: the same root that all trees t1-tm share.
• R: the set of all rules α → β seen in the trees t1-tm.
• The maximum-likelihood parameter estimates are:
qML(α → β) = Count(α → β) / Count(α)
where Count(α → β) is the number of times that the rule α → β is seen in the trees t1-tm, and Count(α) is the number of times the non-terminal α is seen in the trees t1-tm. For example:
	- if the rule VP → Vt NP is seen 105 times in our corpus and
	- the non-terminal VP is seen 1000 times, then
	- q(VP → Vt NP) = 105 / 1000

##### Limits

Does not capture the fact that choices in one branch could affect the probability of choices in another branch

### Grammar induction

#### Recent HCI-relevant papers
1. "Learning Design Patterns with Bayesian Grammar Induction" @ UIST '12 http://graphics.stanford.edu/~lfyg/gi.pdf

### Unsupervised parsing

## Version space

### Learning

### Algebra

## Poverty of the Stimulus

This is an argument for innate human knowledge of grammatical rules, since we learn correct grammar from what linguists & cognitive psychologists believe is a poverty of examples.

## Domain-specific languages

## Human-machine communication

TODO: add Been's work on using examples as a medium
TODO: add edupsych work on inducing good mental models by choosing strategically diverse examples as a medium

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
14. http://ai.vub.ac.be/~ydehauwe/decl_prog/7_InductiveLogicProgramming.pdf
15. https://en.wikipedia.org/wiki/Logic_and_rationality
16. https://www.cs.cornell.edu/courses/cs4110/2016fa/lectures/lecture33.html
17. https://en.wikipedia.org/wiki/Transduction_(machine_learning)
18. https://escholarship.org/uc/item/3k26g6wn#page-1 : Exploring the influence of particle filter parameters on order effects in causal learning
19. https://escholarship.org/uc/item/6n60k9zn : A Rational Analysis of Confirmation with Deterministic Hypotheses
20. http://papers.nips.cc/paper/3621-analyzing-human-feature-learning-as-nonparametric-bayesian-inference.pdf
21. https://cocosci.berkeley.edu/tom/papers/indianbuffet.pdf : The Indian Buffet Process: An Introduction and Review
22. https://en.wikipedia.org/wiki/Logic
23. https://en.wikipedia.org/wiki/First-order_logic
24. https://en.wikipedia.org/wiki/Second-order_logic
25. http://da.qcri.org/jquiane/jorgequianeFiles/papers/sigmod17c.pdf : Generating Concise Entity Matching Rules
26. http://papers.nips.cc/paper/6082-sampling-for-bayesian-program-learning.pdf
27. https://www.cs.cmu.edu/~rsalakhu/papers/LakeEtAl2015Science.pdf
28. http://www.nasonline.org/programs/sackler-forum/frontiers-of-machine-learning/ghahramani-ppt.pdf 
29. http://papers.nips.cc/paper/1666-rules-and-similarity-in-concept-learning.pdf
30. https://cs.stanford.edu/~pliang/papers/programs-icml2010.pdf
31. http://www.cs.columbia.edu/~mcollins/courses/nlp2011/notes/pcfgs.pdf : Probabilistic Context-Free Grammars (PCFGs) by Michael Collins

# Other Helpful Resources Uncited Above

#### Unsupervised Parsing and Grammar Induction
https://nlp.stanford.edu/projects/up-gi.shtml

# Removed sections

## Inference

### Logical


