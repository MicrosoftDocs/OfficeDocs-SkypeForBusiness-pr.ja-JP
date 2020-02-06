---
title: プライマリ管理サーバーの構成
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
description: '概要: プライマリ management server を構成し、System Center Operations Manager をインストールし、Skype for Business Server 2019 の管理パックをインポートします。'
ms.openlocfilehash: a4fda367307b99bb952e6673b3b4d1c2967299c6
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824001"
---
# <a name="configure-the-primary-management-server"></a>プライマリ管理サーバーの構成

**概要:** プライマリ管理サーバーを構成し、System Center Operations Manager をインストールし、Skype for Business Server 2019 の管理パックをインポートします。

Skype for Business Server 2019 に含まれている新しい正常性監視機能を最大限に活用するには、まず、プライマリ管理サーバーとして動作するようにコンピューターを指定する必要があります。 次に、そのコンピューターに System Center Operations Manager 2012 SP1 または R2 または System Center Operations Manager 2007 R2 をインストールする必要があります。 さらに、サポートされているバージョンの SQL Server を、Operations Manager バックエンドデータベースとして機能するようにインストールする必要があります。

System Center Operations Manager をインストールする場合は、次のような製品のすべてのコンポーネントをインストールする必要があります。

- オペレーション データベース

- サーバー

- コンソール

- Windows PowerShell コマンドレット

- Web コンソール

- レポート

- データ ウェアハウス

> [!IMPORTANT]
> System Center Operations Manager 2012 をインストールする前に、"[Microsoft Report Viewer 2010 再頒布可能パッケージ](https://www.microsoft.com/en-us/download/details.aspx?id=6442)" がインストールされている必要があります。

これらの製品とインストールの詳細については、次のリンクを参照してください。

