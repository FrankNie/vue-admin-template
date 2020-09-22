<template>
  <div class="app-container">
    <el-form ref="form" :model="form" label-width="120px">

      <el-form-item label="版本分支">
        <el-select v-model="form.branch" placeholder="请选择版本分支" style="width: 400px">
          <el-option label="机器人3-量产版" value="W3_RELEASE" />
          <el-option label="机器人3-测试版" value="W3_TEST" />
        </el-select>
      </el-form-item>

      <el-form-item label="模块名称">
        <el-select v-model="form.module" placeholder="请选择模块名称" style="width: 400px">
          <el-option label="robot_app" value="robot_app" />
          <el-option label="system" value="system" />
        </el-select>
      </el-form-item>

      <el-form-item label="版本号">
        <el-input v-model="form.version" style="width: 200px" />
      </el-form-item>

      <el-form-item label="发布日期">
        <el-date-picker v-model="form.date" type="date" placeholder="请选择发布日期" style="width: 200px" />
      </el-form-item>

      <el-form-item label="升级包路径">
        <el-input v-model="form.path" class="input-with-select" placeholder="请输入升级包路径" style="width: 600px" />
      </el-form-item>

      <el-form-item label="文件MD5码">
        <el-input v-model="form.md5" style="width: 400px" placeholder="请输入文件MD5码" />
      </el-form-item>

      <el-form-item label="是否生效">
        <el-switch v-model="form.valid" />
      </el-form-item>

      <el-form-item label="更新类型">
        <el-radio-group v-model="form.update">
          <el-radio :label="1">提醒</el-radio>
          <el-radio :label="2">静默</el-radio>
        </el-radio-group>
      </el-form-item>

      <el-form-item label="版本说明">
        <el-input v-model="form.desc" type="textarea" :rows="3" placeholder="请输入版本说明" style="width: 600px" />
      </el-form-item>

      <el-form-item>
        <el-button type="primary" @click="onSubmit">提交</el-button>
        <el-button @click="onCancel">取消</el-button>
      </el-form-item>

    </el-form>
  </div>
</template>

<script>
export default {
  data() {
    return {
      form: {
        branch: 'W3_RELEASE',
        module: 'robot_app',
        version: '1.0',
        date: '',
        path: '',
        md5: '',
        valid: true,
        update: 1,
        desc: ''
      }
    }
  },
  methods: {
    onSubmit() {
      this.$message('submit!')
    },
    onCancel() {
      this.$message({
        message: 'cancel!',
        type: 'warning'
      })
    }
  }
}
</script>

<style scoped>
.line{
  text-align: center;
}
.el-select .el-input {
  width: 130px;
}
.input-with-select .el-input-group__prepend {
  background-color: #fff;
}
</style>

