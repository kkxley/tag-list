<template>
  <div class="tag-list">
    <div class="tag-list__item" :key="tag.id" v-for="(tag, i) in tags">
      <v-icon v-if="i">
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
  }
}
</script>

<style lang="scss" scoped>
.tag-list {
  display: flex;
  align-items: center;

  &__item {
    display: flex;
    align-items: center;
  }

}
</style>