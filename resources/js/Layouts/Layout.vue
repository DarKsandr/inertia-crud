<script setup>
import { Link, Head } from '@inertiajs/vue3'

</script>

<template>
    <Head title="Laravel" />
    <header>
        <nav class="navbar navbar-expand-lg bg-light">
            <div class="container-fluid">
                <a class="navbar-brand" href="#">Laravel</a>
                <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarNav" aria-controls="navbarNav" aria-expanded="false" aria-label="Toggle navigation">
                    <span class="navbar-toggler-icon"></span>
                </button>
                <div class="collapse navbar-collapse" id="navbarNav">
                    <ul class="navbar-nav">
                        <li class="nav-item">
                            <Link href="/" class="nav-link" :class="{active: $page.url === '/'}">Home</Link>
                        </li>
                        <li class="nav-item">
                            <Link href="/post" class="nav-link" :class="{active: $page.url === '/post'}">Posts</Link>
                        </li>
                    </ul>
                </div>
            </div>
        </nav>
    </header>
    <main class="container">
        <slot />
    </main>
</template>