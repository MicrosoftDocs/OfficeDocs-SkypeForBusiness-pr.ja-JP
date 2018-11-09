---
title: プライマリ管理サーバーの構成
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
description: '概要: は、プライマリ管理サーバーを構成する、System Center Operations Manager をインストールして、Skype のビジネス サーバー 2019 の管理パックをインポートします。'
ms.openlocfilehash: 39ed469227c607084dc030fa003700074a6aae9a
ms.sourcegitcommit: 139b3d3b7fcc1dd7fba7fd14ff34e4ffdfcc7eeb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/08/2018
ms.locfileid: "26216129"
---
# <a name="configure-the-primary-management-server"></a>プライマリ管理サーバーの構成

**の概要:** プライマリ管理サーバーを構成して、System Center Operations Manager をインストール Skype のビジネス サーバー 2019 の管理パックをインポートします。

新しい状態監視の業務サーバー 2019 の Skype に含まれている機能を最大限に活用するには、プライマリ管理サーバーとして動作するコンピューターを指定する必要があります。 そのコンピューターにシステム センター操作マネージャーの 2012 SP1 または R2 またはシステム センターの Operations Manager 2007 R2 をインストールする必要があります。 さらに、まず、Operations Manager のバックエンド データベースとして機能する SQL Server のサポートされているバージョンをインストールする必要があります。

System Center Operations Manager をインストールするときは、その製品のすべてのコンポーネントをインストールする必要があります。 など。

- オペレーション データベース

- サーバー

- コンソール

- Windows PowerShell コマンドレット

- Web コンソール

- レポート

- データ ウェアハウス

