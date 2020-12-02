---
title: \[git] 깃 업로드 시, There isn’t anything to compare. 에러
excerpt_separator: "<!--more-->"
categories:
  - git
tags:
  - git
  - git 업로드
  - 에러 
  
---
        
# 상황
         
         
     
깃에 폴더를 업로드 하려고 검색해보며 아래 코드를 쳤다   

```git add .```        
```git commit -m "koa_server"```        
```remote add origin https://github.com/JinHeeeKang/Image-Inpaining-WebService.git```        
```git push -u origin master```        
    
    
그랬더니 
default 가 main 으로 되어있고 master 가 새로 생겨 거기에 추가된 것!
뭐가 뭔지 몰라서 찾아보니 
master 대신 main을 사용하는 것으로 바뀌었는데 모르고 master 브랜치에 추가했던 것!


> 'master', 'slave'를 다른 단어로 대체하기 위해서 
> 'main'을 사용한다고 한다!

# 에러
        
        
> There isn’t anything to compare.        
> main and master are entirely different commit histories.        
        
어쩌구 저쩌구 에러가 나왔다 
    
    
    
# 해결
    
- 브랜치 이동                  
```git checkout master```
```git branch main master -f```        
```git checkout main```        
```git push origin main -f```        
    
    
이렇게 했더니 main 브랜치에 master에 있던 파일이 그대로 옮겨졌다!   
         
         
> 근데 두 브랜치 다 남아 있어서 그냥 지우고 다시 만들 예정...



# 해결2

다시 만들어서 업로드 하는데          
```git push -u origin main```이 안된다!

그래서 그냥 master로 올리고 default를 master로 변경했다!


