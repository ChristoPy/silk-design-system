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

    <SInput name="e-mail" label="E-mail" :hint="hint" v-model="email" :error="error"/>
    <SInput name="e-mail" label="E-mail" :hint="hint" v-model="email" disabled/>

    <SRadio name="e-mail" label="E-mail" v-model="selected"/>
    <SRadio name="e-mail" label="E-mail" v-model="selected"/>

    <SRadio name="disabled" label="Disabled" disabled/>

    <div>
      <SAvatar name="SingleName"/>
      <SAvatar name="Multiple Name"/>
    </div>

    <SList :items="items"/>
  </S-App>
</template>

<script>
import SApp from './components/s-app/index.vue';
import SButton from './components/s-button/index.vue';
import SInput from './components/s-input/index.vue';
import SRadio from './components/s-radio/index.vue';
import SAvatar from './components/s-avatar/index.vue';
import SList from './components/s-list/index.vue';

export default {
  name: 'App',
  components: {
    SApp,
    SButton,
    SInput,
    SRadio,
    SAvatar,
    SList,
  },
  data: () => ({
    email: '',
    hint: "We'll not spam you, it's okay",
    selected: false,
    error: false,
    items: [
      {
        name: 'Item 1 name',
        text: 'Item 1 text',
      },
      {
        name: 'Item 2 name',
      },
      {
        name: 'Item 3 name',
      },
      {
        name: 'Item 4 name',
        text: 'Item 4 text',
      },
    ],
  }),
  watch: {
    email() {
      const noAtSymbol = this.email.length && !this.email.includes('@');

      if (noAtSymbol) {
        this.hint = 'Your email should contain an \'@\' character';
        this.error = true;
      } else {
        this.hint = "We'll not spam you, it's okay";
        this.error = false;
      }
    },
  },
};
</script>
