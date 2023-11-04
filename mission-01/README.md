# mission-01

## HTML
- div.container (전체 박스)
  - article.box CardLinkWide (따뜻한 차 향기)
    - div.wide-title (가로 배치를 위한 div 처리)
      - h1 > img (오뚜기 로고 삽입)
      - p ("따뜻한 차 향기" 입력)
    - button.purchase-btn(구매하기 버튼 생성) > span.icon-angle-right (fontnello 활용하여 ">" 삽입)
  - article.box CardLinkNormal (핸드크림 모음)
    - h1 > img (카밀 로고 삽입)
    - p ("핸드크림 모음" 입력)
    - button.purchase-btn(구매하기 버튼 생성) > span.icon-angle-right (fontnello 활용하여 ">" 삽입)
  - article.box CardLinkNormal (고소한 보리차)
    - h1 > img (곰곰 로고 삽입)
    - p ("고소한 보리차" 입력)
    - button.purchase-btn(구매하기 버튼 생성) > span.icon-angle-right (fontnello 활용하여 ">" 삽입)
  - h1 안에 로고 이미지를 삽입한 이유는 "따뜻한 차 향기", "핸드크림 모음", "고소한 보리차" 이 세 개의 텍스트 보다 로고 자체가 제목의 느낌이 더 강하여 로고 이미지 태그를 h1 태그로 감쌈

## CSS

- 노멀라이즈 사용하지 않고 reset.css 활용하여 초기화
  - box-sizing:border-box / font-size:100% / font-weight:400 / margin:0 / padding:0 등등

- body (.CardLinkWide, .CardLinkNormal 요소 가운데 정렬)
  - display: flex;
  - justify-content: center;

### 전체 박스 배치
- div.container
  - [브라우저와의 일정 간격 유지]
    - margin-top: 50px;
  - [텍스트 관련]
    - font-family: 'Noto Sans KR', sans-serif; (Noto Sans KR 폰트 사용, 없을 시 sans-serif)
    - font-weight: 700; ("따뜻한 차 향기", "핸드크림 모음", "고소한 보리차" 텍스트 요소 굵기 설정)
    - color: #4e4e4e; (글자 색 설정)
    - text-align: center; (텍스트 요소 가운데 정렬)
  - [전체 박스 너비 고정]
    - width: 502px;
  - [3개 article 배치]
    - display: flex;
    - flex-flow: row wrap; (row 방향으로 랩핑)
    - justify-content: space-between; (전체 박스 너비 값 502px 고정된 상태로 상단 article.CardLinkWide는 고정된 상태에서 나머지 article.CardLinkNormal 박스 2개 가운데 여백 준 상태로 가로 정렬됨)

### 각 article 공통 클래스
- article.box
  - [테두리 설정]
    - border: 1px solid #c4c4c4; (1px 실선 회색 테두리 처리)
  - [구매하기 버튼 배치를 위한 position: relative 처리]
    - position: relative;
- article.box p
  - margin: 0 auto; (글자 가운데 정렬)
  - width: 200px; (시안과 동일한 너비 200px 고정)
- article.box h1
  - line-height: 0.8; (로고 이미지와의 라인 높이 맞춤)

### 상단 article
- .CardLinkWide
  - width: 502px; (너비 값 전체 박스 컨테이너와 동일하게 설정)
  - font-size: 24px;
  - [오뚜기 로고 이미지, 텍스트, 꿀생강차 이미지 배치]
    - display: flex;
    - justify-content: space-between;
  - padding: 20px 28px; (안쪽 여백 지정)
  - margin-bottom: 16px; (하단 article과의 간격 설정)

- .CardLinkWide .wide-title (오뚜기 로고 및 텍스트 요소 배치)
  - display: flex;
  - flex-flow: column;
  - justify-content: center;
  - padding-bottom: 42px; (위로 배치하기 위해 안쪽 여백 42px 설정)

- .CardLinkWide p 
  - margin-top: 13px; (시간와 동일하게 로고와 텍스트 사이의 간격 조정)

### 하단 article
- .CardLinkNormal
  - width: 243px; (시안과 동일하게 article 2개 사이 간격 16px 주기 위해 각각 너비 243px 지정)
  - padding: 14px 0; (상,하단 14px 안쪽 여백 지정)
  - font-size: 18px; ("핸드크림 모음", "고소한 보리차" 텍스트 요소 사이즈 지정)
  - height: 310px;

- .CardLinkNormal p 
  - margin-top: 10px; (시안과 동일하게 로고와 텍스트 사이의 간격 조정)
  - margin-bottom: 7px; (시안과 동일하게 텍스트와 제품 이미지 사이의 간격 조정)

### 구매하기 버튼
- .purchase-btn 
  - white-space: nowrap; (해당 속성 사용하지 않을 시 "구매하기" 텍스트가 뭉쳐졌다 펼쳐지는 현상 발생하여 nowrap 지정)
  - position: absolute; (부모 요소 article.box의 position: relative 설정 후 버튼 position: absolute 설정)
  - left: 20px;
  - bottom: 20px;
  - width: 42px;
  - height: 42px;
  - border: none;
  - color: #fff;
  - background: lightgray;
  - cursor: pointer; (포커스 효과 설정)
  - transition: 100ms; (자연스럽게 펼쳐지게 하기 위해 transition 설정)

- .purchase-btn:hover 
  - width: 112px;
  - background: #0074e9;

- .purchase-btn:hover::before 
  - content: "구매하기"; ("구매하기" 텍스트는 가상요소 사용)

