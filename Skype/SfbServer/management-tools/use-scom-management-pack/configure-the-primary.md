---
title: プライマリ管理サーバーの構成
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
ms.assetid: c7e21cce-1dd2-489a-a2eb-f632799f7523
description: '概要: プライマリ管理サーバーを構成し、System Center Operations Manager をインストールし、Skype for Business Server 2015 の管理パックをインポートします。'
ms.openlocfilehash: ace25e1b4971c561dc1544290b04f481f36c9676
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51111643"
---
# <a name="configure-the-primary-management-server"></a>プライマリ管理サーバーの構成

**概要:** プライマリ管理サーバーを構成し、System Center Operations Manager をインストールし、Skype for Business Server 2015 の管理パックをインポートします。

Skype for Business Server 2015 に含まれる新しい正常性監視機能を活用するには、まず、プライマリ管理サーバーとして機能するコンピューターを指定する必要があります。 その後、そのコンピューターに System Center Operations Manager 2012 SP1 または R2 または System Center Operations Manager 2007 R2 をインストールする必要があります。 さらに、Operations Manager のバック エンド データベースとして機能するには、SQL Serverバージョンのサポートされているデータベースを最初にインストールする必要があります。

System Center Operations Manager をインストールする場合は、以下を含む、その製品のすべてのコンポーネントをインストールする必要があります。

- オペレーション データベース

- Server

- コンソール

- Windows PowerShell コマンドレット

- Web コンソール

- Reporting

- データ ウェアハウス

