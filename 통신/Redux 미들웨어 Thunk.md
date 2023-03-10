## Redux 미들웨어 

### 1. 미들웨어 란 ? 

리덕스에서 dispatch를 하면 action이 리듀서로 전달이 되고, 리듀서는 
새로운 state를 반환한다.  **미들웨어를 사용하면 이 과정 사이에 우리가 하고 싶은 작업들을 
넣어서 할 수 있다 ! **



- 특정 조건에 따라 action 이 무시되게 만들 수 있고
- action를 콘솔에 출력하거나, 서버쪽에 로깅을 할 수 있고
- action이 dispatch 됐을 떄 이를 수정해서 리듀서에게 전달되도록 할 수있고
- 특정 action이 발생했을 떄 이에 기반하여 다른 action이 발생되도록 할 수 있고
- 특정 action이 발생했을 때 특정 자바스크립트 함수를 실행  시킬 수 있다 ! 

리덕스에서 미들웨어를 사용하는 주된 사용용도는 비동기 작업을 처리 할떄 사용한다 
예를 들어 리액트앱에서 백엔드 API를 연동해야 된다면, 리덕스 미들웨어를 사용하여 처리한다 



## thunk  

리덕스에서 많이 사용하고 있는 미들웨어 중 하나이다 . 
thunk를 사용하면 우리가 dispatch를 할때 객체가 아닌 함수를 dispatch 할 수 있게 해줍니다. 즉 dispatch(객체) 가 아니라 dispatch(함수)를 할 수 있게 되는 것이죠!

## 정리 
- 리덕스 미들웨어를 사용하면, action 이 리듀서로 전달되기 전에 중간에 어떤작업을 더 할수 있다 
- Thunk를 이용하면 , 객체가 아닌 함수를 Dispatch 할 수 있게 해준다  **Thunk핵심**
- redux-toolkit 에서 Thunk 함수를 생설할떄 `createAsyncThunk` 를 이용한다.
- `createAsyncThunk()` 의 **첫번째 자리에는action value 두번째 자리에는 함수 가  들어간다**
- 두번째로 들어가는 함수에서 2개의 인자를 꺼내 사용할 수 잇는데, 첫번쨰 인자는 컴포넌트에서
	보내준 payload이고, 두번째 인자는 thunk에서 제공하는 여러가지의 기능이다. 


생각보다 코드는 괜찮은데 많이 복잡하고 유기적으로 연결이 되어있어서 