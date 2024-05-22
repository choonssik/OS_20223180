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

TOP 정보 시스템 내용
---

**07:18:34** : 현재 서버의 시간<br>
**up 5 min** : uptime(켜져있는시간)<br>
**0 users** : 총 사용자 수<br>
**load average** : 현재 시스템이 얼마나 일을 하고 있는지 1분, 5분, 15분 단위 동안의 실행/대기 중인 프로세스 수를 나타내는 평균 시스템 부하량 평균값<br>
**Tasks** : 현재 프로세스들의 상태를 출력<br>
프로세스 개수와 running, sleep, stopped, zombie 상태를 나타낸다.<br>

* CPU 사용량
---
**us** (User CPU Time) : 사용자 모드에서 실행되는 프로세스가 사용하는 CPU 시간의 비율<br>
**sy** (System CPU Time) : 커널 모드에서 실행되는 프로세스가 사용하는 CPU 시간의 비율<br>
**ni** (Nice CPU Time) : 프로세스 우선순위 설정에 사용되는 CPU 사용율<br>
**id** (Idle CPU Time) : 사용하지 않는 (유휴상태) CPU 비율<br>
**wa** (I/O Wait Time) : I/O 대기 상태의 CPU 사용율<br>
**hi**(Hardware Interrupt Time) : 하드웨어 인터럽트에 사용되는 CPU 사용율<br>
**si**(Software Interrupt Time) : 소프트웨어 인터럽트에 사용되는 CPU  사용율<br>
**st** (Steal Time) : 가상화 환경에서, CPU가 다른 가상 머신의 작업을 수행하느라 현재 가상 머신이 기다리는 시간의 비율<br>

* 메모리 사용량
---
MiB Mem 은 RAM의 정보를 출력한다. MiB Swap은 디스크를 메모리처럼 사용하는 Swap 메모리 영역의 정보를 출력한다. 
total은 총 메모리 양, free는 사용가능한 메모리 양, used는 사용 중인 메모리 양이다. 
buff/cache는 커널 버퍼와 디스크의 페이지 캐시에 사용되는 메모리 양이다. 즉, I/O에 사용되는 버퍼 메모리이다.

* 상세 정보
---
**PID** : 프로세스 ID<br>
**USER** : 프로세스를 시작한 유효한 사용자의  ID<br>
**PR** : Scheduling Prority, 즉 작업의 우선순위<br>
**NI** : 우선순위에 영향을 주는 값으로 음수이면 우선순위가 높고 양수라면 낮음<br>
**VIRT** : 가상메모리(Virtual Memory) 크기, 프로세스가 사용하고 있는 가상메모리 용량<br>
**RES** : 상주메모리(Resident Memory)  크기, 프로세스가 실제로 사용하고 있는 물리 메모리 용량<br>
**SHR** : 공유메모리(Shared Memory) 크기, 다른 프로세스와 공유하고 있는 공유 메모리 용량<br>
**S** : 프로세스의 상태<br>
**R** : Runnung<br>
**S** : Sleeping<br>
**I** : Idle<br>
**D** : Uninterruptable Sleep<br>
**T** : 작업 제어 신호에 의해 중지됨<br>
**t** : Trace 중 디버거에 의해 중지됨<br>
**Z** : Zombie<br>
**%CPU** : CPU 사용량<br> 
**%MEM** : 메모리 사용량. 현재 사용한 실제 메모리 양<br>
**TIME+** : 프로세스가 사용한 CPU 시간. 작업이 시작된 이후 사용한 총 CPU 시간<br>
**COMMAND** : 명령어 이름. 작업을 시작할 때 사용되는 명령어 라인 혹은 프로그램의 이름을 표시<br>

사용 옵션
---
top 명령 실행시 추가할 수 있는 옵션

    (top) -d [sec]: 설정된 초단위로 Refresh
    (top) -c      : command뒤에 인자값 표시

top 명령 실행 후 사용할 수 있는 옵션

    shift + t     : 실행된 시간이 큰 순서로 정렬
    shift + m     : 메모리 사용량이 큰 순서로 정렬
    shift + p     : cpu 사용량이 큰 순서로 정렬
    k             : Process 종료
       o k 입력 후 종료할 PID를 입력한다
       o signal을 입력하라 표시되면 9를 넣어준다
    c             : 명령 인자 표시 / 비표시
    l(소 문자엘)  : uptime line(첫번째 행)을 표시 / 비표시
    space bar     : Refresh
    u             : 입력한 유저 소유의 Process만 표시
       o which user: 와 같이 유저를 입력하라 표시될때 User를 입력
       o blank(공백) 입력시 모두 표시
    shift + b     : 상단의 uptime 및 기타 정보값을 블락선택해 표시
    f             : 화면에 표시될 프로세스 관련 항목 설정
    
---
### ps
   Process State의 약자로 현재 실행 중인 프로세스와 상태를 출력하는 명령어
리눅스에서는 여러 개의 프로세스가 동시에 실행되기 때문에 현재 실행 중인 프로세스의 정보를 얻기 위해 사용된다. 프로세스 중에서 cpu, 메모리 등등을 많이 점유하고 있거나, 지나치게 많은 자식 프로세스를 생성하는 등등에 시스템에 속도가 느려지는 경우 ps명령어로 분석하여 시스템 오류를 감지할 수 있다.

##### 사용법
      ps
![image](https://github.com/choonssik/OS_20223180/assets/166361178/494fbe65-2438-472f-b04c-736f7ffbce46)


ps 정보 시스템 내용
---

**UID** (System V) : 프로세스 소유자의 이름<br>
**PID** : 프로세스의 식별 번호<br>
**PPID** : 부모 프로세스의 PID<br>
**C** : CPU 사용률<br>
**TTY** : 프로세스와 연결된 터미널<br>
**TIME** : 총 CPU 사용 시간<br>
**STIME** : 프로세스가 시작된 시간 혹은 날짜<br>

사용 옵션
---
    -A           : 모든 프로세스를 출력
     a (BSD)      : 터미널과 연관된 프로세스를 출력, x 옵션과 같이 사용하여 모든 프로세스를 출력할 때 사용
    -a           : 세션 리더를 제외하고 데몬 프로세스처럼 터미널에 종속되지 않은 모든 프로세스를 출력
    -e           : 커널 프로세스를 제외한 모든 프로세스를 출력
    -f           : 출력을 풀 포맷으로 표기 (유닉스 스타일)
                   UID, PID , PPID 등이 함께 표시
    -l (System V):
    l (BSD)      : 출력을 긴 포맷으로 표기
                   프로세스의 정보를 길게 보여주는 옵션으로 우선순위와 관련된 PRI 값과 NI 값을 확인
    -o           : 출력 포맷을 지정
    -M           : 64비트 프로세스들을 출력
    -m           : 프로세스뿐만 아니라 커널 스레드도 출력
    -p           : 특정 PID를 지정하여 출력
    -r           : 현재 실행 중인 프로세스 출력
    u (BSD)      : 프로세스의 소유자를 기준으로 출력
    -u [사용자]  : 특정 사용자의 프로세스 정보를 출력, 사용자를 지정하지 않는다면 현재 사                    용자 기준으로 출력
    x (BSD)      : 데몬 프로세스처럼 터미널에 종속되지 않은 프로세스를 출력
    -x           : 로그인 상태에 있는 동안 아직 완료되지 않은 프로세스를 출력.
