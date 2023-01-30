# Lab Report 1
---

**Part 1: Making StringServer**  
The code for StringServer is as below  
```
import java.io.IOException;
import java.net.URI;

class Handler implements URLHandler {
    String result = "";

    public String handleRequest(URI url) {
        if (url.getPath().equals("/")) {
            return result;
        }
        else {
            System.out.println("Path: " + url.getPath());
            if (url.getPath().contains("/add-message")) {
                String[] parameters = url.getQuery().split("=");
                if (parameters[0].equals("s")) {
                    result += parameters[1] + "\n";
                    return result;
                }
            }
            return "404 Not Found!";
        }
    }
}

class StringServer {
    public static void main(String[] args) throws IOException {
        if(args.length == 0){
            System.out.println("Missing port number! Try any number between 1024 to 49151");
            return;
        }

        int port = Integer.parseInt(args[0]);

        Server.start(port, new Handler());
    }
}
```  
![Image](2-1.png)  
* When typing in the following url: *localhost:4000/add-message?s=pineapple*, the method handleRequest from class Handler is called.
* Relevant arguments for the method above is the *URI url*. The field *String result* stores the data + "\n"(newline) for each input that is taken in the query part(after ?) of the url. The value for the *String result* is changed from ""(empty String) to "pineapple\n" after taking in the above url as a request.   
![Image](2-2.png)  
* When typing in the following url: *localhost:4000/add-message?s=pancake*, the method handleRequest from class Handler is called.
* Relevant arguments for the method above is the *URI url*. The value for the *String result* is changed from "pineapple\n"(empty String) to "pineapple\pancake\n" after taking in the above url as a request.
