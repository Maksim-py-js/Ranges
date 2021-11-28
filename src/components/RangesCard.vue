<template>
    <div class="ranges-card">
        <div class="ranges-card__title">
            forecasts
        </div>
        <Range :data="current_month"/>
        <Range :data="current_quarter"/>
    </div>
</template>

<script>
import Range from './ui-components/Range'
export default {
    components: {
        Range
    },
    data() {
        return {
            current_month: {
                label: 'Current Month',
                from: '1.6',
                to: '2.4',
                progress: 20,
                sections: [
                    {
                        bg: '#0B2035',
                        percent: 30
                    },
                    {
                        bg: '#256BFF',                        
                        percent: 40
                    },
                    {
                        bg: '#76C3F7',
                        percent: 30
                    }
                ]
            },
            current_quarter: {
                label: 'Current Quarter',
                from: '1.6',
                to: '2.4',
                progress: 40,
                sections: [
                    {
                        bg: '#0B2035',
                        percent: 15
                    },
                    {
                        bg: '#256BFF',                        
                        percent: 50
                    },
                    {
                        bg: '#76C3F7',
                        percent: 35
                    }
                ]
            }
        }
    }
}
</script>

<style lang="css">
    @import url('https://fonts.googleapis.com/css2?family=Roboto:wght@700&display=swap');
    .ranges-card {
        border-radius: 16px;
        background: #fafafa;
        box-shadow: 4px 4px 8px 0px rgba(34, 60, 80, 0.2);
        padding: 20px;
        margin: 20px;
        width: 100%;
        max-width: 320px;
    }
    .ranges-card__title {
        font-family: 'Roboto';
        font-style: normal;
        font-weight: 700;
        font-size: 30px;
        line-height: 35px;
        color: #0c0c0c;
        text-transform: uppercase;
        margin-bottom: 15px;
    }
</style>