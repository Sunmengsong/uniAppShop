<template>
	<view>
		<!-- 轮播图 -->
		<view class="carousel">
			<swiper indicator-dots circular=true duration="400">
				<swiper-item class="swiper-item" v-for="(item,index) in imgList" :key="index">
					<view class="image-wrapper">
						<image :src="item.src" class="loaded" mode="aspectFill"></image>
					</view>
				</swiper-item>
			</swiper>
		</view>
		<!-- 商品信息 -->
		<view class="product-section">
			<view class="title">恒源祥2019春季长袖白色T恤 新款春装</view>
			<view class="pri">
				<text class="price">¥ 999.99</text>
				<text class="orig">¥ 9999.99</text>
				<text class="discount">7折</text>
			</view>
			<view class="proStatus">
				<text>销量:199</text>
				<text>库存:9999</text>
				<text>浏览量:6666</text>
			</view>
		</view>
		<!-- 规格及活动 -->
		<view class="c-list">
			<view class="c-row">
				<text class="tit">购买类型</text>
				<view class="con">
					<text class="selected-text">
						S 珊瑚粉
					</text>
				</view>
			</view>
			<view class="c-row">
				<text class="tit">优惠券</text>
				<text class="con red">领取优惠券</text>
			</view>
			<view class="c-row">
				<text class="tit">促销活动</text>
				<view class="con-list">
					<text>新人首单送20元无门槛代金券</text>
					<text>订单满50减10</text>
					<text>订单满100减30</text>
					<text>单笔购买满两件免邮费</text>
				</view>
			</view>
			<view class="c-row">
				<text class="tit">服务</text>
				<view class="con">
					<text>7天无理由退换货 ·</text>
					<text>假一赔十 ·</text>
				</view>
			</view>
		</view>
		<!-- 评价 -->
		<view class="eval-section">
			<view class="eval-head">
				<view>
					评价 <text class="totalNum">(86)</text>
				</view>
				<text class="totalNum">好评率 100%</text>
			</view>
			<view class="eval">
				<image src="http://img5.imgtn.bdimg.com/it/u=2471723103,4261647594&fm=26&gp=0.jpg"></image>
				<view class="right">
					<text class="nickName">我是一只笨笨鸭</text>
					<text class="evalText">商品收到了, 真的超好看, 质量非常不错, 试穿之后发现自己又漂亮了许多, 客服也很给力,回答了好多问题!</text>
					<view class="time">
						<text>购买类型: XL 红色</text>
						<text>2020-02-24 22:22</text>
					</view>
				</view>
			</view>
		</view>
		<!-- 图文详情 -->
		<view class="detail-desc">
			<view class="d-header">
				<text>图文详情</text>
			</view>
			<rich-text :nodes="desc"></rich-text>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				specClass: 'none',
				specSelected: [],
				favorite: true,
				shareList: [],
				imgList: [{
						src: 'https://gd3.alicdn.com/imgextra/i3/0/O1CN01IiyFQI1UGShoFKt1O_!!0-item_pic.jpg_400x400.jpg'
					},
					{
						src: 'https://gd3.alicdn.com/imgextra/i3/TB1RPFPPFXXXXcNXpXXXXXXXXXX_!!0-item_pic.jpg_400x400.jpg'
					},
					{
						src: 'https://gd2.alicdn.com/imgextra/i2/38832490/O1CN01IYq7gu1UGShvbEFnd_!!38832490.jpg_400x400.jpg'
					}
				],
				desc: `
				              <div style="width:100%">
				                <img style="width:100%;display:block;" src="https://gd3.alicdn.com/imgextra/i4/479184430/O1CN01nCpuLc1iaz4bcSN17_!!479184430.jpg_400x400.jpg" />
				                <img style="width:100%;display:block;" src="https://gd2.alicdn.com/imgextra/i2/479184430/O1CN01gwbN931iaz4TzqzmG_!!479184430.jpg_400x400.jpg" />
				                <img style="width:100%;display:block;" src="https://gd3.alicdn.com/imgextra/i3/479184430/O1CN018wVjQh1iaz4aupv1A_!!479184430.jpg_400x400.jpg" />
				                <img style="width:100%;display:block;" src="https://gd4.alicdn.com/imgextra/i4/479184430/O1CN01tWg4Us1iaz4auqelt_!!479184430.jpg_400x400.jpg" />
				                <img style="width:100%;display:block;" src="https://gd1.alicdn.com/imgextra/i1/479184430/O1CN01Tnm1rU1iaz4aVKcwP_!!479184430.jpg_400x400.jpg" />
				              </div>
				            `,
				specList: [{
						id: 1,
						name: '尺寸',
					},
					{
						id: 2,
						name: '颜色',
					},
				],
				specChildList: [{
						id: 1,
						pid: 1,
						name: 'XS',
					},
					{
						id: 2,
						pid: 1,
						name: 'S',
					},
					{
						id: 3,
						pid: 1,
						name: 'M',
					},
					{
						id: 4,
						pid: 1,
						name: 'L',
					},
					{
						id: 5,
						pid: 1,
						name: 'XL',
					},
					{
						id: 6,
						pid: 1,
						name: 'XXL',
					},
					{
						id: 7,
						pid: 2,
						name: '白色',
					},
					{
						id: 8,
						pid: 2,
						name: '珊瑚粉',
					},
					{
						id: 9,
						pid: 2,
						name: '草木绿',
					},
				]
			}
		},
		onLoad(option) {
			uni.showToast({
				title: `id为${option.id}的详情页`,
				icon: 'none'
			})
		},
		methods:{
		}
	}
