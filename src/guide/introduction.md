---
footer: false
---

## 什么是vue-use-form？ {#what-is-vue-use-form}

vue-use-form是一个vue3的表单验证库，对CompositionAPI非常友好，下面让我们来看一个基本示例

<div class="options-api">

```vue
<script>
import { useForm } from 'vue-use-form'

export default defineComponent({
  data() {
    const [usernameField, passwordRef] = useForm({
      mode: 'onChange',
    })

    return {
      usernameField,
      passwordRef,
    }
  },

  mounted() {
    this.$refs.passwordRef = this.passwordRef
  }
})
</script>

<template>
  <input ref='passwordRef' v-model='usernameField'/>
</template>
```

</div>

<div class="composition-api">

```vue
<script setup lang='ts'>
import { useForm } from 'vue-use-form'

interface Inputs {
  username: string
}

const [usernameField, passwordRef] = useForm<Inputs>({
  mode: 'onChange',
})
</script>

<template>
  <input ref='passwordRef' v-model='usernameField'/>
</template>
```

</div>
