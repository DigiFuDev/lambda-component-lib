<template>
  <div class="hero">
    <div class="hero--copy">
      <h1 class="hero--headline">
        <slot name="headline" />
      </h1>
      <h6 class="hero--caption">
        <slot name="caption" />
      </h6>
      <div class="hero-cta">
        <slot name="cta" />
      </div>
    </div>
    <div v-if="$mq != 'mobile'" class="hero-image--container">
      <img :src="img" alt="" class="hero-image--image" />
    </div>
  </div>
</template>

<script setup>
  const props = defineProps({
    img: String,
  });
</script>

<style lang="scss" scoped>
  .hero {
    @include container;
    display: flex;
    flex-direction: column;
    @include tablet {
      flex-direction: row;
    }
  }
  .hero--copy {
    display: block;
    width: max-content;
    margin-top: $spacer-8;
    padding: 0 $spacer-6;
    @include tablet {
      padding: 0 $spacer-10;
    }
    @include laptop {
      margin-top: $spacer-12;
      padding: 0 $spacer-12;
    }
    @include desktop {
      padding: $spacer-19 $spacer-19;
    }

    .hero--headline {
      width: 9em;
      margin-bottom: $spacer-4;
      @include laptop {
        width: 11em;
      }
    }

    .hero--caption {
      width: 16em;
      font-weight: $font-medium;
      @include tablet {
        width: 25em;
      }
      @include desktop {
        width: 30em;
      }
    }
  }
  .hero-cta {
    margin-top: $spacer-12;
    margin-bottom: $spacer-12;
    display: flex;
    flex-direction: column;
    width: 100%;
    @include desktop {
      width: 30rem;
    }
  }
  .hero-image--container {
    display: block;
    @include desktop {
      margin-right: $spacer-19;
    }

    .hero-image--image {
      height: 100%;
      width: 100%;
      max-height: 600px;
      max-width: 420px;
      @include desktop {
        width: auto;
        max-width: 600px;
      }
    }
  }
</style>
