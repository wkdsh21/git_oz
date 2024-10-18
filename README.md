# 미니프로젝트 - 심리테스트 

<br/><br/>


## ER-다이어그램

![](https://velog.velcdn.com/images/wkdsh21/post/d0728196-49ef-4600-a68b-2d16a79e0451/image.jpg)

> Adimn의 username과 password는 너무길지않게 50으로 제한
Participant의 name도 50으로 제한하고 gender 또한 10으로 제한
Participant와 Question은 서로 다대다 관계(N:M)이므로 이를 표현할수있게
중간 테이블(Quiz)을 만들어 1:N M:1로 풀어 냈음

<br/><br/>

## 프로젝트 구조

>app<br/>
 ㄴ__init__.py<br/>
 &nbsp;&nbsp;&nbsp;database.py<br/>
 &nbsp;&nbsp;&nbsp;models.py<br/>
 &nbsp;&nbsp;&nbsp;routes.py<br/>
 &nbsp;&nbsp;&nbsp;templete<br/>
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;ㄴadmin.html<br/>
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;dashboard.html<br/>
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;index.html<br/>
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;manage_questions.html<br/>
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;quiz.html<br/>
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;quiz_list.html<br/>
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;results.html<br/>
 run.py <-- app.run() 실행
 
 <br/><br/>
 
##  기능 설명
>### - "/" [GET]
참여자 정보입력 페이지 렌더링(index.html)

>### - index.html -> "/participants" [POST]
참여자 정보입력후 submit시 "/participants" [POST] 요청
 
>### - "/participants" [POST] -> "/quiz" [GET]
참여자 정보 participant 테이블에 저장후 id와 함께 "/quiz"로 redirect

>### -"/quiz" [GET] -> "quiz.html"
요청에 id가 없으면 "/" 로 redirect, 있다면 question 테이블에서
문제들을 모두 불러와서 "quiz.html" 과 문제리스트들을 렌더링해 응답

>### - quiz.html


 
