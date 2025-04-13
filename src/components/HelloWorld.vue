<template>
  <v-card-text class="px-3 pa-0 text-body-1">
    <v-card-text class="mb-3 pa-0 text-body-1">
      <v-checkbox v-bind:ripple="false" label="テスト" v-model="state.test" v-on:change="changeTest" hide-details />
    </v-card-text>
    <!-- テキスト -->
    <v-card-text class="mb-3 pa-0 text-body-1">
      <v-card-text class="ma-0 pa-0 text-h1" v-bind:style="{ 'background-color': state.backgroundColor }">Heading 1</v-card-text>
      <v-card-text class="ma-0 pa-0 text-h2" v-bind:style="{ 'background-color': state.backgroundColor2 }">Heading 2</v-card-text>
      <v-card-text class="ma-0 pa-0 text-h3" v-bind:style="{ 'background-color': state.backgroundColor }">Heading 3</v-card-text>
      <v-card-text class="ma-0 pa-0 text-h4" v-bind:style="{ 'background-color': state.backgroundColor2 }">Heading 4</v-card-text>
      <v-card-text class="ma-0 pa-0 text-h5" v-bind:style="{ 'background-color': state.backgroundColor }">Heading 5</v-card-text>
      <v-card-text class="ma-0 pa-0 text-h6" v-bind:style="{ 'background-color': state.backgroundColor2 }">Heading 6</v-card-text>
      <v-card-text class="ma-0 pa-0 text-subtitle-1" v-bind:style="{ 'background-color': state.backgroundColor }">Subtitle 1</v-card-text>
      <v-card-text class="ma-0 pa-0 text-subtitle-2" v-bind:style="{ 'background-color': state.backgroundColor2 }">Subtitle 2</v-card-text>
      <v-card-text class="ma-0 pa-0 text-body-1" v-bind:style="{ 'background-color': state.backgroundColor }">Body 1</v-card-text>
      <v-card-text class="ma-0 pa-0 text-body-2" v-bind:style="{ 'background-color': state.backgroundColor2 }">Body 2</v-card-text>
      <v-card-text class="ma-0 pa-0 text-button" v-bind:style="{ 'background-color': state.backgroundColor }">Button</v-card-text>
      <v-card-text class="ma-0 pa-0 text-caption" v-bind:style="{ 'background-color': state.backgroundColor2 }">Caption</v-card-text>
      <v-card-text class="ma-0 pa-0 text-overline" v-bind:style="{ 'background-color': state.backgroundColor }">Overline</v-card-text>
    </v-card-text>
    <!-- ボタン -->
    <v-card-text class="mb-3 pa-0 text-body-1" v-bind:style="{ 'background-color': state.backgroundColor }">
      <v-btn v-bind:ripple="false" style="text-transform:none" v-on:click="onClick1">default</v-btn>
      <v-btn v-bind:ripple="false" style="text-transform:none" v-on:click="onClick2" variant="tonal">tonal</v-btn>
      <v-btn v-bind:ripple="false" style="text-transform:none" v-on:click="onClick3" variant="text">text</v-btn>
      <v-btn v-bind:ripple="false" style="text-transform:none" v-on:click="onClick4" variant="plain">plain</v-btn>
      <v-btn v-bind:ripple="false" style="text-transform:none" v-on:click="onClick5" variant="outlined">outlined</v-btn>
    </v-card-text>
    <!-- ボタン（disabled） -->
    <v-card-text class="mb-3 pa-0 text-body-1" v-bind:style="{ 'background-color': state.backgroundColor }">
      <v-btn style="text-transform:none" v-on:click="onClick1" v-bind:disabled="state.disableFlag1">default</v-btn>
      <v-btn style="text-transform:none" v-on:click="onClick2" v-bind:disabled="state.disableFlag2" variant="tonal">tonal</v-btn>
      <v-btn style="text-transform:none" v-on:click="onClick3" v-bind:disabled="state.disableFlag3" variant="text">text</v-btn>
      <v-btn style="text-transform:none" v-on:click="onClick4" v-bind:disabled="state.disableFlag4" variant="plain">plain</v-btn>
      <v-btn style="text-transform:none" v-on:click="onClick5" v-bind:disabled="state.disableFlag5" variant="outlined">outlined</v-btn>
    </v-card-text>
    <!-- チェックボックス -->
    <v-card-actions class="mb-3 pa-0 text-body-1" v-bind:style="{ 'background-color': state.backgroundColor }">
      <v-checkbox v-bind:ripple="false" label="checkbox 1 (default)" v-model="state.checkboxValue1" v-on:change="changeCheckbox1" />
    </v-card-actions>
    <v-card-actions class="mb-3 pa-0 text-body-1" v-bind:style="{ 'background-color': state.backgroundColor }">
      <!--<v-checkbox label="checkbox 2 (hide details)" v-model="state.checkboxValue2" v-on:change="changeCheckbox2" hide-details v-bind:disabled="true" />-->
      <v-checkbox label="checkbox 2 (hide details)" v-model="state.checkboxValue1" v-on:change="changeCheckbox2" hide-details v-bind:disabled="true" />
    </v-card-actions>
    <!-- ラジオボタン -->
    <v-card-actions class="mb-3 pa-0 text-body-1" v-bind:style="{ 'background-color': state.backgroundColor }">
      <v-radio-group label="radio group 1 (default)" v-model="state.radioValue1" v-on:change="selectRadio1">
        <v-radio v-bind:ripple="false" label="radio 1" value="hoge" />
        <v-radio v-bind:ripple="false" label="radio 2" value="fuga" />
        <v-radio v-bind:ripple="false" label="radio 3" value="piyo" />
      </v-radio-group>
    </v-card-actions>
    <v-card-actions class="mb-3 pa-0 text-body-1" v-bind:style="{ 'background-color': state.backgroundColor }">
      <v-radio-group inline label="radio group 2 (row & default)" v-model="state.radioValue2" v-on:change="selectRadio2">
        <v-radio v-bind:ripple="false" label="radio 1" value="hoge" />
        <v-radio v-bind:ripple="false" label="radio 2" value="fuga" />
        <v-radio v-bind:ripple="false" label="radio 3" value="piyo" />
      </v-radio-group>
    </v-card-actions>
    <v-card-actions class="mb-3 pa-0 text-body-1" v-bind:style="{ 'background-color': state.backgroundColor }">
      <v-radio-group label="radio group 3 (hide details)" v-model="state.radioValue3" v-on:change="selectRadio3" hide-details v-bind:disabled="true">
        <v-radio label="radio 1" value="hoge" />
        <v-radio label="radio 2" value="fuga" />
        <v-radio label="radio 3" value="piyo" />
      </v-radio-group>
    </v-card-actions>
    <v-card-actions class="mb-3 pa-0 text-body-1" v-bind:style="{ 'background-color': state.backgroundColor }">
      <v-radio-group inline label="radio group 4 (row & hide details)" v-model="state.radioValue4" v-on:change="selectRadio4" hide-details v-bind:disabled="true">
        <v-radio label="radio 1" v-bind:value="1" />
        <v-radio label="radio 2" v-bind:value="2" />
        <v-radio label="radio 3" v-bind:value="3" />
      </v-radio-group>
    </v-card-actions>
    <!-- テキスト入力（単一行） -->
    <v-card-text class="mb-3 pa-0 text-body-1" v-bind:style="{ 'background-color': state.backgroundColor }">
      <v-text-field label="default" v-model="text1" />
    </v-card-text>
    <v-card-text class="mb-3 pa-0 text-body-1" v-bind:style="{ 'background-color': state.backgroundColor }">
      <v-text-field label="underlined" v-model="text2" variant="underlined" />
    </v-card-text>
    <v-card-text class="mb-3 pa-0 text-body-1" v-bind:style="{ 'background-color': state.backgroundColor }">
      <v-text-field label="outlined" v-model="text3" variant="outlined" />
    </v-card-text>
    <v-card-text class="mb-3 pa-0 text-body-1" v-bind:style="{ 'background-color': state.backgroundColor }">
      <v-text-field label="solo" v-model="text4" variant="solo" />
    </v-card-text>
    <v-card-text class="mb-3 pa-0 text-body-1" v-bind:style="{ 'background-color': state.backgroundColor }">
      <v-text-field label="solo-filled" v-model="text5" variant="solo-filled" />
    </v-card-text>
    <v-card-text class="mb-3 pa-0 text-body-1" v-bind:style="{ 'background-color': state.backgroundColor }">
      <v-text-field label="solo-inverted" v-model="text6" variant="solo-inverted" />
    </v-card-text>
    <v-card-text class="mb-3 pa-0 text-body-1" v-bind:style="{ 'background-color': state.backgroundColor }">
      <v-text-field label="default (hide details)" hide-details v-bind:disabled="true" />
    </v-card-text>
    <v-card-text class="mb-3 pa-0 text-body-1" v-bind:style="{ 'background-color': state.backgroundColor }">
      <v-text-field label="underlined (hide details)" variant="underlined" hide-details v-bind:disabled="true" />
    </v-card-text>
    <v-card-text class="mb-3 pa-0 text-body-1" v-bind:style="{ 'background-color': state.backgroundColor }">
      <v-text-field label="outlined (hide details)" variant="outlined" hide-details v-bind:disabled="true" />
    </v-card-text>
    <v-card-text class="mb-3 pa-0 text-body-1" v-bind:style="{ 'background-color': state.backgroundColor }">
      <v-text-field label="solo (hide details)" variant="solo" hide-details v-bind:disabled="true" />
    </v-card-text>
    <v-card-text class="mb-3 pa-0 text-body-1" v-bind:style="{ 'background-color': state.backgroundColor }">
      <v-text-field label="solo-filled (hide details)" variant="solo-filled" hide-details v-bind:disabled="true" />
    </v-card-text>
    <v-card-text class="mb-3 pa-0 text-body-1" v-bind:style="{ 'background-color': state.backgroundColor }">
      <v-text-field label="solo-inverted (hide details)" variant="solo-inverted" hide-details v-bind:disabled="true" />
    </v-card-text>
    <!-- テキスト入力（複数行） -->
    <v-card-text class="mb-3 pa-0 text-body-1" v-bind:style="{ 'background-color': state.backgroundColor }">
      <v-textarea label="default" v-model="text7" />
    </v-card-text>
    <v-card-text class="mb-3 pa-0 text-body-1" v-bind:style="{ 'background-color': state.backgroundColor }">
      <v-textarea label="underlined" v-model="text8" variant="underlined" />
    </v-card-text>
    <v-card-text class="mb-3 pa-0 text-body-1" v-bind:style="{ 'background-color': state.backgroundColor }">
      <v-textarea label="outlined" v-model="text9" variant="outlined" />
    </v-card-text>
    <v-card-text class="mb-3 pa-0 text-body-1" v-bind:style="{ 'background-color': state.backgroundColor }">
      <v-textarea label="solo" v-model="text10" variant="solo" />
    </v-card-text>
    <v-card-text class="mb-3 pa-0 text-body-1" v-bind:style="{ 'background-color': state.backgroundColor }">
      <v-textarea label="solo-filled" v-model="text11" variant="solo-filled" />
    </v-card-text>
    <v-card-text class="mb-3 pa-0 text-body-1" v-bind:style="{ 'background-color': state.backgroundColor }">
      <v-textarea label="solo-inverted" v-model="text12" variant="solo-inverted" />
    </v-card-text>
    <v-card-text class="mb-3 pa-0 text-body-1" v-bind:style="{ 'background-color': state.backgroundColor }">
      <v-textarea label="default (hide details)" hide-details v-bind:disabled="true" />
    </v-card-text>
    <v-card-text class="mb-3 pa-0 text-body-1" v-bind:style="{ 'background-color': state.backgroundColor }">
      <v-textarea label="underlined (hide details)" variant="underlined" hide-details v-bind:disabled="true" />
    </v-card-text>
    <v-card-text class="mb-3 pa-0 text-body-1" v-bind:style="{ 'background-color': state.backgroundColor }">
      <v-textarea label="outlined (hide details)" variant="outlined" hide-details v-bind:disabled="true" />
    </v-card-text>
    <v-card-text class="mb-3 pa-0 text-body-1" v-bind:style="{ 'background-color': state.backgroundColor }">
      <v-textarea label="solo (hide details)" variant="solo" hide-details v-bind:disabled="true" />
    </v-card-text>
    <v-card-text class="mb-3 pa-0 text-body-1" v-bind:style="{ 'background-color': state.backgroundColor }">
      <v-textarea label="solo-filled (hide details)" variant="solo-filled" hide-details v-bind:disabled="true" />
    </v-card-text>
    <v-card-text class="mb-3 pa-0 text-body-1" v-bind:style="{ 'background-color': state.backgroundColor }">
      <v-textarea label="solo-inverted (hide details)" variant="solo-inverted" hide-details v-bind:disabled="true" />
    </v-card-text>
  </v-card-text>
