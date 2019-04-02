---
layout: post
title: worpress 포스트(post), 페이지(page) 차이점, 활용기준, 한계
category: wordpress
tag : wordpress
comments: true
---

<!--excerpt.start-->
<div class="message">
  회사에서 wordpress로 custom post type을 만들 일이 생길것 같아 미리 공부하려 한다.  
  그전에 미리 wordpress의 post, page, 기타 용어들에 대해 집어 놓으려고 한다.  
  아무래도 custom post type 만드는데 다 관련이 있다보니.....
</div>
<!--excerpt.end-->

# 1. Post, Page 차이점
>## post
-수시로 추가 되는 글  
## page  
-사이트 골격을 형성하는 고정적으로 배치되는 것, 즉 static page 같은것들(회사소개같은)  
<br>

# 2. 카테고리와 태그  
>-post: 카테고리와 태그를 가질수 있다.  
-psge: 카테고리와 태그를 가질수 없다.  
<br>
**->카테고리와 태그에 연결시켜둔 post는 카테고라와 혹은 태그 별로 그에 속한 포스트들만 listing 할수 있다.**  
<br>

# 3. post와 카테고리  
>-1개의 post는 2개 이상의 카테고리에 속할수 있다.  
-예를 들면 카테고리로 일상, 맛집, 영화가 있다.
-1개의 포스트를 작성하는데 "오늘 맛있는 집에서 밥을 먹고 영화를 봤다."라는 내용이면 이건 일살+맛집+영화 이 세개 모두의 카테고리에 해당 할 수 있다.
<br>
<br>

# 4. 카테고리 성질
>-카테고리들끼리는 상위 하위 설정 가능하다.  
-동물, 사람, 남자, 여자라는 카테고리가 있다면 포함관계 설정 가능하다.  
-동물<- 사람 <- 남자 = 여자 이런식으로 상하관계가 가능하다.  
<br>
<br>

# 5. 태그성질
>-태그들끼리는 상하 하위 관계 설정하지 못한다.
-독립적인 단어들, 서로 중첩되지 않는 단어들로 구성하는게 좋다.  
<br>
<br>

# 6. 템플릿 설정
>-post: 템플릿 설정불가, 모두 동일한 템플릿 적용 (custom 템플릿을 적용 할수는 있지만 각각의 post 마다 템플릿 설정이 불가능 하다는 말인듯하다.)  
-page: 템플릿 설정 가능하다.  
<br>
<br>

# 7. 글 들간의 하이어라키(상하관계)  
> -post: post끼리 상호 상위 하위 관계를 만들수 없다.  
-page: 페이지간의 상위 하위 관계 만들 수 있다. 1개의 page는 1개의 상위 page만 지정 가능하다. 1개의 page는 2개이상의 하위  page를 가질 수있다.
<br>
<br>

# 8. RSS feed
>-포스트에만 된다.  
<br>
<br>

# 9. 워드프레스 기본제공 포스트와 페이지의 한계
>-워드프레스로 회사 홈페이지 구축시 제품 표현에 대한 요구 사항  
-1.기본 제공 포스트엔 블로그처럼 잡다한 글이 기록 되어 있어, 관리가 안된다.  
-2.제품 카테고리를 가질 수 있어야 하고 제품 카테고리별 정렬 기능이 있어야 한다.  
**->위와 같이 기본 제공 포스트만으로 정보표현이 불가능한 경우 사용자의 정의 포스트를 이용하여 해결 가능하다.**  

<br>
  
  
# 결론
<div class="message">
  결국
  <br>
  1. 보통의 글과는 다른 특정 형식을 가진 글 유형을 추가 하고 싶다.  
  <br>
  2. 특정 포스트에 대해 레이아웃을 쉽게 변경하고 싶다.  
  <br>
  3. 특정 글들을 모아서 쉽게 관리하고 싶다.  
  <br>
  -> 사용자 정의 포스트 타입으로 가는 것이 맞다.  
</div>

<br><br>
참고 url

- [https://igotit.tistory.com/62](https://igotit.tistory.com/62)
- [https://www.thewordcracker.com/intermediate/how-to-add-movie-review-post-type-to-wordpress/](https://www.thewordcracker.com/intermediate/how-to-add-movie-review-post-type-to-wordpress/)

