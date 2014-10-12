---
layout: post
title:  "Mode, Type and Class of R objects"
date:   2014-10-12 10:17:59
categories: 
- Issues
tags:
- R
- Discussion

---

## Mode, Type and Class of R objects

In the R training class, some students are confused about the `mode`, `type` and `class` in R language definition. So I write this post to clarify this question.

### Mode, Type

`mode` and `storage.mode` are the old-style types (where storage.mode is more accurate), and `typeof` is the newer, even more accurate version. `typeof` determines the (R internal) type or storage mode of any object.

`mode` and `storage.mode` get or set the type or storage mode of an object, both relying on the output of `typeof(x)`.

R objects are often coerced to different types during computations. There are also many functions available to perform explicit coercion. When programming in the R language the type of an object generally doesn't affect the computations, however, when dealing with foreign languages or the operating system it is often necessary to ensure that an object is of the correct type.

### Class
R possesses a simple generic function mechanism which can be used for an object-oriented style of programming. Method dispatch takes place based on the class of the first argument to the generic function. An object can have any class and more than one class. The class can be created by you. 

`class` is mostly just the class attribute of an object. But when the class attribute is not set, the class function makes up a class from the object type and the dim attribute.

```r
class(3L) # integer
class(structure(3L, dim=1)) # array
class(structure(3L, dim=c(1,1))) # matrix
class(list(1)) # list
class(structure(list(1), dim=1)) # array
class(structure(list(1), dim=c(1,1))) # matrix
class(structure(list(1), dim=1, class='ABC')) # ABC
```


```r
x <- 1:5
class(x) <- "A"
attr(x, "class") <- c("A","B")
class(x)
```

```
## [1] "A" "B"
```


References: 

[R language definition-Objects](http://stat.ethz.ch/R-manual/R-devel/doc/manual/R-lang.html#Objects)

[StackExchange discussion 1](http://stats.stackexchange.com/questions/3212/mode-class-and-type-of-r-objects)

[StackExchange discussion 2](http://stackoverflow.com/questions/8855589/a-comprehensive-survey-of-the-types-of-things-in-r-mode-and-class-and-type)


