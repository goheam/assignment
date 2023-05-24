# top
+ 요약 - 시스템 프로세스/메모리 사용 현황을 실시간으로 출력한다.
+ 경로 - /usr/bin/top
+ top 명령어는 시스템의 프로세스/메모리 사용 상태를 5초의 간격으로 업데이트하여 출력한다. 
+ 화면에 출력되는 기본값은 현재시간, 시스템 업데이트(1) 시간, 시스템에 로그인한 사용자 수, 지난 1분, 지난 5분, 지난 15분간의 시스템 평균 부하를 출력한다.
+  top 명령어를 실행한 후 초기 화면에서  키를 입력하면 사용할 수 있는 단축키 목록을 확인할 수 있다.
---
**` $ top [옵션] `**
+ `$ top` 옵션 없이 명령어를 실행하면 interval간격(기본 3초)으로 화면을 갱신하며 정보를 보여준다.
![tptop](https://github.com/goheam/assignment/assets/133829880/7c91f024-bef3-47dc-91fa-6be9c27fc6b1)

1. -b : 배치모드로 정보를 출력한다. 실시간 상화 대화형모드로 정보를 화면에 일렬로 출력한다.
2. -d delay : 지정한 시간(delay 초)의 간격으로 정보를 업데이트하여 출력한다.
3. -n num : 지정한 시간(num)만큼 업데이트 정보를 출력한다.
4. -q : 시간의 간격 없이 계속하여 업데이트 정보를 출력한다.
---
**top 실행 후 명령어**
+ shift + p : CPU 사용률 내림차순
+ shift + m : 메모리 사용률 내림차순
+ shift + t : 프로세스가 돌아가고 있는 시간 순
+ k : kill, k 입력 후 PID 번호 작성, signal은 9
+ f : sort field 선택 화면 -> q 누르면 RES순으로 정렬
+ a : 메모리 사용량에 따라 정렬
+ b : Batch 모드로 작동
+ 1 : CPU Core별로 사용량 보여줌


# ps
+ 요약 - 프로세스의 현재 상태를 출력한다.
+ 경로 - /bin/ps
+ ps는 'process status'의 약자이다.
+ ps 명령어는 프로세스의 현재 상태를 출력한다. 
+ ps로 현재 사용하는 프로세스의 상태를 살펴보자
+ PID, TTY, TIME, CMD 헤더의 필드와 내용을 출력한다.

![ka38_241_i1](https://github.com/goheam/assignment/assets/133829880/de2069b6-c6ec-4200-8cd0-954756df88e2)
---
**` $ps [옵션] `**

**전체 프로세스와 관련된 옵션**
+ -A : 모든 프로세스를 출력한다.
+ -N : -A 옵션과 비슷하나 ps 프로세스를 제외하고 출력한다.
+ -a : 세션 리더 및 터미널에 속하지 않는 프로세스를 제외하고 출력한다.
+ -d : 세션 리더를 제외한 모든 프로세스를 출력한다.
+ -e : 커널 프로세스를 제외한 모든 프로세스를 출력한다.

+ T : 현재 터미널에서의 모든 프로세스를 출력한다.
+ a : 현재 터미널의 사용자 고유 프로세스를 출력한다.
+ r : 현재 실행 중인 프로세스를 출력한다.
+ x : 터미널이 없는 프로세스를 출력한다.
+  --deselect : -N 옵션과 같다.

`$ ps -p 1` : 프로세스 번호가 1인 프로세스를 출력

`$ ps -u seek` : 계정이 seek인 프로세스들을 출력

`$ ps -ef | more` : 모든 프로세스를 풀 포맷으로 출력, more 명령어를 이용하여 페이지 단위로 출력

`$ ps -ef | grep seek` : 모든 프로세스를 풀 포맷으로 출력한 목록에서 grep을 이용해 seek이 포함된 행(Row)을 출력

----
+ u 옵션은 사용자의 프로세스를, -l 옵션은 자세한 정보를 출력한다.

![ka38_241_i2](https://github.com/goheam/assignment/assets/133829880/eab54e46-c31e-4ced-a94b-0c81799fad32)

+ 시스템의 모든 프로세스를 확인할 경우 aux 옵션을 사용한다.

![image](https://github.com/goheam/assignment/assets/133829880/56d16835-1d57-4c41-9feb-e7bd473c69ba)

+ 자주 사용하는 ps 옵션의 조합이다. 표준 문장으로 시스템의 모든 프로세스를 출력한다.

![image](https://github.com/goheam/assignment/assets/133829880/4ec40b99-f295-472a-97be-27497eff383f)

+ BSD 문장으로 시스템의 모든 프로세스를 출력한다.

![image](https://github.com/goheam/assignment/assets/133829880/fed823af-9a9f-4cf1-b84d-4831f059489e)

+ 프로세스 트리를 출력할 수 있다.

![image](https://github.com/goheam/assignment/assets/133829880/468e96f9-c8a1-45ef-9216-f101747f63be)


# jobs
+ 요약 - 현재 세션의 작업 상태를 출력한다.
+ 경로 - 내부 명령어
+ jobs는 작업이 중지된 상태, 백그라운드로 진행 중인 작업 상태, 변경되었지만 보고되지 않은 상태 등을 표시한다.
+ jobs 명령어는 현재 쉘 프로세스의 자식 백그라우드 프로세스들을 보여준다고 생각하면 된다.
+ 현재 환경의 작업 상태를 아래와 같이 확인할 수 있다.

![image](https://github.com/goheam/assignment/assets/133829880/7c81c7d3-3c1e-4f30-a1b5-1680d60acf9c)

+ -l 옵션은 state 필드 앞에 프로세스 ID를 출력한다.

![image](https://github.com/goheam/assignment/assets/133829880/937a570c-e4b5-4328-b990-09307e5bf4d4)
---
**`$ jobs [옵션] [jobID...]`**

**`$ jobs -x command [args]`**
+ -l : 프로세스 그룹 ID를 state 필드 앞에 출력한다.
+ -n : 프로세스 그룹 중에 대표 프로세스 ID를 출력한다.
+ -p : 각 프로세스 ID에 대해 한 행씩 출력한다.
+ command : 지정한 명령어를 실행한다.
---
**jobs로 출력되는 백그라운드 작업의 상태값**
 | Situation | Explanation |.
 | -------- | -------- | ------- |
 | Running | 작업이 일시 중단되지 않았고 종료하지 않고 계속 진행 중임을 뜻한다.  |.
 | Done | 작업이 완료되어 0을 반환하고 종료했음을 뜻한다.                        |.
 | Done (code) | 작업이 정상적으로 완료했으며, 0이 아닌 코드를 반환했음을 뜻한다.|.
 | Stopped | 작업이 일시 중단됨을 뜻한다.                                       |.
 | Stopped (SIGTSTP) | SIGTSTP 신호가 작업을 일시 중단했음을 뜻한다.            |.
 | Stopped (SIGSTOP) | SIGSTOP 신호가 일시 중단했음을 뜻한다.                   |.
 | Stopped (SIGTTIN) | SIGTTIN 신호가 작업을 일시 중단했음을 뜻한다.            |.
 | Stopped (SIGTTOU) | SIGTTOU 신호가 작업을 일시 중단했음을 뜻한다.            |.
 ---
![image](https://github.com/goheam/assignment/assets/133829880/9bcba09f-0b4e-4275-8365-4d04ec26bd01)
 + v로 시작하는 모든 프로세스 ID를 확인할 수 있다.

# kill
+ 요약 - 프로세스를 종료한다.
+ 경로 - /bin/kill
+ kill 명령어는 프로세스에 종료 시그널을 보낸다. 
+ 시스템에 얘기치 않은 문제가 생긴 프로세스를 종료시킬 수 있다. 
+ 만약 kill 명령으로 종료되지 않는 프로세스는 -9 옵션을 사용해서 강제로 종료하면 된다.
+ 아래와 같이 ps 명령어로 sshd 프로세스를 확인할 수 있다.

![image](https://github.com/goheam/assignment/assets/133829880/d80dba04-44b7-47f6-8a2f-35c886b63d21)
---
**`$kill [-s시그널][-a]pid...`**

**`$kill -l [시그널]`**
+ pid ··· : 종료시킬 프로세스 ID나 프로세스 이름을 지정한다.
+ -s : 전달할 시그널의 종류를 지정한다. 여기에는 시그널 이름이나 번호를 써준다.
+ -l : 시그널로 사용할 수 있는 시그널 이름들을 보여준다. 이것은 /usr/include/linux/signal.h 파일에서도 알 수 있다.
+ -1, : -HUP 프로세스를 재활성화한다.
+ -9 : 프로세스를 강제로 종료시킨다.
---
| Root | USER | 프로세스의 사용자 |
| ------ |------| -------|
| 2518 | PID | 프로세스 ID
| 0.0 | %CPU | 마지막 1분 동안 프로세스가 사용한 CPU 점유율
| 0.1 | %MEM | 마지막 1분 동안 프로세스가 사용한 메모리의 점유율
| 7084 | VSZ | 가상메모리에 있는 프로세스의 KB 단위 크기
| 1076 | RSS | 프로세스의 실제 메모리의 크기로 KB 단위
| ? | TTY | 연결되어 있는 터미널
| Ss | STAT | 실행되고 있는 프로세스 상태
| Jun07 | START | 프로세스가 시작된 날짜
| 0:00 | TIME | 프로세스가 소비한 총 시간
| /usr/sbin/sshd | COMMAND | 사용자가 실행한 명령 이름

![image](https://github.com/goheam/assignment/assets/133829880/fd3f361e-0c37-42b3-a016-8c208433308c)
+ ps 명령으로 확인한 PID를 이용하면 원하는 프로세스를 종료시킬 수 있다.

![image](https://github.com/goheam/assignment/assets/133829880/0432bb2f-b23a-4f38-9495-64f566234ad9)
+ kill 명령으로 종료되지 않으면 -9 옵션으로 강제 종료하자.

![image](https://github.com/goheam/assignment/assets/133829880/5d7b1443-a902-4a4e-af32-883560cfcc3f)
+ kill -HUP pid 명령을 이용하면 프로세스를 종료 후 다시 재실행한다.

*만일 kill -9 1 명령을 수행한다면 시스템이 다운될 것이다. PID 1은 init을 의미한다. 그러므로 이는 사용하지 말자.*
