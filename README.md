# Server to server integration

"뉴스펍"을 선택해 주셔서 감사합니다.<br>
시작하기 위해 제휴를 통해 계정을 발급 받아야 합니다.<br>
아래 메일을 통해 계정을 발급 받으세요.<br>

> 제휴메일 : <newspub@adxcorp.kr>

# 유의사항
> 웹뷰 노출 시 JavaScript를 활성화 해주지 않으면 수익이 발생하지 않을 수 있습니다.<br>
> 빈번한 요청은 계정이 Block 될 수 있습니다.

# Request (Method : GET)

Status|URL
:---:|:---:
TEST|http://wwwt.newspub.kr/ax/rss
LIVE|http://www.newspub.kr/ax/rss

Parameter|Mandantory|Description
:---:|:---:|:---:
aid|O|발급받은 계정 아이디
mid|O|발급받은 매체 아이디

# Response

```

# Response sample.

{
  result: 0,
  message: "Success",
  data: {
    title: "뉴스펍 - 애드엑스",
    link: "http://wwwt.newspub.kr",
    description: "맞춤화 된 실시간 뉴스를 만나보세요.",
    items: [
    {
      _id: "60d00309c6e69076217bdeb0",
      link: "http://wwwt.newspub.kr/content/60d00309c6e69076217bdeb0?rss=1&aid=607ce2d50d0653603e95dd40&mid=607e5f007f88ba08cb651f93",
      category_name: "매거진",
      title: "전설적인 클래식카 탈보-라고 T26이 8월 경매에 나온다",
      author: "IMBOLDN",
      image: "https://kr.imboldn.com/wp-content/uploads/2021/06/1948-Talbot-Lago-T26-Record-Sport-Cabriolet-Decapotable-main-800x450.jpg",
      description: "이제 세상에 단 2대만이 남은 클래식카의 레전드 오브 레전드. The post 전설적인 클래식카 탈보-라고 T26이 8월 경매에 나온다 appeared first on 임볼든(IMBOLDN). ",
      pub_date: "2021-06-21 02:00"
    },
    {
      _id: "60d00309c6e69076217bdeb1",
      link: "http://wwwt.newspub.kr/content/60d00309c6e69076217bdeb1?rss=1&aid=607ce2d50d0653603e95dd40&mid=607e5f007f88ba08cb651f93",
      category_name: "매거진",
      title: "양면을 원해, 거치 가능한 젠스 마그네틱 듀얼 보조 배터리",
      author: "IMBOLDN",
      image: "https://kr.imboldn.com/wp-content/uploads/2021/06/Zens-Magnetic-Dual-Powerbank-with-Stand-main-800x450.jpg",
      description: "한쪽이 노는 꼴은 못 보지. The post 양면을 원해, 거치 가능한 젠스 마그네틱 듀얼 보조 배터리 appeared first on 임볼든(IMBOLDN). ",
      pub_date: "2021-06-21 00:00"
    }, ...]
  }
}

```
### 반복되는 items 하위 항목에 대한 정의.

Parameter|Mandantory|Description
:---:|:---:|:---:
_id|O|아이디
link|O|URL
category_name|O|카테고리 정보
title|O|제목
author|O|소유자
image|X|대표이미지
description|O|설명
pub_date|O|배포일자
