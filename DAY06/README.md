###### DMS(Digital Marketing School), Fast Campus
# Front-End Develop Course ─ DAY 06

1. [테마를 활용한 워드프레스 사이트 제작 DEMO](https://github.com/yamoo9/DMS_2nd/blob/master/DAY04/README.md#6-wordpress-웹-사이트-제작-demo)
1. [워드프레스 유료 테마](https://github.com/yamoo9/DMS_2nd/blob/master/DAY04/README.md#7-유료-테마)
1. [워드프레스 백업/복구](https://github.com/yamoo9/DMS_2nd/blob/master/DAY04/README.md#8-워드프레스wordpress-백업복구)
1. [워드프레스 호스팅/도메인 이전](https://github.com/yamoo9/DMS_2nd/blob/master/DAY04/README.md#9-호스팅도메인-이전)

-

### 워드프레스에 Facebook 메타(Meta) 정보 삽입

페이스북에 컨텐츠 링크를 입력하면 자동으로 컨텐츠의 썸네일, 제목, 요약글 등을 읽어들이는 경우를 볼 수 있다.
이는 페이스북에서 요구하는 메타 정보를 사이트에서 제공하고 있기 때문이다. 이에 대해 공부해보자.

-

### 플러그인 활용 방법

아래 플러그인은 소셜 네트워크의 메타 정보를 자동으로 소스에 넣을 수 있는 기능을 제공한다.

- [All in one SEO](https://wordpress.org/plugins/all-in-one-seo-pack/)
- [Yoast SEO](https://wordpress.org/plugins/wordpress-seo/)
- [NextGEN Facebook](https://wordpress.org/plugins/nextgen-facebook/)

-

### 테마에 직접 메타 정보 작성

페이스북에 링크를 붙여넣으면 물결 로딩이 표시되고 그와 동시에 페이스북 로봇이 붙여진 링크를 따라 들어와
페이스북 메타 정보(open graph: `og`)를 가지고 간다. `og` 메타 정보가 없는 경우에는 임의로 이미지,
타이틀 등을 긁어갈 수 있으니 `og`를 워드프레스에 심어 페이스북에게 정확한 정보를 제공하는 것이 좋다.

-

### OG(오픈 그래프) 정보

[페이스북 OG 소개](https://developers.facebook.com/docs/sharing/opengraph) 글 참고.

1. `og:title` ─ 컨텐츠 제목
1. `og:type` ─ 컨텐츠 타입
1. `og:image` ─ 컨텐츠 특성 이미지
1. `og:url` ─ 컨텐츠 URL
1. `og:description` ─ 컨텐츠 내용
1. `og:site_name` – 사이트 이름


**header.php**

```php
<?php
// #1. 보여줄 포스트/페이지/홈 조건 설정
// 참고 URL: http://codex.wordpress.org/Conditional_Tags
// is_single() : 포스트
// is_page()   : 페이지
// is_home()   : 홈페이지
if (is_single()) {

  global $post;

  if(get_the_post_thumbnail($post->ID, 'thumbnail')) {
    $image = wp_get_attachment_url( get_post_thumbnail_id($postID) );
  } else {
    // #2. 썸네일 이미지가 없을 경우, 보여줄 아미지 경로 추가
    $image = '';
  }
  $description = get_bloginfo('description');
  $description = yamoo9_excerpt( $post->post_content, $post->post_excerpt );
  $description = strip_tags($description);
  $description = str_replace("\"", "'", $description);
?>
<meta property="og:title" content="<?php the_title(); ?>">
<meta property="og:type" content="article">
<meta property="og:image" content="<?php echo $image; ?>">
<meta property="og:url" content="<?php the_permalink(); ?>">
<meta property="og:description" content="<?php echo $description ?>">
<meta property="og:site_name" content="<?php echo get_bloginfo('name'); ?>">
<?php
}
?>
```

**functions.php**

```php
function yamoo9_excerpt($text, $excerpt){
  $raw_excerpt = $text;
  if ($excerpt) return $excerpt;
  return apply_filters('wp_trim_excerpt', $text, $raw_excerpt);
}
```

-

### 현재 년도 화면에 출력

```php
<address>Copyright &copy; <?php the_time('Y'); ?>, <a href="http://yamoo9.net/">yamoo9.net</a>. All Right Reverved.</address>
```