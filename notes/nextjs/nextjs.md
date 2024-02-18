## nextjs
nextjs를 사용하면 SSR(Server Side Rendering)이 가능하다. 그리고 React에서는 CSR(Client Side Rendering)을 하여 SEO에 어려움이 있고 페이지 로딩속도가 느리다는 단점이 있는데,
nextjs를 사용하게 되면 미리 렌더링을 해서 보내주기 때문에 SEO에도 용이하고 페이지 로딩속도도 빠르고 원하는곳에는 CSR도 가능하기 때문에 점점 SSR이 가능한 nextjs가 널리 퍼지고 있다.    
그리고 프레임워크를 사용하게 되어 간단하게 개발도 가능하게되며 진입장벽이 좀 더 낮다는 장점이 있습니다. 

## nextjs에서 ssr(hydration) 
클라이언트에게 웹 페이지를 보내기 전에 server side에서 미리 웹 페이지를 pre-rendering 한다.   
Next.js는 React에서 HTML 파일을 생성하기 위한 React Server-Side API인 ReactDOMServer을 사용해 제작된 사이트의 프로덕션 단계 파일을 생성한다. 이때 웹 페이지에서, 서버로부터 생성된 정적인 HTML을 렌더링한다.   
페이지 첫 로딩 이후 JS가 로드 되고, ReactDOM.hydrate() API는 JS와 함께 서버에서 렌더링되었던 HTML 페이지에 Hydration을 한다.   
Hydration 이후, React reconciler API가 자리를 대체하고, 사이트는 상호작용이 가능해진다.   
