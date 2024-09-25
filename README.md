# Checking for "any character" using regular expressions in multiline text

".\*" may not be what you want in multi-line strings
Suppose you have the string

```cpp
Start this is a 
multiline string End
```

and you want to match everything between the "Start" and "End" using a regular expression. The obvious one to use is

```cpp
Start(.*)End
```

but in multi-line strings (strings that contain newlines) this will fail because "." does not match against newlines. 

The answer? Use "[\s\S]" (match and space character or non-space character) instead of "."

```cpp
Start([\s\S]*)End
```
