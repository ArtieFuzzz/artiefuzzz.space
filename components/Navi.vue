<script setup lang='ts'>
const supabase = useSupabaseClient()
const user = useSupabaseUser()

const logout = async () => {
  await supabase.auth.signOut()
}

const signIn = async () => {
  try {
    const { error } = await supabase.auth.signIn({ provider: 'discord' })
    if (error) throw error
  } catch(err) {
    alert(err.error_description ?? err.message)
  }
}
</script>

<template>
  <nav class='navbar'>
    <button v-if='user' @click='logout' class='button'> Sign Out </button>
    <button v-else @click='signIn' class='button'> Sign In </button>
  </nav>
</template>

<style>
.button {
  @apply hover:text-pink-300 text-white;
}

.navbar {
  @apply items-start justify-start;
  margin-left: 3rem;
  margin-top: 1rem !important;
}
</style>