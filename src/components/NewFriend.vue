<!-- eslint-disable vue/valid-template-root -->
<template>
      <form action="" @submit.prevent="save">
    <div>
      <label for="">Name</label>
      <input type="text" v-model="enteredName" />
    </div>
    <div>
      <label for="">Phone</label>
      <input type="tel" v-model="enteredPhone" />
    </div>
    <div>
      <label for="">Email</label>
      <input type="email" v-model="enteredMail" />
    </div>
    <div>
      <button>Add Contact</button>
    </div>
  </form>
</template>

<script>

export default {
    data () {
        return {
            enteredName : "",
            enteredPhone: "",
            enteredMail: "",
        }
    },
    methods: {
        reset(){
            this.enteredName = "",
            this.enteredPhone = "",
            this.enteredMail = ""
        },
        save(){
            this.$emit(
                'add-contact',
                this.enteredName,
                this.enteredPhone,
                this.enteredMail,
                this.reset()
            )
        }
    },
    emits:['reset-form']
}

</script>
