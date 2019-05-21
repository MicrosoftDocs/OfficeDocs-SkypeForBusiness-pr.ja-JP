---
title: Lync VDI プラグインを Skype for Business Server と共に展開する
ms.author: v-lanac
author: lanachin
manager: serdars
ms.reviewer: krishra
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 11d3bd5d-6dd3-471c-b842-b072fa197714
description: このトピックでは、リモート仮想デスクトップに接続しているときに Skype for Business を使用するための展開手順について説明します。
ms.openlocfilehash: a3955ac3634dbf52b47b70482772e7302876bf1e
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34288755"
---
# <a name="deploy-the-lync-vdi-plug-in-with-skype-for-business-server"></a>Lync VDI プラグインを Skype for Business Server と共に展開する
 
このトピックでは、リモート仮想デスクトップに接続しているときに Skype for Business を使用するための展開手順について説明します。 計画の考慮事項は、 [VDI 環境での Skype For business の計画](../../plan-your-deployment/clients-and-devices/vdi-environments.md)に含まれています。
  
仮想デスクトップ インフラストラクチャ (VDI) 環境は、非常に高度なセキュリティとコンプライアンスが求められる組織で使用します。 ユーザーは、仮想デスクトップのクライアントを使用して、ローカルの Windows コンピューターで作業します。 Skype for Business を接続に使用すると、追加の VDI プラグインソフトウェアが必要になります。
  
VDI プラグインコンポーネントには2つのソリューションがあります。1つは Microsoft が提供しており、もう1つは Citrix によって提供されています。 Microsoft は、新しい展開で新しい HDX リアルタイム最適化パックソリューションを使用することをお勧めしますが、そのライフサイクルの残りの部分については、引き続き元の Lync VDI プラグインをサポートします。 
  
