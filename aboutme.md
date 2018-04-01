---
layout: page
title: About me
subtitle: Why you'd want to go on a date with me
---
18/1/15 = Mon18/1/15 = Mon

#####What is a stream ?

A *stream* is a sequence of data read from or written to an IO device.

- It is to be processed in a sequential order over time (i.e. one by one);
- It it to be interpreted in the format as the user wishes.

Consider

```C++
int a;
double b;
char c;
std::cin >> a;
std::cin >> b;
std::cin >> c;
```

Suppose we enter `1 1 1 ` , then the first 1 would be interpreted as an `int` , the second one a `double` , and the third one a `char` .

#####From What to What ?

Consider

```c++
std::string s1 = "Hello, ";
std::string s2 = "World !";
std::cout << s1 << s2;
```


| operator      | `<<`               | `>>`               |
| :------------ | :----------------- | ------------------ |
| name          | insertion          | extraction         |
| reads         | *put to*           | *get from*         |
| IO direction  | write to / output  | read from / input  |
| syntax        | `ostream << src`   | `istream >> dest`  |
| returns       | `ostream &`        | `istream &`        |
| associativity | from left to right | from left to right |
