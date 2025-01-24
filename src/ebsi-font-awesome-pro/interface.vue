<template>
	<input :value="value" @input="handleChange($event.target.value)" />
</template>

<script lang="ts">
import { defineComponent } from 'vue';

export default defineComponent({
	props: {
		value: {
			type: String,
			default: null,
		},
	},
	emits: ['input'],
	setup(props, { emit }) {
		return { handleChange };

		function handleChange(value: string): void {
			console.log('working')
			emit('input', value);
		}
	},
});
</script>
