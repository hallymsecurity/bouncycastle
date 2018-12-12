### [Bouncycastle](https://www.bouncycastle.org/)이란?
	- 확장된 기능을 가진 자바암호라이브러리

▪ 자바 암호화 기술 사용의 기본 기능은 Java Cryptography Architecture(JCA)와 그 형제인  Java Cryptography Extension(JCE)이 제공한다.
▪ JCA 아키텍처는 공급자 기반 아키텍처
▪ Java 애플리케이션과 암호화 공급자 사이의 중간 층인터페이스)으로 정의됨

여기서 JCA(자바 암호화 아키텍처)와 JCE(자바 암호화 확장)란?
- JCA는 Runtime environment의 일부이며, JCE는 JDK에 들어 있지 않은 JCA의 확장팩, JDK는 JCA에 정의된 특정한 암호 함수만 사용가능.
- JCA 는 구현 독립성/호환성, 알고리즘 확장성을 고려하여 설계되었다.
 - 구현 독립성: 보안 기능별 독립된 제공자(provider)로 프로그래밍
 - 구현 호환성: 프로그램들간 추상화된(고정되지 않은) 제공자를 통해서 호환
 - 알고리즘 확장성: 대부분의 알고리즘을 지원하고, 임의의 제공자(provider) 추가 가능
- JCE는 JDK에 들어있지 않은 JCA의 확장팩인데, JDK 1.4이상부터는 모든 JDK 버전에 JCE가 들어 있다. 또한 service-provider API를 포함하고 있는데 이 API는 Sun외의 회사가 새로운, 교체가 가능한 암호화 알고리즘을 제공하여 Java Cryptography Architecture specification(JCA)에 잘 맞도록 한다. Sun이 만든 JCA의 구현체를 'Sun JCE'라고 한다.
- 보통 Sun의 JCE를 사용하기를 원하지만 일단 Sun의 JCE가 설치되고 나면 다른 것을 사용하지 못한다고 한다. 즉 Sun의 JCE는 DES, TripleDEs, Blowfish, Difie-Hellman외에는 사용할 수가 없습니다. 따라서 Bouncy Castle를 추천한다고 한다.
- JCA는 전자 서명과 메시지 다이제스트 같은 기능에 대한 일반적인 API를 제공한다.

*기타 JDK 암호 라이브러리*
- JSSE(Java Secure Socket Extension): SSL/TLS 기능 제공
- JGSS(Java Generic Security Services): Kerberos, 네트워크 보안 기능 제공
- SASL(Simple Authentication and Security Layer): 네트워크 보안 기능 제공

||장점|단점|
|---|---|---|
|SUN JCA/JCE|●JDK 에 포함되어 있음 ●'provider'를 선택해서 사용할 수 있음|●JDK 별로 provider 가 일치하지 않아서 동작하지 않을 수 있음 (Java mobile 등)●알고리즘을 많이 제공하지 않음 |
|Bouncy Castle|●JCA 보다 많은 알고리즘을 지원 *SEED128 알고리즘 지원 ●사용에 아무런 제한이 없음(128 비트 암호키 제한 등[5])|●라이브러리 파일을 프로젝트에 추가시켜야함 |

1. JCA
- 전자 서명과 메시지 다이제스트 같은 기능에 대한 일반적인 API 제공
- 주요 클래스들
	- MessageDigest
	- Signature
	- KeyPaireGenerator
	- KeyFactory
	- CertificateFactory
	- KeyStore
	- AlgorithmParameters
	- AlgorithmParameterGenerator
	- SecureRandom
- 암호 서비스 제공자 Sun Provider
	- MD5 메시지 다이제스트
	- -SHA-1 메시지 다이제스트
	- DSA 전자 서명 사인과 검증
	- DSA 키 쌍 생성
	- DSA 키 변환
	- X.509 인증서 생성
	- Proprietary keystore 구현
	- DSA 알고리즘 매개변수
	- DSA 알고리즘 매개변수 생성
- 암호 서비스 제공자 RSAJAC provider
	- RSA 키 쌍 생성
	- RSA 키 변환
	- SHA-1 또는 MD5 메시지 다이제스트를 이용한 RSA 서명

2. JCE
- 주요 클래스와 인터페이스
	-  Cipher
	-  KeyAgreement
	-  KeyGenerator
	-  Mac
	-  SecretKey
	-  SecretKeyFactory