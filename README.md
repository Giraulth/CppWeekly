## 278 : `emplace_back` vs `push_back`

```
vector<string> vec;
vec.emplace_back(100, 'c');

// 1. reserve space for a new string
// 2. placement new() into new space
```

```
vector<string> vec;
vec.push_back(std::string(100, 'c' ));

// 1. create temporary string on the stack
// 2. reserve space for a new string
// 3. placement new() into new space (move constructor)
```
- Call `emplace_back` when you want to create a new object
- Call `push_back` when you already have object
- You can not `move` a `const` object
- `push_back` by copy has worst performances

## 287 : Understanding `auto`

- `auto` uses the exact same rules as template type parameters (copy)
- `auto` will never deduce a `&`
- `const`-ness will be deduced (for references and pointers)
- * value type are always copies

