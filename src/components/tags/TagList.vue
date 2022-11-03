<template>
  <div :class="['tag-list', {'tag-list_justify': justify}]" :style="cssVars">
    <div :key="`item-${tag.id}`" v-for="tag in tags" class="tag-list__item">
      <v-icon class="tag-list__divider">
        mdi-circle-small
      </v-icon>
      <Tag :icon="tag.icon"
           :label="tag.label" />
    </div>
  </div>
</template>

<script>
import Tag from "@/components/tags/Tag";

export default {
  name: "TagList",
  components: {Tag},
  props: {
    tags: {
      type: Array,
      default: () => [],
      validator(value) {
        return value.every((element) => element.label);
      }
    },
    justify: {
      type: Boolean,
      default: false
    }
  },
  data() {
    return {
      oneLineHeight: null
    }
  },
  mounted() {
    this.oneLineHeight = this.$el.clientHeight;
  },
  computed: {
    cssVars() {
      if (this.oneLineHeight !== null) {
        return {
          '--max-height': `${this.oneLineHeight}px`,
          '--flex-wrap': 'wrap'
        }
      }
      return {
        '--max-height': 'initial',
        '--flex-wrap': 'nowrap'
      }
    }
  }
}
</script>

<style lang="scss" scoped>
.tag-list {
  display: flex;
  align-items: center;
  flex-wrap: var(--flex-wrap);
  max-height: var(--max-height);
  overflow: hidden;

  &__item:first-of-type &__divider {
    display: none;
  }

  &_justify {
    justify-content: space-between;
  }

  &__item {
    display: flex;
    flex-direction: row;
  }
}
</style>