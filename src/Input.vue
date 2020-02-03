<script lang="tsx">
import { ref, watch, defineComponent, h, computed } from 'vue'

interface InputProps {
  value: string | number,
  onChange?: (value: string) => void,
}

const Input =  defineComponent({
  setup(props: InputProps, { emit }) {
    const handleChange = (e: KeyboardEvent) => {
      emit('update:value', (e.target as any)!.value)
    }

    const id = computed(() => parseInt(`${props.value}`, 10) + 1)

    return () => h('input', {
      class: ['test'],
      style: { 
        display: 'block',
      },
      id: id.value,
      onInput: handleChange,
      value: props.value,
    })
  },
})

export default Input
</script>
