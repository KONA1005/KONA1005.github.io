---
title: "[BLOG] 에러났나 확인용 "
date: 2022-06-27-01
categories: BLOG
---

# STS에서 Git을 연동했다
git연동 후 commit 또는 push를 할 때 sts에서 login이 뜨고 
id, password입력시 더이상 화면이 넘어가지 않고 결국 실패햇다.

찾아보니 git에서 토큰을 받아 설정하면 된다고 하여 설정해줬다.

그 **후** 본래 포스팅을 하려 글을쓰고 VS에서 git push하니 오류발생
>git config --global user.name '아이디'
>git config --global user.password '받았던 깃토큰'

입력 후 git push하니 정상적으로 잘 올라감을 확인했다.