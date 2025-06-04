---
modified: 2025-04-20T23:16:34-07:00
---
## Formalization of Self-Referential Systems
[[Formal Systems]]
[[Process Mechanical Representations of Formal Systems]]
![[Formal Systems 00  Module]]
![[01  Module]]
![[02  Module]]
![[03  Module]]

![[04  Module]]
![[05  Module]]
![[06  Module]]

![[07  Module]]
![[08  Module]]

09 : Module
```
09 : Module
	00 :
	(:= A {
		()
		{~()}
	})
	
	01 : 
	(:= N {
		(=> {} (p {}))
		(=> {} (p| {}))
		(=> {} (m {}))
		(=> {} (m| {}))
	})

10 : Module
	00 :
	(:= A {
		()
		{~()}
	})
	
	01 : 
	(:= N {
		(=> {} (p {}))
		(=> {} (p| {}))
		(=> {} (p|| {}))
		(=> {} (m {}))
		(=> {} (m| {}))
		(=> {} (m|| {}))
	})

```

![[11  Module]]

```
12 : Module
	00 :
	(:= A {
		()
		{~()}
	})
	
	01 : 
	(:= N {
		(=> {} (p {}))
		(=> {} (p| {}))
		(=> {} (p|| {}))
		(=> {} (p||| {}))
		(=> {} (p|||| {}))
		(=> {} (m {}))
		(=> {} (m| {}))
		(=> {} (m|| {}))
		(=> {} (m||| {}))
		(=> {} (m||| {}))
	})
```

```
13 : Module 
	00 :
	(:= A {
		()
		{~()}
	}) 
	
	## Recover difference between symbol and abstraction
	## Generalize the occurances of a {symbol abstraction} in a theorem
	## Represent their interpolation
	## Justification
	00 : 01 : (P (:x (^ (inc x N) (:= x (GEN ))))
	00 : 
	(:= 
		N {
			(()[(m(m()))][()] 
				{(){~()}} 
				{
					{(){~()}}
					{~{(){~()}}}
				}
			)
			
			(()[(m(m()))][(m())]
				{(){~()}} 
				{
					{(){~()}}
					{~{(){~()}}}					
				}
			)

			(=> 
				
					(()[(m(m()))][()] 
						{(){~()}} 
						{
							{(){~()}}
							{~{(){~()}}}
						}
					)
		
					a
					b
				)
				()
			)
		}
	)

	02 : 
	((()[(m(m()))][()] 
		{(){~()}} 
		{
			{(){~()}}
			{~{(){~()}}}
		}
	) x A)
```
[[On expression of abstractions]]

