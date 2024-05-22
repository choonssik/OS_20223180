# OS_20223180
오픈소스개론sw

## 명령어 조사하기
1. top
2. ps
3. jobs
4. kill

### top
    - Linux에서 실행 중인 프로세스의 실시간을 표시하고 커널 관리 작업을 표시한다.
이 명령어는 CPU 및 메모리 사용량을 포함한 리소스 사용량을 보여주는 시스템 정보 요약을 제공한다.
윈도우의 작업관리자랑 비슷하다.

##### 사용법
      top
![image](https://github.com/choonssik/OS_20223180/assets/166361178/ec61d844-5b36-40a6-bbb1-f0686cc7d654)

* TOP 정보 시스템 내용<br>
07:18:34 : 현재 서버의 시간<br>
up 5 min : uptime(켜져있는시간)<br>
0 users : 총 사용자 수<br>
load average : 현재 시스템이 얼마나 일을 하고 있는지 1분, 5분, 15분 단위 동안의 실행/대기 중인 프로세스 수를 나타내는 평균 시스템 부하량 평균값<br>
Tasks : 현재 프로세스들의 상태를 출력<br>
프로세스 개수와 running, sleep, stopped, zombie 상태를 나타낸다.<br>


