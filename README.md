# Capstone-DB
Database for Capstone Project

## Collections

### 1. users(유저 정보)   
 * nickname(PK): 기본키 설정은 고유인덱스를 이용   
 &rarr; 중복된 데이터 삽입 시 에러(그전에 삽입된 데이터는 모두 삽입됨)   
 * userid   
 * kakaoemail   
 * token   
 * type: P or C   
 * agerange   
 * friend   

### 2. chats(채팅 로그)   
 * nickname(PK): 기본키 설정은 고유인덱스를 이용   
 &rarr; 중복된 데이터 삽입 시 에러(그전에 삽입된 데이터는 모두 삽입됨)   
 * userid   
 * kakaoemail   
 * token   
 * type: P or C   
 * agerange   
 * friend   
   
## chatroom   
-채팅 내역 로그형식으로 저장   
->서브 도큐먼트로 저장: 날짜+시간 속성을 기본키로 설정하여 불러올 때 편리함 추구   
-> TTL 인덱스를 사용하여 일정기간이 지날때마다 로그를 삭제하여 데이터공간을 관리   
-myNick+friNick이 기본키   
-사진 디렉토리를 로그 속성으로 추가   
   
## Business Model Suggestion
 1. 사진을 서버에 영구저장->과금 필요   
 2. 채팅방 생성 개수 제한->제한을 풀려면 돈 내!   
