We can use the File Class to work with files. The File Class is inside the java.io.package. The File class can be used by creating an object of the class, then specifying the name of the file.

### Why File Handling is Required?
- File Handling is an integral part of any programming as it allows us to store the output of any program in a file and allows us to perform operations with it.
- file handling means reading and writing data to a file

``` java
import java.io.File;

class GFG { 
	public static void main(String[] args) {
		File obj = new File("myfile.txt");
		System.out.println("File Created!");
	}
}
```

### Streams in Java

- A sequence of data is known as a stream.
- This concept is used to perform I/O operations on a file.
- There are two types of streams:

1. Input Stream:
The Java InputStream class is the superclass of all input streams. The input stream is used to read data from numerous input devices like the keyboard, network, etc. InputStream is an abstract class, and because of this, it is not useful by itself. However, its subclasses are used to read data. 

There are several subclasses of the InputStream class.

**Creating an InputStream**
``` java
InputStream obj = new FileInputStream();
```

Here, an input stream is created using FileInputStream();

