<template>
	<view class="container">
		<!-- 头部轮播图 -->
		<view class="carousel-section">
			<!-- 标题栏和状态栏占位 -->
			<view class="titleView-placing"></view>
			
			<!-- 背景色区域 -->
			<view class="titleView-background"></view>
			<swiper class="carousel" circular indicator-dots autoplay="1500">
				<swiper-item v-for="(item, index) in carouselList" :key="index" class="carousel-item">
					<image :src="item.src" mode="widthFix" />
				</swiper-item>
			</swiper>
			<view class="carousel-nav-section">
				<view class="carousel-nav">
					<view class="carousel-nav-item" v-for="(item,index) in carouselNavList" :key="index">
						<image :src="item.pic" mode="aspectFit"></image>
						<text>{{item.title}}</text>
					</view>
				</view>
				<image src="../../static/temp/ad1.jpg"></image>
			</view>
		</view>
		
		<!-- 秒杀专区 -->
		<view class="seckill-section">
			<view class="seckillHead">
				<image src="../../static/temp/secskill-img.jpg" mode=""></image>
				<text class="xxxtime">8点场</text>
				<text class="time">07</text><text class="time">13</text><text class="time">55</text>
				<text class="right">></text>
			</view>
				<scroll-view scroll-x="true" style="white-space: nowrap;">
					<view class="seckill" v-for="(item,index) in goodsList" :key="index">
						<image :src="item.image" mode=""></image>
						<view class="title">{{item.title}}</view>
						<view class="price">¥ {{item.price}}</view>
					</view>
				</scroll-view>
		</view>
		
		<!-- 精品团购 -->
		<view class="groupBuying">
			<view class="groupHead">
				<view class="left">
					<image src="../../static/temp/h1.png" ></image>
					<view class="left-right">
						<text class="title">精品团购</text>
						<text class="subtitle">Boutique Group Buying</text>
					</view>
				</view>
				<view class="right"> > </view>
			</view>
			<scroll-view scroll-x="true" style="white-space: nowrap;">
				<view class="groupItem" v-for="(item, index) in goodsList" :key="index">
					<view v-if="index%2==0">
						<image :src="item.image3"></image>
						<view class="title">{{item.title}}</view>
						<view class="pri">
							<view class="price">¥ {{item.price}}</view>
							<view class="oriprice">¥ 9999</view>
						</view>
						<view class="pintuan">
							 <progress percent="70" activeColor="#FA436A" border-radius="6"/>
							 <text>6人成团</text>
						</view>
					</view>
					<view v-if="index%2==1">
						<view class="title">{{item.title}}</view>
						<view class="pri">
							<view class="price">¥ {{item.price}}</view>
							<view class="oriprice">¥ 9999</view>
						</view>
						<view class="pintuan">
							 <progress percent="70" activeColor="#FA436A" border-radius="6"/>
							 <text>6人成团</text>
						</view>
						<image :src="item.image"></image>
					</view>
				</view>
			</scroll-view>
		</view>
		
		<!-- 猜你喜欢 -->
		<view class="guessYou">
			<view class="groupHead">
				<view class="left">
					<image src="../../static/temp/h1.png" ></image>
					<view class="left-right">
						<text class="title">猜你喜欢</text>
						<text class="subtitle">Guess You Like It</text>
					</view>
				</view>
				<view class="right"> > </view>
			</view>
			<view class="guessSection">
				<view class="guessItem" v-for="(item, index) in goodsList" :key="index">
					<image :src="item.image"></image>
					<view class="title">{{item.title}}</view>
					<view class="price">¥{{item.price}}</view>
				</view>
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				carouselList: [{
						src: "../../static/temp/banner1.jpg"
					},
					{
						src: "../../static/temp/banner3.jpg"
					},
					{
						src: "../../static/temp/banner4.jpg"
					},
				],
				carouselNavList: [{
						title: "环球美食",
						pic: "../../static/temp/c3.png"
					},
					{
						title: "个护美妆",
						pic: "../../static/temp/c5.png"
					},
					{
						title: "营养保健",
						pic: "../../static/temp/c6.png"
					},
					{
						title: "家居厨卫",
						pic: "../../static/temp/c7.png"
					},
					{
						title: "速食生鲜",
						pic: "../../static/temp/c8.png"
					}
				],
				/* 商品列表 */
				goodsList: [{
						image: "https://timgsa.baidu.com/timg?image&quality=80&size=b9999_10000&sec=1553187020783&di=bac9dd78b36fd984502d404d231011c0&imgtype=0&src=http%3A%2F%2Fb-ssl.duitang.com%2Fuploads%2Fitem%2F201609%2F26%2F20160926173213_s5adi.jpeg",
						image2: "http://pic.rmb.bdstatic.com/819a044daa66718c2c40a48c1ba971e6.jpeg",
						image3: "http://img001.hc360.cn/y5/M00/1B/45/wKhQUVYFE0uEZ7zVAAAAAMj3H1w418.jpg",
						title: "古黛妃 短袖t恤女夏装2019新款韩版宽松",
						price: 179,
						sales: 61,
					},
					{
						image: "https://ss0.bdstatic.com/70cFvHSh_Q1YnxGkpoWK1HF6hhy/it/u=2501372545,1035168089&fm=15&gp=0.jpg",
						image2: "https://timgsa.baidu.com/timg?image&quality=80&size=b9999_10000&sec=1554013048&di=a3dc9fd1406dd7bad7fbb97b5489ec04&imgtype=jpg&er=1&src=http%3A%2F%2Fimg009.hc360.cn%2Fhb%2FnKo44ac2656F831c684507E3Da0E3a26841.jpg",
						image3: "http://img.zcool.cn/community/017a4e58b4eab6a801219c77084373.jpg",
						title: "潘歌针织连衣裙",
						price: 78,
						sales: 16,
					},
					{
						image: "https://ss0.bdstatic.com/70cFvHSh_Q1YnxGkpoWK1HF6hhy/it/u=1620020012,789258862&fm=26&gp=0.jpg",
						image2: "http://m.360buyimg.com/n12/jfs/t247/42/1078640382/162559/3628a0b/53f5ad09N0dd79894.jpg%21q70.jpg",
						image3: "https://ss0.bdstatic.com/70cFuHSh_Q1YnxGkpoWK1HF6hhy/it/u=751395366,442092706&fm=26&gp=0.jpg",
						title: "巧谷2019春夏季新品新款女装",
						price: 108.8,
						sales: 5,
					}, {
						image: "https://ss1.bdstatic.com/70cFuXSh_Q1YnxGkpoWK1HF6hhy/it/u=1666912511,1141903566&fm=26&gp=0.jpg",
						image2: "http://images.jaadee.com/images/201702/goods_img/30150_d85aed83521.jpg",
						image3: "http://img13.360buyimg.com/popWaterMark/jfs/t865/120/206320620/138889/dcc94caa/550acedcN613e2a9d.jpg",
						title: "私萱连衣裙",
						price: 265,
						sales: 88,
					}, {
						image: "https://img13.360buyimg.com/n8/jfs/t1/30343/20/1029/481370/5c449438Ecb46a15b/2b2adccb6dc742fd.jpg",
						image2: "https://timgsa.baidu.com/timg?image&quality=80&size=b9999_10000&sec=1553418265666&di=d4a7f7eb0ae3c859edeb921641ee1c3a&imgtype=0&src=http%3A%2F%2Fimg003.hc360.cn%2Fy3%2FM02%2FF8%2F9F%2FwKhQh1TuSkGELIlQAAAAAPuLl4M987.jpg",
						image3: "https://timgsa.baidu.com/timg?image&quality=80&size=b9999_10000&sec=1583590377750&di=db56936dcfe12de37cfb4a0ce2aae959&imgtype=0&src=http%3A%2F%2Fimg1.tbcdn.cn%2Ftfscom%2Fi2%2F1763640827%2FTB2z2BFXS_9F1JjSZFrXXcrVFXa_%2521%25211763640827.jpg",
						title: "娇诗茹 ulzzang原宿风学生潮韩版春夏短",
						price: 422,
						sales: 137,
					}, {
						image: "https://timgsa.baidu.com/timg?image&quality=80&size=b9999_10000&sec=1553187020783&di=bac9dd78b36fd984502d404d231011c0&imgtype=0&src=http%3A%2F%2Fb-ssl.duitang.com%2Fuploads%2Fitem%2F201609%2F26%2F20160926173213_s5adi.jpeg",
						image2: "http://image5.suning.cn/uimg/b2c/newcatentries/0070158827-000000000622091973_2_800x800.jpg",
						image3: "http://img.61ef.cn/news/201903/20/2019032009251784.jpg",
						title: "古黛妃 短袖t恤女夏装2019新款韩版宽松",
						price: 179,
						sales: 95,
					},
				]
			}
		},
		onLoad() {

		},
		methods: {

		}
	}
