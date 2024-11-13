<template>
  <q-page padding>
    <q-card>
      <q-card-section>
        <div class="text-h4">Registracija</div>
        <div class="text-subtitle2">Unesite podatke za registraciju.</div>
      </q-card-section>

      <q-card-section>
        
        <q-input v-model="username" label="Korisničko ime" />
        <q-input v-model="email" label="E-mail" />
        <q-input v-model="password" type="password" label="Lozinka" />
        <q-input v-model="confirmPassword" type="password" label="Potvrdi lozinku" />

        <q-btn @click="submitRegistration" label="Potvrdi" color="primary" />
      </q-card-section>
    </q-card>
  </q-page>
</template>

<script>
export default {
  data() {
    return {
      username: '',
      email: '',
      password: '',
      confirmPassword: '',
    };
  },
  methods: {
    submitRegistration() {
      if (this.password !== this.confirmPassword) {
        alert('Lozinke se ne podudaraju!');
        return;
      }
      
      console.log('Registracija korisnika:', this.username);
    },
  },
};
</script>
