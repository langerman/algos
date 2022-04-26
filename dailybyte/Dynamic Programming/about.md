# Dynamic Programming

Dynamic programming is an algorithmic problem-solving technique used to determine optimal results. Dynamic programming works by breaking down a complex problem into smaller, simpler subproblems. Dynamic programming leverages the fact that the optimal solution to a problem depends on optimal solutions to its smaller subproblems. Therefore, by solving these smaller subproblems we can eventually arrive at the optimal solution to the larger problem at hand.

## Top-Down

When solving a problem using dynamic programming there are two potential methods you can use: top-down or bottom-up. A top-down dynamic programming approach recursively breaks down the larger problem at hand into smaller subproblems. The problem is continuously broken down until you arrive at your base case(s) (i.e. the conditionals that stop, or bottom out, your recursion). Having now arrived at your base case(s), you are now able to return an answer for the simplest of cases, and it is from here that you can now begin to build up solutions for larger subproblems. If this approach sound familiar that’s because we practiced in last week’s problems. A bottom-up dynamic programming approach memoizes results to subproblems in order to ensure you only solve each unique subproblem at most once. Each time you arrive at a particular subproblem you check if you’ve already solved it. If you have, you simply return it, if you haven’t, you solve that subproblem and store its result in case you visit it again in the future.

## Bottom-Up

While a top-down dynamic programming approach starts at the top of the problem and moves downward, a bottom-up approach starts at the bottom (i.e. the base cases) and builds upward. In a bottom-up approach, you store intermediary results to smaller subproblems in order to build to the problem at hand. For example, let’s imagine we were asked to compute the factorial of N using dynamic programming. If we opted for a bottom-up approach, we’d want to first solve our base case (i.e. the simplest case we can think of), which in this problem would be the factorial of zero which we know to be one. From here, we’d begin building up to N by asking “what is the factorial of 2?”, “what is the factorial of 3?”, etc. By solving these smaller subproblems, we can eventually easily answer what the factorial of the given N is. The important part of solving the intermediary subproblems is understanding how we can leverage the smaller subproblems (that we’ve already solved) to solve the current subproblem. In our example, we can notice that the factorial of any given number i is i *factorial(i - 1). With this knowledge we realize that dp[i] = i* dp[i - 1] where dp[i - 1] is a subproblem we’ve already solved (note that dp[i] represents the factorial of i)! With this simple formula all we have to do is iterate from one to N populating our dp array (since dp[0] is a base case we’ve already initialized). Once we finish populating our dp array, we can simply return dp[n] since that will hold the factorial of N.

    public int factorial(int n) {
        int[] dp = new int[n + 1];
        dp[0] = 1;
        for (int i = 1; i 
Now that we understand the concept of bottom-up processing, we can optimize this code to only store the result to the last subproblem we solved (since to solve dp[i] we only need to remember dp[i - 1].

    public int factorial(int n) {
        int result = 1;
        int last = 1;
        for (int i = 1; i 
What to Know for Interviews

While top-down and bottom-up processing are both valid ways to solve a dynamic programming problem, it’s important to know the different tradeoffs between the two approaches to be able to discuss them with your interviewer. One positive to using a top-down approach is that you don’t always need to solve all the subproblems in order to solve the problem at hand (obviously this is problem dependent and in the worst case you could need to solve all subproblems). Because of this, it’s possible that top-down approaches could be faster than bottom-up approaches for certain problems. One downside to using top-down approaches is that they use recursion which can potentially cause a stack overflow when processing large inputs. One positive about using a bottom-up approach is that you don’t need to worry about stack overflows for large inputs; whereas one downside to bottom-up approaches is that you need to solve each and every subproblem to arrive at the solution to the problem at hand.
