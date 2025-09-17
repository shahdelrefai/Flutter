## What is Dart?
- Open-source
- Scalable
- Class based, purely object oriented
- Dynamic language with C style syntax 

## Why Dart?
- Supports JIT (Just in Time)
  > Code can be continuously recompiled which allows features like `hot reload`; that make the development cycle faster.
- Optionally Typed (static or dynamic)

## Hello World

```dart
// Entry point to Dart program
main() {
    print("Hello, world!");
}
```

***
# Variables 
- Declared using `var` -> optional typing.
  > You can't change the variable's type after the first declaration.
- Variables are references.
- Uninitialized variables have an initial value of null.

**Built-in types**

- int
- double
- string
- boolean
- list
- map

#### List
```dart
var students = ["Shahd", "Devin", "Aslan"]; // accepts any type of (if we added 1 or true no error occurs)

List<String> series = ["Aile", "Chernobyl"];
```

#### Map
```dart
var map = {
    "name": "Shahd Tharwat",
    "age": 22,
    "isEnrolled": true,
    "courses": ["dart", "flutter", "ios"]
};

Map<int, String> user = {
    1: "shahd tharwat",
    2: "devin akin"
};
```

### Nullable
When a variable has an option to be null add `?` after the initialization.
```dart
String? name;
print(name??"user"); // in case name is null print user
``` 

## Constant and Final Values
Values once set can't be changed.

- `const`: Must be assigned when declared (on compile-time).
- `final`: Can stay null until initialized.

***

# User Input
```dart
import 'dart:io';

void main(){
    print("Enter your name:");
    String? name = stdin.readLineSync();
    
    print("Hello, $name!\nWelcome to our website.");
}
```

***

# Loops
### C-like loop
```dart
for(int i; i < 5; i++) {
    print(i);
}
```

### For-in loop for iterable classes
```dart
var cities = ["Istanbul", "Cairo", "Barcelona"];

for(var city in cities) {
    print(city);
}
```

***

# Enums
An enumeration is used for defining named constant values. An enumerated type is declared using the enum keyword.

```dart
enum ComputerStatus {
    running,
    stopped,
    waiting,
    locked
}

void main() {
    ComputerStatus status = ComputerStatus.locked;
    
    switch(status) {
        case ComputerStatus.running:
            print("computer is running"):
            break;
        case ComputerStatus.stopped:
            print("computer is stopped"):
            break;
        case ComputerStatus.waiting:
        case ComputerStatus. locked:
            print("computer is waiting or locked");
            break;
    }
}
```

***

# Functions
### Parameters
- Positional ()
- Optional []
- Named {}

> Use `required` before the parameter when dealing with Named to prevent null handling.

## Function as object
```dart
main() {
    var function;
    function = (String s) => prints);
    doWork(function);
}

doWork(f(String s)) {
    f("hello world");
}
```

***

# OOP
- Dart's OO model is similar to Java and C#.
- Everything is an object, and every object is an instance of a class. All objects inherit from the Object class.

## Class
```dart
class ClassName {
    <fields>
    
    <constructors>
    
    <setters/getters>
    
    <functions>
}
```

## Inheritance
- Dart support single inheritance and multiple interfaces.
- To make attributes private add `_underscore` before the identifier.
- Mixin (includes)

```dart
abstract class User {
    String _name;
    int _age;
    
    User(this._name, this._age);
    
    void setName(String name) {
        _name = name;
    }
    
    String getName() {
        return _name;
    }
    
    void setAge(int age) {
        _age = age;
    }
    
    String getAge() {
        return _age;
    }
}

class Admin extends User with AuthMethod {
    Admin(name, age):super(name, age);
    
    getAllUsers() {}
}

class Customer extends User with AuthMethod {
    Customer(name, age):super(name, age);
    
    getMyOrders() {}
}

class AuthMethod {}
```
