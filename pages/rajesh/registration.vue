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

    custFieldInfo.firstname = {
      component: 'ElInputText',
      type: 'String',
      attributes: {
        id: 'first-name',
        name: 'Student Name',
        placeholder: 'First Name'
      }
    }
    custFieldInfo.middlename = {
      component: 'ElInputText',
      type: 'String',
      attributes: {
        id: 'middle-name',
        name: 'Student Name',
        placeholder: 'Middle Name'
      }
    }
    custFieldInfo.lastname = {
      component: 'ElInputText',
      type: 'String',
      attributes: {
        id: 'last-name',
        name: 'Student Name',
        placeholder: 'Last Name'
      }
    }
    custFieldInfo.address1 = {
      component: 'ElInputText',
      type: 'String',
      attributes: {
        id: 'customer-address1',
        name: 'address line 1',
        placeholder: 'Enter Address1'
      }
    }
    custFieldInfo.address2 = {
      component: 'ElInputText',
      type: 'String',
      attributes: {
        id: 'customer-address2',
        name: 'address line 2',
        placeholder: 'Enter Address2'
      }
    }
    custFieldInfo.city = {
      component: 'ElInputText',
      type: 'String',
      attributes: {
        id: 'student-address3',
        name: 'City',
        placeholder: 'Enter city'
      }
    }
    custFieldInfo.pincode = {
      component: 'ElInputText',
      type: 'String',
      attributes: {
        id: 'customer-pincode',
        name: 'Pincode',
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
