<template>
  <b-container fluid>
    <b-row>
      <b-col>
        <b-form-textarea
          id="textarea"
          v-model="text"
          placeholder="Enter something..."
          rows="100"
          max-rows="6"
        ></b-form-textarea>
      </b-col>

      <b-col class="sticky-top">
        <textarea id="editor" name="editor"></textarea>
      </b-col>
    </b-row>
  </b-container>
</template>

<script>
  export default {
    name: 'EditorManual',
    data () {
      return {
          editor: ''
      }
    },
    mounted(){
        this.editor = new this.$jodit('#editor', {
          height: 400,
          uploader: {
            insertImageAsBase64URI: true
          },
          buttons: "source,|,underline,italic,eraser,|,,ul,ol,,|,fontsize,,image,table,link,|,align,undo,redo,,fullsize,print,selectall",
          askBeforePasteHTML: false,
          askBeforePasteFromWord: false,
        });
    }
  }
</script>
