feather-ini-parser
==================

Intuitive, fast, lightweight, header, portable INI parser for ANSI C++.

## Methods

Statement     | Return Type
------------- | -------------
ini(filename, doParse)|constructor
ini(data, dataSize, doParse)|constructor
ini.parse()|bool
ini.merge(other INI, retainValues)|void
ini.create(section)|bool
ini.select(section)|bool
ini.set(key, value)|bool
ini.get(key, dvalue = value_t())|dvalue_t
ini.save(filename = "")|bool
ini.clear()|bool
ini[section][key]|value_t&
ini[section]|keys_t&

## Example
```
#include <iostream>
#include "INI.h"

using namespace std;
```
...
```
typedef INI<> ini_t;
//or
//typedef INI<section_t, key_t, value_t> ini_t;

ini_t ini("filename.ini", true);
ini.create("section1"); //Create and select section1
ini.set("key", "value");
cout << ini.get("keynumeric", -1) << endl;
ini["section2"]["key"] = "value";
ini.save();
```

## More
Please see the example .cpp file and Code::Blocks .cbp project for a compilable GCC and VSC++ example. Further examples include enabling wide char support.
