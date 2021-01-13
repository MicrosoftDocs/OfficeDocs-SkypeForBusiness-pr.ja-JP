---
title: 監視対象の Skype for Business Server コンピューターを構成する
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
description: '概要: 監視対象の Skype for Business Server 2019 コンピューターに Operations Manager エージェント ファイルをインストールし、System Center プロキシとして動作するコンピューターを構成します。'
ms.openlocfilehash: 08328e430acd4fa651fccd89b827d5c103066dd1
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49806077"
---
# <a name="configure-the-skype-for-business-server-computers-that-will-be-monitored"></a>監視対象の Skype for Business Server コンピューターを構成する

**概要:** 監視対象の Skype for Business Server 2019 コンピューターに Operations Manager エージェント ファイルをインストールし、System Center プロキシとして動作するコンピューターを構成します。

監視する各 Skype for Business Server 2019 コンピューターは、その存在を管理サーバーに自己報告できる必要があります。 このプロセスを有効にするには、監視対象の各コンピューターに Operations Manager エージェント ファイルをインストールする必要があります。 エージェント ファイルをインストールした後、System Center プロキシとして機能するコンピューターを構成する必要があります。 これらの手順を実行する前に、これらのコンピューターに Skype for Business Server を最初にインストールして構成してください。

## <a name="installing-a-certificate-on-a-watcher-node-located-outside-the-perimeter-network"></a>境界ネットワーク外にある監視ノードの証明書のインストール
<a name="watcher_node_outside"> </a>

境界ネットワーク (Skype for Business Server エッジ サーバーなど)、企業の外部 (外部代理トランザクション 監視ノードなど)、または Active Directory 信頼境界を越えて実行する System Center Operations Manager エージェントでは、System Center Operations Manager Gateway Server の構成が必要な場合があります。 このサーバーの役割を使用すると、ルート管理サーバーとの信頼関係を持たないエージェントがアラートを生成できます。 詳細については [、「Operations Manager 2012 でのゲートウェイ](https://technet.microsoft.com/library/hh212823.aspx)サーバーの管理」を参照してください。

これらの場所の 1 つでエージェントを展開する場合は、監視ノードが System Center Operations Manager に通知を送信できる証明書を要求して構成する必要もあります。 このプロセスを簡単にするため、Operations Manager チームは、正しい種類の証明書を要求して監視ノード コンピューターにインストールできる一連のユーティリティを作成しました。 詳細およびこれらのユーティリティをダウンロードするには、「証明書生成ウィザードを使用して容易に行う非ドメイン参加エージェントの証明書の取得」を [参照してください](https://go.microsoft.com/fwlink/p/?LinkID=267421&amp;amp;clcid=0x409)。

### <a name="installing-the-operation-manager-agent-files"></a>Operation Manager エージェント ファイルのインストール

1. System Center セットアップ メディアで、次の設定をダブルクリック **Setup.exe。**

2. System Center Operation Manager セットアップ ウィザードで、[オプションのインストール] の [インストール エージェント] から **[Operations Manager** エージェントのインストール] をクリックします。

3. System Center セットアップ ウィザードの [System Center Operations Manager セットアップ ウィザードへようこそ] ページで、[次へ] をクリック **します**。

4. [保存先フォルダー] ページで、Operations Manager エージェント ファイルをインストールするフォルダーを選択し、[次へ] をクリック **します**。

5. [管理グループの構成] ページで、[管理グループ情報の **指定** ] を選択し、[次へ] をクリック **します**。

6. [管理グループの構成] ページで、[管理グループ名] ボックスにOperations Manager 管理グループの名前を入力し、[管理サーバー] ボックスに Operations Manager サーバーのホスト名 (たとえば、atl-scom-001) を入力します。  Operations Manager で使用されるポート番号を変更した場合は、[管理サーバーのポート] ボックスに新しいポート **番号を入力** します。 それ以外の場合は、ポートを既定値の 5723 のままにして、[次へ] をクリック **します**。

7. [エージェント アクション アカウント] ページで、[ローカル システム] を選択 **し** 、[次へ] を **クリックします**。

8. [Microsoft Update] ページで **、[Microsoft Update** を使用しない] を選択し、[次へ] を **クリックします**。

9. [インストールの準備完了] ページで、[ **インストール**] をクリックします。

10. [System Center Operations Manager セットアップ ウィザードの完了] ページで、[完了] をクリック **します**。

11. **[終了]** をクリックします。

System Center 2012 では、[スタート] ボタン、[すべてのプログラム]の順にクリックし **、[System Center Operations Manager 2012]** をクリックし **、[Operations 2012** マネージャー シェル] をクリックすると、エージェントが作成されたのを確認できます。 Operations Manager シェルで、次のコマンドを入力Windows PowerShell Enter キーを押します。
```PowerShell
Get-SCOMAgent
```

すべての Operations Manager エージェントの一覧が表示されます。
## <a name="configuring-the-skype-for-business-server-computer-to-participate-in-system-center-discovery"></a>System Center Discovery に参加するための Skype for Business Server コンピューターの構成
<a name="watcher_node_outside"> </a>

新しい Skype for Business Server エージェントが System Center Operations Manager の検出プロセスに参加するには、System Center Operations Manager コンソールがインストールされている各コンピューターで次の手順を実行する必要があります。

1. [管理] タブで、[**管理対象のエージェント**] をクリックします。

2. 探索ウィザード **をクリック** し、検出するコンピューターのウィザードを完了します。

3. Health Agent サービスを再起動します。 サービスを再起動すると、強制的に新しいコンピューターが検出されます。 サービスを再起動しない場合、System Center Operations Manager によって新しいコンピューターが検出されるのに 4 時間かかる場合があります。

4. Operations Manager のイベント ログにエラー イベントが記録されなにくかったか確認します。

5. エージェントが正常にプッシュされたコンピューターが [エージェント管理] の一覧に表示され、エージェントが手動でインストールされたコンピューターが [保留中の管理] の下に表示され、コンピューター名をクリックして承認します。

6. コンピューターの名前を右クリックし、[**プロパティ**] をクリックします。 [プロパティ] ダイアログ ボックスの [セキュリティ] タブで、[**このエージェントをプロキシとして動作させ、他のコンピューター上の管理オブジェクトを検出する**] を選択し、[**OK**] をクリックします。


