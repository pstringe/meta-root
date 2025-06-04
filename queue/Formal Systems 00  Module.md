---
modified: 2025-04-19T19:04:55-07:00
---
```
# Formal System Def
00 : Module 
	00 :
	A # Axioms

	01 : 
	N # Inferences

	02 : 
	T # Theorems

	03 : 
	a

	04 : 
	t

	05 : 
	f

	06 : 
	(:= t {T F})

	07 : 
	(=>
		(= t T)
		(=== t ({pm}||| t))
	)

	08 :
	(=>
		(= t F)
		(~(=== t ({pm}||| t))
	)

	09 :
	(⊆ t T)

	10 : 
	(=> 
		(∈ t A)
		(∈ t T)
	)

	11 : 
	(=>
		(∈ t T) 
		(∈ (m t) T)
	)

	12 : 
	(∈ f N)
```