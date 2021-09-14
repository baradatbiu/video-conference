<template>
  <div class="auth">
    <div class="auth__wrapper">
      <form @submit.prevent="loginUser" class="auth__form">
        <label class="auth__label">
          <input
            v-model="roomId"
            type="text"
            class="auth__input"
            placeholder="Room ID"
            autofocus
          />
        </label>
        <label class="auth__label">
          <input
            v-model="userName"
            type="text"
            class="auth__input"
            placeholder="Username"
          />
        </label>
        <button class="auth__submit">Join</button>
      </form>
    </div>
  </div>
</template>

<script lang="ts">
import { Component, Vue } from "vue-property-decorator";

@Component
export default class LoginForm extends Vue {
  roomId = "";
  userName = "";

  loginUser(): void {
    console.log(this.roomId, this.userName);

    this.roomId = "";
    this.userName = "";
  }
}
</script>

<style scoped lang="stylus">
.auth
  height 100%
  display flex
  align-items center
  justify-content center

.auth__wrapper
  width 100%
  max-width 360px

.auth__form
  margin 10px
  display flex
  flex-direction column

.auth__input
  width 100%
  padding 13px
  font-size 21px
  border-radius 8px
  background-color #F2F2F2
  outline none
  border 1px solid #d0d0d0

  &:focus
    border-color #757575


.auth__label
  margin-bottom 27px

.auth__submit
  font-size 18px
  color #fff
  width 100%
  padding 15px
  background-color #757de8
  border-radius 8px
  border 1px solid #757de8
  cursor pointer
  transition background-color 0.3s

  &:focus
    border-color #000

  &:hover
    background-color #575fd2
</style>
