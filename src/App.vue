<script setup></script>

<template>
  <header>
    <div class="navbar bg-white rounded-3xl shadow-xl">
      <div class="flex-none">
        <button class="btn btn-circle btn-ghost">
          <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" class="inline-block w-5 h-5 stroke-current"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 6h16M4 12h16M4 18h16"></path></svg>
        </button>
      </div>
      <div class="flex-1">
        <RouterLink to="/" class="btn btn-ghost normal-case text-xl">🚀即刻发射台</RouterLink>
      </div>
    </div>
    <nav></nav>
  </header>

  <RouterView />
</template>
