<script setup >
import BannerComponent from './components/BannerComponent.vue';

</script>

 <template>
  <div class="p-0 md:p-16 space-y-16">
  <BannerComponent
    mode="square"
    :carouselOnMobile="false"
    :items="[
      {
        type: 'image',
        aspectRatio: 'square',
        src: 'https://picsum.photos/400',
        link: 'https://example.com/link1'
      },
      {
        type: 'cta',
        title: 'CTA Title',
        button: 'CTA Button',
        link: 'https://example.com/link2',
        color:'bg-red-200'
      },
      {
        type: 'image',
        aspectRatio: 'square',
        src: 'https://picsum.photos/400',
        link: 'https://example.com/link3'
      }
    ]"
  />

  <BannerComponent
    mode="square"
    :carouselOnMobile="true"
    :items="[
      {
        type: 'cta',
        title: 'CTA Title',
        button: 'CTA Button',
        link: 'https://example.com/link1',
        color:'bg-yellow-200'
      },
      {
        type: 'image',
        aspectRatio: 'square',
        src: 'https://picsum.photos/400',
        link: 'https://example.com/link2'
      },
      {
        type: 'image',
        aspectRatio: 'square',
        src: 'https://picsum.photos/400',
        link: 'https://example.com/link3'
      },
      {
        type: 'image',
        aspectRatio: 'square',
        src: 'https://picsum.photos/400',
        link: 'https://example.com/link3'
      },
      {
        type: 'image',
        aspectRatio: 'square',
        src: 'https://picsum.photos/400',
        link: 'https://example.com/link3'
      },
      {
        type: 'image',
        aspectRatio: 'square',
        src: 'https://picsum.photos/400',
        link: 'https://example.com/link3'
      }
    ]"
  />

  <BannerComponent
    mode="rectangle"
    :carouselOnMobile="false"
    :items="[
      {
        type: 'image',
        aspectRatio: 'rectangle',
        src: 'https://picsum.photos/1200/400',
        link: 'https://example.com/link1'
      },
      {
        type: 'image',
        aspectRatio: 'square',
        src: 'https://picsum.photos/400',
        link: 'https://example.com/link1'
      },
      {
        type: 'cta',
        title: 'CTA Title',
        button: 'CTA Button',
        link: 'https://example.com/link1'
      }
    ]"
  />
  </div>
</template>

 <!-- <template>
  <div class="p-0 md:p-16 space-y-16">
    <BannerComponent
      mode="square"
      :carouselOnMobile="false"
      :items="squareItems"
    />

    <BannerComponent
      mode="square"
      :carouselOnMobile="true"
      :items="squareCarouselItems"
    />

    <BannerComponent
      mode="rectangle"
      :items="rectangleItems"
    />
  </div>
</template>

<script setup>
import BannerComponent from "../components/BannerComponent.vue"

const squareItems = [
  { type: "image",
   aspectRatio: "square",
    src: "https://picsum.photos/400",
     link: "https://example.com/link1" 
  },

  { type: "cta", title: "CTA Title", button: "CTA Button", link: "https://example.com/link2",color:"bg-red-200" },
  { type: "image", aspectRatio: "square", src: "https://picsum.photos/400", link: "https://example.com/link3" },
]

const squareCarouselItems = [
  { type: "cta", title: "CTA Title", button: "CTA Button", link: "https://example.com/link1",color:"bg-orange-200" },
  { type: "image", aspectRatio: "square", src: "https://picsum.photos/400", link: "https://example.com/link2" },
  { type: "image", aspectRatio: "square", src: "https://picsum.photos/400", link: "https://example.com/link3" },
  { type: "image", aspectRatio: "square", src: "https://picsum.photos/400", link: "https://example.com/link4" },
  { type: "image", aspectRatio: "square", src: "https://picsum.photos/400", link: "https://example.com/link3" },
  { type: "image", aspectRatio: "square", src: "https://picsum.photos/400", link: "https://example.com/link4" }
]

const rectangleItems = [
  { type: "image", aspectRatio: "rectangle", src: "https://picsum.photos/1200/400", link: "https://example.com/link1" },
  { type: "image", aspectRatio: "square", src: "https://picsum.photos/400", link: "https://example.com/link1" },
  { type: "cta", title: "CTA Title", button: "CTA Button", link: "https://example.com/link1" },
]
</script>

 -->