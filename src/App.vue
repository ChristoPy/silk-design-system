<template>
  <S-App>
    <h1>Header 1</h1>
    <h2>Header 2</h2>
    <h3>Header 3</h3>
    <h4>Header 4</h4>
    <p>
      Lorem ipsum dolor sit amet consectetur adipisicing elit.
      Iusto autem, sequi magnam animi hic voluptas qui adipisci suscipit,
      numquam distinctio explicabo quae, molestiae repellat! Velit,
      dignissimos doloribus? Libero, laborum saepe!
    </p>
    <SButton text="Primary" block/>
    <SButton text="Primary" block outlined/>
    <SButton text="Primary" block disabled/>
    <SButton text="Primary" block outlined disabled/>

    <SButton text="Primary" block primary/>
    <SButton text="Primary" block primary outlined/>
    <SButton text="Primary" block primary disabled/>
    <SButton text="Primary" block primary outlined disabled/>

    <SButton text="Primary" block danger/>
    <SButton text="Primary" block danger outlined/>
    <SButton text="Primary" block danger disabled/>
    <SButton text="Primary" block danger outlined disabled/>

    <SInput name="e-mail" label="E-mail"/>
    <SInput name="e-mail" label="E-mail" disabled/>

    <SInput name="e-mail" label="E-mail" :hint="hint" v-model="email"/>
    <SInput name="e-mail" label="E-mail" :hint="hint" v-model="email" disabled/>

    <SRadio name="e-mail" label="E-mail" v-model="selected"/>
    <SRadio name="e-mail" label="E-mail" v-model="selected"/>

    <SRadio name="disabled" label="Disabled" disabled/>
  </S-App>
</template>

<script>
import SApp from './components/s-app/index.vue';
import SButton from './components/s-button/index.vue';
import SInput from './components/s-input/index.vue';
import SRadio from './components/s-radio/index.vue';

export default {
  name: 'App',
  components: {
    SApp,
    SButton,
    SInput,
    SRadio,
  },
  data: () => ({
    email: '',
    hint: "We'll not spam you, it's okay",
    selected: false,
  }),
};
</script>
