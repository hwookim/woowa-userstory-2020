# 공공자원 예약 서비스 (가제)

## 서비스 설명

한정적인 특정 자원에 대해 대표 사용자의 설정에 맞춰 나머지 사용자가 예약할 수 있도록 하는 서비스

기존에 우테코에서 사용하던 '회의실 내껀데'와 비슷한 구조로 작동

대표 사용자는 공유할 자원과 예약 방법에 대해 설정할 수 있음  
대표 사용자는 최대 예약 시간, 연장 가능 여부, 사용 불가 시간 등을 지정 가능

사용자는 관리자가 제공하는 uri를 통해 자원에 접근함  
현재 예약 현황, 예약 가능 시간 등을 조회하고 예약할 수 있음

## Persona #1

- 대학 밴드 동아리 회장

- 문제 상황

동아리 전용 합주실을 사용하는데 동아리 내 밴드가 여러 팀이라 시간 분배가 힘듬  
현재는 단체 카톡방 내 게시글에 댓글을 써두는 형식으로 관리함  
게시글에 예약 양식을 기재했지만 각자 마음대로 써서 한눈에 들어오지 않음  
한 팀이 너무 오랜 시간 예약을 했는데 사전에 파악할 수 없었음  
동아리 행사로 인해 합주 불가능한 시간이 있는데 자꾸 그 시간에 예약함  
합주실을 사용한 뒤에 정리하지 않고 예약 댓글을 지워 청소 책임을 회피하려 함

- 요구 사항

합주실 사용 예약을 시간별로 관리할 수 있으면 좋겠음  
공연 전에는 공연팀들만 합주실을 사용하게 하고 싶음  
예약 가능 회수 / 시간을 강제하고 싶음  
예약 불가능한 시간을 강제하고 싶음  
특정 시간의 사용자가 누군지 알고 싶음  

- 기대 효과

합주실 예약 시간을 편하게 관리할 수 있음

## Persona #2

- 대학 밴드 동아리 부원

- 문제 상황

합주실을 예약하려는데 어느 시간이 비어있는지 잘 모르겠음  
내가 사용하고 싶은 시간이 사용 가능한 시간인지 알기 힘듬  
이미 예약자가 있다면 양해를 구하고 예약 시간을 변경하고 싶은데 누가 예약한건지 모르겠음  
다음 예약한 사람이 없으면 연장해서 사용하려는데 찾기 힘듬  

- 요구 사항

예약 가능 시간을 조회하고 싶음  
특정 시간의 예약자를 조회하고 싶음  

- 기대 효과

합주실을 편하게 예약할 수 있음

## 시나리오

대학 밴드동아리 회장 정상국 씨는 올해 신입 부원들에게 합주실 사용 방법을 공지하고 예약 서비스 링크를 보낸다. 신입 동아리원 김현우 씨는 해당 링크로 접속해 SNS 아이디로 손쉽게 가입한다.

현우 씨는 예약 가능 시간을 확인하고 양식에 맞춰 원하는 시간에 예약한다. 현우 씨네 팀이 원하는 시간에 이미 예약자가 있었다. 하지만 밴드 원들이 가능한 시간이 그때 뿐이라 먼저 예약한 사람에게 연락해 양해를 구하고 예약 할 수 있었다.  
현우 씨네 밴드 연습 중 약속이 있던 팀원의 약속이 취소되어 좀 더 연습을 할 수 있게 되었다. 확인해보니 뒤에 예약자가 없어 연장 신청을 하고 더 연습했다.    

동아리 공연이 다가와 공연 팀들의 연습 시간이 더 필요하다고 생각한 상국 씨는 공연 팀만 예약할 수 있도록 설정했다.  
합주실과 같은 건물에서 교내 연극부의 연극이 있어 합주를 자제해달라는 연락을 받은 상국 씨는 해당 시간에 예약할 수 없도록 설정했다.  
동아리 내 밴드가 많아져 상국 씨는 합주실을 추가로 대관하기로 했다. 상국 씨는 동아리원들에게 알리고 예약 가능 목록에 합주실2를 추가하여 예약 현황을 관리했다.  

## 시나리오에 따른 요구사항

| 시나리오 	| 요구사항 	|
|-	|-	|
| 대학 밴드동아리 회장 정상국씨는 올해 신입 부원들에게 합주실 사용 방법을 공지하고 예약 서비스 링크를 보낸다.<br>신입 동아리원 김현우씨는 해당 링크로 접속해 sns아이디로 손쉽게 가입한다. 	| - 관리자가 공유 가능한 URL을 생성할 수 있어야 한다.<br>- 사용자는 URL을 통해 자원에 접근할 수 있어야 한다.<br>- 사용자는 sns로 가입할 수 있어야 한다. 	|
| 현우 씨는 예약 가능 시간을 확인하고 양식에 맞춰 원하는 시간에 예약한다. 	| - 사용자는 예약 가능 시간을 조회할 수 있다.<br>- 관리자는 예약에 필요한 양식을 지정할 수 있다.<br>- 사용자는 빈 시간에 예약할 수 있다. 	|
| 현우 씨네 팀이 원하는 시간에 이미 예약자가 있었다.<br>하지만 밴드 원들이 가능한 시간이 그때 뿐이라 먼저 예약한 사람에게 연락해 양해를 구하고 예약 할 수 있었다. 	| - 사용자는 특정 시간의 예약 현황을 조회할 수 있다.<br>- 사용자는 특정 시간의 예약자를 조회할 수 있다.<br>- 사용자는 특정 시간 예약자의 연락처를 조회할 수 있다. 	|
| 확인해보니 뒤에 예약자가 없어 연장 신청을 하고 더 연습했다. 	| - 사용자는 예약 시간을 연장할 수 있다. 	|
| 공연 팀만 예약할 수 있도록 설정했다. 	| - 관리자는 예약이 가능한 사람을 설정할 수 있다. 	|
| 해당 시간에 예약할 수 없도록 설정했다. 	| - 관리자는 예약이 불가능한 시간을 설정할 수 있다. 	|
| 예약 가능 목록에 합주실2를 추가하여 예약 현황을 관리했다. 	| - 관리자는 예약 가능한 자원을 추가하거나 삭제할 수 있다. 	|
