<template>
  <link
    rel="stylesheet"
    href="https://fonts.googleapis.com/css2?family=Material+Symbols+Outlined:opsz,wght,FILL,GRAD@24,400,0,0&icon_names=stethoscopeencrypted"
  />

  <div class="row">
    <!-- brand panel -->
    <div class="col-6 brand-panel" style="height: 100vh">
      <!-- title -->
      <div class="left-item q-px-xl">
        <div class="text-h6">+ MediFlow</div>
      </div>

      <!-- content -->
      <div class="left-item">
        <div class="text-h3 text-bold q-px-xl" style="width: 70%">Care that moves at your pace</div>

        <div class="text-body1 q-px-xl q-pt-lg" style="width: 85%">
          Submit prescription requests, track their status, and hear back from a licensed
          practitioner.. all in one calm, secure place.
        </div>

        <div class="row q-px-xl q-pt-lg">
          <q-chip class="chip q-py-md" text-color="white">
            <span class="material-symbols-outlined q-mr-xs"> encrypted </span> Private & encrypted
          </q-chip>
          <q-chip class="chip q-py-md" text-color="white" icon="schedule"> Fast turnaround </q-chip>
          <q-chip class="chip q-py-md" text-color="white"
            ><span class="material-symbols-outlined q-mr-xs"> stethoscope </span> Licensed
            practitioners</q-chip
          >
        </div>
      </div>

      <!-- footer -->
      <div class="column left-item justify-end">
        <div class="q-px-lg">© 2026 MediFlow Health · Not for medical emergencies</div>
      </div>
    </div>

    <!-- form panel -->
    <div class="col-6 column flex-center" style="height: 100vh; background-color: #edede8">
      <div class="contents" style="width: 400px; margin-left: -20%">
        <div class="text-h6 text-black">Welcome back</div>
        <div class="text-body2 text-grey-8 q-mt-sm">Sign in to manage your requests</div>

        <div class="column q-mt-lg">
          <div class="text-body2 text-bold text-grey-8">Email</div>
          <q-input
            class="q-mt-sm custom-input"
            dense
            style="background-color: white"
            color="teal-9"
            filled
            v-model="email"
            placeholder="mjordan@nba.com"
          ></q-input>
          <div class="text-body2 text-bold text-grey-8 q-mt-md">Password</div>
          <q-input
            dense
            class="q-mt-sm custom-input"
            color="teal-9"
            style="background-color: white"
            filled
            v-model="password"
            placeholder="******"
            type="password"
          ></q-input>
          <div class="row">
            <q-space></q-space>
            <span class="text-bold cursor-pointer q-my-md text-teal-9">Forgot password?</span>
          </div>
          <q-btn
            class="q-py-md bg-teal-9"
            style="border-radius: 15px"
            label="Sign in"
            no-caps
            :disable="!valid"
            @click="login"
          ></q-btn>
        </div>

        <div class="text-center q-mt-md">
          <div class="text-grey-9">
            New to MediFlow?
            <span class="text-bold cursor-pointer text-teal-9">Create an account</span>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
import { computed, ref } from 'vue'

const email = ref(null)
const password = ref(null)

const valid = computed(() => {
  if (!email.value || !password.value) return false
  return true
})
</script>

<style scoped>
* {
  color: white;
  font-family: 'Hanken Grotesk', sans-serif;
}
.left-item {
  height: 33%;
}

.chip {
  background: rgba(255, 255, 255, 0.212);
}

.brand-panel {
  background: linear-gradient(350deg, #48a595 0%, #113331 100%);
  position: relative;
  overflow: hidden;
  display: flex;
  flex-direction: column;
  padding: 40px;
}

.brand-panel::before {
  content: '';
  position: absolute;
  top: -150px;
  right: -150px;
  width: 500px;
  height: 500px;
  border-radius: 50%;
  border: 1px solid rgba(255, 255, 255, 0.08);
}

.brand-panel::after {
  content: '';
  position: absolute;
  top: -50px;
  right: -50px;
  width: 350px;
  height: 350px;
  border-radius: 50%;
  border: 1px solid rgba(255, 255, 255, 0.08);
}

.chip {
  background: rgba(255, 255, 255, 0.12);
  border: 1px solid rgba(255, 255, 255, 0.473);
}

.text-h3,
.text-h6 {
  font-family: 'Bricolage Grotesque', sans-serif;
  font-weight: 800;
}

.custom-input {
  border: 2px solid rgba(0, 0, 0, 0.24);
  border-radius: 6px;
}
</style>
