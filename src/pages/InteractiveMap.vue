<template>
  <div class="q-pa-md row items-start q-gutter-md">
    <div class="text-h3 col-12 text-bold">Interactive map</div>
    <q-toolbar class="text-primary row q-ml-none items-center justify-between q-gutter-sm">
      <q-btn flat round dense icon="menu" color="accent"/>
      <q-toolbar-title class="col-auto">
        <div class="text-caption text-weight-medium "><div class="text-accent">Промышленный портал</div><div> Краснодарского края</div></div>
      </q-toolbar-title>
      <q-btn color="primary" class="q-px-xl no-wrap" square icon-right="south_east" no-caps>Каталог</q-btn>

      <q-input class="col-2" v-model="model_input" dense square outlined clearable color="primary" label="Начать поиск">
        <template v-slot:append>
          <q-icon name="search"/>
        </template>
      </q-input>
      <div class="col-grow row justify-center">
        <q-btn flat color="accent" stack square no-caps size="sm" icon="favorite_outline">Избранное</q-btn>
        <q-btn flat color="accent" stack square no-caps size="sm" icon="person_outline">Войти</q-btn>
        <q-btn flat color="accent" stack square no-caps size="sm" icon="work_outline">Выставки</q-btn>
      </div>

      <transition
        appear
        enter-active-class="animated pulse slower delay-5s repeat-2"
        leave-active-class="animated pulse"
      >
        <q-btn color="accent" class="q-px-md" square no-caps>Витрина Кубани</q-btn>
      </transition>
      <q-btn color="accent" class="" square outline>ru</q-btn>
      <q-btn color="accent" class="" square icon="visibility" ></q-btn>

    </q-toolbar>

    <q-card flat bordered style="height: 427px;">
      <q-card-section>
        <div class="text-h6 text-bold">Input</div>
      </q-card-section>
      <q-separator />
      <q-card-actions vertical>

        <q-input class="q-mb-md" v-model="model_input1" dense square outlined clearable color="primary" label="Начать поиск на карте ">
          <template v-slot:append>
            <q-icon name="search"/>
          </template>
        </q-input>
        <q-input class="q-mb-md" v-model="model_input2" dense square outlined clearable color="primary" label="Начать поиск на карте ">
          <template v-slot:append>
            <q-icon name="search"/>
          </template>
        </q-input>
        <q-input class="q-mb-md" v-model="model_input1" dense square outlined clearable disable color="primary" label="Начать поиск на карте ">
          <template v-slot:append>
            <q-icon name="search"/>
          </template>
        </q-input>

        <div class="">Потребность в инвестициях</div>
        <div class="row">
          <q-input dense square outlined v-model="invest_from" label="от 0 руб" class="q-mr-sm"></q-input>
          <q-input dense square outlined v-model="invest_to" label="до 900 000 000 руб"></q-input>
        </div>

        <div class="q-mt-md">Потребность в инвестициях</div>
        <div class="row">
          <q-input dense square outlined v-model="invest_from1"  label="от 0 руб" class="q-mr-sm"></q-input>
          <q-input dense square outlined v-model="invest_to1" label="до 900 000 000 руб"></q-input>
        </div>

      </q-card-actions>
    </q-card>

    <q-card flat bordered>
      <q-card-section>
        <div class="text-h6 text-bold">Checkbox</div>
      </q-card-section>

      <q-separator />

      <q-card-actions vertical>
        <q-item tag="label" dense>
          <q-item-section>
            <q-item-label>Предприятия</q-item-label>
          </q-item-section>
          <q-item-section avatar>
            <q-checkbox color="primary" keep-color v-model="checkbox1"/>
          </q-item-section>
        </q-item>
        <q-item tag="label" dense>
          <q-item-section>
            <q-item-label>Инвестиционные предложения</q-item-label>
          </q-item-section>
          <q-item-section avatar>
            <q-checkbox color="herbal" keep-color v-model="checkbox2"/>
          </q-item-section>
        </q-item>
        <q-item tag="label" dense disable>
          <q-item-section>
            <q-item-label>Инвестиционные площадки</q-item-label>
          </q-item-section>
          <q-item-section avatar>
            <q-checkbox color="accent" keep-color v-model="checkbox3"/>
          </q-item-section>
        </q-item>
        <q-item tag="label" dense>
          <q-item-section>
            <q-item-label>Промышленные парки и технологии</q-item-label>
          </q-item-section>
          <q-item-section avatar>
            <q-checkbox color="lilac" keep-color v-model="checkbox4" />
          </q-item-section>
        </q-item>
        <q-item tag="label">Муниципалиет</q-item>
        <q-checkbox color="accent" keep-color v-model="checkbox_reg1" label="Абинский район" class="q-ml-sm"/>
        <q-checkbox color="accent" keep-color v-model="checkbox_reg2" label="Анапа" class="q-ml-sm"/>
        <q-checkbox color="accent" keep-color v-model="checkbox_reg3" label="Апшеронский район" class="q-ml-sm"/>

      </q-card-actions>
    </q-card>

    <q-card flat bordered>
      <q-card-section>
        <div class="text-h6 text-bold">Select</div>
      </q-card-section>

      <q-separator />

      <q-card-actions vertical>

        <q-select class="q-mb-md" v-model="model_select1" dense square outlined clearable :options="options" color="primary" label="Отрасли предприятия" />

        <q-select class="q-mb-md"  v-model="model_select2" dense square outlined clearable :options="options" color="primary" label="Отрасли предприятия" />

        <q-select v-model="model_select1" dense square outlined disable clearable :options="options" label="Отрасли предприятия" />

      </q-card-actions>
    </q-card>

    <q-card flat bordered>
      <q-card-section>
        <div class="text-h6 text-bold">Button</div>
      </q-card-section>

      <q-separator />

      <q-card-actions vertical>
        <q-btn flat square color="primary" no-caps>
          <div style="border-bottom: solid #1553A3 1px;">
            <span>Открыть все районы</span>
            <q-icon name="south_east" size="1.1em"></q-icon>
        </div></q-btn>
        <q-btn flat square color="accent" no-caps>
          <div style="border-bottom: solid #0A1A3E 1px;">
            <span>Открыть все районы</span>
            <q-icon name="south_east" size="1.1em"></q-icon>
          </div></q-btn>
        <q-btn flat square color="primary" no-caps disabled>
          <div style="border-bottom: solid #0A1A3E 1px;">
            <span>Открыть все районы</span>
            <q-icon name="south_east" size="1.1em"></q-icon>
          </div></q-btn>
      </q-card-actions>
    </q-card>

    <q-card flat bordered>
      <q-card-section>
        <div class="text-h6 text-bold">Chips</div>
      </q-card-section>

      <q-separator />

      <q-card-actions vertical>
        <q-chip  square color="primary" text-color="white">Работает</q-chip>
        <q-chip outline square color="primary" >Создаётся</q-chip>
        <q-chip outline square color="primary" >Планируется</q-chip>
      </q-card-actions>
    </q-card>
  </div>
</template>

<script setup lang="ts">
import { defineComponent, ref } from 'vue';

defineComponent({
  name: 'InteractiveMap',
});

const options = ['Производство кожи, одежды, обуви и так далее', 'Производство текстиля']

const model_select1 = ref(null)
const model_select2 = ref('Производство текстиля')

const model_input = ref(null)
const model_input1 = ref(null)
const model_input2 = ref('Промышленный парк')

const checkbox1 = ref( false)
const checkbox2 = ref( true)
const checkbox3 = ref( false)
const checkbox4 = ref( true)

const checkbox_reg1 = ref( false)
const checkbox_reg2 = ref( true)
const checkbox_reg3 = ref( false)

const invest_from = ref( null)
const invest_to = ref( null)
const invest_from1 = ref( 1000000)
const invest_to1 = ref( 5000657)
</script>
