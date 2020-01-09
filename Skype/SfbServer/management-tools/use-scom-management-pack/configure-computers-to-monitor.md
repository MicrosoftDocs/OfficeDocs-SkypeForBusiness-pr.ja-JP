---
title: 監視対象の Skype for Business Server コンピューターの構成
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: b24ea184-4b3e-4277-a244-157afb4b368b
description: '概要: Skype for Business Server 2015 コンピューターに、監視対象の Operations Manager エージェントファイルをインストールし、System Center プロキシとして動作するようにコンピューターを構成します。'
ms.openlocfilehash: 5279924c29e8dba11882ca7d172c06894a7808b8
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992474"
---
# <a name="configure-the-skype-for-business-server-computers-that-will-be-monitored"></a>監視対象の Skype for Business Server コンピューターの構成

**概要:** 監視する Skype for Business Server 2015 コンピューターに Operations Manager エージェントファイルをインストールし、System Center プロキシとして動作するようにコンピューターを構成します。

監視対象の各 Skype for Business Server 2015 コンピューターは、管理サーバーにその存在を自己報告できる必要があります。 このプロセスを有効にするために、監視する各コンピューターに Operations Manager エージェント ファイルをインストールする必要があります。 エージェント ファイルをインストールした後、System Center プロキシとして動作するようにコンピューターを構成する必要があります。 これらの手順を実行する前に、これらのコンピュータに Skype for Business Server をインストールして構成していることを確認してください。

## <a name="installing-a-certificate-on-a-watcher-node-located-outside-the-perimeter-network"></a>境界ネットワーク外にある監視ノードの証明書のインストール
<a name="watcher_node_outside"> </a>

境界ネットワーク (Skype for Business Server Edge Server など) で実行されている System Center Operations Manager エージェント、エンタープライズ (外部の代理トランザクション監視ノードなど)、または Active Directory の信頼境界を超えている場合は、System Center Operations Manager ゲートウェイサーバーの構成。 このサーバーの役割により、ルート管理サーバーと信頼関係を持たないエージェントは警告を出すことができるようになります。 詳細については、「 [Operations Manager 2012 でゲートウェイサーバーを管理する](https://technet.microsoft.com/en-us/library/hh212823.aspx)」を参照してください。

これらのいずれかの場所でエージェントを展開する場合は、watcher ノードが System Center Operations Manager に通知を送信できるようにする証明書を要求して構成する必要があります。 このプロセスを簡略化するために、Operations Manager チームは、ウォッチャーノードのコンピューターで正しい種類の証明書を要求およびインストールできる一連のユーティリティを作成しました。 詳細については、「[証明書の作成ウィザードを使用して、ドメインに参加していないエージェントの証明書を取得](https://go.microsoft.com/fwlink/p/?LinkID=267421&amp;amp;clcid=0x409)する」を参照してください。

### <a name="installing-the-operation-manager-agent-files"></a>Operation Manager エージェント ファイルのインストール

1. System Center セットアップ メディアで、[**SetupOM.exe**] をダブルクリックします。

2. System Center Operation Manager のセットアップウィザードで、[インストールエージェント] から [オプションのインストール] の [ **Operations Manager エージェントのインストール**] をクリックします。

3. System Center セットアップウィザードの [System Center Operations Manager セットアップウィザードへようこそ] ページで、[**次へ**] をクリックします。

4. [インポート先のフォルダー] ページで、Operations Manager エージェントファイルをインストールするフォルダーを選択し、[**次へ**] をクリックします。

5. [管理グループの構成] ページで、[**管理グループ情報の指定**] を選択し、[**次へ**] をクリックします。

6. [管理グループの構成] ページで、[**管理グループ名**] ボックスに Operations Manager 管理グループの名前を入力し、[ **management server** ] ボックスに operations manager サーバーのホスト名 (例: atl-scom) を入力します。 Operations Manager が使用するポート番号を変更した場合は、[**管理サーバー ポート**] ボックスに新しいポート番号を入力します。 そうしない場合は、ポートを既定の値 5723 のままにし、[**次へ**] をクリックします。

7. [エージェント アクション アカウント] ページで、[**ローカル システム**] を選択し、[**次へ**] をクリックします。

8. [Microsoft Update] ページで、[**Microsoft Update を使用しない**] を選択し、[**次へ**] をクリックします。

9. [インストールの準備完了] ページで、[**インストール**] をクリックします。

10. System Center Operations Manager のセットアップウィザードの完了ページで、[**完了**] をクリックします。

11. [**終了**] をクリックします。

System Center 2012 の場合は、[**スタート**]、[**すべてのプログラム**]、[ **System Center Operations Manager 2012**]、[ **operations 2012 Manager Shell**] の順にクリックして、エージェントの作成が完了していることを確認できます。 In the Operations Manager Shell, type the following Windows PowerShell command, and then press ENTER:
```PowerShell
Get-SCOMAgent
```

すべての Operations Manager エージェントの一覧が表示されます。
## <a name="configuring-the-skype-for-business-server-computer-to-participate-in-system-center-discovery"></a>System Center 検出に関与する Skype for Business Server コンピューターの構成
<a name="watcher_node_outside"> </a>

新しい Skype for Business Server エージェントが System Center Operations Manager の検出プロセスに参加するようにするには、System Center Operations Manager コンソールがインストールされているコンピューターごとに、次の手順を実行する必要があります。

1. [管理] タブで、[**管理対象のエージェント**] をクリックします。

2. [**検出ウィザード**] をクリックし、コンピューターを検出するためのウィザードを完了させます。

3. 正常性エージェント サービスを再起動します。 サービスを再起動すると、強制的に新しいコンピューターの検出が実行されます。 サービスを再起動しないと、System Center Operations Manager によって新しいコンピューターが検出されるまでに4時間かかることがあります。

4. Operations Manager のイベント ログに、エラー イベントが記録されていないことを確認します。

5. エージェントが正常にプッシュされたコンピューターは、[エージェントで管理] リストに表示され、エージェントが手動でインストールされているコンピューターは [保留中の管理] の下に表示され、コンピューター名をクリックして承認します。

6. コンピューターの名前を右クリックし、[**プロパティ**] をクリックします。[プロパティ] ダイアログ ボックスの [セキュリティ] タブで、[**このエージェントをプロキシとして動作させ、他のコンピューター上の管理オブジェクトを検出する**] を選択し、[**OK**] をクリックします。


