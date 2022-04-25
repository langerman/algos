# Greedy Algorithms

Greedy algorithms are simple, intuitive approaches to problems that yield optimal results. Greedy algorithms greedily choose locally optimal choices at each stage in the problem to lead to a globally optimal solution. Oftentimes, greedy algorithms are simpler to code than other solutions and are quite efficient due to their straightforward nature (i.e. pick the best thing at every chance possible). Although coding greedy algorithms tends to be pretty simple, proving their correctness is what can be hard. A good way to understand greedy algorithms is to think of when you get change from a cashier. When a cashier makes change, they will greedily give you the largest denomination of coin until they have fully given you your change. By greedily selecting the largest denomination coin that is less than or equal to what they owe you, the cashier can guarantee that they give you the fewest coins possible. The logic can be thought of as follows:

    List change = new ArrayList();
    while (amount > 0) {
        int coinGiven = giveLargestCoin(amount, coins);
        amount -= coinGiven;
        change.add(coinGiven);
    }
    return numCoins;

## What to Know for Interviews

There are definitely some well known greedy algorithm problems that you should be aware of interviews. A few of them that I’d recommend looking into are the traveling salesperson problem and that knapsack problem. One well known algorithm that uses a greedy approach to find the shortest path between two point is Dijkstra’s algorithm. To understand greedy algorithms, let’s think through one together. Let’s say that you have a list of tasks to complete all of which have an associated time given by tasks[i]. You, a productive person, want to accomplish as many tasks as possible in a given day, represented by time t. Given a list of tasks and a time t, return the maximum number fo tasks you can complete in the given amount of time. A question like this is great since it represents a real life scenario. When organizing tasks we want to greedily select the task that requires the least amount of time. Why? Because doing so will ensure we maximize the total number of tasks we complete. To do this, we can simply sort our array and constantly take the smallest task as long as we have enough time to complete it. Each time we take a task, we can increment our count of complete tasks and decrement the time we have left by however long that task took. This results in O(NlogN) runtime from sorting our array and O(1) or constant space complexity as we only need a few variables to solve our problem.