</script>

<style lang="scss">
	page {
		background: #f5f5f5;
	}
	// 轮播图
	.carousel {
		height: 722upx;
		position: relative;

		swiper {
			height: 100%;
		}

		.image-wrapper {
			width: 100%;
			height: 100%;
		}

		.swiper-item {
			display: flex;
			justify-content: center;
			align-content: center;
			height: 750upx;
			overflow: hidden;

			image {
				width: 100%;
				height: 100%;
			}
		}

	}
	// 商品信息
	.product-section{
		background:#fff;
		padding:20upx 30upx;
		.title{
			font-size: 32upx;
			margin-bottom: 20upx;
		}
		.pri{
			padding-bottom: 20upx;
			.price{
				color:red;
				font-size:32upx;
				margin-right:10upx;
			}
			.orig{
				color:gray;
				font-size:26upx;
				text-decoration: line-through;
				margin-right: 10upx;
			}
			.discount{
				display: inline-block;
				padding:2upx 4upx;
				border-radius: 8upx;
				background:red;
				color:#fff;
				font-size:26upx;
			}
		}
		.proStatus{
			font-size:26upx;
			color:gray;
			text{
				margin-right:70upx;
			}
		}
	}
	// 规格列表
	.c-list{
		font-size: 28upx;
		color: #000;
		background: #fff;
		.c-row{
			display:flex;
			align-items:center;
			padding: 20upx 30upx;
			position:relative;
			border-bottom: 1px solid rgba(0,0,0,.1);
		}
		.tit{
			width: 140upx;
		}
		.con{
			flex: 1;
			color: #000;
			.selected-text{
				margin-right: 10upx;
			}
		}
		.bz-list{
			height: 40upx;
			font-size: 28upx;
			color: #000;
			text{
				display: inline-block;
				margin-right: 30upx;
			}
		}
		.con-list{
			flex: 1;
			display:flex;
			flex-direction: column;
			color: #000;
			line-height: 40upx;
		}
		.red{
			color: red;
		}
	}
	// 评价区域
	.eval-section{
		margin-top: 20upx;
		background:#fff;
		padding:40upx 30upx;
		.eval-head{
			display: flex;
			justify-content: space-between;
			font-size: 28upx;
			.totalNum{
				color:gray;
				font-size:26upx;
			}
		}
		.eval{
			display: flex;
			flex-grow: 1;
			image{
				width: 202upx;
				height: 80upx;
				border-radius: 50%;
			}
			.right{
				margin-left: 30upx;
				display: flex;
				flex-direction: column;
				.nickName{
					color:gray;
					padding:30upx 0;
				}
				.evalText{
					font-seze:26upx;
					margin-bottom: 30upx;
				}
				.time{
					color:#999999;
					display: flex;
					justify-content: space-between;
					font-size: 24upx;
				}
			}
		}
	}
	/*  详情 */
	.detail-desc{
		background: #fff;
		margin-top: 16upx;
		.d-header{
			display: flex;
			justify-content: center;
			align-items: center;
			height: 80upx;
			font-size: 32upx;
			color: #000;
			position: relative;
				
			text{
				padding: 0 20upx;
				background: #fff;
				position: relative;
				z-index: 1;
			}
			&:after{
				position: absolute;
				left: 50%;
				top: 50%;
				transform: translateX(-50%);
				width: 300upx;
				height: 0;
				content: '';
				border-bottom: 1px solid #ccc; 
			}
		}
	}
</style>
