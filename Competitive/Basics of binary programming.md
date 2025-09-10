#algorithms #binary-programming


- The expression `n & (n - 1)` flips all the bits from the rightmost `1` in the number `n` to the rightmost digit, including the rightmost `1`.  
    This means that we can use it to find the number of `1`s in the number.
    
- The numbers which are of the form 2n always have only one `1` in their binary notation.
    
- Binary programming can be used to generate all subsets of a set. This can be done by iterating over numbers 0 to 2n and treating each bit position as an element of the set and the value `0` or `1` as whether the item is present or not.
    

## Find the largest power of 2 (most significant bit in binary form), which is less than or equal to the given number N

If we change all the digits to the right of the most significant `1`, then we can