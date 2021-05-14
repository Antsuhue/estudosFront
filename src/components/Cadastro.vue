<template>
  <div>
    <b-form @submit="onSubmit" @reset="onReset" v-if="show">
      <b-form-group
        id="input-group-1"
        label="Email address:"
        label-for="input-1"
        description="We'll never share your email with anyone else."
      >
        <b-form-input
          id="input-1"
          v-model="form.email"
          type="email"
          placeholder="Enter email"
          required
        ></b-form-input>
      </b-form-group>

      <b-form-group id="input-group-2" label="CPF/CNPJ:" label-for="input-2">
        <b-form-input
          id="input-2"
          v-model="form.cpfcnpj"
          placeholder="Enter CPF or CNPJ">
          </b-form-input>
      </b-form-group>

      <b-form-group id="input-group-3" label="Your Name:" label-for="input-3">
        <b-form-input
          id="input-3"
          v-model="form.name"
          placeholder="Enter name"
        ></b-form-input>
      </b-form-group>

      <b-form-group id="input-group-4" label="Password:" label-for="input-4">
        <b-form-input
          id="input-4"
          v-model="form.password"
          type="password"
          placeholder="Password"
        ></b-form-input>
      </b-form-group>

      <b-form-group id="input-group-5" label="Re-Password:" label-for="input-5">
        <b-form-input
          id="input-5"
          v-model="form.repassword"
          :state="validationPassword"
          type="password"
          placeholder="Enter your passoword again"
        ></b-form-input>
        <b-form-invalid-feedback :state="validation">
          The two passwords not the same
        </b-form-invalid-feedback>
      </b-form-group>

      <b-form-group id="input-group-6" label="Address:" label-for="input-6">
        <b-form-input
          id="input-6"
          v-model="form.adress"
          placeholder="Enter adress"
        ></b-form-input>
      </b-form-group>

      <b-form-group id="input-group-4" v-slot="{ ariaDescribedby }">
        <b-form-checkbox-group
          v-model="form.checked"
          id="checkboxes-4"
          :aria-describedby="ariaDescribedby"
        >
          <b-form-checkbox value="Aceito">Aceito os termos de uso</b-form-checkbox>
        </b-form-checkbox-group>
      </b-form-group>

      <b-button type="submit" variant="primary">Submit</b-button>
      <b-button type="reset" variant="danger">Reset</b-button>
    </b-form>
    <b-card class="mt-3" header="Form Data Result">
      <pre class="m-0">{{ form }}</pre>
    </b-card>
  </div>
</template>

<script>
  export default {
    data() {
      return {
        form: {
          email: '',
          cpfcnpj: '',
          name: '',
          password: '',
          repassword: '',
          adress: '',
          checked: []
        },
        show: true
      }
    },
    computed: {
      validationPassword(){
        return this.form.password == this.form.repassword
      }
    },
    methods: {
      onSubmit(event) {
        event.preventDefault()
        alert(JSON.stringify(this.form))
      },
      onReset(event) {
        event.preventDefault()
        // Reset our form values
        this.form.email = ''
        this.form.name = ''
        this.form.cpfcnpj = ''
        this.form.password = ''
        this.form.repassword = ''
        this.form.adress = ''
        this.form.checked = []
        // Trick to reset/clear native browser form validation state
        this.show = false
        this.$nextTick(() => {
          this.show = true
        })
      }
    }
  }
</script>

<style scoped>

label{
  margin-bottom: 1%;
}

button{
  margin: 10px;
}

</style>

 