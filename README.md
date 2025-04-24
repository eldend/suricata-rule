# Suricata Rule Test Guide

이 프로젝트는 Suricata를 사용하여 특정 웹사이트 접속을 탐지하는 테스트용 환경을 구성한 것입니다. `test.rules` 파일에는 HTTP 및 HTTPS 트래픽에 대한 룰이 포함되어 있습니다.

---

## 📁 파일 구조

- `test.rules` : Suricata에서 사용할 20개의 탐지 룰 파일 (HTTP 10개 + HTTPS 10개)
- `fast.log` : Suricata가 탐지 결과를 기록하는 로그 파일 (기본: /var/log/suricata/fast.log)

---

## 🧪 테스트 방법

### 1. Suricata 설치

```bash
# Suricata Rule Test Guide

이 프로젝트는 Suricata를 사용하여 특정 웹사이트 접속을 탐지하는 테스트용 환경을 구성한 것입니다. `test.rules` 파일에는 HTTP 및 HTTPS 트래픽에 대한 룰이 포함되어 있습니다.

---

## 📁 파일 구조

- `test.rules` : Suricata에서 사용할 20개의 탐지 룰 파일 (HTTP 10개 + HTTPS 10개)
- `fast.log` : Suricata가 탐지 결과를 기록하는 로그 파일 (기본: /var/log/suricata/fast.log)

---

## 🧪 테스트 방법

### 1. Suricata 설치

```bash
sudo apt install suricata
suricata


```



### 2. Suricata 실행

```bash
suricata -s test.rules -i eth0
```

> `eth0`는 현재 사용 중인 네트워크 인터페이스로 변경 필요

### 3. 테스트 트래픽 생성

```bash
curl http://naver.com
curl https://google.com
...
```

### 4. 로그 확인

```bash
tail -f /var/log/suricata/fast.log
```
