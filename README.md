# Go Guide
A friendly guide to the Go programming language. Written by me!

# Table of Contents

## Part 1
<!--ts-->
   * [What is Go?](#What-is-Go?)
   * [The Basics](#The-Basics)
   * [Program Structure](#Program-Structure)
<!--te-->

# What is Go?

Go, more easily searchable as Golang, is a programming language written by Google. They had millions of lines of code that were being constantly updated. The time it took to use their code to make actual programs was just to high. So, they sought to make a new programming language, one that in their words would "eliminate the slowness and clumsiness of software development"

You're probably asking yourself "Why should I learn Go?" The entire purpose of Go was to make it faster and easier for developers to develop, while still being as powerful as possible. On the coding speed side, it has a garbage collector, which means you don't have to waste time dealing with garbage yourself. On the power side, it has multi-core capabilities and built-in concurrency support.

In short, Go was meant to be as easy to develop in as languages like python, while being as powerful and fast as langauges like C. It's not quite as easy as Python, and it's not quite as fast as C. It is, however, a very good compromise.

# The Basics

A fundamental idea of Go is centered around **readability**. When we talk about optimizing development speed, we're not just talking about writing code; we're also talking about reading code. Once you know Go, you'll be surprised how easy it is to look at Go code and immediately see what it's doing.

## Installing Go

Go is very easy to set up; it should take less than a minute. Head on over to https://golang.org/doc/install, download the latest version for your OS, and follow the instructions. It's that easy.

## Our First Program

Before anything else, let's write a very short program just to get a feel for the langauge. This will be a simple program that prints out "Hello World". 

First, find a folder that you want to store your file in. You can store your Go files anywhere you want. My file is going to be in ```~/Documents/GoProjects/FirstProgram/```. Once you've navigated to your folder, open up any text editor and make a file called ```test.go```.

Type this into your ```test.go``` file. Don't worry, I'll explain what it all means shortly.

```
package main

import "fmt"

func main() {
	fmt.Println("Hello World")
}
```

## Compiling

Like any programming language, Go has a **compiler**. This takes the human-readable code and converts it into an **executable** or a binary file, full of 1's and 0's.

Go is extremely simple to compile. It's done with the ```go build``` command. With our file called ```test.go```, all we'd need to do to compile it is type ```go build test.go```. I'm sure you'll notice another great feature of go here: compile time is extremely short.

Compiling creates an executable file in the same directory that the go file was in. From here, all you need to do is run it like any other executable. Using the same example, an executable ```test``` will have been created in our directory. Just run ```./test```. You should see the following output in your terminal:

```Hello World```

You might think it's a little annoying to have to make an executable and then run it every time you make a change. Thankfully, go has another command, ```go run```. This command will skip the executable and just run your program directly. Try it out with ```go run test.go```. Typically, we'll use ```go run``` while developing, and once we're done we'll use ```go build``` to output the executable as our final product.

# Program Structure

Okay, now that we've seen how the langauge works, it's time to start learning how to program in it. We'll start by dissecting that program we wrote earlier:

```
package main

import "fmt"

func main() {
	fmt.Println("Hello World")
}
```

## Packages

The first line of our program is ```package main```. This is called a **package declaration**, and every Go file starts with one. The package declaration informs the compiler whether to create an *executable* or a *library*. 

If you're a seasoned programmer, you may be familiar with the difference between these two, but I'll explain anyway. An **executable** is something that runs on its own. In bigger programs, an executable might be an individual process that runs, with your program made up of many processes. A **library** doesn't run on its own. It is a collection of code that can be used by the executable(s).

Programs that have a package decalaration of ```package main``` will create an executable file. Note that the package name does not have to be the same name as the directory its in or the name of the file itself. Rather, the ```main``` in ```package main``` is a keyword that tells the go compiler to make an executable.

We'll talk about this more later, but if the program has a package declaration of anything other than ```main```, the compiler will create a package archive file, also known as a *library* file.

## Imports

The next line is ```import "fmt"```. Import statements let us bring in code from other packages; they allow us to use libraries. We only want to import the packages we need so as not to bloat the code.

```fmt``` is the "format" package built in to go. It's analogous to C's ```printf``` and ```scanf```. 

## Functions

