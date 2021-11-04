---
title: プライマリ管理サーバーを構成する方法
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: c7e21cce-1dd2-489a-a2eb-f632799f7523
description: '概要: プライマリ管理サーバーを構成し、2015 System Center Operations Manager をインストールし、管理パックをインポートSkype for Business Serverします。'
ms.openlocfilehash: 98a6cb9f18a5ff3fe008e7d07f5101884e5aa0f0
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/04/2021
ms.locfileid: "60774597"
---
# <a name="how-to-configure-the-primary-management-server"></a>プライマリ管理サーバーを構成する方法

**概要:** プライマリ管理サーバーを構成し、2015 System Center Operations Manager をインストールし、管理パックをインポートSkype for Business Serverします。

Skype for Business Server 2015 に含まれる新しい正常性監視機能を活用するには、最初にプライマリ管理サーバーとして機能するコンピューターを指定する必要があります。 その後、そのコンピューター System Center Operations Manager 2012 SP1 または R2 または System Center Operations Manager 2007 R2 をインストールする必要があります。 また、Operations Manager のバック エンド データベースとして機能するには、SQL Serverバージョンのサポートされているデータベースを最初にインストールする必要があります。

Operations Manager にSystem Center、次を含む、その製品のすべてのコンポーネントをインストールする必要があります。

- オペレーション データベース

- サーバー

- コンソール

- Windows PowerShell コマンドレット

- Web コンソール

- Reporting

- データ ウェアハウス

> [!IMPORTANT]
> Operations Manager 2012 をインストールする前に、Microsoft Report Viewer 2010 再頒布可能パッケージをSystem Centerする必要があります。

これらの製品とそのインストールの詳細については[、「System Center Operations Manager 2012」を参照してください。](/previous-versions/system-center/system-center-2012-R2/hh205987(v=sc.12))


ルート管理サーバーは、展開ごとに 1 つのみSkype for Business Serverしてください。

## <a name="importing-the-skype-for-business-server-2015-management-packs"></a>2015 Skype for Business Serverパックのインポート

System Center Operations Manager の機能を拡張するには、管理パック (System Center Operations Manager で監視できるアイテム、それらのアイテムを監視する方法、アラートをトリガーおよび報告する方法を指示するソフトウェア) をインストールします。 Skype for Business Server 2015 には、次System Center機能を提供する 2 つの Operations Manager 管理パックが含まれています。

- コンポーネントおよび **ユーザー** 管理パック (Microsoft.LS.2015.Monitoring.ComponentAndUser.mp) は、イベント ログに記録された Skype for Business Server の問題、パフォーマンス カウンターによって登録された、または通話詳細レコード (CDRs) または QoE (Quality of Experience) データベースに記録された問題を追跡します。 重大な問題については、System Center、インスタント メッセージ、または SMS メッセージングを通じて管理者に直ちに通知するように、Operations Manager を構成できます。 (SMS、またはショート メッセージ サービスは、あるモバイル デバイスから別のモバイル デバイスにテキスト メッセージを送信するために使用されるテクノロジです)。

    > [!NOTE]
    >  Operations Manager 通知の構成の詳細については、「通知の [構成」を参照してください](/previous-versions/system-center/operations-manager-2007-r2/dd440890(v=technet.10))。

- Active **Monitoring Management Pack** (Microsoft.LS.2015.Monitoring.ActiveMonitoring.mp) は、システムへのサインイン、インスタント メッセージの交換、公衆交換電話網 (PSTN) にある電話への通話など、主要な Skype for Business Server コンポーネントを積極的にテストします。 これらのテストは、代理トランザクション コマンドレットSkype for Business Server使用して行われます。 たとえば、**Test-CsIM** コマンドレットは、1 組のテスト ユーザー間でインスタント メッセージングの会話をシミュレートするために使用されます。 このシミュレートされた会話が失敗すると、アラートが生成されます。

管理パックのインポートは重要な手順です。 管理パックがインポートされていない場合は、Operations Manager を使用してイベントの監視や代理トランザクションSkype for Business Server実行Skype for Business Serverできません。

