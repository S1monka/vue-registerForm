<template>
  <div id="passport-form">
    <div class="form-group">
      <label for="document">Тип документа*</label>
      <select name="Тип документа" v-model="document" id="document" required>
        <option value="Паспорт">Паспорт</option>
        <option value="Свидетельство о рождении"
          >Свидетельство о рождении</option
        >
        <option value="Водительское удостоверение"
          >Водительское удостоверение</option
        >
      </select>
    </div>
    <div class="passport">
      <div class="form-group">
        <label for="series">Серия</label>
        <input
          type="text"
          id="series"
          v-model.number.lazy="series"
          placeholder="Серия"
          maxlength="4"
          pattern="[0-9]{4}"
        />
      </div>
      <div class="form-group">
        <label for="number">Номер</label>
        <input
          type="text"
          id="number"
          v-model.number.lazy="number"
          placeholder="Номер"
          pattern="[0-9]{6}"
          maxlength="6"
        />
      </div>
    </div>
    <div class="form-group">
      <label for="place">Кем выдан</label>
      <textarea
        name="Кем выдан"
        v-model="place"
        id="place"
        cols="30"
        rows="5"
      ></textarea>
    </div>
    <div class="form-group">
      <label for="time">Дата выдачи*</label>
      <input
        type="date"
        id="time"
        v-model="time"
        placeholder="Дата выдачи"
        required
      />
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      document: "Паспорт",
      series: "",
      number: "",
      place: "",
      time: "",
    };
  },
};
</script>

<style lang="scss" scoped>
#passport-form {
  display: flex;
  flex-flow: column wrap;
  justify-content: space-between;

  margin-top: 1rem;

  .passport {
    display: flex;
    flex-flow: row wrap;
    justify-content: space-between;

    .form-group {
      width: 49%;
    }
  }
}
</style>
