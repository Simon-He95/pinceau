<script setup lang="ts">
import type { PropType } from 'vue'

defineProps({
  color: {
    type: [String, Object] as PropType<ComputedStyleProp<'color'>>,
  },
  ...variants,
})
</script>

<template>
  <div>
    <slot />
  </div>
</template>

<style scoped lang="ts">
css({
  div: {
    backgroundColor: (props) => {
      return props.color
    },
    color: (props) => {
      return props.color
    },
    display: 'block',
    borderRadius: '{radii.lg}',
    borderWidth: '{borderWidth.md}',
    span: {
      color: 'black'
    }
  },
  variants: {
    size: {
      sm: {
        padding: '{space.6}',
        fontSize: '{fontSize.sm}'
      },
      md: {
        padding: '{space.8}',
        fontSize: '{fontSize.md}'
      },
      lg: {
        padding: '{space.12}',
        fontSize: '{fontSize.lg}'
      },
      xl: {
        padding: '{space.16}',
        fontSize: '{fontSize.xl}'
      },
      options: {
        default: 'xl'
      }
    },
    primary: {
      true: {
        backgroundColor: 'rgba({color.blue.500}, 0.5)',
        color: '{color.blue.200}',
        borderColor: '{color.blue.300}'
      }
    },
    success: {
      true: {
        backgroundColor: 'rgba({color.green.500}, 0.5)',
        color: '{color.green.200}',
        borderColor: '{color.green.300}'
      }
    },
    warning: {
      true: {
        backgroundColor: 'rgba({color.yellow.500}, 0.5)',
        color: '{color.yellow.200}',
        borderColor: '{color.yellow.300}'
      }
    },
    danger: {
      true: {
        backgroundColor: 'rgba({color.red.500}, 0.5)',
        color: '{color.red.200}',
        borderColor: '{color.red.300}'
      }
    }
  }
})
</style>
