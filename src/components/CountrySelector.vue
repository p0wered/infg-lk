<script setup lang="ts">
import { ref, onMounted, onUnmounted } from 'vue';
import SvgChevron from "../icons/SvgChevron.vue";
import SvgCheckmark from "../icons/SvgCheckmark.vue";

const props = defineProps({
  modelValue: String
});

const emit = defineEmits(['update:modelValue']);

const countries = [
  {code: '7', name: 'Россия', flag: '🇷🇺'},
  {code: '1', name: 'США', flag: '🇺🇸'},
  {code: '44', name: 'Великобритания', flag: '🇬🇧'}
];

const selectedCountry = ref(countries.find(c => c.code === props.modelValue) || countries[0]);
const isOpen = ref(false);
const dropdownRef = ref<HTMLElement | null>(null);

const toggleDropdown = () => {
  isOpen.value = !isOpen.value;
};

const selectCountry = (country: any) => {
  selectedCountry.value = country;
  emit('update:modelValue', country.code);
  isOpen.value = false;
};

const handleClickOutside = (event: MouseEvent) => {
  if (dropdownRef.value && !dropdownRef.value.contains(event.target as Node)) {
    isOpen.value = false;
  }
};

onMounted(() => {
  document.addEventListener('mousedown', handleClickOutside);
});

onUnmounted(() => {
  document.removeEventListener('mousedown', handleClickOutside);
});
</script>

<template>
  <div class="country-selector" ref="dropdownRef">
    <div class="selected-country" @click="toggleDropdown">
      <span class="flag">{{ selectedCountry.flag }}</span>
      <SvgChevron :class="{'rotate-180': isOpen}" />
    </div>
    <div v-if="isOpen" class="dropdown-menu">
      <div
          v-for="country in countries"
          :key="country.code"
          class="dropdown-item"
          @click="selectCountry(country)"
      >
        <div class="item-text">
          <span class="flag">{{country.flag}}</span>
          <span class="name">{{country.name}}</span>
          <span class="code">+{{country.code}}</span>
        </div>
        <SvgCheckmark
            v-if="country.code === selectedCountry.code"
            class="checkmark"
        />
      </div>
    </div>
  </div>
</template>

<style scoped>
.country-selector {
  position: relative;
  display: inline-block;
}

.selected-country {
  display: flex;
  align-items: center;
  gap: 8px;
  cursor: pointer;
  border-radius: 4px;
}

.flag {
  font-size: 20px;
}

.dropdown-menu {
  position: absolute;
  top: 140%;
  left: -21px;
  z-index: 1000;
  background: white;
  border: 1px solid #fafafb;
  border-radius:6px;
  box-shadow: 0 4px 8px rgba(0,0,0,0.08);
  max-height: 300px;
  overflow-y: auto;
  width: 282px;
}

.dropdown-item {
  display: flex;
  align-items: center;
  justify-content: space-between;
  gap: 8px;
  padding: 8px 12px;
  cursor: pointer;
}

.dropdown-item .item-text {
  display: flex;
  align-items: center;
  gap: 6px;
}


.dropdown-item:hover {
  background: #f5f5f5;
}

.code {
  color: #666;
}

.rotate-180 {
  transform: rotate(180deg);
  transition: transform 0.2s ease;
}
</style>