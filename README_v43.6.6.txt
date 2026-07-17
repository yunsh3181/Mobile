파파존스 Mobile 통합 v43.6.6

수정 목적
- 먹고가기 주문이 Firestore orders에는 저장되지만 seats가 사용 중으로 바뀌지 않던 문제 수정

수정 내용
1. 주문과 좌석 점유를 Firestore batch로 한 번에 저장
2. 현재 Firestore Rules에서 허용하지 않는 name, capacity 필드를 좌석 업데이트에서 제거
3. 저장 필드를 status, partySize, orderNo, orderId, occupiedAt, updatedAt로 제한
4. 주문과 좌석 중 한쪽만 저장되는 불완전 저장 방지
5. 앱 버전 표기를 mobile-v43.6.6으로 변경

업로드 방법
- GitHub Mobile 저장소의 기존 파일을 이 압축파일 내용으로 교체
- GitHub Pages 배포 완료 후 강력 새로고침
- 먹고가기 주문을 한 번 넣고 /seat/ 화면에서 선택 좌석이 사용 중으로 바뀌는지 확인

Firestore Rules
- 사용자가 보내준 현재 규칙 기준으로 주문 시 좌석 점유가 허용되도록 수정됨
- 이번 버전에서는 Rules를 별도로 변경할 필요 없음
