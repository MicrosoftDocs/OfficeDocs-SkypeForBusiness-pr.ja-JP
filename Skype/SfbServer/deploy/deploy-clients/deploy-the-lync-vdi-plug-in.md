---
title: Skype for Business Server を使用して Lync VDI プラグインを展開する
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
ms.openlocfilehash: 6db05fb3bcd9638a3181eb454de3a3097831b997
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51096001"
---
# <a name="deploy-the-lync-vdi-plug-in-with-skype-for-business-server"></a>Skype for Business Server を使用して Lync VDI プラグインを展開する
 
このトピックでは、リモート仮想デスクトップへの接続中に Skype for Business を使用するための展開手順について説明します。 計画に関する考慮事項は [、「VDI 環境での Skype for Business の計画」を参照してください](../../plan-your-deployment/clients-and-devices/vdi-environments.md)。
  
仮想デスクトップ インフラストラクチャ (VDI) 環境は、セキュリティとコンプライアンスの問題が特に重要である一部の組織で使用されています。 ユーザーはローカルの Windows コンピューター上にいて、仮想デスクトップ上でクライアントを使用しています。 このような接続で Skype for Business を使用するには、追加の VDI プラグイン ソフトウェアが必要です。
  
VDI プラグイン コンポーネントには、Microsoft が提供するソリューションと Citrix が提供するソリューションの 2 つのソリューションがあります。 Microsoft では、新しい展開で新しい HDX RealTime 最適化パック ソリューションを使用をお勧めしますが、そのライフサイクルの残りの期間、元の Lync VDI プラグインを引き続きサポートします。 
  
