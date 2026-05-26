<script lang="ts" setup>
const specs = ['7.4" OLED', '512GB / 1TB', 'Wi-Fi 6E']
</script>

<template>
  <div class="w-full max-w-md overflow-hidden rounded-xl bg-zinc-900 border border-zinc-800 py-6">
    <!-- Image Section -->
    <div class="relative aspect-video overflow-hidden bg-zinc-950">
      <img src="@assets/steamdeck.jpg" alt="Steam Deck OLED" class="w-full h-full object-cover" />

      <span class="absolute top-3 left-3 bg-blue-600 text-white text-xs font-semibold px-2.5 py-1 rounded-full">
        Nuevo
      </span>
    </div>

    <!-- Content Section -->
    <div class="p-5 space-y-4">
      <!-- Title & Brand -->
      <div class="space-y-1">
        <p class="text-xs font-medium uppercase tracking-wider text-blue-400">Valve</p>
        <h2 class="text-xl font-bold text-white">Steam Deck OLED</h2>
      </div>

      <!-- Description -->
      <p class="text-sm text-zinc-400 leading-relaxed">
        La consola portátil más potente. Pantalla HDR OLED de 7.4&quot;,
        hasta 12 horas de batería y acceso a tu biblioteca completa de Steam.
      </p>

      <!-- Specs -->
      <div class="flex flex-wrap gap-2">
        <span v-for="spec in specs" :key="spec"
          class="bg-zinc-800 text-zinc-300 text-xs font-medium px-2.5 py-1 rounded-full">
          {{ spec }}
        </span>
      </div>

      <!-- Price & CTA -->
      <div class="flex items-center justify-between pt-2">
        <div class="space-y-0.5">
          <p class="text-2xl font-bold text-white">$549</p>
          <p class="text-xs text-zinc-500">USD • Envío gratis</p>
        </div>

        <button
          class="bg-blue-600 hover:bg-blue-700 text-white text-sm font-medium px-6 py-2 rounded-md transition-colors cursor-pointer">
          Comprar
        </button>
      </div>
    </div>
  </div>
</template>
