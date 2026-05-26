<script setup lang="ts">
import CardwithCSS from '@sandbox/CardwithCSS.vue';
import CardwithTail from '@sandbox/CardwithTail.vue';
</script>

<template>
  <main class="min-h-screen bg-zinc-950 flex items-center justify-center p-8">
    <div class="flex flex-col sm:flex-row items-start justify-center gap-12">

      <div class="flex flex-col items-center gap-3">
        <span
          class="text-xs font-semibold uppercase tracking-widest text-zinc-400 border border-zinc-700 rounded-full px-3 py-1">
          Vue Scoped CSS + BEM
        </span>
        <CardwithCSS />
      </div>

      <div class="hidden sm:block w-px self-stretch bg-zinc-800"></div>

      <div class="flex flex-col items-center gap-3">
        <span
          class="text-xs font-semibold uppercase tracking-widest text-zinc-400 border border-zinc-700 rounded-full px-3 py-1">
          Tailwind CSS
        </span>
        <CardwithTail />
      </div>

    </div>
  </main>
</template>
