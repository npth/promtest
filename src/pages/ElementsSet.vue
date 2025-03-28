<template>
  <div class="q-pa-md row items-start q-gutter-md">
    <div class="text-h3 col-12 text-bold">Elements</div>

    <q-card flat bordered class="bg-primary">
      <q-card-section>
        <div class="text-h6 text-bold text-secondary">Select</div>
      </q-card-section>

      <q-separator />

      <q-card-actions vertical>
        <q-input outlined dense color="secondary" v-model="text" label="Outlined" />
      </q-card-actions>
    </q-card>

    <q-timeline color="secondary">
      <q-timeline-entry heading> Timeline heading</q-timeline-entry>

      <q-timeline-entry title="01" side="left" subtitle="Первый этап">
        <div>01</div>
      </q-timeline-entry>

      <q-timeline-entry title="02" side="right" subtitle="Второй этап">
        <div>02</div>
      </q-timeline-entry>
    </q-timeline>
<div class="col-12">
    <q-breadcrumbs separator="•" separator-color="neutral">
      <q-breadcrumbs-el label="Главная" />
      <q-breadcrumbs-el label="Полная версия интерактивной карты" />
    </q-breadcrumbs>
</div>

    <div class="col-4">
      <q-card class="my-card" @click="$router.push('/imap')" style="cursor: pointer">
        <q-card-section>
          <div class="text-h6 text-right">08 / 03</div>
          <div class="text-subtitle2 text-right">Мероприятие "Человек Дела - Кубань"</div>
        </q-card-section>

        <img src="https://cdn.quasar.dev/img/mountains.jpg" alt="image" />

        <q-card-section class="q-pt-none text-right">
          <a href="">Подробности</a>
        </q-card-section>
      </q-card>
    </div>

    <transition
      appear
      enter-active-class="animated swing slower delay-5s repeat-3"
      leave-active-class="animated fadeOut"
    >
      <!-- Wrapping only one DOM element, defined by QBtn -->
      <q-btn
        color="secondary"
        icon="mail"
        label="Email"
      />
    </transition>


  </div>
</template>

<script setup lang="ts">
import { defineComponent, ref } from 'vue';

defineComponent({
  name: 'ElementsSet',
});

const text = ref(null);
</script>
