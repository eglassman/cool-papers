# Definitions

## Inference

Can refer to: [6]
1. the conclusion reached from evidence and reasoning
2. the process of reaching that conclusion

### Logical

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

#### Inductive


- "induction is just the inverse of deduction" [10]
- "Bottom-up logic" [5]
- "The process of reaching a general conclusion from specific examples." [1]
- "Inference from particular premises to [a] universal conclusion" [6]
- "Process by which a conclusion is inferred from multiple observations" [6]

Connection to ML:
- "in general, machine learning involves building theories that explain the observed data" [10]

##### Learning from Examples

Examples can be all positive, or a mixture of positive and negative. Negative examples constrain the set of models that are consistent with the examples [1].

##### Inductive bias
"Explicit or implicit assumption(s) about what kind of model is wanted." [1]

###### Inductive Learning Hypothesis
- "Any hypothesis found to approximate the target function well over a sufficiently large set of training examples will also approximate the target function well over other unobserved examples." [1]
- "Given some data D and some background knowledge B, learning can be described as generating a hypothesis h that, together with B, explains D." [10]
- "a logic program, i.e. a definite clause program" [8]

##### Results Correctness

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

###### Inductive Logic Programming
- "designed to learn first-order rules" [10]
- "concerned with finding a hypothesis H from a set of positive and negative examples P and N" [8]


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

### Human

"how humans draw conclusions" [6]

#### Fields where primary and secondary research occur [6]
1. Primary: Studied in cognitive psychology
2. Secondary: Automated inference systems that *emulate* human inference are studied/composed in AI

### Statistical

- Mathematical methods for drawing "conclusions in the presence of uncertainty" [6]
- A generalization of deterministic reasoning [6]

#### Probabilistic inductive logic programming / probabilistic logic learning / statistical relational learning 

"addresses one of the central questions of artificial intelligence: the integration of probabilistic reasoning with first order logic representations and machine learning" [8]

## Concept Learning

Concepts can be categories, labels (e.g., PROSE extractions), or procedures (e.g., PROSE transformations).

### Classical view (philosophy)
"a process of abstraction, data compression, simplification, and summarization" [2]

### Rule-based
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

# Other Helpful Resources Uncited Above

#### Unsupervised Parsing and Grammar Induction
https://nlp.stanford.edu/projects/up-gi.shtml

# Removed sections

## Inference

### Logical


