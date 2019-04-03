---
layout: post
title: worpress login custom error message
category: wordpress
tag : wordpress
comments: true
---

<!--excerpt.start-->
<div class="message">
  현재 회사에서 어드민 보안을 강화를 위해 로그인 보안 플러그인 세개가 운용중이다. 서로 필터와 액션에 의해 로긴 에러 메시지를 여러가지로 어드민 로긴창에 보여주고 있다. 고객사에서 각각의 로긴에러사항에 따른 메세지가 좀 불분명한것 같다고 해서 각각의 사항(예를들어 유저네임이 틀렸다는지 비밀번호가 틀렸다는지 다른 입력란이 틀렸다는지에 대해...)에 대해 명확한 에러 메세지를 표현해 달라고 한다. 보안상으론 그리 좋은 방법은 아니지만 고객사가 해달라면 해야한다.....
</div>
<!--excerpt.end-->

## Wordpress [Plugin API/Filter Reference/login errors](http://https://codex.wordpress.org/Plugin_API/Filter_Reference/login_errors)
>1.일단 세개의 보안 플러그인에서 나오는 로긴 실패시 나오는 에러 메시지는 커스텀을 다 했다.  마지막에 비밀번호가 틀렸을시 나오는 로긴 실패 메세지를 custom 해야 했다. 방법을 찾던 중 워드프레스 코덱스에서 찾았다.  
아래 코드는 워드프레스에서 로긴 에러 메세지를 커스텀 할수 있는 필터이다.  
해당 코드는 [여기](http://https://codex.wordpress.org/Plugin_API/Filter_Reference/login_errors) 가면 자세히 볼수 있다.
<pre><code clsss="php">
add_filter( 'login_errors', function( $error ) {
	global $errors;//전역으로 로긴에러 객체를 받아옴
	$err_codes = $errors->get_error_codes();

	// Invalid username.(유저네임이 틀렸을 경우)
	// Default: '<strong>ERROR</strong>: Invalid username. <a href="%s">Lost your password</a>?'
	if ( in_array( 'invalid_username', $err_codes ) ) {
		$error = '<strong>ERROR</strong>: Invalid username.';
	}

	// Incorrect password.(패스워드가 틀렸을 경우)
	// Default: '<strong>ERROR</strong>: The password you entered for the username <strong>%1$s</strong> is incorrect. <a href="%2$s">Lost your password</a>?'
	if ( in_array( 'incorrect_password', $err_codes ) ) {
		$error = '<strong>ERROR</strong>: The password you entered is incorrect.';
	}

	return $error;
} );
</code></pre>
> 2.위에 나온 코드를 적용시 제대로 작동하는 것 같았으나 어드민 보안 플러그인 기능 중 워드프레스 어드민 url주소를 바꿔주는 기능을 키면 global $errors를 null로 만들어 버린다.  
>  
> 3.결국 아래와 같은 코드로 변경을 했다.

<pre><code clsss="php">
add_filter( 'login_errors', function( $error ) {
    if ( ! empty($_POST['log']) ) {
        $username = $_POST['log'];
    } else {
        $username = '';
    }

    $user = get_user_by('login', $username);
    //user 정보가 있을경우만 비밀번호 체크
    if($user){
    //워드프레스에 패스워드 체크하는 함수를 한번 더 태움
        if ( !wp_check_password( $_POST['pwd'], $user->data->user_pass, $user->ID ) ){//새로운 WP_Error 객체를 만들어 에러메시지 갱신
            $errors = new WP_Error( 'incorrect_password', sprintf ('<strong>ERROR</strong>: The password you entered for the username <strong>%s</strong> is incorrect. If you lost your password, '. 'please click <a href="'.wp_lostpassword_url().'">Lost your password</a> and create new password.', $username));
            $error = $errors->get_error_message();
        }
    }

    return $error;
} );
</code></pre>

# 결론
<div class="message">
  -저위에 필터는 결국 로그인과 관련된 플러그인들을 다 거치고와서 매개변수 $error에 에러메세지를 넘겨준다.
  <br>
  -그래서 그필터안에서 핸들링해서 로긴 에러 메세지를 바꿔주면 되는 것이다.
</div>

