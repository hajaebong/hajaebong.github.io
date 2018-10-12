---
layout: post
title: jekyll과 localhost
category: jekyll
tag :  jekyll
comments: true
---

<div class="message">
  jekyll 블로그를 만들고 github로 호스팅을 했습니다.<br> 
  그런데..........<br>
  호스팅되는 github 실서버에 바로 적용해서 보려니 오타나 에러가 나버리면 실시간으로
  블로그에 보여지게 되니... 참으로 난감했다.^^;;;<br> 
  그래서 <strong>localhost</strong> 가 필요함을 느꼈다....
</div>

## 1. jekyll이 사용하는언어?
- ruby기반의 언어이다.<br>
->나는 ruby를 다뤄 본적이 없다... 하지만 만류귀종(萬流歸宗)이라 했던가... 도에 끝은 결국 다 하나인 것을.....<br>
->이름도 영롱하다, 루비라니~(나중에 안사실이지만 설치명령어가 gem 이었다~ 재미있는 언어이다.) <br>
->한번 localhost를 설치해 보기로 했다.<br>
->전 **windows User** 라서 윈도우 버젼 설치를 하겠습니다.

## 2. [루비(Ruby)](https://rubyinstaller.org/downloads/) 설치
- 설치파일을 다운 받는 [사이트](https://rubyinstaller.org/downloads/)로 갑시다~
<br>
- 아래와 같은 화면이 뜹니다.
![루비다운로드페이지]({{site.url}}/assets/ruby_site.JPG)
- 오른쪽 빨간박스 해놓은것을 보면
>뭘 다운 받을까?<br>
>뭘 받을지 모를땐 그냥 Ruby+devkit 2.4.X를 받아~
>대충 이런 소리다^^;;;
- 그래서 저는 왼쪽에 빨간박스 해놓은것을 받운 받았습니다.<br>
-->예전엔 Devkit이 따로 분리 되어 있었는데 요즘엔 같이 묶여 있는거 같습니다.<br>
- 다운 받은 파일을 실행해서 루비를 설치해 줍니다.
    >![루비setup1]({{site.url}}/assets/setup_ruby1.JPG)<br>
    >![루비setup2]({{site.url}}/assets/setup_ruby2.JPG)<br>
    >![루비setup4]({{site.url}}/assets/setup_ruby4.JPG)<br>
    >![루비setup5]({{site.url}}/assets/setup_ruby5.JPG)<br>
    finish를 누르면 아래처럼 콘솔창이 나오는데요
    >![루비setup6]({{site.url}}/assets/setup_ruby6.JPG)
    MSYS2를 설치하는 과정입니다.<br>
    MSYS2에 대해선 [여기](https://ko.wikipedia.org/wiki/MinGW) 참조하세요.<br>
    전 1번만 설치 했습니다<br>
    >![루비setup7]({{site.url}}/assets/setup_ruby7.JPG)
    다설치 되면 이런 화면이 뜨고요~ 화면을 닫아주세요<br><br>
    
## 3. 루비 콘솔창에서 실행
- 윈도우 하단 bar에 검색하기(돋보기)누르시고 검색명으로 ruby를 입력하시면 ruby 커맨드 콘솔창이 검색 됩니다. 클릭하시구요~
>![루비setup8]({{site.url}}/assets/setup_ruby8.JPG)

- 다음 명령어를 차례로 입력합니다.
{% highlight html %}
gem install jekyll
gem install minima
gem install bundler
gem install jekyll-feed
gem install tzinfo-data
지킬과 그외의 필요한 패키지들을 설치합니다.
{% endhighlight %}

- 루비 콘솔창에서 자신의 블로그 소스가 있는 디렉토리로 이동합니다.
{% highlight html %}
인코딩 에러 발생시 다음의 코드를 실행합니다.
chcp 65001
지킬 로컬서버을 실행합니다.
jekyll serve
{% endhighlight %}

- 아래와 같이 로컬서버가 뜹니다. 그럼 http://127.0.0.1:4000/ 로 접속해서 자신의 블로그를 볼수 있습니다.
>![루비setup10]({{site.url}}/assets/setup_ruby10.JPG)

# 결론
<div class="message">
  기본적인 로컬 세팅 능력과 콘솔창을 안다면 jekyll 로컬세팅을 비교적 간단했습니다.
  이제 local에서 편집해서 잘되었는지 확인후 git push로 github와 연동된 서버로 소스를 올려 블로그에 반영할수 있게 되었습니다^^
</div>

<br><br>
참고 URL

- [https://shryu8902.github.io/_posts/2018-06-22-jekyll-on-windows/](https://shryu8902.github.io/_posts/2018-06-22-jekyll-on-windows/
)

