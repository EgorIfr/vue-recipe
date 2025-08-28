<template>
  <div class="" @click="openModal">
    <div class="">
      <img :src="meal.strMealThumb" :alt="meal.strMeal" loading="lazy">
      <div class="">{{ meal.strCategory }}</div>
    </div>

    <div class="">
      <h3 class="">{{ meal.strMeal }}</h3>
      <p class="">{{ meal.strArea }}</p>

      <div class="">
        <span
        v-for="tag in tags"
        :key="tag"
        >
          {{ tag }}
        </span>
      </div>
    </div>
  </div>
</template>

<script>
import { computed } from 'vue';

export default {
  name: 'MealCard',
  props: {
    meal: {
      type: Object,
      required: true,
    }
  },
  emits: ['meal-selected'],
  setup(props, {emit}) {
    const tags = computed(() => {
      return props.meal.strTags ? props.meal.strTags.split(",") : []
    })

    const openModal = () => {
      emit('meal-selected', props.meal)
    }
    return {
      tags, openModal,
    }
  }
}
</script>
