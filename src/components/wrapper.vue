<script lang="tsx">
import { defineComponent, ref } from 'vue'

const wrapper = defineComponent({
  setup(props, { slots }) {
    const v = ref(0)
    return () => (
      <div>
        一段文字 {slots.default && slots.default()}
        <button onClick={() => v.value++}> + </button>
      	<h1 class="ok">
      		标题{v.value}
        </h1>
      </div>
    )
  },
})
export default wrapper
</script>