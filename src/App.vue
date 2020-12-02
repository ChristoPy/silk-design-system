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
      <SAvatar :image="avatar" :description="description"/>
      <SAvatar name="Multiple Name"/>
    </div>

    <SList :items="items"/>

    <SList>
      <SListItem v-for="item in singleItems" :key="item.name" :name="item.name" :text="item.text"/>
    </SList>

    <SList :items="itemsWithAvatar"/>

    <SCard title="First card"/>
    <SCard title="First card with text" text="some text in here"/>

    <SCard title="First outlined card" outlined/>
    <SCard title="First outlined card with text" text="some text in here" outlined/>
  </S-App>
</template>

<script>
import SApp from './components/s-app/index.vue';
import SButton from './components/s-button/index.vue';
import SInput from './components/s-input/index.vue';
import SRadio from './components/s-radio/index.vue';
import SAvatar from './components/s-avatar/index.vue';
import SList from './components/s-list/index.vue';
import SListItem from './components/s-list-item/index.vue';
import SCard from './components/s-card/index.vue';

export default {
  name: 'App',
  components: {
    SApp,
    SButton,
    SInput,
    SRadio,
    SAvatar,
    SList,
    SListItem,
    SCard,
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
    singleItems: [
      {
        name: 'Single Item Without Text',
      },
      {
        name: 'Single Item',
        text: 'Single Item Text',
      },
    ],
    avatar: 'https://images.pexels.com/photos/709790/pexels-photo-709790.jpeg',
    description: 'A user profile description as alt text',
  }),
  computed: {
    itemsWithAvatar() {
      return [
        {
          name: 'Item 1 with avatar name',
          text: 'Item 1 with avatar text',
          avatar: {
            name: 'Avatar Name',
            description: this.description,
          },
        },
        {
          name: 'Item 2 with avatar name',
          avatar: {
            image: this.avatar,
            description: this.description,
          },
        },
        {
          name: 'Item 3 with avatar and no image',
          avatar: {
            name: 'Design System',
            description: this.description,
          },
        },
        {
          name: 'Item 4 with avatar name',
          text: 'Item 4 with avatar text',
          avatar: {
            image: this.avatar,
            description: this.description,
          },
        },
      ];
    },
  },
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
