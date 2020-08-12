## 정수론(Number Theory)

### 소수
양의 약수가 1과 자기 자신 뿐인 자연수

#### 소수 판별법
1. 가장 단순한 방법
    2부터 n-1까지의 모든 수를 순회하면서 이 중 n의 약수가 있는지 확인하는 방법

    ```
    bool isPrime(int n) {
        if(n <= 1) return false;
        if(n == 2) return true;

        if(n % 2 == 0) return false;

        int sqrtn = int(sqrt(n));

        for(int div = 3; div <= sqrtn; div += 2) {
            if(n % div == 0) return false;
        }
        
        return true;
    }
    ```

    #### 소인수분해
    
    합성수를 소수들의 곱으로 표현하는 방법

    1. 가장 단순한 방법
        2부터 시작하여 n의 소인수가 될 수 있는 수들을 순회하면서, n의 약수를 찾을 때마다 n을 그 숫자로 나누는 방법

        ```
        vector<int> factorSimple(int n) {
            vector<int> ret;
            int sqrtn = int(sqrt(n));

            for(int div = 2; div <= sqrtn; div++) {
                while(n % div == 0) {
                    n /= div;
                    ret.push_back(div);
                }
            }

            if(n > 1) ret.push_back(n);

            return ret;
        }
        ```
