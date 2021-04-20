<script lang="ts">
  import { onMount } from 'svelte';
  import type { editor } from 'monaco-editor';

  let container: HTMLElement;
  let editor: editor.IStandaloneCodeEditor;

  onMount(() => {
    import('monaco-editor').then((monaco) => {
      editor = monaco.editor.create(container, {
        language: 'typescript',
      });
    });
  });
</script>

<div bind:this={container} id="monaco-editor" />

<style>
  #monaco-editor {
    height: 80vh;
    width: 100%;
  }
</style>
