<template>
  <div class="app-container">
    <div class="filter-container">
      <el-form>
        <el-form-item label="按Asset压缩大小">
          <el-radio-group v-model="form.compressed">
            <el-radio label="2M以上" />
            <el-radio label="1M以上" />
            <el-radio label="500K以上" />
            <el-radio label="200K以上" />
            <el-radio label="100K以上" />
            <el-radio label="全部" />
          </el-radio-group>
          <el-input-number />
        </el-form-item>
      </el-form>
    </div>
    <el-table :data="bundleAssets" style="width: 100%">
      <el-table-column prop="asset_path" label="Asset Path" />
      <el-table-column prop="res_size" label="Resource Size (bytes)" />
      <el-table-column prop="res_compressed_size" label="Compressed Size (bytes)" />
    </el-table>
  </div>
</template>

<script>
import tableData from '@/assets/all_bundle_asset_size.json'

export default {
  data() {
    return {
      form: {
        resource: '',
        compressed: ''
      },
      // 假设这是从某处（如API请求、本地文件等）获取的JSON数据
      allBenchmarkItems: tableData,
      // 将assets数据扁平化并存储，以便直接绑定到表格
      bundleAssets: []
    }
  },
  created() {
    console.log(this.allBenchmarkItems['all_benchmark_items']['all_bundle_sorted_items'][0].assets) // 检查是否包含数据
    // debugger
    this.bundleAssets = this.allBenchmarkItems['all_benchmark_items']['all_bundle_sorted_items'][0].assets
  },
  methods: {
    handleResourceChange(value) {
      if (value === '5M以上') {
        this.filterLargeResources()
      } else if (value === '全部') {
        this.bundleAssets = this.bundleAssets = this.allBenchmarkItems['all_benchmark_items']['all_bundle_sorted_items'][0].assets
      }
      // 可以根据需要添加更多条件判断
    },
    filterLargeResources() {
      // 5MB 转换为字节
      const MAX_SIZE = 5 * 1024 * 1024
      this.bundleAssets = this.bundleAssets.filter(bundleAssets => bundleAssets['res_size'] > MAX_SIZE)
    }
  }
}
</script>
