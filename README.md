## `emplace_back` vs `push_back`

### `emplace_back`

```
vector<string> vec;
// call emplace_back when you want to create a new object
vec.emplace_back(100, 'c');

// 1. reserve space for a new string
// 2. placement new() into new space
```
