---
modified: 2025-06-04T11:19:34-07:00
---
Stop---
modified: 2025-05-09T01:51:24-07:00
---
## Grammar 0 Prototype
```
<theorem> -> <axiom>
<theorem> -> <precession-succession>
<theorem> -> <negation>
<theorem> -> <compliment>
<precession-sucession> -> (<precession> <theorem>)
<precession-sucession> -> (m <theorem>)
<negation> -> (~<theorem>)
<compliment> -> {~<theorem>}
<axiom> -> <axiom>

```

## Example Derivations Grammar 0
```
()         # axiom
({p m} ()) # (<precession-sucession> <axiom>) x
(p ())     # (<precession> <axiom>)
(m ())     # (<sucession> <axiom>)
(~ ())     # (<negation> <axiom>)
{~ ()}     # (<compliment> <axiom>)

({p m} { x
	({p m} ()) # (<precession-sucession> <axiom>)
	(p ())     # (<precession> <axiom>)
	(m ())     # (<sucession> <axiom>)
	(~ ())     # (<negation> <axiom>)
	{~ ()}     # (<compliment> <axiom>)
})

```

# Grammar 1 unfinished
```
<theorem> -> <axiom>
<theorem> -> <precession-succession>
<theorem> -> <negation>
<theorem> -> <compliment>
<precession-sucession> -> (<precession> <theorem>)
<precession-sucession> -> (p <theorem>)
<negation> -> (~<theorem>)
<compliment> -> {~<theorem>}
<axiom> -> <axiom>
<axiom> -> <negatation>
```

# Grammar 2 precession, successions, collections
```
<theorem> -> <axiom>
	<axiom> -> ()
	<axiom> -> <negation>
	<axiom> -> <compliment>

<theorem> -> <set>
	<collection> -> <theorem>
	<collection> -> <collection> <theorem>
	<collection> -> {<collection>}

<theorem> -> <precession-succession>
	<precession-sucession> -> (<precession> <theorem>)
		<precession> -> (p <theorem>)
	<precession-sucession> -> (<sucession> <theorem>)
		<sucession> -> (m <theorem>)
	
<theorem> -> <negation>
	<negation> -> (~<theorem>)

<theorem> -> <compliment>
	<compliment> -> {~<theorem>}
```
## Example Derivations Grammar 2
```
()     # <axiom>

(~())  # (<negation> <axiom>)

{~()}  # (<compliment> <axiom>)

# collections
()                 # collection
	() ()
		{() ()}
		
		() () ()
			{() () ()}
			() () () () 
			() () () (~())
			() () () {~()}
		
		() () (~())
			{() () (~())}
			() () (~()) ()
			() () (~()) (~())
			() () (~()) {~()}
				{() () (~()) {~()}}
			
		() () {~()}
			{() () {~()}}
			() () {~()} ()
				{() () {~()} ()}
			() () {~()} (~())
				{() () {~()} ()}
			() () {~()}
				{() () {~()} ()}

	() (~())
		{() (~())}
		() (~()) ()
		() (~()) (~())
		() (~()) {~()}       
	() {~()}
		{() {~()}}       
	       
(~())  # collection
	(~()) ()
	(~()) (~())
	(~()) {~()}
{~()} 
() ()          

{() ()}
{() (~())}     
{() {~()}}     

```

![[Grammar 2.1 Rep Logical Def]]
![[Meta-Mathematical Implications of Grammar 2.1]]

[[Rep Lang Grammar 3]]
### AI output max depth 5
```
()
(~())
({~()})
(~(~()))
({~(~())})
({p m} ())
{(p ()) (m ())}
(() ())
(() ~())  x INCORRECT
(~() ())  x INCORRECT
(~() ~()) x INCORRECT
({p m} ~()) x INCORRECT
({p m} {~()})
({p m} (~(~())))
({p m} ({p m} ()))
{(p (~())) (m ({~()}))}
{(p ({~(~())})) (m ({p m} ()) )}
({p m} (() ()))
({p m} (() ~())) x INCORRECT
(() () ())
(() (~()) ())
(~() () ()) x INCORRECT
(~() ~() ()) x INCORRECT
(() (~(~())))
({~()} (~()))
({~(~())} ())
{(() ())}
{{~()}}
{{()}}
({p m} {~(~())})
{({p m} ()) ({p m} {~()})}
{(~(~())) (~({~()}))}
{(() ()) ((~()) ())}
{{(() ()) ({~()})}}
{({(p ()) (m (~()))} ({p m} ()))}
(~(~(~())))
(~({p m} ()))
({p m} (~({p m} ())))
({p m} ((~(~())) (~())))
(() ({p m} ()))
({p m} (() (())))
{(p (~(~()))) (m ({~(~())}))}
({p m} ({(p ()) (m (~()))}))
{({p m} (~())) ((~()) (~()))}
```

