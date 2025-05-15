---
layout: post
title:  "OWASP Top10 분석"
date:   2025-05-15
category: Design
image: assets/img/blog/blog6.jpg
author: Eunseoim
tags: Jekyll
---

> SQL Injection은 웹 보안 역사상 가장 오래되었지만 여전히 위협적인 취약점입니다. 이 글에서는 SQL Injection의 개념과 원리, 주요 유형, 대응 방안을 중심으로 설명합니다.
---
## 1. SQL Injection이란?
**SQL Injection**(SQL 삽입)은 웹 애플리케이션에서 사용자 입력값이 제대로 필터링되지 않고 SQL 쿼리에 삽입될 때 발생하는 보안 취약점입니다. 공격자는 이 취약점을 통해 데이터베이스를 조작하거나, 비인가된 정보를 조회할 수 있습니다.
---
## 2. 어떤 문제가 발생할까?
SQL Injection은 다음과 같은 공격을 가능하게 만듭니다:
- 로그인 우회 (비밀번호 없이 관리자 로그인)
- 민감한 정보 유출 (사용자 ID, 비밀번호 등)
- 데이터베이스 조작 (삽입, 수정, 삭제)
- 시스템 명령 실행 (DBMS에 따라 가능)
이는 단순한 버그 수준을 넘어, **전체 시스템의 신뢰성 붕괴로 이어질 수 있는 심각한 보안 사고**입니다.
---
## 3. 어떻게 발생하나?
주로 개발자가 사용자 입력값을 SQL 쿼리에 **직접 연결(concatenation)** 하는 방식으로 처리할 때 발생합니다. 예를 들어 아래와 같은 코드가 있다면:
```sql
SELECT * FROM users WHERE username = '[사용자 입력]';
---

```ruby
def print_hi(name)
  puts "Hi, #{name}"
end
print_hi('Ryan')
#=> prints 'Hi, Ryan' to STDOUT.
```
