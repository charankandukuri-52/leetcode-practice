# leetcode-practice


## Subarrays, Substrings, Subsequences

### 459. Repeated Substring Pattern
```javascript

var repeatedSubstringPattern = function(s) {
    // Initialize an empty string to store the potential repeating substring
    let ans = '';
    
    // Iterate up to half the length of the string, as any repeating pattern 
    // must be within this range
    for (let i = 0; i < Math.floor(s.length / 2); i++) {
        // Add the current character to the potential repeating substring
        ans += s[i];
        
        // Create a string by repeating 'ans' enough times to match the length of 's'
        let repeated = ans.repeat(s.length / ans.length);
        
        // Check if:
        // 1. The length of 's' is divisible by the length of 'ans' 
        //    (indicating that 'ans' could be a repeating unit)
        // 2. The repeated version of 'ans' equals the original string 's'
        if (s.length % ans.length === 0 && repeated === s) {
            return true; // If both conditions are met, 's' is made of repeating 'ans'
        }
    }
    
    // If no valid repeating pattern is found, return false
    return false;
};
```
