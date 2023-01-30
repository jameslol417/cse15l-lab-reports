# Lab Report 1
---

**Part 1: Making StringServer**  
The code for StringServer is as below
`import java.io.IOException;
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
} `
