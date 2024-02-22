## nextjs
nextjs를 사용하면 SSR(Server Side Rendering)이 가능하다. 그리고 React에서는 CSR(Client Side Rendering)을 하여 SEO에 어려움이 있고 페이지 로딩속도가 느리다는 단점이 있는데,
nextjs를 사용하게 되면 미리 렌더링을 해서 보내주기 때문에 SEO에도 용이하고 페이지 로딩속도도 빠르고 원하는곳에는 CSR도 가능하기 때문에 점점 SSR이 가능한 nextjs가 널리 퍼지고 있다.    
그리고 프레임워크를 사용하게 되어 간단하게 개발도 가능하게되며 진입장벽이 좀 더 낮다는 장점이 있습니다.    
<br>

## nextjs에서 ssr(hydration) 
클라이언트에게 웹 페이지를 보내기 전에 server side에서 미리 웹 페이지를 pre-rendering 한다.   
Next.js는 React에서 HTML 파일을 생성하기 위한 React Server-Side API인 ReactDOMServer을 사용해 제작된 사이트의 프로덕션 단계 파일을 생성한다. 이때 웹 페이지에서, 서버로부터 생성된 정적인 HTML을 렌더링한다.   
페이지 첫 로딩 이후 JS가 로드 되고, ReactDOM.hydrate() API는 JS와 함께 서버에서 렌더링되었던 HTML 페이지에 Hydration을 한다.   
Hydration 이후, React reconciler API가 자리를 대체하고, 사이트는 상호작용이 가능해진다.   
<br>

## pages
- 13버전 이전에는 pages 폴더안의 파일 및 폴더의 이름이 곧 경로명으로 라우팅 됨
- pages/product 폴더 안에 `[id].js`로 파일을 만들게 되면 /product/ 뒤에 아무 단어나 넣어도 `[id].js`파일로 가게 됨   
<br>

## Link
- Link 컴포넌트를 사용하면 필요한 데이터만을 불러오기 때문에 더 효율적이고 넘어가는 동작도 자연스러움
- next에서는 a 태그 대신 Link 컴포넌트 사용   
<br>

## useRouter
- `useRouter()`를 사용해 경로의 값 사용 및 페이지 이동
- `const router = useRouter(); const { id } = router.query`// [id].js query에들어가는건 경로의 값 또는 파일의 이름
  > ex) `/items?q=blue` 라면 `const { q } = router.query` // q = blue
- `router.push('/search')` 를 사용하면 /search 경로로 이동   
<br>

## 리다이렉트
- 리다이렉트 하기 위해서는 next.config.js 파일수정 -> next공식홈페이지에서 코드 가져다가 사용   
<br>

## 커스텀 404
- pages에 404.js로 만들어 줌   
<br>

## Head 태그
- `<Head><title>사이트 제목</title></Head>` Head 태그 안에 title 안에 텍스트를 써주면 사이트 탭의 제목이 됨
- `<Head><link rel="icon" href="경로"></link></Head>` Head 태그 안에 link 넣어주고 icon과 경로 정해주면 탭에 아이콘 삽입 가능   
<br>

## 프리렌더링
- 초기 로딩이 빨라짐, 검색엔진 최적화 가능
- 정적생성: 빌드될때 미리 렌더링된 html및 css, js 제공
- 서버사이드 렌더링: 클라이언트에서 리퀘스트를 보내면 서버에서 렌더링 한 다음 데이터 보내줌
- `export function getStaticProps(){ ... return { props : {data} } }` getStaticProps로 정적 생성 가능하며 props로 데이터 내려줄수 있음 컴포넌트에서는 인자로 { data } 와 같이 props를 구조분해할당으로 받아 사용
- 정적생성 함수는 훅 사용이 불가능하기때문에 파라미터로 context를 받아와서 context.params['id']로 다이나믹 페이지의 param을 가져올 수 있음
- `export async function getStaticPaths() { return { paths: [{ params: {id: '1'} }, { params: {id: '2'} }], fallback: true } }` getStaticPaths로 다이나믹 페이지는 어떤 것을 정적생성해야하는지 경로를 알려주어야함, 그리고 fallback 의 설정을 true로 하여 경로를 정해주지 않은것도 렌더링 되게 설정 가능 false로하면 없는경로 렌더링 하지 않음
- fallback의 설정을 true로 할때 정적생성 데이터가 없을 떄 보여줄 컴포넌트를 설정해주어야함 ex) `if(!data) return (<div>로딩시 화면 처리</div>)`
- getServerSideProps를 사용해 서버사이드 렌더링 적용, 사용법은 정적생성과 비슷, 자주 바뀌는 부분까지 포함해서 렌더링을 하고싶다면 서버사이드 렌더링을 사용        
<br>


