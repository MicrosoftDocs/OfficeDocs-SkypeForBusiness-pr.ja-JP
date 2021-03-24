---
title: 監視する Skype for Business Server コンピューターを構成する
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
ms.assetid: b24ea184-4b3e-4277-a244-157afb4b368b
description: '概要: 監視対象の Skype for Business Server 2015 コンピューターに Operations Manager エージェント ファイルをインストールし、System Center プロキシとして動作するコンピューターを構成します。'
ms.openlocfilehash: bb4dc64a1c04bbef1b6cb0e391fc27568edfef43
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51111683"
---
# <a name="configure-the-skype-for-business-server-computers-that-will-be-monitored"></a>監視する Skype for Business Server コンピューターを構成する

**概要:** 監視対象の Skype for Business Server 2015 コンピューターに Operations Manager エージェント ファイルをインストールし、システム センター プロキシとして動作するコンピューターを構成します。

監視する各 Skype for Business Server 2015 コンピューターは、その存在を管理サーバーに自己報告できる必要があります。 このプロセスを有効にするには、監視対象の各コンピューターに Operations Manager エージェント ファイルをインストールする必要があります。 エージェント ファイルをインストールした後、System Center プロキシとして機能するコンピューターを構成する必要があります。 これらの手順を実行する前に、これらのコンピューターに Skype for Business Server を最初にインストールして構成済みである必要があります。

## <a name="installing-a-certificate-on-a-watcher-node-located-outside-the-perimeter-network"></a>境界ネットワーク外にある監視ノードの証明書のインストール
<a name="watcher_node_outside"> </a>

境界ネットワークで実行されている System Center Operations Manager エージェント (Skype for Business Server エッジ サーバーなど)、企業外 (外部代理トランザクション 監視ノードなど)、または Active Directory 信頼境界を越えて実行する場合、System Center Operations Manager ゲートウェイ サーバーの構成が必要な場合があります。 このサーバーの役割を使用すると、ルート管理サーバーとの信頼関係を持つエージェントがアラートを発生できます。 詳細については [、「Operations Manager 2012 での](/previous-versions/system-center/system-center-2012-R2/hh212823(v=sc.12))ゲートウェイ サーバーの管理」を参照してください。

これらの場所の 1 つでエージェントを展開する場合は、監視ノードが System Center Operations Manager にアラートを送信できる証明書を要求および構成する必要もあります。 このプロセスを簡単にするため、Operations Manager チームは、正しい種類の証明書を要求して監視ノード コンピューターにインストールできる一連のユーティリティを作成しました。 これらのユーティリティの詳細とダウンロードについては、「証明書生成ウィザードを使用して簡単に行う非ドメイン参加エージェントの証明書の取得」 [を参照してください](https://go.microsoft.com/fwlink/p/?LinkID=267421&amp;amp;clcid=0x409)。

### <a name="installing-the-operation-manager-agent-files"></a>Operation Manager エージェント ファイルのインストール

1. System Center セットアップ メディアで、[次へ] を **ダブルクリックSetup.exe。**

2. System Center Operation Manager セットアップ ウィザードで、[オプションのインストール] の下の **[エージェント** のインストール] から [操作マネージャー エージェントのインストール] をクリックします。

3. System Center セットアップ ウィザードの [System Center Operations Manager セットアップ ウィザードへようこそ] ページで、[次へ] を **クリックします**。

4. [移動先フォルダー] ページで、Operations Manager エージェント ファイルをインストールするフォルダーを選択し、[次へ] を **クリックします**。

5. [管理グループの構成] ページで、[管理グループ情報 **の指定] を選択し、[** 次へ] を **クリックします**。

6. [管理グループ構成] ページで、[管理グループ名] ボックスに Operations  Manager 管理グループの名前を入力し、[管理サーバー] ボックスに Operations Manager サーバーのホスト名 (atl-scom-001 など) を入力します。  Operations Manager で使用されるポート番号を変更した場合は、[管理サーバー ポート] ボックスに新しいポート **番号を入力** します。 それ以外の場合は、ポートを既定値の 5723 のままにし、[次へ] を **クリックします**。

7. [エージェント アクション アカウント] ページで、[ローカル システム] **を選択し、[次** へ] を **クリックします**。

8. [Microsoft Update] ページで、[Microsoft Update を使用しない] を選択し、[ **次** へ] を **クリックします**。

9. [インストールの準備完了] ページで、[ **インストール**] をクリックします。

10. [System Center Operations Manager セットアップ ウィザードの完了] ページで、[完了] を **クリックします**。

11. **[終了]** をクリックします。

System Center 2012 では、[スタート] ボタン、[すべてのプログラム]の順にクリックし **、[System Center Operations Manager 2012]** をクリックし、[Operations **2012 Manager Shell]** をクリックして、エージェントが作成されたと確認できます。 Operations Manager シェルで、次のコマンドを入力Windows PowerShell Enter キーを押します。
```PowerShell
Get-SCOMAgent
```

すべての Operations Manager エージェントの一覧が表示されます。
## <a name="configuring-the-skype-for-business-server-computer-to-participate-in-system-center-discovery"></a>システム センターの検出に参加するための Skype for Business Server コンピューターの構成
<a name="watcher_node_outside"> </a>

新しい Skype for Business Server エージェントが System Center Operations Manager の検出プロセスに参加するには、System Center Operations Manager コンソールがインストールされている各コンピューターで次の手順を実行する必要があります。

1. [管理] タブで、[**管理対象のエージェント**] をクリックします。

2. [検出 **ウィザード] をクリック** し、検出するコンピューターのウィザードを完了します。

3. Health Agent サービスを再起動します。 サービスを再起動すると、新しいコンピューターが強制的に検出されます。 サービスを再起動しない場合、System Center Operations Manager によって新しいコンピューターが検出されるまで、4 時間ほどかかる場合があります。

4. Operations Manager イベント ログにエラー イベントが記録されなかっているのを確認します。

5. エージェントが正常にプッシュされたコンピューターが [エージェント管理] リストに表示され、エージェントが手動でインストールされたコンピューターが [保留中の管理] の下に表示され、コンピューター名をクリックして承認します。

6. コンピューターの名前を右クリックし、[**プロパティ**] をクリックします。 [プロパティ] ダイアログ ボックスの [セキュリティ] タブで、[**このエージェントをプロキシとして動作させ、他のコンピューター上の管理オブジェクトを検出する**] を選択し、[**OK**] をクリックします。