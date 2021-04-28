<template>
  <div class="ct-bodySet" style="color:#6E7A84;min-width: 1000px;">
    <el-container>
      <el-header
        class="bgclr-dk-sp0 mb20 headerCoster"
        style="margin: 0px 20px 15px 20px; min-width: 1000px;height: 50px;display: inline-flex;align-items: center;justify-content: space-between;"
      >
        <div class="breadcrumb">
          <el-breadcrumb separator-class="el-icon-arrow-right">
            <el-breadcrumb-item>应急事件管理</el-breadcrumb-item>
            <el-breadcrumb-item>事件报告管理</el-breadcrumb-item>
            <el-breadcrumb-item>报告上传</el-breadcrumb-item>
            <el-breadcrumb-item>
              <span class="main-Clr-ft">报告列表</span>
            </el-breadcrumb-item>
          </el-breadcrumb>
          <div style="color: #259BFF;cursor: pointer;">
            <i class="el-icon-back" @click="back()">返回</i>
          </div>
        </div>
      </el-header>
      <div class="pl20 pr20 newTb">
        <el-card class="mb20 cardWidth">
          <div class="titlebar">
            <p class="titlebar-p">照片</p>
            <div class="btn-list">
              <el-button size="small" type="primary" @click="dialogVisiblePic = true">上传</el-button>
              <p class="btn-line"></p>
              <el-button size="small" morePlain class="btn-return">删除</el-button>
            </div>
          </div>
          <div class="inline-block">
            <div v-for="(v, i) in data" :key="'id'+i" class="year-item">
              <the-time-line :time-data="v" @fun1="getUrl" @func="getMsgFormSon"></the-time-line>
            </div>
          </div>
        </el-card>
      </div>
    </el-container>
    <!-- 上传弹窗 开始 -->
    <el-dialog
      title="上传图片"
      :visible.sync="dialogVisiblePic"
      width="800px"
      style="text-align: left;"
      close-on-click-modal
      class="rejectDialogPic"
      :before-close="dialogVisiblePicClick"
    >
      <div class>
        <el-form :model="ruleForm" ref="ruleForm" label-width="100px">
          <el-form-item label="拍摄时间：" prop="value">
            <el-date-picker
              style="width: 95%;"
              v-model="ruleForm.value"
              type="date"
              placeholder="选择日期"
            ></el-date-picker>
          </el-form-item>
          <!-- <el-form-item style="color:red" label="上传照片 " prop="name">
                        <span>支持上传格式为：png、jpg；单个文件不能超过3M</span>
          </el-form-item>-->
          <div style="margin: 0px 10px 15px 20px;">
            <span style="font-size: 15px;font-weight: bold;">上传照片</span>
            <span style="margin-left: 15px;">支持上传格式为：png、jpg；单个文件不能超过3M</span>
          </div>
          <el-form-item label prop="imageUrl">
            <el-upload
              action
              list-type="picture-card"
              ref="pictureUpload"
              multiple
              :limit="9"
              :on-exceed="handleExceed"
              :on-preview="handlePictureCardPreview"
              :on-remove="handleRemove"
              :on-change="handleChange"
              :on-success="handleSuccess"
              :class="{hide:hideUpload}"
              :auto-upload="false"
              :file-list="fileList"
            >
              <i slot="default" class="el-icon-plus"></i>
            </el-upload>
            <el-dialog append-to-body :visible.sync="dialogVisible">
              <img width="100%" :src="dialogImageUrl" alt />
            </el-dialog>
          </el-form-item>
        </el-form>
      </div>
      <template slot="footer" class="dialogFooter">
        <div style="display: flex;justify-content: center;">
          <el-button size="small" @click="dialogVisiblePicClick()">取 消</el-button>
          <el-button size="small" type="primary" @click="submitForm()">提 交</el-button>
        </div>
      </template>
    </el-dialog>
  </div>
</template>

