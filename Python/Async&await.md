## async/await 단계적 이해 (해당 코드 기준)
1️) 기본 개념
async def: 비동기 함수 정의 (코루틴)

await: 비동기 작업 완료 대기

이벤트 루프: 모든 비동기 작업의 스케줄링 관리자

2️) 코드 흐름 분석
python
async def main():  # ✅ 비동기 함수 선언
    urls = [...]  # CSV에서 URL 목록 로드
    for url, brand in zip(urls, brands):
        htmls, fname = await scrape_reviews(url, brand)  # ⏸️ 여기서 실행 중단 후 결과 기다림
        # 결과 수신 후 아래 코드 실행
        df_reviews = parse_reviews(htmls) 
        df_reviews.to_csv(...)

3️) 작동 원리
asyncio.run(main()) 실행

이벤트 루프 시작 → main() 코루틴 실행

await scrape_reviews() 호출 시:

현재 코루틴 일시 정지

이벤트 루프가 다른 작업 실행

scrape_reviews() 완료 시 재개

** 코루틴(coroutine)은 "co(함께)"와 "routine(규칙적 일의 순서, 작업의 집합)"이 합쳐진 말, 함께 동작하면서 규칙이 있는 일의 순서를 의미.
간단히 말해, 여러 작업이 서로 협력하면서 실행되는 구조

4️) 주요 활용 부분
python
# 페이지 이동 (네트워크 요청 대기)
await page.goto(url)  

# 요소 로딩 대기
await page.wait_for_selector(".pageing")  

# 페이지 클릭 이벤트
await page.click("a:has-text('리뷰')")  

# 브라우저 종료
await browser.close()  

5️) 왜 async가 필요한가?
동시성 향상: 페이지 로딩 대기 시간에 다른 작업 처리

리소스 효율: 단일 스레드에서 여러 네트워크 요청 처리

실제 예시: 리뷰 페이지 1을 기다리는 동안 페이지 2 요청 가능

6️) 주의사항
동기 코드 금지: time.sleep() 대신 await page.wait_for_timeout() 사용

중첩 await: 항상 await 체인 유지

예외 처리: try/except로 네트워크 오류 포착 필수

7️) 팁
async def로 함수 정의

I/O 작업마다 await 추가

이벤트 루프 실행(asyncio.run()) 필수

Playwright의 비동기 API 문서 참고

💡 체감 효과: async를 사용하면 대기 시간을 활용해 더 빠른 스크래핑이 가능해집니다. (실제 환경에선 병렬 처리 추가 시 효과 극대화)