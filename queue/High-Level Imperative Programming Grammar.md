## High-Level Imperative Programming Grammar
Write a grammar capable of generalizing the construction of the following code: 
```
#include "ft_printf.h"

int		chr(t_m *m, char buf[MAX])
{
	int arg;
	int w;
	int i;

	arg = va_arg(m->ap, int);
	w = m->place->width - 1;
	i = -1;
	if (!(m->place->flags & MINUS))
		while (w-- > 0)
			buf[m->pos_b++] = ' ';
	buf[m->pos_b++] = !arg ? '\0' : arg;
	if (m->place->flags & MINUS)
		while (w-- > 0)
			buf[m->pos_b++] = ' ';
	return (0);
}
```
## Enumeration of Grammar Features
- [x] function ✅ 2025-05-07
	- [x] definition ✅ 2025-05-07
		- [x] prototype ✅ 2025-05-07
		- [x] body ✅ 2025-05-07
			- [x] instructions ✅ 2025-05-07
	- [x] call ✅ 2025-05-07
		- [x] name ✅ 2025-05-07
		- [x] arguments ✅ 2025-05-07

- [x] paramaters ✅ 2025-05-07
- [x] arguments ✅ 2025-05-07
- [x] types ✅ 2025-05-07

- [x] dereferences ✅ 2025-05-07
	- [x] general-dereferences ✅ 2025-05-07
	- [x] structural-dereferences ✅ 2025-05-07
	
- [x] index ✅ 2025-05-07

- [x] variable ✅ 2025-05-07

- [x] string ✅ 2025-05-07
	- [x] character ✅ 2025-05-07

- [ ] operation
	- [ ] binary
		- [ ] logical
		- [ ] bitwise
		- [ ] arithmetic
	- [ ] unary
		- [ ] ++
		- [ ] --
	
- [x] name ✅ 2025-05-07
- [x] arguments ✅ 2025-05-07

- [x] instructions ✅ 2025-05-07
	- [x] declaration ✅ 2025-05-07
	- [x] assignment ✅ 2025-05-07
	- [x] control-flow ✅ 2025-05-07

- [x] control-flow ✅ 2025-05-07
	- [x] if ✅ 2025-05-07
	- [x] while ✅ 2025-05-07

- [x] if ✅ 2025-05-07
- [x] while ✅ 2025-05-07
- [x] paramater ✅ 2025-05-07
- [x] argument ✅ 2025-05-07
- [x] string ✅ 2025-05-07
- [x] number ✅ 2025-05-07
- [x] bool ✅ 2025-05-07
- [x] char ✅ 2025-05-07
- [x] void ✅ 2025-05-07
- [x] general-dereferences ✅ 2025-05-07
- [x] structural-dereferences ✅ 2025-05-07
- [x] array ✅ 2025-05-07
- [x] number-type ✅ 2025-05-07
- [x] boolean-type ✅ 2025-05-07
- [x] character-type ✅ 2025-05-07
- [x] string-type ✅ 2025-05-07
- [x] void-type ✅ 2025-05-07

```
(:= `<function-definition>` `<prototype><body>`)
(:= `<function-call>` `<name>(<arguments>)`)
(:= `<prototype>` `<type><white-space><name>(<paramaters>)`)

(:= `<body>` `{<instructions>}`)

(:= `<instructions>` {
	`<declaration>`
	`<variable-assignment>`
	`<control-flow-structure>`
	`<instructions>\n<instructions>`
})

(:= `<type>` {
	`<number-type>`
	`<boolean-type>`
	`<character-type>`
	`<string-type>`
	`<void-type>`
	`<string>`
})

(:= `<name>` `<string>`)

(:= `<paramaters>` {
	`<paramater>`
	`<paramater>, <parameter>`
})

(:= `<arguments>` {
	`<argument>`
	`<argument> <argument>`
})

(:= `<parameter>` {
	`<type> <variable-name>`
	`<type> <general-dereference>` 
})

(:= `<argument>` `<variable-name>`)

(:= `<declaration>` {
	`<variable-declaration>`
	`<typedef-declaration>`
})

(:= `<dereference>` {
	`<general-dereference>`
	`<structure-dereference>`
})

(:= `<general-dereference>` {
	`*`
	`<general-dereference><general-dereference>`
})

(:= `<structure-dereferenc>`
	`<dynamic-structure-dereference>`
	`<static-structure-dereference>`
)

(:= `<dynamic-structure-dereference>` {
	`<variable-name>-><property-name>`
	`<dynamic-structure-dereference>-><property-name>`
})

(:= `<static-structure-dereference>` {
	`<variable-name>.<property-name>`
	`<static-structure-dereference>.<property-name>`
})

(:=
	`<property-name>` `<variable-name>`
)

(:= `<reference>` `&`)

(:= `<index>` {
	`<variable-name>[<number>]`
	`<variable-name>[<variable-name>]`
})

(:= `<variable>` {
	`<variable-name>`
	`<variable-declaration>`
	`<variable-assignment>`
})

(:= `<variable-name>` `<string>`)

(:= `<variable-declaration>` {
	`<type><whitespace><variable-name>`;
	`<type><whitespace><variable-assignment>`
})

(:= `<variable-assignment> {
	`<variable-name>` = '<character>'
	`<variable-name> = <number>`
	`<variable-name> = <boolean>`
	`<variable-name> = <string-literal>`
	`<variable-name> = <string>`
	`<variable-name> = <expression>`
	`<varaible-name> = <array>`
	`<variable-name> = <variable-name>`
})