<script>
// import upload from './picTest.vue'
import axios from 'axios'
import theTimeLine from '@/components/TheTimeLine'
export default {
  name: 'uploadPic',
  components: {
    // upload,
    theTimeLine,
  },
  data() {
    return {
      aaaaa: [],
      dialogVisiblePic: false,
      dialogImageUrl: '',
      dialogVisible: false,
      disabled: false,
      fileList: [],
      file: [],
      hideUpload: false,
      ruleForm: {
        value: '',
      },
      data: [
        {
          yearData: '2021年2月',
          mouthData: [
            {
              dateArr: [
                'https://fuss10.elemecdn.com/1/34/19aa98b1fcb2781c4fba33d850549jpeg.jpeg',
                'https://fuss10.elemecdn.com/a/3f/3302e58f9a181d2509f3dc0fa68b0jpeg.jpeg',
                'https://fuss10.elemecdn.com/0/6f/e35ff375812e6b0020b6b4e8f9583jpeg.jpeg',
              ],
            },
          ],
        },
        {
          yearData: '2021年1月',
          mouthData: [
            {
              dateArr: [
                'https://fuss10.elemecdn.com/9/bb/e27858e973f5d7d3904835f46abbdjpeg.jpeg',
                'https://fuss10.elemecdn.com/d/e6/c4d93a3805b3ce3f323f7974e6f78jpeg.jpeg',
                'https://fuss10.elemecdn.com/e/5d/4a731a90594a4af544c0c25941171jpeg.jpeg',
                'https://cube.elemecdn.com/6/94/4d3ea53c084bad6931a56d5158a48jpeg.jpeg',
              ],
            },
          ],
        },
      ],
    }
  },
  mounted() {},
  methods: {
    handleChange(file, fileList) {
      this.fileList = fileList
      this.file = file
      if (fileList.length >= 9) {
        this.hideUpload = true
      } else {
        this.hideUpload = false
      }
    },
    handleRemove(file, fileList) {
      this.fileList = fileList
      this.hideUpload = false
    },
    handlePictureCardPreview(file) {
      this.dialogImageUrl = file.url
      this.dialogVisible = true
    },
    handleSuccess(response, file, fileList) {
      this.fileList = fileList
    },
    handleExceed(files, fileList) {
      //   console.log(fileList.length)
      this.$message.warning(
        `当前限制选择 9 个文件，本次选择了 ${files.length} 个文件，共选择了 ${
          files.length + fileList.length
        } 个文件`
      )
    },
    dialogVisiblePicClick() {
      this.$toast({
        text: '审核通过',
        type: 'info',
        duration: 3000,
      })

      this.$refs.pictureUpload.clearFiles()
      this.dialogVisiblePic = false
    },
    getMsgFormSon(url) {
      let a = this.aaaaa.includes(url)
      // let flag = this.aaaaa.find((item) => item == url)
      // this.a = data
      console.log(a)
    },
    submitForm() {
      let formData = new FormData()
      //   for(let x in this.form){
      //     this.formData.append(x,this.form[x]);
      //   }
      for (let i = 0; i < this.fileList.length; i++) {
        formData.append('files', this.fileList[i].raw)
        console.log(this.fileList[i].raw)
      }
      formData.append('storageSpaceId', 'c7838a7e-d0e8-4ad8-8e2b-55ec632fad5e')
      axios({
        url: '/api/file/upload',
        method: 'post',
        headers: {
          'Content-Type': 'multipart/form-data',
        },
        data: formData,
      })
        .then((response) => {
          console.log(response)
        })
        .catch(function (error) {
          console.log(error)
        })
    },
  },
}
</script>

<style scoped lang="scss">
.headerCoster {
  height: 49px;
}
.cardWidth {
  width: 100%;
  height: calc(100vh - 160px);
  overflow-y: auto;
  .el-card__body {
    padding: 7px;
  }
}
.main-Clr-ft {
  color: #313d47;
  font-weight: 600;
}
.breadcrumb {
  display: flex;
  justify-content: space-between;
  width: 100%;
}
.titlebar {
  display: flex;
  align-items: center;
  justify-content: space-between;
  left: 210px;
  right: 0;
  color: #333;
  font-size: 16px;
  font-weight: bold;
  height: 50px;
  padding-bottom: 10px;
  margin-top: -1px;
  padding: 0 20px;
  z-index: 20;
  .titlebar-p {
    height: 17px;
    line-height: 17px;
    border-left: 4px solid #259bff;
    padding-left: 10px;
  }
}
.btn-list {
  display: flex;
  justify-content: space-between;
  align-items: center;
  .he-button--normal {
    margin-left: 10px;
  }
  .btn-line {
    height: 30px;
    margin: 0 10px 0 10px;
  }
  .el-button {
    width: 64px;
  }
}
</style>
<style lang="scss">
.rejectDialogPic {
  min-height: 400px;
  .el-dialog__title {
    font-size: 14px;
  }
  .el-dialog__header {
    background: #f7f7f7;
    padding: 10px 20px 8px;
  }
  .el-dialog__headerbtn {
    top: 15px;
  }
  .el-dialog__body {
    padding: 15px 20px;
  }
  .el-textarea__inner {
    min-height: 260px !important;
  }
}
.hide .el-upload--picture-card {
  display: none;
}
</style>
