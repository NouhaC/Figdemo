<template>
  <section>
    <prismic-rich-text class="content-section" :class="'text-section'" :field="slice.primary.richtext"/>
  </section>
</template>

<script>
export default {
  props: {
    slice: {
      type: Object,
      required: true,
      default() {
        return {}
      }
    }
  },
}
</script>

<style lang="sass" scoped>
.text-section
    margin: 80px 0;
    padding: 48px;
    background-color: #f6f5f5;
    text-align: center;
    color: #091c18;

.text-section-1col img, .text-section-2col img, .gallery img
    margin: 80px 0;
    padding: 48px;
    background-color: #f6f5f5;
    text-align: center;
    color: #091c18;

.text-section-1col p:last-child, .text-section-2col p:last-child, .content-section.text-section-2col
  margin-bottom: 0

@media (max-width: 767px)
  .text-section-2col
    -webkit-column-count: 1
    -moz-column-count: 1
    column-count: 1
    -webkit-column-gap: 40px
    -moz-column-gap: 40px
    column-gap: 40px
</style>
