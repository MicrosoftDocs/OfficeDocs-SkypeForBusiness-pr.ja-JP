---
title: 監視対象の Skype for Business Server コンピューターを構成する
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
description: '概要: Skype for Business Server 2019 コンピューターに Operations Manager エージェントファイルをインストールして監視し、システムセンタープロキシとして動作するようにコンピューターを構成します。'
ms.openlocfilehash: a79101a80fd68eb7b65b7f981874afa44f5cb5f3
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2020
ms.locfileid: "42006062"
---
# <a name="configure-the-skype-for-business-server-computers-that-will-be-monitored"></a>監視対象の Skype for Business Server コンピューターを構成する

**概要:** 監視対象の Skype for Business Server 2019 コンピューターに Operations Manager エージェントファイルをインストールし、System Center プロキシとして動作するようにコンピューターを構成します。

監視する各 Skype for Business Server 2019 コンピューターは、管理サーバーへのその存在を自己報告できる必要があります。 このプロセスを有効にするには、監視する各コンピューターに Operations Manager エージェントファイルをインストールする必要があります。 エージェントファイルをインストールした後、システムセンタープロキシとして動作するようにコンピューターを構成する必要があります。 これらの手順を実行する前に、これらのコンピューターで Skype for Business Server を最初にインストールして構成したことを確認してください。

## <a name="installing-a-certificate-on-a-watcher-node-located-outside-the-perimeter-network"></a>境界ネットワーク外にある監視ノードの証明書のインストール
<a name="watcher_node_outside"> </a>

境界ネットワーク (Skype for Business Server エッジサーバーなど)、エンタープライズ外部 (外部代理トランザクション監視ノードなど)、または Active Directory 信頼境界を越えて実行されている System Center Operations Manager エージェントは、System Center Operations Manager ゲートウェイサーバーの構成。 このサーバーの役割によって、ルート管理サーバーとの信頼関係を持たないエージェントがアラートを発生させることができます。 詳細については、「 [Operations Manager 2012 でゲートウェイサーバーを管理する](https://technet.microsoft.com/library/hh212823.aspx)」を参照してください。

これらのいずれかの場所にエージェントを展開する場合は、監視ノードが System Center Operations Manager に通知を送信できるようにする証明書を要求して構成する必要もあります。 このプロセスを簡単にするため、Operations Manager チームは、正しい種類の証明書を要求して監視ノード コンピューターにインストールできる一連のユーティリティを作成しました。 詳細について、およびこれらのユーティリティをダウンロードするには、「[証明書の生成ウィザードを使用して簡単にドメインに参加していないエージェントの証明書を取得](https://go.microsoft.com/fwlink/p/?LinkID=267421&amp;amp;clcid=0x409)する」をご覧ください。

### <a name="installing-the-operation-manager-agent-files"></a>Operation Manager エージェントファイルのインストール

1. System Center セットアップメディアで **、setup.exe をダブルクリックし**ます。

2. System Center Operation Manager セットアップウィザードで、[オプションのインストール] の [エージェントのインストールからの**Operations Manager エージェントのインストール**] をクリックします。

3. System Center setup ウィザードの [System Center Operations Manager セットアップウィザードへようこそ] ページで、[**次へ**] をクリックします。

4. [保存先フォルダー] ページで、Operations Manager エージェントファイルをインストールするフォルダーを選択し、[**次へ**] をクリックします。

5. [管理グループの構成] ページで、[**管理グループ情報の指定**] を選択し、[**次へ**] をクリックします。

6. [管理グループの構成] ページで、[管理**グループ名**] ボックスに Operations Manager 管理グループの名前を入力し、[**管理サーバー** ] ボックスに、operations manager サーバーのホスト名 (たとえば、「atl-scom-001」) を入力します。 Operations Manager で使用されるポート番号を変更した場合は、[**管理サーバーのポート**] ボックスに新しいポート番号を入力します。 それ以外の場合は、ポートを既定値の5723のままにして、[**次へ**] をクリックします。

7. [エージェントアクションアカウント] ページで、[**ローカルシステム**] を選択し、[**次へ**] をクリックします。

8. [Microsoft Update] ページで、[ **Microsoft update を使用しない**] を選択し、[**次へ**] をクリックします。

9. [インストールの準備完了] ページで、[ **インストール**] をクリックします。

10. [System Center Operations Manager セットアップウィザードを完了しています] ページで、[**完了**] をクリックします。

11. **[終了]** をクリックします。

System Center 2012 では、[**スタート**]、[**すべてのプログラム**]、[ **System Center Operations Manager 2012**]、[ **operations 2012 Manager シェル**] の順にクリックして、エージェントが作成されたことを確認できます。 Operations Manager シェルで、次の Windows PowerShell コマンドを入力し、enter キーを押します。
```PowerShell
Get-SCOMAgent
```

Operations Manager エージェントの一覧が表示されます。
## <a name="configuring-the-skype-for-business-server-computer-to-participate-in-system-center-discovery"></a>System Center Discovery に参加するように Skype for Business Server コンピュータを構成する
<a name="watcher_node_outside"> </a>

System Center operations manager の検出プロセスに新しい Skype for Business Server エージェントが参加するようにするには、System Center Operations Manager コンソールがインストールされている各コンピューターで次の手順を実行する必要があります。

1. [管理] タブで、[**管理対象のエージェント**] をクリックします。

2. **探索ウィザード**をクリックして、コンピューターが検出されるようにウィザードを完了します。

3. 正常性エージェントサービスを再起動します。 サービスを再起動すると、新しいコンピューターが強制的に検出されます。 サービスを再起動しない場合は、System Center Operations Manager によって新しいコンピューターが検出されるまでに4時間かかることがあります。

4. Operations Manager イベントログにエラーイベントが記録されていないことを確認します。

5. エージェントが正常にプッシュされたコンピューターは、[エージェントで管理] 一覧に表示され、エージェントが手動でインストールされたコンピューターは [保留中の管理] の下に表示されます。 [コンピューター名] をクリックして、を承認します。

6. コンピューターの名前を右クリックし、[**プロパティ**] をクリックします。 [プロパティ] ダイアログ ボックスの [セキュリティ] タブで、[**このエージェントをプロキシとして動作させ、他のコンピューター上の管理オブジェクトを検出する**] を選択し、[**OK**] をクリックします。


