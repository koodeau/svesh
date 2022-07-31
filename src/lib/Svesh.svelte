<script>  
    import { randomColor } from "./utils/randomColor";
    import { Gradient } from "./webgl";
    import { onMount } from "svelte";
  

    export let colors = [randomColor(), randomColor(), randomColor(), randomColor()];
    export let groupColors = false;
    export let prefix = "g";
    export let instances = 1
    export let width = 1920;
    export let height = 600;
    export let meshId = Math.floor(Math.random() * 1000);
    export let fixMeshId = false;
    export let identifier = "svesh";

    onMount(() => {
      const mesh = []
      // const colors = [randomColor(), randomColor(), randomColor(), randomColor()];
      for (let index = 0; index < instances; index++) {
        const id = fixMeshId ? meshId : Math.floor(Math.random() * 1000);
        const div = document.querySelector(`#${identifier}`)
        const canvas = document.createElement("canvas");
        canvas.id = `${prefix}-${identifier}-${index+id}`;
        mesh.push(canvas.id);
        canvas.setAttribute("data-transition-in", "");
        div.appendChild(canvas);
        // gradient.changeGradientColors(colors)
        // gradient.changePosition(Math.floor(Math.random() * 1000));
      }
      for (let index = 0; index < mesh.length; index++) {
        const useColors = groupColors ? colors : [randomColor(), randomColor(), randomColor(), randomColor()];
        // const colors = ["#ef008f", "#6ec3f4", "#7038ff", "#ffba27"]
        const id = fixMeshId ? meshId : Math.floor(Math.random() * 1000);
        const gradient = new Gradient();
        gradient.initGradient("#"+mesh[index], useColors);
        gradient.changeGradientColors(useColors)
        gradient.changePosition(id);
  
        const canvas = document.getElementById(mesh[index]);

        canvas.width = width;
        canvas.height = height;
        gradient.setCanvasSize(width, height, false);
        gradient.reGenerateCanvas();
  
        // const outerHTML = canvas.outerHTML,
        //   blob = new Blob([outerHTML],{type:'image/svg+xml;charset=utf-8'});
        //   console.log(outerHTML)
        // const blobURL = URL.createObjectURL(blob);
        // console.log(blob)
        // const image = new Image();
        // image.src = blobURL;
  
        // console.log(image.src+".svg")
      }
    });
  </script>
  
  <div id={identifier}>
  </div>
  
  <style>
    .svesh {
      width: 100%;
      height: 100%;
      display: flex;
      flex-direction: column;
    }
  </style>
  