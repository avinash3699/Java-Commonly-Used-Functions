## **Reading a file**
```java
BufferedReader reader = new BufferedReader(new FileReader(path));
String line;
while((line = reader.readLine()) != null)
    System.out.println(line);
```

___


## **Writing in a file**

### *Without removing the file contents(appending)*
```java
FileWriter myWriter = new FileWriter(path, true);
BufferedWriter bw = new BufferedWriter(myWriter);
bw.write("text to be written in the file");
bw.newLine(); //move to the next line
bw.close(); //should be closed after writing
```

### *removes the file contents. The newly added contents only will be present(writing)* - **true** parameter is removed from the FileWriter initialization
```java
FileWriter myWriter = new FileWriter(path);
BufferedWriter bw = new BufferedWriter(myWriter);
bw.write("text to be written in the file");
bw.newLine(); //move to the next line
bw.close(); //should be closed after writing
```

___

## **Running *cmd* commands from a java program**

### Using ***Runtime*** and ***Process*** class
```java
Runtime r = Runtime.getRuntime();
Process p = r.exec(command); 

//to get the output of the command
BufferedReader reader = new BufferedReader(new InputStreamReader(p.getInputStream()));
String line;
while ((line = reader.readLine()) != null)
    System.out.println(line);

reader.close();
```

### Using ***ProcessBuilder*** and ***Process*** class
```java
ProcessBuilder builder = new ProcessBuilder("cmd.exe", "/c", command);
builder.redirectErrorStream(true);

Process p = builder.start();

//to get the output of the command
BufferedReader reader = new BufferedReader(new InputStreamReader(p.getInputStream()));
String line = null;
while ((line = reader.readLine()) != null)
    System.out.println(line);

reader.close();
```

___

## **Initialization of a Data Structure with values**

### Map
```java
//Using Anonymous Class (technically very expensive)
Map<String, String> map = new HashMap<>() {
		{
			put(key1, value1);
			put(key2, value2);
			put(key3, value3);
			put(key4, value4);
		}	
};
```

```java
Map<String, String> map = Map.of(
            key1, value1, 
            key2, value2, 
            key3, value3
        );
//This method supports only a maximum of 10 key-value pairs and initializes key-value pairs in random order.
 
```

### List
```java
//Using Anonymous Class (technically very expensive)
List<String> list = new ArrayList<>() {
    {
        add(value);
        add(value);
        add(value);
    }
};
```

```java
List<String> list = new ArrayList<>(Arrays.asList(value, value, value));
```

### Set
```java
//Using Anonymous Class (technically very expensive)
Set<String> list = new HashSet<>() {
    {
        add(value);
        add(value);
        add(value);
    }
};
```

```java
Set<String> list = new HashSet<>(Arrays.asList(value, value, value));
```

___

## **Iterating a map object**
```java
for(String key : map.keySet()){
    System.out.println(map.get(key));
}
```
___
