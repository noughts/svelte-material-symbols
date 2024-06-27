<script context="module">
    let linkTagInserted = false;
</script>

<script lang="ts">
    export let icon: string;
    export let opacity: number = 1;
    export let fill: boolean = false;
    export let weight: number = 400; // 200 〜 700
    export let grade: -25 | 0 | 200 = 0;
    export let opticalSize: 20 | 24 | 40 | 48 = 24;

    let shouldInsertLinkTag = !linkTagInserted;
    linkTagInserted = true;

    $: style = `
        font-variation-settings:
            'FILL' ${fill ? 1 : 0},
            'wght' ${weight},
            'GRAD' ${grade},
            'opsz' ${opticalSize};
        `;
</script>

<svelte:head>
    {#if shouldInsertLinkTag}
        <!-- &display=block を指定することで、ロード中のアイコン名の表示を抑制できます -->
        <link
            href="https://fonts.googleapis.com/css2?family=Material+Symbols+Rounded:opsz,wght,FILL,GRAD@20..48,100..700,0..1,-50..200&display=block"
            rel="stylesheet"
        />
    {/if}
</svelte:head>

<span style:opacity {style} class="material-symbols-rounded root">{icon}</span>

<style>
    .root {
        font-size: 1em;
        line-height: 1;
        overflow: hidden;
        vertical-align: -0.15em;

        /* レイアウトシフト防止 */
        width: 1em;
    }
</style>
