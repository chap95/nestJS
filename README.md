# Nset.js

nest.js를 사용해보자

---

### nest.js 기본 개념과 각 파일들의 역할

##### Philosophy

이 부분은 조금 더 조사후 올릴 예정

---

##### controller

컨트롤러란 무엇일까??
컨트롤러는 클라이언트로부터 온 request를 핸들링하여 다시 클라이언트에게로 response를 보내주는 역할을한다.

라우팅 메커니즘은 request에 대해 어떤 controller 가 작업을 핸들링 할지 정해준다. 각가의 controller 는 하나 이상의 route를 가지며 routes는 서로 다른 동작을 수행한다.

가장 기본적인 controller를 만들기 위해 classes 와 decorators 를 사용한다. decorator는 클래스들을 필수 메타데이와 연결하고 Nest가 라우팅 맵을 만들수 있도록 한다.

##### Routing

```js
import { Controller, Get } from '@nestjs/common';

@Controller('cats')
export class CatsController {
  @Get()
  findAll(): string {
    return 'This action returns all cats';
  }
}
```

위의 예제에서는 `@controller` 기본적인 컨트롤러를 만들때 필요한 데코레이터를 사용했다. 위 코드에서는 cat의 optional 라우트 경로 prefix를 지정했다. 이렇게 prefix를 사용하게 되면은 연관성 있는 route path를 그룹화 할 수 있고 코드의 반복을 줄일 수가 있다.

예를 들어서 customer 엔티티와 관련된 동작을 `/customer` 라우트 path 에서 수행하고자 할 때 `@controller('customer')` 와 같이 데코레이터로 route path prefix 를 지정해주면 각각의 하위 path 에 대해서 반복적인 코드 작성을 할 필요가 없어진다.
