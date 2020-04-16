<template>
  <section id="myeditor">11111</section>
</template>

<script>
import "tinymce";
import "tinymce/themes/silver/theme";
import "tinymce/skins/ui/oxide/skin.min.css";
import "@/langs/zh_CN.js";
import "tinymce/plugins/preview/plugin.min.js";
import "tinymce/plugins/image/plugin.min.js";
import "tinymce/plugins/table/plugin.min.js";
import "tinymce/plugins/print/plugin.min.js";
import "tinymce/plugins/fullscreen/plugin.min.js";
import "tinymce/plugins/code/plugin.min.js";
import "tinymce/plugins/insertdatetime/plugin.min.js";
export default {
  mounted() {
    tinymce.init({
      selector: "#myeditor",
      language: "zh_CN",
      menubar: "bar1 bar2 format",
      menu: {
        bar1: { title: "菜单一", items: "copy paste" },
        bar2: { title: "菜单二", items: "cut format" }
      },
      toolbar:
        " myButton1 | myButton2 redo undo styleselect forecolor insertdatetime code fullscreen image preview table print | formatselect | bold italic | alignleft aligncenter alignright alignjustify | numlist bullist | outdent indent",
      // plugins: "preview image table print bbcode",
      plugins: "preview image table print fullscreen code insertdatetime",
      bbcode_dialect: "punbb",
      setup: function(editor) {
        editor.ui.registry.addButton("myButton1", {
          icon: "user",
          onAction: function(_) {
            editor.insertContent(
              "&nbsp;<strong>It's my icon button!</strong>&nbsp;"
            );
          }
        });

        editor.ui.registry.addButton("myButton2", {
          text: "My Button",
          onAction: function(_) {
            editor.insertContent(
              "&nbsp;<strong>It's my text button!</strong>&nbsp;"
            );
          }
        });
      }
    });
  }
};
</script>

<style>
</style>