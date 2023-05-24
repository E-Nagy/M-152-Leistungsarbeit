<script setup>
import {onMounted, ref, watch} from "vue";

const data = ref([
  {
    'id': 1,
    'name': 'Mathe',
    'grades': [5.5, 6, 5.25]
  },
  {
    'id': 2,
    'name': 'Französisch',
    'grades': [2.5, 3, 4.25, 5]
  },
  {
    'id': 3,
    'name': 'Allgemeinbildung',
    'grades': [4.75, 5]
  },
  {
    'id': 4,
    'name': 'Deutsch',
    'grades': [5.5]
  },
])

function resetGrades() {
  data.value = [
    {
      'id': 1,
      'name': 'Mathe',
      'grades': [5.5, 6, 5.25]
    },
    {
      'id': 2,
      'name': 'Französisch',
      'grades': [2.5, 3, 4.25, 5]
    },
    {
      'id': 3,
      'name': 'Allgemeinbildung',
      'grades': [4.75, 5]
    },
    {
      'id': 4,
      'name': 'Deutsch',
      'grades': [5.5]
    },
  ]
}

function saveToLocalStorage() {
  localStorage.setItem('data', JSON.stringify(data.value))
}
onMounted(() => {
  const dataFromLocalStorage = localStorage.getItem('data')
  if (dataFromLocalStorage) {
    data.value = JSON.parse(dataFromLocalStorage)
  }
})
watch(data, saveToLocalStorage, {deep: true})

function average(grades) {
  return roundToPoint5(grades.reduce((a, b) => a + b, 0) / grades.length)
}

function deleteSubject(id) {
  data.value = data.filter(subject => subject.id !== id)
}

function roundToPoint5(number) {
  return Math.round(number * 2) / 2
}

const maxId = ref(4)

function addGrade(id) {
  const grade = prompt('Note eingeben')
  if (grade === null) {
    return
  }

  const subject = data.value.find(subject => subject.id === id)
  subject.grades.push(grade)
}

function removeGradeFromSubject(gradeIndex, subjectIndex) {
  data.value[subjectIndex].grades.splice(gradeIndex, 1)
}

function addSubject() {
  const name = prompt('Fachname eingeben')
  if (name === null) {
    return
  }
  data.value.push({
    id: ++maxId.value,
    name,
    grades: []
  })
}
</script>

<template>
  <main>
    <h1>Notenverwaltung</h1>

    <div class="container header">
      <div class="w-wide">Fach</div>
      <div class="w-wide">Noten</div>
      <div class="w-small">Durchschnitt</div>
      <div class="w-normal">Optionen</div>
    </div>

    <div class="container" v-for="(subject, subjectIndex) in data" :key="subject.id">
      <div class="w-wide">{{ subject.name }}</div>
      <div class="w-wide">
        <span class="grade" v-for="(grade, index) in subject.grades" :key="index" @click="removeGradeFromSubject(index, subjectIndex)">
            {{ grade }}
          </span>
      </div>
      <div class="w-small">
        {{ average(subject.grades) }}
        <template v-if="average(subject.grades) > 4">
          <svg width="10" height="10">
            <circle cx="10" cy="10" r="10" fill="green"/>
          </svg>
        </template>
        <template v-else>
          <svg width="10" height="10">
            <circle cx="10" cy="10" r="10" fill="red"/>
          </svg>
        </template>
      </div>
      <div class="w-normal">
        <button @click="deleteSubject(subject.id)">Löschen</button>
        <button @click="addGrade(subject.id)">Note hinzufügen</button>
      </div>
    </div>

    <div class="buttons">
      <button @click="addSubject">Fach hinzufügen</button>
      <button class="button-red" @click="resetGrades">Alle Noten zurücksetzen</button>
    </div>
  </main>
</template>

<style lang="scss">
.buttons {
  display: flex;
  flex-direction: column;
  align-items: flex-end;

  button {
    margin-top: 0.5rem;
  }
}

.container {
  display: flex;
  width: 100%;
  margin-bottom: 0.5rem;

  &.header {
    font-weight: bold;
  }
  
  .w-small {
    width: 10%;
  }
  .w-wide {
    width: 30%;
  }
  .w-normal {
    width: 20%;
  }
}
table {
  border-collapse: collapse;
  width: 100%;
  // center the table
  margin-left: auto;
  margin-right: auto;

  td {
    border: 1px solid black;
    padding: 0.5rem;

    &.center {
      text-align: center;
    }
  }
}

.grade {
  display: inline-block;
  width: 2rem;
  text-align: center;
  border: 1px solid #a3d06c;
  margin-right: 0.5rem;
  border-radius: 5px;
  cursor: pointer;
  padding-right: 0.75rem;

  &:hover {
    background-color: #a3d06c;
    color: white;
    position: relative;

    &:after {
      content: 'x';
      position: absolute;
      right: 10px;
      top: 0;
    }
  }
}
</style>