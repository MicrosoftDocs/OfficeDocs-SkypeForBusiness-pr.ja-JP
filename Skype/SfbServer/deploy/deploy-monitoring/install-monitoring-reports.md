---
title: '[監視レポートのインストール] Skype for Business Server'
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 6f417569-b100-442c-ad48-fdd794626cf7
description: '概要: 監視レポートを生成するサービスをインストールする方法について、Skype for Business Server。'
ms.openlocfilehash: bda56b297f9e4f46033cb6d09c46c61f56092b4c
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2021
ms.locfileid: "58581031"
---
# <a name="install-monitoring-reports-in-skype-for-business-server"></a>[監視レポートのインストール] Skype for Business Server
 
**概要:** 監視レポートを生成するサービスをインストールする方法については、Skype for Business Server。
  
Skype for Business Server監視レポートは、組織内で行う通信セッションの質と量に関する豊富な情報を提供します。 
  
## <a name="install-monitoring-reports"></a>監視レポートのインストール

監視レポートは、インストール時に自動的にインストールSkype for Business Server。代わりに、監視レポートを個別にインストールし、Skype for Business Serverインストールした後にのみインストールする必要があります。
  
> [!NOTE]
> 監視レポートは、監視データベースがインストールされているのと同じコンピューターにインストールすることをお勧めします。これにより、レポートへのアクセス許可の割り当てプロセスが簡単になります。監視ストアをホストしているコンピューターに監視レポートをインストールすると、別のコンピューター上で実行されている Reporting Services とデータベースが対話できるようにするためのアクセス許可を構成する必要がなくなります。 
  
Skype for Business Server監視レポートには、会議、ピアツーピア IM セッション、ユーザー登録、応答グループ アプリケーションなどの詳細情報を提供するように設計された 30 を超えるレポートが含まれます。 2013 バージョンの場合、Skype for Business Serverレポートには、次のような機能拡張が含まれます。
  
- **新しい音声品質レポート**。 これらの新しいレポートには[、Skype for Business Server](../../manage/health-and-monitoring/comparison.md)のメディア品質比較レポートが含まれます。これは、さまざまな種類の通話 (有線通話とワイヤレス通話の間など) の品質を比較します。ユーザーが[会議に](../../manage/health-and-monitoring/join-time-report.md)参加するために必要な時間の量に関する情報を提供する Skype for Business Server の会議参加時刻レポート。 
    
- **ビデオ共有セッションとアプリケーション共有セッションの両方を分析およびトラブルシューティングするためのレポートが改善されました。** Skype for Business Server の[メディア](../../manage/health-and-monitoring/summary.md)品質の概要レポートでは、ビデオとアプリケーションの共有呼び出しを分析する方法が提供され、Skype for Business Server の[サーバー](../../manage/health-and-monitoring/server-performance.md)パフォーマンス レポートでは、これらの呼び出しを生成するサーバーのパフォーマンスを詳細に示します。 ビデオとアプリケーション共有の指標は、Skype for Business Server のピア[](../../manage/health-and-monitoring/peer-to-peer-session-detail-report.md)ツーピア セッション詳細レポートと Skype for Business Server の会議詳細[レポートによっても報告されます](../../manage/health-and-monitoring/detail-report.md)。
    
- **レポートのパフォーマンスの向上**: 応答時間とデータ取得時間が短縮され、レポート間の移動をすばやく簡単に行えるようになりました。
    
個々のレポートの詳細については、監視レポートのドキュメントを参照してください。
  
> [!NOTE]
> 別のレポート (QoE 通話詳細サブレポート) は、Skype for Business Server。 ただし、このレポートは主に内部用であり、直接アクセスするためのものではありません。 
  
Skype for Business Server 監視レポートをインストールするには、Skype for Business Server 展開ウィザードを使用するか、Skype for Business Server インストール ファイルに含まれる Windows PowerShell スクリプトを使用できます。 どちらの方法でレポートをインストールする場合でも、最初に次のことを確認する必要があります。
  
- 監視データベースのユーザー アカウントにデータベースの役割を追加する権限を持っている。
    
- SQL Server Reporting Services のコンテンツ マネージャーの役割を持っている。この役割では、SQL Server Reporting Services にレポートを展開する権限が付与されます。
    
展開ウィザードを使用して監視レポートをインストールするには、次の手順を実行します。
  
