### screen

| 명령어                | 설명                                                        |
| --------------------- | ----------------------------------------------------------- |
| screen                | 새로운 screen 세션을 시작합니다.                            |
| screen -S             | [세션이름] 지정된 이름으로 새로운 screen 세션을 시작합니다. |
| screen -ls            | 현재 실행 중인 모든 screen 세션을 나열합니다.               |
| screen -r [세션ID]    | 특정 screen 세션을 재연결합니다.                            |
| screen -d [세션ID]    | 특정 screen 세션을 분리합니다.                              |
| screen -d -r [세션ID] | 현재 연결된 screen 세션을 분리하고 다시 연결합니다.         |
| Ctrl-a c              | 새로운 창을 생성합니다.                                     |
| Ctrl-a n              | 다음 창으로 이동합니다.                                     |
| Ctrl-a p              | 이전 창으로 이동합니다.                                     |
| Ctrl-a d              | 현재 screen 세션을 분리합니다.                              |
| Ctrl-a k              | 현재 창을 강제 종료합니다.                                  |
| Ctrl-a w              | 창 목록을 표시합니다.                                       |
| Ctrl-a 0..9           | 지정된 번호의 창으로 이동합니다.                            |
| Ctrl-a A              | 현재 창의 이름을 변경합니다.                                |
| Ctrl-a "              | 창 목록을 선택할 수 있게 표시합니다.                        |
| Ctrl-a S              | 창을 수평으로 분할합니다.                                   |
| Ctrl-a tab            | 분할된 영역 사이를 이동합니다.                              |
| Ctrl-a X              | 활성 창을 닫습니다.                                         |
| Ctrl-a Q              | 모든 창을 한 화면에 표시합니다.                             |
| Ctrl-a x              | 현재 화면을 잠급니다.                                       |
| Ctrl-a ?              | screen 도움말을 표시합니다.                                 |
| Ctrl-a Esc            | 스크롤 모드로 전환합니다.                                   |
