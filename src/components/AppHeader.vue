<template>
    <header>
        <h1>Cooking Masterclass</h1>
        <span class="wishlist">wishlist ({{ wishlistCount }})</span>
    </header>
</template>

<script >
export default {
  props: ['wishlistCount']
}
</script>