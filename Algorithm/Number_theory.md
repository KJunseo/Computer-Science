## 정수론(Number Theory)

### 소수
양의 약수가 1과 자기 자신 뿐인 자연수

#### 소수 판별법
1. 가장 단순한 방법
    2부터 n-1까지의 모든 수를 순회하면서 이 중 n의 약수가 있는지 확인하는 방법

    <code>
    bool isPrime(int n) {
        if(n <= 1) return false;
        if(n == 2) return true;

        if(n % 2 == 0) return false;

        int sqrtn = int(sqrt(n));

        for(int div = 3; div <= sqrtn; div += 2) {
            if(n % div == 0) return false;
        }
    }
    </code>