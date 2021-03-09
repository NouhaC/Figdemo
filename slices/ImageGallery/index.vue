<template>
  <section class='image-gallery content-section'>
    <prismic-rich-text :field="slice.primary.galleryTitle"/>
    <div class="gallery">
      <div v-for="item in slice.items" :key="item.id" class="gallery-item">
        <prismic-image :field="item.image"/>
        <div class="bottom-text">
          <prismic-rich-text :field="item.imageDescription"/>
          <prismic-link :field="item.link" class="gallery-link">{{ $prismic.asText(item.linkLabel) }}</prismic-link>
        </div>
      </div>
    </div>
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
.gallery
  display: -webkit-box
  // OLD - iOS 6-, Safari 3.1-6, BB7
  display: -ms-flexbox
  // TWEENER - IE 10
  display: -webkit-flex
  // NEW - Safari 6.1+. iOS 7.1+, BB10
  display: flex
  -webkit-flex-wrap: wrap
  flex-wrap: wrap
  -webkit-justify-content: space-between
  justify-content: space-between

.bottom-text
  margin-bottom: 0.3rem;

.gallery-item
  -webkit-box-flex: 0 1 48%
  -moz-box-flex: 0 1 48%
  -webkit-flex: 0 1 48%
  -ms-flex: 0 1 48%
  flex: 0 1 48%
  font-size: 2.5rem
  line-height: 1.1
  text-position: center
  margin-bottom: 0rem

.gallery-link
  margin-top: -20px
  text-transform: uppercase

@media (max-width: 767px)
  .content-section
    margin-bottom: 2rem
  .gallery-item
    -webkit-box-flex: 100%
    -moz-box-flex: 100%
    -webkit-flex: 100%
    -ms-flex: 100%
    flex: 20%
</style>
