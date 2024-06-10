# LINUX



|-|-|
|-|-|
|ORACLE VM 설치 |[바로가기](https://phantom.tistory.com/6)|
|UBUNTU ISO DOWNLOAD|[바로가기](https://ubuntu.com/download/desktop)|
|UBUNTU VM 설치|[바로가기](https://mainia.tistory.com/2379)|
|UBUNTU NETWORK 설정|[바로가기](https://losskatsu.github.io/it-infra/virtualbox-ubuntu-ip/#3-%EA%B2%8C%EC%8A%A4%ED%8A%B8%EC%9A%B0%EB%B6%84%ED%88%AC-ip-%EC%84%A4%EC%A0%95)|
|UBUNTU SSH SETTING|[바로가기](https://jjeongil.tistory.com/1977)|



---
#
---
ROOT 암호 초기화
---
```
일반 유저로 로그인 -> sudo passwd root 
```

---
#
---

ORACLE VM NETWORK SETTING
---

```
1 다른 종류의 가상머신툴 네트워크 어댑터 종료 
  실행창 -> ncpa.cpl -> Vmware Network Adapter VMnet* 우클릭 -> 사용안함

2 우분투 가상머신 종료
  우측하단 X 클릭 -> 시스템 전원 끄기, 확인

3 우분투 VM 가상 어댑터 생성
  ORACLE VM VirtualBox 관리자 상단  '파일' -> 도구 -> 네트워크 관리자 -> 만들기 (VirtualBox Host-Only Ethernet Adapter #2 가 생성)
  -> IPv4 주소 : 192.168.10.1
  -> Ipv4 서브넷 마스크 : 255.255.255.0
  -> DHCP 서버탭 클릭 -> 서버 활성화 체크 -> 적용

4 우분투 가상머신 설정
   우분투 가상머신 클릭 -> 설정 -> 네트워크 -> 어댑터2 ->
    -> 다음에 연결됨 : 호스트 전용 어탭터
    -> 이름 : VirtualBox Host-Only Ethernet Adapter #2 선택
    -> 확인

5 우분투 가상머신 동작
  1) net-tool 설치
    바탕화면 우클릭 -> 터미널로 열기 -> sudo apt install net-tools -> ifconfig

6 고정 IP 
  시작 -> 로그인 -> 우측상단 전원 버튼 클릭 -> 설정 ->  네트워크 -> 이더넷(enp0s8)설정 -> IPv4 -> 수동
  주소 : 192.168.10.10
  네트마스크 : 255.255.255.0
  게이트웨이 : 192.168.10.1
  네임서버 : 168.126.63.1
  -> 적용

```





