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
      type: 'String',
      attributes: {
        id: 'customer-name',
        name: 'Name',
        placeholder: 'Enter Your Name',
        disabled: 'true'
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
    custFieldInfo.gender = {
      component: 'ElRadioBtn',
      type: 'Array',
      arrayValues: ['Male', 'Female', 'Others'],
      attributes: {
        name: 'gender',
        id: 'gender'
      }
    }
    custFieldInfo.message = {
      component: 'ElInputTextArea',
      type: 'text',
      attributes: {
        id: 'message',
        name: 'Message',
        labelValue: 'Enter Job Description',
        placeholder: 'Enter Your Job Details'
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
