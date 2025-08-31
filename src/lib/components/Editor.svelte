<script lang="ts">
    import {onMount, onDestroy} from 'svelte';

    interface Props {
        language: string;
    }

    let {language}: Props = $props();

    let container: HTMLDivElement;
    let editor: import('monaco-editor').editor.IStandaloneCodeEditor | undefined;

    onMount(async () => {
        const monaco = await import('monaco-editor');
        await import('monaco-editor/min/vs/editor/editor.main.css');

        editor = monaco.editor.create(container, {
            value: '// Monaco in Svelte\n',
            language: language,
            theme: 'vs-light',
            automaticLayout: true,

            minimap: {enabled: false}
        });
    });

    onDestroy(() => editor?.dispose());
</script>

<style>
    .editor {
        width: 100%;
        height: 80vh;
    }
</style>

<div bind:this={container} class="editor"></div>
