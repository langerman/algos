# Memoization

Memoization is a technique to increase the speed of code by caching expensive computations in order to avoid recomputing them. Once a specific computation is computed, it is then stored and in the event that the same computation is required, its saved result can be returned. By avoiding rerunning unnecessary computations, the overall runtime of the code improves. Long story short, memoization is a form of caching. If the thing you’re looking for is already in your cache (i.e. you’ve already solved that particular case), return it. If not, run the necessary calculations and remember it (i.e. place it in your cache).

## What to Know for Interviews

Memoization is a common technique used during interview questions involving dynamic programming. Memoization is used during recursive top-down dynamic programming solutions in order to avoid recomputing unnecessary subproblems for the problem at hand. A great way to visualize the benefits of memoization is when trying to return the nth Fibonacci number in the Fibonacci sequence recursively. Note that the Fibonacci sequence is a sequence of numbers where each number in the sequence is given by the sum of the previous two numbers and the first two Fibonacci numbers are zero and one. It then follows that the third Fibonacci number is 0 + 1 = 1, the fourth is 1 + 1 = 2, etc. This yields the following formula to calculate the nth Fibonacci number: f(n) = f(n - 1) + f(n - 2) and therefore the following code…

    public int fibN(int n) {
        if (n == 0) {
            return 0;
        } else if (n == 1) {
            return 1;
        } else {
            return fibN(n - 1) + fibN(n - 2);
        }
    }
Let’s image we were asked to compute the nth Fibonacci number recursively and in our example here, we’re computing f(5) (i.e. the fifth Fibonacci number)…

                      f(5)
                    /       \
               f(4)          f(3)
              /    \          /  \
          f(3)    f(2)       f(2) f(1)
          /   \   /   \      /  \
        f(2) f(1) f(1) f(0) f(1) f(0)
Above is the following recursion tree that results from calculating f(5) (i.e. the fifth Fibonacci number). Note that the entire left subtree will be computed before the f(3) (i.e. f(5)’s right child) is called. This results from calling fibN(n -1) before fibN(n - 2). Because of this, we will have solved certain subproblems that are going to repeat, like f(3) and f(2). In order to prune this recursion tree and speed up our code, we can remember the results of these computations (i.e. memoize them) using an array to store the result. Then, if during any of our recursive calls, we’ve already solved the current subproblem, we can simply return its result from our array.

    public int fibNMemoized(int n, int[] memoize) {
        if (n == 0) {
            return 0;
        } else if (n == 1) {
            return 1;
        } else if (memoize[n] != 0) {
            return memoize[n];
        } else {
            memoize[n] = fibNMemoized(n - 1) + fibNMemoized(n - 1);
            return memoize[n];
        }
    }
Now, thanks to our memoize array, our recursion tree will look as follows:

                  f(5)
                  /
                f(4)
               /    \
             f(3)   f(2)
            /   \
         f(2)  f(1)