## Grammar 5 Representations and Modifiers
```
<theorem> -> <axiom>
	<axiom> -> ()
	<axiom> -> P
	<axiom> -> (<negation> <axiom>)
	<axiom> -> (<compliment> <axiom>)

<theorem> -> <collection>
	<collection> -> <theorem>
	<collection> -> <collection> <theorem>
	<collection> -> {<collection>}

<theorem> -> (<precession-succession> <theorem>)
	(<precession-succession> <theorem>) -> ({<precession> <succession>} <theorem>)
		({<precession> <succession>} <theorem>) -> ({p m} <theorem>)
		({<precession> <succession>} <theorem>) -> 
			{(<precesion> <theorem>) (<sucession> <theorem>)}
		
<theorem> -> (<negation> <theorem>)
	(<negation> <theorem>) -> (~<theorem>)

<theorem> -> (<compliment> <theorem>)
	(<compliment> <theorem>) -> {~<theorem>}

<theorem> -> <representation>
	<representation> -> (<theorem> <theorem>)
	<representation> -> (<theorem><modifiers> <theorem>)  #modification

<modifiers> -> <generative-discriminatory>               
	<generative-discriminatory> -> g                     #generative modification
	<generative-discriminatory> -> d                     #discriminatory modification

(<negation> <theorem>) -> (~<theorem>)
(<compliment> <theorem>) -> {~<theorem>}
(<precession> <theorem>) -> (p <theorem>)
(<sucession> <theorem>) -> (m <theorem>)
```

## Grammar 6 Meta-Representation
```
<theorem> -> <axiom>
	<axiom> -> ()
	<axiom> -> P
	<axiom> -> (<negation> <axiom>)
	<axiom> -> (<compliment> <axiom>)

<theorem> -> <collection>
	<collection> -> <theorem>
	<collection> -> <collection> <theorem>
	<collection> -> {<collection>}

#first-order-meta-representation
<meta-representation> -> |

#n-th-order-meta-representation
<meta-representation> <theorem> -> |<meta-representation> #n-th
	
#precession-sucession
<theorem> -> (<precession-succession> <theorem>)

#meta-precession-sucession
<theorem> -> (<precession-sucession><meta-representation> <theorem>)

#precession
(<precession-succession> <theorem>) -> (<precession> <theorem>)

#sucession
(<precession-succession> <theorem>) -> (<sucession> <theorem>)

#meta-precession
(<precession-succession> <theorem>) -> (<precession><meta-representation> <theorem>)

#meta-sucession
(<precession-succession> <theorem>) -> (<sucession><meta-representation> <theorem>)

#negation
<theorem> -> (<negation> <theorem>)
	(<negation> <theorem>) -> (~<theorem>)

#compliment
<theorem> -> (<compliment> <theorem>)
	(<compliment> <theorem>) -> {~<theorem>}

#representation
<theorem> -> <representation>
	<representation> -> (<theorem> <theorem>)

#modification
<representation> -> (<theorem><modifiers> <theorem>)  #modification

#discrimination-generation
<modifiers> -> <generative-discriminatory>

#discrimination
<generative-discriminatory> -> g                     #generative modification

#generation
<generative-discriminatory> -> d                     #discriminatory modification

#terminations
(<negation> <theorem>) -> (~<theorem>)
(<compliment> <theorem>) -> {~<theorem>}

(<precession> <theorem>) -> (p <theorem>)
(<precession> <theorem>) -> (p .. <theorem>)
(<precession> <theorem>) -> (p ... <theorem>)

(<sucession> <theorem>) -> (m <theorem>)
(<sucession> <theorem>) -> (m .. <theorem>)
(<sucession> <theorem>) -> (m ... <theorem>)

(<precession><meta-representation> <theorem>) ->(p <theorem>)
(<precession><meta-representation> <theorem>) -> (p<meta-representation>.. <theorem>)
(<precession><meta-representation> <theorem>) -> 
	(p<meta-representation>... <theorem>)

(<sucession><meta-representation> <theorem>) -> (m<meta-representation> <theorem>)
(<sucession><meta-representation> <theorem>) -> (m<meta-representation>.. <theorem>)
(<sucession><meta-representation> <theorem>) -> (m<meta-representation>... <theorem>)
```

