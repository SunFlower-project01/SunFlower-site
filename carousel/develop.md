현재 상황(무한루프는 돌아간다)
after 버튼, [4]에서 [0]으로 돌아간다.
before 버튼(미완성) [0]에서 버튼을 2번 눌렀을 때, [3]으로 감

초기 값 설정
carousel.style.transform = translate3d(-${400 \* index}px, 0,0); // 인덱스 값에 맞게 사진 위치를 이동

인덱스 값을 알맞게 조정
if (index > 0) {
index -= 1;
carousel.style.transform = translate3d(-${400 * index}px, 0,0);
        }
        if (index === 0) {
          index = total - 2;
          carousel.style.transform = translate3d(-${400 \* index}px, 0,0);
}
console.log(index);
});

디자인
이미지 조정 중(가운데, 버튼도 같이 조정)

// imgWidth를 완벽히 구현을 하고
// 액자의 길이를 변수로 빼서 구현하고
// 추가 변수 : (액자 - imgwidth ) / 2
// 자연스러운 순환

회의 주제
어떻게 분리할 것인지

<!-- navbar -->

    <!-- sidebar -->
    <!-- header -->
    <!-- main -->
        <!-- container -->
        <!-- container -->
        <!-- container -->
    <!-- footer -->