<template>
  <div>
    <NuxtPage />
  </div>
</template>

<script setup lang='ts'>
  useHead({
    title: 'Artie',
    meta: [
      { charset: 'utf-8' },
      { name: 'theme-color', content : '#f9a8d4' },
      { name: 'og:image', content: '/profilepic.png'},
      { name: 'og:description', content: 'Australian Developer doing Frontend and Backend' },
      { description: 'Australian Developer doing Frontend and Backend' },
      { name: 'og:url', content: 'https://artiefuzzz.space' },
      { keywords: 'ArtieFuzzz, Artie, Fuzzz, Fuzz, Fuzzzy' }

    ],
    link: [
      { rel: 'icon', href: '/favicon.png' }
    ],
    script: [
      { defer: true, async: true, src: 'https://analytics.artiefuzzz.space/umami.js', 'data-website-id': '04c0fa1c-3536-4ec4-b4da-a5b2968fd6f0' },
      { defer: true, async: true, src: 'https://arc.io/widget.min.js#RHQdmiNq' }
    ]
  })
</script>