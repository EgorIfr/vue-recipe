<script>
import SearchBar from './SearchBar.vue'
export default { components: { SearchBar } }
</script>

<template>
  <div class="space-y-6">
    <!-- Заголовок и поиск -->
    <div class="flex flex-col sm:flex-row sm:items-center sm:justify-between gap-4">
      <h2 class="text-2xl font-semibold">Поиск рецептов</h2>
      <SearchBar />
    </div>

    <!-- Фильтры -->
    <div class="flex gap-2 flex-wrap">
      <input type="checkbox" id="breakfast" class="hidden peer/breakfast" />
      <label
        for="breakfast"
        class="px-4 py-2 rounded-2xl border border-gray-300 cursor-pointer peer-checked/breakfast:bg-blue-500 peer-checked/breakfast:text-white hover:bg-gray-100 transition"
      >
        Завтрак
      </label>

      <input type="checkbox" id="lunch" class="hidden peer/lunch" />
      <label
        for="lunch"
        class="px-4 py-2 rounded-2xl border border-gray-300 cursor-pointer peer-checked/lunch:bg-blue-500 peer-checked/lunch:text-white hover:bg-gray-100 transition"
      >
        Обед
      </label>

      <input type="checkbox" id="dinner" class="hidden peer/dinner" />
      <label
        for="dinner"
        class="px-4 py-2 rounded-2xl border border-gray-300 cursor-pointer peer-checked/dinner:bg-blue-500 peer-checked/dinner:text-white hover:bg-gray-100 transition"
      >
        Ужин
      </label>

      <input type="checkbox" id="dessert" class="hidden peer/dessert" />
      <label
        for="dessert"
        class="px-4 py-2 rounded-2xl border border-gray-300 cursor-pointer peer-checked/dessert:bg-blue-500 peer-checked/dessert:text-white hover:bg-gray-100 transition"
      >
        Десерт
      </label>
    </div>
  </div>
</template>
