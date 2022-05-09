# Intro to Advanced Topics

## Binary search

Binary search is an algorithm that is used to quickly find an element in an array given some criteria. Binary search leverages the fact that the given array is sorted in order to reduce the runtime of finding the particular element in question from O(N) (i.e.a linear scan through all N elements) to O(log(N)) which results from halving our search space with every comparison. Binary search typically works as follows:

Initialize pointers left and right to represent your initial search space
Calculate a midpoint, mid ((left + right) / 2)
Check if array[mid] is your desired value
Return array[mid]/mid if it is the desired value or adjust your left/right pointer and go back to step two if not.
Brain teasers

While brainteasers have largely stopped being asked during technical interviews it’s better to prepare for the worst and hope for the best than to not prepare at all. Because of this, we’ve decided to add a brainteaser question in the small chance you encounter one during your interview. Some of the questions that used to be asked by companies like Google included: “How many gas stations are there in Manhattan?”, “Why are manhole covers round?”, and my personal favorite: “You’re shrunk to the size of a nickel and thrown in a blender. The blades begin turning in 60 seconds, what do you do to escape?”.

## Math

Most Interview questions will not direct test your mathematical skills, but knowing some mathematical properties and formulas can definitely help you in certain instances. Remember that if you’re asked a math question during one of your interviews don’t be afraid to ask additional questions…again, they’re testing your algorithmic problem solving skills, not your math knowledge directly. For example, if you were given a set of points and asked to find the maximum number of points that exist on the same line it’d be fair to ask for a reminder that the equation for a line is given by: y = mx + b.

## Bit Manipulation

Bit manipulation is the act of assessing or manipulating the binary representation of numbers using low level operators. Some of these common bitwise operators are OR (|), AND (&), XOR (^), left shift (>>/>>>), and right shift (<</<<<). It is important to know how to leverage these operators in the event that your interview question pertains to the binary representation of numbers. If it does, here are some quick tricks to remember: 
Multiply i by 2N: i << n 
Divide i by 2N: i >> n 
Extract lowest set bit: i & (-i) 
Toggle ith bit: num ^= (1 << i) 
Swap values: x ^= y; y ^= x; x ^= y;

## Tries

A trie, also known as a prefix tree, is a tree data structure typically used to compactly store strings. Tries offer efficient runtimes for answering queries like “how many words start with the prefix x?” and “what letter is most likely to follow the prefix ‘co’?”. Tries can also help reduce space complexity when storing strings that share common prefixes. Tries offer a space complexity of O(N * M) in the worst case where N is the number of words stored in your trie and M is the maximum number of letters in any string. Tries offer an insert and lookup time of O(M) where M is the total number of characters in the string to be inserted/searched for.

## Union-Find

Union find is a data structure that efficiently tracks disjoint sets of elements (i.e. non-connected subsets of elements). Union-find can also efficiently merge two independent sets together and quickly answer questions like “do these two elements belong to the same group?”. Union find utilizes two key methods union, responsible for merging two disjoint sets together, and find, responsible for finding the source of the two disjoint sets that are to be merged.

## Sieve of Eratosthenes

The Sieve of Eratosthenes is an ancient algorithm, created by Greek mathematician Eratosthenes, used to quickly find prime numbers up to a given value. It accomplishes this by iteratively eliminating multiples of the current number beginning with the first prime number two. By continuously eliminating multiples of the current number we are eventually left with only primes. The Sieve of Eratosthenes runs in O(N * loglog(N)) time where N is the number we’re asking to generate primes up until and requires O(N) space complexity where again N is the number we’re asked to generate primes up until.