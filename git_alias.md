# Git Alias Convention

## Git Alias 설정

### Git Alias 설정 확인
* Git Alias가 사전에 설정 되어 있는지 확인한다.
`git config --global --list | grep alias`

### Git Alias 설정 적용
* Alias들은 ~/.gitconfig 파일에 입력해도 동일하게 동작한다.
* 아래 Log Type 중에 원하는 타입을 선택하여 Git Config에 적용한다.
**Log Type 1**
```
git config --global alias.ll "log --color --graph --pretty=format:'%Cred%h%Creset -%C(yellow)%d%Creset %s %Cgreen(%cr) %C(bold blue)<%an>%Creset' --abbrev-commit"
```
**Log Type 2**
```
git config --global alias.ll "log --graph --abbrev-commit --decorate --format=format:'%C(cyan)%h%C(reset) - %C(green)(%ar)%C(reset) %C(white)%s%C(reset) %C(dim white)- %an%C(reset)%C(yellow)%d%C(reset)' --all"
```

### Git Alias 설정 확인
* Git Alias 설정이 정상적으로 적용되었는지 확인한다. 
```
$ git config --global --list | grep alias
alias.ll=log --color --graph --pretty=format:'%Cred%h%Creset -%C(yellow)%d%Creset %s %Cgreen(%cr) %C(bold blue)<%an>%Creset' --abbrev-commit
alias.lg=log --graph --abbrev-commit --decorate --format=format:'%C(cyan)%h%C(reset) - %C(green)(%ar)%C(reset) %C(white)%s%C(reset) %C(dim white)- %an%C(reset)%C(yellow)%d%C(reset)' --all
```

### Git Alias 동작 확인
* Git Alias에 의해 Log 형식이 변경된 것을 확인할 수 있다.
```
$ git lg -n 5
* 5fe3d59 - (4 weeks ago) Update | RDS template #1 - jaehwan (origin/ui)
* 9816da2 - (4 weeks ago) Update | SG Tasks #32 - jaehwan
* ae010e4 - (4 weeks ago) Update | SG Tasks #31 - jaehwan
* 1b7c94d - (4 weeks ago) Update | SG Tasks #30 - jaehwan
* 57d4970 - (4 weeks ago) Update | SG Tasks #29 - jaehwan
```