> [!IMPORTANT]
> 「[Microsoft レポート ビューアー 2010 再頒布可能パッケージ](https://www.microsoft.com/en-us/download/details.aspx?id=6442)」では、System Center オペレーション マネージャー 2012 をインストールする前にインストールする必要があります。

これらの製品とインストールの詳細については、次のリンクを参照してください。

- [System Center Operations Manager 2012](https://go.microsoft.com/fwlink/p/?linkid=257527)

- [System Center Operations Manager 2007](https://technet.microsoft.com/en-us/library/bb735860.aspx)

ビジネス サーバー配置の Skype あたり 1 つだけのルート管理サーバーを持つことができることに留意してください。

## <a name="importing-the-skype-for-business-server-2019-management-packs"></a>Skype のビジネス サーバー 2019 の管理パックのインポート

管理パックをインストールすると、System Center Operations Manager の機能を拡張することができます-System Center Operations Manager の項目が決定を監視するソフトウェアがそれらの項目を監視する方法、およびアラートがトリガーされるようにする方法と報告します。 ビジネス サーバー 2019 の Skype には、次の機能を提供する 2 つの System Center Operations Manager 管理パックが含まれています。

- **コンポーネントとユーザーの管理パック**(Microsoft.LS.2019.Monitoring.ComponentAndUser.mp) は、ビジネスのサーバーのイベント ログに記録された、パフォーマンス カウンターが登録されている、または通話詳細記録 (Cdr) または高品質のエクスペリエンス (QoE) データベースに記録の問題は、Skype を追跡します。 重大な問題は、System Center Operations Manager は即座に管理者に通知する電子メール、インスタント メッセージ、または SMS メッセージを構成できます。 (SMS、またはショート メッセージ サービスは 1 つのモバイル デバイスからのテキスト メッセージを送信するに使用されるテクノロジ)。

    > [!NOTE]
    >  Operations Manager の通知の構成の詳細については、「[通知の構成](https://go.microsoft.com/fwlink/p/?LinkID=268785&amp;amp;clcid=0x409)」を参照してください。

- **作業中の監視管理パック**(Microsoft.LS.2019.Monitoring.ActiveMonitoring.mp) 積極的にテスト キー Skype ビジネス サーバーなどのコンポーネント、システムへのサインイン、インスタント メッセージを交換する、または公衆交換電話網 (PSTN の電話呼び出しを行う). ビジネス サーバー代理トランザクションのコマンドレットは、Skype を使用してこれらのテストが行われます。 たとえば、インスタント メッセージの 2 つのテスト ユーザー間での会話をシミュレートする**テスト CsIM**コマンドレットが使用されます。 このシミュレートされた会話が失敗した場合、アラートが生成されます。

管理パックのインポートは、必要不可欠なステップです。管理パックをインポートしていない場合は、Operations Manager を使用して Skype for Business Server イベントを監視することや、Skype for Business Server 代理トランザクションを実行することができません。

ビジネス サーバー 2019 Skype のみを監視するには、コンポーネントとユーザーの管理パックが使用されます。 共存シナリオではビジネス サーバー 2019 の Skype と Skype のビジネス サーバー 2015 の両方がインストールされている場合は、ビジネス サーバー 2015 のコンピューターに、Skype のビジネス サーバー 2015 管理パックは、Skype を使用して続行してください。

> [!NOTE]
> ビジネス サーバー 2019 の Skype の管理パックには、ビジネス サーバー 2019 作業中の監視管理パックのビジネス サーバー 2019 コンポーネントとユーザーの管理パックと、Skype は、Skype が含まれます。

次のいずれかのツールを使用して、管理パックをインポートできます。

- **System Center Operations Manager**この方法では、Skype のビジネス サーバーの監視を追加するのには、Operations Manager を使用します。

- **オペレーション マネージャーのシェル**を直接インポートするか、System Center Operations Manager コンソールを使用して管理パックをインポートするときに発生するすべての問題のトラブルシューティングを行うには、オペレーション マネージャーのシェルを使用できます。

### <a name="importing-the-management-packs-by-using-system-center-operations-manager"></a>System Center Operations Manager を使用した管理パックのインポート

1. マイクロソフトの Web ダウンロードから、SkypeForBusiness2019ManagementPacks.msi をダウンロードし、msi をインストールします。

2. System Center Operations Manager では、[**管理**] をクリックします。

3. 管理ウィンドウで、**管理パック**を右クリックし、[**管理パックのインポート**] をクリックします。

4. [**管理パックの選択**] ダイアログ ボックスで、[**追加**] をクリックし、[**ディスクから追加する**] をクリックします。

5. [**オンライン カタログ接続**] ダイアログ ボックスで、[**いいえ**] をクリックします。

6. **インポートする管理パックの選択**] ダイアログ ボックスで Microsoft.LS.2019.Monitoring.ActiveMonitoring.mp と Microsoft.LS.2019.Monitoring.ComponentAndUser.mp、ファイルを選択し、[**開く**] をクリックします。 ダイアログ ボックスで複数のファイルを選択するには、最初のファイルをクリックした後、Ctrl キーを押しながら 2 番目のファイルをクリックします。

7. [**管理パックの選択**] ダイアログ ボックスで、[**インストール**] をクリックします。エラー メッセージが表示されてインストールが失敗する場合は、通常、管理パックのファイルが Windows ユーザー アカウント制御によって保護されているフォルダー内にあることを意味します。その場合は、ファイルを別のフォルダーにコピーした後、インポートとインストールの処理を再度開始します。

8. [**管理パックの選択**] ダイアログ ボックスで、[**閉じる**] をクリックします。インポートとインストールの処理には数分かかることがあります。

## <a name="importing-the-management-packs-by-using-the-operations-manager-shell"></a>Operations Manager シェルを使用した管理パックのインポート

一般には、管理パックをインポートするには Operations Manager コンソールを使用する方が簡単です。ただし、エラーが発生してインポートが失敗する場合、コンソールでは適切にエラーが報告されないことがあります。これに対し、Operations Manager シェルでは詳細な情報が提供されます。Operations Manager を使用していて、管理パックのインポートに問題がある場合は、Operations Manager シェルを使用してパックをインポートしてください。Operations Manager シェルではインポートが失敗した理由の特定に役立つ可能性のある詳細な情報が提供されます。

1. [**スタート**]、[**すべてのプログラム**]、[**Microsoft System Center 2012**]、[**Operations Manager**] の順にクリックし、[**Operations Manager シェル**] をクリックします。

2. オペレーション マネージャー シェルでは、Microsoft.LS.2019.Monitoring.ActiveMonitoring.mp、ファイルのコピーには、実際のパスを使用して、コマンド プロンプトで次のコマンドを入力し、ENTER キーを押します。

   ```
   Import-SCOMManagementPack -FullName "D:\MP\Microsoft.LS.2019.Monitoring.ActiveMonitoring.mp"
   ```

3. 最初の管理パックをインポートした後は、Microsoft.LS.2019.Monitoring.ComponentAndUser.mp ファイルのコピーへのパスを使用して、プロセスを繰り返します。

   ```
   Import-SCOMManagementPack -FullName "D:\MP\Microsoft.LS.2019.Monitoring.ComponentAndUser.mp"
   ```