<script setup>
import Title from "./components/Title.vue"
import Menu from "./components/Menu.vue"
import MathContents from "./components/math/MathContents.vue"
import Card from "./components/Card.vue"
import Tab from "./components/Tab.vue"
import Article from "./components/Article.vue"
import Footer from "./components/Footer.vue"

function presentation(id){
    let content = document.getElementById(id);
    let elem = document.getElementById("presentation-area");
    elem.innerHTML = content.innerHTML;
  }

</script>
<template>
  <div class="bg">
    <!-- タイトル -->
    <Title></Title>
    <Tab>
       <template v-slot:FirstTabTitle>News</template>
       <template v-slot:SecondTabTitle>コンピュータ</template>
       <template v-slot:ThirdTabTitle>数学</template>
       <template v-slot:ForthTabTitle>哲学</template>
       <template v-slot:FifthTabTitle>音楽</template>

       <template v-slot:FirstTab>
        <div>
          <Card class="card"> 
            <template v-slot:author> 音無 恠環</template>
            <template v-slot:date> 2025/6/14 </template>
            <template v-slot:tags>                   
              <ul>
                  <li><a href="#">test</a></li>
                  <li><a href="#">test</a></li>
              </ul>
            </template>
            <template v-slot:title>テスト</template>
            <template v-slot:subtitle>テスト</template>
            <template v-slot:ReadMore><a href="#presentation-area" @click="presentation('article_20260614');">Read More</a></template>
            <template v-slot:article> 
              <div id="article_20260614">
                <Article>
                  <template v-slot:title>テスト</template>
                  <template v-slot:subtitle>テスト</template>
                  <template v-slot:content>テスト</template>
                </Article>
              </div>
            </template>
            テスト 
          </Card>
          <Card class="card"> テスト </Card>
          <Card class="card"> テスト </Card>
        </div>
       </template>

       <template v-slot:SecondTab>
           <Card class="card"> 
            <template v-slot:author> 音無 恠環</template>
            <template v-slot:date> 2025/6/14 </template>
            <template v-slot:tags>                   
              <ul>
                  <li><a href="#">test</a></li>
                  <li><a href="#">test</a></li>
              </ul>
            </template>
            <template v-slot:title>テスト</template>
            <template v-slot:subtitle>テスト</template>
            テスト 
          </Card>
       </template>
       <template v-slot:ThirdTab> </template>
       <template v-slot:ForthTab> </template>
       <template v-slot:FifthTab> 
          <iframe width="100%" height="450" scrolling="no" frameborder="no" allow="autoplay" src="https://w.soundcloud.com/player/?url=https%3A//api.soundcloud.com/playlists/2036581299&color=%23ff5500&auto_play=false&hide_related=false&show_comments=true&show_user=true&show_reposts=false&show_teaser=true"></iframe><div style="font-size: 10px; color: #cccccc;line-break: anywhere;word-break: normal;overflow: hidden;white-space: nowrap;text-overflow: ellipsis; font-family: Interstate,Lucida Grande,Lucida Sans Unicode,Lucida Sans,Garuda,Verdana,Tahoma,sans-serif;font-weight: 100;"><a href="https://soundcloud.com/kewa-otonaki" title="Kewa Otonaki" target="_blank" style="color: #cccccc; text-decoration: none;">Kewa Otonaki</a> · <a href="https://soundcloud.com/kewa-otonaki/sets/my-songs" title="My songs" target="_blank" style="color: #cccccc; text-decoration: none;">My songs</a></div>
       </template>
    </Tab>

    <div id="presentation-area">
      aaaaaa

    </div>    
    <!-- コンピュータ関連 -->    
    <!-- コンピュータアーキテクチャ -->
       <!-- 論理回路 -->
    <!-- コンパイラ -->
       <!-- 字句解析 -->
       <!-- 構文解析 -->
       <!-- 意味解析 -->
       <!-- 最適化 --> <!-- LLVM -->
    <!-- プログラミング -->
       <!-- C言語 -->
       <!-- オブジェクト指向 -->
       <!-- 関数型言語 -->
    <!-- ソフトウェアのビルド -->
       <!-- ビルドシステム -->
    <!-- オペレーティングシステム -->
       <!-- プロセス管理 -->
       <!-- リソース管理 -->
       <!-- ファイル管理 -->
       <!-- システムコール -->
    <!-- 関係データベース -->
      <!-- 有名なデータベース -->
      <!-- SQL -->
      <!-- データベースの管理方法 -->
    <!-- コンピュータネットワーク -->
       <!-- LAN-->
       <!-- インターネット -->
       <!-- World Wide Web(WWW)-->

    <!-- セキュリティ -->
    <!-- ソフトウェア開発 -->
    <!-- UI/UX -->
    <!-- OSS(オープンソースソフトウェア) -->
    
    <!-- 数学関連 -->
    <!-- 基礎として計算と論理-->
    <!-- 数と図形 -->
    <!-- 関数 -->
    <!-- 方程式 -->
    <!-- ベクトルと行列 -->
    <!-- 線形代数I -->
    <!-- 微積分 -->
       <!-- 実数論 -->
       <!-- 関数 -->
       <!-- 微分(一変数) -->
       <!-- 積分(一変数) -->
       <!-- 多変数関数 -->
       <!-- 微分(多変数) -->
       <!-- 積分(多変数) -->
    <!-- 論理と証明 -->
       <!-- (一階)命題論理 -->
          <!-- 統語論 -->
          <!-- 意味論 -->
          <!-- 推論 -->
        <!-- (一階)述語論理 -->
           <!-- 統語論 -->
           <!-- 意味論 -->
           <!-- 推論 -->
        <!-- 証明論 -->
           <!-- ヒルベルト流 -->
           <!-- 自然演繹 -->
           <!-- シーケント計算 -->
           <!-- カット除去定理 -->
           <!-- 完全性と健全性 -->
           <!-- 完全性定理 -->
           <!-- 不完全性定理 -->
           <!-- 型理論 -->
             <!-- 分岐型理論 -->
             <!-- 単純型理論 -->
             <!-- 依存型理論 -->
             <!-- ホモトピー型理論 -->
    <!-- 集合と位相 -->
       <!-- 集合 -->
       <!-- 濃度 -->
       <!-- 順序数 -->
       <!-- 位相空間 -->
       <!-- 距離空間 -->
       <!-- 位相空間の性質 -->
          <!-- コンパクト -->
          <!-- ハウスドルフ -->
          <!-- 連結 -->
          <!-- 同相 -->
    <!-- 多様体 -->
       <!-- 位相多様体 -->
       <!-- 微分可能多様体 -->
    <!-- 測度と確率-->
       <!-- 測度 -->
       <!-- 確率論 -->
    <!-- 群・環・加群・体-->
       <!-- 群論 -->
       <!-- 環論 -->
       <!-- 環上の加群 -->
       <!-- 体論 -->
    <!-- 線形代数II -->
       <!-- 代数的構造としてのベクトル空間 -->
       <!-- 線形写像 -->
         <!-- 準同型写像 -->
    <!-- ガロア理論 -->
       <!-- ガロアの主定理 -->
       <!-- アーベルの定理-->
       <!-- 代数学の基本定理 -->
    <!-- 微分幾何 -->
       <!-- リーマン多様体 -->
       <!-- 測地線 -->
    <!-- 層・圏・トポス -->
       <!-- 層 -->
       <!-- 圏 -->
       <!-- トポス -->
    <!-- 代数幾何 -->
       <!-- 代数多様体 -->
       <!-- スキーム -->
    <!-- 初等整数論 -->
       <!-- 整数 -->
       <!-- 数論的関数 -->
       <!-- 連分数 -->
       <!-- p進数 -->
    <!-- 代数的整数論 -->
       <!-- 代数的整数 -->
       <!-- 類体論 -->
    <!-- 数論幾何 -->
       <!-- ドリーニュの定理(ヴェイユ予想) -->
    <!-- リー群論 -->
       <!-- リー群 -->

    <!-- 番外編: 計算と論理 -->
       <!-- カリーハワード同型対応 -->
  </div>
  <Footer></Footer>
</template>

<style scoped>
/* CSSアニメーション */

.card {
    display: inline-block;
    width : 500px;
    margin : 30px;
  }

</style>

<script scoped>
export default {
  mounted() {

    function slide(){
      const track = this.$refs.slideTrack;
      console.log("My log:" + track); // Access the DOM element
      let index = 0;

      setInterval(() => {
        index = (index + 1) % 3; // 3はアイテム数
        track.style.transform = `translateX(-${index * 300}px)`;
      }, 3000); // 3秒ごとにスライド
    }
  }
};
</script>