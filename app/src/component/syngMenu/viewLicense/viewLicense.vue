<template>
  <i-col span="4" class='main-column'>
    <Menu theme="light" width='100%' active-key='1'>
      <Menu-item key='1' v-on:click='loadView("syngLicense")'>
        <center>
          <h3>Syng License</h3>
        </center>
      </Menu-item>
      <Menu-item key='2' v-on:click='loadView("cccedictLicense")'>
        <center>
          <h3>CC-CEDICT License</h3>
        </center>
      </Menu-item>
      <Menu-item key='3' v-on:click='loadView("nodecccedictLicense")'>
        <center>
          <h3>Node-CC-CEDICT License</h3>
        </center>
      </Menu-item>
      <Menu-item key='4' v-on:click='loadView("jundaLicense")'>
          <center>
              <h3>Jun Da License</h3>
          </center>
      </Menu-item>
    </Menu>
  </i-col>
  <i-col span="17" class='main-column'>
    <div id="license-content">
        <br>
        <component :is='currentView'></component>
    </div>
  </i-col>
</template>

<style>
.ivu-col-span-4 {
  background-color: #fff;
  border-right: 2px solid #d7dde4;
}
.ivu-col-span-4:after {
  background: #d7dde4;
  position: absolute;
  bottom: 0;
  display: block;
}
#license-content {
  height: 100vh;
  width: 100vh;
  overflow-y: scroll;
}
</style>

<script>
  var SyngLicense = require('./syngLicense.vue');
  var CCCEDICTLicense = require('./cccedictLicense.vue');
  var NodeCCCEDICTLicense = require('./nodeCCCEDICTLicense.vue');
  var JundaLicense = require('./jundaLicense.vue');

  module.exports = {
    data: function() {
      return {
        currentView: 'syngLicense'
      }
    },
    components: {
      'syngLicense': SyngLicense,
      'cccedictLicense': CCCEDICTLicense,
      'nodecccedictLicense': NodeCCCEDICTLicense,
      'jundaLicense': JundaLicense
    },
    methods: {
      loadView: function(viewName) {
        this.currentView = viewName;
      }
    }
  };
</script>
