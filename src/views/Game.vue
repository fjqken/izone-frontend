<template>
    <div class="box">
    <div class="app" :style="size">
        <div class="rect" :class="drop?'drop':''">
            <Decorate/>
            <div class="screen">
                <div class="panel">
                    <Matrix :propMatrix="matrix" :cur="cur" :reset="reset" />
                    <Logo :cur="!!cur" :reset="reset" />
                    <div class="state">
                        <Point :cur="!!cur" :max="max" :point="points" />
                        <p>{{pContent}}</p>
                        <Number :number='cur ? clearLines : startLines' />
                        <p>{{level}}</p>
                        <Number :number='cur?speedRun:speedStart' :length="1" />
                        <p>{{nextText}}</p>
                        <Next :data="next" />
                        <div class="bottom">
                            <Music :data="music" />
                            <Pause :data="pause" />
                            <Number :propTime="true" />
                        </div>
                    </div>
                </div>
            </div>
        </div>
        <Keyboard :filling='filling' />
        <Guide/>
    </div>
    </div>
</template>

<style lang="less">
    @import '../app.less';
    @import '../loader.less';
    html,body{
        height:100%;
        font-size:14px;
    }
    .box{
        position:absolute;
        width:100%;
        height:100%;
        overflow:hidden;
        background:#009688 !important;;
    }
</style>

<script src="../app.js"></script>

