## Tips

The simplest way of retrieving arguments in Node.js is via the process.argv array. This is a global object that you can use without importing any additional libraries to use it. You simply need to pass arguments to a Node.js application, just like we showed earlier, and these arguments can be accessed within the application via the process.argv array.

The first element of the process.argv array will always be a file system path pointing to the node executable. The second element is the name of the JavaScript file that is being executed. And the third element is the first argument that was actually passed by the user.

To avoid confusion, I'd like to remind you beginners out there that JavaScript uses zero-based indexes on arrays (like many other languages), which means that first element will be stored at "0th" index and last element will be stored at "n-1" index, where "n" is the total number of elements in the array.

Now let's write a simple Node script that prints all of the command line arguments passed to the application, along with their index. Copy and paste the following code to a file named "processargv.js".

``` 'use strict';

for (let j = 0; j < process.argv.length; j++) {
    console.log(j + ' -> ' + (process.argv[j]));
}

```
All this script does is loop through the process.argv array and prints the indexes, along with the elements stored in those indexes. It's very useful for debugging if you ever question what arguments you're receiving, and in what order.

Now, to run this type the following command. Just make sure you are in the directory where the "processargv.js" file is saved.

$ node processargv.js tom jack 43
Here we are passing three arguments to the "processargv.js" program. You will see that "tom" will be stored at 2nd index while "jack" and "43" will be stored at 3rd and 4th indexes, respectively. 