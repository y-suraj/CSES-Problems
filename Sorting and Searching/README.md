# Sorting and Searching

**Note:** 
- `ll` is `long long`
- `ull` is `unsigned long long`

## 1. Distinct Numbers [link](https://cses.fi/problemset/task/1621/)

Solution:
```cpp
int n;
cin >> n;

set<int> s;

for (int i = 0; i <= n - 1; i++) {
  int num;
  cin >> num;

  s.insert(num);
}
cout << s.size();
```

## 2. Apartments [link](https://cses.fi/problemset/task/1084/)

Solution:
```cpp
ll n, m, k;

cin >> n >> m >> k;

vector<ll> a(n, 0), b(m, 0);

for (int i = 0; i <= n - 1; i++) {
  cin >> a[i];
}
for (int i = 0; i <= m - 1; i++) {
  cin >> b[i];
}

sort(a.begin(), a.end());
sort(b.begin(), b.end());

ll ans = 0;


int i = 0, j = 0;
while (i <= n - 1 && j <= m - 1) {
  ll apl_req = a[i];
  ll available_aptmt = b[j];

  if (abs(apl_req - available_aptmt) <= k) {
    ans++;
    i++;
    j++;
  }
  else if (apl_req - k > available_aptmt) {
    j++;
  }
  else i++;
}
cout << ans;
```
