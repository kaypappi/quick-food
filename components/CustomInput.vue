<template>
  <div class="">
    <ValidationProvider
      :bail="bail"
      :name="$attrs.name"
      :rules="rules"
      :vid="vid"
      mode="lazy"
      v-slot="{ valid, errors }"
      :immediate="immediate"
    >
      <div
        :class="[
          'input-holder form-floating d-flex align-items-center position-relative',{'bordered':bordered}
        ]"
      >
        <div
          class="position-absolute left-icon"
        >
        <slot name="left-slot"></slot>
        </div>
        <input
          :class="[
            'form-control form__input',
            inputClass,
            { errors: errors[0] ? true : valid ? true : null },
          ]"
          v-model="innerValue"
          v-bind="$attrs"
          :type="showPassword ? 'text' : type"
          :name="name"
          :id="name"
          :disabled="disabled"
          :placeholder="placeholder"
        />
        <!-- <label class="" :for="name">
          <span class="first__word--highlight">{{ thickLabel }}</span
          ><span>{{ label }}</span></label
        > -->
        <div  class="position-absolute right-icon">
          <slot name="right-slot"></slot>
        </div>
      </div>

      <span
        class="form__error mb-2"
        v-if="errors[0] ? true : valid ? true : null"
        >{{ errors[0] }}</span
      >
    </ValidationProvider>
  </div>
</template>

<script>
import { ValidationProvider } from "vee-validate";
export default {
  components: {
    ValidationProvider,
  },
  props: {
    vid: {
      type: String,
    },
    rules: {
      type: [Object, String],
      default: "",
    },
    // must be included in props
    value: {
      type: null,
    },
    bordered: {
      type: Boolean,
      default: false,
    },
    bail: { type: Boolean, default: true },
    placeholder: String,
    disabled: { type: Boolean, default: false },
    type: {
      type: String,
      default: "text",
    },
    name: String,
    label: String,
    thickLabel: String,
    inputClass: String,
    immediate: {
      type: Boolean,
      default: false,
    },
    right_icon: {
      type: String,
      default: "",
    },
    left_icon: {
      type: String,
      default: "",
    },
    right_icon_action: {
      type: Function,
      default: () => {},
    },
    left_icon_action: {
      type: Function,
      default: () => {},
    },
    showPassword: {
      type: Boolean,
      default: false,
    },
  },
  data: () => ({
    innerValue: "",
  }),
  watch: {
    // Handles internal model changes.
    innerValue(newVal) {
      this.$emit("input", newVal);
    },
    // Handles external model changes.
    value(newVal) {
      this.innerValue = newVal;
    },
  },
  created() {
    if (this.value) {
      this.innerValue = this.value;
    }
  },
};
</script>

<style scoped>
.right-icon {
  right: 20px;
}
.left-icon {
  left: 20px;
}

</style>