- [System Center Operations Manager 2012](https://go.microsoft.com/fwlink/p/?linkid=257527)

- [System Center Operations Manager 2007](https://technet.microsoft.com/en-us/library/bb735860.aspx)

Skype for Business Server の展開には、1つのルート管理サーバーしか設定できないことに注意してください。

## <a name="importing-the-skype-for-business-server-2019-management-packs"></a>Skype for Business Server 2019 管理パックのインポート

管理パック (System Center Operations Manager で監視できる項目、それらの項目の監視方法、およびアラートのトリガー方法を決定するソフトウェア) をインストールすることによって System Center Operations Manager の機能を拡張することができます。発生. Skype for Business Server 2019 には、次の機能を提供する System Center Operations Manager 管理パックが2つ含まれています。

- **コンポーネントとユーザー管理パック**(Microsoft.LS.2019.Monitoring.ComponentAndUser.mp) は、イベントログに記録された Skype For business Server の問題を追跡し、パフォーマンスカウンターで登録するか、または通話の詳細レコード (CDRs) または Quality of Experience (qoe) データベースに記録します。 重要な問題については、System Center Operations Manager を構成して、メール、インスタントメッセージ、または SMS メッセージングを介して管理者にすぐに通知することができます。 (SMS、またはショートメッセージサービス) は、あるモバイルデバイスから別のモバイルデバイスにテキストメッセージを送信するために使用されるテクノロジです。

    > [!NOTE]
    >  Operations Manager の通知の構成について詳しくは、「[通知の構成](https://go.microsoft.com/fwlink/p/?LinkID=268785&amp;amp;clcid=0x409)」をご覧ください。

- **アクティブな監視管理パック**(Microsoft.LS.2019.Monitoring.ActiveMonitoring.mp) は、システムにサインインしたり、インスタントメッセージを交換したり、公衆交換電話網 (PSTN) にある電話への通話を発信したりするなど、Skype For business Server の主要なコンポーネントを事前にテストします。 これらのテストは、Skype for Business Server の代理トランザクションコマンドレットを使用して行われます。 たとえば、テスト用の**cgi**コマンドレットを使って、一連のテストユーザー間のインスタントメッセージの会話をシミュレートします。 このシミュレートされた会話が失敗すると、アラートが生成されます。

管理パックのインポートは、必要不可欠なステップです。管理パックをインポートしていない場合は、Operations Manager を使用して Skype for Business Server イベントを監視することや、Skype for Business Server 代理トランザクションを実行することができません。

コンポーネントとユーザー管理パックは、Skype for Business Server 2019 のみを監視するために使用されます。 Skype for business server 2019 と Skype for Business Server 2015 の両方がインストールされている共存シナリオの場合は、引き続き skype for business server 2015 コンピューター用の Skype for Business Server 2015 管理パックを使用する必要があります。

> [!NOTE]
> Skype for business Server 2019 用の管理パックには、Skype for Business Server 2019 コンポーネントとユーザー管理パック、および Skype for Business Server 2019 Active Monitoring Management Pack が含まれています。

次のいずれかのツールを使用して、管理パックをインポートできます。

- **System Center Operations Manager**この方法では、Operations Manager を使用して、Skype for Business Server の監視を追加します。

- **Operations Manager Shell**Operations Manager Shell を使用して直接インポートすることも、System Center Operations Manager コンソールを使用して管理パックをインポートするときに発生する問題のトラブルシューティングを行うこともできます。

### <a name="importing-the-management-packs-by-using-system-center-operations-manager"></a>System Center Operations Manager を使用した管理パックのインポート

1. Microsoft Web ダウンロードから SkypeForBusiness2019ManagementPacks をダウンロードし、msi をインストールします。

2. System Center Operations Manager で、[**管理**] をクリックします。

3. [管理] ウィンドウで、[**管理パック**] を右クリックし、[**管理パックのインポート**] をクリックします。

4. [**管理パックの選択**] ダイアログ ボックスで、[**追加**] をクリックし、[**ディスクから追加する**] をクリックします。

5. [**オンライン カタログ接続**] ダイアログ ボックスで、[**いいえ**] をクリックします。

6. [**インポートする管理パックの選択**] ダイアログボックスで、Microsoft.LS.2019.Monitoring.ActiveMonitoring.mp と Microsoft.LS.2019.Monitoring.ComponentAndUser.mp のファイルを見つけて選び、[**開く**] をクリックします。 ダイアログ ボックスで複数のファイルを選択するには、最初のファイルをクリックした後、Ctrl キーを押しながら 2 番目のファイルをクリックします。

7. [**管理パックの選択**] ダイアログ ボックスで、[**インストール**] をクリックします。エラー メッセージが表示されてインストールが失敗する場合は、通常、管理パックのファイルが Windows ユーザー アカウント制御によって保護されているフォルダー内にあることを意味します。その場合は、ファイルを別のフォルダーにコピーした後、インポートとインストールの処理を再度開始します。

8. [**管理パックの選択**] ダイアログ ボックスで、[**閉じる**] をクリックします。インポートとインストールの処理には数分かかることがあります。

## <a name="importing-the-management-packs-by-using-the-operations-manager-shell"></a>Operations Manager シェルを使用した管理パックのインポート

一般には、管理パックをインポートするには Operations Manager コンソールを使用する方が簡単です。ただし、エラーが発生してインポートが失敗する場合、コンソールでは適切にエラーが報告されないことがあります。これに対し、Operations Manager シェルでは詳細な情報が提供されます。Operations Manager を使用していて、管理パックのインポートに問題がある場合は、Operations Manager シェルを使用してパックをインポートしてください。Operations Manager シェルではインポートが失敗した理由の特定に役立つ可能性のある詳細な情報が提供されます。

1. [**スタート**]、[**すべてのプログラム**]、[**Microsoft System Center 2012**]、[**Operations Manager**] の順にクリックし、[**Operations Manager シェル**] をクリックします。

2. Operations Manager Shell で、コマンドプロンプトで次のコマンドを入力します。これには、Microsoft.LS.2019.Monitoring.ActiveMonitoring.mp ファイルの実際のパスを使用し、enter キーを押します。

   ```PowerShell
   Import-SCOMManagementPack -FullName "D:\MP\Microsoft.LS.2019.Monitoring.ActiveMonitoring.mp"
   ```

3. 最初の管理パックをインポートした後、Microsoft.LS.2019.Monitoring.ComponentAndUser.mp ファイルのコピーのパスを使用して、次の手順を繰り返します。

   ```PowerShell
   Import-SCOMManagementPack -FullName "D:\MP\Microsoft.LS.2019.Monitoring.ComponentAndUser.mp"
   ```
