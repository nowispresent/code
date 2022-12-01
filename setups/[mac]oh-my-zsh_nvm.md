# [mac]oh-my-zsh_nvm
- 터미널(bash or zsh)에서 oh-my-zsh로 변경했음
- nvm이 안됨 => nvm 환경변수 설정해 줘야함
- 구글링 결과 bash, zsh 등등 다양한 nvm 환경변수 반영 소스들이 뒤섞여있어 정리해 놓기로 함.

## 1. oh-my-zsh 을 설치한다
- [https://ohmyz.sh/]https://ohmyz.sh/로 접속
```
//curl로 설치
sh -c "$(curl -fsSL https://raw.github.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"

//wget으로 설치
sh -c "$(wget https://raw.github.com/ohmyzsh/ohmyzsh/master/tools/install.sh -O -)"
```
## 2. 설치를 하면 nvm이 당연히 안되기 때문에 vim 에디터로 .zshrc 파일을 열어준다.
```
vi ~/.zshrc
```

## 3. 아래의 설정을 추가해준다
- i 눌러서 insert 모드에서 편집
- esc키 눌러서 insert 모드에서 나오기
- :wq 저장하고 닫기
```
echo 'export NVM_DIR=~/.nvm' >> ~/.zshrc
echo '[ -s "$NVM_DIR/nvm.sh" ] && . "$NVM_DIR/nvm.sh"' >> ~/.zshrc
```

## 4. 설정파일 적용해주기
```
source ~/.zshrc
```

## 5. 확인하기
```
nvm -v
```
