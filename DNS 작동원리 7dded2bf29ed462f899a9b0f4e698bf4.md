# DNS 작동원리

목차

- [DNS에 대해](DNS%20%E1%84%8C%E1%85%A1%E1%86%A8%E1%84%83%E1%85%A9%E1%86%BC%E1%84%8B%E1%85%AF%E1%86%AB%E1%84%85%E1%85%B5%207dded2bf29ed462f899a9b0f4e698bf4.md)
    
    [DNS 구조](DNS%20%E1%84%8C%E1%85%A1%E1%86%A8%E1%84%83%E1%85%A9%E1%86%BC%E1%84%8B%E1%85%AF%E1%86%AB%E1%84%85%E1%85%B5%207dded2bf29ed462f899a9b0f4e698bf4.md) 
    

[DNS 등록](DNS%20%E1%84%8C%E1%85%A1%E1%86%A8%E1%84%83%E1%85%A9%E1%86%BC%E1%84%8B%E1%85%AF%E1%86%AB%E1%84%85%E1%85%B5%207dded2bf29ed462f899a9b0f4e698bf4.md) 

- [DNS 사용](DNS%20%E1%84%8C%E1%85%A1%E1%86%A8%E1%84%83%E1%85%A9%E1%86%BC%E1%84%8B%E1%85%AF%E1%86%AB%E1%84%85%E1%85%B5%207dded2bf29ed462f899a9b0f4e698bf4.md)
    
    [역할 정리](DNS%20%E1%84%8C%E1%85%A1%E1%86%A8%E1%84%83%E1%85%A9%E1%86%BC%E1%84%8B%E1%85%AF%E1%86%AB%E1%84%85%E1%85%B5%207dded2bf29ed462f899a9b0f4e698bf4.md) 
    
    [동작 순서](DNS%20%E1%84%8C%E1%85%A1%E1%86%A8%E1%84%83%E1%85%A9%E1%86%BC%E1%84%8B%E1%85%AF%E1%86%AB%E1%84%85%E1%85%B5%207dded2bf29ed462f899a9b0f4e698bf4.md) 
    

<aside>
📌 메모

- 정보의 빈틈이 있습니다. 주의하세요.
</aside>

![Untitled](DNS%20%E1%84%8C%E1%85%A1%E1%86%A8%E1%84%83%E1%85%A9%E1%86%BC%E1%84%8B%E1%85%AF%E1%86%AB%E1%84%85%E1%85%B5%207dded2bf29ed462f899a9b0f4e698bf4/Untitled.png)

---

# DNS에 대해

DNS(Domain Name System)은 접속하려는 페이지의 html파일을 불러오기 위해 해당 파일이 있는 서버의 주소인 IP로 접속할 때, 매번 IP주소로 접속하려면 번거롭고, 외우기 힘들기 때문에 외우기 쉬운 단어로 이루어진 문자로 대체하는 방법.

## DNS 구조

### DNS구조가 생긴 이유

1. DNS가 잘 작동하기 위해서는 “’www.xxxxx.com’도메인의 IP는 ‘xxx.xxx.xxx.xxx’이다.”라는 것을 저장해줄 공간이 필요하다.
2. 첫번째로, 하나의 서버에 모든 이 정보를 저장하면, 전세계의 모든 컴퓨터의 트래픽을 감당할 수 있어야 한다. 그렇기 때문에 불가능. 두번째로, 여러 개의 서버로 정보를 분할해서 저장한다면, 어떤 도메인에 관한 정보는 여기 있고, 어떤 것은 여기 있고 등에 대한 정보도 공유되어야 하기 때문에 분할 된 서버가 서로 어떤 정보가 어디 있는지 알아야 한다는 단점이 있다.
3. 그래서 DNS는 조직도처럼 계층화된 구조를 갖는다.

![Untitled](DNS%20%E1%84%8C%E1%85%A1%E1%86%A8%E1%84%83%E1%85%A9%E1%86%BC%E1%84%8B%E1%85%AF%E1%86%AB%E1%84%85%E1%85%B5%207dded2bf29ed462f899a9b0f4e698bf4/Untitled%201.png)

