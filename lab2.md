# Lab 2: Servers and Bugs 
<img width="454" alt="Screen Shot 2023-04-24 at 5 59 48 PM" src="https://user-images.githubusercontent.com/130105980/234149328-768bfea6-3cb7-422a-82d4-50cd4ad4ef0d.png">

## Part 1: String Server

<img width="200" alt="String Server" src="https://user-images.githubusercontent.com/130105980/234154256-3646beae-ac1a-43c5-8bd1-799f4deaea20.jpg">

In this part of the lab, we wrote a web server that takes a URL and concatenates the input string to other input strings and prints them on the web page. The code for this process is below:
```
import java.net.URI;
import java.io.IOException;
import java.util.ArrayList;

class StringHandler implements URLHandler {
    ArrayList<String> storedStrings = new ArrayList<>(){};
    public String handleRequest(URI url){
        if (url.getPath().contains("/add")){
            String [] strArr = url.getQuery().split("=");
            storedStrings.add(strArr[1]);
            String printed = storedStrings.get(0);
            for (int i = 1; i < storedStrings.size(); i ++){
                printed = String.join("\n", printed, storedStrings.get(i));
            }
            return printed;
        }
        else {
            return "Please enter a valid extension";
        }
    }
}

public class StringServer{
    public static void main(String[] args) throws IOException {
        if(args.length == 0){
            System.out.println("Missing port number! Try any number between 1024 to 49151");
            return;
        }

        int port = Integer.parseInt(args[0]);

        Server.start(port, new StringHandler());
    }
}
```
**Example 1:**

<img width="670" alt="Screen Shot 2023-04-24 at 6 07 24 PM" src="https://user-images.githubusercontent.com/130105980/234150129-d7317f4e-890d-483f-8b31-5eeb69b83946.png">

In this example, the main method is the first method to be called. The command line arguments were as follows:
``` 
$ javac StringServer.java
$ java StringServer 4003
    Server Started! Visit http://localhost:4003 to visit.
```
The first command compiles the code and the second calls the main method to activate the server. The main method takes a string array as an argument. This should contain the port number, which is needed to activate the server. This number is parsed to an integer and passed to the Server.start method. The Server.start method instantiates a new StringHandler object so the server can access the StringHandler code. 
   
Next, the handleRequest method is called when a valid URL is entered into a browser. This method takes a URL as a parameter. It uses this input to get the proper output. It parses the URL, adds the correct string to the list of strings, and concatenates and returns all the input string. The strings are stored in an ArrayList that is initialized at the beginning of the program. This allows the server to print out all the strings that are added to the site. 

We use the contains method to determine the path of the URL. If it contains the proper key word, we add the following string to the list, and if it doesn't an error message is returned. Before adding the string, we must separate the string from the rest of the path with the use of the getQuery and split methods. GetQuery gets the portion of the path after the "?", and split splits the resulting string at the character "=", which is specified in the paramter of the split method.

The output of these methods is added to the ArrayList with the add method. The strings in the ArrayList are concatenated, stored in a single field, and returned. This is what is printed on screen in the screenshot above. Each line is a separate string that was entered as a query into the URL. The above process was repeated for each string entry.

**Example 2:**

<img width="372" alt="Screen Shot 2023-04-24 at 6 34 56 PM" src="https://user-images.githubusercontent.com/130105980/234153151-a85b5ca5-c958-4e21-9b1e-a3e40efc0218.png">

In this example, the main method is called again.
```
$ javac StringServer.java
$ java StringServer 4005
    Server Started! Visit http://localhost:4005 to visit.
```
The same methods are called as in the example above, but different arguments are passed into the methods because the port and the input strings are different. However, the program functions in the same way. For some of the methods, the arguments will be the same. For example, we always want to split the string at "=" and we always want to look for "/add" in the URL, so there are no changes to the split and contains methods. The join method will still join the strings with a new line, but the strings will be different for each input. 


## Part 2: Bugs

<img width="400" alt="output" src="https://user-images.githubusercontent.com/130105980/234154471-0ed23984-ba8d-45ce-a648-352e7fe73a1d.png">

Array Example:
1. Failure inducing input:
    ```
    @Test
    public void testReverseInPlace(){
    int[] input1 = {1, 2, 3};
    ArrayExamples.reverseInPlace(new int[] {3, 2, 1}, input1};
    }
    ```
    
2. Non-failure inducing input:
    ```
    @Test
    public void testReverseInPlace(){
    int[] input1 = {1};
    ArrayExamples.reverseInPlace(new int[] {3}, input1};
    }
    ```
    
3. The code produces an error for one of the tests, but not the other.

    <img width="700" alt="Screen Shot 2023-04-24 at 7 15 50 PM" src="https://user-images.githubusercontent.com/130105980/234157850-4e1a0de3-30e7-40db-8b78-2636361b4a36.png">


4. The code did not properly change all the elements of the array. It is correct in some aspects. For example, the programmer did recognize that the first    element should be assigned to the last and the second element should be assigned to the second to last and so on. This is evident from the line of code
   in the initial for loop. The problem is, the loop iterates through all indices of the array and doesn't store the values that are changed, so only part
   of the list can be correctly reversed. 

    ```
    static void reverseInPlace(int[] arr) {
        for(int i = 0; i < arr.length; i += 1) {
          arr[i] = arr[arr.length - i - 1];
        }
      }
     ```
 
    In the revised code, the loop iterates through only half of the list, and each variable closer to the end of the array is stored in a temporary
    variable so the data is not lost when the data in the earlier element is assigned to the later element. This allows the later element to be assigned 
    to the earlier element after the data stored at the index has been changed. 

    ```
    static void reverseInPlace(int[] arr) {
        for(int i = 0; i < arr.length/2; i += 1) {
          int temp = arr[i];
          arr[i] = arr[arr.length - i - 1];
          arr[arr.length - i - 1] = temp;
        }
      }
    ```

## Part 3: What I Learned 

I big part of my learning in lab 2 was about how servers interpret user input. I really had no idea how browsers interpretted data, and although this was a highly simplified example, it still gave me an idea of how these techniques can be implemented on a larger scale. I especially enjoyed programming the search engine. A lot of the programming classes I have taken don't produce such a clear output, and it was fun to interact with. Even though my friends made fun of me for how bad the search engine was at searching anything besides previously entered strings, I was thrilled to be able to program something like that with little guidance. Although I have done some JUnit testing in CSE 12, I found the testing practice in lab 3 to be incredibly healpful and I was glad to learn more about how to properly implement JUnit tests.



Thanks for reading!

<img width="484" alt="Screen Shot 2023-04-24 at 7 18 27 PM" src="https://user-images.githubusercontent.com/130105980/234158175-709bd52e-625e-4f8f-8b21-1410104af197.png">
