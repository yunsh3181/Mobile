Papa John's Mobile v43.6.5

URL 구조 변경
- 고객 주문: https://order.papabottle.com/
- 관리자: https://order.papabottle.com/admin/
- 좌석관리: https://order.papabottle.com/seat/

변경 사항
1. admin/index.html에 관리자 페이지 배치
2. seat/index.html에 좌석관리 페이지 배치
3. 기존 admin.html, seats.html, admin-login.html은 새 주소로 자동 이동
4. 관리자 안의 좌석관리 화면도 /seat/ 경로 사용
5. CNAME 파일 포함: order.papabottle.com

업로드 방법
- ZIP 압축 해제 후 안의 파일과 폴더 전체를 Mobile 저장소 루트에 업로드
- admin 폴더와 seat 폴더가 반드시 함께 올라가야 함
- ZIP 파일 자체는 업로드하지 않음
