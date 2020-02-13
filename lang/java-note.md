# Java Note

## Index
* [Read files](#Read-files)
* [Write files](#Write-files)

## Read files
```java
try {
    File myObj = new File("filename.txt");
    Scanner myReader = new Scanner(myObj);
    while (myReader.hasNextLine()) {
        String data = myReader.nextLine();
        // ...
    }
    myReader.close();
} catch (FileNotFoundException e) {
    System.out.println("File not found.");
    e.printStackTrace();
}
```

## Write files
```java
try {
    String fileName = "example.txt"
    BufferedWriter bWriter = new BufferedWriter(new FileWriter(fileName));
    bWriter.write("example");
    bWriter.close();
} catch (IOException e) {
    System.out.println("Output Exception.");
    e.printStackTrace();
}
```
