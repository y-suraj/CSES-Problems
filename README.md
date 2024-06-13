# CSES-Problems
## [Introduction](https://cses.fi/problemset/text/2433)
####[Reference books](https://cses.fi/book/)
####[FREE Ebook on Competitive Programming](https://cses.fi/book/book.pdf)

Click here to see all the CSES problems set.](https://cses.fi/problemset/)

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
