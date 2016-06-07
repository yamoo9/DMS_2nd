###### DMS(Digital Marketing School), Fast Campus
# Front-End Develop Course ─ DAY 05

### 워드프레스 공부합시다!

1. [워드프레스 기본기 다지기(실습)](https://github.com/yamoo9/DMS_2nd/blob/master/DAY03/README.md#3-워드프레스-기본기-다지기실습)
1. [워드프레스 테마](https://github.com/yamoo9/DMS_2nd/blob/master/DAY04/README.md#4-워드프레스-테마)
1. [워드프레스 플러그인](https://github.com/yamoo9/DMS_2nd/blob/master/DAY04/README.md#5-플러그인)
1. [테마를 활용한 워드프레스 사이트 제작 DEMO](https://github.com/yamoo9/DMS_2nd/blob/master/DAY04/README.md#6-wordpress-웹-사이트-제작-demo)
1. [워드프레스 유료 테마](https://github.com/yamoo9/DMS_2nd/blob/master/DAY04/README.md#7-유료-테마)
1. [워드프레스 백업/복구](https://github.com/yamoo9/DMS_2nd/blob/master/DAY04/README.md#8-워드프레스wordpress-백업복구)
1. [워드프레스 호스팅/도메인 이전](https://github.com/yamoo9/DMS_2nd/blob/master/DAY04/README.md#9-호스팅도메인-이전)

-

### 워드프레스 주소 변경으로 사이트 접속문제 발생 시 해결책

일반적으로 워드프레스는 루트 디렉터리(Root Directory)에 설치되지만, 경우에 따라 `/wp`, `/wordpress` 또는 다른 경로에 설치하기도 한다. 예를 들어 웹 호스팅 서비스 신청 과정에서 **워드프레스 자동 설치 옵션**을 선택시, `/wp` 또는 `/wordpress` 경로에 설치하도록 선택하는 경우가 있다. 이럴 경우 `www.my-domain.com/wp/` 또는 `www.my-domain.com/wordpress/` 처럼 사이트 URL 주소 뒤에 하위 디렉토리 경로를 입력해야 하는 번거로움이 발생한다. 이 문제를 해결하고자 워드프레스의 관리자 페이지에서 사이트 주소를 변경할 경우 사이트 접속 문제가 발생할 수 있다. (주의!)

`알림판 > 설정 > 일반 메뉴` 아래 `워드프레스 주소(URL)`와 `사이트 주소(URL)`를 변경할 수 있는데 사이트 주소가 아닌 워드프레스 주소를 변경할 경우 오류가 발생할 수 있다.

- **워드프레스 주소(URL)** WordPress 코어 어플리케이션 파일(예: `wp-config.php`, `wp-admin`, `wp-content`, `wp-includes`)이 포함된 디렉토리의 전체 URL 주소
- **사이트 주소(URL)** 사용자들이 WordPress 사이트에 접속하기 위해 입력하는 주소로 WordPress의 메인 `index.php` 파일이 위치하는 디렉토리

만약 `/wp` 또는 `/wordpress` 하위 디렉토리에 워드프레스 코어 파일들이 위치해 있는데, 워드프레스 주소와 사이트 주소를 변경하고 저장을 누르면 사이트에서 다음과 비슷한 오류 메시지가 출력된다.

```sh
# 찾을 수 없습니다.
Not Found
# 현재 서버에서 /wp-login.php 파일을 찾았다는 응답이 없습니다.
The requested URL /wp-login.php was not found on this server.
```

오류에 당황한 후, 사이트에 접속해보면 다음 오류 메시지와 유사한 메시지가 웹 브라우저에 출력된다.

```sh
# 출입금지!
Forbidden
# 현재 서버의 루트(/)에 접근 권한이 없습니다.
You don't have permission to access / on this server.
```

처음 워드프레스를 사용한다면? 이런 상황에 몹시 당황하게 된다. 이 경우 다음과 같은 방법으로 다시 원래 상태로 복구할 수 있다.

#### 데이터베이스(DB) 복원

대부분의 웹 호스팅 업체에서 기본 서비스로 데이터베이스(DB) 복원 기능을 제공한다. Cafe24의 경우 자신의 계정에 로그인한 후,
**DATA&DB복원/백업** 메뉴를 통해 이전 상태로 복원이 가능하다.

DB 복원 기능을 제공하는 경우 이 방법으로 쉽게 복원할 수 있다. 다른 웹 호스팅 서비스도 비슷한 기능을 제공할 것이다.
두 번째 방법을 사용하기 전에 DB 복원이 가능한지 확인해본다.

#### 사이트 접속 문제 발생 시, DB를 복구하지 않고 임시로 문제를 해결하는 방법

위에서 설명한 방법이 정상적인 복구 방법이지만, DB 접속이 어려울 경우 임시 방법으로 문제를 해결 할 수 있다. FTP에 접속하여 `wp-config.php` 파일을 열어
`// ** MySQL settings – You can get this info from your web host **` 라인 바로 위에 아래 코드를 추가한다.

```php
// 자신의 도메인 이름 뒤에 하위 디렉토리 이름을 추가한다.

// 워드프레스 주소(URL)
define('WP_HOME','http://www.my-domain.com/wordpress');
// 워드프레스 사이트 주소(URL)
define('WP_SITEURL','http://www.my-domain.com/wordpress');
```

이렇게 하면 URL 주소를 변경하기 전으로 돌릴 수 있다. 이를 저장하고 업로드한 후 워드프레스 사이트에 접속하면 정상적으로 접속될 것이다.
다만... 사이트 URL 주소와 워드프레스 URL 주소 설정은 편집할 수 없어진다. 이 방법은 어디까지나 임시 복구 방법임을 기억하라.



<!-- http://hwangc.com/how-to-move-wordpress-site-3-different-cases -->
<!-- http://www.thewordcracker.com/basic/how-to-backup-wordpress-site/ -->
<!-- http://www.thewordcracker.com/basic/how-to-backup-wordpress-site-2/ -->

<!-- 워드프레스 청소하고 퍼포먼스
http://hwangc.com/cleanup-wordpress/ -->

<!-- 워드프레스 주소 변경으로 사이트에 접속하지 못하는 문제 해결
http://www.thewordcracker.com/basic/how-to-solve-problems-after-changing-the-site-url-in-wordpress/ -->