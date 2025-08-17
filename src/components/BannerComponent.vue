
<template>
  <!-- Square Mode -->
  <div v-if="mode === 'square'" class="w-full">
  <div v-if="carouselOnMobile" class="md:hidden flex flex-col">
    <template v-if="items.length">
      <component
        v-if="items.find(i => i.type === 'cta')"
        :is="resolveComponent(items.find(i => i.type === 'cta'))"
        v-bind="items.find(i => i.type === 'cta')"
        :mode="mode"
      />
      <Swiper :slides-per-view="1" class="w-full aspect-square mb-2">
        <SwiperSlide v-for="(item, idx) in items.filter(i => i.type === 'image')" :key="'main-' + idx">
          <component
            :is="resolveComponent(item)"
            v-bind="item"
            :mode="mode"
          />
        </SwiperSlide>
      </Swiper>
      <div v-if="items.filter(i => i.type === 'image').length > 1" class="flex flex-row overflow-x-auto">
        <div v-for="(item, index) in items.filter(i => i.type === 'image')" :key="'thumb-' + index" class="w-20 h-20 flex-shrink-0 overflow-hidden rounded-lg mr-2 sm:w-24 sm:h-24 md:w-32 md:h-32">
          <component
            :is="resolveComponent(item)"
            v-bind="item"
            :mode="mode"
          />
        </div>
      </div>

    </template>
  </div>

  <div v-else class="md:hidden flex flex-col w-full">
      <div
        v-for="(item, index) in items"
        :key="index"
        class="w-full"
      >
        <component
          :is="resolveComponent(item)"
          v-bind="item"
          :mode="mode"
        />
      </div>
    </div>

  <div class="hidden md:grid grid-cols-3">
      <div
        v-for="(item, index) in items"
        :key="index"
        class="aspect-square"
      >
        <component
          :is="resolveComponent(item)"
          v-bind="item"
          :mode="mode"
        />
      </div>
    </div>
  </div>

  <!-- Rectangle Mode -->
  <div v-else-if="mode === 'rectangle'" class="relative">
    <div class="hidden md:block">
      <BannerImage
        v-if="items[0]?.type === 'image'"
        :src="items[0].src"
        :link="items[0].link"
      />
      <BannerCTA
        v-if="items.find(i => i.type === 'cta')"
        v-bind="items.find(i => i.type === 'cta')"
        mode="rectangle"
      />
    </div>

  <div class="md:hidden flex flex-col">
      <BannerImage
        v-if="items[1]?.type === 'image'"
        :src="items[1].src"
        :link="items[1].link"
      />
      <BannerCTA
        v-if="items.find(i => i.type === 'cta')"
        v-bind="items.find(i => i.type === 'cta')"
        mode="square"
      />
    </div>
  </div>
</template>

<script setup>
import BannerImage from "./BannerImage.vue"
import BannerCTA from "./BannerCTA.vue"
import { Swiper, SwiperSlide } from 'swiper/vue';
import 'swiper/swiper-bundle.css';

defineProps({
  mode: { type: String, required: true },
  carouselOnMobile: { type: Boolean, default: false },
  items: { type: Array, required: true },
})

const resolveComponent = (item) => {
  if (item.type === "image") return BannerImage
  if (item.type === "cta") return BannerCTA
  return "div"
}
</script>
