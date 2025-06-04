---
modified: 2025-05-18T16:55:45-07:00
---
## Grammar as Argument
```
00 : Module
	00: (:= <s> {
		`(` # <open-paren>
		`:` # <colon>
		`=` # <equal>
		`<` # <a-bracket-o>
		`s` # <char-s>
		`>` # <a-bracket-close>
		`{` # <c-bracket-open>
		`\`` # <quote>
		`\\` # <escape>
		`a` # <a-char>
		`b` # <>
		`c`
		`s`
		`0`
		`1`
		`2`
		`3`
		`4`
		`5`
		`6`
		`7`
		`8`
		`9`
		`-`
		`)`
		`}`
	})


00: (:= `<a>` {
	`<b><c>`
	`<b><a><c>`
})

01 : (:= {00} {              #(>> {00} {01})
	(:= `<a>` `<b><c>`)
	(:= `<a>` `<b><a><c>`)
})

02 : (:= `<a>` `<b><c>`)     #(>> {01} {02})

03 : (:= `<a>` `<b><a><c>`)  #(>> {01} {03})

01 : (:= `<b>` `(`)     

02 : (:= `<c>` `)`)         

```
## Method of Proof of completed information
0. Argument 
1. Comment inferences
2. Generalize inference
3. Add inference to formal system
4. Derive the conclusion of the argument as a theorem

Formal Systems may then be:
0. re-used for future proofs
1. united with others to resolve inconsistency
2. or modified to prove a theorem/state that would normally result in an inconsistency. 

```
(<
	(e (formalization x))
	(e (formalization (formalization x)))
)

(interpretation x)
(<
	(e (interpretation x))
	(e (interpretation (interpretation x)))
)

(e 
	({(){~()}}
		({interpretation formalization} x)
	)
)

# low e operations
#geometry
#succession 
#combination
#arithmetic
#chrome

Given 
(>>

	(:= 
		({(){~()}} {(){~()}}) 
		({(){~()}} ({(){~()}} {(){~()}}) ) 
	)
	
	(:=
		({(){~()}} x)
		({(){~()}} ({(){~()}} x))
	)
)

(=> 
	(!= () {~()})
	(!= (- () {~()}) 0)
)

(>>
	(- ({(){~()}} x) ())
	(!= ())

({(){}~()} (= (e (f x)) 0))
```

PROPN : An inference is a rule defining how to move/transform one theorem/state into the next.
PROPN : An ing
PROPN : An implication is an abstraction of one or more inferences
## Formalization of Grammar as Argument
```
00: (:= `<a>` {
	`<b><c>`
	`<b><a><c>`
})

01 : (:= {00} {              #(>> {00} {01})
	(:= `<a>` `<b><c>`)
	(:= `<a>` `<b><a><c>`)
})

02 : (:= `<a>` `<b><c>`)     #(>> {01} {02})

03 : (:= `<a>` `<b><a><c>`)  #(>> {01} {03})

(>> 
	(:= <abstraction> {<collection>})
	(:= <abstraciton> (:
		{(p <collection>) <abstraction>}
			(= (m (p <collection>)) ())
	})
)
```