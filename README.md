## iterm custom
plugin 
-  zsh-autosuggestions
-  zsh-syntax-highlighting
-  autojump

표시이름 변경 ```~/.zshrc``` 맨 밑
```
prompt_context() {
  prompt_segment black default "yujung"
}
```

줄바꿈 ```~/.oh-my-zsh/themes/agnoster.zsh-theme prompt_end``` 바로위에 ```prompt_newline``` 추가하기
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


## 그외 설치
- Better Touch Tool
- Session
- Discord
- Deepl
- Logi Options+
- Obsidian
- Send to Kindle
