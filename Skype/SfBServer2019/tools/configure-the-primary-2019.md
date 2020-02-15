---
title: プライマリ管理サーバーを構成する
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
description: '概要: プライマリ管理サーバーを構成し、System Center Operations Manager をインストールして、Skype for Business Server 2019 用の管理パックをインポートします。'
ms.openlocfilehash: ccc522da216b98e6f18ea381a74aff19fc5cc24d
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2020
ms.locfileid: "42006052"
---
# <a name="configure-the-primary-management-server"></a>プライマリ管理サーバーを構成する

**概要:** プライマリ管理サーバーを構成し、System Center Operations Manager をインストールして、Skype for Business Server 2019 用の管理パックをインポートします。

Skype for Business Server 2019 に含まれている新しい正常性監視機能を十分に活用するには、まず、プライマリ管理サーバーとして動作するコンピューターを指定する必要があります。 その後、そのコンピューターに System Center Operations Manager 2012 SP1 または R2 または System Center Operations Manager 2007 R2 をインストールする必要があります。 また、Operations Manager のバックエンドデータベースとして機能するために、サポートされているバージョンの SQL Server をインストールする必要があります。

System Center Operations Manager をインストールするときには、次のような製品のすべてのコンポーネントをインストールする必要があります。

- オペレーション データベース

- サーバー

- コンソール

- Windows PowerShell コマンドレット

- Web コンソール

- Reporting

- データ ウェアハウス

