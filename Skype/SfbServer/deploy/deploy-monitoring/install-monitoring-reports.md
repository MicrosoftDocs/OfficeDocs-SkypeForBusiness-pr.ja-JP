---
title: Skype for Business Server での監視レポートのインストール
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 6f417569-b100-442c-ad48-fdd794626cf7
description: '概要: Skype for Business Server で監視レポートを生成するサービスをインストールする方法について学習します。'
ms.openlocfilehash: 10a98bea4af3511c50a0b2b814f8b44911f3742f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802257"
---
# <a name="install-monitoring-reports-in-skype-for-business-server"></a>Skype for Business Server での監視レポートのインストール
 
**概要:** Skype for Business Server で監視レポートを生成するサービスをインストールする方法について学習します。
  
Skype for Business Server Monitoring Reports は、組織で行う通信セッションの品質と量に関する豊富な情報を提供します。 
  
## <a name="install-monitoring-reports"></a>監視レポートのインストール

Skype for Business Server をインストールする場合、監視レポートは自動的にはインストールされません。代わりに、コンピューターに Skype for Business Server をインストールした後にのみ、監視レポートを個別にインストールする必要があります。
  
> [!NOTE]
> 監視レポートは、監視データベースがインストールされているのと同じコンピューターにインストールすることをお勧めします。これにより、レポートへのアクセス許可の割り当てプロセスが簡単になります。監視ストアをホストしているコンピューターに監視レポートをインストールすると、別のコンピューター上で実行されている Reporting Services とデータベースが対話できるようにするためのアクセス許可を構成する必要がなくなります。 
  
Skype for Business Server の監視レポートには、電話会議、ピアツーピア IM セッション、ユーザー登録、応答グループ アプリケーションなどの詳細情報を提供するために設計された 30 を超えるレポートが含まれます。 2013 バージョンの Skype for Business Server 監視レポートには、次のような多くの拡張機能が含まれます。
  
- **新しい音声品質レポート**。 これらの新しいレポートには [、Skype for Business Server](../../manage/health-and-monitoring/comparison.md)のメディア品質比較レポートが含まれます。このレポートは、さまざまな種類の通話 (有線通話とワイヤレス通話の間など) の品質を比較します。および [Skype for Business Server](../../manage/health-and-monitoring/join-time-report.md)の電話会議参加時間レポート。ユーザーが会議に参加するために必要な時間の量に関する情報を提供します。 
    
- **ビデオ共有セッションとアプリケーション共有セッションの両方を分析およびトラブルシューティングするためのレポートが改善されました。** [Skype for Business Server](../../manage/health-and-monitoring/summary.md)のメディア品質概要レポートは、ビデオ通話とアプリケーション共有通話を分析する方法を提供し[、Skype for Business Server](../../manage/health-and-monitoring/server-performance.md)のサーバー パフォーマンス レポートは、これらの通話を生成するサーバーのパフォーマンスを詳細に示します。 ビデオおよびアプリケーション共有の指標は [、Skype for Business Server](../../manage/health-and-monitoring/peer-to-peer-session-detail-report.md) のピアツーピア セッション詳細レポートおよび Skype for Business Server の電話会議詳細レポートでも [報告されます](../../manage/health-and-monitoring/detail-report.md)。
    
- **レポートのパフォーマンスの向上**: 応答時間とデータ取得時間が短縮され、レポート間の移動をすばやく簡単に行えるようになりました。
    
個々のレポートの詳細については、監視レポートのドキュメントを参照してください。
  
> [!NOTE]
> Skype for Business Server には、QoE 通話詳細サブレポートという別のレポートが含まれています。 ただし、このレポートは主に内部用であり、直接アクセスするためのものではありません。 
  
Skype for Business Server 監視レポートをインストールするには、Skype for Business Server 展開ウィザードを使用する方法と、Skype for Business Server インストール ファイルに含まれている Windows PowerShell スクリプトを使用する方法の 2 つがあります。 どちらの方法でレポートをインストールする場合でも、最初に次のことを確認する必要があります。
  
- 監視データベースのユーザー アカウントにデータベースの役割を追加する権限を持っている。
    
- SQL Server Reporting Services のコンテンツ マネージャーの役割を持っている。この役割では、SQL Server Reporting Services にレポートを展開する権限が付与されます。
    
展開ウィザードを使用して監視レポートをインストールするには、次の手順を実行します。
  
1. [ **スタート] ボタン**、[すべてのプログラム] **の順** にクリックし **、[Skype for Business Server]** をクリックして、[Skype for Business Server 展開ウィザード **] をクリックします**。
    
2. 展開ウィザードで [**監視レポートの展開**] をクリックして、監視レポートの展開ウィザードを開始します。
    
3. 監視レポートの展開ウィザードの [**監視データベースの指定**] ページで、[**監視データベース**] ドロップダウン リストに、監視ストアをホストしているコンピューターの完全修飾ドメイン名が表示されていることを確認します (複数の監視ストアがある場合は、ドロップダウン リストから適切なサーバーを選択する必要があります)。[**SQL Server Reporting Services (SSRS) インスタンス**] ボックスに正しい SQL Server インスタンス (たとえば **atl-sql-001.litwareinc.com/archinst**) が表示されていることを確認し、[**次へ**] をクリックします。
    