> [!IMPORTANT]
> System Center Operations Manager 2012 をインストールする前に、「Microsoft Report[Viewer 2010 再](https://www.microsoft.com/download/details.aspx?id=6442)頒布可能パッケージ」をインストールする必要があります。

これらの製品とそのインストールの詳細については、次のリンクを参照してください。

- [System Center Operations Manager 2012](/previous-versions/system-center/system-center-2012-R2/hh205987(v=sc.12))

- [System Center Operations Manager 2007](https://technet.microsoft.com/library/bb735860.aspx)

Skype for Business Server 展開ごとに使用できるルート管理サーバーは 1 つのみです。

## <a name="importing-the-skype-for-business-server-2015-management-packs"></a>Skype for Business Server 2015 管理パックのインポート

System Center Operations Manager の機能を拡張するには、管理パック (System Center Operations Manager で監視できるアイテム、それらのアイテムの監視方法、アラートのトリガーと報告方法を指示するソフトウェア) をインストールします。 Skype for Business Server 2015 には、次の機能を提供する 2 つの System Center Operations Manager 管理パックが含まれています。

- コンポーネントおよび **ユーザー** 管理パック (Microsoft.LS.2015.Monitoring.ComponentAndUser.mp) は、イベント ログに記録された Skype for Business Server の問題、パフォーマンス カウンターによって登録された、または通話詳細レコード (CDRs) または QoE (Quality of Experience) データベースに記録された問題を追跡します。 重大な問題については、System Center Operations Manager を構成して、電子メール、インスタント メッセージ、または SMS メッセージングを通じて管理者に直ちに通知できます。 (SMS、またはショート メッセージ サービスは、あるモバイル デバイスから別のモバイル デバイスにテキスト メッセージを送信するために使用されるテクノロジです)。

    > [!NOTE]
    >  Operations Manager 通知の構成の詳細については、「通知の [構成」を参照してください](/previous-versions/system-center/operations-manager-2007-r2/dd440890(v=technet.10))。

- Active **Monitoring Management Pack** (Microsoft.LS.2015.Monitoring.ActiveMonitoring.mp) は、システムへのサインイン、インスタント メッセージの交換、公衆交換電話網 (PSTN) にある電話への通話など、Skype for Business Server の主要なコンポーネントを積極的にテストします。 これらのテストは、Skype for Business Server 代理トランザクション コマンドレットを使用して行われます。 たとえば、**Test-CsIM** コマンドレットは、1 組のテスト ユーザー間でインスタント メッセージングの会話をシミュレートするために使用されます。 このシミュレートされた会話が失敗すると、アラートが生成されます。

管理パックのインポートは重要な手順です。 管理パックがインポートされていない場合、Operations Manager を使用して Skype for Business Server イベントを監視したり、Skype for Business Server 代理トランザクションを実行したりすることはできません。

コンポーネントとユーザー管理パックは、Skype for Business Server 2015 のみを監視するために使用されます。 Skype for Business Server 2015 と Lync Server 2013 の両方がインストールされている共存シナリオの場合は、Lync Server 2013 コンピューターに Lync Server 2013 管理パックを引き続き使用する必要があります。

> [!NOTE]
> Skype for Business Server 2015 の管理パックには、Skype for Business Server 2015 コンポーネントとユーザー管理パック、Skype for Business Server 2015 Active Monitoring Management Pack が含まれます。

次のいずれかのツールを使用して、管理パックをインポートできます。

- **System Center Operations Manager** このメソッドでは、Operations Manager を使用して Skype for Business Server の監視を追加します。

- **Operations Manager シェル** Operations Manager シェルを使用して直接インポートしたり、System Center Operations Manager コンソールを使用して管理パックをインポートするときに発生する問題のトラブルシューティングを行います。

### <a name="importing-the-management-packs-by-using-system-center-operations-manager"></a>System Center Operations Manager を使用した管理パックのインポート

1. Microsoft Web ダウンロードSkypeForBusiness2015ManagementPacks.msiをダウンロードし、msi をインストールします。

2. System Center Operations Manager で、[管理] を **クリックします**。

3. [管理] ウィンドウで、[**管理パック**] を右クリックして [**管理パックのインポート**] をクリックします。

4. [**管理パックの選択**] ダイアログ ボックスで、[**追加**] をクリックし、[**ディスクから追加する**] をクリックします。

5. [オンライン カタログ **接続] ダイアログ ボックスで** 、[いいえ] を **クリックします**。

6. [インポートする **管理パック** の選択] ダイアログ ボックスで、ファイルを検索して選択し、Microsoft.LS.2015.Monitoring.ActiveMonitoring.mp を Microsoft.LS.2015.Monitoring.ComponentAndUser.mp し、[開く] を **クリックします**。 ダイアログ ボックスで複数のファイルを選択するには、最初のファイルをクリックし、Ctrl キーを押しながら後続のファイルをクリックします。

7. [**管理パックの選択**] ダイアログ ボックスで、[**インストール**] をクリックします。 エラー メッセージが表示されてインストールが失敗する場合は、通常、管理パックのファイルが Windows ユーザー アカウント制御によって保護されているフォルダー内にあることを意味します。 この場合は、ファイルを別のフォルダーにコピーし、インポートおよびインストール プロセスを再起動します。

8. [**管理パックの選択**] ダイアログ ボックスで、[**閉じる**] をクリックします。 インポートおよびインストール プロセスの完了に数分が必要になる場合があります。

## <a name="importing-the-management-packs-by-using-the-operations-manager-shell"></a>Operations Manager シェルを使用した管理パックのインポート

一般に、Operations Manager コンソールを使用して管理パックをインポートする方が簡単です。 ただし、エラーが発生してインポートが失敗した場合、コンソールは必ずしも適切なエラー レポートを提供するとは限らない。 一方、Operations Manager シェルは詳細情報を提供します。 Operations Manager を使用している場合に、管理パックをインポートするときに問題が発生した場合は、Operations Manager シェルを使用してパックをインポートします。 Operations Manager シェルによって提供される情報は、インポートが失敗した理由を判断するのに役立ちます。

1. [ **スタート] ボタン**、[ **すべてのプログラム] の** 順にクリックし **、[Microsoft System Center 2012]** をクリックし **、[Operations Manager]** をクリックし **、[Operations Manager シェル] をクリックします**。

2. [Operations Manager Shell] で、コマンド プロンプトで、ファイル のコピーへの実際のパスを使用して次のコマンドを入力し Microsoft.LS.2015.Monitoring.ActiveMonitoring.mp Enter キーを押します。

   ```PowerShell
   Import-SCOMManagementPack -FullName "D:\MP\Microsoft.LS.2015.Monitoring.ActiveMonitoring.mp"
   ```

3. 最初の管理パックをインポートした後、次の手順に示すファイルのコピーへのパスを使用して、プロセスを繰り Microsoft.LS.2015.Monitoring.ComponentAndUser.mp。

   ```PowerShell
   Import-SCOMManagementPack -FullName "D:\MP\Microsoft.LS.2015.Monitoring.ComponentAndUser.mp"
   ```