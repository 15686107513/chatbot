<template>
    <div class="content">
        <div class="content-wrap">
            <img src="../../assets/result/unadd.png" class="content-unadd"/>
            <img src="../../assets/result/added.png" class="content-unadd"/>
            <div class="content-title">Hight quality or think through give more suggestion</div>
            <div class="content-info">
                <div class="content-sign">US9496517 B1</div>
                <img src="../../assets/result/country.png" class="content-img"/>
                <span>US</span>
                <div class="content-date">02/12/2021</div>
                <div class="content-name"> Justin </div>
            </div>
            <div class="content-detail">
                Aim to create small, focused pull requests that fulfill a single purpose. Smaller pull requests are easier and faster to review and merge, leave less room to introduce bugs, and provide a clearer history of changes. Aim to create small, focused pull requests that fulfill a single purpose. Smaller pull requests are easier and faster to review and merge, leave less room to introduce bugs, and provide a clearer history of changesAim to create small, focused pull requests that fulfill a single purpose. Smaller pull requests are easier and faster to review and merge, leave less room to introduce bugs, and provide a clearer history of changes
            </div>
        </div>
    </div>  
</template>

<style>
.content {
    padding: 20px 50px 0 100px;
    color: #000;
    .content-wrap {
        position: relative;
    }
    .content-unadd, .content-added {
        width: 24px;
        height: 24px;
        position: absolute;
        top: 50%;
        left: -60px;
    }
    .content-title {
        color: #171923;
        font-size: 20px;
        font-weight: 600;
    }
    .content-info {
        display: flex;
        margin-top: 5px;
        font-size: 14px;
    }
    .content-sign {
        color: #6149F8;
    }
    .content-img {
        width: 22px;
        height: 22px;
        margin-left: 6px;
    }
    .content-date {
        color: #171923;
        margin-left: 10px;
    }
    .content-name {
        color: #171923;
        margin-left: 10px;
    }
    .content-detail {
        word-break: break-all;
        display: -webkit-box;
        -webkit-line-clamp: 4;
        -webkit-box-orient: vertical;
        overflow: hidden;
        color: #6F7387;
        margin-top: 10px;
    }
}
</style>
