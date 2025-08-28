<template>
  <div>
    <div v-if="loading">
      <div v-for="n in 8" :key="n">
        <div></div>
        <div>
          <div></div>
          <div></div>
        </div>
      </div>
    </div>

    <div v-else-if="Error">
      <p>{{ error }}</p>
      <button @click="$emit('retry')">Повторить попытку</button>
    </div>

    <div v-else-if="meals.length === 0">
      <p>Рецепты не найдены</p>
    </div>

    <div v-else>
      <Card v-for="meal in meals" :key="meal.idMeal" :meal="meal" @meal-selected="$emit('meal-selected', $event)"></Card>
    </div>
  </div>
</template>

<script>
import Card from './MainCard.vue'
export default {
  name: 'MealCard',
  components: { Card },
  props: {
    meals: {
      type: Array,
      default: () => []
    },
    loading: {
      type: Boolean,
      default: false
    },
    error: {
      type: String,
      default: ''
    }
  },
  emits: ['meal-selected', 'retry']

}
</script>
