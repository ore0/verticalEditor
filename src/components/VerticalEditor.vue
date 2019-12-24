<template>
  <editor-content class="editor" :editor="editor" />
</template>

<script>
import { Editor, EditorContent } from "tiptap";
import {
  Blockquote,
  CodeBlock,
  HardBreak,
  Heading,
  OrderedList,
  BulletList,
  ListItem,
  TodoItem,
  TodoList,
  Bold,
  Code,
  Italic,
  Link,
  History
} from "tiptap-extensions";
export default {
  components: {
    EditorContent
  },
  data() {
    return {
      editor: new Editor({
        extensions: [
          new Blockquote(),
          new BulletList(),
          new CodeBlock(),
          new HardBreak(),
          new Heading({ levels: [1, 2, 3] }),
          new ListItem(),
          new OrderedList(),
          new TodoItem(),
          new TodoList(),
          new Bold(),
          new Code(),
          new Italic(),
          new Link(),
          new History()
        ],
        content: `
          <h1>美しい日本語</h1>
          <h2>草枕</h2>
          <p>山路を登りながら、こう考えた。</p>
          <p>智に働けば角が立つ。情に掉させば流される。意地を通せば窮屈だ。とかくに人の世は住みにくい。</p>
          <p>住みにくさが高じると、安いところへ引き越したくなる。どこへ越しても住みにくいと悟ったとき、詩が生れて、絵ができる。</p>

          <h2>東京の坂道</h2>
          <ul>
            <li>乃木坂</li>
            <li>けやき坂</li>
            <li>日向坂</li>
          </ul>
          <h2>徒然草</h2>
          <h3>折節の移り変るこそ、ものごとにあはれなれ。</h3>
          <p>さて、冬枯のけしきこそ、秋にはをさをさ劣るまじけれ。汀の草に紅葉の散り止りて、霜いと白うおける朝、遣水より烟の立つこそをかしけれ。年の暮れ果てて、人ごとに急ぎあへるころぞ、またなくあはれなる。すさまじきものにして見る人もなき月の寒けく澄める、廿日余りの空こそ、心ぼそきものなれ。御仏名、荷前の使立つなどぞ、あはれにやんごとなき。公事ども繁く、春の急ぎにとり重ねて催し行はるるさまぞ、いみじきや。追儺より四方拝に続くこそ面白けれ。晦日の夜、いたう闇きに、松どもともして、夜半過ぐるまで、人の、門叩き、走りありきて、何事にかあらん、ことことしくのゝしりて、足を空に惑ふが、暁がたより、さすがに音なくなりぬるこそ、年の名残も心ぼそけれ。亡き人のくる夜とて魂祭るわざは、このごろ都にはなきを、東のかたには、なほする事にてありしこそ、あはれなりしか。</p>
          <p>かくて明けゆく空のけしき、昨日に変りたりとは見えねど、ひきかへめづらしき心地ぞする。大路のさま、松立てわたして、はなやかにうれしげなるこそ、またあはれなれ。</p>
          `
      })
    };
  },
  beforeDestroy() {
    this.editor.destroy();
  }
};
</script>

<style lang="scss">
.editor {
  display: block;
  width: 100%;
  height: 100%;
  padding: 80px 160px;
  -webkit-writing-mode: vertical-rl;
  -ms-writing-mode: tb-rl;
  writing-mode: vertical-rl;
  font-size: 20px;
  font-family: "Noto Serif JP", serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  -webkit-font-feature-settings: "palt";
  font-feature-settings: "palt";
  color: #2c3e50;
  line-height: 2em;
  .ProseMirror {
    display: block;
    width: 100%;
    height: 100%;
    padding: 0.5em 0;
    overflow-x: scroll;
    &:focus {
      outline: none;
    }
    &::-webkit-scrollbar {
      height: 4px;
    }
    &::-webkit-scrollbar-thumb {
      background-color: #999;
      border-radius: 1px;
    }
    p {
      text-indent: 1em;
    }
    ul,
    ol {
      margin-top: 1em;
      padding: 0;
      p {
        text-indent: 0em;
      }
    }
    h1,
    h2,
    h3,
    h4 {
      margin-left: 1em;
      &:not(:first-child) {
        margin-right: 2em;
      }
    }
    p {
      display: block;
    }
  }
}
</style>
