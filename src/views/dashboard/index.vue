<template>
  <el-table :data="tableData" style="width: 100%">
    <el-table-column type="expand">
      <template slot-scope="props">
        <el-form label-position="left" inline class="demo-table-expand">
          <el-form-item label="asset_path">
            <span>{{ props.row.asset_path }}</span>
          </el-form-item>
          <el-form-item label="res_size">
            <span>{{ props.row.res_size }}</span>
          </el-form-item>
          <el-form-item label="res_compressed_size">
            <span>{{ props.row.res_compressed_size }}</span>
          </el-form-item>
        </el-form>
      </template>
    </el-table-column>
    <el-table-column label="asset_path" prop="asset_path">
    </el-table-column>
    <el-table-column label="res_size" prop="res_size">
    </el-table-column>
    <el-table-column label="res_compressed_size" prop="res_compressed_size">
    </el-table-column>
  </el-table>
</template>

<style>
.demo-table-expand {
  font-size: 0;
}

.demo-table-expand label {
  /* width: 90px; */
  color: #99a9bf;
}

.demo-table-expand .el-form-item {
  margin-right: 0;
  margin-bottom: 0;
  width: 50%;
}
</style>

<script>
export default {
  data() {
    return {
      tableData: [
        {
          "asset_path": "Assets/ResourcesRaw/Player/9001_male/Ani/ani_idle_lob_male.anim",
          "res_size": 5557452,
          "res_compressed_size": 3359532
        },
        {
          "asset_path": "Assets/ResourcesRaw/NPC/001_ProfessorPhorus/00/Model/rig_lob_00100_lv3.FBX",
          "res_size": 1782579,
          "res_compressed_size": 1080452
        },
        {
          "asset_path": "Assets/ResourcesRaw/NPC/0555_jiangbei/07/Mat_Tex/t_nm_lob_07jiangbei_Shuijing_lv3.tga",
          "res_size": 1048576,
          "res_compressed_size": 641518
        },
        {
          "asset_path": "Assets/ResourcesRaw/NPC/0555_jiangbei/07/Mat_Tex/t_nm_lob_07jiangbei_lv3.tga",
          "res_size": 1048576,
          "res_compressed_size": 641518
        }
      ]
    }
  }
}
</script>
