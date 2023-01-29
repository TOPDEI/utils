# TOPDEI - How to compile, run and test!

## How to compile, run and test my program?

This file contains instructions on how to compile, run and test the program for different languages (C++, C, Python and Java).

The instructions are divided into three parts:
1. Compiling the program
2. Run the program
3. Run the program with tests
4. Script to compile, run and test the program

## Requirements

* C and C++ (17 or higher): GCC 8.5.0 compiler
* Python 3.7.9 (or higher) and pypy3 3.7.9 (or higher)
* Java 11 (or higher): OpenJDK 11.0.13 compiler

For Windows, you can use the following tools:

* Windows Subsystem for Linux (WSL) (https://ubuntu.com/tutorials/install-ubuntu-on-wsl2-on-windows-10#1-overview) and then install the tools mentioned above execute the following commands:

```bash
sudo apt update
sudo apt install build-essential
sudo apt install openjdk-11-jdk
sudo apt install pypy3
```

* Visual Studio Code
  * C/C++ (https://code.visualstudio.com/docs/languages/cpp)
  * Java (https://code.visualstudio.com/docs/languages/java)
  * Python (https://code.visualstudio.com/docs/languages/python)

For Mac OS X, you can use the following tools:

* Xcode (https://developer.apple.com/xcode/)
* Visual Studio Code (https://code.visualstudio.com/docs/languages/cpp)

For Linux, you can use the following tools:

* Visual Studio Code (https://code.visualstudio.com/docs/languages/cpp)

To verify the version of the compiler, run the following command:

```bash
g++ --version
```

__Note:__ If you want to use another compiler, you must make sure that it supports the C++17 standard.

---


## 1. Compilation

This section describes how to compile each source code in Linux.

__Note:__ The compilation process is the same for Windows and Mac OS X, but the commands are different.

### C

1. Open a terminal and go to the directory where the source code is located.
2. Run the following command:
  
  ```bash
  gcc -std=c17 -Wall -Wextra -O2 -lm -o <output_file> <source_file>
  ```
3. Example:
  
  ```bash
  gcc -std=c17 -Wall -Wextra -O2 -lm -o main main.c
  ```

### C++ source code

1. Open a terminal and go to the directory where the source code is located.
2. Run the following command:

```bash
g++ -std=c++17 -Wall -Wextra -O2 -lm -o <output_file> <source_file>
```
3. Example:
  
  ```bash
  g++ -std=c++17 -Wall -Wextra -O2 -lm -o main main.cpp
  ```

### Java source code

1. Open a terminal and go to the directory where the source code is located.
2. Run the following command:

```bash
javac -encoding utf8 <source_file>
```
3. Example:
  
  ```bash
  javac -encoding utf8 Main.java
  ```
4. __Note:__ The output file is `Main.class`.

---

## 2. Running the program

This section describes how to run each program.

### C, C++ source code

1. Open a terminal and go to the directory where the source code is located.
2. Run the following command:

```bash
./<output_file>
```
3. Example:
  
  ```bash
  ./main
  ```

### Python source code

1. Open a terminal and go to the directory where the source code is located.
2. Run the following command:

```bash
pypy3 <source_file>
```
3. Example:
  
  ```bash
  pypy3 main.py
  ```

### Java source code

1. Open a terminal and go to the directory where the output code is located.
2. Run the following command:

```bash
java -Xmx256M -Xss256M -classpath . <output_file>
```
3. Example:
  
  ```bash
  java -Xmx256M -Xss256M -classpath . Main
  ```
4. __Note:__ The output file is the name of the class without the `.java` extension.

---

## 3. Running the program with tests

### 3.1 Read input from the input file
To run each program with the input data, you must redirect the input data to the program.

For example, if you want to run the program with the input data `input.txt`, you must run the following command:

### C, C++ source code

```bash
./<output_file> < input.txt
```

### Python source code

```bash
pypy3 <source_file> < input.txt
```

### Java source code

```bash
java -Xmx256M -Xss256M -classpath . <output_file> < input.txt
```

### 3.2 Output to the output file

To output the result to a file, you must redirect the output to a file.

For example, if you want to run the program with the input data `input.txt` and output the result to the file `output.txt`, you must run the following command:

### C, C++ source code

```bash
./<output_file> < input.txt > output.txt
```

### Python source code

```bash
python3 <source_file> < input.txt > output.txt
```

### Java source code

```bash
java -Xmx256M -Xss256M -classpath . <output_file> < input.txt > output.txt
```

---
## 4. Script to compile, run and test the program

In this folder there is also a script called `run.sh` that can be used to compile, run and test the program using the instructions presented in the following sections. The script can be used as follows:

```bash
./run.sh <code> <input>
```

where `<code>` is the name of the file with the source code and `<input>` is the name of the file with the input to the program.

For example, if you want to run the program with the source code `main.cpp` and the input data `input.txt`, you must run the following command:

```bash
./run.sh main.cpp input.txt
```

**Note**: To run the script, you must have the permissions to execute it. If you don't have the permissions, you can run the following command:

```bash
chmod +x run.sh
```
