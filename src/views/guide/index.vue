<template>
  <div>
    <!-- 表格 -->
    <el-table
      :data="tableData.slice((currentPage - 1) * pageSize, currentPage * pageSize)"
      style="width: 100%"
    >
      <el-table-column
        prop="size"
        label="size"
      />
      <el-table-column
        prop="name"
        label="name"
      />
      <!-- 根据需要添加更多列 -->
    </el-table>

    <!-- 分页 -->
    <el-pagination
      :current-page="currentPage"
      :page-sizes="[10, 20, 30, 40]"
      :page-size="pageSize"
      layout="total, sizes, prev, pager, next, jumper"
      :total="tableData.length"
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
      pageSize: 10
    }
  },
  created() {
    // 假设这里你从后端获取数据
    this.fetchData();
  },
  methods: {
    fetchData() {
      // 这里应该是你请求数据的代码，这里只是模拟
      this.tableData = originData['all_comparison_items']['all_pkg_sorted_items']
    },
    handleSizeChange(val) {
      this.pageSize = val
      this.fetchData() // 注意：这里通常不需要重新请求数据，除非你需要基于新的 pageSize 来获取数据
    },
    handleCurrentChange(val) {
      this.currentPage = val
    }
  }
}
</script>
