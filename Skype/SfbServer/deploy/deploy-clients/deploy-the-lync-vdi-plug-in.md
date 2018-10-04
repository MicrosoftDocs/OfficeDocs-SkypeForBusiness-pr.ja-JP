---
title: ビジネス サーバーの Skype では、プラグインの Lync VDI の導入します。
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 11d3bd5d-6dd3-471c-b842-b072fa197714
description: このトピックでは、Skype を使用してリモート仮想デスクトップへの接続中にビジネスの展開手順について説明します。
ms.openlocfilehash: 08f676632e11c4bf95beee9b97be03703978a4a6
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/04/2018
ms.locfileid: "25373345"
---
# <a name="deploy-the-lync-vdi-plug-in-with-skype-for-business-server"></a>ビジネス サーバーの Skype では、プラグインの Lync VDI の導入します。
 
このトピックでは、Skype を使用してリモート仮想デスクトップへの接続中にビジネスの展開手順について説明します。 計画に関する考慮事項は、 [VDI 環境でのビジネス用の Skype を計画](../../plan-your-deployment/clients-and-devices/vdi-environments.md)します。
  
仮想デスクトップ インフラストラクチャ (VDI) 環境は、非常に高度なセキュリティとコンプライアンスが求められる組織で使用します。 ユーザーは、仮想デスクトップのクライアントを使用して、ローカルの Windows コンピューターで作業します。 使用して Skype ビジネスの接続のようなことには、VDI のプラグイン ソフトウェアを追加する必要があります。
  
ある 2 つのソリューションは、VDI のプラグイン コンポーネントでの使用可能ないずれかで提供されているマイクロソフトと Citrix が提供します。 マイクロソフトでは、新しい環境で新しい HDX リアルタイム最適化パック ソリューションを使用することをお勧めがライフ サイクルの残りの部分の元のプラグインの Lync VDI をサポートするために続行されます。 
  
