<template>
  <q-page padding>
    <q-card>
      <q-card-section>
        <div class="text-h4">Login</div>
        <div class="text-subtitle2">Unesite svoje korisničke podatke za prijavu.</div>
      </q-card-section>

      <q-card-section>
       
        <q-input v-model="username" label="Korisničko ime" />
        <q-input v-model="password" type="password" label="Lozinka" />
        <q-btn @click="submitLogin" label="Prijavi se" color="primary" />
      </q-card-section>
    </q-card>
  </q-page>
</template>

<script>
export default {
  data() {
    return {
      username: '',
      password: '',
    };
  },
  methods: {
    submitLogin() {
      console.log('Prijava korisnika:', this.username);
    },
  },
}
</script>
