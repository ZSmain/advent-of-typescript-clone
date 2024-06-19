<script lang="ts">
    import { onMount } from "svelte";
    import "$lib/monaco/index";
    import * as monaco from "monaco-editor";

    let container: HTMLDivElement;

    const value = `
        function hello() {
            alert("Hello, World!");
        }
    `;

    onMount(() => {
        const myEditor = monaco.editor.create(container, {
            value,
            language: "javascript",
            automaticLayout: true,
        });
    });
</script>

<div bind:this={container}></div>

<style>
    html,
    body {
        margin: 0;
        padding: 0;
    }
    div {
        width: 100vw;
        height: 100vh;
    }
</style>
