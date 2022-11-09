<script setup>
const date = ref(Date);
onMounted(() => {
    if (IVSPlayer.isPlayerSupported) {
        const player = IVSPlayer.create();
        player.attachHTMLVideoElement(document.getElementById("video-player"));
        player.load("https://3fc23fa3dfd6.us-east-1.playback.live-video.net/api/video/v1/us-east-1.612025208159.channel.NRAjrwcZ7JaY.m3u8");
        player.play();
    }
});
</script>
<template>
    <div>
        <Head>
            <Title>ivs-testing</Title>
            <Script src="https://player.live-video.net/1.11.0/amazon-ivs-player.min.js"></Script>
        </Head>
        <div style="position: fixed; right: 0; top: 0; color: aliceblue; font-size: 11px">SD</div>
        <video id="video-player" autoplay playsinline class="video-js" style="width: 100vw; height: 56.25vw"></video>
    </div>
</template>

<style>
body {
    overflow: hidden;
    margin: 0;
}
</style>
>
