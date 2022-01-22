[![version-info](https://img.shields.io/badge/release-v0.0.1-blue)](https://github.com/hiphop5782/score/releases/latest)

# score jquery plugin

평점 표시 및 수정용 jquery plugin 입니다.

## 설치

### CDN 적용

아래 둘 중 하나를 작성

```html
<script src="https://cdn.jsdelivr.net/gh/hiphop5782/score@latest/score.js"></script>
<script src="https://cdn.jsdelivr.net/gh/hiphop5782/score@latest/score.min.js"></script>
```

### 사용법

```javascript
$(selector).score({options});
```

### sample code

```html
<!DOCTYPE html>
<html lang="ko">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>score demo</title>
    <script src="https://code.jquery.com/jquery-3.6.0.js"></script>
    <script src="https://cdn.jsdelivr.net/gh/hiphop5782/score@latest/score.min.js"></script>
    <script>
        $(function(){
            $(".test-score1").score();
            $(".test-score2").score({
                editable:true,
                integerOnly:true,
                display:{
                    showNumber:true,
                }
            });
        });
    </script>
</head>
<body>
    <div class="test-score1" data-max="5" data-rate="4.5"></div>
    <div class="test-score2" data-max="5" data-rate="3"></div>
</body>
</html>
```

## options

생성 시 옵션을 설정하여 기본 옵션을 덮어쓰기 할 수 있습니다.

기본 옵션은 다음과 같습니다.

```
{
  starColor: "gold", //별 색상
  backgroundColor: "transparent", //배경 색상
  editable: false, //점수 변경 가능 여부
  integerOnly: false, //정수만 설정 가능 여부
  zeroAvailable:false,//0 설정 가능 여부
  display: {
    showNumber: false, //설정된 숫자 표시 가능 여부
    placeLimit: 1, //소수점 자리수 표시 길이
    textColor:"gold",//텍스트 색상
  },
  point: {
    max: 5,//최대 점수(data-max로 대체 가능)
    rate: 0,//실제 점수(data-rate로 대체 가능)
  }
}
```

