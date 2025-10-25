<template>
  <div>
    Nombre completo: {{ fullname }}
  </div>
</template>

<script>
import { toRefs, computed } from "vue";

export default {
  props: {
    firstName: String,
    lastName: String,
  },

  setup(props, { expose }) {
    const { firstName, lastName } = toRefs(props);

    const fullname = computed(() => {
      return `${firstName.value} ${lastName.value}`;
    });

    expose({
      fullname,
    })

    return {
      fullname,
    };
  },
}
</script>
