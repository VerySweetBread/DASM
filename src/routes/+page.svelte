<style>
	.nav-group {
		margin: 1rem;
		display: flex;
		align-items: baseline;
		justify-content: center;
	}

	.list-nav {
		margin: 1rem;
		background-color: rgb(var(--color-surface-800));
	}

	.title {
		width: 100%;
		display: inline-block;
		height: 1.5rem;
		text-align: center;
		background-color: rgb(var(--color-surface-700));
	}
</style>

<nav class="nav-group">
	<nav class="list-nav">
		<span class="title">Архитектуры</span>
		<ul>
			<li>
				<a href="#">
					<span class="flex-auto">X86</span>
					<a href="/cs/x86"> <span>Заметки</span> </a>
				</a>
			</li>
			<li>
				<a href="#">
					<span class="flex-auto">ARM</span>
					<a href="/cs/x86"> <span>Заметки</span> </a>
				</a>
			</li>
			<!-- ... -->
		</ul>
	</nav>
	<nav class="list-nav">
		<span class="title">Операционные системы</span>
		<ul>
			<li>
				<a href="#">
					<span class="flex-auto">Linux</span>
					<a href="/cs/kos"> <span>Заметки</span> </a>
					<!-- <a href="/tutorial/kos"> <span>Туториал</span> </a> -->
				</a>
			</li>
			<li>
				<a href="#">
					<span class="flex-auto">Windows</span>
					<a href="/cs/kos"> <span>Заметки</span> </a>
					<!-- <a href="/tutorial/kos"> <span>Туториал</span> </a> -->
				</a>
			</li>
			<li>
				<a href="#">
					<span class="flex-auto">КолибриОС</span>
					<a href="/tutorial/kos/get-started"> <span>Туториал</span> </a>
					<a href="/cs/kos/get-started"> <span>Заметки</span> </a>
				</a>
			</li>
		</ul>
	</nav>
</nav>
