<template>
  <div class="app-container">
    <div class="filter-container">
      <el-form>
        <el-form-item label="按Bundle进包大小">
          <el-radio-group v-model="form.resource" @change="handleResourceChange">
            <!-- 5242880 -->
            <el-radio label="5M以上" />
            <el-radio label="4M以上" />
            <el-radio label="3M以上" />
            <el-radio label="2M以上" />
            <el-radio label="1M以上" />
            <el-radio label="全部" />
          </el-radio-group>
        </el-form-item>
        <el-form-item label="按Asset压缩大小">
          <el-radio-group v-model="form.compressed">
            <el-radio label="1M以上" />
            <el-radio label="500K以上" />
            <el-radio label="200K以上" />
            <el-radio label="100K以上" />
            <el-radio label="全部" />
          </el-radio-group>
        </el-form-item>
      </el-form>
    </div>
    <el-table :data="tableData.slice((currentPage - 1) * pageSize, currentPage * pageSize)" style="width: 100%">
      <el-table-column prop="asset_path" label="Asset Path" />
      <el-table-column prop="res_size" label="Resource Size (bytes)" />
      <el-table-column prop="res_compressed_size" label="Compressed Size (bytes)" />
    </el-table>
    <!-- 分页 -->
    <el-pagination
      :current-page="currentPage"
      :page-sizes="[10, 20, 30, 40]"
      :page-size="pageSize"
      layout="total, sizes, prev, pager, next, jumper"
      :total="bundleAssets.length"
      @size-change="handleSizeChange"
      @current-change="handleCurrentChange"
    />
  </div>
</template>

<script>
import originData from '@/assets/all_bundle_asset_size.json'

export default {
  data() {
    return {
      tableData: originData, // 假设这是你从后端获取的数据
      currentPage: 1,
      pageSize: 10,
      form: {
        resource: '',
        compressed: ''
      },
      // 假设这是从某处（如API请求、本地文件等）获取的JSON数据
      allBenchmarkItems: originData,
      // 将assets数据扁平化并存储，以便直接绑定到表格
      bundleAssets: []
    }
  },
  created() {
    // 假设这里你从后端获取数据
    this.fetchData()
  },
  methods: {
    fetchData() {
      // 这里应该是你请求数据的代码，这里只是模拟
      this.tableData = originData['all_benchmark_items']['all_bundle_sorted_items'][0].assets
    },
    handleSizeChange(val) {
      this.pageSize = val
      this.fetchData() // 注意：这里通常不需要重新请求数据，除非你需要基于新的 pageSize 来获取数据
    },
    handleCurrentChange(val) {
      this.currentPage = val
    },
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
