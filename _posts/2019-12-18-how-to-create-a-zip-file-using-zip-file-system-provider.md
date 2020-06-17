---
title: How to create a zip file using Zip File System Provider
---

> The zip file system provider introduced in the JDK 7 release is an implementation of a custom file system provider. The zip file system provider treats a zip or JAR file as a file system and provides the ability to manipulate the contents of the file. 

According to the docs, we can use the `java.nio.file.FileSystems` class to create a new zip file system and manipulate its' content directly.

Here is a code snippet that can compress one file or directory into a zip file.

<script src="https://gist.github.com/pentiumao/f6ddca4087760362acf5cdccfaba34f7.js"></script>
