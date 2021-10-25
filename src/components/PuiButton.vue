<template>
  <button v-bind="$attrs">
    <slot />
  </button>
</template>

<style lang="scss">
  button,
  a {
    box-sizing: border-box;
  }
  .btn {
    padding: $spacer-3 $spacer-4;

    border-width: $border-2;
    border-radius: $rounded;
    border-style: solid;
    white-space: nowrap;
    transition-timing-function: cubic-bezier(0.4, 0, 0.2, 1);
    text-align: center;

    @include text-sm;
    font-weight: $font-semibold;
    font-family: $font-body;

    @include tablet {
      padding: $spacer-3 $spacer-4;
      @include text-base;
    }
    color: $gray-0;
    background-color: $gray-6;
    border-color: $gray-6;

    &:hover {
      box-shadow: $shadow-md;
      border-color: $gray-6;
    }
    &:active {
      box-shadow: $shadow;
    }
    &:focus {
      @include focus-ring($gray-3);
    }

    &--primary {
      color: $green-9;
      background-color: $green-3;
      border-color: $green-3;
      box-shadow: $shadow;
      @include ripple($green-4, $green-5);
      &:hover {
        border-color: $green-4;
        box-shadow: $shadow-md;
      }
      &:active {
        box-shadow: $shadow;
      }
      &:focus {
        @include focus-ring($green-5);
      }
      &--outline {
        transition: all;
        background-color: transparent;
        box-shadow: none;
        color: $green-9;
        border-color: $green-5;

        &:hover,
        &:active,
        &.active {
          color: $green-9;
          border-color: $green-3;
          background-color: $green-3;
        }
        &:focus {
          @include focus-ring($green-6);
        }
      }
    }
    &--outline {
      transition-property: background-color, color, fill, stroke, border-color;
      transition-duration: 0.5s;
      background-color: transparent;
      &:hover {
        color: $gray-0;
        fill: $gray-0;
        background-color: $gray-7;
      }
      &:active {
        color: $gray-0;
        fill: $gray-0;
        background-color: $gray-7;
      }
      &.active {
        border-color: $gray-8;
        background-color: $gray-8;
        color: $gray-0;
        fill: $gray-0;
      }
    }
    &--sm {
      padding: $spacer-2 $spacer-3;
      font-size: $text-xs !important;
      line-height: 1rem !important;
      @include tablet {
        font-size: $text-sm !important;
      }
    }
    &--lg {
      font-size: $text-lg !important;
      line-height: 1.75rem !important;
      padding: $spacer-5 $spacer-6;
      @include tablet {
        font-size: $text-xl !important;
      }
    }
    &--icon {
      height: 100%;
      fill: $gray-6;
      svg {
        height: 24px;
        width: 24px;
      }
    }
  }
  .btn-ripple {
    @include ripple($gray-7, $gray-8);
  }

  .btn--block {
    display: block;
  }
  .btn--link {
    display: inline-block;
  }
</style>
