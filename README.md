## list
1. top
2. ps
3. jobs
4. kill


# top
**시스템의 실시간 프로세스 모니터링을 제공, 시스템 상태를 모니터링하거나 문제가 있는 프로세스를 식별하는데 유용.

* 현재 실행 중인 모든 프로세스의 목록 : 프로세스ID, 사용자, CPU사용량, 메모리 사용량 등이 표시된다.
* 시스템 전반적인 상태 : 전체 CPU사용량, 메모리 사용량, 스왑영역 사용량, 실행중인 프로세스 개수 등이 표시된다.
* 프로세스 정렬 및 제여 : 'top'화면에서 특정 컬럼을 기준으로 프로세스를 정렬할 수 있으며, 프로세스를 중지하거나 우선순위를 변경하는 등의 제어 동작을 수행 할 수 있다.

* top 명령어 실행 이미지

![Rinux command image - top](https://github.com/HaNSunG9/20233169-/assets/133843553/2519cb87-c17e-44ff-ba90-e52486f87176)

**프로세스 상태
|--------------------------------------------------------------------------|

|PID|프로세스 ID(PID)|
|:-------:|:-------------------------------------------------------------------------------------------:|
|USER|프로세스를 실행시킨 사용자 ID|
|PR|프로세스의 우선수위 (priority)|
|NI|NICE값, 일의 nice value값, 마이너스를 가지는 nice value는 우선순위가 높음|
|VIRT| 가상 메모리의 사용량(SWAP+RES)
|RES|현재 페이지, 프로세스가 상주하고 있는 크기(Resident Size)
|SHR| 분할된 페이지, 프로세스에 의해 사용된 메모리의 총합|
|S|프로세스의 상태 - S(sleeping), R(running), W(swapped out process), Z(zombies)|
|%CPU|프로세스가 사용하는 CPU의 사용률|
|%MEN|프로세스가 사용하는 메모리의 사용률|
|COMMAND|실행된 명령어|

**top [옵션]
|------------------------------------------------------------------------------------------------------|

|   옵션   |                                             설명                                            |
|:-------:|:------------------------------------------------------------------------------------------:|
|    -b    | 배치모드로 정보를 출력합니다. 실시간 상화 대화형모드로 정보를 화면에 일렬로 출력.        |
| -d delay | 지정한 시간(delay 초)의 간격으로 정보를 업데이트하여 출력합니다.                   |
|  -i idle | 토글값이 off일 때, idle프로세스나 좀비 프로세스 정보를 출력하지 않습니다.  |
|-n num| 지정한 시간(num)만큼 업데이트 정보를 출력합니다.|
|-p pid| 지정한 프로세스 ID(pid)의 정보만을 출력합니다.|
|-q| 시간의 간격 없이 계속하여 업데이트 정보를 출력합니다.|
|-s| 몇 개의 대화식 명령을 비활성화 합니다.|
|-S| ㅏ누적된 정보를 출력합니다.|

|**top 실행 후 단축키 명령어|
|----------------------------|

| 명령어 |설명|
|:-------:|:---------------------------------------------------------------------------------------------:|
|space| 정보를 업데이트합니다.|
|shift + p| CPU 사용률이 높은 프로세스 순서대로 표시|
|shift + m| 메모리 사용률이 높은 프로세스 순서대로 표시|
|shift + t| 프로세스가 돌아가고 있는 시간 순서대로 표시|
|k| 프로세스를 종료시킨다.|
|a| 메모리 사용량에 따라 정렬|
|b| Batch 모드|
|c| 명령행, 프로그램 이름 토글|
|h| 도움말|
|n or #| 출력할 프로세스의 수를 지정|
|s| 출력할 정보의 업데이트의 시간을 지정|
|p| top을 종료한다.|

## ps
현재 실행중인 프로세스 정보를 표시. 기본적으로는 현재 사용자와 관련된 프로세스만 표시한다.

* 프로세스 ID (PID): 각 프로세스의 고유 식별자입니다.
* 부모 프로세스 ID (PPID): 각 프로세스의 부모 프로세스를 나타냅니다.
* CPU 사용량, 메모리 사용량: 각 프로세스가 사용하는 CPU 및 메모리의 양을 나타냅니다.
* 실행 시간: 프로세스가 실행된 시간을 표시합니다.
* 프로세스 상태: 실행 중인 프로세스인지, 대기 중인 프로세스인지 등의 상태를 표시합니다.

* ps 명령어 실행 이미지

![Rinux command image - ps](https://github.com/HaNSunG9/20233169-/assets/133843553/eeb1041d-24a6-4464-9248-1ccd603a8c2a)

**ps 항목
|------------|

|항목|의미|
|:----------:|:----------------------------------------------------------------------------------------:|
|USER|BSD계열에서 나타나는 항목으로 프로세스 소유자의 이름|
|UID|SYSTEM V계열에서 나타나는 항목으로 프로세스 소유자의 이름|
|PID|프로세스의 식별번호|
|PPID|무모 프로세스 ID|
|%CPU|CPU사용 비율의 추정치(BSD)|
|%MEN|메모리의 사용 비율의 추정치 (BSD)|
|VSZ|K단위 또는 페이지 단위의 가상메모리 사용량|
|RSS|실제 메모리 사용량 (Resident Set Size)|
|TTY|프로세스와 연결된 터미널|
|S, STAT|현재 프로세스의 상태 코드(S : Sys V, STAT : BSD)|
|TIME|총 CPU사용시간|
|COMMAND|프로세스의 실행 명령행|
|STIME|프로세스가 시작된 시간 혹은 날짜|
|C, CP|짧은 기간 동안의 CPU사용률(C : Sys V, STAT : BSD|
|F|프로세스의 플래그|
|PRI|실제 실행 우선순위|
|NI|nice우선순위 번호|

**ps [옵션]
|-----------------|

|   옵션   |                                             설명                                            |
|:----------:|:----------------------------------------------------------------------------------------:|
|-A|모든 프로세스를 출력한다.|
|a (BSD계열)| 터미널과 연관된 프로세스를 출력하는 옵션이다. 보통 x옵션과 연계하여 모든 프로세스를 출력할떼 사용|
|-a| 세션 리더(일반적으로 로그인 셀)을 제외하고 데몬 프로세스처럼 터미널에 종속되지 않은 모든 프로세스를 출력|
|-e|커널 프로세스를 제외한 모든 프로세스를 출력|
|-f|풀 포맷으로 보여준다, 유닉스 스타일로 출력해주는 옵션으로 UID, PID, PPID등이 함께 표시된다.|
|-l(sys V) l (BSD계열)|긴 포맷으로 보여준다. 프로세스의 정보를 길게 보여주는 옵션으로 우선순위와 관련된 PRI와 NI값을 확인할 수 있다.|
|-o 값|출력 포맷을 지정하는 옵션으로 값으로는 pid, tty, time, cmd 등을 지정할 수 있다.|
|-M|64비트 프로세스들을 보여준다.|
|-m|프로세스들 뿐만 아니라 커널 스레드들도 보여준다.|
|-p|특정 PID를 지정할 때 사용합니다.|
|-r|현재 실행 중인 프로세서를 보여준다.|
|u (BSD계열)|프로세스의 소유자를 기준으로 출력한다.(ps as만 하면 USER 기준의 정보가 안뜸, 따라서 aus이렇게 같이 써준다.|
|-u|특정 사용자의 프로세스 정보를 확인할 때 사용한다. 사용자를 지정하지 않으면 현재 사용자를 기준으로 정보를 출력한다.|
|x (BSD계열)|데몬 프로세스처럼 터미널에 종속되지 않는 프로세스를 출력한다. 보통 a옵션과 결합하여 모든 프로세스를 출력할 때 사용|
|-x| 로그인 상태에 있는 동안 아직 완료되지 않은 프로세서들을 보여준다. 유닉스 시스템은 사용자가 로그아웃 한 후에도 임의의 프로세서가 계속 동작하게 할 수 있다. 그러면 그 프로세서는 자신을 실행시킨 셀이 없어도 계속 자신의 일을 수행하는데 이러한 프로세스는 일반적인 ps명령으로 확인할 수 없다. 이 때 -x옵션을 사용하면 자신의 터미널이 없는 프로세서들을 확인할 수 있다.|

##jobs
현재 셸에서 실행 중인 작업 목록을 표시합니다. 셸에서 백그라운드로 실행된 작업이나 일시 중지된 작업 등을 확인할 수 있습니다. 작업 ID와 상태를 함께 표시.

* 작업 번호 (Job ID): 각 작업에 할당된 고유 번호입니다.
* 작업 상태: 실행 중인 작업인지, 중지된 작업인지 등의 상태를 표시합니다.

* jobs 명령어 실행 이미지

![Rinux command image - jobs](https://github.com/HaNSunG9/20233169-/assets/133843553/560d5105-71cd-4cee-9122-37991873d601)

**jobs 상태
|-------------|

|상태||설명|
|:----------:|:---------------------------------------------------------------------------------------:|
|Running|작업이 계속 진행중임|
|Done|작업이 완료되어 0을 반환|
|Done(code)|작업이 종료되었으며 0이 아닌 코드를 반환|
|Stopped|작업이 일시 중단|
|Stopped(SIGTSTP)|SIGTSTP 시그널이 작업을 일시 중단|
|Stopped(SIGSTOP)|SIGSTOP 시그널이 작업을 일시 중단|
|Stopped(SIGTTIN)|SIGTTIN 시그널이 작업을 일시 중단|
|Stopped(SIGTTOU)|SIGTTOU 시그널이 작업을 일시 중단|

**jobs [옵션]
|------------------------------------------------------------------------------------------------------|

|   옵션   |                                             설명                                            |
|:-------:|:------------------------------------------------------------------------------------------:|
|-l|프로세스 그룹 ID를 state 필드 앞에 출력|
|-n| 프로세스 그룹 중에 대표 프로세스 ID를 출력|
|-p|각 프로세스 ID에 대해 한 행씩 출력|
|command|지정한 명령어를 실행|

##kill
지정한 프로세스에 지정한 시그널을 보냄. 시스템에 문제가 생겨 해당 프로세스를 터미널에서 종료시킬 경우 유용함. 만약 kill 명령으로 종료되지 않는 프로세스가 있다면 -9 옵션을 이용하여 프로세스를 강제 종료시킴.

* 'kill <PID>': 특정 PID에 해당하는 프로세스를 종료합니다. 기본적으로는 TERM 시그널을 보내어 프로세스에 종료 신호를 전달합니다.
* 'kill -<signal> <PID>': 특정 PID에 해당하는 프로세스에 지정한 시그널을 보냅니다. 예를 들어, 'kill -9 <PID>'는 해당 프로세스를 강제로 종료하는 것을 의미합니다. 일반적으로 TERM 시그널 (15)이 가장 일반적인 종료 방법이지만, 강제 종료가 필요한 경우에는 KILL 시그널 (9)를 사용할 수 있습니다.

* kill 명령어 실행 이미지


  
  
  
  
  
  

