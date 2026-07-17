파파존스 모바일 키오스크 v43.2.1 Hotfix
======================================

수정 내용
- GitHub Pages에서 data.js 경로 또는 캐시 문제로 빈 화면이 발생하는 현상 수정
- 메뉴 데이터(data.js)를 index.html 안에 직접 포함
- Firebase 초기화 설정도 index.html 안에 직접 포함
- 앱 시작 중 오류가 발생하면 초록색 빈 화면 대신 오류 안내 화면 표시
- Firebase 주문 저장 기능은 v43.2와 동일하게 유지

GitHub 업로드 방법
1. 이 폴더 안의 모든 파일과 assets 폴더를 Mobile 저장소의 최상위에 업로드
2. index.html이 반드시 저장소 최상위에 있어야 함
3. GitHub Pages 설정에서 배포 브랜치의 /(root) 선택
4. 업로드 후 Ctrl+F5 또는 시크릿 창에서 확인

주의
- 폴더 전체를 한 단계 더 감싸서 업로드하지 마세요.
- URL이 /Mobile/ 이라면 /Mobile/index.html 위치에 파일이 있어야 합니다.
