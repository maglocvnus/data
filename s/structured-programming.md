# Structured programming

`Structured programming` is an approach to writing computer programs using clear control structures, rather than allowing execution to jump around unpredictably using low-level `goto` instructions (‘spaghetti code’).

Three fundamental control structures allow program logic to be organised into predictable, understandable blocks:
- **sequence** – instructions run one after the other
- **selection** – the program chooses between paths, eg. `if / else`
- **iteration** – instructions repeat using loops, eg. `for`, `while`. 

The main benefits of structured programming are: readability, maintainability, testability, reusability, fewer defects, and better collaboration.

Structured programming emerged during the 1960s, with the move away from using machine code and assembly language to write programs:
- 1957: The FORTRAN language made high-level programming practical.
- 1966: Corrado Böhm and Giuseppe Jacopini demonstrated theoretically that complex programs could be constructed solely using sequence, selection and iteration operations, and without using arbitrary jumps.
- 1968: Edsger W. Dijkstra published his famous letter ‘Go To Statement Considered Harmful’ in *Communications of the ACM*.
- 1968: NATO Software Engineering Conference led to a greater awareness that intellectual structure could be imposed on programs so that humans could reason about increasingly complicated software – one solution to the growing [software crisis](software-crisis.md).
- 1970: Niklaus Wirth designed the Pascal language in order to teach structured programming principles.
- 1972: Dijkstra, C.A.R. Hoare and Ole-Johan Dahl published the influential book *Structured Programming*.


## Iteration

### Java

```
for (int i = 1; i <= 5; i++) {
    System.out.println(i);
}
```

```
int i = 1;
while (i <= 5) {
    System.out.println(i);
    i++;
}
```

```
String[] names = {"Alice", "Bob", "Charlie"};
for (String name : names) {
    System.out.println(name);
}
```


----

Back up to: [Maglocvnus](../index.md)
