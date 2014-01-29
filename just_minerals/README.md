Minerals Only Template
===============
This template assumes the lessor owns the mineral rights, but not the surface rights, to a piece of property.

Graphical Representation
===========
Accompanying the template is a graphical representation of the lease rendered using graphviz.  The code is shown below. 

```DOT
digraph G {
 j [label = "development obligation"];
 a [label = "lease starts", style="filled", color="palegreen"];
 b [label = "deferred drilling", style="filled", color="palegreen"];
 c [label = "drill", style="filled", color="palegreen"];
 branch [label="production-triggered spawn pt"];
 d [label = "production", color="darkgreen", style="filled", fontcolor="white"];
 f [label = "rework"];
 g [label = "shut-in", color="palegreen", style="filled"];
 h [label = "force majeure", color="palegreen", style="filled"];
 i [label = "lease ends"];
 k [label = "spawn pt triggered by offset obligation"];
 a -> c;
 a -> i [label = "2 yrs"];
 c -> branch;
 branch -> d;
 branch -> j;
 d -> f [dir="both"];
 d -> g [dir="both"];
 d -> h [dir="both"];
 f -> i [label="2 months"];
 g -> i [label="1 year"];
 h -> i [label="1 year"];
 j -> i [label="2 months"];
 j -> c;
 f -> g [dir="both"];
 h -> g [dir="both"];
 h -> f [dir="both"];
 c -> i [label="1 yr"];
 j -> b;
 b -> i [label="3 months"];
 b -> c;
 k -> c;
 k -> i [label="2 months"]; 
}
```
