This question is asked by Microsoft. Given a message that is encoded using the following encryption method …

    A -> 1
    B -> 2
    C -> 3
    ...
    Z -> 26
Return the total number of ways it can be decoded.
Note: ‘0’ has no mapping and a character following a ‘0’ also has no mapping (i.e. “03”)

Ex: Given the following message…

    message = "23", return 2.
    The message can be decrypted as "BC" (i.e. 2 -> B, 3 -> C)
    The message can also be decrypted as "W" (i.e. 23 -> W)  
Ex: Given the following message…

    message = "1234", return 3.
To solve our problem we must count the total number of ways we can decrypt our message.Because our encryption method maps to the alphabet, the highest number we can decrypt is 26. This important point helps us realize that at every index in our message, we must consider decrying both the current letter and the current letter and next letter together (assuming the two characters represent a number that is at most 26, i.e. 35 could only be considered 3 and 5 separately). Because we must simulate decrypting one or two characters at a time where applicable, this problem can be solved easily using recursion. If at any point during our recursion we reach two digits that cannot be decrypted (i.e. two digits that represent a number larger than 26 or the current character is a ‘0’), we can return early which will help prune our search space. On the other hand if we ever reach the end of our message successfully, we’ve found a valid decryption. If we’ve reached none of these cases, we can continue our recursion trying to find a valid decryption for both the path that only considers the current character as well as the recursive paths that considers the current character and next character together. Once we have the results, we memoize (i.e. store) them in order to ensure we only solve unique subproblems (i.e. if we’ve already solved the current subproblem in a previous recursive calls, let’s store the result so we can return it immediately instead of recomputing it). If we every find that we’re at a subproblem we’ve already solved, we can return its result from our memorize hash map. Once our top level recursive call returns, we will have successfully found all the possible ways to decrypt our message.

    public int numDecodings(String message) {
        if (message == null || message.length() == 0) {
            return 0;
        }

        return decryptMessage(0, message, new HashMap<Integer, Integer>());
    }

    public int decryptMessage(int index, String message, Map<Integer, Integer> memoize) {
        if (index >= message.length()) {
            return 1;
        }
        if (message.charAt(index) == '0') {
            return 0;
        }
        if (index == message.length() - 1) {
            return 1;
        }
        if (memoize.containsKey(index)) {
            return memoize.get(index);
        }

        int waysToDecrypt = decryptMessage(index + 1, message, memoize);
        if (Integer.parseInt(message.substring(index, index + 2)) <= 26) {
            waysToDecrypt += decryptMessage(index + 2, message, memoize);
        }

        memoize.put(index, waysToDecrypt);
        return waysToDecrypt;
    }
## Big-O Analysis

Runtime: O(N) where N is the total number of characters in our message. 

Space complexity: O(N) where N is the total number of characters in our array. This results from storing at most N elements in our memoize hash map.