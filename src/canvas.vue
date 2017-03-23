<template>
    <body>
        <div>
            <canvas width="300" height="150" style="border:1px solid #BBB;" v-insert-message="exampleContent"></canvas>
            <input type="text" v-model="exampleContent" />
            <span>{{ exampleContent }}</span>
        </div>
    </body>
</template>

<script>
  let model = { exampleContent: 'vue' }
  export default {
    directives: {
            replace: false,
            insertMessage: function() {
                var canvasElement = this.el;
                var ctx = canvasElement.getContext("2d");
                ctx.clearRect(0, 0, 300, 150);
                ctx.fillStyle = "black";
                ctx.font = "20px Georgia";
                ctx.fillText(model.exampleContent, 10, 50);
            }
        },
  	data() {
      return model;
    },
  }
</script>