---
title: 監視対象の Skype for Business Server コンピューターの構成
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 11/7/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
description: '概要: は、Operations Manager エージェントにファイルをインストール、監視対象サーバー 2019 のビジネス コンピューターの Skype と System Center のプロキシとして動作するコンピューターを構成します。'
ms.openlocfilehash: 90608d9233bea466b523418553d5421735234aee
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30875419"
---
# <a name="configure-the-skype-for-business-server-computers-that-will-be-monitored"></a>監視対象の Skype for Business Server コンピューターの構成

**の概要:** Operations Manager エージェントにファイルをインストール、監視対象サーバー 2019 のビジネス コンピューターの Skype と System Center のプロキシとして動作するコンピューターを構成します。

ビジネス サーバー 2019 のコンピューターを監視するには、各 Skype では、自己管理サーバーにその存在を報告する必要があります。 このプロセスを有効にするために、監視する各コンピューターに Operations Manager エージェント ファイルをインストールする必要があります。 エージェント ファイルをインストールした後、System Center プロキシとして動作するようにコンピューターを構成する必要があります。 必ず最初にインストールしている Skype をビジネス サーバーのこれらの手順を実行する前にこれらのコンピューターで構成します。

## <a name="installing-a-certificate-on-a-watcher-node-located-outside-the-perimeter-network"></a>境界ネットワーク外にある監視ノードの証明書のインストール
<a name="watcher_node_outside"> </a>

システム センター オペレーション マネージャー エージェントが境界で実行されているが (、外部代理トランザクション監視ノードなど)、企業の外部ネットワークなど、Skype ビジネス エッジ サーバーの)、または、Active Directory の信頼間の境界をする必要があります。システム センター オペレーション マネージャー ゲートウェイ サーバーの構成。 このサーバーの役割により、ルート管理サーバーと信頼関係を持たないエージェントは警告を出すことができるようになります。 詳細については、[運用マネージャー 2012 でゲートウェイ サーバーを管理する](https://technet.microsoft.com/en-us/library/hh212823.aspx)を参照してください。

これらの場所のいずれかでエージェントを展開する場合を要求し、System Center Operations Manager にアラートを送信するウォッチャー ノードを有効にする証明書を構成する必要がもあります。 このプロセスを簡略化には、Operations Manager チームが作成を要求し、監視ノード コンピューターで適切な種類の証明書をインストールできるようにするユーティリティのセットです。 詳細については、し、これらのユーティリティをダウンロードするには、[非ドメイン参加しているエージェント作成を簡単に証明書の生成ウィザードを使用しての証明書の取得](https://go.microsoft.com/fwlink/p/?LinkID=267421&amp;amp;clcid=0x409)を参照してください。

### <a name="installing-the-operation-manager-agent-files"></a>Operation Manager エージェント ファイルのインストール

1. System Center セットアップ メディアで、[**SetupOM.exe**] をダブルクリックします。

2. システム センター操作マネージャー セットアップ ウィザードで、[**操作マネージャー エージェントのインストール**、インストールのオプション] の下には、[エージェントのインストール] をクリックします

3. System Center セットアップ ウィザードで、システム センター操作マネージャーのセットアップ ウィザードのページへようこそ] で、**次へ**をクリックします。

4. コピー先のフォルダー] ページで、[操作マネージャー エージェントのファイルがインストールされ、[**次へ**] をクリックする、フォルダーを選択します。

5. [管理グループの構成] ページで、[**管理グループ情報の指定**] を選択し、[**次へ**] をクリックします。

6. [管理グループの構成] ページで、**管理グループ名**] ボックスに、オペレーション マネージャーの管理グループの名前を入力し、Operations Manager サーバーのホスト名を入力し (たとえば、atl の scom-001)**管理サーバーで**ボックスです。 Operations Manager が使用するポート番号を変更した場合は、[**管理サーバー ポート**] ボックスに新しいポート番号を入力します。 そうしない場合は、ポートを既定の値 5723 のままにし、[**次へ**] をクリックします。

7. [エージェント アクション アカウント] ページで、[**ローカル システム**] を選択し、[**次へ**] をクリックします。

8. [Microsoft Update] ページで、[**Microsoft Update を使用しない**] を選択し、[**次へ**] をクリックします。

9. [インストールの準備完了] ページで、[**インストール**] をクリックします。

10. 完了システム センター操作マネージャーのセットアップ ウィザード ページで、[**完了**] をクリックします。

11. [**終了**] をクリックします。

System Center 2012 では、 **[スタート] ボタン**、**すべてのプログラム**をクリックすると、 **System Center オペレーション マネージャー 2012**をクリックし、 **2012年マネージャー シェルの操作**によって、エージェントが作成されたことを確認できます。 In the Operations Manager Shell, type the following Windows PowerShell command, and then press ENTER:
```
Get-SCOMAgent
```

すべての Operations Manager エージェントの一覧が表示されます。
## <a name="configuring-the-skype-for-business-server-computer-to-participate-in-system-center-discovery"></a>System Center 検出に関与する Skype for Business Server コンピューターの構成
<a name="watcher_node_outside"> </a>

ビジネス サーバー エージェントの新しい Skype は、System Center Operations Manager の検出プロセスでに参加することを確認、System Center Operations Manager コンソールがインストールされている各コンピューターで次の手順を行う必要があります。

1. [管理] タブで、[**管理対象のエージェント**] をクリックします。

2. [**検出ウィザード**] をクリックし、コンピューターを検出するためのウィザードを完了させます。

3. 正常性エージェント サービスを再起動します。 サービスを再起動すると、強制的に新しいコンピューターの検出が実行されます。 サービスを再起動しない場合は、System Center Operations Manager で、新しいコンピューターが検出される前に、4 時間に限りがかかります。

4. Operations Manager のイベント ログに、エラー イベントが記録されていないことを確認します。

5. 一覧の [エージェントの管理」の下で、エージェントが正常にプッシュされたコンピューターが表示され、エージェントを手動でインストールされているコンピューターの「保留中の管理」の下に表示されます、コンピューター名をクリックして、および承認します。

6. コンピューターの名前を右クリックし、[**プロパティ**] をクリックします。[プロパティ] ダイアログ ボックスの [セキュリティ] タブで、[**このエージェントをプロキシとして動作させ、他のコンピューター上の管理オブジェクトを検出する**] を選択し、[**OK**] をクリックします。


