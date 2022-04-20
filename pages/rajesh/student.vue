<template>
  <div>
    Hello Store {{ customers }}
    <FormRenderer :formSpec="custFieldInfo" :storeName="storeName" />
  </div>
</template>

<script>
export default {
  computed: {
    customers () {
      return this.$store.state.customer.list
    }
  },
  data () {
    return {
      customer: {},
      storeName: 'customer'
    }
  },
  methods: {
    atClicked (value) {
      this.customer = value
    }
  },
  created () {
    const custFieldInfo = {}

    custFieldInfo.name = {
      component: 'ElInputText',
      type: 'text',
      attributes: {
        id: 'customer-name',
        name: 'Student Name',
        placeholder: 'Enter Your Name'
      }
    }
    custFieldInfo.rollno = {
      component: 'ElInputText',
      type: 'String',
      attributes: {
        id: 'roll-no',
        name: 'Roll number',
        placeholder: 'Enter Your Roll'
      }
    }
    custFieldInfo.Nationality = {
      component: 'ElInputText',
      type: 'String',
      attributes: {
        id: 'nationality',
        name: 'Nationality',
        placeholder: 'Citizenship '
      }
    }
    custFieldInfo.Birthplace = {
      component: 'ElInputText',
      type: 'String',
      attributes: {
        id: 'birthplace',
        name: 'Birth Place',
        placeholder: 'Citizenship '
      }
    }
    custFieldInfo.Height = {
      component: 'ElInputText',
      type: 'String',
      attributes: {
        id: 'height',
        name: 'Height',
        placeholder: 'hight in cm '
      }
    }
    custFieldInfo.email = {
      component: 'ElInputText',
      type: 'String',
      attributes: {
        id: 'email',
        name: 'E-mail',
        placeholder: 'Enter Your Name'
      }
    }
    custFieldInfo.saveButton = {
      component: 'ElButton',
      attributes: {
        id: 'saveForm',
        value: 'save',
        type: 'submit'
      }
    }
    this.custFieldInfo = custFieldInfo
  }
}
</script>
