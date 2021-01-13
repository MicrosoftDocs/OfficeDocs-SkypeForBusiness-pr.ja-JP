---
title: Skype for Business Server を使用した Lync VDI プラグインの展開
ms.author: v-cichur
author: cichur
manager: serdars
ms.reviewer: krishra
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 11d3bd5d-6dd3-471c-b842-b072fa197714
description: このトピックでは、リモート仮想デスクトップへの接続中に Skype for Business を使用するための展開手順について説明します。
ms.openlocfilehash: f7ff99045c861c4435675d9e9e86deaedd499c10
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49805937"
---
# <a name="deploy-the-lync-vdi-plug-in-with-skype-for-business-server"></a>Skype for Business Server を使用した Lync VDI プラグインの展開
 
このトピックでは、リモート仮想デスクトップへの接続中に Skype for Business を使用するための展開手順について説明します。 計画に関する考慮事項については [、VDI 環境での Skype for Business の計画に関する説明を参照してください](../../plan-your-deployment/clients-and-devices/vdi-environments.md)。
  
仮想デスクトップ インフラストラクチャ (VDI) 環境は、セキュリティとコンプライアンスの問題が特に重要である一部の組織で使用されています。 ユーザーは、ローカル Windows コンピューター上にいて、仮想デスクトップ上のクライアントを使用しています。 このような接続で Skype for Business を使用するには、追加の VDI プラグイン ソフトウェアが必要です。
  
VDI プラグイン コンポーネントには、Microsoft が提供するソリューションと Citrix が提供するソリューションの 2 つがあります。 Microsoft では、新しい展開で新しい HDX RealTime Optimization Pack ソリューションの使用をお勧めしますが、ライフサイクルの残りの部分では元の Lync VDI プラグインを引き続きサポートします。 
  
