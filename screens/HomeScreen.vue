<template>
  <view class="container">
    <text>{{ text }}</text>
    <switch
            :on-value-change = "handleChange"
            :value = "value"/>
    <button
      :on-press="goMessages"
      title="Проверка связи"
    />
    <text 
      v-if="isOpen">
    Good morning</text>
  </view>
</template>
<script>
  export default {
    data: function() {
      return {
        text: 'Home',
        value: false,
        isOpen: false
      }
    },
    props: {
      navigation: {
        type: Object
      }
    },
    methods: {
      goMessages: function() {
        this.navigation.navigate("Messages")
      },
      handleChange: function(val) {
        this.value = val;
        this.isOpen = val;
      }
    }
  }
</script>
<style>
.container {
  background-color: white;
  align-items: center;
  justify-content: center;
  flex: 1;
}
.text-color-primary {
  color: blue;
}
</style>
