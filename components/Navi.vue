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
    <UButton v-if='user' @click='logout' class='button' label='Sign Out' target='_blank' icon='mdi:door-open' variant='black' />
    <UButton v-else @click='signIn' class='button' label='Sign In' target='_blank' icon='mdi:discord' variant='black'/>
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