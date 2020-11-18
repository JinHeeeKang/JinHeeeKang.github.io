---
title: \[환경 구축\]\[macOS\] 맥에서 AWS ssh로 접속, vscode 연결하기

categories:
- Project
- 세팅

tags:
  
---

> 1. windows 에서는 putty 로 나름? 간편하게 사용하다가 그 노트북 쓸날도 얼마 남지 않았기에 평소 사용하는 맥북에 다시 개발 환경을 세팅했다.
> AWS ssh를 사용해 인스턴스에 연결하는 과정을 기록한다. 혼자 하는데에 나름 애먹었고, 다음에도 잘써먹기 위해..
>
> 2. 인스턴스 생성하는 과정은 깃에 있음   
> windows환경 putty로 세팅하는 과정도 구글 드라이브에 있음    
> authorized_keys 복사하는 과정도 구글 드라이브에 있음


- - -   

# 1. .pem 파일 .ssh 폴더로 옮기기

> 1. 인스턴스 생성 하게되면 .pem 파일이 있음
>
> 2. ~ 위치에서 .ssh폴더 생성   
> ```gangjinhuiui-MacBook-Pro:~ kangjinhee$ mkdir .ssh```
>
> 3. 키 파일을 .ssh 폴더로 이동   
> ```gangjinhuiui-MacBook-Pro:~ kangjinhee$ mv file이름.pem ./.ssh```





# 2. vscode 연결

> 1. extension 에서 ```Remote - SSH``` install
>
> 2-1. ```gangjinhuiui-MacBook-Pro:.ssh kangjinhee$ vi config```
> 
> 2-2. F1 누르고
> ```Remote - SSH\:connect to host``` -> ``` configure SSH Hosts```
> -> 맨 위 ```~/.ssh/config``` 
> 
> 3. config로 들어간 뒤 이러한 형태로 입력   
> (주의)```HostName, User, IdentityFile``` 간격을 tab으로 맞추는게 좋음
> ```
> Host 사용할 서버 이름(아무거나)
>     HostName 퍼블릭 IPv4 주소 or 퍼블릭 IPv4 DNS
>     User 유저이름
>     IdentityFile .pem파일 위치( 예) ~/.ssh/파일이름.pem )
> ```




# 3. (중요) 권한 설정
- 이 과정을 안하면 connect to host 할때 bad permissions permission denied (publickey) 에러가 남

> 1.  chmod로 키파일 권한 변경   
> ```gangjinhuiui-MacBook-Pro:.ssh kangjinhee$ chmod 400 ./file이름.pem ```
> 
> 2. authorized_keys 폴더 생성   
> ```gangjinhuiui-MacBook-Pro:.ssh kangjinhee$ vi authorized_keys```
> 
> 3. centos(인스턴스)안에 있는 authorized_keys 파일에서 복사/붙여넣기   
> 
> 4.```gangjinhuiui-MacBook-Pro:.ssh kangjinhee$ chmod 400 ./authorized_keys```   
> 
> 5.```gangjinhuiui-MacBook-Pro:~ kangjinhee$ chmod 700 ./.ssh```   




# 4. 터미널 연결
- 3 까지 과정은 1번만 하면 끝, 4번 터미널 연결은 서버 킬때마다 사용   
- 폴더 위치가서 ```npm start```

> 1. 사용자 이름으로 로그인 됨   
> ```ssh -i .pem파일 위치 사용자 이름 @퍼블릭 IPv4 주소 or 퍼블릭 IPv4 DNS```



- - - 

# 끝
기억 나는 대로 썼지만 빠트린게 있을수 있음 생각나는대로 추가 예정!

