<template>
  <div id="address-form">
    <div class="form-group">
      <label for="index">Индекс</label>
      <input
        type="text"
        v-model="index"
        id="index"
        placeholder="Индекс"
        pattern="^[0-9]+$"
        maxlength="6"
      />
    </div>
    <div class="form-group">
      <label for="country">Страна</label>
      <input type="text" id="country" v-model="country" placeholder="Страна" />
    </div>
    <div class="form-group">
      <label for="region">Область</label>
      <input type="text" id="region" v-model="region" placeholder="Область" />
    </div>
    <div class="form-group">
      <label for="city">Город*</label>
      <input type="text" id="city" v-model="city" placeholder="Город" />
    </div>
    <div class="form-group">
      <label for="street">Улица</label>
      <input type="text" id="street" v-model="street" placeholder="Улица" />
    </div>
    <div class="form-group">
      <label for="building">Дом</label>
      <input type="text" id="building" v-model="building" placeholder="Дом" />
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      index: "",
      country: "",
      region: "",
      city: "",
      street: "",
      building: "",
    };
  },
};
</script>

<style lang="scss" scoped>
#address-form {
  display: flex;
  flex-flow: row wrap;

  justify-content: space-between;

  .form-group {
    min-width: 49%;
  }
}

@media screen and (max-width: 576px) {
  #address-form {
    .form-group {
      width: 100%;
    }
  }
}
</style>
