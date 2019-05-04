<template>
  <div>
    <header>
      <h1 class="title">イトムラ ヨウスケ</h1>
    </header>
    <main class="container">
      <nuxt/>
    </main>
  </div>
</template>

<style>
html {
  font-family: "Source Sans Pro", 游ゴシック体, 'Yu Gothic', YuGothic, 'ヒラギノ角ゴシック Pro', 'Hiragino Kaku Gothic Pro', メイリオ, Meiryo, sans-serif;
  font-size: 16px;
}
h1, h2, h3 {
  font-weight: normal;
}
.title {
  color: #35495e;
  margin: 100px 0 30px;
  text-align: center;
}
.container {
  width: 80%;
  margin: 0 auto;
  transition: all .5s cubic-bezier(.55,0,.1,1);
}

.page-enter-active, .page-leave-active {
  transition: opacity .5s
}
.page-enter, .page-leave-active {
  opacity: 0
}

.bounce-enter-active {
  animation: bounce-in .8s;
}
.bounce-leave-active {
  animation: bounce-out .5s;
}
@keyframes bounce-in {
  0% { transform: scale(0) }
  50% { transform: scale(1.5) }
  100% { transform: scale(1) }
}
@keyframes bounce-out {
  0% { transform: scale(1) }
  50% { transform: scale(1.5) }
  100% { transform: scale(0) }
}

.slide-left-enter,
.slide-right-leave-active {
  opacity: 0;
  transform: translate(30px, 0);
}
.slide-left-leave-active,
.slide-right-enter {
  opacity: 0;
  transform: translate(-30px, 0);
}
</style>