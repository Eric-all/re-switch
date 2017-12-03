<template>
 <div>
   <v-switch></v-switch>
 </div>
</template>

<script>
import '../../lib/switch.css'
import Switch from '../../lib/switch'
export default {
  name: 'App',
  components: {
    VSwitch: Switch
  }
}
</script>
