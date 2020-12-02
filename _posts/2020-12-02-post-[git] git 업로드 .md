---
title: \[git] 터미널로 깃 업로드
excerpt_separator: "<!--more-->"
categories:
  - git
tags:
  - git
  - git 업로드
  
  
---
        
# 깃에 업로드 할때       
       
              
1. 터미널로 해당 폴더가 있는 곳으로 이동                   
            
       
       
2. 깃 초기화        
```git init```       
제대로 초기화 됐는지 위치 확인       
       
       
         
3. 업로드할 파일 add       
```git add .```  : 하위 파일 전체 add       
```git add (폴더명/파일명)``` : 특정 파일만 add       
       
       
       
4. commit       
```git commit```               
```git commit -m "koa_server"``` : 메세지를 포함해 커밋              
       
       
       
5. 올릴 Repositories 지정       
```remote add origin "Repositories 주소"```  
       
       
6. push       
```git push -u origin master```        
```git push -u origin (올릴 브랜치 이름)```        

       
      
