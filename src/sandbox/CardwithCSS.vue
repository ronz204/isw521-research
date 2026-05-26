<script lang="ts" setup>
const specs = ['7.4" OLED', '512GB / 1TB', 'Wi-Fi 6E']
</script>

<template>
  <div class="card">
    <!-- Image Section -->
    <div class="card__image-wrapper">
      <img src="@assets/steamdeck.jpg" alt="Steam Deck OLED" class="card__image" />
      <span class="card__badge">Nuevo</span>
    </div>

    <!-- Content Section -->
    <div class="card__content">
      <!-- Title & Brand -->
      <div class="card__header">
        <p class="card__brand">Valve</p>
        <h2 class="card__title">Steam Deck OLED</h2>
      </div>

      <!-- Description -->
      <p class="card__description">
        La consola portátil más potente. Pantalla HDR OLED de 7.4&quot;,
        hasta 12 horas de batería y acceso a tu biblioteca completa de Steam.
      </p>

      <!-- Specs -->
      <div class="card__specs">
        <span v-for="spec in specs" :key="spec" class="card__spec">
          {{ spec }}
        </span>
      </div>

      <!-- Price & CTA -->
      <div class="card__footer">
        <div class="card__price-group">
          <p class="card__price">$549</p>
          <p class="card__price-note">USD • Envío gratis</p>
        </div>
        <button class="card__buy-btn">Comprar</button>
      </div>
    </div>
  </div>
</template>

<style scoped>
.card {
  width: 100%;
  max-width: 28rem;
  overflow: hidden;
  border-radius: 0.75rem;
  background-color: #18181b;
  border: 1px solid #27272a;
  padding-top: 1.5rem;
  padding-bottom: 1.5rem;
}

.card__image-wrapper {
  position: relative;
  aspect-ratio: 16 / 9;
  overflow: hidden;
  background-color: #09090b;
}

.card__image {
  width: 100%;
  height: 100%;
  object-fit: cover;
}

.card__badge {
  position: absolute;
  top: 0.75rem;
  left: 0.75rem;
  background-color: #2563eb;
  color: #ffffff;
  font-size: 0.75rem;
  font-weight: 600;
  padding: 0.25rem 0.625rem;
  border-radius: 9999px;
}

.card__content {
  padding: 1.25rem;
  display: flex;
  flex-direction: column;
  gap: 1rem;
}

.card__header {
  display: flex;
  flex-direction: column;
  gap: 0.25rem;
}

.card__brand {
  font-size: 0.75rem;
  font-weight: 500;
  text-transform: uppercase;
  letter-spacing: 0.05em;
  color: #60a5fa;
}

.card__title {
  font-size: 1.25rem;
  font-weight: 700;
  color: #ffffff;
}

.card__description {
  font-size: 0.875rem;
  color: #a1a1aa;
  line-height: 1.625;
}

.card__specs {
  display: flex;
  flex-wrap: wrap;
  gap: 0.5rem;
}

.card__spec {
  background-color: #27272a;
  color: #d4d4d8;
  font-size: 0.75rem;
  font-weight: 500;
  padding: 0.25rem 0.625rem;
  border-radius: 9999px;
}

.card__footer {
  display: flex;
  align-items: center;
  justify-content: space-between;
  padding-top: 0.5rem;
}

.card__price-group {
  display: flex;
  flex-direction: column;
  gap: 0.125rem;
}

.card__price {
  font-size: 1.5rem;
  font-weight: 700;
  color: #ffffff;
}

.card__price-note {
  font-size: 0.75rem;
  color: #71717a;
}

.card__buy-btn {
  background-color: #2563eb;
  color: #ffffff;
  font-size: 0.875rem;
  font-weight: 500;
  padding: 0.5rem 1.5rem;
  border-radius: 0.375rem;
  border: none;
  cursor: pointer;
  transition: background-color 0.15s ease;
}

.card__buy-btn:hover {
  background-color: #1d4ed8;
}
</style>
