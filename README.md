## 278 : `emplace_back` vs `push_back`

```
vector<string> vec;
// call emplace_back when you want to create a new object
vec.emplace_back(100, 'c');

// 1. reserve space for a new string
// 2. placement new() into new space
```

```
vector<string> vec;
// call push_back when you already have object
vec.push_back(std::string(100, 'c' ));

// 1. create temporary string on the stack
// 2. reserve space for a new string
// 3. placement new() into new space (move constructor)
```

- You can not move const object
- push_back by copy has worst performances
