<script>
import KeyButton from "./components/KeyButton.vue";
import Operatorbutton from "./components/Operatorbutton.vue";

export default {
  name: "App",
  data() {
    return {
      operators: ["+", "-", "*", "/"],
      chiffres: [1, 2, 3, 4, 5, 6, 7, 8, 9, 0, "."],
      current_value: 0,
      prev_value: 0,
      output_value: 0,
      result_value: 0,
      current_operator: "",
      ans: null,
    };
  },
  methods: {
    updateCurrentvalue(key) {
      if (this.current_value === 0) {
        this.current_value += key;
        this.current_value = this.current_value.toString();
      } else {
        this.current_value += key.toString();
      }

      this.output_value = this.current_value;
    },

    useOperator(operator) {
          if(this.ans!=null){
            this.prev_value=this.ans
            this.calcul(this.current_operator);
            this.current_operator=operator
            this.current_value=0
            this.ans=this.output_value
          }
          else{
            this.current_value = parseFloat(this.current_value);
            this.calcul(operator);
            this.prev_value = this.current_value;
            this.output_value = this.prev_value;

            this.current_operator =operator;
            this.current_value = 0
            this.ans=this.output_value
          }


    },
    display_result() {
      this.calcul(this.current_operator);
      this.ans=this.output_value
      this.current_operator = "";
    },

    calcul(operator) {
      switch (operator) {
        case "+":
          this.output_value = parseFloat(this.prev_value) + parseFloat(this.current_value);
          break;
        case "*":
          this.output_value = parseFloat(this.prev_value) * parseFloat(this.current_value);
          break;
        case "-":
          this.output_value = parseFloat(this.prev_value) - parseFloat(this.current_value);
          break;
        case "/":
          
          this.output_value = parseFloat(this.prev_value) / parseFloat(this.current_value);
          break;

        default:
          break;
      }
    },

    ac_function() {
      (this.current_value = 0), (this.prev_value = 0), (this.output_value = 0),(this.ans= null);
    },
    bs_function() {
      if (parseFloat(this.current_value) > 0) {
        this.current_value = this.current_value.toString();
        let new_current = this.current_value;
        new_current = new_current.slice(0, -1);
        this.current_value = new_current;
        this.output_value = this.current_value;
      }
    },
  },
  components: {
    KeyButton,
    Operatorbutton,
  },
};
</script>

<template>
  <div class="calculator">
    <div class="calculator__output">{{ output_value }}</div>
    <div class="calculator__keys">
      <Operatorbutton
        v-for="operator in operators"
        :keys="operator"
        :operator="operator"
        @click="useOperator(operator)"
      ></Operatorbutton>

      <KeyButton
        v-for="chiffre in chiffres"
        :number="chiffre"
        :key="chiffre"
        @click="updateCurrentvalue(chiffre)"
      ></KeyButton>
      <button class="calculator__key calculator__key--bs" @click="bs_function">
        {{ `<=` }}
      </button>
      <button class="calculator__key calculator__key--ac" @click="ac_function">
        AC
      </button>

      <button
        class="calculator__key calculator__key--enter"
        @click="display_result"
      >
        =
      </button>
    </div>
  </div>
</template>

<style lang="scss" scoped></style>
