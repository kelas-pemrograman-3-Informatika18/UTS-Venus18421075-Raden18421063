<template>
  <q-page class="bg-cyan-8">
    <div class="row">
      <q-card class="fixed-center col-md-3 col-xs-12 bg-grey-4" flat>
        <q-card-section>
          <div class="text-h5 q-pb-md" align="center">

            COSAAN-CLUB
          </div>
          <p class="text-h9 bg-blue-4">WEBSITE STUDY </p>
          <q-form
            @submit="onSubmit"
            @reset="onReset"
            class="q-gutter-md"
          >
            <q-input
              filled
              v-model="username"
              label="Username"
              lazy-rules
              :rules="[ val => val && val.length > 0 || 'Tolong Ketik Username']"
            />

            <q-input
              filled
              type="password"
              v-model="password"
              label="Password"
              lazy-rules
              :rules="[
                val => val !== null && val.length > 0 || 'Password Tidak Boleh Kosong'
              ]"
            />
            <div class="q-gutter-md">
              <q-btn label="Login" type="submit" color="primary"/>
              <q-btn label="Register" to="/register" flat color="primary"/>
            </div>
        </q-form>
        </q-card-section>
    </q-card>
    </div>
  </q-page>
</template>
<script>
export default {
  data () {
    return {
      username: null,
      password: null
    }
  },
  methods: {
    onSubmit () {
      if (this.username === 'venus' && this.password === '18421075') {
        this.$q.notify({
          type: 'positive',
          message: 'Selamat Berhasil Login'
        })
        this.$router.push('/home')
      } else {
        this.$q.notify({
          type: 'negative',
          message: 'Gagal Login, Username/Password Salah'
        })
      }
    },
    onReset () {
      this.username = null
      this.password = null
    }
  }
}
</script>
