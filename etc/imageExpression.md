# html에서 이미지를 사용하는 세 가지 방법(svg)

<br />
<br />

1. body 태그 내에서 img 태그 사용하기

2. css에서 배경이미지로 사용하기

3. svg 태그 사용하기
<br />
svg 파일을 열어보면 svg 태그로 표현되어있다.<br />
이를 복사해서 사용할 수 있다.<br />
이 방식의 장점은 aria-label이나 fill 등을 수정할 수 있어 control할 수 있는 부분이 많아진다.<br />
다만 line이 길어 관리가 힘들어진다는 특징이 있다. 용량에는 차이가 없다.<br />
이를 위해 icon font를 사용할 수 있다.<br />
svg를 font로 변환해 주는 여러 서비스들이 있는데, 아래의 사이트를 사용하였다.<br />
[icomoon](https://icomoon.io/app/#/select)