<template>

  <div>
    <h1>{{ $tr('header') }}</h1>
    <p v-if="isSuperuser"><a href="/management/device#/content">{{ $tr('adminLink') }}</a></p>
    <p v-else>{{ $tr('notAdmin') }}</p>
  </div>

</template>


<script>

  import { isSuperuser } from 'kolibri.coreVue.vuex.getters';

  export default {
    name: 'learnContentUnavailable',
    $trs: {
      header: 'No content channels available',
      adminLink: 'Download content from the Management page',
      notAdmin:
        'You need to sign in as the Device Owner to manage content. (This is the account originally created in the Setup Wizard.)',
    },
    vuex: {
      getters: {
        isSuperuser,
      },
    },
  };

</script>


<style lang="stylus" scoped>

  h1
    margin-top: 42px // height of toolbar

</style>
