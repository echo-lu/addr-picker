<template>
	<div>
		<b-form-select  v-model="province" :options="provinceOpt" class="mb-3 col-sm-2" :value ="changeCity"/>
		<b-form-select  v-model="city" :options="cityOpt" class="mb-3 col-sm-2"  />
<!-- 		<div>Selected: <strong>{{ province }} - {{city}}</strong></div> -->
	</div>
</template>

<script>
const response = require('./data.json');
export default {
	created () {
		for(let i=0;i<response.length;i++) {
			// console.log(response[i].name);
			this.provinceOpt.push(response[i].name)
		}
	},
	data () {
		return {
			city: null,
			province: "",
			provinceOpt: [],
			cityOpt:[]
		}
	},
	computed : {
		changeCity () {
			// alert(this.province);
			this.cityOpt = [];
			this.city = "";
			var pro = this.province;
			var optinsValue;
			switch(pro){
				case "北京市":
				optinsValue = response[0].北京市;
				break;
				case "天津市":
				optinsValue = response[1].天津市;
				break;
				case "河北省":
				optinsValue = response[2].河北省;
				break;
				case "山西省":
				optinsValue = response[3].山西省;
				break;
				case "内蒙古自治区":
				optinsValue = response[4].内蒙古自治区;
				break;
				case "辽宁省":
				optinsValue = response[5].辽宁省;
				break;
				case "吉林省":
				optinsValue = response[6].吉林省;
				break;
				case "黑龙江省":
				optinsValue = response[7].黑龙江省;
				break;
				case "上海市":
				optinsValue = response[8].上海市;
				break;
				case "江苏省":
				optinsValue = response[9].江苏省;
				break;
				case "浙江省":
				optinsValue = response[10].浙江省;
				break;
				case "安徽省":
				optinsValue = response[11].安徽省;
				break;
				case "福建省":
				optinsValue = response[12].福建省;
				break;
				case "江西省":
				optinsValue = response[13].江西省;
				break;
				case "山东省":
				optinsValue = response[14].山东省;
				break;
				case "河南省":
				optinsValue = response[15].河南省;
				break;
				case "湖北省":
				optinsValue = response[16].湖北省;
				break;
				case "湖南省":
				optinsValue = response[17].湖南省;
				break;
				case "广东省":
				optinsValue = response[18].广东省;
				break;
				case "广西壮族自治区":
				optinsValue = response[19].广西壮族自治区;
				break;
				case "海南省":
				optinsValue = response[20].海南省;
				break;
				case "重庆市":
				optinsValue = response[21].重庆市;
				break;
				case "四川省":
				optinsValue = response[22].四川省;
				break;
				case "贵州省":
				optinsValue = response[23].贵州省;
				break;
				case "云南省":
				optinsValue = response[24].云南省;
				break;
				case "西藏自治区":
				optinsValue = response[25].西藏自治区;
				break;
				case "陕西省":
				optinsValue = response[26].陕西省;
				break;
				case "甘肃省":
				optinsValue = response[27].甘肃省;
				break;
				case "青海省":
				optinsValue = response[28].青海省;
				break;
				case "宁夏回族自治区":
				optinsValue = response[29].宁夏回族自治区;
				break;
				case "新疆维吾尔自治区":
				optinsValue = response[30].新疆维吾尔自治区;
				break;
				case "香港特别行政区":
				optinsValue = response[31].香港特别行政区;
				break;
				case "澳门特别行政区":
				optinsValue = response[32].澳门特别行政区;
				break;
			}
			for(let i in optinsValue) {
				this.cityOpt.push(optinsValue[i]);
			}
		}
	}
}
</script>