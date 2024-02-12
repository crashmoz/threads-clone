<template>
	<div id="MainLayout" class="h-screen">
		<div class="w-full max-w-[500px] mx-auto">
			<div id="TopMenu" class="w-full flex items-center justify-center px-2 h-10 my-2">
				<img src="/threads-logo.png" class="w-[35px]">
			</div>
		</div>

		<div class="flex w-full max-w-[500px] mx-auto h-screen">
			<slot />
		</div>

		<CreatePost
			:class="[{ 'max-h-[100vh] transition-all duration-200 ease-in visible': userStore.isMenuOverlay }, { 'max-h-0 transition-all duration-200 ease-out invisible': !userStore.isMenuOverlay }]" />

		<Modal
			:class="[{ 'max-h-[100vh] transition-all duration-200 ease-in visible': userStore.isLogoutOverlay }, { 'max-h-0 transition-all duration-200 ease-out invisible': !userStore.isLogoutOverlay }]" />

		<div id="BottomNav" class="fixed z-50 bottom-0 flex w-full h-[70px] border-t border-t-gray-700 bg-black">
			<div class="flex w-full max-w-[500px] mx-auto items-center justify-around">
				<button @click="navigateTo('/')" class="w-full h-full">
					<Icon name="material-symbols:home-outline" size="35" color="#ffffff" />
				</button>
				<button @click="userStore.isMenuOverlay = true" class="w-full h-full">
					<Icon class="mb-1" name="material-symbols:edit-square-outline-rounded" size="32" color="#ffffff" />
				</button>
				<button @click="userStore.isLogoutOverlay = true" class="w-full h-full">
					<Icon class="mb-1" name="ph:sign-out" size="32" color="#ffffff" />
				</button>
			</div>
		</div>

	</div>
</template>

<script setup>
const userStore = useUserStore();
</script>