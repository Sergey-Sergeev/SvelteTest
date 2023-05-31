<nav>
    <dir class="nav-container">
        <a href="/" class="nav-logo" title="Back to Homepage">Sergey Sergeev</a>
        <div class="nav-links">
            <a href="/about" class="link">About me</a>
            <a href="/blog" class="link">Blog</a>
            <a href="/projects" class="link">My projects</a>
            <a href="/contact" class="link">Contacts</a>
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