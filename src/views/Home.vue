<template>
  <div class="mx-2 my-10 sm:mx-60 my-10">
    <div class="header">
			<img src="@/assets/images/logo-icon.png"/>
      <br />
			<div class="header-title">
				<div class="title-bold">目の不自由なお客様</div>
				<div class="title-normal">視覚に障がいをお持ちで、WEBページやチラシ等の閲覧にお困りの方へ。アフラックの各情報を音声コードUni-Voice」で確認いただけます。視覚障がい者向けアプリ「Uni-Voice Blind」をダウンロードいただきご活用ください。本ページに情報が追加された際には、上記アプリのプッシュ通知機能にてご案内いたします。</div>
			</div>
		</div>

    <div class="content">
      <div class="mb-5">
        <div class="text-left">組み込みアドレスを入力してください。</div>
        <input class="input-custom" type="text" v-model="iframeCode" style="width: 100%;"/>
      </div>
      <div v-if="iframeCode" v-html="iframeCode" class="iframe-container"/>
    </div>

    
    <div class="footer">
			<div>Uni-Voiceとは：2次元コード「音声コードUni-Voice」を専用のスマートフォンアプリで読み取り、文字情報を読み上げると同時にテキストにて画面表示されるアプリ機能です。</div>
			<div class="grid grid-rows- grid-flow-col gap-4 my-5">
				<div class="flex flex-col justify-center text-right">
					<div style="color: #00B7FF;">視覚障がい者向けアプリ</div>
					<div style="color: #00B7FF;">Uni-Voice Blind（iOS版）</div>
				</div>
				<div class="text-left">
					<img onclick="redirectToAppStore()" src="@/assets/images/univoice-icon.png" style="width: 100px; height: auto; margin-right: 15px;" />
					<img onclick="redirectToAppStore()" src="@/assets/images/appstore-icon.png" style="width: 100px; height: auto;" />
				</div>
			</div>
			<div class="text-justify">
				<div>AppleとAppleのロゴは、米国およびその他の国で登録されたApple Inc.の商標です。</div>
				<div>App Storeは、Apple Inc.のサービスマークです。</div>
				<div>Google Play および Google Play ロゴは、Google LLC の商標です。</div>
			</div>
		</div>

  </div>
</template>

<script>
export default {
  data () {
    return {
      iframeCode: ''
    }
  }
}
</script>

<style scoped lang="scss">
.header {
  .header-title {
    .title-bold {
      @apply font-bold;
      @apply text-center;
      @apply text-xl;
      @apply mb-2;
    }
    .title-normal {
      @apply text-justify;
    }
  }
}

.content {
  @apply my-10; 

  .input-custom {
    border: 1px solid #d9d9d9; 
    border-radius: 4px;
    padding: 5px 10px;
  }

  .iframe-container {
    width: 100%; 
    height: 400px;
    border: 1px solid #d9d9d9;
    border-radius: 4px;
  }
}

.footer {
  @apply text-justify;
}
</style>