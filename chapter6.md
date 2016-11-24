# remoteを使用する
remoteサーバーを利用してWeb系以外の言語を実行する方法を説明します。

## remoteを定義する
見出し3(###)を使用してremoteサブセクションを定義し、リスト形式でcommandを定義します。
### main(chpater1.md)

```
### ${remote}

- command: ruby main.rb
```

## Rubyを使う
Rubyを実行するためにはmainのファイル名の拡張子を"rb"とし、remoteのコマンドで「ruby [mainのファイル名]」を指定します。

### main(main.rb)

```
# Specify `puts` to show "Hello world!"
${puts} "Hello World!"
__END__
// Chapter file has following remote definition.

### remote
- command: ruby.rb
```

### remote
- command: ruby main.rb

## PHPを使う
PHPを実行するためにはmainのファイル名の拡張子を"php"とし、remoteのコマンドで「php [mainのファイル名]」を指定します。

phpファイルの先頭行は「<?php」でなければなりません。

### main(main.php)

```
<?php
// Specify `echo` to show "Hello world!"
${echo} "Hello World!";

/*
// Chapter file has following remote definition.

### remote
- command: php main.php
*/
```

### remote
- command: php main.php


## node.jsを使う
nodeを実行するためにはmainのファイル名の拡張子を"js"とし、remoteのコマンドで「node [mainのファイル名]」を指定します。

### main(main.js)

```
// Specify `console.log` to show "Hello world!"
${console}.${log}("Hello World!");

/*
// Chapter file has following remote definition.

### remote
- command: node main.js
*/
```

### remote
- command: node main.js

## Python2を使う
pythonを実行するためにはmainのファイル名の拡張子を"py"とし、remoteのコマンドで「python [mainのファイル名]」を指定します。

### main(main.py)

```
# Specify `print` to show "Hello world!"
${print} "Hello World!"

"""
// Chapter file has following remote definition.

### remote
- command: python main.py
"""
```

### remote
- command: python main.py

## Python3を使う
python3を実行するためにはmainのファイル名の拡張子を"py"とし、remoteのコマンドで「python3 [mainのファイル名]」を指定します。

### main(main.py)

```
# Specify `print` to show "Hello world!"
${print}("Hello World!")

"""
// Chapter file has following remote definition.

### remote
- command: python3 main.py
"""
```

### remote
- command: python3 main.py


## Scalaを使う
Scalaを実行するためにはmainのファイル名の拡張子を"scala"とし、remoteのコマンドで「scala [mainのファイル名]」を指定します。

### main(main.scala)

```
// Specify `println` to show "Hello world!"
${println}("Hello World!")

/*
// Chapter file has following remote definition.

### remote
- command: scala main.scala
*/
```

### remote
- command: scala main.scala

## Goを使う
Goを実行するためにはmainのファイル名の拡張子を"go"とし、remoteのコマンドで「go run [mainのファイル名]」を指定します。

### main(main.go)

```
package main

import "fmt"

func main() {
    // Specify `fmt.Println` to show "Hello world!"
    ${fmt}.${Println}("hello world")
}


/*
// Chapter file has following remote definition.

### remote
- command: go run main.go
*/
```

### remote
- command: go run main.go

## Javaを使う
Javaを実行するためにはmainのファイル名の拡張子を"java"とし、buildでjavacをcommandでjavaを指定します。

### main(Main.java)

```
class Main {
  public static void main(String[] args) {
    // Specify `println` to show "Hello world!"
    ${System}.${out}.${println}("Hello world!");
  }
}

/*
// Chapter file has following remote definition.

### remote
- build: javac Main.java
- command: java -cp . Main
*/
```

### remote
- build: javac Main.java
- command: java Main

## C#を使う
C#を実行するためにはmainのファイル名の拡張子を"cs"とし、buildでmcsをcommandでmonoを指定します。

### main(Main.cs)

```
using System;

class HelloWorld {
  public static void Main( )
  {
    //Specify Console.WriteLine to show "Hello world"
    ${Console}.${WriteLine}("Hello world!");
  }
}


/*
// Chapter file has following remote definition.

### remote
- build: mcs Main.cs
- command: mono Main.exe
*/
```

### remote
- build: mcs Main.cs
- command: mono Main.exe

## Cを使う
Cを実行するためにはmainのファイル名の拡張子を"c"とし、buildでgccをcommandでコンパイルされたファイルを実行します。

### main(main.c)

```
#include <stdio.h>
 
main()
{
    //Specify printf to show "Hello world"
    ${printf}("Hello world!");
}

/*
// Chapter file has following remote definition.

### remote
- build: gcc -o main main.c
- command: ./main
*/
```

### remote
- build: gcc -o main main.c
- command: ./main

## C++を使う
C++を実行するためにはmainのファイル名の拡張子を"c"とし、buildでmcsをcommandでmonoを指定します。

### main(main.cpp)

```
#include <iostream>
 
int main()
{
    //Specify std::cout to show "Hello world"
    ${std}::${cout} << "Hello World!";
}

/*
// Chapter file has following remote definition.

### remote
- build: c++ -o main main.cpp
- command: ./main
*/
```

### remote
- build: c++ -o main main.cpp
- command: ./main

## nodeでnpmを使う
nodeでnpmを使う場合はmainのファイル名の拡張子を"js"とし、buildでnpm installをcommandでnodeを指定します。

### main(main.js)

```
var moment = require("moment");

//Show current time by moment
console.log("This time is" + ${moment}());

/*
// Chapter file has following remote definition.

### remote
- build: npm install
- command: node main.js
*/
```

### files
- [package.json](npm-test/package.json)

### remote
- build: npm install
- command: node main.js
