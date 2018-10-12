---
layout: post
title: jekyll에 Disqus붙이기
category: jekyll
tag :  jekyll
comments: true
---

<!--excerpt.start-->
<div class="message">
  안녕하세요, 이번 포스트는 jekyll에 disqus댓글을 달아 보는것을 하겠습니다.
</div>
<!--excerpt.end-->

### **1.[Disqus](http://https://disqus.com/) 접속해서 가입**
![index]({{site.url}}/assets/index.JPG)
<br>


### **2.GET STARTED 누르면 아래와 같은 Signup 화면이 나옵니다.**
![sign_up]({{site.url}}/assets/signup.JPG)

- 자신이 댓글에 쓸 자신의 닉네임을 쓰세요
- 자신의 이메일(나중에 verify할 이메일 입니다.)
- 비밀번호
- 기타 등등 다 체크 하시고 Signup 버튼 클릭
<br>

### **3.가입하시면 자신의 이메일로 인증 이메일이 옵니다.**
![email]({{site.url}}/assets/email.JPG)
<br>

### **4.인증을 누르면 아래와 같은 화면이 나옵니다.**
![tobni]({{site.url}}/assets/tobni.JPG)

- 오른쪽 위쪽에 톱니모양 아이콘을 누릅니다.
- 펼치지는 메뉴에서 Add Disqus To site를 클릭합니다.
<br>

### **5.스크롤을 맨아래로 내려 Get started 클릭합니다.**
![get_started]({{site.url}}/assets/get_started.JPG)
<br>

### **6.다음의 화면이 나오면 I want to install Disqus on my site를 클릭합니다.**
![select]({{site.url}}/assets/select.JPG)
<br>

### **7.사이트를 등록하는 화면이 나옵니다.**
![newsite]({{site.url}}/assets/newsite.JPG)
<br>

### **8.서비스 설정하는 화면 인데 물론 저는 개인 블로그 이기 때문에 free 서비스를 선택합니다.**
![paln]({{site.url}}/assets/paln.JPG)
<br>

### **9.플랫폼을 선택합니다.(저는 jekyll로 블로그를 만들었습니다.)**
![platform]({{site.url}}/assets/platform.JPG)
<br>

### **10.다음에 이런 화면이 뜹니다. 그럼 저아래 있는 Universal Embed Code 를 클릭 해주세요.**
![embedcode]({{site.url}}/assets/embedcode.JPG)
<br>

### **11.아래와 같은 화면이 뜨면 빨산색 네모 박스안에 있는 코드들을 다 복사해서 따로 놔둬 주세요.**
![embed2]({{site.url}}/assets/embed2.JPG)
<br>

### **12.스코롤을 아래로 내려서 Configure를 클릭해주세요**
![embed3]({{site.url}}/assets/embed3.JPG)
<br>

### **13.마지막 설정 화면 입니다. 여기서 자신의 블로그 주소를 등록해 줍니다.**
![configute]({{site.url}}/assets/configute.JPG)
<br>
   
### **14.자신의 블로그 폴더로 오셔서 _includes 폴더안에 comments.html 파일을 하나 만듭니다.**
![comments]({{site.url}}/assets/comments.JPG)
<br>

### **15.comments.html 파일에 11번에서 복사했던(아래의 코드들) 코드들을 사이에 다 붙여넣기 합니다.**
{% highlight html %}
<div id="disqus_thread"></div>
<script>

    /**
     *  RECOMMENDED CONFIGURATION VARIABLES: EDIT AND UNCOMMENT THE SECTION BELOW TO INSERT DYNAMIC VALUES FROM YOUR PLATFORM OR CMS.
     *  LEARN WHY DEFINING THESE VARIABLES IS IMPORTANT: https://disqus.com/admin/universalcode/#configuration-variables*/
    /*
    var disqus_config = function () {
    this.page.url = PAGE_URL;  // Replace PAGE_URL with your page's canonical URL variable
    this.page.identifier = PAGE_IDENTIFIER; // Replace PAGE_IDENTIFIER with your page's unique identifier variable
    };
    */
    (function() { // DON'T EDIT BELOW THIS LINE
        var d = document, s = d.createElement('script');
        s.src = 'https://jbblog-1.disqus.com/embed.js';
        s.setAttribute('data-timestamp', +new Date());
        (d.head || d.body).appendChild(s);
    })();
</script>
<noscript>Please enable JavaScript to view the <a href="https://disqus.com/?ref_noscript">comments powered by Disqus.</a></noscript>

{% endhighlight %}

### **16.자신의 블로그 폴더에가서 _layouts 폴더밑에 post.html에 해당 코드를 추가 해줍니다.**
![post]({{site.url}}/assets/post.JPG)
<br>

### **17.post를 작성 할때 아래 처럼 설정 값을 주면 그 포스트에 댓글기능이 붙게 됩니다.**
![sel]({{site.url}}/assets/sel.JPG)

<br><br>
참고 URL

- [https://cjh5414.github.io/Disqus/](https://cjh5414.github.io/Disqus/
)
- [https://17billion.github.io/jekyll/disqus/reply/2017/06/01/jekyll_disqus.html](https://17billion.github.io/jekyll/disqus/reply/2017/06/01/jekyll_disqus.html)