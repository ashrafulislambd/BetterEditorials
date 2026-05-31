# CodeForces 2218 - Problem E: The 67th XOR Problem

* **Problem Link:** https://codeforces.com/problemset/problem/2218/E
* **Difficulty/Rating:** 1200
* **Topics:** Brute Force

---

## 💡 The "Aha!" Moment (Core Intuition)

Notice that after each operation, the array size decreases by one. For instance, an array of size 10 will progressively shrink to 9, 8, 7, and eventually reach a size of 2. Let's say these last two elements are $x$ and $y$. 

Now, we need to see what storm has gone over these two numbers throughout the whole **journey**. Did they change? Surely they did. Notice that they were XORed with **the** same number every time. Thus, if a bit of $x$ was toggled, the bit at the same position in $y$ was also toggled. Although the bits were toggled, their XOR sum remained the same because toggling **a bit twice is the same as not toggling it at all**. So, we can say all the previous operations had no effect on the value of $x \oplus y$.

At the next step, the final value is $x \oplus y$, which is the last element remaining. Thus, we can say **the answer totally depends on which $x$ and $y$ we choose to leave for last**. As the value of `n` is not large, we can brute-force over all pairs of $x$ and $y$ and choose the maximum one.

---

## 📉 Complexity Analysis

* **Time Complexity:** $O(n^2)$ due to all possible pair checking.
* **Space Complexity:** $O(1)$.

---

## 💻 Implementation

### C++ Source Code

```cpp
#include <bits/stdc++.h>
using namespace std;

#define int long long

void solve(int tcase) {
	//input
	int n; cin >> n;
	vector<int> a(n);
	for(auto& x : a) cin >> x;

	//mx keeps track of the maximum answer
	int mx = 0;

	//iterate over all pairs of x and y we can leave for the last
	for(int i=0; i<n-1; i++) {
		for(int j=i+1; j<n; j++) {
			//update maximum possible value of x ^ y
			mx = max(mx, a[i]^a[j]);
		}
	}

	//output
	cout << mx << endl;
}		

signed main() {
	int t=1; cin >> t;
	for(int i=1; i<=t; i++) {
		solve(i);
	}
    return 0;
}
