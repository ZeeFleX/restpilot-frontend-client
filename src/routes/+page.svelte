<script lang="ts">
	import { MenuItem } from '$lib/components/client/menuItem';
	import { MenuCategories } from '$lib/components/client/menuCategories';
	import type { Picture } from 'vite-imagetools';
	import philadelphiaRoll from '$lib/assets/images/rolls/philadelphia.jpg?enhanced';
	import dragonRoll from '$lib/assets/images/rolls/dragon.jpg?enhanced';
	import tempuraRoll from '$lib/assets/images/rolls/tempura.jpg?enhanced';

	interface IMenuItem {
		title: string;
		weight: string;
		description: string;
		price: number;
		image: Picture | string;
		imageAlt: string;
		isNew?: boolean;
	}

	const handleOrderClick = () => {
		console.log('Order clicked!');
		// Здесь будет логика заказа
	};

	const menuItems: IMenuItem[] = [
		{
			title: 'Ролл Филадельфия',
			weight: '280 г',
			description:
				'Классический ролл с нежным лососем, сливочным сыром и свежим огурцом. Украшен тонкими ломтиками слабосоленого лосося',
			price: 450,
			image: philadelphiaRoll,
			imageAlt: 'Ролл Филадельфия - классический ролл с лососем',
			isNew: true
		},
		{
			title: 'Ролл Дракон',
			weight: '290 г',
			description:
				'Изысканный ролл с копченым угрем, авокадо и огурцом, украшенный тонкими ломтиками авокадо и соусом унаги',
			price: 520,
			image: dragonRoll,
			imageAlt: 'Ролл Дракон с угрем и авокадо'
		},
		{
			title: 'Ролл Темпура',
			weight: '260 г',
			description: 'Теплый ролл в хрустящей панировке с креветкой темпура, авокадо и спайси соусом',
			price: 390,
			image: tempuraRoll,
			imageAlt: 'Ролл Темпура в хрустящей панировке',
			isNew: true
		},
		{
			title: 'Калифорния с крабом',
			weight: '270 г',
			description: 'Популярный ролл с крабовым мясом, огурцом и авокадо, украшенный икрой тобико',
			price: 420,
			image: philadelphiaRoll,
			imageAlt: 'Ролл Калифорния с крабовым мясом'
		},
		{
			title: 'Радужный ролл',
			weight: '285 г',
			description: 'Эффектный ролл с лососем, тунцом и угрем на рисе с авокадо внутри',
			price: 580,
			image: dragonRoll,
			imageAlt: 'Радужный ролл с разными видами рыбы'
		},
		{
			title: 'Спайси лосось',
			weight: '250 г',
			description: 'Острый ролл с рубленым лососем, огурцом и фирменным спайси соусом',
			price: 390,
			image: tempuraRoll,
			imageAlt: 'Острый ролл с лососем'
		},
		{
			title: 'Унаги маки',
			weight: '240 г',
			description: 'Классический ролл с копченым угрем, огурцом и соусом унаги',
			price: 450,
			image: dragonRoll,
			imageAlt: 'Ролл с угрем'
		},
		{
			title: 'Бонито ролл',
			weight: '265 г',
			description: 'Теплый ролл с лососем и сливочным сыром, украшенный стружкой тунца',
			price: 440,
			image: philadelphiaRoll,
			imageAlt: 'Ролл с лососем и стружкой тунца'
		},
		{
			title: 'Вулкан',
			weight: '280 г',
			description: 'Запеченный ролл с креветкой, крабовым мясом и сырным соусом',
			price: 490,
			image: tempuraRoll,
			imageAlt: 'Запеченный ролл Вулкан'
		},
		{
			title: 'Зеленый дракон',
			weight: '295 г',
			description: 'Ролл с креветкой темпура внутри, украшенный авокадо и соусом васаби',
			price: 520,
			image: dragonRoll,
			imageAlt: 'Ролл Зеленый дракон с авокадо'
		},
		{
			title: 'Филадельфия люкс',
			weight: '290 г',
			description: 'Премиальный ролл с лососем, икрой тобико, авокадо и сливочным сыром',
			price: 590,
			image: philadelphiaRoll,
			imageAlt: 'Премиальный ролл Филадельфия'
		},
		{
			title: 'Темпура с угрем',
			weight: '275 г',
			description: 'Хрустящий ролл в панировке с угрем, авокадо и соусом унаги',
			price: 510,
			image: tempuraRoll,
			imageAlt: 'Темпура ролл с угрем'
		}
	];
</script>

<div class="mx-auto grid grid-cols-1 gap-4">
	<div class="relative sticky top-16 z-40">
		<MenuCategories />
	</div>
	<div class="relative grid grid-cols-1 gap-4 sm:grid-cols-2 md:grid-cols-3 lg:grid-cols-4">
		{#each menuItems as { title, weight, description, price, image, imageAlt, isNew }}
			<MenuItem
				{title}
				{weight}
				{description}
				{price}
				{image}
				{imageAlt}
				{isNew}
				onOrderClick={handleOrderClick}
			/>
		{/each}
	</div>
</div>

<style lang="postcss">
	@tailwind utilities;
</style>
