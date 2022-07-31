<p align="center">
  <img alt="Svesh" src="static/mesh.png" />
</p>

# Svesh

Simple Svelte component library to easily use generated mesh gradients in your project.

## Installing

```bash
npm i --save-dev svesh
```

## Using

```svelte
<script>
    import { Svesh } from "svesh";
</script>

<Svesh />

```

## Advanced Usage

You can omit the default settings by setting props to Svesh:

```svelte
<script>
    import { Svesh } from "svesh";

    // default: random
    const colors = ["#ef008f", "#6ec3f4", "#7038ff", "#ffba27"];

    // default: false. If set to true then all instances will be same color
    const groupColors = true;
    
    // default: "g". Used by svesh as canva id with added meshId and its instance index;
    const prefix = "g";

    // default: 1. How many canvas instances you'd need to generate.
    const instances = 5;

    // these values are default. These properties are assigned to all instances.
    const width = 1920;
    const height = 600;
    
    // default: random. Use this to set static gradient.
    const meshId = 666;

    // default: false. Use this prevent other instances from generating their own meshId. Use this to set static gradient.
    const fixMeshId = true;
</script>

<Svesh {colors} {groupColors} {prefix} {instances} {width} {height} {meshId} {fixMeshId} />

```

Please, star this repo ;)