> [!IMPORTANT]
> System Center Operations Manager 2012 をインストールする前に、「[Microsoft Report Viewer 2010 再頒布可能パッケージ](https://www.microsoft.com/download/details.aspx?id=6442)」をインストールする必要があります。

これらの製品とそのインストールの詳細については、次のリンクを参照してください。

- [System Center Operations Manager 2012](https://go.microsoft.com/fwlink/p/?linkid=257527)

- [System Center Operations Manager 2007](https://technet.microsoft.com/library/bb735860.aspx)

Skype for Business Server 展開ごとに1つのルート管理サーバーしか使用できないことに注意してください。

## <a name="importing-the-skype-for-business-server-2019-management-packs"></a>Skype for Business Server 2019 管理パックのインポート

System Center Operations Manager の機能を拡張するには、System Center Operations Manager が監視できるアイテム、それらのアイテムを監視する方法、およびアラートをトリガーする方法を決定するソフトウェアをインストールします。返さ. Skype for Business Server 2019 には、次の機能を提供する2つの System Center Operations Manager 管理パックが含まれています。

- **コンポーネントおよびユーザー管理パック**(Microsoft.LS.2019.Monitoring.ComponentAndUser.mp) は、イベントログに記録された Skype For business Server の問題、パフォーマンスカウンターでの登録、または通話詳細レコード (cdr) または Qoe (Quality of Experience) データベースに記録された問題を追跡します。 重大な問題については、System Center Operations Manager を構成して、管理者に電子メール、インスタントメッセージ、または SMS メッセージングをすぐに通知できます。 (SMS または Short Message Service) は、あるモバイルデバイスから別のモバイルデバイスにテキストメッセージを送信するために使用されるテクノロジです。

    > [!NOTE]
    >  Operations Manager 通知の構成の詳細については、「[通知の構成](https://go.microsoft.com/fwlink/p/?LinkID=268785&amp;amp;clcid=0x409)」を参照してください。

- **Active Monitoring Management Pack** (Microsoft.LS.2019.Monitoring.ActiveMonitoring.mp) は、システムへのサインイン、インスタントメッセージの交換、または公衆交換電話網 (PSTN) に配置された電話機への通話の作成など、主要な Skype For business Server コンポーネントを事前にテストします。 これらのテストは、Skype for Business Server 代理トランザクションコマンドレットを使用して行われます。 たとえば、**Test-CsIM** コマンドレットは、1 組のテスト ユーザー間でインスタント メッセージングの会話をシミュレートするために使用されます。 このシミュレートされた会話が失敗すると、アラートが生成されます。

管理パックのインポートは、重要な手順です。 管理パックがインポートされていない場合、Operations Manager を使用して Skype for business Server イベントを監視したり、Skype for Business Server 代理トランザクションを実行したりすることはできません。

コンポーネントおよびユーザー管理パックは、Skype for Business Server 2019 のみを監視するために使用されます。 Skype for business server 2019 と Skype for Business Server 2015 の両方がインストールされている共存シナリオでは、skype for business server の2015コンピューターで Skype for Business Server の2015管理パックを引き続き使用する必要があります。

> [!NOTE]
> Skype for business Server 2019 用の管理パックには、Skype for Business Server 2019 コンポーネントおよびユーザー管理パックと、Skype for Business Server 2019 アクティブ監視管理パックが含まれています。

次のいずれかのツールを使用して、管理パックをインポートできます。

- **System Center Operations Manager**この方法では、Operations Manager を使用して Skype for Business Server の監視を追加します。

- **Operations Manager シェル**Operations Manager シェルを使用して、System Center Operations Manager コンソールを使用して、管理パックのインポート時に発生した問題のトラブルシューティングを行うことができます。

### <a name="importing-the-management-packs-by-using-system-center-operations-manager"></a>System Center Operations Manager を使用した管理パックのインポート

1. Microsoft Web ダウンロードから SkypeForBusiness2019ManagementPacks をダウンロードし、msi をインストールします。

2. System Center Operations Manager で、[**管理**] をクリックします。

3. [管理] ウィンドウで、[**管理パック**] を右クリックして [**管理パックのインポート**] をクリックします。

4. [**管理パックの選択**] ダイアログ ボックスで、[**追加**] をクリックし、[**ディスクから追加する**] をクリックします。

5. [**オンラインカタログ接続**] ダイアログボックスで、[**いいえ**] をクリックします。

6. [**インポートする管理パックの選択**] ダイアログボックスで、Microsoft.LS.2019.Monitoring.ActiveMonitoring.mp および Microsoft.LS.2019.Monitoring.ComponentAndUser.mp ファイルを見つけて選択し、[**開く**] をクリックします。 ダイアログボックスで複数のファイルを選択するには、最初のファイルをクリックし、Ctrl キーを押しながら、次のファイルをクリックします。

7. [**管理パックの選択**] ダイアログ ボックスで、[**インストール**] をクリックします。 エラー メッセージが表示されてインストールが失敗する場合は、通常、管理パックのファイルが Windows ユーザー アカウント制御によって保護されているフォルダー内にあることを意味します。 その場合は、ファイルを別のフォルダーにコピーしてから、インポートとインストールのプロセスを再実行してください。

8. [**管理パックの選択**] ダイアログ ボックスで、[**閉じる**] をクリックします。 インポートとインストールのプロセスが完了するまでに数分かかることがあります。

## <a name="importing-the-management-packs-by-using-the-operations-manager-shell"></a>Operations Manager シェルを使用した管理パックのインポート

通常、Operations Manager コンソールを使用して、管理パックをインポートする方が簡単です。 ただし、エラーが発生してインポートが失敗した場合、コンソールは、適切なエラーレポートを常に提供するわけではありません。 比較すると、Operations Manager シェルは詳細情報を提供します。 Operations Manager を使用していて、管理パックをインポートするときに問題が発生した場合は、Operations Manager シェルを使用してパックをインポートします。 Operations Manager シェルによって提供される情報は、インポートが失敗した理由を判断するのに役立ちます。

1. [**スタート**]、[**すべてのプログラム**]、[ **Microsoft System Center 2012**]、[ **Operations manager**]、[ **operations manager Shell**] の順にクリックします。

2. Operations Manager シェルで、Microsoft.LS.2019.Monitoring.ActiveMonitoring.mp ファイルのコピーへの実際のパスを使用して、コマンドプロンプトで次のコマンドを入力し、ENTER キーを押します。

   ```PowerShell
   Import-SCOMManagementPack -FullName "D:\MP\Microsoft.LS.2019.Monitoring.ActiveMonitoring.mp"
   ```

3. 最初の管理パックをインポートした後、Microsoft.LS.2019.Monitoring.ComponentAndUser.mp ファイルのコピーのパスを使用して、この手順を繰り返します。

   ```PowerShell
   Import-SCOMManagementPack -FullName "D:\MP\Microsoft.LS.2019.Monitoring.ComponentAndUser.mp"
   ```
