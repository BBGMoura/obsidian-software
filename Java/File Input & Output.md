The easiest and best way is to use BufferedWriter or BufferedReader. 

``` java
import java.io.BufferedWriter;

public class FileIO {
	public static void main(String[] args) {
		try (BufferedWriter writer = new BufferedWriter(new FileWriter("output.txt"));
		){
			writer.write("write to file");
		} catch {IOException e} {
			e.printStackTrace();
		}
	}
}
```


BufferedReader

``` java
import java.io.BufferedWriter;

public class FileIO {
	public static void main(String[] args) {
		try (BufferedReader reader = new BufferedREader(new FileReader("input.txt"));
		){
			while(reader.readLine() != null) {
				System.out.println(reader.readLine());
			}
		} catch {IOException e} {
			e.printStackTrace();
		}
	}
}
```

try-with-resources mean we do not need to close the reader or writer, it automatically does this.  Even if there are multiple resources:

``` java
try (BufferedWriter writer = new BufferedWriter(new FileWriter(fileName)); 
	 Scanner scanner = new Scanner(System.in)) { 
	if (scanner.hasNextLine()) writer.write(scanner.nextLine()); 
	} catch(IOException e) {
	 /
	}
```