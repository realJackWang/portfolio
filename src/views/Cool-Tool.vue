<template>
  <el-container>
    <el-aside width="150px">
      <el-row type="flex" class="row-bg" justify="center">
        <div>&nbspCOOOOOL WEB</div>
      </el-row>
      <el-row type="flex" class="row-bg" justify="center"></el-row>
      <el-row type="flex" class="row-bg" justify="center"></el-row>
      <el-row type="flex" class="row-bg" justify="center"></el-row>
      <el-row type="flex" class="row-bg" justify="center"></el-row>

      <el-row type="flex" class="row-bg" justify="center">
        <el-col :span="6">
          <img src="https://i.loli.net/2020/06/07/rgBP7vXmbn3KeOD.png" height="32px" />
        </el-col>
        <el-col :span="10">
          <div id="title">
            <a href="cool">创意</a>
          </div>
        </el-col>
      </el-row>

      <el-row type="flex" class="row-bg" justify="center">
        <el-col :span="6">
          <img src="https://i.loli.net/2020/06/07/t5gyRKsqp6mwfvQ.png" height="32px" />
        </el-col>
        <el-col :span="10">
          <div id="title">
            <a href="cool-game">游戏</a>
          </div>
        </el-col>
      </el-row>

      <el-row type="flex" class="row-bg" justify="center">
        <el-col :span="6">
          <img src="https://i.loli.net/2020/06/07/m9xqdZpBk1SLIAo.png" height="32px" />
        </el-col>
        <el-col :span="10">
          <div id="title">
            <a href="cool-code">编程</a>
          </div>
        </el-col>
      </el-row>

      <el-row type="flex" class="row-bg" justify="center">
        <el-col :span="6">
          <img src="https://i.loli.net/2020/06/07/63r9OXxuELPegSp.png" height="32px" />
        </el-col>
        <el-col :span="10">
          <div id="title">
            <a href="cool-tool">工具</a>
          </div>
        </el-col>
      </el-row>

      <el-row type="flex" class="row-bg" justify="center">
        <el-col :span="6">
          <img src="https://i.loli.net/2020/06/07/OtKLlowZ9Jbp2kn.png" height="32px" />
        </el-col>
        <el-col :span="10">
          <div id="title">
            <a href="cool-book">Kindle</a>
          </div>
        </el-col>
      </el-row>

      <el-row type="flex" class="row-bg" justify="center">
        <el-col :span="6">
          <img src="https://i.loli.net/2020/06/07/67MeAYjUf8qWFdi.png" height="32px" />
        </el-col>
        <el-col :span="10">
          <div id="title">
            <a @click="open3">投稿</a>
          </div>
        </el-col>
      </el-row>

      <el-row type="flex" class="row-bg" justify="center">🚀：可能需要VPN</el-row>
    </el-aside>
    <el-main>
      <el-row>
        <el-col
          :span="6"
          v-for="site in sites"
          :key="site.index"
          :offset="1"
          :xs="{span: 20, offset: 0}"
          :sm="{span: 10, offset: 1}"
          :lg="{span: 6, offset: 1}"
        >
          <WebCard :msg="site.name" :description="site.msg" :icon="site.img" :link1="site.url" />
        </el-col>
      </el-row>
    </el-main>
  </el-container>
</template>

<script>
import WebCard from '@/components/WebCard.vue'
import axios from 'axios'