4. [**資格情報の指定**] ページの [**ユーザー名**] ボックスに、監視レポートへのアクセス時に使用するアカウントのドメイン名とユーザー名 (たとえば **litwareinc\kenmyer**) を入力します。 この形式 (ドメイン\ユーザー名) を使用しない場合は、エラーが発生します。
    
    [**パスワード**] ボックスにユーザー アカウントのパスワードを入力し、[**次へ**] をクリックします。 このアカウントには特別な権限は必要ありません。 セットアップが完了すると、アカウントに必要なログオンとデータベースのアクセス許可が自動的に付与されます。
    
5. [**読み取り専用グループの指定**] ページの [ユーザー グループ] ボックスに、SQL Server Reporting Services への読み取り専用の管理者アクセス権を付与するセキュリティ グループの名前を入力します。たとえば、レポートへの読み取り専用の管理者アクセス権を付与するには、「**RTCUniversalReadOnlyAdmins**」と入力します。その後、[**次へ**] をクリックします。
    
6. [**コマンドを実行しています**] ページで、[**完了**] をクリックします。
    
また、Skype for Business Server 管理シェルから監視レポートをインストールするには、次のスクリプトをDeployReports.ps1。このWindows PowerShellは \<install location\> 、\Skype for Business Server 2015\Deployment\Setup フォルダーにあります。 DeployReports.ps1 を使用して監視レポートをインストールするには、管理シェル プロンプトで次のようなコマンドを入力します。
  
```powershell
C:\Program Files\Skype for Business Server 2015\Deployment\Setup\DeployReports.ps1 -storedUserName "litwareinc\kenmyer" -storedPassword "p@ssw0rd" -readOnlyGroupName "RTCUniversalReadOnlyAdmins" -reportServerSqlInstance "atl-sql-001.litwareinc.com" -monitoringDatabaseId "MonitoringDatabase:atl-sql-001.litwareinc.com"
```

このコマンドで使用されているパラメーターの説明を次の表に示します。
  
|**パラメーター名**|**必須**|**説明**|
|:-----|:-----|:-----|
|storedUserName  <br/> |必要  <br/> |監視ストアへのアクセスに使用するユーザーアカウント (形式はドメイン\ユーザー名)。次に例を示します。  <br/> ```-storedUserName "litwareinc\kenmyer"``` このアカウントには、Reporting Services のアクセス許可とSQL Server以前SQL Serverが必要です。この場合、スクリプトは失敗します。  <br/> |
|storedPassword  <br/> |必要  <br/> |監視ストアへのアクセスに使用するユーザー アカウントのパスワード。  <br/> |
|readOnlyGroupName  <br/> |いいえ  <br/> |監視レポートへの読み取り専用アクセス権を付与するユーザーが属するドメインまたはローカル セキュリティ グループ。 指定したグループが存在しない場合、スクリプトは失敗することに注意してください。 後でこれらのアクセス権を無効にしたり他のユーザーまたはグループにアクセス権を付与したりする必要が生じた場合は、SQL Service Reporting Services レポート マネージャーを使用して実行できます。  <br/> |
|reportSqlServerInstance  <br/> |いいえ  <br/> |Reporting Service をホストする SQL Server インスタンス。Reporting インスタンスは、レポート サーバーの完全修飾ドメイン名を使用して指定する必要があります。次に例を示します。<br/> ```-reportServerSqlInstance atl-sql-001.litwareinc.com``` このパラメーターを指定しない場合、スクリプトは、レポート サービスが監視データベースをホストする同じ SQL Serverホストされている必要があります。  <br/> |
|monitoringDatabaseId  <br/> |いいえ  <br/> |監視データベースのサービス ID。次のコマンドを実行することで、監視データベースの ID を取得できます。<br/> ```Get-CsService -MonitoringDatabase```|
   
監視レポートをインストールした後、New-CsReportingConfiguration コマンドレットを使用して、これらのレポートへのアクセスに使用する URL を構成する必要があります。 このタスクは、次のコマンドを実行して Skype for Business Server 管理シェルからWindows PowerShellできます。 レポート URL の構成時には、必須ではありませんが、HTTPS プロトコルを使用することをお勧めします。
  
```powershell
New-CsReportingConfiguration -Identity 'service:MonitoringDatabase:atl-sql-001.litwareinc.com' -ReportingURL 'https://atl-sql-001.litwareinc.com:443/Reports_ARCHINST'
```

上のコマンドでは、ReportingUrl プロパティを、SQL Server 2008 R2 Reporting Services で使用されているレポート マネージャー URL に設定する必要があります。レポート マネージャー URL は、SQL Server Reporting Services がインストールされているコンピューターで次の手順を実行することで確認できます。
  
1. [スタート]、[すべてのプログラム]、[Microsoft SQL Server 2008 R2] 、[構成ツール]、[Reporting Services 構成マネージャー] の順にクリックします。
    
2. [Reporting Services 構成の接続] ダイアログ ボックスで、Reporting Services コンピューターの名前が [サーバー名] ボックスに表示されていることを確認します。[レポート サーバー インスタンス] ドロップダウン リストから SQL Server インスタンスを選択し、[接続] をクリックします。
    
3. Reporting Services 構成マネージャーで、[レポート マネージャー URL] をクリックします。すると、[レポート マネージャー URL] ウィンドウに 1 つ以上の URL が表示されます。いずれの URL もレポート用 URL として使用できますが、上で説明したように ReportingUrl には HTTPS プロトコルを使用することをお勧めします。
    
監視データベースのミラー データベースを設定している場合は、監視レポートをミラー データベースに関連付ける必要があります。 詳細については、「監視レポートを Skype for Business Server のミラー データベースに関連付 [ける」を](monitoring-reports-with-a-mirror-database.md) 参照してください。
  

