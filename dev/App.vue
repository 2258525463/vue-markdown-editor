<template>
  <div>
    <v-md-editor
      v-model="text"
      mode="preview"
      height="500px"
      autofocus
      toc-nav-position-right
      :disabled-menus="[]"
      :default-toc-visible="true"
      @upload-image="handleUploadImage"
      @fullscreen-change="handleFullscreenChange"
      @save="handleSave"
      @copy-code-success="handleCopyCodeSuccess"
      @image-click="handleImageClick"
      @toc-nav-loaded="handleTocNavLoaded"
      ref="editor"
    />
  </div>
</template>

<script>
import text from './text';

export default {
  mounted() {
    debugger
  },
  data() {
    return {
      text,
    };
  },
  methods: {
    handleTocNavLoaded(titles) {
      //跳转到某个标题
      /*if (titles.length > 0) {
        let title = titles.filter(item=> item.title === 'Refrence');
        this.$refs.editor.scrollToLine(title.lineIndex)
      }*/
    },
    handleImageClick(images, currentIndex) {
      console.log(images, currentIndex);
    },
    handleFullscreenChange(v) {
      console.log(v);
    },
    handleUploadImage(e, insertImage, files) {
      console.log(files);

      insertImage({
        url: '111',
        desc: '111',
      });
    },
    handleSave(v, html) {
      console.log(v, html);
    },
    handleCopyCodeSuccess(code) {
      console.log(code);
    },
  },
};
</script>