(:= `<string>` {
	`<character>`
	`<string><character>`
	`<string><whitespace>`
})

(:= `<string-literal>` `"<string>"`)

(:= `<character>` {`a`..`z`,`A`..`Z`, `0`..`9`,`!`..`)`}) # any ascii char

(:= `<whitespace>` {
	` `
	`\t`
	'\n'
})

(:= `<number>` {
	<integer>
	<float>
	{`0` .. `9`}
	<number><number>
})

(:= `<integer>` {
	{`0` .. `9`}
	`<integer><integer>`
})

(:= `<float>` {
	`<integer>.<integer>`
})

(:= `<bool>` {
	`true`
	`false`
})

(:= `<expression>` {
	`<operator>`
	`(<operator>)`
})

(:= `<operation>` {
	`<binary-operation>`
	`<unary-operation>`
} )

(:= `<binary-operation>` {
	`<logical-binary-operation>`
	`<arithmetic-binary-operation>`
	`<bitwise-binary-operation>`
})

(:=
	`<logical-binary-operation>` {
		`<expression> && <expression>`
		`<expression> || <expression>`
	}
)

(:=
	`<arithmetic-binary-operation>` {
		`<expression> + <expression>`
		`<expression> - <expression>`
		`<expression> * <expression>`
		`<expression> / <expression>`
	}
)

(:= `<unary-operation>` {
	`<succession>`
	`<precession>`
	`<logical-negation>`
	`<arithmetic-negation>`
	`<add-assignment>`
	`<sub-assignment>`
	`<div-assignment>`
	`<mult-assignment>`
})

(:= `<succession>` {
	`++<variable-name>`
	`<variable-name>++`
})

(:= `<precession>` {
	`--<variable-name>`
	`<variable-name>++`
})

(:= `<logical-negation>` `!<expression>`)

(:= `<arithmetic-negation>` `-<expression>`)
(:= `<add-assignment>` { 
	`<variable-name> += <expression>`
})
(:= `<sub-assignment>`
(:= `<div-assignment>`
(:= `<mult-assignment>`
	
(:=
	`<control-flow-structure>` {
		`<conditional>`
		`<loop>`
	}
)

(:= `<conditional>` `<if>`)

(:= `<if>` {
	`if (<expression>) {
		<instructions>
	}\n`
	`<else-if>`
	`<if><else>`
})

(:= <else-if> {
	`else if (<expression>) {
		<instructions>
	}\n`
	`<elseif><elseif>`
	`<elseif><else>`
)

(:= `<else>` 
	`else {
		<instructions>
	}`
)

(:= `<loop>` {
	<while>
	<for>
})

(:= `<while>` 
	`while (<expression>) {
		<instructions>
	}`
)

(:= `<array>` {
	`[]`
	`[<elements>]`
})

(:= `<elements>` {
	`<element>`
	`<elements>, <element>`
})

(:=
	`<element>` {
		`<number>`
		`<bool>`
		`<char>`
		`<string>`
	}	
)



(:= `<number-type>` {`<integer-type>` `<float-type>` `<double-type>`})

(:= `<boolean-type>` `bool`)

(:= `<character-type>` `char`)

(:= `<string-type>` `char<general-dereference>`)

(:= `<void-type>` `void`)

(:= `<integer-type>` `int`)

(:= `<float-type>` `float`)

(:= `<double-type>` `double`)
```