# Git Commit Message Convention

## Git Commit Message 구성
* <타입(type)> : <제목(Title)>
* <본문(Description)>
* <꼬리말(Issue-Number)>

## Git Commit Message 설정

### **1. Git Commit Message 템플릿 생성**
```
cat << EOF >> ~/.gitmessage.txt
<type> : <subject>
##### Subject 50 characters ################# -> |

# Body Message
######## Body 72 characters ####################################### -> |
<Description>
-
# Issue Tracker Number or URL
<Issue-Number>
# --- COMMIT END ---
# Type can be
#   feat     : 기능 추가, 삭제, 변경
#   fix      : 버그 수정
#   refactor : 코드 리펙토링
#   style    : 코드 형식, 정렬, 주석 등의 변경
#   docs     : 문서 추가, 삭제, 변경
#   test     : 테스트 코드 추가, 삭제, 변경
#   etc      : 위에 해당하지 않는 변경
# ------------------
# Remember me ~
#   Capitalize the subject line
#     제목줄은 대문자로 시작한다.
#   Use the imperative mood in the subject line
#     제목줄은 명령어로 작성한다.
#   Do not end the subject line with a period
#     제목줄은 마침표로 끝내지 않는다.
#   Separate subject from body with a blank line
#     본문과 제목에는 빈줄을 넣어서 구분한다.
#   Use the body to explain what and why vs. how
#     본문에는 "어떻게" 보다는 "왜"와 "무엇을" 설명한다.
#   Can use multiple lines with "-" for bullet points in body
#     본문에 목록을 나타낼때는 "-"로 시작한다.
# ------------------
EOF
```

### **2. Git Config에서 template 설정 적용**
`git config --global commit.template ~/.gitmessage.txt`

### **3. Git Config에서 template 설정 확인**
`git config --global --list | grep "commit.template"`

## Git Commit Message 사용 방법
1. git commit 명령어 실행 후 vim 에디터가 열림
`git commit`
2. vim 에디터에서 템플릿 형식에 맞게 수정 후 저장
3. git push 명령어 실행
`git push`