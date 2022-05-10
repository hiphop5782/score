[![version-info](https://img.shields.io/badge/release-v0.0.2-blue)](https://github.com/hiphop5782/score/releases/latest)

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

Result : [https://hiphop5782.github.io/score/demo/example.html](https://hiphop5782.github.io/score/demo/example.html)

```html
<!DOCTYPE html>
<html lang="ko">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>score demo</title>
    <script src="https://code.jquery.com/jquery-3.6.0.js"></script>
    <script src="https://cdn.jsdelivr.net/gh/hiphop5782/score@latest/score.js"></script>
    <script>
        $(function(){
            $(".test-score1").score();
            $(".test-score2").score({
                editable:true,
                display:{
                    showNumber:true,
                    placeLimit:2
                }
            });
            $(".test-score3").score({
                editable:true,
                integerOnly:true,
                display:{
                    showNumber:true
                }
            });
        });
    </script>
</head>
<body>
    <div class="test-score1" data-max="5" data-rate="4.5"></div>
    <hr>
    <div class="test-score2" data-max="5" data-rate="3"></div>
    <hr>
    <div class="test-score3" data-max="5"></div>
</body>
</html>
```

## options

생성 시 옵션을 설정하여 기본 옵션을 덮어쓰기 할 수 있습니다.

기본 옵션은 다음과 같습니다.

```javascript
{
    starColor: "gold", //별 색상
    backgroundColor: "transparent", //배경 색상
    editable: false, //점수 변경 가능 여부
    integerOnly: false, //정수만 설정 가능 여부
    zeroAvailable:false,//0 설정 가능 여부
    send:{
        sendable:false,//전송 가능 여부
        name:"star",//전송 가능할 경우 전송될 이름
    },
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

### starColor (String)
별 모양의 배경 색상을 CSS String 형태로 지정
- rgb()
- rgba()
- hex string
- hsl()
- hsla()

### backgroundColor (String)
배경 색상을 CSS String 형태로 지정
- rgb()
- rgba()
- hex string
- hsl()
- hsla()

### editable (Boolean)
수정 가능 여부를 true/false로 설정

- true : 수정 가능
- false : 수정 불가

### integerOnly (Boolean)
점수를 정수로만 관리할 것인지를 true/false로 설정

- true : 정수로만 표시. 소수점 미만은 반올림 처리
- false : 소수점을 허용

### zeroAvailable (Boolean)

0을 설정할 수 있도록 할 것인지를 true/false로 설정

- true : 0 설정을 가능하도록 처리
- false : 0 설정을 불가능하도록 처리. 0 설정시 0.1로 변경

### send (Object)
전송과 관련된 설정
- sendAvailable (Boolean) : 전송 가능 여부를 true/false로 설정
- name (String) : 전송될 이름을 설정

### display (Object)
표시와 관련된 설정
- showNumber (Boolean) : 숫자를 표시할 것인지를 true/false로 설정
- placeLimit (Number) : 표시할 소수점 자리수를 설정(1 - 한자리, 2 - 두자리)
- textColor (String) : 표시될 숫자의 글자색을 CSS String으로 설정

### point (Object)
- max (Number) : 설정할 최대 점수(data-max로 대체 가능)
- rate (Number) : 설정할 실제 점수(data-rate로 대체 가능)