このトピックでは、Windows 7 および Windows 8 または Windows Server 2008 でのみサポートされ、Lync 2013 または Skype for Business クライアントのみをサポートする Microsoft Lync VDI プラグインの展開に関する詳細について説明します。 このプラグインを更新する予定はありません。 [ただし、Citrix HDX RealTime Optimization Pack](../../plan-your-deployment/clients-and-devices/vdi-environments.md#Citrix_RT) for Skype for Business は必要に応じて更新されます。
  
## <a name="prepare-your-environment-for-the-lync-vdi-plug-in"></a>Lync VDI プラグインの環境を準備する
<a name="Prepare_vdi"> </a>

1. Skype for Business Server で、すべての Lync VDI プラグイン ユーザーに対して EnableMediaRedirection が TRUE に設定されている必要があります。 詳細については [、New-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/new-csclientpolicy?view=skype-ps) コマンドレットと [Set-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/set-csclientpolicy?view=skype-ps) コマンドレットのヘルプ トピックを参照してください。
    
2. データ センター サーバーで、すべての仮想デスクトップに Skype for Business クライアントをインストールします。
    
3. ローカル コンピューターに、Lync VDI プラグインをインストールします。
    
    ユーザーは、ヘッドセットや Web カメラのようなデバイスをローカル コンピューターに接続する必要があります。
    
## <a name="configure-remote-desktop-connection-settings"></a>リモート デスクトップ接続の設定を構成する
<a name="Prepare_vdi"> </a>

Lync VDI プラグインのリモート デスクトップ接続を準備するには、ローカル コンピューターで次の手順を実行します。
  
1. ローカル コンピューターがローカル コンピューターを実行しているWindows 8、この手順をスキップします。 ローカル コンピューターで Windows 7 SP1 を実行している場合は、リモート デスクトップ Windows 8 クライアントの最新バージョン [をインストールします](https://go.microsoft.com/fwlink/p/?LinkId=268032)。
    
2. [**スタート**]、[**リモート デスクトップ接続**] の順にクリックして、リモート デスクトップ サービス クライアントを起動します。
    
3. [**オプション**] をクリックします。
    
4. [**ローカル リソース**] タブをクリックします。[**リモート オーディオ**] の下にある [**設定**] をクリックし、次の手順を実行します。
    
   - [**リモート オーディオ再生**] の下の [**このコンピュータで再生**] を選択します。
    
   - [**リモート オーディオ録音**] の下の [**録音しない**] を選択します。
    
   - [**OK**] をクリックします。
    
5. [**エクスペリエンス**] タブをクリックします。[**パフォーマンス**] の下にある [**ビットマップのキャッシュを保持**] チェック ボックスをオフにします。
    
6. [全般] **タブをクリック** します。コンピューター **で**、仮想デスクトップの名前を入力し、[接続] をクリック **します**。 
    
## <a name="sign-in-and-use-skype-for-business-on-the-virtual-desktop"></a>仮想デスクトップでサインインして Skype for Business を使用する
<a name="SfB_signin"> </a>

Lync VDI プラグインを有効にした後、ユーザーは仮想デスクトップで Skype for Business にサインインするときに次の手順を実行します。
  
1. ユーザーは、仮想デスクトップで実行されている Skype for Business クライアントに自分の資格情報を入力します。
    
2. Skype for Business が Lync VDI プラグインを検出すると、Skype for Business はユーザーに資格情報の再入力を求めるメッセージを表示します。 このダイアログ ボックスでは、ユーザーが後でサインインする際に資格情報を入力する必要が生じないので、[パスワードを保存する] チェック ボックスをオンにすることをお勧めします。
    
3. Skype for Business は、Lync VDI プラグインとのペアリングを開始します。 この場合、クライアントは Skype for Business ステータス バーに 2 つのアイコンを表示します。 左下のアイコンは、オーディオ デバイスが使用できない状態を示し、右下の点滅するアイコンは VDI ペアリングが進行中を示します。a. VDI ペアリングが成功すると、アイコンが変更され、呼び出しに使用されるオーディオ デバイスと VDI ペアリングの成功を示します。b. これで、ユーザーは、ローカル コンピューターに接続されている Skype for Business 互換デバイスで自分のプレゼンスを確認し、通常どおり通話を行って応答できます。
    
## <a name="troubleshoot-the-lync-vdi-plug-in"></a>Lync VDI プラグインのトラブルシューティング
<a name="tshoot_VDI"> </a>

Lync VDI プラグインのインストール後に問題が発生した場合は、以下のセクションを参照してください。
  
### <a name="issues-with-installing-the-lync-vdi-plug-in"></a>Lync VDI プラグインのインストールに関する問題

Lync VDI プラグインのインストールに問題がある場合は、次のチェック を行います。
  
- TEMP および TMP システム変数で指定したフォルダーに十分な容量がある。
    
- 書き込み保護がオフになっている。 手順については、デバイスの製造元のドキュメントを参照してください。
    
### <a name="troubleshooting-issues-with-pairing"></a>ペアリングに関する問題のトラブルシューティング

Lync VDI プラグインのペアリングが失敗すると、右下のペアリング アイコンは次のように赤い "X" で表示されます。 
  
エラーの考えられる原因と、問題を修正するために実行できる操作を次に示します。 
  
- **ユーザーがサインインの際に入力した資格情報が正しくない。**
    
    ユーザーは Skype for Business からサインアウトし、正しい資格情報でもう一度サインインする必要があります。 ペアリングのダイアログ ボックスが再表示され、ペアリングに成功したかどうかが表示されます。
    
- **リモート デスクトップ クライアントの別のインスタンスが実行している。**
    
    Windows でリモート デスクトップ接続を使用している場合、ユーザーは次の操作を行う必要があります。
    
1. タスク マネージャーを起動します。**Alt+Ctrl+Del** キーを押し、[**タスク マネージャーの起動**] をクリックします。
    
2. [**プロセス**] タブをクリックし、リスト内で **mstsc.exe** という名前のすべてのプロセスを見つけます。
    
3. 各 **mstsc.exe** プロセスを強調表示し、[**プロセスの終了**] をクリックします。 
    
4. 新しいリモート デスクトップ セッションを起動して、再び接続を試みます。 
    
- **必要なファイルが適切にインストールされていない。**
    
    プラグインがローカル コンピューターにインストールされた後、これらのファイルが C:\Program Files\Microsoft Office\Office15 (または適切なドライブ文字) の下に存在する必要があります。
    
  - LyncVdiPlugin.dll
    
  - UcVdi.dll
    
- **Skype for Business クライアントがローカル コンピューターで実行されている。**
    
    Lync VDI プラグインを使用するには、Skype for Business クライアントがローカル コンピューターで実行されていない必要があります。実行しないと、ペアリングが失敗します。 ベスト プラクティスとして、ユーザーはローカル コンピューターに Skype for Business クライアントをインストールしなけずにしてください。
    
## <a name="see-also"></a>関連項目
<a name="tshoot_VDI"> </a>

[VDI 環境での Skype for Business の計画](../../plan-your-deployment/clients-and-devices/vdi-environments.md)
