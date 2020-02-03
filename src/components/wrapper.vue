<script lang="tsx">
import { defineComponent, ref, reactive } from 'vue'

const wrapper = defineComponent({
  setup(props, { slots }) {
    const v = ref(0)
    const state = reactive({
      count: 0
    })
    return () => (
      <div>
        一段文字 {slots.default && slots.default()}
        <button onClick={() => {v.value++; state.count++}}> + </button>
      	<h1 class="ok">
          标题{v.value}
          <br/>
          数目： {state.count}
        </h1>
      </div>
    )
  },
})
export default wrapper
</script>