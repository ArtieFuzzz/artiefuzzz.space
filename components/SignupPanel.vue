<script setup lang='ts'>
const supabase = useSupabaseClient()
const router = useRouter()

const email = ref('')
const password = ref('')
const loading = ref(false)
const handleSignup = async () => {
  loading.value = true

  try {
    const { error } = await supabase.auth.signUp({ email: email.value, password: password.value }, { redirectTo: '/' })
    if (error) throw error
  } catch (err) {
    alert(err.error_description ?? err.message)
  } finally {
    loading.value = false
    router.push('/')
  }
}
</script>

<template>
  <form @submit.prevent='handleSignup'>
    <div class='prose prose-zinc lg:prose-xl w-screen h-screen'>
      <div class='flex flex-col justify-center items-center w-screen h-screen'>
        <h1 class='text-white font-bold'>Sign up</h1>
        <div class='box'>
          <label for="email-input">Email</label>
          <input class='input-text' id='email-input' type="email" placeholder='Email Address' v-model='email'
            required />
        </div>
        <div class='box' style='margin-top: 1rem' >
          <label for="password-input">Password (5 Characters Minimum)</label>
          <input class='input-text' id='password-input' type="password" placeholder='Password' v-model='password'
            required minlength='5' />
        </div>
        <button class='button' type='submit' style='padding-top: 1rem' :disabled='loading'>
          {{ loading ? 'Loading...' : 'Submit' }}
        </button>
      </div>
    </div>
  </form>
</template>


<style>
label {
  @apply text-white font-semibold;
}

input {
  text-align: center;
}

.box {
  @apply flex flex-col justify-center items-center;
}

.input-text {
  @apply text-white bg-black;
  border-radius: 8px;

}

.button {
  @apply text-white hover:text-pink-300;
}
</style>