コンポーネントとユーザー管理パックは、2015 年Skype for Business Server使用されます。 Skype for Business Server 2015 と Lync Server 2013 の両方がインストールされている共存シナリオの場合は、Lync Server 2013 コンピューターに Lync Server 2013 管理パックを引き続き使用する必要があります。

> [!NOTE]
> Skype for Business Server 2015 の管理パックには、Skype for Business Server 2015 コンポーネントとユーザー管理パック、Skype for Business Server 2015 Active Monitoring Management Pack が含まれます。

次のいずれかのツールを使用して、管理パックをインポートできます。

- **System Center Operations Manager** このメソッドでは、Operations Manager を使用して、ユーザーの監視を追加Skype for Business Server。

- **Operations Manager シェル** 管理パックを直接インポートOperations Manager シェル、管理パックをインポートするときに発生する問題のトラブルシューティングには、System Center Operations Manager コンソールを使用します。

### <a name="importing-the-management-packs-by-using-system-center-operations-manager"></a>Operations Manager を使用して管理パックをSystem Centerする

1. Microsoft Web ダウンロードSkypeForBusiness2015ManagementPacks.msiをダウンロードし、msi をインストールします。

2. [System Centerマネージャー] で、[管理] を **クリックします**。

3. [管理] ウィンドウで、[**管理パック**] を右クリックして [**管理パックのインポート**] をクリックします。

4. [**管理パックの選択**] ダイアログ ボックスで、[**追加**] をクリックし、[**ディスクから追加する**] をクリックします。

5. [オンライン カタログ **接続] ダイアログ ボックスで** 、[いいえ] を **クリックします**。

6. [インポートする **管理パック** の選択] ダイアログ ボックスで、ファイルを検索して選択し、Microsoft.LS.2015.Monitoring.ActiveMonitoring.mp を Microsoft.LS.2015.Monitoring.ComponentAndUser.mp し、[開く] を **クリックします**。 ダイアログ ボックスで複数のファイルを選択するには、最初のファイルをクリックし、Ctrl キーを押しながら後続のファイルをクリックします。

7. [**管理パックの選択**] ダイアログ ボックスで、[**インストール**] をクリックします。 エラー メッセージが表示されてインストールが失敗する場合は、通常、管理パックのファイルが Windows ユーザー アカウント制御によって保護されているフォルダー内にあることを意味します。 この場合は、ファイルを別のフォルダーにコピーし、インポートおよびインストール プロセスを再起動します。

8. [**管理パックの選択**] ダイアログ ボックスで、[**閉じる**] をクリックします。 インポートおよびインストール プロセスの完了に数分が必要になる場合があります。

## <a name="importing-the-management-packs-by-using-the-operations-manager-shell"></a>管理パックを使用して管理パックをインポートOperations Manager シェル

一般に、Operations Manager コンソールを使用して管理パックをインポートする方が簡単です。 ただし、エラーが発生してインポートが失敗した場合、コンソールは必ずしも適切なエラー レポートを提供するとは限らない。 比較して、このOperations Manager シェル情報を提供します。 Operations Manager を使用している場合に、管理パックをインポートするときに問題が発生した場合は、管理パックを使用してパックをOperations Manager シェル。 ユーザーが提供するOperations Manager シェル、インポートが失敗した理由を判断するのに役立ちます。

1. [**スタート]** ボタン、[**すべてのプログラム]** の順にクリックし **、[Microsoft System Center 2012] を** クリックし、[Operations **Manager]** をクリックして、[Operations Manager シェル]**をクリックします**。

2. [Operations Manager シェル] で、コマンド プロンプトで、ファイル のコピーへの実際のパスを使用して次 Microsoft.LS.2015.Monitoring.ActiveMonitoring.mp 入力し、Enter キーを押します。

   ```PowerShell
   Import-SCOMManagementPack -FullName "D:\MP\Microsoft.LS.2015.Monitoring.ActiveMonitoring.mp"
   ```

3. 最初の管理パックをインポートした後、次の手順に示すファイルのコピーへのパスを使用して、プロセスを繰り Microsoft.LS.2015.Monitoring.ComponentAndUser.mp。

   ```PowerShell
   Import-SCOMManagementPack -FullName "D:\MP\Microsoft.LS.2015.Monitoring.ComponentAndUser.mp"
   ```