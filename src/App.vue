<template>
  <v-app>
    <v-main>
      <v-container>
        <div class="example-block">
          <TagList :tags="tags" />
        </div>
        <div class="example-block">
          <TagList :tags="tags" justify />
        </div>
      </v-container>
    </v-main>
  </v-app>
</template>

<script>

const TAGS = [
  {
    id: 1,
    label: '5',
    icon: 'star-outline'
  },
  {
    id: 2,
    label: 'Обзорная',
  },
  {
    id: 3,
    label: 'На автобусе',
    icon: 'bus'
  },
  {
    id: 4,
    label: '25 марта',
  },
  {
    id: 5,
    label: '6 часов',
    icon: 'clock-outline'
  },
  {
    id: 6,
    label: 'до 49',
    icon: 'account'
  }
];

import TagList from "@/components/tags/TagList";

export default {
  name: 'App',
  components: {TagList},
  data: () => ({
    tags: TAGS
  }),
};
</script>

<style lang="scss" scoped>
.example-block {
  padding: 10px;
  border: 1px solid black;

  & + & {
    margin-top: 10px;
  }

  &_small {
    max-width: 500px;
  }
}
</style>
