<demo>
常规使用
</demo>
<template>
  <Button @click="toggle">打开对话框</Button>
  <Dialog v-model:visible="x" :closeOnClickOverlay="true" :ok="f1" :cancel="f2">
    <template v-slot:title>
      <strong>加粗的标题</strong>
    </template>
    <template v-slot:content>
      <strong>hi</strong>
      <div>hi2</div>
    </template>
  </Dialog>
</template>
<script lang="ts">
import {Button, Dialog} from "../lib/index";
import {ref} from 'vue'

export default {
  components: {
    Dialog,
    Button
  },
  setup() {
    const x = ref(false)
    const toggle = () => {
      x.value = !x.value
    }
    const f1 = () => {
      console.log('click ok')
      return false
    }
    const f2 = () => {
      console.log('click cancel')
    }
    return {x, toggle, f1, f2}
  }
}

</script>
