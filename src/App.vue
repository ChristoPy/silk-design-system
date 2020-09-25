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
    <SButton text="Primary" block />
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
