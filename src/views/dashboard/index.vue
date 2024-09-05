<template>
  <div class="app-container">
    <div class="filter-container">
      <el-form>
        <el-form-item label="按Bundle进包大小">
          <el-radio-group v-model="form.resource">
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

    <el-table :data="assets" style="width: 100%">
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
      <el-table-column label="asset_path" prop="asset_path" />
      <el-table-column label="res_size" prop="res_size" />
      <el-table-column label="res_compressed_size" prop="res_compressed_size" />
    </el-table>
  </div>
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
      form: {
        resource: '',
        compressed: ''
      },
      assets: [
        {
          'asset_path': 'Assets/ResourcesRaw/Player/9001_male/Ani/ani_idle_lob_male.anim',
          'res_size': 5557452,
          'res_compressed_size': 3359532
        },
        {
          'asset_path': 'Assets/ResourcesRaw/NPC/001_ProfessorPhorus/00/Model/rig_lob_00100_lv3.FBX',
          'res_size': 1782579,
          'res_compressed_size': 1080452
        },
        {
          'asset_path': 'Assets/ResourcesRaw/NPC/0555_jiangbei/07/Mat_Tex/t_nm_lob_07jiangbei_Shuijing_lv3.tga',
          'res_size': 1048576,
          'res_compressed_size': 641518
        },
        {
          'asset_path': 'Assets/ResourcesRaw/NPC/0555_jiangbei/07/Mat_Tex/t_nm_lob_07jiangbei_lv3.tga',
          'res_size': 1048576,
          'res_compressed_size': 641518
        },
        {
          'asset_path': 'Assets/ResourcesRaw/NPC/001_ProfessorPhorus/00/Mat_Tex/t_nm_npc01body_lv3.tga',
          'res_size': 1048576,
          'res_compressed_size': 641518
        },
        {
          'asset_path': 'Assets/ResourcesRaw/Heroes/0025_Pikachu/00/Mat_Tex/t_n_lob_0025body_lv3.tga',
          'res_size': 1048576,
          'res_compressed_size': 641518
        },
        {
          'asset_path': 'Assets/ResourcesRaw/Player/9002_female/Ani/ani_pws01_lob_female.anim',
          'res_size': 723558,
          'res_compressed_size': 438933
        },
        {
          'asset_path': 'Assets/ResourcesRaw/Heroes/0025_Pikachu/00/Model/rig_lob_0025_lv3.FBX',
          'res_size': 482713,
          'res_compressed_size': 286995
        },
        {
          'asset_path': 'Assets/ResourcesRaw/NPC/001_ProfessorPhorus/00/AniCity/ani_citytalk2_lob_001.anim',
          'res_size': 342425,
          'res_compressed_size': 202584
        },
        {
          'asset_path': 'Assets/ResourcesRaw/NPC/001_ProfessorPhorus/00/Ani/ani_idle_lob_001.anim',
          'res_size': 334336,
          'res_compressed_size': 202584
        },
        {
          'asset_path': 'Assets/ResourcesRaw/NPC/001_ProfessorPhorus/00/Ani/ani_runout_lob_001.anim',
          'res_size': 325836,
          'res_compressed_size': 202584
        },
        {
          'asset_path': 'Assets/ResourcesRaw/Player/9002_female/Ani/ani_lookat_lob_female.anim',
          'res_size': 284262,
          'res_compressed_size': 168820
        },
        {
          'asset_path': 'Assets/ResourcesRaw/NPC/001_ProfessorPhorus/00/Ani/ani_fallball01_lob_001.anim',
          'res_size': 282624,
          'res_compressed_size': 168820
        },
        {
          'asset_path': 'Assets/ResourcesRaw/Scene/Lobby/lobby_maincity_open/Texture/t_d_sce_maincityop_ship02b_lv3.tga',
          'res_size': 262348,
          'res_compressed_size': 151938
        },
        {
          'asset_path': 'Assets/ResourcesRaw/Scene/Lobby/lobby_maincity_open/Texture/t_d_sce_maincityop_ship02a_lv3.tga',
          'res_size': 262348,
          'res_compressed_size': 151938
        },
        {
          'asset_path': 'Assets/ResourcesRaw/NPC/0555_jiangbei/07/Mat_Tex/t_d_lob_07jiangbei_Shuijing_lv3.tga',
          'res_size': 262348,
          'res_compressed_size': 151938
        },
        {
          'asset_path': 'Assets/ResourcesRaw/Effect_Lobby/Textures/t_fx_lob_088802_daoguang_34_xh.png',
          'res_size': 262348,
          'res_compressed_size': 151938
        },
        {
          'asset_path': 'Assets/ResourcesRaw/Effect_Lobby/Textures/t_fx_lob_088802_daoguang_33_xh.png',
          'res_size': 262348,
          'res_compressed_size': 151938
        },
        {
          'asset_path': 'Assets/ResourcesRaw/NPC/0555_jiangbei/07/Mat_Tex/t_i_lob_07jiangbei_lv3.tga',
          'res_size': 262348,
          'res_compressed_size': 151938
        },
        {
          'asset_path': 'Assets/ResourcesRaw/NPC/0555_jiangbei/07/Mat_Tex/t_d_lob_07jiangbei_lv3.tga',
          'res_size': 262348,
          'res_compressed_size': 151938
        },
        {
          'asset_path': 'Assets/ResourcesRaw/NPC/001_ProfessorPhorus/00/Mat_Tex/t_d_lob_npc01body_lv3.tga',
          'res_size': 262348,
          'res_compressed_size': 151938
        },
        {
          'asset_path': 'Assets/ResourcesRaw/Heroes/0025_Pikachu/00/Mat_Tex/t_mroe_lob_0025body_lv3.tga',
          'res_size': 262348,
          'res_compressed_size': 151938
        },
        {
          'asset_path': 'Assets/ResourcesRaw/Heroes/0025_Pikachu/00/Mat_Tex/t_d_lob_0025body_lv3.tga',
          'res_size': 262348,
          'res_compressed_size': 151938
        },
        {
          'asset_path': 'Assets/ResourcesRaw/Guide/Animation/timeline05/t_d_city_ZB_02_lv3.png',
          'res_size': 262348,
          'res_compressed_size': 151938
        },
        {
          'asset_path': 'Assets/ResourcesRaw/Guide/Animation/timeline05/t_d_city_ZB_01_lv3.png',
          'res_size': 262348,
          'res_compressed_size': 151938
        },
        {
          'asset_path': 'Assets/ResourcesRaw/Guide/Animation/timeline05/t_d_city_XB_02_lv3.png',
          'res_size': 262348,
          'res_compressed_size': 151938
        },
        {
          'asset_path': 'Assets/ResourcesRaw/Guide/Animation/timeline05/t_d_city_XB_01_lv3.png',
          'res_size': 262348,
          'res_compressed_size': 151938
        },
        {
          'asset_path': 'Assets/ResourcesRaw/Guide/Animation/timeline05/t_d_city_NL_03_lv3.png',
          'res_size': 262348,
          'res_compressed_size': 151938
        },
        {
          'asset_path': 'Assets/ResourcesRaw/Guide/Animation/timeline05/t_d_city_NL_02_lv3.png',
          'res_size': 262348,
          'res_compressed_size': 151938
        },
        {
          'asset_path': 'Assets/ResourcesRaw/Guide/Animation/timeline05/t_d_city_NL_01_lv3.png',
          'res_size': 262348,
          'res_compressed_size': 151938
        },
        {
          'asset_path': 'Assets/ResourcesRaw/NPC/001_ProfessorPhorus/00/AniCity/ani_guidetalk7_lob_001.anim',
          'res_size': 233472,
          'res_compressed_size': 135056
        },
        {
          'asset_path': 'Assets/ResourcesRaw/NPC/001_ProfessorPhorus/00/AniCity/ani_guidetalk1_lob_001.anim',
          'res_size': 230400,
          'res_compressed_size': 135056
        },
        {
          'asset_path': 'Assets/ResourcesRaw/NPC/001_ProfessorPhorus/00/AniCity/ani_citytalk_lob_001.anim',
          'res_size': 229580,
          'res_compressed_size': 135056
        },
        {
          'asset_path': 'Assets/ResourcesRaw/Player/9002_female/Ani/ani_runstopleft_lob_female.anim',
          'res_size': 228044,
          'res_compressed_size': 135056
        },
        {
          'asset_path': 'Assets/ResourcesRaw/NPC/001_ProfessorPhorus/00/AniCity/ani_guidetalk6_lob_001.anim',
          'res_size': 207974,
          'res_compressed_size': 118174
        },
        {
          'asset_path': 'Assets/ResourcesRaw/NPC/001_ProfessorPhorus/00/AniCity/ani_citytalk5_lob_001.anim',
          'res_size': 196505,
          'res_compressed_size': 118174
        },
        {
          'asset_path': 'Assets/ResourcesRaw/NPC/001_ProfessorPhorus/00/AniCity/ani_citytalk4_lob_001.anim',
          'res_size': 191078,
          'res_compressed_size': 118174
        },
        {
          'asset_path': 'Assets/ResourcesRaw/NPC/001_ProfessorPhorus/00/AniCity/ani_guidetalk4_lob_001.anim',
          'res_size': 190464,
          'res_compressed_size': 118174
        },
        {
          'asset_path': 'Assets/ResourcesRaw/NPC/001_ProfessorPhorus/00/AniCity/ani_citytalk7_lob_001.anim',
          'res_size': 190054,
          'res_compressed_size': 118174
        },
        {
          'asset_path': 'Assets/ResourcesRaw/NPC/001_ProfessorPhorus/00/Ani/ani_takle01_lob_001.anim',
          'res_size': 180633,
          'res_compressed_size': 118174
        },
        {
          'asset_path': 'Assets/ResourcesRaw/NPC/001_ProfessorPhorus/00/AniCity/ani_citytalk6_lob_001.anim',
          'res_size': 176025,
          'res_compressed_size': 101292
        },
        {
          'asset_path': 'Assets/ResourcesRaw/NPC/001_ProfessorPhorus/00/AniCity/ani_citytalk3_lob_001.anim',
          'res_size': 170598,
          'res_compressed_size': 101292
        },
        {
          'asset_path': 'Assets/ResourcesRaw/NPC/001_ProfessorPhorus/00/AniCity/ani_citytalk9_lob_001.anim',
          'res_size': 167833,
          'res_compressed_size': 101292
        },
        {
          'asset_path': 'Assets/ResourcesRaw/NPC/0555_jiangbei/07/Model/sm_lob_07jiangbei_lv3.FBX',
          'res_size': 165478,
          'res_compressed_size': 101292
        },
        {
          'asset_path': 'Assets/ResourcesRaw/Heroes/0025_Pikachu/00/Ani/ani_idle_lob_0025.anim',
          'res_size': 157696,
          'res_compressed_size': 101292
        },
        {
          'asset_path': 'Assets/ResourcesRaw/Player/9001_male/Ani/ani_lookat_lob_male.anim',
          'res_size': 156774,
          'res_compressed_size': 101292
        },
        {
          'asset_path': 'Assets/ResourcesRaw/Player/9002_female/Ani/ani_idle_lob_female.anim',
          'res_size': 145715,
          'res_compressed_size': 84410
        },
        {
          'asset_path': 'Assets/ResourcesRaw/NPC/001_ProfessorPhorus/00/AniCity/ani_citytalk1_lob_001.anim',
          'res_size': 136704,
          'res_compressed_size': 84410
        },
        {
          'asset_path': 'Assets/ResourcesRaw/Heroes/0025_Pikachu/00/Mat_Tex/t_n_lob_0025eye_lv3.tga',
          'res_size': 131276,
          'res_compressed_size': 84410
        },
        {
          'asset_path': 'Assets/ResourcesRaw/Guide/Animation/timeline05/t_d_city_DB_07_lv3.png',
          'res_size': 131276,
          'res_compressed_size': 84410
        },
        {
          'asset_path': 'Assets/ResourcesRaw/Guide/Animation/timeline05/t_d_city_DB_06_lv3.png',
          'res_size': 131276,
          'res_compressed_size': 84410
        },
        {
          'asset_path': 'Assets/ResourcesRaw/Guide/Animation/timeline05/t_d_city_DB_05_lv3.png',
          'res_size': 131276,
          'res_compressed_size': 84410
        },
        {
          'asset_path': 'Assets/ResourcesRaw/Guide/Animation/timeline05/t_d_city_DB_04_lv3.png',
          'res_size': 131276,
          'res_compressed_size': 84410
        },
        {
          'asset_path': 'Assets/ResourcesRaw/Guide/Animation/timeline05/t_d_city_DB_03_lv3.png',
          'res_size': 131276,
          'res_compressed_size': 84410
        },
        {
          'asset_path': 'Assets/ResourcesRaw/Guide/Animation/timeline05/t_d_city_DB_02_lv3.png',
          'res_size': 131276,
          'res_compressed_size': 84410
        },
        {
          'asset_path': 'Assets/ResourcesRaw/Guide/Animation/timeline05/t_d_city_DB_01_lv3.png',
          'res_size': 131276,
          'res_compressed_size': 84410
        },
        {
          'asset_path': 'Assets/ResourcesRaw/Effect/Textures/t_fx_city_R5_13_gp.png',
          'res_size': 131276,
          'res_compressed_size': 84410
        },
        {
          'asset_path': 'Assets/ResourcesRaw/Effect/Textures/t_fx_city_R5_12_gp.png',
          'res_size': 131276,
          'res_compressed_size': 84410
        },
        {
          'asset_path': 'Assets/ResourcesRaw/Guide/Animation/timeline02/t_d_city_R5_lv3.png',
          'res_size': 131276,
          'res_compressed_size': 84410
        },
        {
          'asset_path': 'Assets/ResourcesRaw/NPC/001_ProfessorPhorus/00/AniCity/ani_guidetalk3_lob_001.anim',
          'res_size': 123289,
          'res_compressed_size': 67528
        },
        {
          'asset_path': 'Assets/ResourcesRaw/Heroes/0025_Pikachu/00/Ani/ani_guide00_lob_0025.anim',
          'res_size': 115916,
          'res_compressed_size': 67528
        },
        {
          'asset_path': 'Assets/ResourcesRaw/Heroes/0025_Pikachu/00/Ani/ani_runturn_bat_0025.anim',
          'res_size': 111411,
          'res_compressed_size': 67528
        },
        {
          'asset_path': 'Assets/ResourcesRaw/NPC/001_ProfessorPhorus/00/AniCity/ani_citytalk8_lob_001.anim',
          'res_size': 109875,
          'res_compressed_size': 67528
        },
        {
          'asset_path': 'Assets/ResourcesRaw/NPC/001_ProfessorPhorus/00/AniCity/ani_cityidle_lob_001.anim',
          'res_size': 109158,
          'res_compressed_size': 67528
        },
        {
          'asset_path': 'Assets/ResourcesRaw/NPC/001_ProfessorPhorus/00/AniCity/ani_cityface_lob_001.anim',
          'res_size': 102092,
          'res_compressed_size': 67528
        },
        {
          'asset_path': 'Assets/ResourcesRaw/Player/9001_male/Ani/ani_walk_lob_male.anim',
          'res_size': 96563,
          'res_compressed_size': 50646
        },
        {
          'asset_path': 'Assets/ResourcesRaw/Player/Pokeball/Model/rig_newPokeball01_lob_lv3.FBX',
          'res_size': 95641,
          'res_compressed_size': 50646
        },
        {
          'asset_path': 'Assets/ResourcesRaw/Heroes/0025_Pikachu/00/Ani/ani_guide02_lob_0025.anim',
          'res_size': 94310,
          'res_compressed_size': 50646
        },
        {
          'asset_path': 'Assets/ResourcesRaw/NPC/001_ProfessorPhorus/00/AniCity/ani_citycongratulations_lob_001.anim',
          'res_size': 93491,
          'res_compressed_size': 50646
        },
        {
          'asset_path': 'Assets/ResourcesRaw/Heroes/0025_Pikachu/00/Ani/ani_guide03_lob_0025.anim',
          'res_size': 93491,
          'res_compressed_size': 50646
        },
        {
          'asset_path': 'Assets/ResourcesRaw/Player/9002_female/Ani/ani_run_lob_female.anim',
          'res_size': 87756,
          'res_compressed_size': 50646
        },
        {
          'asset_path': 'Assets/ResourcesRaw/Heroes/0025_Pikachu/00/Ani/ani_release_bat_0025.anim',
          'res_size': 82636,
          'res_compressed_size': 50646
        },
        {
          'asset_path': 'Assets/ResourcesRaw/Player/9001_male/Ani/ani_run_lob_male.anim',
          'res_size': 79360,
          'res_compressed_size': 50646
        },
        {
          'asset_path': 'Assets/ResourcesRaw/Player/9002_female/Ani/ani_pws02_lob_female.anim',
          'res_size': 73728,
          'res_compressed_size': 50646
        },
        {
          'asset_path': 'Assets/ResourcesRaw/Heroes/0025_Pikachu/00/Ani/ani_guide01_lob_0025.anim',
          'res_size': 68710,
          'res_compressed_size': 33764
        },
        {
          'asset_path': 'Assets/ResourcesRaw/Scene/Lobby/lobby_avatar/0094_gengar/lobby_009401_space/Texture/t_lm_lightmap_009401_disc01_final_mix.tga',
          'res_size': 65740,
          'res_compressed_size': 33764
        },
        {
          'asset_path': 'Assets/ResourcesRaw/Scene/Lobby/lobby_maincity_open/Texture/t_d_sce_maincityop_ship04_lv3.tga',
          'res_size': 65740,
          'res_compressed_size': 33764
        },
        {
          'asset_path': 'Assets/ResourcesRaw/Scene/Lobby/lobby_maincity_open/Texture/t_d_sce_maincityop_ship03_lv3.tga',
          'res_size': 65740,
          'res_compressed_size': 33764
        },
        {
          'asset_path': 'Assets/ResourcesRaw/Scene/Lobby/lobby_maincity_open/Texture/t_d_sce_maincityop_ship02d_lv3.tga',
          'res_size': 65740,
          'res_compressed_size': 33764
        },
        {
          'asset_path': 'Assets/ResourcesRaw/Scene/Lobby/lobby_maincity_open/Texture/t_d_sce_maincityop_ship02c_lv3.tga',
          'res_size': 65740,
          'res_compressed_size': 33764
        },
        {
          'asset_path': 'Assets/ResourcesRaw/Effect_Lobby/Textures/t_fx_lob_088802_daoguang_25_xh.png',
          'res_size': 65740,
          'res_compressed_size': 33764
        },
        {
          'asset_path': 'Assets/ResourcesRaw/Player/Female/lob_50000/Mat_Tex/t_d_lob_50000head_white_lv3.tga',
          'res_size': 65740,
          'res_compressed_size': 33764
        },
        {
          'asset_path': 'Assets/ResourcesRaw/NPC/001_ProfessorPhorus/00/Mat_Tex/t_nm_lob_npc01hair_lv3.tga',
          'res_size': 65740,
          'res_compressed_size': 33764
        },
        {
          'asset_path': 'Assets/ResourcesRaw/NPC/001_ProfessorPhorus/00/Mat_Tex/t_h_lob_npc01hair_lv3.tga',
          'res_size': 65740,
          'res_compressed_size': 33764
        },
        {
          'asset_path': 'Assets/ResourcesRaw/Heroes/0025_Pikachu/00/Mat_Tex/t_m_lob_0025body_lv3.tga',
          'res_size': 65740,
          'res_compressed_size': 33764
        },
        {
          'asset_path': 'Assets/ResourcesRaw/Guide/Animation/timeline05/t_d_city_BG_1_lv3.png',
          'res_size': 65740,
          'res_compressed_size': 33764
        },
        {
          'asset_path': 'Assets/ResourcesRaw/Effect/Textures/t_fx_city_R5_16_gp.png',
          'res_size': 65740,
          'res_compressed_size': 33764
        },
        {
          'asset_path': 'Assets/ResourcesRaw/Effect/Textures/t_fx_city_R5_15_gp.png',
          'res_size': 65740,
          'res_compressed_size': 33764
        },
        {
          'asset_path': 'Assets/ResourcesRaw/Effect/Textures/t_fx_city_R5_14_gp.png',
          'res_size': 65740,
          'res_compressed_size': 33764
        },
        {
          'asset_path': 'Assets/ResourcesRaw/Effect/Textures/t_fx_city_R5_11_gp.png',
          'res_size': 65740,
          'res_compressed_size': 33764
        },
        {
          'asset_path': 'Assets/ResourcesRaw/Effect/Textures/t_fx_city_R5_10_gp.png',
          'res_size': 65740,
          'res_compressed_size': 33764
        },
        {
          'asset_path': 'Assets/ResourcesRaw/Effect/Textures/t_fx_city_R5_09_gp.png',
          'res_size': 65740,
          'res_compressed_size': 33764
        },
        {
          'asset_path': 'Assets/ResourcesRaw/Effect/Textures/t_fx_city_R5_08_gp.png',
          'res_size': 65740,
          'res_compressed_size': 33764
        },
        {
          'asset_path': 'Assets/ResourcesRaw/Effect/Textures/t_fx_city_R5_07_gp.png',
          'res_size': 65740,
          'res_compressed_size': 33764
        },
        {
          'asset_path': 'Assets/ResourcesRaw/Effect/Textures/t_fx_city_R5_06_gp.png',
          'res_size': 65740,
          'res_compressed_size': 33764
        },
        {
          'asset_path': 'Assets/ResourcesRaw/Effect/Textures/t_fx_city_R5_05_gp.png',
          'res_size': 65740,
          'res_compressed_size': 33764
        },
        {
          'asset_path': 'Assets/ResourcesRaw/Effect/Textures/t_fx_city_R5_04_gp.png',
          'res_size': 65740,
          'res_compressed_size': 33764
        },
        {
          'asset_path': 'Assets/ResourcesRaw/Effect/Textures/t_fx_city_R5_03_gp.png',
          'res_size': 65740,
          'res_compressed_size': 33764
        },
        {
          'asset_path': 'Assets/ResourcesRaw/Effect/Textures/t_fx_city_R5_02_gp.png',
          'res_size': 65740,
          'res_compressed_size': 33764
        },
        {
          'asset_path': 'Assets/ResourcesRaw/Player/Pokeball/Mat_Tex/t_d_pokeball_lv3.tga',
          'res_size': 65740,
          'res_compressed_size': 33764
        },
        {
          'asset_path': 'Assets/ResourcesRaw/Guide/Animation/timeline05/t_d_city_BG_lv3.png',
          'res_size': 65740,
          'res_compressed_size': 33764
        },
        {
          'asset_path': 'Assets/ResourcesRaw/Scene/Lobby/lobby_maincity_open/Model/sm_sce_maincityop_ship05_lv3.fbx',
          'res_size': 63385,
          'res_compressed_size': 33764
        },
        {
          'asset_path': 'Assets/ResourcesRaw/Scene/Lobby/lobby_maincity_open/Model/sm_sce_maincityop_ship02c_lv3.fbx',
          'res_size': 59801,
          'res_compressed_size': 33764
        },
        {
          'asset_path': 'Assets/ResourcesRaw/Scene/Lobby/lobby_avatar/0815_cinderace/lobby_081501_pirate/Ani/ani_idle_027800_03.anim',
          'res_size': 49561,
          'res_compressed_size': 33764
        },
        {
          'asset_path': 'Assets/ResourcesRaw/Heroes/0025_Pikachu/00/Ani/ani_guideidle_lob_0025.anim',
          'res_size': 43724,
          'res_compressed_size': 33764
        },
        {
          'asset_path': 'Assets/ResourcesRaw/Scene/Lobby/lobby_avatar/0815_cinderace/lobby_081501_pirate/Ani/ani_idle_027800_01.anim',
          'res_size': 41881,
          'res_compressed_size': 33764
        },
        {
          'asset_path': 'Assets/ResourcesRaw/Scene/Lobby/lobby_avatar/0815_cinderace/lobby_081501_pirate/Ani/ani_idle_027800_06.anim',
          'res_size': 40960,
          'res_compressed_size': 16882
        },
        {
          'asset_path': 'Assets/ResourcesRaw/Scene/Lobby/lobby_avatar/0815_cinderace/lobby_081501_pirate/Ani/ani_idle_027800_02.anim',
          'res_size': 40960,
          'res_compressed_size': 16882
        },
        {
          'asset_path': 'Assets/ResourcesRaw/Scene/Lobby/lobby_avatar/0815_cinderace/lobby_081501_pirate/Ani/ani_idle_027800_05.anim',
          'res_size': 40448,
          'res_compressed_size': 16882
        },
        {
          'asset_path': 'Assets/ResourcesRaw/Scene/Lobby/lobby_maincity_open/Model/sm_sce_maincityop_ship02e_lv3.fbx',
          'res_size': 36352,
          'res_compressed_size': 16882
        },
        {
          'asset_path': 'Assets/ResourcesRaw/Scene/Lobby/lobby_avatar/0815_cinderace/lobby_081501_pirate/AniFBX/rig_lob_027800_lv1.FBX',
          'res_size': 36147,
          'res_compressed_size': 16882
        },
        {
          'asset_path': 'Assets/ResourcesRaw/Heroes/0025_Pikachu/00/Mat_Tex/t_mroe_lob_0025eye_lv3.tga',
          'res_size': 32972,
          'res_compressed_size': 16882
        },
        {
          'asset_path': 'Assets/ResourcesRaw/Heroes/0025_Pikachu/00/Mat_Tex/t_d_lob_0025eye_lv3.tga',
          'res_size': 32972,
          'res_compressed_size': 16882
        },
        {
          'asset_path': 'Assets/ResourcesRaw/Heroes/0025_Pikachu/00/Ani/ani_touch_lob_0025.anim',
          'res_size': 31027,
          'res_compressed_size': 16882
        },
        {
          'asset_path': 'Assets/ResourcesRaw/NPC/001_ProfessorPhorus/00/Ani/avtmsk_face_001.mask',
          'res_size': 19660,
          'res_compressed_size': 16882
        },
        {
          'asset_path': 'Assets/ResourcesRaw/Scene/Lobby/lobby_maincity_open/Model/sm_sce_maincityop_ship02d_lv3.fbx',
          'res_size': 17612,
          'res_compressed_size': 16882
        },
        {
          'asset_path': 'Assets/ResourcesRaw/Effect/Model/sm_fx_guide_maincity_qiu_01_xh.fbx',
          'res_size': 17305,
          'res_compressed_size': 16882
        },
        {
          'asset_path': 'Assets/ResourcesRaw/Guide/Animation/timeline06/t_NpcGuideTL6_ball.png',
          'res_size': 17100,
          'res_compressed_size': 16882
        },
        {
          'asset_path': 'Assets/ResourcesRaw/Effect_Lobby/Textures/t_fx_guide_maincity_qiu_05_xh.png',
          'res_size': 16588,
          'res_compressed_size': 16882
        },
        {
          'asset_path': 'Assets/ResourcesRaw/Effect_Lobby/Textures/t_fx_guide_maincity_qiu_02_xh.png',
          'res_size': 16588,
          'res_compressed_size': 16882
        },
        {
          'asset_path': 'Assets/ResourcesRaw/Effect_Lobby/Textures/t_fx_guide_maincity_qiu_01_xh.png',
          'res_size': 16588,
          'res_compressed_size': 16882
        },
        {
          'asset_path': 'Assets/ResourcesRaw/Effect_Lobby/Textures/t_fx_lob_066302_trail_04_gp.png',
          'res_size': 16588,
          'res_compressed_size': 16882
        },
        {
          'asset_path': 'Assets/ResourcesRaw/Scene/Lobby/lobby_avatar/0815_cinderace/lobby_081501_pirate/Texture/t_d_sce_027800body_lv1.tga',
          'res_size': 16588,
          'res_compressed_size': 16882
        },
        {
          'asset_path': 'Assets/ResourcesRaw/NPC/0555_jiangbei/07/Mat_Tex/t_matcap_Jiangbei07a_lv3.tga',
          'res_size': 16588,
          'res_compressed_size': 16882
        },
        {
          'asset_path': 'Assets/ResourcesRaw/NPC/001_ProfessorPhorus/00/Mat_Tex/t_tex_lob_npc01hair_lv3.tga',
          'res_size': 16588,
          'res_compressed_size': 16882
        },
        {
          'asset_path': 'Assets/ResourcesRaw/NPC/001_ProfessorPhorus/00/Mat_Tex/t_m_lob_npc01hair_lv1.tga',
          'res_size': 16588,
          'res_compressed_size': 16882
        },
        {
          'asset_path': 'Assets/ResourcesRaw/Effect/Textures/t_fx_device_mask_04_pjh.png',
          'res_size': 16588,
          'res_compressed_size': 16882
        },
        {
          'asset_path': 'Assets/ResourcesRaw/Effect/Textures/t_fx_0378_noise_01_zz.png',
          'res_size': 16588,
          'res_compressed_size': 16882
        },
        {
          'asset_path': 'Assets/ResourcesRaw/Effect/Textures/t_fx_0037_trail_01_wxm.png',
          'res_size': 16588,
          'res_compressed_size': 16882
        },
        {
          'asset_path': 'Assets/ResourcesRaw/NPC/001_ProfessorPhorus/00/Mat_Tex/t_lob_npc01bianse_1.tga',
          'res_size': 16588,
          'res_compressed_size': 16882
        },
        {
          'asset_path': 'Assets/ResourcesRaw/NPC/001_ProfessorPhorus/00/Mat_Tex/t_lob_npc01bianse.tga',
          'res_size': 16588,
          'res_compressed_size': 16882
        },
        {
          'asset_path': 'Assets/ResourcesRaw/Effect/Textures/t_fx_city_R5_17_gp.png',
          'res_size': 16588,
          'res_compressed_size': 16882
        },
        {
          'asset_path': 'Assets/ResourcesRaw/Effect/Textures/t_fx_city_R5_01_gp.png',
          'res_size': 16588,
          'res_compressed_size': 16882
        },
        {
          'asset_path': 'Assets/ResourcesRaw/Heroes/0025_Pikachu/00/Mat_Tex/t_m_lob_0025eye_lv3.tga',
          'res_size': 8396,
          'res_compressed_size': 0
        },
        {
          'asset_path': 'Assets/ResourcesRaw/Effect/Animation/ani_fx_maincity_poster_01_gp.anim',
          'res_size': 7577,
          'res_compressed_size': 0
        },
        {
          'asset_path': 'Assets/ResourcesRaw/Effect/Model/sm_fx_maincity_zhengyan_mesh_01_gp.FBX',
          'res_size': 7475,
          'res_compressed_size': 0
        },
        {
          'asset_path': 'Assets/ResourcesRaw/Player/Pokeball/Ani/ani_ball_lob_001.anim',
          'res_size': 6656,
          'res_compressed_size': 0
        },
        {
          'asset_path': 'Assets/ResourcesRaw/Scene/Lobby/lobby_maincity_open/Model/sm_sce_maincityop_ship04c_lv3.fbx',
          'res_size': 6041,
          'res_compressed_size': 0
        },
        {
          'asset_path': 'Assets/ResourcesRaw/Scene/Lobby/lobby_maincity_open/Model/sm_sce_maincityop_ship04b_lv3.fbx',
          'res_size': 6041,
          'res_compressed_size': 0
        },
        {
          'asset_path': 'Assets/ResourcesRaw/Scene/Lobby/lobby_maincity_open/Model/sm_sce_maincityop_ship04a_lv3.fbx',
          'res_size': 5939,
          'res_compressed_size': 0
        },
        {
          'asset_path': 'Assets/ResourcesRaw/Effect/Textures/t_fx_trainerlevelup_light_01_pjh.png',
          'res_size': 4300,
          'res_compressed_size': 0
        },
        {
          'asset_path': 'Assets/ResourcesRaw/Effect/Textures/t_fx_bglogin_ribbon_01_pjh.tga',
          'res_size': 4300,
          'res_compressed_size': 0
        },
        {
          'asset_path': 'Assets/ResourcesRaw/Effect/Textures/t_fx_city_R5_mask_01_gp.png',
          'res_size': 4300,
          'res_compressed_size': 0
        },
        {
          'asset_path': 'Assets/ResourcesRaw/Effect/Model/sm_fx_bglogin_ribbon_01_pjh.FBX',
          'res_size': 2662,
          'res_compressed_size': 0
        },
        {
          'asset_path': 'Assets/ResourcesRaw/Scene/Lobby/lobby_maincity_open/Model/sm_sce_maincityop_ship02f_lv3.fbx',
          'res_size': 2355,
          'res_compressed_size': 0
        },
        {
          'asset_path': 'Assets/ResourcesRaw/Effect/Textures/t_fx_catchpokemoon_spark_01.png',
          'res_size': 2252,
          'res_compressed_size': 0
        },
        {
          'asset_path': 'Assets/ResourcesRaw/Scene/Lobby/lobby_maincity_open/Model/sm_sce_maincityop_ship04f_lv3.fbx',
          'res_size': 2252,
          'res_compressed_size': 0
        },
        {
          'asset_path': 'Assets/ResourcesRaw/Scene/Lobby/lobby_maincity_open/Model/sm_sce_maincityop_ship04e_lv3.fbx',
          'res_size': 2150,
          'res_compressed_size': 0
        },
        {
          'asset_path': 'Assets/ResourcesRaw/Scene/Lobby/lobby_maincity_open/Model/sm_sce_maincityop_ship04k_lv3.fbx',
          'res_size': 1638,
          'res_compressed_size': 0
        },
        {
          'asset_path': 'Assets/ResourcesRaw/Scene/Lobby/lobby_maincity_open/Model/sm_sce_maincityop_ship04j_lv3.fbx',
          'res_size': 1638,
          'res_compressed_size': 0
        },
        {
          'asset_path': 'Assets/ResourcesRaw/Scene/Lobby/lobby_maincity_open/Model/sm_sce_maincityop_ship04h_lv3.fbx',
          'res_size': 1638,
          'res_compressed_size': 0
        },
        {
          'asset_path': 'Assets/ResourcesRaw/Scene/Lobby/lobby_maincity_open/Model/sm_sce_maincityop_ship02a_lv3.fbx',
          'res_size': 1536,
          'res_compressed_size': 0
        },
        {
          'asset_path': 'Assets/ResourcesRaw/Effect/Model/sm_fx_scene_0815_plane_02_zx.FBX',
          'res_size': 1536,
          'res_compressed_size': 0
        },
        {
          'asset_path': 'Assets/ResourcesRaw/Scene/Lobby/lobby_maincity_open/Model/sm_sce_maincityop_ship04g_lv3.fbx',
          'res_size': 1536,
          'res_compressed_size': 0
        },
        {
          'asset_path': 'Assets/ResourcesRaw/Effect/Textures/t_fx_maincity_zhengyan_mask_01_gp.png',
          'res_size': 1228,
          'res_compressed_size': 0
        },
        {
          'asset_path': 'Assets/ResourcesRaw/Effect/Textures/t_fx_catchpokemoon_glow_01.png',
          'res_size': 1228,
          'res_compressed_size': 0
        },
        {
          'asset_path': 'Assets/ResourcesRaw/Effect/Textures/t_fx_catchpokemoon_ball_01.png',
          'res_size': 1228,
          'res_compressed_size': 0
        },
        {
          'asset_path': 'Assets/ResourcesRaw/Effect/Textures/t_fx_0280_guanghuang_01_gp.png',
          'res_size': 1228,
          'res_compressed_size': 0
        },
        {
          'asset_path': 'Assets/ResourcesRaw/NPC/0555_jiangbei/07/Mat_Tex/t_matcap_Jiangbei07b_lv3.tga',
          'res_size': 1228,
          'res_compressed_size': 0
        },
        {
          'asset_path': 'Assets/ResourcesRaw/NPC/001_ProfessorPhorus/00/Mat_Tex/t_i_lob_npc01body_lv1.tga',
          'res_size': 1228,
          'res_compressed_size': 0
        },
        {
          'asset_path': 'Assets/ResourcesRaw/Effect/Textures/t_fx_scoredead_ring_01.tga',
          'res_size': 1228,
          'res_compressed_size': 0
        },
        {
          'asset_path': 'Assets/ResourcesRaw/Effect/Textures/t_fx_0092_mask_05_wxc.png',
          'res_size': 1228,
          'res_compressed_size': 0
        },
        {
          'asset_path': 'Assets/ResourcesRaw/Effect/Textures/t_fx_0004_noise_01_tjj.tga',
          'res_size': 1228,
          'res_compressed_size': 0
        },
        {
          'asset_path': 'Assets/ResourcesRaw/Player/Female/lob_50000/Mat_Tex/t_d_lob_50000_lv3.tga',
          'res_size': 1228,
          'res_compressed_size': 0
        },
        {
          'asset_path': 'Assets/ResourcesRaw/Effect/Textures/t_fx_0037_star_04_lx.png',
          'res_size': 1228,
          'res_compressed_size': 0
        },
        {
          'asset_path': 'Assets/ResourcesRaw/Effect/Textures/t_fx_0004_mask_01_cj.png',
          'res_size': 1228,
          'res_compressed_size': 0
        },
        {
          'asset_path': 'Assets/ResourcesRaw/Effect/Textures/t_fx_0001_flare_06.png',
          'res_size': 1228,
          'res_compressed_size': 0
        },
        {
          'asset_path': 'Assets/ResourcesRaw/Scene/Lobby/lobby_maincity_open/Model/sm_sce_maincityop_ship02b_lv3.fbx',
          'res_size': 1024,
          'res_compressed_size': 0
        },
        {
          'asset_path': 'Assets/ResourcesRaw/Scene/Lobby/lobby_maincity_open/Model/sm_sce_maincityop_ship03_lv3.fbx',
          'res_size': 614,
          'res_compressed_size': 0
        },
        {
          'asset_path': 'Assets/ResourcesRaw/Effect/DeleteTexture/t_fx_delete_0025_mask_01.png',
          'res_size': 512,
          'res_compressed_size': 0
        },
        {
          'asset_path': 'Assets/ResourcesRaw/Effect/Textures/t_fx_0661_glow_01_cj.png',
          'res_size': 512,
          'res_compressed_size': 0
        },
        {
          'asset_path': 'Assets/ResourcesRaw/Effect/Textures/t_fx_0661_glow_01.png',
          'res_size': 512,
          'res_compressed_size': 0
        },
        {
          'asset_path': 'Assets/ResourcesRaw/Effect/Textures/t_fx_0037_glow_01_xz.tga',
          'res_size': 512,
          'res_compressed_size': 0
        },
        {
          'asset_path': 'Assets/ResourcesRaw/Effect/Textures/t_fx_0025_wave_04.TGA',
          'res_size': 512,
          'res_compressed_size': 0
        },
        {
          'asset_path': 'Assets/ResourcesRaw/Effect/Textures/t_fxui_minimap_icon_ring_01.tga',
          'res_size': 409,
          'res_compressed_size': 0
        }
      ]

    }
  }
}
</script>
