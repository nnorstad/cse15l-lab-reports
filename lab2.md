# Lab 2: Servers and Bugs 
<img width="454" alt="Screen Shot 2023-04-24 at 5 59 48 PM" src="https://user-images.githubusercontent.com/130105980/234149328-768bfea6-3cb7-422a-82d4-50cd4ad4ef0d.png">

## Part 1: String Server
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
The same methods are called as in the example above, but different arguments are passed into the methods because the port and the input strings are different. However, the program functions in the same way.

