# SSL Certificate
## What is TLS

**TLS**는 **SSL** 기반이며, SSLv3의 알려진 취약성에 대응한 대체품으로서 개발되었다.

SSL은 일반적으로 사용되는 용어이며, 요즘에는 일반적으로 TLS를 나타낸다.

## Security Provided

SSL/TLS는 데이터 암호화, 데이터 무결성 및 인증을 제공한다.

즉, SSL/TLS를 사용하는 경우 다음을 확신할 수 있다.

- 아무도 메시지를 읽지 않았다.
- 아무도 메시지를 변경하지 않았다.
- 의도한 사람(서버)과 통신 중이다.

두 사람 간에 메시지를 보낼 때 해결해야 할 두 문제가 있다.

- 아무도 메시지를 읽지 않았다는 걸 어떻게 알까?
- 아무도 메시지를 변경하지 않았다는 걸 어떻게 알까?

이러한 문제의 해결 방법은 다음과 같다.

- **암호화**
    - 이렇게 하면 내용을 읽을 수 없으므로 메시지를 보는 모든 사람이 이해할 수 없다.
- **서명**
    - 메시지를 보낸 사람이 본인이며, 메시지가 변경되지 않았음을 수신인이 확신할 수 있다.

이 두 프로세스 모두 키를 사용해야 한다.

이러한 키는 단순한 숫자(일반적으로 128비트인 경우)로, 메시지를 암호화하거나 서명하기 위해 일반적으로 알고리즘(예: RSA)으로 알려진 특정 방법을 사용하여 메시지와 결합된다.

## Symmetrical Keys and Public and Private Keys

오늘날 사용되는 거의 모든 암호화 방법은 **공개키** 및 **개인키**를 사용한다.
이들은 이전의 대칭키 배열보다 훨씬 더 안전한 것으로 간주된다.

대칭키를 사용하면 메시지를 암호화하거나 서명하는 데 키가 사용되며, 메시지의 암호를 해독하는 데에도 **동일한 키**가 사용된다.

이는 우리가 일상 생활에서 다루는 열쇠와 같다.

이러한 유형의 키 배열에서 문제는 키를 잃어버린 경우 키를 발견한 모든 사용자가 문을 열 수 있다는 것이다.

**공개키와 개인키**를 사용하면 수학적으로 관련이 있지만 (**키 쌍**으로 속함) 서로 다른 두 개의 키가 사용된다.

이는 **공개키로 암호화**된 메시지를 **동일한 공개키로 해독할 수 없음**을 의미한다.

메시지의 암호를 해독하려면 **개인키**가 필요하다.

만약 이러한 유형의 키 배열이 자동차와 함께 사용되었다면, 차를 잠그고, 같은 열쇠로는 차의 잠금을 **해제할 수 없기 때문**에 열쇠를 자물쇠에 넣어둘 수 있다.

이러한 유형의 키 배열은 매우 안전하며, 모든 최신 암호화/서명 시스템에 사용된다.

## Keys and SSL Certificates

SSL/TLS는 데이터 암호화 및 데이터 무결성을 위해 **공개키 및 개인키** 시스템을 사용한다.

공개키는 누구나 사용할 수 있으므로 공개(public)라는 용어가 붙는다.
이 때문에 특히 다음과 같은 신뢰 문제가 발생한다. 특정 공개키가 자신이 주장하는 개인/기업에 속한다는 것을 어떻게 알 수 있는가?

예를 들어, 은행에 속해 있다고 주장하는 키를 받게 되었을 때, 그것이 당신의 은행에 속한다는 것을 어떻게 알 수 있을까?

정답은 **디지털 인증서**를 사용하는 것이다.

인증서는 일상 생활에서 여권이 하는 것과 같은 목적을 제공한다.

여권은 사진과 사람 사이를 연결을 설정했으며, 해당 연결은 **신뢰할 수 있는 기관**(여권 사무소)에 의해 확인되었다.

디지철 인증서는 신뢰할 수 있는 제3자(**인증 기관**)에 의해 확인(**서명**)된 **공개키**와 엔티티(비즈니스, 도메인 이름 등) 사이의 링크를 제공한다.

**디지털 인증서**를 사용하면 **신뢰할 수 있는 공개 암호화 키**를 편리하게 배포할 수 있다.

## Obtaining a Digital Certificate



## Reference
- http://www.steves-internet-guide.com/ssl-certificates-explained/