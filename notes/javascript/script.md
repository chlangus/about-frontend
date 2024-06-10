## <script>
- javascript 를 다운로드 하고 실행하는데 이때 HTML 파싱이 중단
<br>

## <script defer>
- 스크립트를 다운하는 동안 HTML 파싱이 중단되지 않음
- DOM 생성이 완료될때까지 지연 후 스크립트 정의 순서대로 실행
<br>

## <script async>
- 스크립트를 다운하는 동안 HTML 파싱이 중단되지 않음
- 스크립트 다운로드가 완료되면 바로 실행, 실행할 때는 HTML 파싱 중단
