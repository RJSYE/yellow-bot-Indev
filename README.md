# yellow-bot-Indev
이름이 yellow bot인 이유는 사용된 디스코드 계정 이름이 yellow 이기 때문입니다.

main.py의 기능은 다음과 같이 단계적으로 작동합니다 :
1 . 봇 토큰 , 기본 설정을 입력받고 봇을 구동 |
2 . DB 초기화 함수 선언
3 . DB에서 부적절한 키워드 불러오기
4 . 간편 처벌 버튼 클래스 Punishmentview 선언
   {
   4-2 - def __init__() : 생성자 함수가 디스코드 UI 와 처벌 대상 사용자를 불러옴
   
   4-3 : async def interaction_check() : 비동기적으로 사용자가 관리자인지 확인하고 참일 경우에만 메시지 표시
   
   4-4 : async def ban() : 비동기적으로 사용자 영구추방 버튼 생성
   
   4-5 : async def kick() : 비동기적으로 사용자 일시추방 버튼 생성
   
   4-6 : async def mute() : 비동기적으로 사용자 격리 버튼 생성
   
   4-7 : async def decline() : 비동기적으로 처벌 취소및 자동 타임아웃 해제 버튼 생성
   }
5 . async def on_ready() : 로그인된 봇의 이름및 id를 출력한 뒤 DB 초기화 함수 실행
6 . async def on_message(message) : 
  {
  6-2 : if message.author == bot.user or message.author.bot : 메시지 작성자가 봇인 경우 실행 취소

  6-3 : bad_words = get_bad_words() : 부적절한 키워드를 불러오는 함수 실행한 뒤 반환 값 저장
  
  6-4 : word_pattern = ... : 단어를 안전하게 리컴파일 하여 필터링 우회및 보안 위협 방지
  
  6-5 : if word_pattern and word_pattern.search(message.content) : 사용자의 메시지를 삭제하고 2분 타임아웃 및 사용자에게 적발 메시지를 보내고 Punishmentview 클래스를 호출하여 간편 처벌 버튼을 받아온 뒤 관리자 채널에 간편 처벌 버튼 전송
  }
7 . cmd_module.setup(bot) 을 통해 커맨드 모듈 불러오기
