# 내 컴퓨터에 개발자용 '작업실' 꾸미기

## 프로젝트 소개
macOS 개발 환경(터미널/Docker/Git)을 단계별로 구축하는 과제.

## 진행 단계
- [x] 1단계: 터미널 기본 조작 및 권한 실습 (파일+디렉토리)
- [x] 2단계: Docker 설치 및 기본 점검
- [x] 3단계: Docker 기본 운영 (이미지/컨테이너/로그/리소스)
- [x] 4단계: 커스텀 이미지 제작 + 포트 매핑
- [x] 5단계: 바인드 마운트 반영 + 볼륨 영속성 검증
- [ ] 6단계: Git 설정 및 GitHub/VSCode 연동
- [ ] 7단계: 보안/개인정보 마스킹 최종 점검 + 기술 문서 정리

## 검증 방법
| 항목 | 명령어 | 결과 위치 |
|---|---|---|
| 터미널 기본 조작 | pwd, ls -al, mkdir, cp, mv, rm | logs/step_1_terminal_permission_log.txt |
| 파일 권한 변경 | chmod 000/644 test.txt | logs/step_1_terminal_permission_log.txt |
| 디렉토리 권한 변경 | chmod ... (디렉토리) | logs/step_1_permission_supplement_log.txt |
| Docker 버전/데몬 확인 | docker --version, docker info | logs/step_2_docker_setup_log.txt, logs/step_2_docker_version_supplement_log.txt |
| Docker 기본 운영 | docker images/ps/logs/stats | logs/step_3_docker_basic_ops_log.txt |
| 커스텀 이미지 빌드/실행 | docker build, docker run -p | logs/step_4_docker_custom_image_log.txt |
| 포트 매핑 접속 | curl http://localhost:8080 | logs/step_4_docker_custom_image_log.txt |
| 바인드 마운트/볼륨 영속성 | (진행 예정) | logs/step_5_... |
| Git 설정/연동 | git config --list | logs/step_6_... |

## 트러블슈팅
### 1) docker build 시 데몬 연결 실패
- 문제: `docker build -t my_web:1.0 .` 실행 시 "Cannot connect to the Docker daemon" 에y러
- 원인 가설: OrbStack 데몬이 완전히 기동되기 전에 명령을 실행함
- 확인: `dockers info`로 데몬 상태 재확인 → 정상 응답 확인
- 해결: 잠시 후 `docker build` 재실행 → 정상 빌드 성공
- (출처: logs/step_4_docker_custom_image_log.txt)

### 2) 디렉토리 권한 변경(chmod 700) 결과 캡처 실패
- 문제: chmod 700 perm_test_dir 실행 직후 `zsh: unknown file attribute: 7` 에러 발생,
  로그 전체에서 700 상태의 ls -ld 출력이 확인되지 않음 (시작 755 → 끝 755만 확인)
- 원인 가설: 여러 줄을 한 번에 붙여넣는 과정에서 명령 뒤 `# 주석` 처리 중 공백이 소실되며
  괄호가 파일명에 바로 붙어(`확인(700`) zsh가 이를 글롭 한정자로 오인, 해당 ls 명령이
  파싱 에러로 실행되지 못함 (인터랙티브 zsh는 기본적으로 # 주석 미지원이라 더 취약)
- 확인: 로그 상 unknown file attribute 에러 위치와 700 상태 ls 출력 부재를 대조
- 해결/대안: ~/.zshrc에 `setopt interactivecomments` 추가 + 명령은 주석 없이 한 줄씩 실행.
  perm_test_dir 재사용해 ls -ld → chmod 700 → ls -ld(700 확인) → chmod 755를
  짧게 재실행하여 700 상태를 별도로 캡처 예정
- (출처: logs/step_1_permission_supplement_log.txt)