# v43.9.1 보안 1차 적용 안내

## 포함된 변경사항
- Firestore 공개 전체 읽기/쓰기를 최소 권한 규칙으로 교체
- 주문: 비로그인 고객은 검증된 신규 주문 생성만 가능, 읽기/수정/삭제는 관리자만 가능
- 좌석: 누구나 상태 조회 가능, 고객은 방금 생성한 주문과 연결된 `occupied` 변경만 가능
- 줄서기: 전체 전화번호 저장을 제거하고 마스킹 번호/뒤 4자리만 저장
- 고객/매출/통계 컬렉션: 관리자 Custom Claim이 있는 계정만 접근
- 관리자 주문/대기/통계/좌석 화면의 외부 데이터 HTML 이스케이프 강화
- 좌석 관리자 화면도 `admin === true` Custom Claim을 재검증
- 모바일 주문 전송 전 기본 형식/수량/금액 검증 추가

## Firebase 콘솔 적용 순서
1. 현재 Firestore Rules를 별도 파일로 백업합니다.
2. 이 프로젝트의 `firestore.rules` 내용을 Firebase Console > Firestore Database > Rules에 붙여넣습니다.
3. 게시하기 전에 Rules Playground에서 아래 동작을 확인합니다.
   - 비로그인: seats 읽기 성공
   - 비로그인: orders 읽기 실패
   - 비로그인: 정상 주문 create 성공
   - 비로그인: orders update/delete 실패
   - admin claim 계정: orders/seats/waitlist/customers/stats 읽기·수정 성공
4. 매장 운영 전 포장 주문, 먹고가기 주문, 좌석 점유, 관리자 접수/완료/취소, 줄서기 등록/취소를 각각 1회 테스트합니다.

## 중요한 제한
- 웹 Firebase API Key는 공개되어도 정상이며 보안 경계가 아닙니다. 실제 보호는 Rules/Auth/App Check가 담당합니다.
- 이번 1차 버전은 클라이언트가 계산한 가격을 형식과 범위로만 검사합니다. 가격 위변조를 완전히 차단하려면 다음 단계에서 Cloud Functions가 메뉴 원가표로 금액을 다시 계산해야 합니다.
- 비로그인 줄서기에서 대기 순번 계산을 유지하려고 waitlist 읽기는 공개 상태입니다. 다만 전체 전화번호는 저장하지 않도록 변경했습니다. 더 강한 개인정보 보호가 필요하면 공개 대기현황 컬렉션과 관리자 전용 개인정보 컬렉션을 분리해야 합니다.
- Firestore Rules는 문서 내부 배열의 모든 메뉴 가격을 공식 가격표와 대조하기에 적합하지 않습니다. 서버 주문 생성 전환을 권장합니다.

## 권장 다음 단계
- Firebase App Check(웹 reCAPTCHA Enterprise 또는 v3) 적용
- Cloud Functions를 통한 서버 가격 재계산 및 주문 생성
- 관리자 계정 MFA 적용
- Firebase Authentication 승인 도메인 최소화
- Firebase 예산 알림 및 사용량 알림 설정