최상단에는 ICANN이라는 모든 도메인을 관리하는 단체 그 밑에는 일반 사용자와 국가 사용자를 구분, 또, 용도에 대한 구분이 있다. 자세한 것은 밑에서 다룸. (ICANN 밑에 TLD가 있다만 알아두자.)

---

# DNS 등록

![Untitled](DNS%20%E1%84%8C%E1%85%A1%E1%86%A8%E1%84%83%E1%85%A9%E1%86%BC%E1%84%8B%E1%85%AF%E1%86%AB%E1%84%85%E1%85%B5%207dded2bf29ed462f899a9b0f4e698bf4/Untitled%202.png)

1. 등록자가 사용할 도메인을 정함 ex) www.back-end.com
2. 등록자가 등록대행자에 도메인을 등록함. 
3. 등록대행자가 바로 등록소에 도메인을 정보를 등록해주는게 아니라, Authoritative server 혹은 Second-level domain(SLD)라는 서버를 만들어서 등록해줌.(등록소(TLD)에서 도메인 정보를 찾기위해 하위 계층을 두기 위한 것.) 주로 등록대행자가 만들어서 등록해주지만, 개인이나 단체가 따로 서버를 만들기도 함. 

---

# DNS 사용

![Untitled](DNS%20%E1%84%8C%E1%85%A1%E1%86%A8%E1%84%83%E1%85%A9%E1%86%BC%E1%84%8B%E1%85%AF%E1%86%AB%E1%84%85%E1%85%B5%207dded2bf29ed462f899a9b0f4e698bf4/Untitled%203.png)

## 역할 정리

**Local DNS** 

클라이언트 요청에의해 도메인에 대응하는 IP주소찾기 위해 먼저, Local DNS 서버 캐시에서 찾고 있으면 클라이언트에게 IP반환 없으면, 네임 서버에 요청을 하고 응답을 받아서 클라이언트에게 반환하는 역할. (KT, SKT같은 회사들이 여기에 해당 함.)

**Root DNS**

DNS 최고 기관인 ICANN에서 관리하는 서버로 네임 서버 계층구조에서 가장 높다. Local DNS요청을 TLD로 중개해줌.(도메인의 가장 뒤에 붙은 .com, .net부분을 보고 해당 부분의 IP를 관리하는 TLD로 보냄.)

**TLD**

Top-level DNS의 약자로, 도메인의 중간부분. 예를 들어 www.naver.com의 naver부분을 보고 해당 부분의 IP가 저장된 Second-level DNS(SLD) 혹은 Authoritative server로 중개함.

**SLD, Authoritative server**

www.naver.com에서 www에 해당하는 부분으로 www가아닌 [blog.naver.com](http://blog.naver.com) , [cafe.naver.com](http://cafe.naver.com)처럼 앞에 붙은 부분이 다른데 이 부분에 대한 IP를 저장하고 있는 곳이다.

그림에서는 com DNS가 TLD, [naver.com](http://naver.com) DNS가 SLD다.

---

## 동작 순서

예시로 도메인은 “www.google.com” IP는 “111.111.111.111”로 함.

1. 클라이언트에서 주소창에 “www.google.com”(도메인)을 검색함.
2. 브라우저 캐시, OS 캐시, 라우터 캐시에 해당 도메인에 대한 IP가 있는지 확인하고 없으면, Local DNS에 요청.
3. Local DNS에서도 캐시를 확인하고 해당 정보가 없으면, Root DNS에 요청을 중개.
4. Root DNS에서 정보가 없으면, .com을 관리하는 TLD로 요청을 중개.
5. TLD에서 해당 정보가 없으면, google.com을 관리하는 SLD로 중개.
6. SLD에서 www이 붙은 google.com을 찾고 해당 IP를 Local DNS로 전달.
7. Local DNS에서 “111.111.111.111”을 브라우저에 전달.
8. 브라우저가 “111.111.111.111”로 접속해서 html을 받아옴.
9. 구글 열림.

여기서 중개한다는 표현은 예를 들어, Root DNS에서 TLD로 중개한다는 것은 Root DNS에서 바로 TLD로 넘어가는게 아니고, Root DNS에서 TLD주소를 Local DNS로 넘겨주고, local DNS에서 TLD로 요청하는 것이다.