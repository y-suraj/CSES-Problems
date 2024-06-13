### Introductory Problems
1. Weird Algorithm
   [Link](https://cses.fi/problemset/task/1068)
   Solution:
   ```cpp
   		ll n;
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
