# Server to server integration

"뉴스펍"을 선택해 주셔서 감사합니다.<br>
시작하기 위해 제휴를 통해 계정을 발급 받아야 합니다.<br>
아래 메일을 통해 계정을 발급 받으세요.<br>

연동 매체정보 및 제휴내용을 함께 보내주시면 보다 빠른 처리가 가능합니다.

> 제휴메일 : <newspub@adxcorp.kr>

# 유의사항
> 웹뷰 노출 시 JavaScript를 활성화 해주지 않으면 수익이 발생하지 않을 수 있습니다.<br>
> 빈번한 요청은 계정이 Block 될 수 있습니다.<br>
> 데이터는 10분 마다 갱신됩니다.<br>
> RSS 요청시 데이터는 기본 200개씩 제공되나, 중복클릭율이 높거나, 사용자 별 발생 클릭수가 많으면 제한 될 수 있습니다.<br>
> 제공 되는 기사는 최신기사 위주로 노출해야 합니다. 2일 전 기사는 적립이 되지 않습니다. (운영에 착오없길 바랍니다.)

# Request (Method : GET)

Status|URL
:---:|:---:
TEST|https://wwwt.newspub.kr/api/rss
LIVE|https://www.newspub.kr/api/rss

Parameter|Mandantory|Description
:---:|:---:|:---:
aid|O|발급받은 계정 아이디
mid|O|발급받은 매체 아이디
cat|X|요청 카테고리(값이 없는경우 전체 카테고리)<br>여러 카테고리 요청시엔 comma(,)로 구분<br>예) 1,2,3<br>카테고리표 하단 참조

# Request sample
https://www.newspub.kr/api/rss?aid={발급받은AID}&mid={발급받은MID}&cat={원하는카테고리,없으면전체카테고리}

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
      link: "http://wwwt.newspub.kr/content?nid=60d5b028c26d38571259b2e6&rss=1&aid=6090a3918428577c038d1161&mid=607e5f007f88ba08cb651f93",
      category_name: "매거진",
      title: "전설적인 클래식카 탈보-라고 T26이 8월 경매에 나온다",
      author: "IMBOLDN",
      image: "https://kr.imboldn.com/wp-content/uploads/2021/06/1948-Talbot-Lago-T26-Record-Sport-Cabriolet-Decapotable-main-800x450.jpg",
      description: "이제 세상에 단 2대만이 남은 클래식카의 레전드 오브 레전드. The post 전설적인 클래식카 탈보-라고 T26이 8월 경매에 나온다 appeared first on 임볼든(IMBOLDN). ",
      pub_date: "2021-06-21 02:00"
    },
    {
      _id: "60d00309c6e69076217bdeb1",
      link: "http://wwwt.newspub.kr/content?nid=60d5af5fc26d38571259b2e2&rss=1&aid=6090a3918428577c038d1161&mid=607e5f007f88ba08cb651f93",
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

Key|Key|Key|Mandantory|Description
:---:|:---:|:---:|:---:|:---
result|||O|응답 코드
message|||O|응답 메세지
data|||O|응답 데이터
||title||O|Rss 제목
||link||O|사이트 주소
||description||O|Rss 설명
||items||O|Rss Asset (Array)
|||_id|O|아이디
|||link|O|URL
|||category_name|O|카테고리 정보
|||title|O|제목
|||author|O|소유자
|||image|X|대표이미지
|||description|O|설명
|||pub_date|O|배포일자

# 응딥 코드 (result)
Code|Description
:---:|:---:
0|Success
400|Bad Request

# 카테고리 코드
Code|Description
:---:|:---:
1|사회
2|정치
3|연예
4|스포츠
5|매거진
6|생활/문화
7|경제
8|재테크
9|IT/과학
10|주식
11|해외