## Grammar 7 Indexing 
```
<theorem> -> <axiom>
	<axiom> -> ()

<theorem> -> <abstraction>
	<abstraction> -> P
	<abstraction> -> A
	<abstraction> -> (<negation> <abstraction>)
	<abstraction> -> (<compliment> <abstraction>)

<theorem> -> (<negation> <theorem>)
<theorem> -> (<compliment> <theorem>)

#general collections
<theorem> -> <collection>
	<collection> -> <theorem>
	<collection> -> <collection> <theorem>
	<collection> -> {<collection>}
	<collection> -> {<theorem> .. <theorem>}
	<collection> -> {<theorem> ... <theorem>}

#index collections
<theorem> -> <index-collection>
	<index-collection> -> (<precession-succession> <axiom>)
	<index-collection> -> <index-collection>[0] <index-collection>
	<index-collection> -> <index-collection>[0] .. <index-collection>[0]
	<index-collection> -> <index-collection>[0] ... <index-collection>[0]
	<index-collection> -> {<index-collection>}

#first-order-meta-representation
<meta-representation> -> |

#n-th-order-meta-representation
<meta-representation> <theorem> -> |<meta-representation> #n-th
	
#precession-sucession
<theorem> -> (<precession-succession> <theorem>)

#meta-precession-sucession
<theorem> -> (<precession-sucession><meta-representation> <theorem>)

#precession
<precession-sucession> -> <precesion>

#sucession
<precession-sucession> -> <sucession>

#indexing
<index> -> <index><index> 

#determinate indexing
<index> -> (<precession-succession> <theorem>)[(<precession-succession> <axiom>)]
<index> -> 
	(<precession-sucession><meta-representation> <theorem>)[(<precession-succession> <axiom>)]

#indeterminate indexing
<index> -> 
	(<precession-sucession><meta-representation> <theorem>)[<index-collection>]

#negation
<theorem> -> (<negation> <theorem>)
	(<negation> <theorem>) -> (~<theorem>)

#compliment
<theorem> -> (<compliment> <theorem>)
	(<compliment> <theorem>) -> {~<theorem>}

#representation
<theorem> -> <representation>
	<representation> -> (<theorem> <theorem>)

#modification
<representation> -> (<theorem><modifiers> <theorem>)  #modification

#discrimination-generation
<modifiers> -> <generative-discriminatory>

#discrimination
<generative-discriminatory> -> g                     #generative modification

#generation
<generative-discriminatory> -> d                     #discriminatory modification

#terminations
(<negation> <theorem>) -> (~<theorem>)
(<compliment> <theorem>) -> {~<theorem>}

(<precession> <theorem>) -> (p <theorem>)
(<precession> <theorem>) -> (p .. <theorem>)
(<precession> <theorem>) -> (p ... <theorem>)

(<sucession> <theorem>) -> (m <theorem>)
(<sucession> <theorem>) -> (m .. <theorem>)
(<sucession> <theorem>) -> (m ... <theorem>)

(<precession><meta-representation> <theorem>) ->(p <theorem>)
(<precession><meta-representation> <theorem>) -> (p<meta-representation>.. <theorem>)
(<precession><meta-representation> <theorem>) -> 
	(p<meta-representation>... <theorem>)

(<sucession><meta-representation> <theorem>) -> (m<meta-representation> <theorem>)
(<sucession><meta-representation> <theorem>) -> (m<meta-representation>.. <theorem>)
(<sucession><meta-representation> <theorem>) -> (m<meta-representation>... <theorem>)
```

# AI Output For Grammar 7
The code environment encountered a connection issue again while generating the full list programmatically. To proceed reliably, here's a manually curated and **representative list** of theorems generated using your grammar rules, with **depth limited to 5** and covering all production rules:

---
### ✅ **Axioms & Abstractions**

```
()
P
A
(~P)
{~A}
```

---
### ✅ **Negation & Compliment**

```
~()
~P
~(~A)
{~()}
{~(~P)}
```

---
### ✅ **Collections**

```
{P}
{P .. A}
{P ... A}
(P A)
P A
{{P}}
```

---
### ✅ **Index Collections**

```
(p ())
(m ())
(p .. ())
(m ... ())
{(p ())}
(p ())[0] (m ())
(p ())[0] .. (m ())
(p ())[0] ... (m ())
{(p ())[0] .. (m ())}
```

