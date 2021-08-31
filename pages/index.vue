<template>
  <div
    class="
      h-screen
      w-screen
      bg-yellow-50
      flex flex-col
      items-stretch
      overflow-hidden
      gap-0.5
    "
  >
    <!-- top bar -->
    <div
      class="
        border-b-4 border-yellow-900
        flex flex-row
        space-between
        items-center
        px-4
        py-2
      "
    >
      <!-- logo -->
      <div class="flex-grow">
        <img
          class="cursor-pointer hover:opacity-70 h-16 w-auto"
          src="https://upload.wikimedia.org/wikipedia/en/9/9d/Eternal_University_logo.png"
          alt="Eternal University, Baru Sahib, HP"
          title="Eternal University, Baru Sahib, HP"
          @click="loadIframeUrl(euHomePage)"
        />
      </div>
      <!-- nav -->
      <div
        class="cursor-pointer text-2xl hover:opacity-70"
        title="Refresh"
        @click="loadIframeUrl(carbonCalcUrl)"
      >
        🔃
      </div>
    </div>
    <!-- iframe -->
    <iframe
      class="h-full overflow-y-scroll block"
      frameborder="0"
      marginwidth="0"
      marginheight="0"
      scrolling="yes"
      :src="iframeSrc"
    ></iframe>
  </div>
</template>

<script lang="ts">
import Vue from 'vue'

export default Vue.extend({
  data() {
    return {
      iframeSrc: '',
      euHomePage: 'https://www.eternaluniversity.edu.in/',
      carbonCalcUrl:
        'https://calculator.carbonfootprint.com/calculator.aspx?b=99CCFF',
    }
  },
  beforeMount() {
    this.iframeSrc = this.carbonCalcUrl
  },
  methods: {
    loadIframeUrl(url: string) {
      this.iframeSrc = url
    },
  },
})
</script>
