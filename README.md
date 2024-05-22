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

