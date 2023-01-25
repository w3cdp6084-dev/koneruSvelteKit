<script lang="ts">
    import "../app.css";
    import Header from '../components/layouts/Header.svelte';
    import Footer from '../components/layouts/Footer.svelte';
    import { onMount } from 'svelte';
    let canvas;

    onMount(() => {
    const canvas = document.querySelector('canvas')
    , cx = canvas.getContext('2d')

    const INCREMENT = 12345
    , MULTIPLIER = 1103515245
    , MODULUS = Math.pow(2, 31)


    const stepX = 8
        , stepY = 8
        , sizeX = 1
        , sizeY = 1
        , marginTop = 0
        , marginBottom = 0
        , marginLeft = 0
        , marginRight = 0

    let frameID

    function lcg(x, c = INCREMENT, a = MULTIPLIER, m = MODULUS) {
    return (a * x + c) % m
    }

    function createRandom(initialSeed = 0) {
    let seed = initialSeed
    return {
        get currentSeed() {
        return seed
        },
        reset(newSeed) {
        seed = newSeed
        },
        get() {
        seed = lcg(seed)
        return seed / MODULUS
        }
    }
    }

    const random = createRandom()

    function frame(frameTime) {
    // First element
    cx.clearRect(0,0,cx.canvas.width,cx.canvas.height)
    for (let y = marginTop; y < cx.canvas.height - marginBottom; y += stepY) {
        random.reset(y)
        for (let x = marginLeft; x < cx.canvas.width - marginRight; x += stepX) {
        const randomValue = random.get()
        const distX = randomValue * 4
        const distY = randomValue * 4
        const phase = randomValue * Math.PI * 2
        cx.fillStyle = '#aaa'
        cx.fillRect(
            x, 
            y, 
            sizeX + Math.sin(phase + frameTime / 700) * distX,
            sizeY + Math.cos(phase + frameTime / 700) * distY
        )
        }
    }
    frameID = window.requestAnimationFrame(frame)
    }

    function resize() {
    canvas.width = canvas.clientWidth
    canvas.height = canvas.clientHeight
    }

    function start() {
        window.addEventListener('resize', resize)
        window.dispatchEvent(new Event('resize'))
        frameID = window.requestAnimationFrame(frame)
    }
start()
});
</script>

<div class="wrap">
<canvas
bind:this={canvas}
></canvas>
    <Header />
        <main class="l-content mt-24">
            <slot />
        </main>
    <Footer />
</div>
<style lang="postcss">
    .wrap{
        position: relative;
        width: 100%;
    }
    .l-content{
        position: relative;
        max-width: 1280px;
        margin: 0 auto;
    }
    canvas {
		width: 100%;
		min-height: 100vh;
    }
</style>