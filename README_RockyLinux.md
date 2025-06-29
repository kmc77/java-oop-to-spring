# Rocky Linux 설치 및 MongoDB 실습 환경 구축 실습 (MacBook M1 기준)

## 1. 환경 및 버전 정보
- **호스트 PC:** MacBook Pro (Apple M1 실리콘 칩)
- **가상화 도구:** VMware Fusion (최신 버전 권장)
- **운영체제:** Rocky Linux 9.6 (ARM64)
- **이전 시도 버전:** Rocky Linux 8.10 (VMware Fusion 구버전과 호환 문제 발생)

## 2. 버전 변경 배경
- MacBook M1 실리콘 환경에서 VMware Fusion 구버전은 ARM64 가상화 지원이 불완전하여 Rocky Linux 8.10 설치 실패 사례 다수
- Rocky Linux 9.6은 ARM64 네이티브 빌드가 안정적이며 VMware Fusion, UTM 등 M1 기반 가상화 환경에서 정상 작동
- 실습 및 개발 효율을 위해 9.6 버전으로 변경하여 진행

## 3. Linux 설치 실습 개요
- VMware 환경에 Rocky Linux 9.6 설치
- 기본 명령어 및 vi/vim 편집기 사용법 실습
- Shell Script 기본 활용법 학습

## 4. MongoDB 설치 및 실습
- VMware 내 Rocky Linux 9.6 환경에서 직접 MongoDB 설치 복잡
- MacBook 로컬에서 Docker로 MongoDB 컨테이너 실행 후 VMware 내 가상 머신에서 접근 가능
- Docker 컨테이너 설치, 시작, 중지, 접속 명령어 실습

## 5. 주의사항 및 권한 문제
- VMware 가상 머신 내 일반 사용자(`min`)는 기본적으로 `sudo` 권한이 없을 수 있음
- 루트 계정 또는 `sudo` 권한 확보 필요 (루트 비밀번호 설정 및 사용자 sudoers 등록)
- Docker 사용 시 권한 문제 발생 시, `docker` 그룹에 사용자 추가 필요

## 6. 주요 명령어 및 참고 사항
- 루트 계정 전환
  ```bash
  su -
  # 또는
  sudo -i
  
docker stop <컨테이너명>
# 권한 문제 시
sudo docker stop <컨테이너명>

docker exec -it <컨테이너명> mongosh

```
