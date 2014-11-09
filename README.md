Nalie
=====

Nalie tries to modernize Javascript by throwing away ugly parts an rewrite some of its keywords. It also adds modern programming language features such as routines for creating light weight threads.

#Basic operators
##Mutations and immutations
In Javascript there is no mutable and immutable types. In Nalie we define a mutable type with the let keyword and immutable with the set keyword. Both keywords are short and expresses their meaning quite well. `Set` in spoken English implies a strong declaration, whereas `let` implies a soft declaration. We know that `let` keyword is used for block scoping variables in ES6, though we are questioning its usefulness, hence we want to break the API in this case to use `let` keyword for immutable types, because we think mutablility and immutablility is much more important than block scoping variables. We also don't understand why the `let` keyword is used for block scoping variables, it seems unreasonable to use the `let` keyword.

We are inspired by how Swift have implemented their definition. Though we don’t like short names for naming anything in Nalie, e.g for variable->var in Swift. And we think we can improve the simplicity by setting it to just the set keyword. That's why we are dropping `var` keyword in Javascript. 

```
set x, y = 1i, 2i
let x, y = 1i, 2i
```

##Assignment operators
We are adding multiple assignments in Nalie.
```
set x:Int, y:Int = 1, 2
let x:Int, y:int = 1, 2
```

#Control flows
## if
Works as before though we drop the parenthesis.
```
if x == 1 {
  //do stuff
}
```
##For-in
`For-in` statements can take a range specified with `n1..n2`.
```
for something in 1..3 {
  //do stuff
}
```
They can also take an array as before.

```
set posts = [{ 'title': 'title1' }, { title: 'title2'}, ...];
for post in posts {
  //do stuff
}
```


##When
We are dropping the parenthesis because parenthesis implies callability and confuses developers. We still want all blocks to be encapsulated with curly brackets {}. And we are also dropping the switch keyword. We don’t know why many programming languages adopted either the switch or select keywords, but one guess is that select is the short name for selection and thereby used the select keyword for a selection of cases. Switch doesn’t make any sense for us, though it might come from the switch button. Though a switch button usually only have two cases on/off. Switch in spoken English implies two cases also switch means switch to something, which breaks semantics, because we are executing blocks of code if some case is happening and we are not switching from one block to an another.

```
when something {
  is 'ewffe' {
     // do stuff
  }
  is 'wffwe', 'ewfefwewf' {
    // do stuff
    break;
  }
  is any {
    //do stuff
  }
}
```