export default {
  name: 'cool',
  components: {
    WebCard
  },

  data: {
    sites: []
  },

  data() {
    return {
      sites: [
              {
          name: 'Steam历史价格',
          msg: '查询Steam游戏的历史价格',
          url: 'https://steamdb.info/',
          img: 'https://i.loli.net/2020/06/07/wcRP4ljN9YQbtx6.png'
        },
          {
          name: '匿名发邮件',
          msg: 'Temp Mail提供临时、安全、匿名、免费的一次性电子邮件地址。',
          url: 'https://temp-mail.org/zh/',
          img: 'https://i.loli.net/2020/06/07/j4Xnf7CJSoam2Zu.png'
        },
           {
          name: 'Temp Mail',
          msg: 'Temp Mail提供临时、安全、匿名、免费的一次性电子邮件地址。',
          url: 'https://temp-mail.org/zh/',
          img: 'https://i.loli.net/2020/06/07/j4Xnf7CJSoam2Zu.png'
        },
          {
          name: '在线流程图',
          msg: '一个免费的在线流程图制作工具',
          url: '//www.remove.bg/zh',
          img: 'https://i.loli.net/2020/06/07/Bc9dLFqRpjZkJDW.png'
        },
          {
          name: '自动抠人像',
          msg: '快速AI自动抠图！不止人物还有车、动物、产品',
          url: '//www.remove.bg/zh',
          img: 'https://i.loli.net/2020/06/07/MnkoRFHmfu7UxEN.png'
        },
        {
          name: '黑白照片上色',
          msg: '通过AI将黑白照片上色为彩色',
          url: '//colourise.sg/',
          img: 'https://i.loli.net/2020/06/03/RVliYBWyKxkvn4r.png'
        },
        {
          name: '图片分辨率↑',
          msg: '通过AI将提高照片的分辨率，漫画效果极佳',
          url: '//bigjpg.com/',
          img: 'https://i.loli.net/2020/06/07/jzfpurgcZOoMxwV.png'
        },
        
      ]
    }
  },

  /* mounted() {
    axios
      .get('http://www.baidu.com')
      .then(response => (this.sites = response.data.t))
      .catch(function(error) {
        // 请求失败处理
        console.log(error)
      })
  },*/

  methods: {
    open() {
      this.$alert('这是一段内容', '标题名称', {
        confirmButtonText: '确定',
        callback: action => {
          this.$message({
            type: 'info',
            message: `action: ${action}`
          })
        }
      })
    },
     open3() {
      this.$prompt('请输入有趣的网址（Bark推送提供支持）', '提示', {
        confirmButtonText: '确定',
        cancelButtonText: '取消',
        inputPattern: /^([a-zA-Z0-9]([a-zA-Z0-9\-]{0,61}[a-zA-Z0-9])?\.)+[a-zA-Z]{2,6}$/,
        inputErrorMessage: '网页格式不正确'
      })
        .then(({ value }) => {
          this.$message({
            type: 'success',
            message: '感谢你提交的网站~'
          }),
            axios
              .get(
                'https://api.day.app/N7e3N26kYCWjb5vQCLfNZg/收到一条来自Cool Web的投稿?url=' +
                  value
              )
              .then(response => (this.sites = response.data.t))
              .catch(function(error) {
                // 请求失败处理
                console.log(error)
              })
        })
        .catch(() => {
          this.$message({
            type: 'info',
            message: '哎，没有的嘛'
          })
        })
    }
  }
}
</script>

<style lang="css" scoped>
h2 {
  font-weight: 700;
  font-size: 20px;
  padding: 10px 0;
}

h3 {
  font-weight: 700;
  font-size: 18px;
  padding: 18px 0 0 0;
  margin: 0;
}

ul {
  padding-left: 15px;
  line-height: 30px;
  margin: 0;
}

p {
  line-height: 30px;
  text-align: center;
}

a {
  text-decoration: none;
  color: #292626;
}

#title {
  font-size: 16px;
  text-align: left;
  width: 60%;
}

.time {
  font-size: 13px;
  color: #999;
}

.bottom {
  margin-top: 13px;
  line-height: 12px;
}

.button {
  padding: 0;
  float: right;
}

.image {
  width: 100%;
  display: block;
}

.clearfix:before,
.clearfix:after {
  display: table;
  content: '';
}

.clearfix:after {
  clear: both;
}

.el-row {
  margin-bottom: 20px;
  &:last-child {
    margin-bottom: 0;
  }
}
</style>
