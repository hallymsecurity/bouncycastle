# Explanation of Cryptographic Hash APIs

암호화 해시 함수(cryptographic hash function)은 해시 함수의 일종으로, 해시값으로부터 원래의 입력 값과의 관계를 찾기 어려운 성질을 가지는 경우를 의미한다.   
사용되는 알고리즘은 아래와 같다.  
![APIS](https://github.com/kkjy0519/bouncycastle/blob/Member_1/images/HASH_APIS.png?raw=true)


이중에서 가장 많이 사용되는 것은 **MD5**와 **SHA-1**이다. 하지만 <u>안전하지 않다</u>는 것이 밝혀져있다. NIST에서는 2008년 SHA-1 사용을 중지하며 SHA-2를 사용할 것이라고 발표했다.


아래는 해쉬 함수를 테스트 한 것이다.
![test](https://github.com/kkjy0519/bouncycastle/blob/Member_1/images/Test_sha256.png?raw=true)