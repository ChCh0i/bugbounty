# 💰Bugbounty
![js](https://img.shields.io/badge/HTML-239120?style=for-the-badge&logo=html5&logoColor=white) 

## 개요
 - 최근들어 시작한 버그바운티를 통해 찾은 취약점들을 모아 놓은곳입니다.
 - 시작한지 얼마되지않아 찾을때마다 하나씩 올리도록 하겠습니다.
 - hunt reward제외 취약점도 마찬가지로 업로드 됩니다.

## 🪬STORED XSS 1
 - USER input 폼으로 요청을 받는 서버를 통해 발견된 취약점입니다.
 - 게시글 폼 img
 - <img width="367" alt="image" src="https://github.com/ChCh0i/bugbounty/assets/108965611/1d835c0d-4b2c-405b-a628-421e3ea6a209">
 - 게시글 입력폼 Img 파일을 주소로 받을수있는데 해당 게시글에 주소를 입력한 결과입니다.
 - <img width="409" alt="image" src="https://github.com/ChCh0i/bugbounty/assets/108965611/f591429a-b152-43bc-864b-e6206cf6399d">
 - 위 와 같이 img를 삽입했을경우 src의 인자값으로 주소값이 들어가는것을 확인할수 있었습니다.
 - 해당 입력 결과로 더블쿼터를 통하여 인자값을받는 폼을 닫아버리고 on객체를 통하여 script를 삽입해보았습니다.
```
imgur.png" onload="alert(1)
```
 - 해당 입력결과로 img가 load 될때 script문이 실행되는것을 확인할수있었습니다.
 - <img width="371" alt="image" src="https://github.com/ChCh0i/bugbounty/assets/108965611/84ecc05f-59e4-4e7d-ac31-b0d92e827a12">
 - 아래의 코드는 script문을 삽입한 공격코드가 들어간 서버응답 코드입니다.
 - <img width="358" alt="image" src="https://github.com/ChCh0i/bugbounty/assets/108965611/9c585d83-4a49-4187-ba26-692dacbc27cf">
 

## 마무리
 - 해당 취약점은 Self XSS 였습니다.
 - 해당 취약점으로 csrf 권한상승을 해보려 하였지만 전부 블랙리스트 검증 및 세션검증을 통해 넘어가기때문에 불가능하였습니다.
 - Reward받을줄알고 기대했는데.. 쩝.. 아쉽습니다. 다음엔 조금더 노력하여 성공해보겠습니다.
