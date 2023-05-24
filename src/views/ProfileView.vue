<script setup>

const profiles = ref([
    {
        name: 'Link',
        schoolMail: 'mail@hatenoschool.hy',
        mail: 'link@hyrule.hy',
        year: 2000,
        schoolYear: 3,
        password: 'HYAH!'
    }


])

function newProfile() {
    const newElement = {
        name: newName.value,
        schoolMail: newSchoolMail.value,
        mail: newMail.value,
        year: parseFloat(newYear.value),
        schoolYear: parseFloat(newSchoolYear.value),
        password: newPassword.value
    }

    profiles.value.push(newElement)

}

const newName = ref();
const newSchoolMail = ref();
const newMail = ref();
const newYear = ref();
const newSchoolYear = ref();
const newPassword = ref();

</script>

<template>
      <h1>Profil</h1>
      
      <div class="form">
        <h2>Neuer Eintrag</h2>

        <label for="text">Name und Vorname</label>
        <input ref="newTextField" v-model="newName" type="text" name="text" id="text" @keyup.enter="newProfile">
        <label for="text">E-Mail Adresse der Schule</label>
        <input v-model="newSchoolMail" type="text" name="text" id="text" @keyup.enter="newProfile">
        <label for="text">E-Mail Adresse Privat</label>
        <input v-model="newMail" type="text" name="text" id="text" @keyup.enter="newProfile">
        <label for="text">Jahrgang</label>
        <input v-model="newYear" type="number" name="text" id="text" @keyup.enter="newEntry">
        <label for="text">Schuljahr</label>
        <input v-model="newSchoolYear" type="number" name="text" id="text" @keyup.enter="newEntry">
        <label for="text">Passwort</label>
        <input v-model="newPassword" type="password" name="text" id="text" @keyup.enter="newEntry">
        <button @click="newProfile">Profil erstellen</button>
    </div>
  </template>

  <style lang="scss">

  .form{
    display: flex;
    flex-direction: column;
    width: fit-content;
    margin: auto;
    background-color: rgb(231, 231, 231);
    padding: 10px;
    border-radius: 10px;

    input{
      margin-bottom: 10px;
    }

    button{
      margin-top: 20px;
      &:hover{
        background-color: rgb(48, 116, 50);
      }
    }
  }

</style>