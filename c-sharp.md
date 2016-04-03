# C sharp
[in progress] 3 presentations processed

This cheatsheet constains most important parts from [Programming in C# Jump Start](https://mva.microsoft.com/en-US/training-courses/programming-in-c-jump-start-14254).
I have experience with C++/Java, etc. so here will be only new parts for me. I will try to don't put here evident parts. Struct of this document will be changed on-the-fly.

Word *CLASSIC* - it has same behavior as in C++/Java.

# Comments

```C#
/// <summary>
/// Comment
/// </summary>
```


# Regular expressions
```C#
var pattern = @"\b\w+\b";
var matches = Regex.Matches(source, pattern);
var value = matches[1].Value;
```

# String
Immutable.
Use **Stringbuilder** for building.
# Class

## Struct
Like classes, but stored as value, not reference.
## Constructor
```C#
public Class() :base(name) {}
```

## Virtual methods

Can be overriden. Non virtual be overriden too. But we need right cast to call them.

## Casting
```C#
a is object; // same like java 'instanceof'
```

```C#
Dog a;
Cat b = a as Cat; // will be null, because cannot cast dog as cat
Cat c = (Cat)a; // throw exception
```
## Inheritance

simple

+ **static**
	- *CLASSIC*
+ **abstract**
	- *CLASSIC*
+ **sealed**
	- like java *final* keyword
	
## Visibility

+ **public**
	- visible from any assembly
+ **private**
	- *CLASSIC*
+ **protected**
	- *CLASSIC*
+ **internal**
	- visible from same assembly

## Named arguments

```C#
AddPoint(maxPoints:10);
```


## Properties

```C#
public double Weight {get; private set;}

private string _color;
public string Color
{
	get { return _color; }
	set { _color = value; }
}
```


## Events

```C#
public event EventHandler Completed;

public void Process() {
	
	Completed += myHandler;

	if (Completed != null) { // we need to check it in general
		Completed(this, EventArgs.Empty);
	}
}
```

# Flow
## Foreach
```C#
var strings = new[] { "a", "b" };
foreach (var s in strings) {
	Console.WriteLine(s);
}
```
## GOTO
*CLASSIC*

# Variables
```C#
var a = 5; // like C++ auto a = 5;
```

# Reflexion
