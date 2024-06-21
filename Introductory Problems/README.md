# Introductory Problems

**Note:** 
- `ll` is `long long`
- `ull` is `unsigned long long`

## 1. Weird Algorithm [link](https://cses.fi/problemset/task/1068)

Solution:
```cpp
long long n;
cin >> n;
cout << n;

while (n != 1) {
   if (n % 2 != 0)
      n = n * 3 + 1;
   else
      n /= 2;
   cout << " " << n;
}
```

## 2. Missing Number [link](https://cses.fi/problemset/task/1083)

Solution:
```cpp
int n;
cin >> n;

for (int i = 1; i <= n; i++) {
   int num;
   cin >> num;
   arr[num] = 1;
}
for (int i = 1; i <= n; i++) {
   if (arr[i] == 0) {
      cout << i;
      break;
   }
}
```

**Better Solution:**
```cpp
ll n;
cin >> n;

ll a[n - 1];

ll xor1 = 0;

for (int i = 0; i < n - 1; i++) {
  cin >> a[i];
  xor1 ^= a[i];
}

ll xor2 = 0;

for (int i = 1; i <= n; i++)
  xor2 ^= i;

cout << (xor1 ^ xor2);
```

## 3. Repetitions [link](https://cses.fi/problemset/task/1069)

Solution:
```cpp
string s;
cin >> s;

int n = s.size();

int maxRep = 1, curLen = 1;

for (int i = 1; i < n; i++) {
  if (s[i] == s[i - 1])
      curLen++;
  else
      curLen = 1;

  maxRep = max(maxRep, curLen);
}
cout << maxRep;
```

## 4. Increasing Array [link](https://cses.fi/problemset/task/1094)

Solution:
```cpp
int n;
cin >> n;

ll sum = 0;
int temp = 0;

for (int i = 0; i < n; i++) {
   int num;
   cin >> num;

   int diff = max(temp - num, 0);
   if (i)
       sum += diff;

   temp = num + diff;
}
cout << sum;
```

## 5. Permutations [link](https://cses.fi/problemset/task/1070)

Solution:
```cpp
int n;
cin >> n;

if (n <= 3 && n > 1) cout << "NO SOLUTION";
else {
   for (int i = 2; i <= n; i += 2)
       cout << i << " ";
   for (int i = 1; i <= n; i += 2)
       cout << i << " ";
}
```

## 6. Number Spiral [link](https://cses.fi/problemset/task/1071)

Solution:
```cpp
int x, y;
cin >> x >> y;

ll n = max(x, y);

ll mid = n * (n - 1) + 1;

if (x == y) cout << mid;
else {
   if (n % 2)
       cout << mid + y - x;
   else
       cout << mid + x - y;
}
```

## 7. Two Knights [link](https://cses.fi/problemset/task/1072)

Solution:
```cpp
vector<ll> ckp(10001, 0);
ckp[1] = 0;
ckp[2] = 6;

for (ll k = 3; k <= 10000; k++) {
   // Calculate the number of ways for a k x k chessboard
   ll total = (k) * k * (k * k - 1) / 2;
   ll attacked = 4 * (k - 1) * (k - 2);

   ckp[k] = total - attacked;
}
ll n;
cin >> n;
for (ll k = 1; k <= n; k++) {
   ll ways = ckp[k];
   cout << ways << "\n";
}
```
