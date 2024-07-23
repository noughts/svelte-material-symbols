<script lang="ts">
    import MaterialSymbol from "$lib/MaterialSymbol.svelte";
</script>

<div class="root">
    <div class="circle">
        <MaterialSymbol icon="check_circle" opacity={0.5} color="#ffffff" />
    </div>

    <div class="circle2">
        <div class="circleBg"></div>
        <MaterialSymbol icon="check_circle" color="red" />
    </div>

    <div class="simple">
        <MaterialSymbol icon="mood" fill />
        <span class="label">Label without Flexbox</span>
    </div>

    <div class="simple">
        <MaterialSymbol icon="mood" fill />
        <span class="label">Lorem ipsum dolor sit amet, consectetur adipiscing elit.</span>
    </div>

    <div class="pill">
        <MaterialSymbol icon="mood" fill />
        <div>Mood</div>
    </div>

    <div class="pill">
        <MaterialSymbol icon="home" fill />
        <div>Home</div>
    </div>
    <div class="pill">
        <MaterialSymbol icon="thumb_up" fill />
        <div>Like</div>
    </div>

    <div class="rating">
        <div class="starts">
            <MaterialSymbol icon="star" fill />
            <MaterialSymbol icon="star" fill />
            <MaterialSymbol icon="star" fill />
            <MaterialSymbol icon="star_half" fill />
            <MaterialSymbol icon="star" />
        </div>
        <div class="label">3.5</div>
    </div>
</div>

<style>
    .root {
        display: flex;
        flex-direction: column;
        align-items: flex-start;
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
            color: white;
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
        font-size: 24px;
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
