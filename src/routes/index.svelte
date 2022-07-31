<script>
    import Svesh from "$lib/Svesh.svelte";

    const colors = ["#ef008f", "#6ec3f4", "#7038ff", "#ffba27"];
    const groupColors = true;
    const prefix = "g";
    const instances = 5;
    const width = 1920;
    const height = 600;
    const meshId = 666;
    const fixMeshId = true;
</script>

<Svesh {colors} {groupColors} {prefix} {instances} {width} {height} {meshId} {fixMeshId} />
