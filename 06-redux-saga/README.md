## 06 Redux-Saga


**01 - 安装**

```
npm install redux-saga --save
```

**02 - 配置**

> `src/index.js`

```js
import createSagaMiddleware from 'redux-saga'
import mySaga from './sagas'

const sagaMiddleware = createSagaMiddleware();

const store = createStore(
  reducer,
  applyMiddleware(sagaMiddleware)
);

sagaMiddleware.run(mySaga);
```

> `src/sagas.js`

```js
import { takeEvery, put, fork, call, delay} from 'redux-saga/effects';

function* asyncInc(){
  // 并发执行
  const posts = yield fork(fetch, 'https://jsonplaceholder.typicode.com/posts');
  const users = yield fork(fetch, 'https://jsonplaceholder.typicode.com/users');

  yield delay(1000); 

  // 阻塞执行
  const photos = yield call(fetch, 'https://jsonplaceholder.typicode.com/photos');
  const toto = yield call(fetch, 'https://jsonplaceholder.typicode.com/todos');

  
  yield put({type: 'INC'});
}

function* mySaga() {
  yield takeEvery('INC_ASYNC', asyncInc) 
}
```

### API

* `delay`: 延时 
* `takeLatest`: 只允许一个任务在执行
* `takeEvery`: 允许多个任务执行
* `call`: 调用函数
* `put`: 发送action
* `all`: 并发执行
* `fork`


### 参考资料

* [Redux-Saga](https://redux-saga.js.org/) / [中文](https://redux-saga-in-chinese.js.org/)
* [轻松学 Redux-Saga](https://github.com/guxiaobai/learn-course-100/tree/main/com.qiuzhi99/012-redux-saga)
* [从redux-thunk到redux-saga实践](https://github.com/Pines-Cheng/blog/issues/9)
* [Redux Saga实践](http://yanqiw.github.io/react/2017/03/05/redux-saga.html)
* [redux-saga 初级学习教程](https://www.jianshu.com/p/f3c7594c4fb4)