</template>

<script lang="ts">
import { defineComponent, reactive, ref, watch } from 'vue'

interface State {
  test: boolean
  backgroundColor: string
  backgroundColor2: string
  disableFlag1: boolean
  disableFlag2: boolean
  disableFlag3: boolean
  disableFlag4: boolean
  disableFlag5: boolean
  checkboxValue1: boolean
  checkboxValue2: boolean
  radioValue1: string
  radioValue2: string
  radioValue3: string
  radioValue4: number
}

export default defineComponent({
  name: 'HelloWorld',
  setup () {
    const state = reactive<State>({
      test: false,
      backgroundColor: '#ffffff',
      backgroundColor2: '#ffffff',
      disableFlag1: true,
      disableFlag2: true,
      disableFlag3: true,
      disableFlag4: true,
      disableFlag5: true,
      checkboxValue1: false,
      checkboxValue2: false,
      radioValue1: 'hoge',
      radioValue2: 'hoge',
      radioValue3: 'hoge',
      radioValue4: 1
    })

    const text1 = ref('')
    const text2 = ref('')
    const text3 = ref('')
    const text4 = ref('')
    const text5 = ref('')
    const text6 = ref('')
    const text7 = ref('')
    const text8 = ref('')
    const text9 = ref('')
    const text10 = ref('')
    const text11 = ref('')
    const text12 = ref('')

    const changeTest = () => {
      if (state.test) {
        state.backgroundColor = '#ffffc0'
        state.backgroundColor2 = '#ffc0ff'
      } else {
        state.backgroundColor = '#ffffff'
        state.backgroundColor2 = '#ffffff'
      }
    }
    const onClick1 = () => {
      console.log('onClick1')
    }
    const onClick2 = () => {
      console.log('onClick2')
    }
    const onClick3 = () => {
      console.log('onClick3')
    }
    const onClick4 = () => {
      console.log('onClick4')
    }
    const onClick5 = () => {
      console.log('onClick5')
    }
    const changeCheckbox1 = () => {
      console.log('changeCheckbox1 ' + state.checkboxValue1)
    }
    const changeCheckbox2 = () => {
      console.log('changeCheckbox2 ' + state.checkboxValue2)
    }
    const selectRadio1 = () => {
      console.log('selectRadio1 ' + state.radioValue1)
    }
    const selectRadio2 = () => {
      console.log('selectRadio2 ' + state.radioValue2)
    }
    const selectRadio3 = () => {
      console.log('selectRadio3 ' + state.radioValue3)
    }
    const selectRadio4 = () => {
      console.log('selectRadio4 ' + state.radioValue4)
    }

    watch([text1, text2, text3, text4, text5, text6, text7, text8, text9, text10, text11, text12], (
      [newText1, newText2, newText3, newText4, newText5, newText6, newText7, newText8, newText9, newText10, newText11, newText12],
      [oldText1, oldText2, oldText3, oldText4, oldText5, oldText6, oldText7, oldText8, oldText9, oldText10, oldText11, oldText12]
    ) => {
      if (newText1 !== oldText1) {
        console.log('text1 ' + newText1)
      }
      if (newText2 !== oldText2) {
        console.log('text2 ' + newText2)
      }
      if (newText3 !== oldText3) {
        console.log('text3 ' + newText3)
      }
      if (newText4 !== oldText4) {
        console.log('text4 ' + newText4)
      }
      if (newText5 !== oldText5) {
        console.log('text5 ' + newText5)
      }
      if (newText6 !== oldText6) {
        console.log('text6 ' + newText6)
      }
      if (newText7 !== oldText7) {
        console.log('text7 ' + newText7)
      }
      if (newText8 !== oldText8) {
        console.log('text8 ' + newText8)
      }
      if (newText9 !== oldText9) {
        console.log('text9 ' + newText9)
      }
      if (newText10 !== oldText10) {
        console.log('text10 ' + newText10)
      }
      if (newText11 !== oldText11) {
        console.log('text11 ' + newText11)
      }
      if (newText12 !== oldText12) {
        console.log('text12 ' + newText12)
      }
    })

    return {
      state,
      text1,
      text2,
      text3,
      text4,
      text5,
      text6,
      text7,
      text8,
      text9,
      text10,
      text11,
      text12,
      changeTest,
      onClick1,
      onClick2,
      onClick3,
      onClick4,
      onClick5,
      changeCheckbox1,
      changeCheckbox2,
      selectRadio1,
      selectRadio2,
      selectRadio3,
      selectRadio4
    }
  }
})
</script>
