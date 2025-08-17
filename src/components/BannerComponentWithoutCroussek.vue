<template>
  <!-- Square Mode -->
  <div v-if="mode === 'square'" class="w-full">
  <div v-if="carouselOnMobile" class="md:hidden flex flex-col">
      <!-- Custom Mobile Carousel Layout: CTA on top, then first image, then stacked images -->
      <template v-if="items.length">
        <component
          v-if="items[0].type === 'cta'"
          :is="resolveComponent(items[0])"
          v-bind="items[0]"
          :mode="mode"
        />
        <component
          v-if="items[1] && items[1].type === 'image'"
          :is="resolveComponent(items[1])"
          v-bind="items[1]"
          :mode="mode"
        />
        <div v-if="items.length > 2" class="flex flex-row overflow-x-auto">
          <div v-for="(item, index) in items.slice(2)" :key="index + 2" class="w-30 h-30 flex-shrink-0 overflow-hidden rounded-lg mr-2">
            <component
              v-if="item.type === 'image'"
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