このトピックでは、Windows 7 および Windows 8 または Windows Server 2008 でのみサポートされ、Lync 2013 または Skype for Business クライアントのみをサポートする Microsoft Lync VDI プラグインの展開に関する詳細を説明します。 このプラグインを更新する予定はありません。 [ただし、Citrix HDX RealTime](../../plan-your-deployment/clients-and-devices/vdi-environments.md#Citrix_RT) Optimization Pack for Skype for Business は必要に応じて更新されます。
  
## <a name="prepare-your-environment-for-the-lync-vdi-plug-in"></a>Lync VDI プラグインの環境を準備する
<a name="Prepare_vdi"> </a>

1. Skype for Business Server で、すべての Lync VDI プラグイン ユーザーに対して EnableMediaRedirection が TRUE に設定されている必要があります。 詳細については [、New-CsClientPolicy](/powershell/module/skype/new-csclientpolicy?view=skype-ps) コマンドレットと [Set-CsClientPolicy](/powershell/module/skype/set-csclientpolicy?view=skype-ps) コマンドレットのヘルプ トピックを参照してください。
    
2. データ センター サーバーで、Skype for Business クライアントをすべての仮想デスクトップにインストールします。
    
3. ローカル コンピューターで、Lync VDI プラグインをインストールします。
    
    これで、ヘッドセットや Web カメラのようなデバイスをローカル コンピューターに接続する必要があります。
    
## <a name="configure-remote-desktop-connection-settings"></a>リモート デスクトップ接続の設定を構成する
<a name="Prepare_vdi"> </a>

Lync VDI プラグインのリモート デスクトップ接続を準備するには、ローカル コンピューターで次の手順を実行します。
  
1. ローカル コンピューターが実行されている場合Windows 8この手順をスキップします。 ローカル コンピューターで SP1 を使用して Windows 7 を実行している場合は、最新のバージョンWindows 8リモート デスクトップ サービス クライアント [をインストールします](/windows-server/remote/remote-desktop-services/clients/remote-desktop-clients)。
    
2. [**スタート**]、[**リモート デスクトップ接続**] の順にクリックして、リモート デスクトップ サービス クライアントを起動します。
    
3. [**オプション**] をクリックします。
    
4. [**ローカル リソース**] タブをクリックします。[**リモート オーディオ**] の下にある [**設定**] をクリックし、次の手順を実行します。
    
   - [**リモート オーディオ再生**] の下の [**このコンピュータで再生**] を選択します。
    
   - [**リモート オーディオ録音**] の下の [**録音しない**] を選択します。
    
   - [**OK**] をクリックします。
    
5. [**エクスペリエンス**] タブをクリックします。[**パフォーマンス**] の下にある [**ビットマップのキャッシュを保持**] チェック ボックスをオフにします。
    
6. [全般] **タブをクリック** します。[ **コンピューター]** で、仮想デスクトップの名前を入力し、[接続] を **クリックします**。 
    
## <a name="sign-in-and-use-skype-for-business-on-the-virtual-desktop"></a>仮想デスクトップでサインインして Skype for Business を使用する
<a name="SfB_signin"> </a>

Lync VDI プラグインが有効になると、ユーザーは仮想デスクトップで Skype for Business にサインインするときに次の手順に従います。
  
1. ユーザーは、仮想デスクトップ上で実行されている Skype for Business クライアントに資格情報を入力します。
    
2. Skype for Business が Lync VDI プラグインを検出すると、Skype for Business はユーザーに資格情報の再入力を求めるメッセージを表示します。 このダイアログ ボックスでは、ユーザーが後続のサインイン時に資格情報を入力する必要が生じないので、[パスワードを保存する] チェック ボックスをオンにすることをお勧めします。
    
3. Skype for Business は、Lync VDI プラグインとのペアリングを開始します。 その間、クライアントは Skype for Business の状態バーに 2 つのアイコンを表示します。 左下のアイコンは、オーディオ デバイスが使用できない状態を示し、右下の点滅アイコンは、VDI のペアリングが進行中である (a) を示します。 VDI のペアリングが成功すると、アイコンが変更され、通話に使用されるオーディオ デバイスと VDI ペアリングの成功 (b) が示されます。 これで、ユーザーは、ローカル コンピューターに接続されている Skype for Business 互換デバイスで自分のプレゼンスを確認し、通常どおり通話を行って応答できます。
    
## <a name="troubleshoot-the-lync-vdi-plug-in"></a>Lync VDI プラグインのトラブルシューティング
<a name="tshoot_VDI"> </a>

Lync VDI プラグインのインストール後に問題が発生した場合は、以下のセクションを参照してください。
  
### <a name="issues-with-installing-the-lync-vdi-plug-in"></a>Lync VDI プラグインのインストールに関する問題

Lync VDI プラグインのインストールに問題がある場合は、次の情報を確認してください。
  
- TEMP および TMP システム変数で指定したフォルダーに十分な容量がある。
    
- 書き込み保護がオフになっている。 手順については、デバイスの製造元のドキュメントを参照してください。
    
### <a name="troubleshooting-issues-with-pairing"></a>ペアリングに関する問題のトラブルシューティング

Lync VDI プラグインのペアリングが失敗すると、右下のペアリング アイコンは、次のように赤い "X" として表示されます。 
  
次に、エラーの考えられる理由と、問題を修正するために実行できるアクションを示します。 
  
- **ユーザーがサインインの際に入力した資格情報が正しくない。**
    
    ユーザーは Skype for Business からサインアウトし、正しい資格情報でもう一度サインインする必要があります。 ペアリングのダイアログ ボックスが再表示され、ペアリングに成功したかどうかが表示されます。
    
- **リモート デスクトップ クライアントの別のインスタンスが実行している。**
    
    Windows でリモート デスクトップ接続を使用している場合、ユーザーは次の操作を行う必要があります。
    
1. タスク マネージャーを起動します。**Alt+Ctrl+Del** キーを押し、[**タスク マネージャーの起動**] をクリックします。
    
2. [**プロセス**] タブをクリックし、リスト内で **mstsc.exe** という名前のすべてのプロセスを見つけます。
    
3. 各 **mstsc.exe** プロセスを強調表示し、[**プロセスの終了**] をクリックします。 
    
4. 新しいリモート デスクトップ セッションを起動して、再び接続を試みます。 
    
- **必要なファイルが適切にインストールされていない。**
    
    ローカル コンピューターにプラグインがインストールされた後、これらのファイルが C:\Program Files\Microsoft Office\Office15 (または適切なドライブ文字) の下に存在する必要があります。
    
  - LyncVdiPlugin.dll
    
  - UcVdi.dll
    
- **Skype for Business クライアントがローカル コンピューターで実行されています。**
    
    Lync VDI プラグインを使用するには、Skype for Business クライアントがローカル コンピューターで実行されていない必要があります。それ以外の場合、ペアリングは失敗します。 ベスト プラクティスとして、ユーザーはローカル コンピューターに Skype for Business クライアントをインストールする必要があります。
    
## <a name="see-also"></a>関連項目
<a name="tshoot_VDI"> </a>

[VDI 環境での Skype for Business の計画](../../plan-your-deployment/clients-and-devices/vdi-environments.md)