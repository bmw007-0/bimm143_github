# Class 6: R Functions
Brian Wong (PID: A18639001)

- [Background](#background)
- [Our first function](#our-first-function)
- [A Protein generating function](#a-protein-generating-function)

## Background

ALl functions in R have at least 3 things:

- A **name** that we use to call the function.
- One or more input **arguments**.
- The **body** the lines of R code that do the work

## Our first function

Let’s write a silly wee function called `add()` to add some numbers (the
input arguments)

``` r
add <- function(x, y){
  x + y
}
```

Now we can use this function

``` r
add(100, 1)
```

    [1] 101

``` r
add(x=10, y=10)
```

    [1] 20

``` r
add(x=c(100, 1, 100), y=1)
```

    [1] 101   2 101

> Q. What if I give a multiple element vector to `x` and `y`?

``` r
add(x=c(100, 1), y=c(100, 1))
```

    [1] 200   2

> Q. What if I give three inputs to the function?

``` r
#add(x=c(100, 1), y=1, z=1)
```

> Q. What if I give only one input to the add function?

``` r
addnew <- function(x, y=1){
  x + y
}
```

``` r
addnew(x=100)
```

    [1] 101

``` r
addnew(c(100,1), 100)
```

    [1] 200 101

If we write our function with input arguments having no default value,
then the user will be required to set them when they use the function.
We can give our input arguments “default” values by setting them equal
to some sensible value - e.g. y=1 in the `addnew()` function.

\##A second function

Let’s try something more interesting: Make a sequence generating tool…

The `sample()` function can be a useful starting point here:

``` r
sample(1:10, size = 4)
```

    [1] 7 3 2 4

> Q. Generate 9 random numbers taken from the input vector x=1:10?

``` r
sample(1:10, size = 9)
```

    [1]  5  8 10  4  6  9  3  7  1

> Q. Generate 12 random numbers taken from the input vector x=1:10?

``` r
sample(1:10, size = 12, replace = TRUE)
```

     [1] 6 9 5 2 4 7 6 7 8 6 6 1

> Q. Write code for the `sample()` function that generates nucleotide
> sequences of length 6?

``` r
sample(c("A","T","C","G"), size = 6, replace = TRUE)
```

    [1] "T" "C" "A" "T" "A" "T"

> Q. Write a first function `generate_dna()` that returns a user
> specified length DNA sequence:

``` r
generate_dna <- function(len=6){
  sample(c("A","T","C","G"), size = len, replace = TRUE)
}
```

``` r
generate_dna(len=100)
```

      [1] "T" "G" "T" "A" "C" "A" "T" "A" "A" "C" "A" "T" "G" "G" "C" "A" "T" "C"
     [19] "A" "G" "G" "T" "T" "A" "A" "C" "A" "A" "T" "T" "T" "A" "A" "T" "C" "C"
     [37] "T" "T" "A" "G" "A" "C" "T" "T" "C" "C" "T" "A" "G" "T" "C" "G" "C" "G"
     [55] "G" "T" "G" "T" "C" "C" "G" "G" "G" "A" "G" "C" "T" "T" "C" "C" "T" "T"
     [73] "G" "T" "C" "G" "C" "T" "A" "A" "A" "A" "G" "T" "A" "C" "C" "G" "C" "A"
     [91] "G" "A" "T" "G" "G" "T" "A" "G" "T" "C"

> **Key-Points** Every function in R looks fundamentally the same in
> terms of its structure. Basically 3 things: name, input, body

    name <- function(input){
      body
    }

> Functions can have multiple inputs. These can be **required**
> arguments or **optional** argument with optional arguments having a
> set default value.

> Q. Modify and improve our `generate_dna()` function to return its
> generated sequence in a more standard format like “AGTAGTA” rather
> than the vector “A”, “C”, “G”, “A”

``` r
generate_dna <- function(len=6, fasta=TRUE){
  ans <- sample(c("A","T","C","G"), size = len, replace = TRUE)
  if(fasta){
    cat("Single-element vector output")
    ans <- paste(ans, collapse = "")
  }else{
    cat("Multi-element vecotr ouptut")
  }
  
  return(ans)
}

generate_dna()
```

    Single-element vector output

    [1] "AACCCC"

The `paste()` function - its job is to join up or stick together (a.k.a
paste) input strings together

``` r
paste(c("alice", "loves R", sep="****"))
```

    [1] "alice"   "loves R" "****"   

FLow control means where the R brain goes in your code

``` r
good_mood <- TRUE

if(good_mood){
  cat("Great!")
}else{
  cat("Bummer!")
}
```

    Great!

## A Protein generating function

> Q. Write a funciton, called `generate_protein()`, that genreates a
> user specified length protein sequence.

There are 20 natural amino-acids:

``` r
aa <-c("A","R","N","D","C","E","Q","G","H",
       "I","L","K","M","F","P",
       "S","T", "W", "Y", "V")
```

``` r
generate_protein <- function(len){
  
  # The amino-acids to sample from
  aa <-c("A","R","N","D","C","E","Q","G","H",
       "I","L","K","M","F","P",
       "S","T", "W", "Y", "V")
  # Draw n=len amino-acids to make our sequence
  ans <- sample(aa, size = len, replace = T)
  ans <- paste(ans, collapse = "")
  return(ans)
}
```

``` r
myseq <- generate_protein(42)
myseq
```

    [1] "GCHITWIDRWGRNWFEWSVYHCQTREMQYRQDCILGFGWMIF"

> Q. Use that function to generate random protein sequences betwen
> length 6 and 12

``` r
for(i in 6:12){
  # FASTA ID line > ">id"
  cat(">",i,sep="","\n")
  # Protein Sequence Line
  cat(generate_protein(i), "\n")
}
```

    >6
    YYPASY 
    >7
    RDRFCLP 
    >8
    AYTMDLNP 
    >9
    DNTEGKHML 
    >10
    RQKMAFAKGQ 
    >11
    SPPSHAREFYY 
    >12
    TIKLHFQCQFPA 

> Q. Are any of your sequences unique i.e. not found anywhere in nature?

Yes, there are unique sequences starting at 9 amino acids all the way up
to 12.
