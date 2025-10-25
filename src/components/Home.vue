<template>
  <div>
    Nombre completo: {{ fullname }}
    <div>{{ username }}</div>
  </div>
</template>

<script>
import { toRefs, computed, inject } from "vue";

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

    const username = inject("username");

    expose({
      fullname,
    })

    return {
      fullname,
      username,
    };
  },
}
</script>
