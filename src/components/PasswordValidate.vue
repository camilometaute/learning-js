<template>
  <div class="password-validate">
    Password validate
    <input type="password" placeholder="Write you password" name="" value="" v-model="password">

    <p>
      <span :class="has_min_lenght ? 'has_required' : ''">Atleast 8 Characters</span> -
      <span :class="has_num ? 'has_required' : ''">One number</span> -
      <span :class="has_low ? 'has_required' : ''">One Lowercase</span> -
      <span :class="has_upper ? 'has_required' : ''">One Uppercase</span> -
      <span :class="has_special ? 'has_required' : ''">One Special</span>
    </p>
  </div>
</template>

<script>
export default {
  name: 'PasswordValidate',
  data() {
    return {
      password: '',
      has_min_lenght: false,
      has_num: false,
      has_low: false,
      has_upper: false,
      has_special: false,
    }
  },
  watch: {
    password() {
      this.has_min_lenght = (this.password.length > 8);
      this.has_num = /\d/.test(this.password);
      this.has_low = /[a-z]/.test(this.password);
      this.has_upper = /[A-Z]/.test(this.password);
      this.has_special = /[!@#/&*%$]/.test(this.password);
    }
  }
  }
</script>
