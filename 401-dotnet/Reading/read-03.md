# Read: System.I.O
#### 7/3/20

- [File and Stream I/O](https://docs.microsoft.com/en-us/dotnet/standard/io/)
- [Write to a file](https://docs.microsoft.com/en-us/dotnet/standard/io/how-to-write-text-to-a-file)
- [Read to a file](https://docs.microsoft.com/en-us/dotnet/standard/io/how-to-read-and-write-to-a-newly-created-data-file)

## File and Stream I/O
- Transfer of data either to or from a storage medium
- `System.IO`
    - reading and writing
    - sync and async
    - compression and decompression
- A file is an ordered and named collection of bytes that has persistent storage
- A stream is a sequence of bytes that ust to read from and write to a backing store.

### Files and Directories
- common file and directory classes
    - File - static
    - FileInfo - instance methods
    - Directory - static
    - DirectoryInfo - instance methods
    - Path
- should use exception handling when called filesystem methods [Docs on that](https://docs.microsoft.com/en-us/dotnet/standard/io/handling-io-errors)

### Streams
- fundamental operations:
    - Reading
    - Writing
    - Seeking
- stream classes
    - FileStream
    - IsolatedStorageStream
    - MemoryStream
    - BufferedStream
    - NetworkStream
    - PipeStream
    - CryptoStream
### Async I/O ops
- Reading and writing large data is resource intensive. 
    - When possible you should perform these actions async
    - While doing this in sync it will look like the app has stopped working
- contains `Async` in their names. use `async` and `await` keywords
    - CopyToAsync
    - FlushAsync
    - ReadAsync
    - WriteAsync
### Compression
- `System.IO.Compression` namespace
### Isolated storage
- for secure storage when working on the internets 
### I/O and security
- use access control lists (ACLs)
- don't use I/O classes that require a path to a physical file when writing code that will be downloaded over the internet.
    - use isolated storage instead
- A security check is performed only when the stream is constructed. So don't open a stream and then pass it to a less-trusted code or app domain.

---

## How to: Write text to a file
- Typical classes and methods used:
    - StreamWriter
    - File
    - Path
- `using` - ensures the correct use of `IDisposable` objects.

``` C#
    // Use this to create and write to a txt file
    string[] lines = { "First line", "Second line", "Third line" };

    // Set a variable to the Documents path.
    string docPath =
        Environment.GetFolderPath(Environment.SpecialFolder.MyDocuments);

    // Write the string array to a new file named "WriteLines.txt".
    using (StreamWriter outputFile = new StreamWriter(Path.Combine(docPath, "WriteLines.txt")))
    {
        foreach (string line in lines)
            outputFile.WriteLine(line);
    }
```
``` C#
// Use this to append to a document
    // Set a variable to the Documents path.
    string docPath = Environment.GetFolderPath(Environment.SpecialFolder.MyDocuments);

    // Append text to an existing file named "WriteLines.txt".
    using (StreamWriter outputFile = new StreamWriter(Path.Combine(docPath, "WriteLines.txt"), true)) //the true appends
    {
        outputFile.WriteLine("Fourth Line");
    }
```
``` C#
// use for async
    // Set a variable to the Documents path.
    string docPath = Environment.GetFolderPath(Environment.SpecialFolder.MyDocuments);

    // Write the specified text asynchronously to a new file named "WriteTextAsync.txt".
    using (StreamWriter outputFile = new StreamWriter(Path.Combine(docPath, "WriteTextAsync.txt")))
    {
        await outputFile.WriteAsync("This is a sentence.");
    }
```

---

## How to: Read and write to a newly created data file
- `System.IO.BinaryWriter` and `System.IO.BinaryReader` classes are used for data other than strings