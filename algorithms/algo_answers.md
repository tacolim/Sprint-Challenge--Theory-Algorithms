# Exercise I

### A
  * linear O(n)

### B
  * log O(log n)

### C
  * linear O(n)

### D
  * log linear O(n log n)

### E
  * cubic O(n^3)

### F
  * linear O(n)

### G
  * linear O(n)

# Exercise II

### A
```
function maxDiff(arr) {
    let low = arr[0];
    let high = arr[1] - low;
        
    for (let i = 0; i < arr.length; i++) {
      let current = arr[i];
      let possible = current - low;
      low = low < current ? low : current;
      high = possible > high ? possible : high;
    }
    return high;
  }
  ```