<nav>
    <dir class="nav-container">
        <a href="/" class="nav-logo" title="Back to Homepage">Sergey Sergeev</a>
        <div class="nav-links">
            {#each nav as link}
                {#if link.isShow}
                    <a href={link.href} class="link">{link.title}</a>
                {/if}
            {/each}
        </div>
    </dir>
</nav>

<div class="container">
    <slot></slot>
</div>

<style>
    .container {
        max-width: 1400px;
        margin: 50px auto;
    }
</style>

<script>
    const nav = 
    [
        {
            title: "Обо мне",
            href: "/about",
            isShow: true
        },
        {
            title: "Блог",
            href: "/blog",
            isShow: true
        },
        {
            title: "Портфолио",
            href: "/project",
            isShow: true
        },
        {
            title: "Контакты",
            href: "/contact",
            isShow: true
        },
        {
            title: "Учёты расходов",
            href: "/expense",
            isShow: true
        }
    ]



</script>