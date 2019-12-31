<template>
  <div>
    <h1>見出し１</h1>
    <h2>見出し２</h2>
    <h3>見出し３</h3>
    <p>テキスト</p>
    <a href="#">リンク</a>
    <p><strong>太字</strong></p>
    <p><small>小文字</small></p>
    <ul>
      <li>リスト1</li>
      <li>リスト2</li>
      <li>リスト3</li>
    </ul>
    <ol>
      <li>順序リスト1</li>
      <li>順序リスト2</li>
      <li>順序リスト3</li>
    </ol>
    <form>
      <div>
        <input type="text" value="1行テキストボックス" />
      </div>
      <div>
        <input type="submit" />
      </div>
      <div>
        <label><input type="checkbox" />チェックボックス</label>
      </div>
    </form>
    <ul>
      <li v-for="(fact, factIdx) in facts" :key="factIdx">
        {{ fact.text }}
      </li>
    </ul>
    <div class="buttons">
      <b-button size="is-small">Small</b-button>
      <b-button>Default</b-button>
      <b-button size="is-medium">Medium</b-button>
      <b-button size="is-large">Large</b-button>
    </div>
  </div>
</template>
<script>
import axios from 'axios'
export default {
  async asyncData() {
    const res = await axios.get('https://nuxt-ssr.firebaseio.com/facts.json')
    const facts = res.data
    return { facts }
  }
}
</script>
<style></style>
