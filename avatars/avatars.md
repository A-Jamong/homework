
>커밋순서 / 의문점 기록 / 과제를 하다보니 느낀 점   
## 커밋순서
- **초기 세팅 - 이미지 저장**   

- **이미지 파일 이름 오류 수정**
- **기본적인 설정 적용 (프로필 크기, 간격, 배경색)**    
: profile-item 에 프로필 사진\<img>과 온오프 상태를 보여줄 status-online/offline 을 포함했다.   
: profile-item 의 img 에 border radius 적용
- **float을 이용해 수직 정렬**   
: 프로필 4개씩 그룹1,2로 묶은 다음에 float:left, clear:both 이용해서 수직으로 정렬해줬다.   
: 프로필 컨테이너에 display: flow-root 를 이용해서 float으로 뜬 프로필을 인식하고 border로 외곽선을 줬다.
- **position 이용해서 상태 정보 위치 변경**   
: 온오프 상태를 프로필 이미지 위로 올려줘야 하니까 프로필 사진과 상태를 포함하고 있는 item은 position:relative, 온오프 상태는 position:absolute와 left, top을 줘서 위치를 변경했다.
- **support이용해 flex가 지원되는 환경에서는 flex를 사용할 수 있게 추가**   
: flex가 지원되는 환경에서는 float를 전부 none으로 변경하고 대신 display:flex를 추가.    
: 이번에는 남자 그룹이 위로 와야 하기 때문에 group1(여자 그룹)에 order:2, group2(남자 그룹)에 order:1을 줘서 정렬을 바꿔줬다.
- **특정 프로필은 오프라인 상태로 보이게 변경**   
: 아이템 전부에 online 상태를 넣어줬었기 때문에 몇개의 아이템에는 offline으로 변경했다. 
- **alt, aria-label 작성**   
: 프로필마다 여자 프로필, 남자 프로필로 alt를 작성하고 온라인, 오프라인 상태를 알 수 있게 status-online/offline 에 aria-lable="온라인/오프라인" 을 줬다. 

## 의문점 기록
**의문1.**    
그룹을 이용해서 4개씩 나눠줬는데 이게 아니라 컨테이너의 기본 사이즈를 정해두고 화면이 줄어들면 줄어드는 컨테이너 사이즈에 맞게 자식들(프로필)이 다음줄로 넘어가게 하는 걸 해보고 싶다.

**의문1-1.**    
flex 로 하면 flex-wrap 으로 프로필 컨테이너의 width를 넘기면 넘어가게 할 수 있을 것 같은데 그러면 프로필 컨테이너의 max-width를 정해두고 화면이 좁아지면 줄어들게 하면 되나? + 근데 남자(5~8)부터 올려야 하는데 이 경우 어떻게 하지. wrap-reverse 로 위로 올려도 되나?

**의문2.**   
프로필 컨테이너가 안에 있는 프로필만큼의 공간을 가진 채로 보더를 주고 싶은데 어떻게 해야할까.   
  => width : fit-content 로 해결.   
  *+* display : flow-root 로 프로필을 인식 못 해서 보더가 안 보이는 것도 해결.

**의문3.**   
이미지 순서대로 첫번째 여자 프로필 식으로 alt를 적다보니 의문. 만약 프로필끼리 순서가 바뀌면 어떻게 동적으로 바꿔서 읽어주지? 인덱스랑 $ 로 어떻게 될 것 같은데.    
=> 자바스크립트, script를 이용해서 aria-label을 업데이트 해줄 수 있다고 한다. (후에 공부 필요)

**의문4.**   
role = listiem 도 적어뒀는데 목록 항목. 이라고 까지 읽어주는데 이런 부분은 어떻게 해야할지 고민이다. 

**의문5.**    
온라인, 오프라인 상태가 동적으로 변하니까 리스트 아이템에 여자 프로필, 온라인 으로 한꺼번에 아리아 라벨을 주는 건 부적절할 것 같다. 

## 과제를 하다보니
확실히 아직 html, css 에 대해서 수업을 쫙 빨아들이진 못 한 것 같다. 그래도 과제하면서 지금까지 배웠던 것들이 머리에서 둥둥 떠다니다 조금 윤곽이 잡히는 느낌? 재밌다! 😆

