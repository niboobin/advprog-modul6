## Module 6 Tutorial


### Commit 1

### `handle_connection`

The first line inside the function creates a BufReader from the TcpStream. Next, the code creates a vector named http_request by reading lines from the buffered reader. 

The `lines()` method returns an iterator over the lines of the stream. The `map()` method is used to unwrap each Result, effectively ignoring any errors and leaving just the String values. The `take_while()` method is then used to continue taking lines from the iterator until it encounters an empty line.
Finally, `collect` method converts the iterator and collect the lines into a Vec<String>.

The last line of the function prints out the `http_request` vector. the `{:#?}` format specifier used to pretty-print the vector.

