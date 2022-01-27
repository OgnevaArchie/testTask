<template>
  <section class="section-profile">
    <div class="user-profile-desctiption">
      <div class="profile-description-item">
        <p>ID</p>
      </div>
      <div class="profile-description-item">
        <p>Имя</p>
      </div>
      <div class="profile-description-item">
        <p>Фамилия</p>
      </div>
      <div class="profile-description-item">
        <p>E-mail</p>
      </div>
      <div class="profile-description-item">
        <p>Пол</p>
      </div>
      <div class="profile-description-item">
        <p>Навык</p>
      </div>
      <div class="profile-description-item">
        <p>Город</p>
      </div>
      <div class="profile-description-item">
        <p>Карта</p>
      </div>
      <div class="profile-description-item">
        <p>Статус</p>
      </div>
    </div>

    <div class="user-profile-information">
      <div class="profile-information-item">
        <p>{{ person?.id }}</p>
      </div>
      <div class="profile-information-item">
        <p>{{ person?.first_name }}</p>
      </div>
      <div class="profile-information-item">
        <p>{{ person?.last_name }}</p>
      </div>
      <div class="profile-information-item">
        <p>{{ person?.email }}</p>
      </div>
      <div class="profile-information-item">
        <p>{{ person?.gender }}</p>
      </div>
      <div class="profile-information-item">
        <p>{{ person?.employment.key_skill }}</p>
      </div>
      <div class="profile-information-item">
        <p>{{ person?.address.city }}</p>
      </div>
      <div class="profile-information-item">
        <p>{{ person?.credit_card.cc_number }}</p>
      </div>
      <div class="profile-information-item">
        <p>{{ person?.subscription.status }}</p>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: "person-component",
  data() {
    return {
      person: null,
    };
  },
  async created() {
    const response = await fetch(
      "https://random-data-api.com/api/users/random_user"
    );
    const data = await response.json();
    this.person = data;
  },
};
</script>

<style>
.user-profile-desctiption {
  display: flex;
  flex-direction: column;
  flex-wrap: nowrap;
  justify-content: start;
  height: 620px;
  min-width: 100px;
  max-width: 150px;
  margin-left: 5%;
  padding-top: 20px;
  padding-bottom: 5px;
  padding-left: 40px;
  background-color: #1b1b1b;
}

.profile-description-item {
  max-width: 300px;
  min-width: 100px;
  height: 50px;
  text-align: center;
  background-color: rgb(245, 245, 245);
  margin-top: 15px;
}

.user-profile-information {
  display: flex;
  flex-direction: column;
  flex-wrap: nowrap;
  background-color: #e0dfdf;
  justify-content: start;
  height: 625px;
  width: 360px;
  margin-left: 0;
  padding-top: 20px;
}

.profile-information-item {
  max-width: 300px;
  min-width: 100px;
  height: 50px;
  text-align: center;
  background-color: #1b1b1b;
  margin-top: 15px;
  color: white;
}

.section-profile {
  display: flex;
  flex-direction: row;
  margin-top: 60px;
  margin-left: auto;
}

body {
  font-family: "Rubik", sans-serif;
  height: auto;
}
</style>