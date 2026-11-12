<template>
    <view class="userCenter">
        <view class="userCard">
            <view class=" user-box  ">
                <view class="user-img">
                    <u-avatar :src="pic" size="80"></u-avatar>                    
                </view>
                <view class="user-info">
                    <view class=" ">{{userName}}</view>
                    <view class="user-info-phone">{{phone}}</view>
                </view>
                <view class="sign">
                    <navigator url='/pages/index/index'><text>签到</text></navigator>
                </view>
                <view class="sign-icon">
                    <u-icon name="arrow-right" color="#fff" size="20"></u-icon>
                </view>
            </view>
            <view class="overview">
                <view class="view-item">
                    <view>{{revenue}}</view>
                    <view>累计收益</view>
                </view>
                <view class="view-item">
                    <view>{{orderTimes}}</view>
                    <view>回收次数</view>
                </view>
                <view class="view-item">
                    <view>{{totalScore}}</view>
                    <view>积分</view>
                </view>
            </view>
        </view>
        
        <view class="overview ">
            <u-cell-group>
                <u-cell icon="star" title="积分记录" isLink  :iconStyle="iconStyle"></u-cell>
                <u-cell icon="photo" title="兑换记录" isLink :iconStyle="iconStyle"></u-cell>
                <u-cell icon="coupon" title="我的贡献" isLink :iconStyle="iconStyle"></u-cell>
                <u-cell icon="heart" title="收入记录" isLink :iconStyle="iconStyle"></u-cell>
                <u-cell icon="setting" title="设置" isLink :iconStyle="iconStyle"></u-cell>
            </u-cell-group>
        </view>
    </view>
</template>

<script>    
    export default {
        data() {
            return {
                pic:'../../static/avatar.png',
                show:true,
                userName: '小甜鱼',
                phone: '',
                orderTimes: 23,
                revenue: 100,
                totalScore: 100,
                iconStyle:{
                padding: '8px 8px'
                }
            }
        },
        onLoad() {

        },
        methods: {

        }
    }
</script>

<style lang="scss">
page{
    background-color: #ededed;
}


.user-box{
    padding-top: 10px;
    color: #fff;
    display: flex;
    padding: 30 10 20 30;
    align-items: center;
}

.userCenter{
    box-sizing: border-box;
    padding: 0 15px;
    background-color: #fff;
    overflow: hidden;
}
.userCard{
    margin: 15px auto ;
    background-color: #71d9ca;
    border-radius: 10px;
    padding: 10px;
    margin-bottom: 0px;
}
.user-info{
    flex:1;
    font-size: 18px;
    margin-left: 15px;
}
.user-info-phone{
    font-size: 15px;
}
.sign{
    font-size: 15px;
    margin-right: 15px;
}

.overview{
    display: flex;
    align-items: center;
    padding-top: 15px;
}
.view-item{
    flex: 1;
    font-size: 16px;
    text-align: center;
    color: #fff;
    line-height: 24px;
}
.userDetail{
    padding-top: 20px;
    padding-bottom: 20px;
}
.iconStyle{
    padding-top: 50px;
}
</style>