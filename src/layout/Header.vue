<template>
    <nav class="navbar navbar-dark bg-info">
        <a href="#" class="navbar-brand">
            <img src="../assets/logo.png" width="30" height="30" alt="Brand">
        </a>
        <span class="navbar-text text-light">
            {{ title }}
        </span>
    </nav>
</template>

<script>
export default {
    name: "Header",
    props: ["title"],
}
</script>

<style>

</style>