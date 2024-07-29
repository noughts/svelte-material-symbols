<script lang="ts">
    import { onMount } from "svelte";

    export let icon: string;
    export let fill: boolean = false;
    export let weight: number = 400; // 200 〜 700
    export let grade: -25 | 0 | 200 = 0;
    export let opticalSize: 20 | 24 | 40 | 48 = 24;
    export let color: string = "#000000";
    export let darkColor: string = color; // ダークモード時の色を追加
    export let opacity: number = 1;
    export let size: number | undefined = undefined;

    let isDarkMode: boolean = false;

    function updateDarkMode(e: MediaQueryListEvent) {
        isDarkMode = e.matches;
    }

    onMount(() => {
        const darkModeQuery = window.matchMedia("(prefers-color-scheme: dark)");
        isDarkMode = darkModeQuery.matches;
        darkModeQuery.addEventListener("change", updateDarkMode);
        return () => {
            darkModeQuery.removeEventListener("change", updateDarkMode);
        };
    });

    $: options = [
        weight == 400 ? undefined : `wght${weight}`,
        grade == 0 ? undefined : `grad${grade}`,
        fill == false ? undefined : `fill1`
    ].join("");
    $: ary = [icon, options.length > 0 ? options : "", `${opticalSize}px`].filter(
        (x) => x.length > 0
    );
    $: filename = ary.join("_");
    $: src = `https://raw.githubusercontent.com/google/material-design-icons/master/symbols/web/${icon}/materialsymbolsrounded/${filename}.svg`;
</script>

<span
    class="root"
    style:-webkit-mask-image="url({src})"
    style:mask-image="url({src})"
    style:background-color={isDarkMode ? darkColor : color}
    style:opacity
    style:font-size={size ? `${size}px` : "1em"}
/>

<style>
    .root {
        all: unset;

        display: inline-block;
        vertical-align: -0.15em;
        pointer-events: none;

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
