<script lang="ts">
    import { AppShell } from '@skeletonlabs/skeleton';
    import { page } from '$app/stores';

    $: classesActive = (href: string) => (href === $page.url.pathname ? '!bg-primary-active-token' : '');
</script>

<style>
    .list-nav {
        height: 100%;
        background-color: rgb(var(--color-surface-900));
    }
</style>

<AppShell>
    <svelte:fragment slot="sidebarLeft">
        <nav class="list-nav">
            <ul>
                <li>
                    <a href="get-started" class="{classesActive("/cs/kos/get-started")}">
                        <span class="flex-auto">Для начала</span>
                    </a>
                </li>
                <li>
                    <a href="sysfunc" class="{classesActive("/cs/kos/sysfunc")}">
                        <span class="flex-auto">Системные функции</span>
                    </a>
                </li>
            </ul>
        </nav>
    </svelte:fragment>
    <slot />
</AppShell>