---
title: Lync VDI プラグインをインストールして展開Skype for Business Server
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.reviewer: krishra
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.assetid: 11d3bd5d-6dd3-471c-b842-b072fa197714
description: このトピックでは、リモート仮想デスクトップに接続するSkype for Businessを使用するための展開手順について説明します。
---

# <a name="deploy-the-lync-vdi-plug-in-with-skype-for-business-server"></a>Lync VDI プラグインをインストールして展開Skype for Business Server
 
このトピックでは、リモート仮想デスクトップに接続するSkype for Businessを使用するための展開手順について説明します。 計画に関する考慮事項は、「[VDI 環境でのSkype for Business計画」を参照してください](../../plan-your-deployment/clients-and-devices/vdi-environments.md)。
  
仮想デスクトップ インフラストラクチャ (VDI) 環境は、セキュリティとコンプライアンスの問題が特に重要である一部の組織で使用されています。 ユーザーはローカル コンピューター上Windows、仮想デスクトップ上のクライアントを使用しています。 このようなSkype for Businessを使用するには、追加の VDI プラグイン ソフトウェアが必要です。
  
VDI プラグイン コンポーネントには、Microsoft が提供するソリューションと Citrix が提供するソリューションの 2 つのソリューションがあります。 Microsoft では、新しい展開で新しい HDX RealTime 最適化パック ソリューションを使用をお勧めしますが、そのライフサイクルの残りの期間、元の Lync VDI プラグインを引き続きサポートします。 
  
このトピックでは、Microsoft Lync VDI プラグインの展開に関する詳細を説明します。これは、Windows 7 および Windows 8 または Windows Server 2008 でのみサポートされ、Lync 2013 または Skype for Business クライアントのみをサポートします。 このプラグインを更新する予定はありません。ただし、[Citrix HDX RealTime Optimization Pack](../../plan-your-deployment/clients-and-devices/vdi-environments.md#Citrix_RT) for Skype for Business必要に応じて更新されます。
  
## <a name="prepare-your-environment-for-the-lync-vdi-plug-in"></a>Lync VDI プラグインの環境を準備する
<a name="Prepare_vdi"> </a>

1. このSkype for Business Server、すべての Lync VDI プラグイン ユーザーに対して EnableMediaRedirection が TRUE に設定されている必要があります。 詳細については、 [New-CsClientPolicy コマンドレットと Set-CsClientPolicy](/powershell/module/skype/new-csclientpolicy?view=skype-ps) コマンドレットのヘルプ [トピックを参照](/powershell/module/skype/set-csclientpolicy?view=skype-ps) してください。
    
2. データ センター サーバーで、すべての仮想デスクトップSkype for Businessクライアントをインストールします。
    
3. ローカル コンピューターで、Lync VDI プラグインをインストールします。
    
    これで、ヘッドセットや Web カメラのようなデバイスをローカル コンピューターに接続する必要があります。
    
## <a name="configure-remote-desktop-connection-settings"></a>リモート デスクトップ接続の設定を構成する
<a name="Prepare_vdi"> </a>

Lync VDI プラグインのリモート デスクトップ接続を準備するには、ローカル コンピューターで次の手順を実行します。
  
1. ローカル コンピューターが実行されている場合Windows 8この手順をスキップします。 ローカル コンピューターが SP1 で Windows 7 を実行している場合は、最新Windows 8バージョンのリモート デスクトップ サービス クライアント[をインストールします](/windows-server/remote/remote-desktop-services/clients/remote-desktop-clients)。
    
2. [**スタート**]、[**リモート デスクトップ接続**] の順にクリックして、リモート デスクトップ サービス クライアントを起動します。
    
3. [**オプション**] をクリックします。
    
4. [**ローカル リソース**] タブをクリックします。[**リモート オーディオ**] の下にある [**設定**] をクリックし、次の手順を実行します。
    
   - [**リモート オーディオ再生**] の下の [**このコンピュータで再生**] を選択します。
    
   - [**リモート オーディオ録音**] の下の [**録音しない**] を選択します。
    
   - [**OK**] をクリックします。
    
5. [**エクスペリエンス**] タブをクリックします。[**パフォーマンス**] の下にある [**ビットマップのキャッシュを保持**] チェック ボックスをオフにします。
    
6. [全般] **タブをクリック** します。[**コンピューター]** に仮想デスクトップの名前を入力し、[コンピューター] **をクリックConnect**。 
    
## <a name="sign-in-and-use-skype-for-business-on-the-virtual-desktop"></a>仮想デスクトップでサインインしてSkype for Businessを使用する
<a name="SfB_signin"> </a>

Lync VDI プラグインが有効になると、ユーザーは仮想デスクトップ上のユーザーにサインインするときにSkype for Business手順に従います。
  
1. ユーザーは、仮想デスクトップ上で実行されているクライアントSkype for Business資格情報を入力します。
    
2. Lync VDI Skype for Businessが検出されると、Skype for Business資格情報の再入力を求めるメッセージが表示されます。 このダイアログ ボックスでは、ユーザーが後続のサインイン時に資格情報を入力する必要が生じないので、[パスワードを保存する] チェック ボックスをオンにすることをお勧めします。
    
3. Skype for Business Lync VDI プラグインとのペアリングを開始します。 この場合、クライアントはステータス バーに 2 つのSkype for Business表示します。 左下のアイコンは、オーディオ デバイスが使用できない状態を示し、右下の点滅アイコンは、VDI のペアリングが進行中である (a) を示します。 VDI のペアリングが成功すると、アイコンが変更され、通話に使用されるオーディオ デバイスと VDI ペアリングの成功 (b) が示されます。 これで、ユーザーはローカル コンピューターに接続Skype for Business互換性のあるデバイスで自分のプレゼンスを確認し、通常どおり通話を行って応答できます。
    
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
    
    ユーザーはアカウントからサインアウトSkype for Business資格情報を使用してもう一度サインインする必要があります。 ペアリングのダイアログ ボックスが再表示され、ペアリングに成功したかどうかが表示されます。
    
- **リモート デスクトップ クライアントの別のインスタンスが実行している。**
    
    ユーザーがリモート デスクトップ接続を使用している場合Windowsは、次の操作を行う必要があります。
    
1. タスク マネージャーを起動します。**Alt+Ctrl+Del** キーを押し、[**タスク マネージャーの起動**] をクリックします。
    
2. [**プロセス**] タブをクリックし、リスト内で **mstsc.exe** という名前のすべてのプロセスを見つけます。
    
3. 各 **mstsc.exe** プロセスを強調表示し、[**プロセスの終了**] をクリックします。 
    
4. 新しいリモート デスクトップ セッションを起動して、再び接続を試みます。 
    
- **必要なファイルが適切にインストールされていない。**
    
    プラグインがローカル コンピューターにインストールされた後、これらのファイルが C:\Program Files\Microsoft Office\Office15 (または適切なドライブ文字) の下に存在する必要があります。
    
  - LyncVdiPlugin.dll
    
  - UcVdi.dll
    
- **クライアントSkype for Businessローカル コンピューターで実行されています。**
    
    Lync VDI プラグインを使用するには、Skype for Businessクライアントがローカル コンピューターで実行されていない必要があります。それ以外の場合、ペアリングは失敗します。 ベスト プラクティスとして、ユーザーはローカル コンピューターにSkype for Businessクライアントをインストールする必要があります。
    
## <a name="see-also"></a>関連項目
<a name="tshoot_VDI"> </a>

[VDI 環境での Skype for Business の計画](../../plan-your-deployment/clients-and-devices/vdi-environments.md)