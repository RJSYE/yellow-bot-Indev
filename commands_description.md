1. def get_db_connection() 함수를 통해 DB와 연동
add : 필터링 키워드를 추가함 {
  add-1 : DB와 연결한 뒤 DB에 INSERT 문으로 모두 소문자로 치환된 키워드를 추가함.
}
remove 필터링 키워드를 제거함 {
  remove-1 : DB와 연결한 뒤 DB에 REMOVE 문으로 키워드를 제거함.
}
list: 필터링 키워드 리스트를 보여줌{
  list-1 : DB와 연결한 뒤 SELECT 문으로 DB에서 키워드를 가져오고 출력함. 키워드가 없을경우 필터링 키워드가 리스트에 없다고 출력함.
unban : 유저 영구정지 해제{
  unban-1 : 봇이 대상의 사용자ID를 가져온다.
  unban-2 : 디스코드 자채 기능으로 밴을 해제한다.
  unban-3 : 사용자에게 정지 해제 사실과 초대링크를 보낸다.
unmute: 유저 채팅 격리 해제
kick : 유저 일시 추방