1. [**スタート] ボタン**、[**すべてのプログラム] の** 順にクリックし、[Skype for Business Server]**をクリック** し、[展開ウィザードSkype for Business Server **クリックします**。
    
2. 展開ウィザードで [**監視レポートの展開**] をクリックして、監視レポートの展開ウィザードを開始します。
    
3. 監視レポートの展開ウィザードの [**監視データベースの指定**] ページで、[**監視データベース**] ドロップダウン リストに、監視ストアをホストしているコンピューターの完全修飾ドメイン名が表示されていることを確認します (複数の監視ストアがある場合は、ドロップダウン リストから適切なサーバーを選択する必要があります)。[**SQL Server Reporting Services (SSRS) インスタンス**] ボックスに正しい SQL Server インスタンス (たとえば **atl-sql-001.litwareinc.com/archinst**) が表示されていることを確認し、[**次へ**] をクリックします。
    
4. [**資格情報の指定**] ページの [**ユーザー名**] ボックスに、監視レポートへのアクセス時に使用するアカウントのドメイン名とユーザー名 (たとえば **litwareinc\kenmyer**) を入力します。 この形式 (domain\user name) を使用しない場合は、エラーが発生します。
    
    [**パスワード**] ボックスにユーザー アカウントのパスワードを入力し、[**次へ**] をクリックします。 このアカウントには特別な権限は必要ありません。 セットアップが完了すると、アカウントに必要なログオンとデータベースのアクセス許可が自動的に付与されます。
    
5. [**読み取り専用グループの指定**] ページの [ユーザー グループ] ボックスに、SQL Server Reporting Services への読み取り専用の管理者アクセス権を付与するセキュリティ グループの名前を入力します。たとえば、レポートへの読み取り専用の管理者アクセス権を付与するには、「**RTCUniversalReadOnlyAdmins**」と入力します。その後、[**次へ**] をクリックします。
    
6. [**コマンドを実行しています**] ページで、[**完了**] をクリックします。
    
監視レポートは、スクリプト を実行して、Skype for Business Server管理シェルからインストールDeployReports.ps1。このWindows PowerShellは \<install location\> 、\Skype for Business Server\Deployment\Setup フォルダーにあります。 管理シェルを使用して監視レポートDeployReports.ps1するには、管理シェル プロンプトで次のようなコマンドを入力します。
  
```powershell
C:\Program Files\Skype for Business Server 2015\Deployment\Setup\DeployReports.ps1 -storedUserName "litwareinc\kenmyer" -storedPassword "p@ssw0rd" -readOnlyGroupName "RTCUniversalReadOnlyAdmins" -reportServerSqlInstance "atl-sql-001.litwareinc.com" -monitoringDatabaseId "MonitoringDatabase:atl-sql-001.litwareinc.com"
```

このコマンドで使用されているパラメーターの説明を次の表に示します。
  
|**パラメーター名**|**必須**|**説明**|
|:-----|:-----|:-----|
|storedUserName  <br/> |はい  <br/> |監視ストアへのアクセスに使用するユーザーアカウント (形式はドメイン\ユーザー名)。次に例を示します。  <br/> ```-storedUserName "litwareinc\kenmyer"```このアカウントには、以前に指定したアクセス許可とSQL ServerアクセスSQL Server Reporting Services、スクリプトが失敗する必要があります。  <br/> |
|storedPassword  <br/> |はい  <br/> |監視ストアへのアクセスに使用するユーザー アカウントのパスワード。  <br/> |
|readOnlyGroupName  <br/> |いいえ  <br/> |監視レポートへの読み取り専用アクセス権を付与するユーザーが属するドメインまたはローカル セキュリティ グループ。 指定したグループが存在しない場合、スクリプトは失敗することに注意してください。 後でこれらのアクセス権を無効にしたり他のユーザーまたはグループにアクセス権を付与したりする必要が生じた場合は、SQL Service Reporting Services レポート マネージャーを使用して実行できます。  <br/> |
|reportSqlServerInstance  <br/> |いいえ  <br/> |Reporting Service をホストする SQL Server インスタンス。Reporting インスタンスは、レポート サーバーの完全修飾ドメイン名を使用して指定する必要があります。次に例を示します。<br/> ```-reportServerSqlInstance atl-sql-001.litwareinc.com```このパラメーターが含まれていない場合、スクリプトは、レポート サービスが監視データベースをホストする同じSQL Serverホストされている必要があります。  <br/> |
|monitoringDatabaseId  <br/> |いいえ  <br/> |監視データベースのサービス ID。次のコマンドを実行することで、監視データベースの ID を取得できます。<br/> ```Get-CsService -MonitoringDatabase```|
   
監視レポートがインストールされた後、New-CsReportingConfigurationコマンドレットを使用して、これらのレポートへのアクセスに使用する URL を構成する必要があります。 このタスクは、次のコマンドを実行Skype for Business Server管理シェルからWindows PowerShellできます。 レポート URL の構成時には、必須ではありませんが、HTTPS プロトコルを使用することをお勧めします。
  
```powershell
New-CsReportingConfiguration -Identity 'service:MonitoringDatabase:atl-sql-001.litwareinc.com' -ReportingURL 'https://atl-sql-001.litwareinc.com:443/Reports_ARCHINST'
```

上のコマンドでは、ReportingUrl プロパティを、SQL Server 2008 R2 Reporting Services で使用されているレポート マネージャー URL に設定する必要があります。レポート マネージャー URL は、SQL Server Reporting Services がインストールされているコンピューターで次の手順を実行することで確認できます。
  
1. [スタート]、[すべてのプログラム]、[Microsoft SQL Server 2008 R2] 、[構成ツール]、[Reporting Services 構成マネージャー] の順にクリックします。
    
2. [Reporting Services 構成の接続] ダイアログ ボックスで、Reporting Services コンピューターの名前が [サーバー名] ボックスに表示されていることを確認します。[レポート サーバー インスタンス] ドロップダウン リストから SQL Server インスタンスを選択し、[接続] をクリックします。
    
3. Reporting Services 構成マネージャーで、[レポート マネージャー URL] をクリックします。すると、[レポート マネージャー URL] ウィンドウに 1 つ以上の URL が表示されます。いずれの URL もレポート用 URL として使用できますが、上で説明したように ReportingUrl には HTTPS プロトコルを使用することをお勧めします。
    
監視データベースのミラー データベースを設定している場合は、監視レポートをミラー データベースに関連付ける必要があります。 詳細については、「[監視レポートをミラー データベースに関連付ける」の記事Skype for Business Server](monitoring-reports-with-a-mirror-database.md)参照してください。
  

