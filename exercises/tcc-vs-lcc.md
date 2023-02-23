# TCC *vs* LCC

Explain under which circumstances *Tight Class Cohesion* (TCC) and *Loose Class Cohesion* (LCC) metrics produce the same value for a given Java class. Build an example of such as class and include the code below or find one example in an open-source project from Github and include the link to the class below. Could LCC be lower than TCC for any given class? Explain.

## Answer
Tight class cohesion TCC = Nombre de connection direct / Nombre de connection (possible) total

Loose class cohesion LCC = (Nombre de connection direct + Nombre de connection indirect) / Nombre de connection (possible) total

Il est donc possible que les metriques TCC et LCC soit égale si le nombre de connection indirect est égale à zéro.
Il est donc impossible pour la métrique LCC d'être inférieur à TCC

```Python
class A:
    B b

class B:
    A a
    C c

class C:
    B b
```

