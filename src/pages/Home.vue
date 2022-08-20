<!-- eslint-disable vue/multi-word-component-names -->
<template>
  <div>
    <section class="hero">
      <div class="hero-body">
        <p class="title">Find your dream job today</p>
        <p class="subtitle">Apply for vacancies below</p>
      </div>
    </section>
    <NewVacancy v-if="isAdmin" @save="handleSubmit" />
    <Vacancy
      v-for="vacancy in vacancies"
      :key="vacancy.id"
      :isAdmin="isAdmin"
      :vacancy="vacancy"
      @delete="handleDelete"
    />
  </div>
</template>

<script>
import NewVacancy from "../components/NewVacancy.vue";
import Vacancy from "../components/Vacancy.vue";
import { vacancies } from "../../data.js";

export default {
  components: { NewVacancy, Vacancy },
  data() {
    return {
      vacancies: vacancies,
      isAdmin: true
    };

  },
  methods: {
    handleSubmit(formData) {
      console.log("form data", formData);
      this.vacancies.unshift(formData);
    },
    handleDelete(vacancyId) {
        this.vacancies = this.vacancies.filter( vacancy => vacancy.id !== vacancyId)
    }
  },
};
</script>

<style></style>
