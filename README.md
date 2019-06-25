# vim-increment-array
A snippet of .vimrc that allows you to dumb increment an array (Currently only tested in JavaScript, a VERY early WIP)

# What is it?
Currently overly restrictive and dumb array auto-incrementer; great for kludged legacy code and overly restrictive design limits.

# Why should I use it?
If elements need to be grouped but you must use a 1D Array, this allows you to append a new value halfway in the array, while updating all variables beyond that point.
For example, arr = [0,1,2,3,4]; foo = arr[2] = 2; arr.unshift(-1) => [-1,0,1,2,3,4]; NOW foo = arr[2] = >>1<<

# What does it work on?
Expected to work on: JavaScript, Python, Java, C++
ANY Language that formats arrays as:

[Any Previous Text] Definition = [data,
  goes,
  here
]

# What are the restrictions for now?
Circa 2019-06-05, the current restrictions are:
* INCREDIBLY VOLITILE, WRITES a file named "temp" as I current don't know how to write to a buffer or something along those lines
* Bound to F5, requires grep and awk
* CURRENTLY, CANNOT decrement values when an array element is removed, this will come after the Offset.
* Assumes the Array starts on Line 1 (An offset needs to be added)
* Assumes the Variable Name of the Array is the WORD BEFORE the equals sign; vim is smart and knows that equals is another word, so spacing is lenient.
