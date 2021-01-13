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
description: '概要: プライマリ管理サーバーの構成、System Center Operations Manager のインストール、および Skype for Business Server 2015 の管理パックのインポートを行います。'
ms.openlocfilehash: be7e484814e241b4aebb042a23497ed4806693e0
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814867"
---
# <a name="configure-the-primary-management-server"></a>プライマリ管理サーバーの構成

**概要:** プライマリ管理サーバーを構成し、System Center Operations Manager をインストールし、Skype for Business Server 2015 の管理パックをインポートします。

Skype for Business Server 2015 に含まれる新しい正常性監視機能を活用するには、まずプライマリ管理サーバーとして機能するコンピューターを指定する必要があります。 その後、そのコンピューターに System Center Operations Manager 2012 SP1 または R2 または System Center Operations Manager 2007 R2 をインストールする必要があります。 さらに、Operations Manager のバック エンド データベースとして機能するには、サポートされているバージョンの SQL Serverを最初にインストールする必要があります。

System Center Operations Manager をインストールする場合は、次を含む、その製品のすべてのコンポーネントをインストールする必要があります。

- オペレーション データベース

- Server

- コンソール

- Windows PowerShell コマンドレット

- Web コンソール

- Reporting

- データ ウェアハウス

> [!IMPORTANT]
> System Center Operations Manager 2012 をインストールする前に[、"Microsoft Report Viewer 2010 再](https://www.microsoft.com/download/details.aspx?id=6442)頒布可能パッケージ" をインストールする必要があります。

これらの製品とそのインストールの詳細については、次のリンクを参照してください。

- [System Center Operations Manager 2012](https://go.microsoft.com/fwlink/p/?linkid=257527)

- [System Center Operations Manager 2007](https://technet.microsoft.com/library/bb735860.aspx)

Skype for Business Server の展開ごとに使用できるルート管理サーバーは 1 つのみです。

## <a name="importing-the-skype-for-business-server-2015-management-packs"></a>Skype for Business Server 2015 管理パックのインポート

System Center Operations Manager の機能を拡張するには、管理パック (System Center Operations Manager が監視できる項目、それらのアイテムを監視する方法、アラートをトリガーおよび報告する方法を指定するソフトウェア) をインストールします。 Skype for Business Server 2015 には、次の機能を提供する 2 つの System Center Operations Manager 管理パックが含まれています。

- Component **and User Management Pack** (Microsoft.LS.2015.Monitoring.ComponentAndUser.mp) は、イベント ログに記録された Skype for Business Server の問題、パフォーマンス カウンターによって登録された問題、通話詳細記録 (CDRs) または QoE (Quality of Experience) データベースに記録された問題を追跡します。 重大な問題については、System Center Operations Manager を構成して、電子メール、インスタント メッセージ、または SMS メッセージングを使用して管理者に直ちに通知できます。 (SMS またはショート メッセージ サービスは、あるモバイル デバイスから別のモバイル デバイスにテキスト メッセージを送信するために使用されるテクノロジです)。

    > [!NOTE]
    >  Operations Manager 通知の構成の詳細については、「通知の構成 [」を参照してください](https://go.microsoft.com/fwlink/p/?LinkID=268785&amp;amp;clcid=0x409)。

- **Active Monitoring Management Pack** (Microsoft.LS.2015.Monitoring.ActiveMonitoring.mp) は、システムへのサインイン、インスタント メッセージの交換、公衆交換電話網 (PSTN) 上の電話への通話など、主要な Skype for Business Server コンポーネントを事前にテストします。 これらのテストは、Skype for Business Server 代理トランザクション コマンドレットを使用して実行されます。 たとえば、**Test-CsIM** コマンドレットは、1 組のテスト ユーザー間でインスタント メッセージングの会話をシミュレートするために使用されます。 このシミュレートされた会話が失敗した場合は、アラートが生成されます。

管理パックのインポートは重要な手順です。 管理パックがインポートされていない場合、Operations Manager を使用して Skype for Business Server イベントを監視したり、Skype for Business Server 代理トランザクションを実行したりすることはできません。

コンポーネントおよびユーザー管理パックは、Skype for Business Server 2015 のみを監視するために使用されます。 Skype for Business Server 2015 と Lync Server 2013 の両方がインストールされている共存シナリオの場合は、Lync Server 2013 コンピューター用の Lync Server 2013 管理パックを引き続き使用する必要があります。

> [!NOTE]
> Skype for Business Server 2015 の管理パックには、Skype for Business Server 2015 コンポーネントとユーザー管理パック、および Skype for Business Server 2015 Active Monitoring Management Pack が含まれます。

次のいずれかのツールを使用して、管理パックをインポートできます。

- **System Center Operations Manager** この方法では、Operations Manager を使用して Skype for Business Server の監視を追加します。

- **Operations Manager シェル** Operations Manager シェルを使用すると、直接インポートしたり、System Center Operations Manager コンソールを使用して管理パックをインポートするときに発生する問題のトラブルシューティングを行えます。

### <a name="importing-the-management-packs-by-using-system-center-operations-manager"></a>System Center Operations Manager を使用して管理パックをインポートする

1. Microsoft Web ダウンロードSkypeForBusiness2015ManagementPacks.msiファイルをダウンロードし、msi をインストールします。

2. System Center Operations Manager で、[管理] を **クリックします**。

3. [管理] ウィンドウで、[**管理パック**] を右クリックして [**管理パックのインポート**] をクリックします。

4. [**管理パックの選択**] ダイアログ ボックスで、[**追加**] をクリックし、[**ディスクから追加する**] をクリックします。

5. [オンライン カタログ **接続] ダイアログ ボックス** で、[いいえ] を **クリックします**。

6. In the **Select Management Packs to import** dialog box, locate and select the files Microsoft.LS.2015.Monitoring.ActiveMonitoring.mp and Microsoft.LS.2015.Monitoring.ComponentAndUser.mp, and then click **Open**. ダイアログ ボックスで複数のファイルを選択するには、最初のファイルをクリックし、Ctrl キーを押しながら後続のファイルをクリックします。

7. [**管理パックの選択**] ダイアログ ボックスで、[**インストール**] をクリックします。 エラー メッセージが表示されてインストールが失敗する場合は、通常、管理パックのファイルが Windows ユーザー アカウント制御によって保護されているフォルダー内にあることを意味します。 この場合は、ファイルを別のフォルダーにコピーし、インポートとインストールのプロセスを再開します。

8. [**管理パックの選択**] ダイアログ ボックスで、[**閉じる**] をクリックします。 インポートとインストールのプロセスが完了するには数分が必要な場合があります。

## <a name="importing-the-management-packs-by-using-the-operations-manager-shell"></a>Operations Manager シェルを使用して管理パックをインポートする

一般に、Operations Manager コンソールを使用して管理パックをインポートする方が簡単です。 ただし、エラーが発生してインポートが失敗した場合、コンソールは常に適切なエラーレポートを提供するとは限らない。 一方、Operations Manager シェルは詳細情報を提供します。 Operations Manager を使用している場合に、管理パックをインポートするときに問題が発生した場合は、Operations Manager シェルを使用してパックをインポートします。 Operations Manager シェルによって提供される情報は、インポートが失敗した理由を判断するのに役立ちます。

1. [ **スタート] ボタン**、[すべてのプログラム] **の** 順にクリックし **、[Microsoft System Center 2012]** をクリックし **、[Operations Manager]** をクリックして **、[Operations Manager シェル] をクリックします**。

2. Operations Manager シェルで、コマンド プロンプトで次のコマンドを入力し、ファイル ファイルのコピーへの実際のパスを使用Microsoft.LS.2015.Monitoring.ActiveMonitoring.mp、Enter キーを押します。

   ```PowerShell
   Import-SCOMManagementPack -FullName "D:\MP\Microsoft.LS.2015.Monitoring.ActiveMonitoring.mp"
   ```

3. 最初の管理パックをインポートした後、次の手順を繰り返して、ファイルのコピーへのパスを使用Microsoft.LS.2015.Monitoring.ComponentAndUser.mp。

   ```PowerShell
   Import-SCOMManagementPack -FullName "D:\MP\Microsoft.LS.2015.Monitoring.ComponentAndUser.mp"
   ```
