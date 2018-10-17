---
layout: post
title: Docker setting
category: docker
tag :  docker
comments: true
---

<!--excerpt.start-->
<div class="message">
  현재 라라벨 프로젝트를 vagrant와 homestead로 로컬세팅을 해서 관리하고 있다.<br>
  그런데 vagrant는 속도도 느리고 여러모로 불편해서 <strong>docker</strong>로 로컬 세팅을 바꿔 보려고 합니다.<br>
  일단은 기본적인 docker를 학습하고 난후에 vagrant로 세팅되어 있는 라라벨 프로젝트들을 하나씩 docker로 옮기려 합니다
</div>
<!--excerpt.end-->

# windows 버젼입니다. setting 입니다.

## 1.[docker window버젼 다운로드](https://docs.docker.com/engine/installation)
## 2.![도커다운로드1]({{site.url}}/assets/docker1.JPG)<br>
## 3.![도커다운로드2]({{site.url}}/assets/docker2.JPG)<br>
## 4.회원 가입을 해야지 다운이 가능하더라고요. 회원 가입은 간단하니 회원 가입해주세요.^^
![도커다운로드3]({{site.url}}/assets/docker3.JPG)<br>
## 5.회원 가입을 하고 난후 다시 돌아오면 다운로드 버튼이 바뀌어 있습니다.
![도커다운로드4]({{site.url}}/assets/docker4.JPG)<br>
## 6.다운로드 받은 파일을 실행해주시고 그냥 별거 없이 계속 next눌러주시면 docker가 깔아 집니다.<br> setting을 위해 컴퓨터가 몇번 재시작 할수 있습니다~<br><br>
## 7.컴퓨터 재시작이 끝나면 오른쪽 아래 보시면 저렇게 docker is running이라고 뜹니다.
![도커다운로드5]({{site.url}}/assets/docker5.JPG)<br>
## 8.커맨드 창을 여시고요(전 git bash를 썼습니다)<br>-docker version 라고 쳐주세요.<br>아래처럼 나와야지 제대로 설치 된겁니다.
![도커다운로드6]({{site.url}}/assets/docker6.JPG)<br>

## 결론
-윈도우의 장점은 간단한 세팅입니다... 나중에 맥에다가도 세팅을 해봐야 겠네요^^ 다음 포스팅은 docker 실습편을 올리도록 하겠습니다.
<br><br>
## 덧붙임
docker 설치시 Hyper-V라는 가상화 시스템을 이용합니다.<br>
### **이걸 설치하니 vagrant와 충돌을 하더군요.** <br>
vagrant를 쓰고 있는 Laravel 프로젝트를 아직 docker 시스템에 옮기지 않았기 때문에 vagrant를 쓰려면 Hyper-v를 꺼야 합니다.<br><br>
1. 아래 그림 처럼 windows 기능을 찾아 실행하세요.
![도커다운로드8]({{site.url}}/assets/docker8.JPG)<br>
2. 빨간색 박스의 hyper-v 체크항목을 없애주시고 확인! ![도커다운로드9]({{site.url}}/assets/docker9.JPG)<br>
3. 컴퓨터가 여러번 재부팅 되면서 vagrant가 사용 가능 합니다.<br><br>
4. 그런데 docker가 시작프로그램에 등록 되어 있다면 자꾸 docker를 시작하려면 hyper-v를 실행해야 한다고 뜹니다. 그러니 docker를 시작 프로그램에서 제외시켜 주세요.