このトピックでは、Microsoft Lync VDI プラグインの展開について詳しく説明します。これは、Windows 7、Windows 8、または Windows Server 2008 でのみサポートされ、Lync 2013 または Skype for Business クライアントでのみサポートされます。 このプラグインを更新する予定はありませんが、Skype for Business 用の[CITRIX HDX リアルタイム最適化パック](../../plan-your-deployment/clients-and-devices/vdi-environments.md#Citrix_RT)は必要に応じて更新されます。
  
## <a name="prepare-your-environment-for-the-lync-vdi-plug-in"></a>Lync VDI プラグイン向けに環境を準備する
<a name="Prepare_vdi"> </a>

1. Skype for Business Server で、Lync VDI プラグインのすべてのユーザーに対して EnableMediaRedirection が TRUE に設定されていることを確認します。 詳細については、「[新しい-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/new-csclientpolicy?view=skype-ps)コマンドレット」および「 [csclientpolicy](https://docs.microsoft.com/powershell/module/skype/set-csclientpolicy?view=skype-ps)コマンドレット」のヘルプトピックを参照してください。
    
2. データセンターサーバーで、すべての仮想デスクトップに Skype for Business クライアントをインストールします。
    
3. ローカルコンピューターで、Lync VDI プラグインをインストールします。
    
    ここで、ヘッドセットや Web カメラなどのデバイスをローカル コンピューターに接続します。
    
## <a name="configure-remote-desktop-connection-settings"></a>リモート デスクトップ接続の設定を構成する
<a name="Prepare_vdi"> </a>

Lync VDI プラグインのリモートデスクトップ接続を準備するには、ローカルコンピューターで次の手順を実行します。
  
1. ローカルコンピューターで Windows 8 を実行している場合は、この手順をスキップしてください。 ローカルコンピューターで Windows 7 SP1 を実行している場合は、最新の Windows 8 バージョンの[リモートデスクトップサービスクライアント](https://go.microsoft.com/fwlink/p/?LinkId=268032)をインストールします。
    
2. [**スタート**]、[**リモート デスクトップ接続**] の順にクリックして、リモート デスクトップ サービス クライアントを起動します。
    
3. [**オプション**] をクリックします。
    
4. [**ローカル リソース**] タブをクリックします。[**リモート オーディオ**] の下にある [**設定**] をクリックし、次の手順を実行します。
    
   - [**リモート オーディオ再生**] で [**このコンピューターで再生**] を選択します。
    
   - [**リモート オーディオ録音**] で [**録音しない**] を選択します。
    
   - [**OK**] をクリックします。
    
5. [**エクスペリエンス**] タブをクリックします。[**パフォーマンス**] で [**ビットマップのキャッシュを保持**] チェック ボックスをオフにします。
    
6. [**全般**] タブをクリックします。[**コンピューター**] に仮想マシンの名前を入力し、[**接続**] をクリックします。 
    
## <a name="sign-in-and-use-skype-for-business-on-the-virtual-desktop"></a>仮想デスクトップにサインインして、Skype for Business を使用します。
<a name="SfB_signin"> </a>

Lync VDI プラグインを有効にすると、ユーザーは仮想デスクトップで Skype for Business にサインインするときに次の手順を実行します。
  
1. ユーザーは、仮想デスクトップで実行されている Skype for Business クライアントに自分の資格情報を入力します。
    
2. Skype for Business が Lync VDI プラグインを検出した後、Skype for Business は資格情報を再入力するようにユーザーに求めます。 このダイアログボックスでは、ユーザーが [**パスワードを保存**する] チェックボックスをオンにして、以降のサインインで資格情報を入力する必要がないようにすることをお勧めします。
    
3. Skype for Business は、Lync VDI プラグインとのペアリングを開始します。 この場合、クライアントは、Skype for Business のステータスバーに2つのアイコンを表示します。 左下のアイコンは、オーディオデバイスが利用できないことを示し、右下の点滅するアイコンは、VDI ペアリングが進行中であることを示します。 VDI ペアリングが成功すると、そのアイコンが、通話に使用するオーディオデバイスと VDI ペアリング成功: b を示すように変更されます。 ユーザーは、ローカルコンピューターに接続されている Skype for Business 互換デバイスで自分のプレゼンスを確認できるようになりました。また、通常通りに通話を発信して応答することができます。
    
## <a name="troubleshoot-the-lync-vdi-plug-in"></a>Lync VDI プラグインのトラブルシューティング
<a name="tshoot_VDI"> </a>

Lync VDI プラグインのインストール後に問題が発生した場合は、次のセクションを参照してください。
  
### <a name="issues-with-installing-the-lync-vdi-plug-in"></a>Lync VDI プラグインのインストールに関する問題 

Lync VDI プラグインのインストールで問題が発生した場合は、次の点を確認してください。
  
- TEMP および TMP システム変数で指定したフォルダーに十分な容量がある。
    
- 書き込み保護がオフになっている。 手順については、お使いのデバイスの製造元のマニュアルを参照してください。
    
### <a name="troubleshooting-issues-with-pairing"></a>ペアリングに関する問題のトラブルシューティング

Lync VDI プラグインのペアリングに失敗した場合、右下のペアリングアイコンは、次のように赤い "X" として表示されます。 
  
考えられる失敗の原因と、問題を修正するために行うことのできる対策を、以下に示します。 
  
- **ユーザーがサインインの際に入力した資格情報が正しくない。**
    
    ユーザーは、Skype for Business からサインアウトし、正しい資格情報を使用してもう一度サインインする必要があります。 ペアリングのダイアログ ボックスが再表示され、ペアリングに成功したかどうかが表示されます。
    
- **リモート デスクトップ クライアントの別のインスタンスが実行している。**
    
    Windows でリモートデスクトップ接続を使用している場合、ユーザーは次の操作を行う必要があります。
    
1. タスク マネージャーを起動します。**Alt+Ctrl+Del** キーを押し、[**タスク マネージャーの起動**] をクリックします。
    
2. [**プロセス**] タブをクリックし、リスト内で **mstsc.exe** という名前のすべてのプロセスを見つけます。
    
3. 各 **mstsc.exe** プロセスを強調表示し、[**プロセスの終了**] をクリックします。 
    
4. 新しいリモート デスクトップ セッションを起動して、もう一度接続してみます。 
    
- **必要なファイルが適切にインストールされていない。**
    
    プラグインをローカル コンピューターにインストールしたら、次のファイルが C:\Program Files\Microsoft Office\Office15 (または適切なドライブ文字) にあることを確認します。
    
  - LyncVdiPlugin.dll
    
  - UcVdi.dll
    
- **Skype for Business クライアントはローカルコンピューターで実行されています。**
    
    Lync VDI プラグインを使用するには、ローカルコンピューターで Skype for Business クライアントを実行している必要があります。そうでないと、ペアリングは失敗します。 ベストプラクティスとして、ユーザーはローカルコンピューターに Skype for Business クライアントをインストールしないようにする必要があります。
    
## <a name="see-also"></a>関連項目
<a name="tshoot_VDI"> </a>

[Plan for Skype for Business in VDI environments](../../plan-your-deployment/clients-and-devices/vdi-environments.md)
