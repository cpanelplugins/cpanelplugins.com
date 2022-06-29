<template>
  <Card class="plugin" :image="node.screenshot" :link="node.path">
    <h4 class="plugin__title">
      {{ node.title }}
    </h4>
    <p v-if="node.description" class="plugin__desc"> {{ node.description }} </p>
    <div class="plugin__footer">
      <div class="plugin__actions flex gap-15">
        By {{ node.author.title }}
      </div>
      <div class="plugin__platform">
        <g-image v-if="node.platforms" :src="node.platforms.logo" :alt="node.platforms.title" />
      </div>
    </div>
  </Card>
</template>

<script>
export default {
  props: {
    node: { type: Object, required: true }
  }
}
</script>

<style lang="scss">
.plugin {

  .card__inner {
    padding: 1rem;
  }

  &:hover {
    .card__image img {

    }
  }

  &__title {
    font-size: .9rem;
    font-weight: 500;
    white-space: nowrap;
    max-width: 220px;
    overflow: hidden;
    text-overflow: ellipsis;
  }

  &__desc {
    font-size: .85rem;
    margin-bottom: .5rem!important;
    opacity: .8;
    white-space: nowrap;
    max-width: 220px;
    text-overflow: ellipsis;
    overflow-x: hidden;
  }

  &__footer {
    display: flex;
    background-color: var(--bg);
    align-items: center;
    justify-content: space-between;
    font-size: .85rem;
    position: relative;
    transition: background-color .3s;
  }

  &__actions {
    opacity: .6;
  }

  &__platform {
    img {
      width: 25px;
      max-height: 25px;
      margin:0;
    }
  }

  &:hover {
    .plugin__footer {
      transform: translateY(0);
    }
  }
}
</style>
