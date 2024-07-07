<script lang="ts">
    export let icon: string;
    export let fill: boolean = false;
    export let weight: number = 400; // 200 〜 700
    export let grade: -25 | 0 | 200 = 0;
    export let opticalSize: 20 | 24 | 40 | 48 = 24;
    export let color = "#000000";
    export let opacity: number = 1;

    $: options = [
        weight == 400 ? undefined : `wght${weight}`,
        grade == 0 ? undefined : `grad${grade}`,
        fill == false ? undefined : `fill1`,
    ].join("");
    $: ary = [icon, options.length > 0 ? options : "", `${opticalSize}px`].filter(
        (x) => x.length > 0,
    );
    $: filename = ary.join("_");
    $: src = `https://raw.githubusercontent.com/google/material-design-icons/master/symbols/web/${icon}/materialsymbolsrounded/${filename}.svg`;
</script>

<span
    class="root"
    style:-webkit-mask-image="url({src})"
    style:mask-image="url({src})"
    style:background-color={color}
    style:opacity
/>

<style>
    .root {
        all: unset;

        display: inline-block;
        vertical-align: -0.15em;

        /* レイアウトシフト防止 */
        width: 1em;
        height: 1em;

        /* 色 */
        -webkit-mask-size: contain;
        -webkit-mask-repeat: no-repeat;
        -webkit-mask-position: center;

        mask-size: contain;
        mask-repeat: no-repeat;
        mask-position: center;
    }
</style>
