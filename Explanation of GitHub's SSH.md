Explanation of GitHub's SSH
=
[SSH란?](https://terms.naver.com/entry.nhn?docId=3351634&cid=40942&categoryId=32828)
-
Secure Shell의 약어.
인터넷상에서 두 호스트(Host) 사이의 통신 암호화 관련 인증 기술들을 사용하여, 안전한 접속과 통신을 제공하는 프로토콜을 의미한다. 이 프로토콜은 보안에 취약점을 가지고 있는 프로토콜, 즉 원격 로그인(rlogin), 원격 명령 실행(rsh), 원격 파일 복사(rcp), 원격 접속 서비스(telnet), 파일 전송용 프로토콜(ftp) 등을 대체하여 사용되며, 임의의 포트에 대해 안전한 채널을 제공하고 있다.

원격 접속에서 가장 중요한 부분이 인증 방법인데, 기본적으로는 사전에 미리 약속된 공개키를 사용하여 전자 서명을 통해 인증을 하지만, 공개키를 사용한 전자 서명에 의한 인증이나 다른 인증 방법들이 사용될 수 없는 경우에는 전통적인 인증 방식인 패스워드를 사용하여 인증을 하게 된다. 이러한 경우에도 호스트 사이의 모든 통신이 암호화에 의해서 자동 보호되기 때문에 어떠한 네트워크 공격으로도 패스워드가 노출되지 않는다.

GitHub에서의 SSH
-
### SSH를 사용하는 방법
+ 자동으로 생성된 public-private 키 쌍을 사용하여 네트워크 연결을 암호화한 다음, 암호 인증을 사용하여 로그온하는 것이다.
+ 수동으로 생성된 public-private 키 쌍을 사용하여 암호를 지정하지 않고 로그인하여 사용자 또는 프로그램을 허용하는 것이다.

### GitHub에서의 SSH설정 방법
1. SSH사용을 원하는 repository의 Settings를 클릭한다.
2. Settings의 Options중 Deploy keys를 클릭한다.
3. 우측 상단의 Add deploy key를 클릭한다.
4. key에 자신의 public키를 입력한 후 쓰기를 원할경우 Allow write access를 체크한다.(체크하지 않을시 읽기만 가능)
5. Clone시 ssh주소를 사용하며 private키로 로그인한다.
![SSH-1](https://github.com/kkjy0519/bouncycastle/tree/Member_2/SSH%20Image/SSH-1.png)
![SSH-2](https://github.com/kkjy0519/bouncycastle/tree/Member_2/SSH%20Image/SSH-2.png)
![SSH-3](https://github.com/kkjy0519/bouncycastle/tree/Member_2/SSH%20Image/SSH-3.png)

