<script setup lang="ts">
import { NConfigProvider } from "naive-ui";
import TitleBar from "@renderer/components/TitleBar.vue";
import DragRegion from "@renderer/components/DragRegion.vue";
import NavBar from "./components/NavBar.vue";

onMounted(async () => {
	console.log("App mounted");
	await nextTick();
	throw new Error("Test error");
});
</script>
<template>
	<n-config-provider class="h-full w-[100vw] flex text-tx-primary">
		<aside class="siderbar h-full flex flex-shrink-0 flex-col w-[320px]">
			<div class="flex-auto flex">
				<nav-bar />
				<div class="flex-auto">conversation-list</div>
			</div>
		</aside>
		<div class="flex-auto">
			<title-bar>
				<drag-region class="w-full" />
			</title-bar>
			Main
		</div>
	</n-config-provider>
</template>

<style scoped>
.siderbar {
	background-color: var(--bg-color);
	box-shadow: -3px -2px 10px rgba(101, 101, 101, 0.2);
}
</style>
