# CodeForces [Contest ID] - Problem [Letter]: [Problem Name]

* **Problem Link:** [Insert Link Here]
* **Difficulty/Rating:** [e.g., 1200 / Div. 2 B]
* **Topics:** [e.g., Greedy, Dynamic Programming, Two Pointers]

---

## 💡 The "Aha!" Moment (Core Intuition)

*Explain the mental leap required to solve this problem here. What pattern-recognition hints did the problem statement give? Why does a naive/brute-force approach fail, and what trick unlocks the optimal solution? Keep this conversational and highly intuitive.*

---

## 🚶 Step-by-Step Approach

Break down your solution logic into clear, chronological steps:

1. **Step 1:** [e.g., Sorting the array because order doesn't impact the subset sum...]
2. **Step 2:** [e.g., Using a frequency array to track...]
3. **Step 3:** [e.g., Handling edge cases where $N = 1$...]

> 📊 **Visual Trace / Example Walkthrough:**
> If applicable, trace a sample test case here.
> Input: `[3, 1, 4, 2]`
> Sorted: `[1, 2, 3, 4]` -> Dynamic state changes...

---

## 📉 Complexity Analysis

* **Time Complexity:** $O(N \log N)$ due to the initial sorting step. The subsequent linear scan takes $O(N)$ time.
* **Space Complexity:** $O(1)$ auxiliary space as we modify the array in place.

---

## 💻 Implementation

### C++ Source Code

```cpp
// Add your clean, well-commented solution here
#include <iostream>
#include <vector>
#include <algorithm>

using namespace std;

void solve() {
    int n;
    cin >> n;
    vector<int> a(n);
    for (int i = 0; i < n; i++) cin >> a[i];

    // Core logic start
    sort(a.begin(), a.end());
    
    // Add comments to explain tricky code blocks
    int ans = 0;
    for (int i = 0; i < n; i++) {
        // Explaining why this condition is checked...
    }
    
    cout << ans << "\n";
}

int main() {
    ios_base::sync_with_stdio(false);
    cin.tie(NULL);
    int t;
    cin >> t;
    while (t--) solve();
    return 0;
}
