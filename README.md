## Module 6 Tutorial


### Commit 1

### `handle_connection`

The first line inside the function creates a BufReader from the TcpStream. Next, the code creates a vector named http_request by reading lines from the buffered reader. 

The `lines()` method returns an iterator over the lines of the stream. The `map()` method is used to unwrap each Result, effectively ignoring any errors and leaving just the String values. The `take_while()` method is then used to continue taking lines from the iterator until it encounters an empty line.
Finally, `collect` method converts the iterator and collect the lines into a Vec<String>.

The last line of the function prints out the `http_request` vector. the `{:#?}` format specifier used to pretty-print the vector.

### Commit 2

`status_line` is set to "HTTP/1.1 200 OK", which represents a successful HTTP response status line. 

The `contents` variable is set to the contents of the `hello.html` file. This file is read from the file system using `fs::read_to_string`. The `unwrap` method is used to handle any potential errors from reading the file.

`length` variable is set to the length of the contents, which represents the size of the HTTP response body.

`response` is set to a formatted string that includes the status line, the content length, and the contents of the "hello.html" file.

Lastly, the HTTP response is written back to the `TcpStream` using the `write_all` method. The `unwrap` method is used to handle any potential errors from writing to the stream.

![Commit 2 screen capture](/assets/images/commit2.png)

### Commit 3

We refactor the code using `if` and `else` to reduce repetition.

![Commit 3 screen capture](/assets/images/commit3.png)

### Commit 4

If we use the / URL, itll respond quickly. But if you use /sleep, it will `sleep` for 10 seconds before it starts loading the page.

### Commit 5

A thread pool is a way of managing multiple threads to perform tasks in parallel. This is particularly useful for tasks that can be broken down into smaller, independent tasks.