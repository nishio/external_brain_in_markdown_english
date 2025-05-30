---
title: "3NOT Problem Explanation (Spoiler Alert)"
---

- [[3NOT problem]]
![image](https://gyazo.com/10e6d74d0b066e4206ddb5c12faaaabc/thumb/1000)
The explanation in natural language is below (but it is a natural language explanation of the intent of the code).
python

```
values = {}
values["X"] = [1 if i & 1 else 0 for i in range(8)]
values["Y"] = [1 if i & 2 else 0 for i in range(8)]
values["Z"] = [1 if i & 4 else 0 for i in range(8)]
print(values)
```

output

```
{'X': [0, 1, 0, 1, 0, 1, 0, 1], 'Y': [0, 0, 1, 1, 0, 0, 1, 1], 'Z': [0, 0, 0, 0, 1, 1, 1, 1]}
```


python

```
def do_and(a, b):
    return [values[a][i] & values[b][i] for i in range(8)]


def do_or(a, b):
    return [values[a][i] | values[b][i] for i in range(8)]


print(do_and("X", "Y"))
```

output

```
[0, 0, 0, 1, 0, 0, 0, 1]
```


python

```
def to_str(bits):
    return "".join(str(i) for i in bits)


for v in values:
    print(v, to_str(values[v]))
```

output

```
X 01010101
Y 00110011
Z 00001111
```


python

```
exists = {to_str(v) for v in values}
new_values = values
next_values = {}
for a in new_values:
    for b in values:
        if a != b:
            v = do_and(a, b)
            s = to_str(v)
            if s not in exists:
                exists.add(s)
                next_values[join("&", a, b)] = v
            v = do_or(a, b)
            s = to_str(v)
            if s not in exists:
                exists.add(s)
                next_values[join("|", a, b)] = v
print(next_values)
```

output

```
{'X&Y': [0, 0, 0, 1, 0, 0, 0, 1], 'X|Y': [0, 1, 1, 1, 0, 1, 1, 1], 'X&Z': [0, 0, 0, 0, 0, 1, 0, 1], 'X|Z': [0, 1, 0, 1, 1, 1, 1, 1], 'Y&Z': [0, 0, 0, 0, 0, 0, 1, 1], 'Y|Z': [0, 0, 1, 1, 1, 1, 1, 1]}
```


python

```
exists = {to_str(v) for v in values}
new_values = values
while True:
    next_values = {}
    for a in new_values:
        va = new_values[a]
        for b in values:
            vb = values[b]
            if a != b:
                v = do_and(va, vb)
                s = to_str(v)
                if s not in exists:
                    exists.add(s)
                    next_values[join("&", a, b)] = v
                v = do_or(va, vb)
                s = to_str(v)
                if s not in exists:
                    exists.add(s)
                    next_values[join("|", a, b)] = v
    values.update(new_values)
    new_values = next_values
    if not new_values:
        break
```

output

```
X       01010101
Y       00110011
Z       00001111
X&Y     00010001
X|Y     01110111
X&Z     00000101
X|Z     01011111
Y&Z     00000011
Y|Z     00111111
(X&Y)|X 01010101
(X&Y)|Y 00110011
(X&Y)&Z 00000001
(X&Y)|Z 00011111
(X|Y)&Z 00000111
(X|Y)|Z 01111111
(X&Z)|Y 00110111
(X&Z)|Z 00001111
(X|Z)&Y 00010011
(Y&Z)|X 01010111
(Y|Z)&X 00010101
((X&Y)|Z)&(X|Y) 00010111
```


python

```
ONE_NOT = {"P": do_not(values["((X&Y)|Z)&(X|Y)"])}

update_values(ONE_NOT)
print_values(values)
# (P|((X&Y)&Z))&((X|Y)|Z) 01101001

TWO_NOT = {"Q": do_not(values["(P|((X&Y)&Z))&((X|Y)|Z)"])}
update_values(TWO_NOT)
print_values(values)
# OK

reverse_map = {to_str(v): k for k, v in values.items()}
for name in "XYZ":
    v = values[name]
    s = to_str(do_not(v))
    print(f"~{name} = {reverse_map[s]}")
```

:

```
~X = (Q&(P|(Y&Z)))|(P&(Y|Z))
~Y = (Q&(P|(X&Z)))|(P&(X|Z))
~Z = (Q&(P|(X&Y)))|(P&(X|Y))
```


[full code](https://gist.github.com/nishio/3a76e573c53289049fa985777ef2cc24)

Explanations in natural language
- The output of the logic circuit is either 0/1
- The inputs that affect it are 3 bits and 8 types
- Therefore, "logic circuit" means
    - It is a function that takes a 3-bit 8-way input and outputs 1 bit
    - This is a collection of 8 one bits of "return 0/1 for 8 different inputs"
    - So it can be represented as an 8-bit value.
- No need to distinguish between those with the same bit representation.
    - No need to distinguish between different logic circuits that behave the same
    - Let it be represented by the simplest of things.
    - That is, we can think about at most 256 8-bit integers.
- Given three functions X, Y, and Z
    - Process this to make ~X, ~Y, ~Z
- Only two not operations can be used.
    - S0 "The entire set of functions that can be made in NOT0 times"
    - S1 "The entire set of functions that can be created by adding NOT of one of the functions in S0."
    - S2 "The entire set of functions that can be created by adding NOT of one of the functions in S1."
    - The puzzle of "choosing a function that does a good NOT" so that S2 contains ~X, ~Y, ~Z
- If you enumerate all S0s, there is an obviously suspicious one called `((X&Y)|Z)&(X|Y) 00010111`.
    - Let P be the NOT of this.
- S1 has symmetric `(P|((X&Y)&Z))&((X|Y)|Z) 01101001`.
    - Let Q be the NOT of this
- A quick look at S2 shows that ~X, ~Y, ~Z seem to have been successfully generated.
    - That's a clean output.
:

```
~X = (Q&(P|(Y&Z)))|(P&(Y|Z))
~Y = (Q&(P|(X&Z)))|(P&(X|Z))
~Z = (Q&(P|(X&Y)))|(P&(X|Y))
```


ex-post facto consideration
- ![image](https://gyazo.com/2743b94757a8faacfddec898a3144287/thumb/1000)
- P and Q, where n is the number of standing bits.
    - $P(n) = [n \le 2]$
    - $Q(n) = [n {\,\text{is even}}]$
    - such that the function
    - Considering before the inversion, each bit of n. Is it easier to understand this way?
- The code calculates the and first, so it's an "expression that will eventually be bracketed by and", but it's easier for humans to understand if it's bracketed by or.
    - `~P = ((X&Y)|Z)&(X|Y) = X&Y | Z&X | Z&Y`
        - X, Y, Z when any two and is 1, "n is greater than or equal to 2".
    - `~Q = (P|((X&Y)&Z))&((X|Y)|Z) = X&Y&Z | (P & (X|Y|Z))`
        - n is odd if either all three of X, Y, and Z are 1 (X&Y&Z) or n is less than 2 (P) and one of X, Y, or Z is 1 (X|Y|Z).
    - `~X = (Q&(P|(Y&Z)))|(P&(Y|Z)) = Q&P | P&Y | P&Z | Q&Y&Z`
        - n is even (Q) and less than 2 (P)" i.e. n is 0 and X, Y, Z are all 0
        - Y or Z with n less than 2 (P)."
        - Y and Z with n even (Q)."
        - X is zero when

---
This page is auto-translated from [/nishio/3NOT問題解説(ネタバレ注意)](https://scrapbox.io/nishio/3NOT問題解説(ネタバレ注意)) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.