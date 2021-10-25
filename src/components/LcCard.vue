<template>
  <div class="card">
    <div v-if="$slots.header" class="card--header">
      <slot name="header"></slot>
    </div>
    <div class="card--body">
      <slot name="body" />
    </div>
    <div v-if="$slots.footer" class="card--footer">
      <slot name="footer"></slot>
    </div>
  </div>
</template>

<style lang="scss" scoped>
  .card {
    display: flex;
    flex-direction: column;
    width: fit-content;
    height: auto;
    box-shadow: $shadow-md;
    border-radius: $rounded;
    overflow: hidden;
    background-color: $gray-0;
    @include mobile {
      width: 100%;
    }
  }

  .card--body {
    @include card-container;
  }
  .card--header {
    height: max-content;
  }
  .c-card-footer {
    display: flex;
    justify-content: center;
    margin-top: $spacer-8;
  }
</style>
