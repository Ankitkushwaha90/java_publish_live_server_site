---
title: "live server"
decription: "In this server write in java code for good understaindin . and it 's give best knowleage again. I hope help this content. Thanks So must :) "
---

### Liver server And  We can access from any where.

```java
import com.sun.net.httpserver.HttpServer;
import com.sun.net.httpserver.HttpHandler;
import com.sun.net.httpserver.HttpExchange;
import java.io.IOException;
import java.io.OutputStream;
import java.net.InetSocketAddress;

public class SimpleHttpServer {
    public static void main(String[] args) throws IOException {
        // Create a new HTTP server on port 8000
        HttpServer server = HttpServer.create(new InetSocketAddress(8000), 0);

        // Create a simple handler to handle incoming requests
        server.createContext("/", new MyHandler());

        // Start the server
        server.start();
        System.out.println("Server is running and listening on port 8000...");
    }

    static class MyHandler implements HttpHandler {
        @Override
        public void handle(HttpExchange exchange) throws IOException {
            // Prepare the response content
            String response = "Hello, this is my simple HTTP server!";

            // Set the response headers
            exchange.getResponseHeaders().set("Content-Type", "text/plain");
            exchange.sendResponseHeaders(200, response.getBytes().length);

            // Write the response content to the output stream
            OutputStream os = exchange.getResponseBody();
            os.write(response.getBytes());
            os.close();
        }
    }
}



```