このトピックでは、Microsoft Lync VDI プラグイン、Windows 7 と Windows 8 または Windows Server 2008 ではサポートされてのみとのみ Lync 2013 または Skype をサポートする、ビジネス クライアント用の展開の詳細を説明します。 このプラグインを更新する予定はありませんが、ビジネスの Skype の[Citrix HDX のリアルタイム最適化パック](../../plan-your-deployment/clients-and-devices/vdi-environments.md#Citrix_RT)は必要に応じて更新されます。
  
## <a name="prepare-your-environment-for-the-lync-vdi-plug-in"></a>Lync VDI プラグイン向けに環境を準備する
<a name="Prepare_vdi"> </a>

1. ビジネス サーバーの Skype で Lync VDI プラグインのすべてのユーザーの EnableMediaRedirection を TRUE に設定されていることを確認します。 詳細については、[新規 CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/new-csclientpolicy?view=skype-ps)コマンドレットと[セット CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/set-csclientpolicy?view=skype-ps)コマンドレットのヘルプ トピックを参照してください。
    
2. データ センター サーバーで、すべての仮想デスクトップ上のビジネス クライアント用の Skype をインストールします。
    
3. ローカルのコンピューターでは、Lync VDI のプラグインをインストールします。
    
    ここで、ヘッドセットや Web カメラなどのデバイスをローカル コンピューターに接続します。
    
## <a name="configure-remote-desktop-connection-settings"></a>リモート デスクトップ接続の設定を構成する
<a name="Prepare_vdi"> </a>

プラグインの Lync VDI のリモート デスクトップ接続を準備するには、ローカル コンピューターでは以下の手順を実行。
  
1. ローカル コンピューターが Windows 8 を実行している場合は、この手順をスキップします。 ローカル コンピューターでは、SP1 を適用した Windows 7 を実行している場合、は、Windows 8 の最新バージョンの[リモート デスクトップ サービス クライアント](https://go.microsoft.com/fwlink/p/?LinkId=268032)をインストールします。
    
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

Lync VDI のプラグインを有効にすると、ユーザーによって、仮想デスクトップ上でビジネス用の Skype にサインインするときがこれらの手順に従います。
  
1. ユーザーが自分の資格情報で仮想デスクトップで実行されているビジネス クライアント用の Skype を入力します。
    
2. ビジネス用の Skype では、Lync VDI のプラグインが検出され後、Skype ビジネスの資格情報を再入力するように求めるプロンプトを表示します。 このダイアログ ボックスで、ことをお勧めユーザーが**自分のパスワードを保存**] チェック ボックスを選択、必要はありませんそれ以降のサインイン時に資格情報を入力するようにします。
    
3. ビジネス用の Skype では、Lync VDI のプラグインとのペアリングを開始します。 発生したときに、クライアントでは、ビジネス ・ ステータス ・ バーの Skype での 2 つのアイコンが表示されます。 左下のアイコンを示し、あるオーディオ デバイスは存在しません、右下で点滅しているアイコンは、VDI のペアが進行中のことを示します。。 呼び出しと VDI の成功の組み合わせを使用するオーディオ デバイスを示すためにアイコンを変更する VDI のペアリングが成功した後は、: b。 ユーザーことができますようになりましたを参照してください自分のプレゼンス Skype のビジネスの互換性のあるデバイスは、ローカルのコンピューターに接続し、通話に応答したりいつものようにするのです。
    
## <a name="troubleshoot-the-lync-vdi-plug-in"></a>Lync VDI プラグインのトラブルシューティング
<a name="tshoot_VDI"> </a>

Lync VDI プラグインのインストール後に問題が発生した場合は、次のセクションを参照してください。
  
### <a name="issues-with-installing-the-lync-vdi-plug-in"></a>Lync VDI プラグインのインストールに関する問題 

Lync VDI のプラグインをインストールすると問題がある場合は、以下を確認します。
  
- TEMP および TMP システム変数で指定したフォルダーに十分な容量がある。
    
- 書き込み保護がオフになっている。 手順については、デバイスの製造元のマニュアルを参照してください。
    
### <a name="troubleshooting-issues-with-pairing"></a>ペアリングに関する問題のトラブルシューティング

Lync VDI のプラグインのペアリングが失敗したとき、右下の表示で、赤い"X"として表示されているとのペアリングのアイコン。 
  
考えられる失敗の原因と、問題を修正するために行うことのできる対策を、以下に示します。 
  
- **ユーザーがサインインの際に入力した資格情報が正しくない。**
    
    ユーザーは、ビジネスの Skype からサインアウトして、正しい資格情報でサインインする必要があります。 ペアリングのダイアログ ボックスが再表示され、ペアリングに成功したかどうかが表示されます。
    
- **リモート デスクトップ クライアントの別のインスタンスが実行している。**
    
    リモート デスクトップ接続を使用して、windows には、ユーザーが、次の操作にする必要があります。
    
1. タスク マネージャーを起動します。**Alt+Ctrl+Del** キーを押し、[**タスク マネージャーの起動**] をクリックします。
    
2. [**プロセス**] タブをクリックし、リスト内で **mstsc.exe** という名前のすべてのプロセスを見つけます。
    
3. 各 **mstsc.exe** プロセスを強調表示し、[**プロセスの終了**] をクリックします。 
    
4. 新しいリモート デスクトップ セッションを起動して、もう一度接続してみます。 
    
- **必要なファイルが適切にインストールされていない。**
    
    プラグインをローカル コンピューターにインストールしたら、次のファイルが C:\Program Files\Microsoft Office\Office15 (または適切なドライブ文字) にあることを確認します。
    
  - LyncVdiPlugin.dll
    
  - UcVdi.dll
    
- **ビジネス クライアント用の Skype は、ローカル コンピューターで行われています。**
    
    プラグインでは、ローカル コンピューター上、Skype のビジネスのクライアントが実行されていない必要がありますの Lync VDI を使用するには、それ以外の場合の組み合わせは失敗します。 ベスト プラクティスとして、ユーザーは、ローカル コンピューター上、Skype のビジネスのクライアントをインストールしないでください。
    
## <a name="see-also"></a>この手順は役に立ちましたか? 役に立った場合は、この記事の下でお知らせください。役に立たなかった場合は、わかりにくかった部分をお知らせください。いただいたフィードバックを元に手順を再確認します。
<a name="tshoot_VDI"> </a>

[VDI 環境における Skype for Business の計画](../../plan-your-deployment/clients-and-devices/vdi-environments.md)