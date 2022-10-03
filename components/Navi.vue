<script setup lang='ts'>
const supabase = useSupabaseClient()
const user = useSupabaseUser()

const logout = async () => {
  await supabase.auth.signOut()
}
</script>

<template>
  <nav>
    <button v-if='user' @click='logout' class='button'> Sign Out </button>
    <a v-else href='/signup' class='text-white'> Sign In </a>
  </nav>
</template>

<style>
.button {
  @apply hover:text-pink-300
}

nav {
  @apply items-start justify-start;
  margin-left: 3rem;
  margin-top: 1rem !important;
}
</style>