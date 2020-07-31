<template>
  <div id="user-form">
    <div class="form-group">
      <label for="lastName">Фамилия*</label>
      <input
        type="text"
        v-model.trim="name.lastName"
        id="lastName"
        placeholder="Фамилия"
        required
        pattern="^[А-Яа-яЁё]+$"
      />
    </div>
    <div class="form-group">
      <label for="firstName">Имя*</label>
      <input
        type="text"
        id="firstName"
        v-model.trim="name.firstName"
        placeholder="Имя"
        required
        pattern="^[А-Яа-яЁё]+$"
      />
    </div>
    <div class="form-group">
      <label for="middleName">Отчество</label>
      <input
        type="text"
        id="middleName"
        v-model.trim="name.middleName"
        placeholder="Отчество"
        pattern="^[А-Яа-яЁё]+$"
      />
    </div>
    <div class="form-group">
      <label for="birthday">День рождения*</label>
      <input type="date" id="birthday" v-model="birthday" required />
    </div>
    <div class="form-group">
      <label for="phone">Номер телефона*</label>
      <input
        type="tel "
        placeholder="7 XXX XXX-XX-XX"
        pattern="7\s[0-9]{3}\s[0-9]{3}-[0-9]{2}-[0-9]{2}"
        id="phone"
        maxlength="15"
        v-model="phoneNumber"
        required
      />
    </div>
    <div class="form-group  ">
      <label>Пол</label>
      <div class="gender">
        <input type="radio" v-model="gender" id="male" value="Мужской" />
        <label for="male">Мужской</label>
      </div>
      <div class="gender">
        <input type="radio" value="Женский" v-model="gender" id="female" />
        <label for="female">Женский</label>
      </div>
    </div>
    <div class="form-group">
      <label for="group">Группа клиентов*</label>
      <select
        name="group"
        id="group"
        size="3"
        v-model="clientGroup"
        multiple
        required
      >
        <option value="vip">VIP</option>
        <option value="troublesome">Проблемные</option>
        <option value="oms">ОМС</option>
      </select>
    </div>
    <div class="form-group">
      <label for="doctor">Лечащий врач</label>
      <select name="doctor" id="doctor" v-model="doctor">
        <option value="Иванов">Иванов</option>
        <option value="Захаров">Захаров</option>
        <option value="Чернышева">Чернышева</option>
      </select>
    </div>
    <div class="form-group sms">
      <label for="sms">Не отправлять СМС</label>
      <input type="checkbox" id="sms" v-model="notPushSms" />
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      name: {
        firstName: "",
        middleName: "",
        lastName: "",
      },
      birthday: "",
      phoneNumber: "",
      gender: "Мужской",
      clientGroup: [],
      doctor: "Иванов",
      notPushSms: false,
    };
  },
};
</script>

<style lang="scss">
#user-form {
  display: flex;
  flex-flow: column wrap;

  margin-top: 2rem;

  .sms {
    label {
      margin-bottom: 0;
    }
    flex-flow: row nowrap;
    align-items: center;
  }
}
</style>
