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

    custFieldInfo.name1 = {
      component: 'ElInputText',
      type: 'String',
      attributes: {
        id: 'customer-name',
        name: 'Student Name',
        placeholder: 'First Name'
      }
    }
    custFieldInfo.name2 = {
      component: 'ElInputText',
      type: 'String',
      attributes: {
        id: 'student-name',
        name: 'Student Name',
        placeholder: 'Middle Name'
      }
    }
    custFieldInfo.name3 = {
      component: 'ElInputText',
      type: 'String',
      attributes: {
        id: 'customer-name',
        name: 'Student Name',
        placeholder: 'Last Name'
      }
    }
    custFieldInfo.address1 = {
      component: 'ElInputText',
      type: 'String',
      attributes: {
        id: 'customer-address1',
        name: 'address1',
        placeholder: 'Enter Address1'
      }
    }
    custFieldInfo.address2 = {
      component: 'ElInputText',
      type: 'String',
      attributes: {
        id: 'customer-address2',
        name: 'address1',
        placeholder: 'Enter Address2'
      }
    }
    custFieldInfo.address3 = {
      component: 'ElInputText',
      type: 'String',
      attributes: {
        id: 'customer-address3',
        name: 'address1',
        placeholder: 'Enter Address3'
      }
    }
    custFieldInfo.pincode = {
      component: 'ElInputText',
      type: 'String',
      attributes: {
        id: 'customer-pincode',
        name: 'address1',
        placeholder: 'Enter Pincode'
      }
    }
    custFieldInfo.email = {
      component: 'ElInputText',
      type: 'String',
      attributes: {
        id: 'email',
        name: 'Student E-mail',
        placeholder: 'Your MailId'
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
    custFieldInfo.work = {
      component: 'ElDropdown',
      type: 'Array',
      arrayValues: ['Linux', 'Azure', 'RedHat', 'Hadoop'],
      attributes: {
        name: 'work',
        labelValue: 'Course'
      }
    }
    custFieldInfo.mobNo = {
      component: 'ElInputText',
      type: 'String',
      attributes: {
        id: 'customer-mobNo',
        name: 'mobNo',
        placeholder: 'Enter Your Mobile Number'
      }
    }
    custFieldInfo.saveButton = {
      component: 'ElButton',
      attributes: {
        id: 'saveForm',
        value: 'submit',
        type: 'submit'
      }
    }
    this.custFieldInfo = custFieldInfo
  }
}
</script>
