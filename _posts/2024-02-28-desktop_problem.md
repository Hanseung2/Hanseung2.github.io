---
layout: single
title:  "[Git] Git Desktop의 문제와 Jekyll 블로그의 Liquid syntax error"
categories: Git
---

### 문제점

- Github Desktop을 통해 Java 2차원 배열 코드를 포스팅 했을 때, 잘 commit 되고 push 까지 되어 문제가 없는 줄 알았는데 블로그에 포스팅되지 않았다.
- PowerShell 을 이용해 `localhost : 4000` 을 열려고 보니 다음과 같은 Liquid syntax error 가 떴다.

![](/assets/images/20240228/error.JPG)

<br/>

<hr/>

### 원인

구글링해보니 Jekyll blog에서 사용되는 liquid는 `{% raw %}{{{% endraw %}` 와 `{% raw %}}}{% endraw %}` 를 escape 문자로 사용하여 2024-02-27-java03.md의 2차원 배열 코드에 있는 `{% raw %}{{{% endraw %}` 와`{% raw %}}}{% endraw %}` 이 에러 메시지를 유발했다.

> Github Desktop이 Git을 관리하기 편한 거 같아 이용했는데, 오류를 찾아주지 않는 것이 조금 아쉬웠다. Git Bash 를 이용해야 하나 고민이 됐다.

<br/>

<hr/>

### 해결

![](/assets/images/20240228/solve.JPG)

다음과 같이 2차원 배열을 선언할 때 다음과 같은 raw tag를 사용하면 오류가 나지 않는다. (앞에 raw를 뒤에 endraw) 

