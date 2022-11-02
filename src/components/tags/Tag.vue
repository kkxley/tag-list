<template>
  <div class="tag">
    <v-icon v-if="icon" class="tag__icon">
      mdi-{{ icon }}
    </v-icon>
    <span class="tag__label">
        {{ label }}
    </span>
  </div>
</template>

<script>
export default {
  name: "TagItem",
  props: {
    label: {
      type: String,
      required: true
    },
    icon: {
      type: String,
      default: null
    }
  }
}
</script>

<style lang="scss" scoped>
.tag {
  display: flex;
  align-items: center;

  &__icon {
    margin-right: 5px;
  }

  &__label {
    white-space: nowrap;
    color: #919191;
  }
}
</style>