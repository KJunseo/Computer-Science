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

#### 에라토스테네스의 체

주어진 수 이하의 모든 소수를 찾아내는 방법

1. 2부터 n까지의 모든 수를 나열한다.

2. 2부터 시작하여 그 수의 배수를 모두 지운다.

3. 지워지지 않은 수를 기준으로 2번 작업을 계속한다.

```
int n;
bool isPrime[MAX_N+1]; // 소수 여부를 bool로 나타냄

void eratosthenes() {
    memset(isPrime, 1, sizeof(isPrime));

    isPrime[0] = isPrime[1] = false; // 예외처리
    int sqrtn = int(sqrt(n));

    for(int i = 2; i <= sqrtn; i++) {
        
        // 아직 지워지지 않았다면
        if(isPrime[i]) {
            
            // i*i 미만의 배수는 이미 지워진 상태
            for(int j = i*i; j <= n; j+=i) {
                isPrime[j] = false;
            }
        }
    }


}
```

수행 시간이 빠르지만, 메모리를 많이 사용할 수 있다. 짝수를 별도로 처리하든지, 비트마스크를 사용하든지 하여 메모리 사용량을 최적화해야한다.

#### 에라토스테네스의 체를 이용한 빠른 소인수 분해

**각 숫자가 소수인지 합성수인지만을 기록하지 않고, 각 숫자의 가장 작은 소인수를 같이 기록해둔다.**

```
int minFactor[MAX_N]; // 각 수의 가장 작은 소인수를 기록해 두는 배열

// 에라토스테네스의 체
void eratosthenes() {

    minFactor[0] = minFactor[1] = -1; // 1은 예외 처리 해주기

    // 자기자신으로 초기화
    for(int i = 2; i <= n; i++) {
        minFactor[i] = i;
    }

    int sqrtn = int(sqrt(n));
    for(int i = 2; i <= sqrtn; i++) {
        if(minFactor[i] == i) {
            for(int j = i*i; j <= n; j+=i) {

                // 아직 약수를 본 적 없는 수인 경우 i로 바꾸기 
                if(minFactor[j] == j) {
                    minFactor[j] == i;
                }
            }
        }
    }
}

// 소인수 분해
vector<int> factor(int n) {
    vector<int> ret;

    while(n > 1) {
        ret.push_back(minFactor[n]);
        n /= minFactor[n];
    }

    return ret; 
}
```