<template>
  <div>
    <input
      @input="handleInput"
      @blur="deactivationFocus"
      @focus="actiovationFocus"
      :class="['input', { input_error: !isFocus && !isValid }]"
      :id="id"
      :type="type"
      :placeholder="placeholder"
      v-model="content"
    />
    <p v-if="!isFocus && !isValid" class="input__text-error">{{ textError }}</p>
  </div>
</template>

<script>
export default {
  props: {
    id: String,
    isValid: Boolean,
    textError: String,
    placeholder: String,
    type: String,
    value: {
      type: String,
      default: '',
    },
  },
  data() {
    return {
      content: this.value,
      isFocus: false,
    };
  },
  watch: {
    value(newVal, oldVal) {
      if (newVal !== this.content) {
        this.content = newVal;
      }
    },
  },
  methods: {
    handleInput() {
      this.$emit('input', this.content);
    },
    actiovationFocus() {
      this.isFocus = true;
    },
    deactivationFocus() {
      this.$emit('blur');
      this.isFocus = false;
    },
  },
};
</script>

<style scoped>
.input__text-error {
  font-size: 16px;
  line-height: 24px;
  position: absolute;
  color: #cc0000;
}
.input {
  outline: none;
  width: 100%;
  padding: 10px 0;
  border: none;
  font-size: 18px;
  line-height: 24px;
  font-family: inherit;
  box-sizing: border-box;
  border-bottom: 1px solid #e7e7e7;
  color: #000;
}
.input:focus {
  padding-bottom: 9px;
  border-bottom: 2px solid #613a93;
}
.input_error:focus,
.input_error {
  border-bottom: 2px solid #cc0000;
}
@media screen and (max-width: 1280px) {
  .input__text-error,
  .input {
    font-size: 16px;
    line-height: 22px;
  }
}
@media screen and (max-width: 768px) {
  .input {
    font-size: 15px;
    line-height: 19px;
  }
}
@media screen and (max-width: 650px) {
  .input__text-error,
  .input {
    font-size: 13px;
    line-height: 16px;
  }
}
</style>
