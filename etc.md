Vue에서 v-model은 HTML에서 value와 비슷하지만 자바스크립트랑 html이랑 바인딩 하는 역할
watch: 데이터의 변경이 일어날 때마다 알아챔. 예를 들어서 console.log를 찍으면 계속해서 console에 찍힌다.

v-if와 v-show로 화면에 보이게 하는 것은 큰 차이가 있다. v-if는 조건을 만족하지 않으면 해당 코드 자체를 렌더링 하지 않지만 v-show는 조건이 만족하는 지에 별개로 일단 렌더링을 하지만 보이고 안보이고를 조절한다.

화면에 자꾸 뭔가를 보였다 안보였다를 자주 한다면 v-show를 사용하는 것이 낫다. 렌더링을 해놓고 보이는지 유무만 바꾸면 되기 때문에 v-if보다 리소스를 덜 잡아 먹는다.

carStore에서 router push하는 name이랑 index.js의 name이랑 *대소문자*까지 일치해야 함.

use_ssafydb

's' 유의하기!!!

### stores에 가져와서 사용하기
script setup에서 import를 통해 바꿔준다.
```
<script setup>
import { useRoute } from 'vue-router'
```

이후에 인스턴스화 시켜준다.
```
<script setup>
import { useTmpStore } from '@/stores/tmpStore'

const store = useTmpStore();
```

이후에 store를 사용하면 된다.

```
<script setup>
import { useTmpStore } from '@/stores/tmpStore'

const store = useTmpStore();

const createTmp = () => {
    store.createTmpStore();
}
```

여기서 주의할 점은 const createTmp에 해당하는 createTmp와 store.createTmpStore의 createTmp는 다른 것이다. 후자는 store에서 가져오는 createTmpStore이니까 이 부분 주의하자!

RouterLink는 하이퍼링크를 만들어주는 것이다. 이 때 name에 해당하는 값은 router에 있는 name과 대소문자까지 일치해야 한다.

