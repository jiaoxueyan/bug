<template>
	value{{value}}
	<wd-picker-view ref="picker" :columns="storeList" v-model="value" label-key="storeName" value-key="storeId" />
	<button @click="getList">getList</button>
	<button @click="getSelects">getSelects</button>
</template>

<script lang="ts" setup>
	import {ref} from 'vue'
	const storeList = ref([])
	const value = ref<string>('')
	const getList = () => {
		storeList.value = [
			{
				storeId: 1,
				storeName: 'aaa'
			}
		]
	}
	
	const picker = ref()
	const getSelects = () => {
		console.log(picker.value.getValues())
		console.log(picker.value.getSelects())
	}
</script>

<style>
</style>
