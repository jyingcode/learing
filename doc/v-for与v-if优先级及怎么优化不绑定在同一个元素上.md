- 因为v-for优先级比v-if高，如果每一次都需要遍历整个数组，将会影响渲染速度，尤其是当之需要渲染很小一部分的时候。这个时候可以通过Vue中计算属性compute属性计算过滤出当前需要的数据。
#### v-for和v-if同用在一个元素上：
```<ul>
    <li
        v-for="user in users"
        v-if="user.isActive"
        :key="user.id"
        >
        {{ user.name }}
    </li>
</ul>
```
#### 通过vue中计算属性computed：
<ul>
    <li
          v-for="user in activeUsers"
          :key="user.id"
        >
        {{ user.name }}
    </li>
</ul>

computed: {
    activeUsers: function () {
        return this.users.filter(function (user) {
          return user.isActive
        })
    }
}
#### 把一个</template>当作一个元素在上面绑定v-if,然后再内部进行v-for循环。
```
<template v-if="isUser">
    <div v-for="user in users">{{user.title}}</div> 
</template>
```