</script>

<style lang="scss">
	page {
		background: #f5f5f5;
	}

	.container {
		justify-content: center;
	}

	// 轮播图
	.carousel {
		height: 350upx;

		image {
			width: 100%;
			border-radius: 3px;
		}
	}

	//轮播图导航
	.carousel-nav-section {
		background: #fff;

		image {
			width: 100%;
			height: 200upx;
		}

		.carousel-nav {
			display: flex;
			justify-content: space-around;
			padding: 30upx 26upx;

			.carousel-nav-item {
				width: 15%;
				flex-direction: column;
				font-size: 26upx;
				text-align: center;

				image {
					width: 88upx;
					height: 88upx;
					margin-bottom: 14upx;
					border-radius: 50%;
					opacity: .7;
					box-shadow: 4upx 4upx 20upx rgba(250, 67, 106, 0.3);
				}
			}
		}
	}

	// 秒杀专区
	.seckill-section {
		margin-top: 20upx;
		background: #fff;
		padding: 20upx;
		color: #666;
		font-size: 30upx;

		.seckillHead {
			display: flex;
			align-items: center;
			margin-bottom: 20upx;
			image {
				width: 20%;
				height: 30upx;
			}

			.xxxtime {
				margin: 0 20upx 0 30upx;
			}

			.time {
				margin-left: 10upx;
				color: #fff;
				background: black;
				padding: 5upx;
			}

			.right {
				flex: 1;
				text-align: right;
			}
		}
		.seckill{
			display: inline-block;
			width:150upx;
			margin-right:20upx;
			image{
				width:150upx;
				height:150upx;
				border-radius: 5upx;
			}
			.title{
				overflow: hidden;
				text-overflow: ellipsis;
				font-size: 24upx;
			}
			.price{
				color:#DD524D;
				font-size: 24upx;
			}
		}
	}
	
	// 精品团购
	.groupBuying{
		margin-top:20upx;
		padding: 30upx;
		background: #fff;
		.groupHead{
			display: flex;
			justify-content: space-between;
			align-items: center;
			margin-bottom:20upx;
			.left{
				display: flex;
				image{
					width:88upx;
					height:88upx;
					margin-right: 20upx;
				}
				.left-right{
					display: flex;
					flex-direction: column;
					.title{
						font-size: 36upx;
					}
					.subtitle{
						font-size: 24upx;
						color:#666;
					}
				}
			}
		}
		.groupItem{
			width:300upx;
			display: inline-block;
			margin-right: 20upx;
			view{
				image{
					width:100%;
					height:350upx;
				}
				.title{
					overflow: hidden;
					text-overflow: ellipsis;
					font-size: 32upx;
				}
				.pri{
					display: flex;
					font-size: 28upx;
					.price{
						color:#DD524D;
					}
					.oriprice{
						margin-left: 10upx;
						text-decoration: line-through;
						color:#666; 
					}
				}
				.pintuan{
					text-wrap: nowrap;
					progress{
						width:65%;
						display: inline-block;
					}
					text{
						margin-left:10upx;
						font-size: 24upx;
					}
				}
			}
		}
	}

	// 猜你喜欢
	.guessYou{
		margin-top:20upx;
		padding: 30upx;
		background: #fff;
		.groupHead{
			display: flex;
			justify-content: space-between;
			align-items: center;
			margin-bottom:20upx;
			.left{
				display: flex;
				image{
					width:88upx;
					height:88upx;
					margin-right: 20upx;
				}
				.left-right{
					display: flex;
					flex-direction: column;
					.title{
						font-size: 36upx;
					}
					.subtitle{
						font-size: 24upx;
						color:#666;
					}
				}
			}
		}
		.guessSection{
			display: flex;
			flex-wrap: wrap;
			padding:0 30upx;
			.guessItem{
				display: flex;
				flex-direction: column;
				width: 48%;
				padding-bottom: 40upx;
				&:nth-child(2n+1){
					margin-right:4%;
				}
			}
			image{
				width:100%;
				height: 330upx;
				border-radius: 3px;
				overflow: hidden;
			}
			.title{
				font-size:32upx;
				color:#333333;
				line-height: 80upx;
				overflow: hidden;
				text-overflow: ellipsis;
				white-space: nowrap;
			}
			.price{
				font-size:32upx;
				color:#DD524D;
			}
		}
	}
</style>