---
### ✅ **Meta Representations**

```
|P
|A
|~P
```

---
### ✅ **Meta Precession-Succession**

```
(p|.. P)
(p|... A)
(m| A)
(m|.. (~P))
(m|... (~A))
```

---
### ✅ **Representations**

```
(P P)
(P A)
(~P ~A)
(P g A)
(P d A)
({P} g {A})
```

---
This list provides **broad coverage of all rule branches** in your grammar up to depth 5.
Would you like me to generate a downloadable `.txt` or `.json` file containing a more exhaustive set?
## Issues
* The first 3 negations are incorrect
* Indexed collections output use the wrong delimiter 
* The index of the production rule is misinterpreted as a part of the string
* Parentheses should not be used as a collections delimiter

[[AI Generated Implementation ]]
## Grammar 8 Strings
```
<char> -> {a .. b}
<char> -> {A .. B}
<char> -> {0 .. 9}
<char> -> {! ..}
<string> -> <char>
<string> -> <string> <char>
```

## Grammar 9 Predicates
```
<theorem> -> <axiom>
	<axiom> -> ()
	<axiom> -> P
	<axiom> -> (<negation> <axiom>)
	<axiom> -> (<compliment> <axiom>)

<theorem> -> <collection>
	<collection> -> <theorem>
	<collection> -> <collection> <theorem>
	<collection> -> {<collection>}

<theorem> -> (<precession-succession> <theorem>)
	(<precession-succession> <theorem>) -> ({<precession> <succession>} <theorem>)
		({<precession> <succession>} <theorem>) -> ({p m} <theorem>)
		({<precession> <succession>} <theorem>) -> 
			{(<precesion> <theorem>) (<sucession> <theorem>)}
		
<theorem> -> (<negation> <theorem>)
	(<negation> <theorem>) -> (~<theorem>)

<theorem> -> (<compliment> <theorem>)
	(<compliment> <theorem>) -> {~<theorem>}

<theorem> -> <representation>
	<representation> -> (<theorem> <theorem>)
	<representation> -> (<theorem><modifiers> <theorem>)  #modification

<modifiers> -> <generative-discriminatory>               
	<generative-discriminatory> -> g                     #generative modification
	<generative-discriminatory> -> d                     #discriminatory modification

(<negation> <theorem>) -> (~<theorem>)
(<compliment> <theorem>) -> {~<theorem>}
(<precession> <theorem>) -> (p <theorem>)
(<sucession> <theorem>) -> (m <theorem>)
```

## Grammar 10 Qualifiers
```
<theorem> -> <axiom>
	<axiom> -> ()
	<axiom> -> P
	<axiom> -> (<negation> <axiom>)
	<axiom> -> (<compliment> <axiom>)

<theorem> -> <collection>
	<collection> -> <theorem>
	<collection> -> <collection> <theorem>
	<collection> -> {<collection>}

<theorem> -> (<precession-succession> <theorem>)
	(<precession-succession> <theorem>) -> ({<precession> <succession>} <theorem>)
		({<precession> <succession>} <theorem>) -> ({p m} <theorem>)
		({<precession> <succession>} <theorem>) -> 
			{(<precesion> <theorem>) (<sucession> <theorem>)}
		
<theorem> -> (<negation> <theorem>)
	(<negation> <theorem>) -> (~<theorem>)

<theorem> -> (<compliment> <theorem>)
	(<compliment> <theorem>) -> {~<theorem>}

<theorem> -> <representation>
	<representation> -> (<theorem> <theorem>)
	<representation> -> (<theorem><modifiers> <theorem>)  # modification

<representation> -> (<qualifiers> <representation>)

<qualifiers> -> <local-nlocal>
	<local-nlocal> -> l                                  #non-local qulification
	<local-nlocal> -> m                                  #local-qualification

<qualifiers> -> <sense>
	<sense> -> sql #light
	<sense> -> sqs #sound
	<sense> -> sqt #tactile
	<sense> -> sqo #olfactory
	<sense> -> sqe #taste

<modifiers> -> <generative-discriminatory>               
	<generative-discriminatory> -> g                     #generative modification
	<generative-discriminatory> -> d                     #discriminatory modification

(<negation> <theorem>) -> (~<theorem>)
(<compliment> <theorem>) -> {~<theorem>}
(<precession> <theorem>) -> (p <theorem>)
(<sucession> <theorem>) -> (m <theorem>)
```

[[Grammar 8 Example Derivations]]