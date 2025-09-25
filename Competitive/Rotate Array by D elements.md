#array #competetive #problem

# Problem

Rotate an array `arr` by `d` elements.

##  Example

```
arr = [1, 2, 3, 4, 5]
```

and we need to shift it by 3

```
d = 3
```

The final product needed is:-

```
arr = [4, 5, 1, 2, 3]
```
# Solution:-
(Reversal Algorithm)

If we reverse the whole array, we get this:-
```
arr = [5, 4, 3, 2, 1]
```

If we reverse the first `arr.size() - d`, we get:-

```
arr = [4, 5, 3, 2, 1]
```

Now reverse the last `d` indices:-

```
arr [4, 5, 1, 2, 3]
```

## Code

```C++
#include <bits/stdc++.h>
using namespace std;

void print(vector<int> & arr){
    for(auto i : arr){
        cout << i << " ";
    }
    cout << endl;
}

void reverse(vector<int> & arr, int start, int end){
    for(int left = start, right = end; left < right; left++, right--){
        int temp = arr[left];
        arr[left] = arr[right];
        arr[right] = temp;
    }
}

void actualLogic(vector<int>& arr, int shift){
    int lastIndex = arr.size() - 1;
    reverse(arr, 0, lastIndex);
    reverse(arr, 0, lastIndex - shift);
    reverse(arr, lastIndex - shift + 1, lastIndex);
    print(arr);
}


int main() {
	int t;
	cin >> t;
	while(t-- != 0){
	    int n, d;
	    cin >> n >> d;
	    vector<int> arr(n);
	    for(int i = 0; i < n; i++){
	        cin >> arr[i];
	    }
	    actualLogic(arr, d);
	}
	return 0;
}


```


