<template>
  <v-app>
    <v-main>
      <v-container>
        <h1>Demo</h1>
        <div class="example-block">
          <h2>The block by width, center alignment</h2>
          <TagList :tags="tags" is-center-alignment />
        </div>
        <div class="example-block">
          <h2>The block by width, left alignment</h2>
          <TagList :tags="tags" />
        </div>
        <div class="example-block example-block_small">
          <h2>The little block, left alignment</h2>
          <TagList :tags="tags" />
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
    label: 'Station name',
  },
  {
    id: 3,
    label: 'By bus',
    icon: 'bus'
  },
  {
    id: 4,
    label: 'March, 25',
  },
  {
    id: 5,
    label: '6 hours',
    icon: 'clock-outline'
  },
  {
    id: 6,
    label: 'Up to 49',
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
.example {
  &-block {
    padding: 10px;
    border: 1px solid black;

    & + & {
      margin-top: 10px;
    }

    &_small {
      max-width: 400px;
    }
  }
}
</style>
