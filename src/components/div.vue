<template>
	<div v-for="(tag,index) in tags" :key="index">
	        {{tag}}
	        <a @click.prevent="removeTag(index)" href="#">&times;</a>
	    </div>
	    <hr />
	    {{newTag}}
	    <input 
	        type="text" 
	        v-model.trim="newTag"
	        @keydown.enter="addNewTag"
	        @keydown.delete="removeLastTag"
	        @keydown.tab.prevent="addNewTag"  
	        :class="{'tag-exists': isTagExists }"
	    />
</template>

<script setup lang="ts">
defineProps<{ 
	tags: string[];
	removeTag: (index: any) => void;
	newTag: string;
	addNewTag: () => void;
	removeLastTag: () => void;
	isTagExists: boolean;
}>()
</script>
