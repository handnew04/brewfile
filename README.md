homebrew 설치 후 brew를 찾지 못할 때 
```
$ brew --version
zsh: command not found: brew

zshrc에 homebrew path 추가
$ echo 'export PATH=/opt/homebrew/bin:$PATH' >> ~/.zshrc
zshrc 반영
$ source ~/.zshrc
```

## iterm custom
```
brew install zsh
sh -c "$(curl -fsSL https://raw.github.com/robbyrussell/oh-my-zsh/master/tools/install.sh)"
```
[iterms 컬러 사이트](https://iterm2colorschemes.com/) 
1. 마음에 드는 테마 선택 후 주소 복사
2. curl이 설치되어 있지 않은 경우
   brew install curl
3. 다운 받을 폴더로 이동 후 
   curl -LO {테마주소}
4. iterm perference-profie-color-import

### 테마 변경
vi ~/.zshrc\
<img width="585" alt="스크린샷 2023-12-27 오후 10 22 32" src="https://github.com/handnew04/brewfile/assets/44838136/065f5da0-c3f6-4af3-9342-3439bc13878c">\
`ZSH_THEME=agnoster`로 변경

### 폰트 변경
[폰트 D2](https://github.com/naver/d2codingfont)

### [plugin] 
#### brew install로 설치
1. zsh-syntax-highlighting
2. autojump

3. zsh-autosuggestions는 아래 명령어로 설치\
`git clone https://github.com/zsh-users/zsh-autosuggestions $ZSH_CUSTOM/plugins/zsh-autosuggestions` 

설치 후

`~/.zshrc` 아래에 
`source /opt/homebrew/share/zsh-syntax-highlighting/zsh-syntax-highlighting.zsh` 추가\
`plugins=(git)`를 찾아서 
```
plugins=(
git
zsh-autosuggestions
autojump
)
로 변경
```

### 표시이름 변경 
`~/.zshrc` 맨 밑
```
prompt_context() {
  prompt_segment black default "보여질이름"
}
```

### 줄바꿈 
`vi ~/.oh-my-zsh/themes/agnoster.zsh-theme`의 맨 아래에\
`prompt_end` 바로위에 `prompt_newline` 추가하기
```
prompt_newline() {
  if [[ -n $CURRENT_BG ]]; then
    echo -n "%{%k%F{$CURRENT_BG}%}$SEGMENT_SEPARATOR
%(?.%F{$CURRENT_BG}.%F{red})❯%f"

  else
    echo -n "%{%k%}"
  fi

  echo -n "%{%f%}"
  CURRENT_BG=''
}
```

<img width="585" alt="스크린샷 2023-12-27 오후 10 22 32" src="https://github.com/handnew04/brewfile/assets/44838136/d6838076-fdad-4897-8471-217fdd3442dd">

## 그외 설치
- Better Touch Tool
- Discord
- Deepl
- Logi Options+
- Obsidian
- Send to Kindle
