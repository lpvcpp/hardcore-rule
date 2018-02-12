# Problem 1:
```

class Solution {
public:
    string longestWord(vector<string>& words) {
        std::sort(words.begin(), words.end());
        std::unordered_set<string> built;
        string result;
        for (string w : words) {
            if (w.size() == 1 || built.count(w.substr(0, w.size() - 1))) {
                result = w.size() > result.size() ? w : result;
                built.insert(w);
            }
        }
        return result;
    }
};
```
