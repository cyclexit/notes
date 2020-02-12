# Java Note

## Index
* [Read files](#Read-files)

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
