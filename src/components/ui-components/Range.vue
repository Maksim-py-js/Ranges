<template>
    <div class="range-slider">
        <div class="range-slider__label">{{ data.label }}</div>
        <div class="range-slider__wrapper">
            <div class="range-slider__sections">
                <div 
                    class="range-slider__section"
                    v-for="(section, index) in data.sections"
                    :key="index"
                    :style="
                        'background:' + section.bg + ';' +
                        'width:' + section.percent + '%;'
                    "
                    ></div>
            </div>
            <div class="range-slider__progress-line">
                <span :style="'width:' + data.progress + '%;'"></span>
                <svg :style="'left:' + data.progress + '%;'" width="80" height="80" viewBox="0 0 80 80" fill="none" xmlns="http://www.w3.org/2000/svg">
                    <path d="M0 0L80 40L0 80L33.5 40L0 0Z" fill="white"/>
                </svg>
            </div>
        </div>        
        <div class="d-flex content-between">
            <div class="range-slider__from">${{ data.from }}k</div>
            <div class="range-slider__to">${{ data.to }}k</div>
        </div>
    </div>
</template>

<script>
export default {
    props: ['data']
}
</script>

<style lang="css">
    @import url('https://fonts.googleapis.com/css2?family=Roboto&display=swap');
    .d-flex {
        display: flex;
    }
    .content-between {
        justify-content: space-between;
    }
    .range-slider__label {
        font-family: 'Roboto';
        font-style: normal;
        font-weight: normal;
        font-size: 20px;
        line-height: 35px;
        color: #0c0c0c;
        margin-bottom: 15px;
    }
    .range-slider__wrapper {
        position: relative;
    }
    .range-slider__sections {
        display: flex;
    }
    .range-slider__section {
        width: 200px;
        height: 15px;
    }
    .range-slider__section:first-child {
        border-radius: 10px 0 0 10px;
    }
    .range-slider__section:last-child {
        border-radius: 0 10px 10px 0;
    }
    .range-slider__progress-line {
    }
    .range-slider__progress-line span {
        position: absolute;
        top: 50%;
        width: 500px;
        border:none;
        border-top: 1px dashed #fff;
    }
    .range-slider__progress-line svg {
        position: absolute;
        top: calc(10% + 1px);
        left: 500px;
        width: 10px;
        height: 10px;
    }
    .range-slider__from, 
    .range-slider__to {
        font-family: 'Roboto';
        font-style: normal;
        font-weight: normal;
        font-size: 16px;
        line-height: 20px;       
        color: #0c0c0c;
        margin-top: 15px;
    }
</style>