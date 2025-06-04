---
modified: 2025-04-08T00:26:44-07:00
---
```
[Point : {
	[properties : {
		(:= (/ |P| (:x (inc x Number))) {})            # E1.1
	}]
}]

[Line : {
	[properties : {
		[length : Number],                             # E1.2 
		[breadth : Number],
		(:= breadth {})                                # E1.3
	}],
	[extremities : Point{}],
	[straight : (Line) -> {T F}],
	[lie : (points : Points, lie : Line) -> {T F}]
}]

(= lie  =>  
(= straigt (line : Line) : { T F } => (? lie)
```