<template>
  <article class="flex flex-col gap-4 max-w-96 font-sans">
    <img
      :src="imgSource || defaultImgSource"
      class="w-full h-60 bg-neutral-200 rounded-lg object-cover"
      :alt="`Image for the blog post: ${title}`"
      tabindex="0"
    />
    <div>
      <header>
        <h3 class="font-semibold leading-6 text-base mb-2 text-neutral-950">
          {{ title }}
        </h3>
      </header>
      <p class="text-sm leading-5 text-neutral-700">
        {{ description }}
      </p>
    </div>
    <span class="text-xs leading-4 text-neutral-700">- {{ writer }}</span>
  </article>
</template>
<script setup lang="ts">
// add a default img source in case PostDetails.imgSource is not provided.
const defaultImgSource = "";

const { title, description, writer, imgSource } = defineProps<{
  title: string;
  description: string;
  writer: string;
  imgSource?: string;
}>();
</script>
