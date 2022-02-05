<template>
	<a-card hoverable style="width: 160px">
		<template #cover>
			<img alt="example" src="../assets/rabbit_img.jpg" />
		</template>
		<div>
			<h2>В нашем роддоме родились</h2>
			<p>пушистых коров: {{ items.cows }}</p>
			<p>милых кроликов: {{ items.rabbits }}</p>
			<p>крутых овц: {{ items.sheeps }}</p>
		</div>
	</a-card>
</template>

<script setup>
import { onMounted, computed } from 'vue'
import { useStore } from 'vuex'

const store = useStore()
const items = computed(() => store.getters.getWidget)

onMounted(() => {
	store.dispatch('setWidget')
})
</script>

<style lang="scss" scoped></style>
