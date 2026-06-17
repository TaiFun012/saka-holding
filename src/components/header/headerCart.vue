<script setup lang="ts">

interface Props {
  count?: number;
}


const props = withDefaults(defineProps<Props>(), {
  count: 0
});
</script>

<template>
  <div class="header-cart">
    <div class="cart-icon-wrapper">
      
      
      <div class="cart-circle">
        <img 
          src="@/assets/icons/ShoppingCart.svg" 
          alt="Корзина" 
          class="cart-icon" 
        />
      </div>
      
      
      <span v-if="props.count > 0" class="cart-badge">
        {{ props.count }}
      </span>

    </div>
  </div>
</template>

<style scoped>
.header-cart { 
  cursor: pointer; 
  display: flex;
  align-items: center;
  justify-content: center;
}

.cart-icon-wrapper { 
  position: relative; 
  display: inline-flex; 
}

.cart-circle {
  width: 44px; 
  height: 44px;
  background-color: #243241 !important; 
  border: 1px solid #2d3d4f; 
  border-radius: 50%; 
  display: flex;
  align-items: center;
  justify-content: center;
  transition: background-color 0.2s ease;
}

.cart-circle:hover {
  background-color: #2d3d4f !important; 
}

.cart-icon {
  width: 20px; 
  height: 20px;
  object-fit: contain;
}

.cart-badge {
  position: absolute;
  top: 0;
  right: 0;
  background-color: #f5eedc !important; 
  color: #614e3b !important; 
  font-family: sans-serif;
  font-size: 10px;
  font-weight: 700;
  line-height: 1;
  border-radius: 10px;
  padding: 3px 6px;
  min-width: 12px;
  text-align: center;
  border: 1.5px solid #243241 !important; 
  transform: translate(25%, -25%);
  z-index: 2;
}
</style>
