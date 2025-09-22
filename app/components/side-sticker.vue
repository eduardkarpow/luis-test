<script lang="ts" setup>
    const BASE_URL = 'https://cataas.com/cat?_t=';
    const ImagesToFetch: string[] = [];
    for(let i = 0; i < 3; i++) {
        ImagesToFetch.push(BASE_URL + Date.now() + i);
    }
</script>

<template>
    <div class="container">
        <h2 class="title">Консультация<br> эксперта</h2>
        <div class="images">
            <div class="image__item" v-for="(url, index) in ImagesToFetch" :key="index">
                <img :src="url" :alt="'cat'+index"></img>
            </div>
            
        </div>
        
        <app-arrow class="arrow" />
        <button class="button">Получить Консультацию</button>
    </div>
</template>

<style lang="scss" scoped>
.container {
    position: fixed;
    top: calc(50vh - 133px);
    bottom: 50vh;
    right: 0;
    height: 266px;
    width: 68px;
    padding: 0 2px;
    background-color: #F4F6F9;
    border-radius: 14px 0 0 14px;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
}

.title {
    font-weight: 600;
    font-size: 23px;
    color: #333333;
    text-align: center;
    margin-top: 16px;
    position: absolute;
    opacity: 0;
}

.images {
    width: 64px;
    height: 152px;
    margin-top: 24px;
    margin-bottom: 32px;
    display: flex;
    flex-direction: column;
}

.images>.image__item {
    width: 58px;
    height: 58px;
    border: 3px solid #F4F6F9;
    border-radius: 16px;
    margin-top: -20px;
}
.image__item>img {
    width: 100%;
    height: 100%;
    border-radius: 16px;
}


.images>.image__item:first-child {
    margin-top: 0;
}

.container:hover>.images>.image__item {
    margin-top: 0;
}

.button {
    border-radius: 6px;
    padding: 20px 24px;
    background-color: #fff;
    font-size: 16px;
    font-weight: 500;
    border: none;
    color: #333333;
    cursor: pointer;
    position: absolute;
    opacity: 0;
    box-shadow: 0px 4px 20px 0px #7373731A;
}

.arrow {
    margin: 0 auto;
    cursor: pointer;
}

.container:hover {
    animation-name: body-animation;
    animation-duration: .4s;
    animation-iteration-count: 1;
    animation-fill-mode: forwards;
}

.container:hover>.title {
    animation-name: title-animation;
    animation-duration: .4s;
    animation-iteration-count: 1;
    animation-fill-mode: forwards;
}

.container:hover>.images {
    animation-name: images-animation;
    animation-duration: .4s;
    animation-iteration-count: 1;
    animation-fill-mode: forwards;
    margin-bottom: 16px;
    margin-top: 16px;
    margin-left: 11px;
}

.container:hover>.images>.image__item:first-child {
    animation-name: first-image-animation;
    animation-duration: .4s;
    animation-iteration-count: 1;
    animation-fill-mode: forwards;
}

.container:hover>.images>.image__item:nth-child(2) {
    animation-name: second-image-animation;
    animation-duration: .4s;
    animation-iteration-count: 1;
    animation-fill-mode: forwards;
}

.container:hover>.images>.image__item:last-child {
    animation-name: last-image-animation;
    animation-duration: .4s;
    animation-iteration-count: 1;
    animation-fill-mode: forwards;
}

.container:hover>.button {
    animation-name: title-animation;
    animation-duration: .4s;
    animation-iteration-count: 1;
    animation-fill-mode: forwards;
}

.container:hover>.arrow {
    display: none;
}

@keyframes title-animation {
    80% {
        position: absolute;
        opacity: 0;
    }

    100% {
        position: relative;
        opacity: 1;
    }
}

@keyframes body-animation {
    50% {
        width: 68px;
    }

    80% {
        width: 280px;
    }

    100% {
        width: 280px;
    }
}

@keyframes images-animation {
    90% {
        flex-direction: column;
    }

    80% {
        width: 64px;
        height: 152px;
    }

    100% {
        width: 170px;
        height: 64px;
        flex-direction: row;
    }
}

@keyframes first-image-animation {
    20% {
        transform: translateY(58px);
        opacity: 1;
    }

    30% {
        opacity: 0;
    }

    90% {
        opacity: 0;
    }

    100% {
        opacity: 1;
    }
}

@keyframes second-image-animation {
    20% {
        opacity: 1;
    }

    30% {
        opacity: 0;

    }

    80% {
        opacity: 0;
        margin-left: 0;
    }

    90% {
        opacity: 0;
        margin-left: -11px;
    }

    100% {
        opacity: 1;
        margin-left: -11px;
    }
}

@keyframes last-image-animation {
    20% {
        transform: translateY(-58px);
        opacity: 1;
    }

    30% {
        opacity: 0;
    }

    80% {
        opacity: 0;
        margin-left: 0;
    }

    90% {
        opacity: 0;
        margin-left: -11px;
    }

    100% {
        opacity: 1;
        margin-left: -11px;
    }
}
</style>