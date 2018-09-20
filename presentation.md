# Julia

A new interpreted programming language *specifically* made for scientists and engineers

Note: 5 years ago


----

## Compiled

* `C`, `Java`, `Fortran`, `Go`, `Haskell`, `Rust`
* Once compiled, saved in native code as an executable
* Static: you can't change anything once compiled
* Fast: because more things are known about the program's constructs
* Industry standard

----

## Interpreted

* `MATLAB`, `Python`, `R`, `Mathematica`, `JavaScript`, `Julia`
* Dynamic: write → (interpretation-layers) → run
* Easy to code
* Slow: Not so much can be optimized about the program because less is known
* Most relevant for scientific work

Note: interpreted language is best suited for back and forth coding, test, look, repeat.


---

# Two-language problem

Note: R, Python, and MATLAB are coded mostly in C/++. Anything that is fast in those languages is coded in C.

----

## Build good programs

1. Brain-storm in an interpreted language for algorithm exploration and testing.
2. Deliver a performant final-version in a compiled language.


----

## Using interpreted languages

```none
Does a package do exactly
what you need?
             ├── Yes: Great!
             ├── Dunno: You need to read C/++ code.
             └── No: You need to code in C/++.
```

----

## What if the interpreted language is fast enough?

* [Benchmarks](https://julialang.org/benchmarks/)
* Solves the two-language problem

Note: Julia is mostly coded in Julia!

----

## LOC versus speed

![](./assets/cpu_vs_lines.png)


---

# Dynamic & fast, how?

1. Just-in-time compilation (JIT): User-level code is compiled to machine code on-the-fly.
2. Meticulous type system: Designed to maximize impact of JIT.
3. Multiple dispatch: Function dispatch determined at compile time when possible, run time when not.

Note: Julia: easy, dynamic, and fast. How? JIT compilation times are slow for first run


---

# Easy code
Looks like python/MATLAB but with prettier syntax


----

## Syntax

<section style="text-align: left;">
Math:
```julia
2π√3/5α₀
```
Python:
```python
2*np.pi*np.sqrt(3)/(5*alpha0)
```
Julia:
```julia
2π*√3/5α₀
```

----

## Custom infix operators

```julia
# rotate coordinate `c` by `θ` radians
julia> ↺(c, θ) = [cos(θ) -sin(θ); sin(θ) cos(θ)]*c
↺ (generic function with 1 method)

julia> [1,0] ↺ π/2
2-element Array{Float64,1}:
 0.0
 1.0   
```

----

## Embedded units

It took a beetle 36 seconds to walk 25 cm. How many days will it take it to walk 3 km?

```julia
using Unitful:uconvert, cm, km, s, d
v = 25cm/36s
t = 3km/v
uconvert(d, t)
```
5 days

Note: Unicode characters (degree symbol, Greek letters, square root, units!, multidimensional for-loops. Easy to read and understand, scientists are not programmers.


---

# Missing

The concept of `missing` and `NaN` is treated correctly:
```julia
julia> NaN + 1         = NaN

julia> missing + 1     = missing

julia> true | missing  = true

julia> false | missing = missing

julia> true & missing  = missing

julia> false & missing = false
```


---

# Zero overhead

`PyCall.jl, JavaCall.jl, RCall.jl, CCall.jl, Mathematica.jl, MATLAB.jl`

Note: access to all their packages with zero overhead



---

# Free & open source

* Easy to share and collaborate with *anyone*
* Drives the language forward
* Highly specialized and niche solutions and tools
* Free from hardware requirements
* No "black boxes", everything is within reach


---

# Disadvantages

* Ecosystems (e.g. packages, IDEs, debugger) not as mature as in other environments.
* Because R and MATLAB are more purpose-specific, it can be harder to find what you're looking for.
* So new it's harder to Google for answers.
* Loading some packages is still a bit slow.

Note: IDE (Integrated Development Environment)

---

# Conclusions

* Julia is considered by many one of the best interpreted languages out there.
* A number of libraries already far out-perform their equivalents in other languages.
* People come to Julia because of its speed, but stay for the type-dispatch system.
* Suffers from being "too new"


---

<!-- .slide: data-background-color="#ffffff" data-background="./assets/logo.svg" data-background-size="contain" -->
