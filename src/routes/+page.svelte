<script lang="ts">
    import MaterialSymbol from "$lib/MaterialSymbol.svelte";
</script>

<div class="root">
    <MaterialSymbol icon="check_circle" size={24} color="purple" />

    <div class="circle">
        <MaterialSymbol icon="check_circle" opacity={0.5} color="#ffffff" />
    </div>

    <div class="circle2">
        <div class="circleBg"></div>
        <MaterialSymbol icon="check_circle" color="red" />
    </div>

    <div class="simple">
        <MaterialSymbol icon="mood" fill color="var(--text-color)" />
        <span class="label">Label without Flexbox</span>
    </div>

    <div class="simple">
        <MaterialSymbol icon="mood" fill color="var(--text-color)" />
        <span class="label">Lorem ipsum dolor sit amet, consectetur adipiscing elit.</span>
    </div>

    <div class="simple">
        <MaterialSymbol icon="mood" fill color="var(--key-color)" />
        <span class="label">I'm always green</span>
    </div>

    <div class="pill">
        <MaterialSymbol icon="mood" fill color="var(--text-color)" />
        <div>Mood</div>
    </div>

    <div class="pill">
        <MaterialSymbol icon="home" fill color="var(--text-color)" />
        <div>Home</div>
    </div>
    <div class="pill">
        <MaterialSymbol icon="thumb_up" fill color="var(--text-color)" />
        <div>Like</div>
    </div>

    <div class="rating">
        <div class="starts">
            <MaterialSymbol icon="star" fill color="var(--text-color)" />
            <MaterialSymbol icon="star" fill color="var(--text-color)" />
            <MaterialSymbol icon="star" fill color="var(--text-color)" />
            <MaterialSymbol icon="star_half" fill color="var(--text-color)" />
            <MaterialSymbol icon="star" color="var(--text-color)" />
        </div>
        <div class="label">3.5</div>
    </div>
</div>

<style>
    :root {
        --text-color: #333333;
        --key-color: green;
    }
    @media (prefers-color-scheme: dark) {
        :root {
            --text-color: #eeeeee;
        }
    }
    .root {
        color-scheme: light dark;
        display: flex;
        flex-direction: column;
        align-items: flex-start;
        color: var(--text-color);
        width: 320px;
        gap: 16px;
        padding: 16px;
        font-family:
            system-ui,
            -apple-system,
            BlinkMacSystemFont,
            "Segoe UI",
            Roboto,
            Oxygen,
            Ubuntu,
            Cantarell,
            "Open Sans",
            "Helvetica Neue",
            sans-serif;
    }
    @media (prefers-color-scheme: dark) {
        .root {
            background-color: #333;
        }
    }
    .simple {
        font-size: 22px;
    }
    .circle {
        background-color: red;
        color: white;
        display: flex;
        align-items: center;
        justify-content: center;
        width: 32px;
        height: 32px;
        border-radius: 50%;
        font-size: 24px;
    }
    .circle2 {
        position: relative;
        width: 44px;
        height: 44px;
        display: flex;
        align-items: center;
        justify-content: center;
        border-radius: 50%;
        overflow: hidden;
        font-size: 32px;
        color: red;
    }
    .circleBg {
        position: absolute;
        inset: 0;
        background-color: red;
        opacity: 0.2;
    }
    .pill {
        display: flex;
        align-items: center;
        font-size: 32px;
        font-weight: 500;
        gap: 4px;
        line-height: 1;
        background-color: rgba(0 0 0/20%);
        padding: 8px;
        padding-right: 14px;
        border-radius: 20px;
    }
    .rating {
        display: flex;
        gap: 4px;
        font-size: 15px;
        align-items: center;
        line-height: 1;
        & .starts {
            display: flex;
            gap: 0;
        }
    }
</style>
