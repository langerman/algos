# Intro to Hash Maps

## Hash Maps

Hash maps, in short, are collections of objects stored using key-value pairings. Being that this more technical definition can be thought of as special arrays. Arrays are data structures that allow us to store collections of objects. To access these objects, we ask for a particular index as an integer, and the object located at that index is returned. Hash maps are extremely similar, but more flexible. In arrays, the key-value pairing can be thought of as the index we ask for and the associated object that is returned as a result of asking for that index. When dealing with hash maps, the only difference is we have more flexibility in terms of what data type will act as out key. We ask for specific kay (where out key could be an integer, or a string, or a boolean, etc.) and its associated value is returned (where out value could also be a wide variety of objects).

## Has Map Methods to Know for Interviews

Hash maps offer O(1) or constant time lookup which helps us in a lot of interview questions that require us to answer the questions, "have we seen x before?". For example, when iterating over an array of numbers, we could very quickly answer "have we seen the number 5 yet" if we were to add each of out numbers to a hash map (or hash set) as we see them. Because each key in a hash map can store an associated value, hash maps are also great for things like keeping track of how many times we've seen a specific element, as well as coupling pieces of information together that could be helpful to solve the problem at hand.

## .get() & .put()

Both of these methods are used for retrieving an associated object from our hash map as well as placing a particular object with the associated key in our hash map, respectively.

    // Create a hash map with a string mapping to a boolean.
    Map<String, Boolean> map = new HashMap<>();

    //Adds the given string to our hash map with the associated values.
    map.put("Coding interviews are hard?", true);

    //returns true.
    map.get("Coding interviews are hard?");

## .getOrDefault()

This method is great for retrieving the value associated with the give key if it exists, and placing a default value with the given key otherwise. This helps condense your code from something like "if this key exists, do x and otherwise do y". Less code= less bugs (but never sacrifice code brevity for readability).

Map<Integer, Integer> mpa = new HashMap<>();

    // Returns 1 since 0 does not exist in our map.
    int num = map.getOrDefault(0, 1);

    map.put(3, 4);

    // Returns 4 because 3 exists in our map and maps to 4.
    int otherNum = map.get(3);

## .keySet() & .values()

These two methods will allow you to retrieve all the keys or all thee values currently stored in your map respectively. This could be helpful in the event that you need to see if a certain value exists within the values of hash map (but you don't know the key associated with it if it exists) or for some reason you need to iterate through all the keys in your hash map (because you know a certain value exists in your hash map, but you're not sure which key is associated with it).

    Map<Integer, Integer> map = new HashMap<>();

    // Iterate through all the keys in your hash map.
    for (int key : map.keySet()) {
        // Do something with the current key.
    }

    // Iterate through all the values in your hash map.
    for (int value : map.values()) {
        // Do something with the current value.
    }
