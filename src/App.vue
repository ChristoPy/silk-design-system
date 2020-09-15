<template>
  <S-App>
    <h1>Header 1</h1>
    <h2>Header 2</h2>
    <h3>Header 3</h3>
    <h4>Header 4</h4>
    <h5>Header 5</h5>
    <p>
      Lorem ipsum dolor sit amet consectetur adipisicing elit.
      Iusto autem, sequi magnam animi hic voluptas qui adipisci suscipit,
      numquam distinctio explicabo quae, molestiae repellat! Velit,
      dignissimos doloribus? Libero, laborum saepe!
    </p>
    <SButton text="yo"/>
    <SButton text="yo" outlined/>
    <SButton text="yo" disabled/>
    <SButton text="yo" outlined disabled/>

    <SButton text="yo" primary/>
    <SButton text="yo" outlined primary/>
    <SButton text="yo" primary disabled/>
    <SButton text="yo" outlined primary disabled/>

    <SButton text="yo" danger/>
    <SButton text="yo" outlined danger/>
    <SButton text="yo" danger disabled/>
    <SButton text="yo" outlined danger disabled/>
  </S-App>
</template>

<script>
import SApp from './components/s-app/index.vue';
import SButton from './components/s-button/index.vue';

export default {
  name: 'App',
  components: {
    SApp,
    SButton,
  },
};
</script>
