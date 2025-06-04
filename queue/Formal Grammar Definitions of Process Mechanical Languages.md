---
modified: 2025-05-06T23:28:15-07:00
---
## Grammar 0
```
<abstraction> -> 
	<stimulus-response>

<abstraction> ->
	<action>

<abstraction> ->
	<reaction>

<abstraction> -> 
	<rep-logical-theorem>
	
<stimulus-response> -> 
	<stimulus>
	
<stimulus-response> ->
	<response>

<stimulus> ->
	(-> <abstraction> <abstraction>)
	
<response> ->
	(<- <abstraction> <abstraction>)

<action> ->
	(==> <abstraction> <abstraction>)
	
<action> -> 
	(==> <abstraction> <abstraction> <abstraction> <abstraction>)
	
<reaction> ->
	(<reaction-class>> <abstraction> <abstraction>)

<reaction> -> 
	(<reaction-class>> <abstraction> <abstraction> <abstraction>)

<reaction-class> -> +
<reaction-class> -> -
<reaction-class> -> ~
```

# Grammar 1 (Isomorphisms)
```
<reticulation> -> <action>
<ingratiation> -> <reaction>
```
