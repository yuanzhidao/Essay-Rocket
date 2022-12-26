<script setup>
import { ref } from 'vue';
import axios from 'axios';

const essaytext = ref('');
const buttonText1 = ref('发送');

const submitText = ref(() => {
  var btn = document.querySelector('.btn1');
  btn.classList.add('loading');
  axios
    .get('https://essay-api.o0.work/send-essay?key=iYuanKeyTemporary', {
      params: {
        text: essaytext.value,
        from: '即刻发射台',
      },
    })
    .then(function (response) {
      console.log(response);
      if (response.status == 200) {
        btn.classList.remove('loading');
        btn.classList.add('btn-success');
        buttonText1.value = '发送成功';
      }
    })
    .catch(function (err) {
      console.log(err);
      btn.classList.remove('loading');
      btn.classList.add('btn-error');
      buttonText1.value = '发送失败';
    });
});
</script>

<template>
  <main>
    <div class="p-4 rounded-3xl shadow-xl mt-4 bg-white flex justify-center items-center flex-col">
      <div class="bg-clip-text text-transparent bg-gradient-to-r from-green-300 via-blue-500 to-purple-600 font-bold text-3xl mb-4">文字版即刻发送</div>
      <input type="text" placeholder="占位符qwq" class="input input-bordered input-primary w-full h-[12rem] mb-4" v-model="essaytext" />
      <button class="btn btn-primary w-full btn1" @click="submitText">{{ buttonText1 }}</button>
    </div>
  </main>
</template>
