# SoftwareEngineering

**'Camera Motion Sensing Project for Home Security'** project for 2021-1 software engineering class


## Problem Statement
최근 들어 자취방 등 혼자 사는 곳에 괴한이 창문을 뚫고 침입하는 범죄가 많이 일어나고 있다. '혼자 사는 사람'들의 '보다 안전한 삶'을 위해, 집을 비울 때에 지속적으로 공간을 모니터링하고 이상 행위를 알려주는 시스템이 필요하다. 회원가입 및 로그인을 하고 카메라 설정을 마치면 모니터링 시스템을 활성화 시킬 수 있다. 모니터링 시스템이 활성화 되면 이상 행위가 감지되었을 때 집 밖에서도 경보 알림을 받을 수 있다. 경보가 울린 후 사용자는 집 안의 상황을 확인할 수 있으며, 이상이 없다고 판단되면 경보를 해제할 수 있다. 이상 행위가 탐지된 이후에도 당시의 상황을 사진 기록으로 확인할 수 있으면 좋을 것이다. 해당 시스템은 간단한 UI로 구성되어 쉽게 조작할 수 있으면 좋겠다.

## Scenarios
- 앱 최초 실행 시 사용자는 회원가입을 진행한다. 
- 아이디와 비밀번호를 입력하여 로그인한 후에, 사용자는 ‘모니터링 시작’과 ‘갤러리’, ‘설정’ 버튼을 볼 수 있다. 
- 사용자는 ‘설정’ 버튼을 눌러 카메라로 사용할 스마트 기기를 세팅할 수 있다.
- 사용자는 ‘설정’ 버튼을 눌러 비밀번호를 변경할 수 있다.
- ‘모니터링 시작’ 버튼 클릭 후, 카메라 연결이 확인되고 나면 사용자는 모니터링을 시작할 수 있다. 
- 모니터링 중 카메라 기기가 꺼지거나 문제가 감지되었을 경우 모니터링이 종료되며 사용자에게 알림이 발송된다.
- 모니터링이 중 움직임이 감지됐을 때, 연동된 휴대폰에 알림음이 울리고 경보 상태로 진입한다. 
- 경보 상태를 해제하기 위해 사용자는 비밀번호를 입력해야 한다.
- 경보 상태에서 감지된 움직임에 대한 사진은 갤러리에 저장된다. 사용자는 이후 언제든지 로그인하여 갤러리에서 기록된 장면들을 볼 수 있다. 
- 사용자는 ‘모니터링 종료’ 버튼을 누르면 비밀번호를 입력하고 모니터링을 마칠 수 있다. 모니터링이 종료되면, 연동된 휴대폰에 알림과 기록을 중지한다.
- 모니터링이 너무 오랜 기간 지속될 경우 모니터링이 종료되며 사용자의 기기로 알림 메시지가 전송된다.


## Requirements
### Functional Requirements
Identifier | User Story | Size
:---------:|-----------|:----:
REQ-1 | 사용자로서, 나는 회원가입을 할 수 있다. | 0
REQ-2 | 사용자로서, 나는 아이디와 비밀번호를 입력하여 로그인 할 수 있다. | 0
REQ-3 | 사용자로서, 나는 카메라로 사용할 스마트 기기를 설정할 수 있다. | 0
REQ-4 | 사용자로서, 나는 비밀번호를 변경할 수 있다. | 0
REQ-5 | 사용자로서, 나는 카메라를 이용하여 모니터링을 시작할 수 있다. | 0
REQ-6 | 사용자로서, 나는 원격으로 모니터링을 종료할 수 있다. | 0
REQ-7 | 사용자로서, 나는 경보가 울리면 비밀번호를 입력하여 끌 수 있다. | 0
REQ-8 | 사용자로서, 나는 모니터링 기록에 접근하고 삭제할 수 있다. | 0
REQ-9 | 인가되지 않은 사용자로서, 나는 모니터링 기록에 접근할 수 없다. | 0
REQ-10 | 인가되지 않은 사용자로서, 나는 모니터링을 강제로 끌 수 없다. | 0
REQ-11 | 기기는 카메라에 움직임이 감지되면 사진을 저장하고 사용자에게 알림을 전송한다. | 0
REQ-12 | 기기는 모니터링이 너무 오랜시간 지속되는 경우, 프로그램을 종료하고 사용자에게 알림을 전송한다. | 0
REQ-13 | 기기는 의도치 않게 카메라가 꺼진 경우 사용자에게 알림을 전송한다. | 0


### Non-Functional Requirements
Identifier | User Story | Size
:---------:|-----------|:----:
REQ-14 | 프로그램은 안정적으로 끊김없는 모니터링을 제공해야 한다. | 0
REQ-15 | 프로그램은 누구나 사용하기 쉬운 단순한 UI로 구성되어야 한다. | 0
REQ-16 | 카메라와 사용자 앱은 항상 연동되어 있어야 한다. | 0


## Subproblems
- **모션 감지** : 일정 시간 이상의 움직임 감지
  - 직접적인 행동 (창문에 물리적 힘을 가한다, 현관 잠금 해제를 시도한다, 침입한다) 이전에 일정시간 이상의 예외적인 움직임을 감지하여 범죄 예방 할 방법이 필요하다
- **History 관리** : 이상 행위 감지 시 화면 사진 저장, 저장된 사진 관리
  - 집에 사람이 없어도 보안 시스템이 작동해야 한다, 과거 자료를 필요할 땐 사용할 수 있어야 하고 저장 공간을 정기적으로 확보해야 한다
- **Admin 관리** : 활성화/비활성화(특정 시간 비활성화 등), 보안코드 설정, 알림 설정(해지 등) 등의 수동 조작 기능.
  - 시스템이 감지한 움직임을 매뉴얼하게 구별할 필요도 있다 (배달원, 이웃주민, 청소부 등의 모션 감지 시), 문제 파악 시 수동 조작이 편리해야 한다


## Method
Agile


## Etc.
[Camera Motion Sensing Project](https://nevonprojects.com/camera-motion-sensing-project/)
