---
title: Skype for Business Server 2015 への監視レポートのインストール
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 7/21/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6f417569-b100-442c-ad48-fdd794626cf7
description: '概要: は、Skype のビジネス サーバー 2015 の監視レポートを生成するサービスをインストールする方法を説明します。'
ms.openlocfilehash: 239274c6692358c06863d2e074bda1daf9d6c6b3
ms.sourcegitcommit: a79668bb45b73a63bea5c249d76a4c4c2530a096
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/05/2018
ms.locfileid: "19569548"
---
# <a name="install-monitoring-reports-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 への監視レポートのインストール
 
**の概要:** Skype のビジネス サーバー 2015 の監視レポートを生成するサービスをインストールする方法について説明します。
  
ビジネス サーバー 2015 監視レポートの Skype では、品質と組織内で行われる通信セッションの数に関する情報が豊富に提供します。 
  
## <a name="install-monitoring-reports"></a>監視レポートのインストール

ビジネス サーバー 2015; の Skype をインストールすると、監視レポートが自動的にインストールされません。代わりに、個別に監視レポートをインストールする必要があり、だけ後に Skype ビジネス サーバーがコンピューターにインストールされています。
  
> [!NOTE]
> 監視レポートは、監視データベースがインストールされているのと同じコンピューターにインストールすることをお勧めします。この操作を行うと、レポートへのアクセス許可の割り当てプロセスが簡単になります。監視ストアをホストしているコンピューターに監視レポートをインストールすると、別のコンピューター上で実行されている Reporting Services とデータベースが対話できるようにするためのアクセス許可を構成する必要がなくなります。 
  
Skype ビジネス サーバー レポートの監視には、会議、ピア ツー ピア IM セッション、ユーザー登録、応答グループ アプリケーション、およびその他の詳細な情報を提供するように設計された 30 以上のレポートが含まれます。 2013 バージョンでは、Skype ビジネス サーバーの監視のレポートには、拡張機能の番号です。
  
- **新しい音声の品質評価レポート**。 これらの新しいレポートには、[ビジネス サーバー 2015 の Skype でメディアの品質の比較レポート](../../manage/health-and-monitoring/comparison.md)を別の種類 (たとえば、ワイヤード (有線) の呼び出しとワイヤレスの呼び出し) の間の呼び出しの間での品質を比較するが含まれます。ユーザーが会議に参加する[ビジネス サーバー 2015 の Skype で会議参加時のレポート](../../manage/health-and-monitoring/join-time-report.md)の時間に関する情報を提供する必要があります。 
    
- **分析とトラブルシューティングの両方のビデオとアプリケーションの共有セッションのレポートを向上します。** [ビジネス サーバー 2015 の Skype でのメディア品質概要レポート](../../manage/health-and-monitoring/summary.md)には、ビデオ、および[ビジネス サーバー 2015 の Skype のサーバー パフォーマンス レポート](../../manage/health-and-monitoring/server-performance.md)の詳細をサーバーのパフォーマンスの中に、呼び出しを共有するアプリケーションを分析する方法が用意されています。これらの呼び出しを生成します。 ビデオ、およびアプリケーションの測定値を共有するようになりました、[ビジネス サーバー 2015 の Skype でのピア ツー ピア セッション詳細レポート](../../manage/health-and-monitoring/peer-to-peer-session-detail-report.md)と[ビジネス サーバー 2015 の Skype で会議の詳細] レポート](../../manage/health-and-monitoring/detail-report.md)で報告されます。
    
- **レポートのパフォーマンスの向上**: 応答時間とデータ取得時間が短縮され、レポート間の移動をすばやく簡単に行えるようになりました。
    
個々のレポートの詳細については、監視レポートのドキュメントを参照してください。
  
> [!NOTE]
> ビジネス サーバー 2015 の Skype に含まれている別のレポートの QoE を呼び出す詳細サブレポートには。 ただし、このレポートは主に内部用であり、直接アクセスするためのものではありません。 
  
ビジネス サーバー監視レポートの Skype をインストールするのには 2 つの方法: ビジネス サーバーの展開ウィザードは、Skype を使用するか、Skype ビジネス サーバー 2015 ファイルのインストールに含まれている Windows PowerShell スクリプトを使用することができます。 どちらの方法でレポートをインストールする場合でも、最初に次のことを確認する必要があります。
  
- 監視データベースのユーザー アカウントにデータベースの役割を追加する権限を持っている。
    
- SQL Server Reporting Services のコンテンツ マネージャーの役割を持っている。この役割では、SQL Server Reporting Services にレポートを展開する権限が付与されます。
    
展開ウィザードを使用して監視レポートをインストールするには、次の手順を実行します。
  
1. [**スタート**] ボタン [**すべてのプログラム**] をクリックして、 **Skype**、 **Skype ビジネス サーバーの展開ウィザード**] をクリックします。
    
2. 展開ウィザードで [**監視レポートの展開**] をクリックして、監視レポートの展開ウィザードを開始します。
    
3. 監視レポートの展開ウィザードの [**監視データベースの指定**] ページで、[**監視データベース**] ドロップダウン リストに、監視ストアをホストしているコンピューターの完全修飾ドメイン名が表示されていることを確認します (複数の監視ストアがある場合は、ドロップダウン リストから適切なサーバーを選択する必要があります)。[**SQL Server Reporting Services (SSRS) インスタンス**] ボックスに正しい SQL Server インスタンス (たとえば **atl-sql-001.litwareinc.com/archinst**) が表示されていることを確認し、[**次へ**] をクリックします。
    
4. [**資格情報の指定**] ページの [**ユーザー名**] ボックスに、監視レポートへのアクセス時に使用するアカウントのドメイン名とユーザー名 (たとえば **litwareinc\kenmyer**) を入力します。この形式 (ドメイン\ユーザー名) を使用しない場合はエラーが発生します。
    
    [**パスワード**] ボックスにユーザー アカウントのパスワードを入力し、[**次へ**] をクリックします。このアカウントに特別な権限は必要ありません。セットアップが完了すると、このアカウントには必要なログオンおよびデータベース アクセス許可が自動的に付与されます。
    
5. [**読み取り専用グループの指定**] ページの [ユーザー グループ] ボックスに、SQL Server Reporting Services への読み取り専用の管理者アクセス権を付与するセキュリティ グループの名前を入力します。たとえば、レポートへの読み取り専用の管理者アクセス権を付与するには、「**RTCUniversalReadOnlyAdmins**」と入力します。その後、[**次へ**] をクリックします。
    
6. [**コマンドを実行しています**] ページで、[**完了**] をクリックします。
    
レポートを監視するインストールすることも、Skype からビジネス サーバー管理シェルの DeployReports.ps1 はスクリプトを実行して、この Windows PowerShell スクリプトを参照して、\<インストール場所\>\Skype ビジネス サーバーの 2015\Deployment\Setup のフォルダーにします。 DeployReports.ps1 を使用して監視のレポートをインストールするには、管理シェル プロンプトで次のようなコマンドを入力します。
  
```
C:\Program Files\Skype for Business Server 2015\Deployment\Setup\DeployReports.ps1 -storedUserName "litwareinc\kenmyer" -storedPassword "p@ssw0rd" -readOnlyGroupName "RTCUniversalReadOnlyAdmins" -reportServerSqlInstance "atl-sql-001.litwareinc.com" -monitoringDatabaseId "MonitoringDatabase:atl-sql-001.litwareinc.com"
```

このコマンドで使用されているパラメーターの説明を次の表に示します。
  
|**パラメーター名**|**必須**|**説明**|
|:-----|:-----|:-----|
|storedUserName  <br/> |はい  <br/> |監視ストアへのアクセスに使用するユーザーアカウント (形式はドメイン\ユーザー名)。次に例を示します。  <br/> ```-storedUserName "litwareinc\kenmyer"```このアカウントには、以前に指定された SQL Server および SQL Server Reporting Services のアクセス許可が必要か、スクリプトは失敗します。  <br/> |
|storedPassword  <br/> |はい  <br/> |監視ストアへのアクセスに使用するユーザー アカウントのパスワード。  <br/> |
|readOnlyGroupName  <br/> |いいえ  <br/> |監視レポートへの読み取り専用アクセス権を付与するユーザーが属するドメインまたはローカル セキュリティ グループ。指定したグループが存在しない場合、スクリプトは失敗することに注意してください。後でこれらのアクセス権を無効にしたり他のユーザーまたはグループにアクセス権を付与したりする必要が生じた場合は、SQL Service Reporting Services レポート マネージャーを使用して実行できます。  <br/> |
|reportSqlServerInstance  <br/> |いいえ  <br/> |Reporting Service をホストする SQL Server インスタンス。Reporting インスタンスは、レポート サーバーの完全修飾ドメイン名を使用して指定する必要があります。次に例を示します。<br/> ```-reportServerSqlInstance atl-sql-001.litwareinc.com```このパラメーターが含まれていない場合、スクリプトは、レポート サービスは、監視データベースをホストしている同じ SQL Server インスタンスによってホストされていると見なされます。  <br/> |
|monitoringDatabaseId  <br/> |いいえ  <br/> |監視データベースのサービス ID。次のコマンドを実行することで、監視データベースの ID を取得できます。<br/> ```Get-CsService -MonitoringDatabase```|
   
監視レポートのインストールが完了したら、New-CsReportingConfiguration コマンドレットを使用して、これらのレポートへのアクセスに使用する URL を構成する必要があります。 このタスク実行できます、Skype からビジネス サーバー管理シェルの次の Windows PowerShell コマンドを実行することによって。 レポート URL の構成時には、必須ではありませんが、HTTPS プロトコルを使用することをお勧めします。
  
```
New-CsReportingConfiguration -Identity 'service:MonitoringDatabase:atl-sql-001.litwareinc.com' -ReportingURL 'https://atl-sql-001.litwareinc.com:443/Reports_ARCHINST'
```

上のコマンドでは、ReportingUrl プロパティを、SQL Server 2008 R2 Reporting Services で使用されているレポート マネージャー URL に設定する必要があります。レポート マネージャー URL は、SQL Server Reporting Services がインストールされているコンピューターで次の手順を実行することで確認できます。
  
1. [スタート]、[すべてのプログラム]、[Microsoft SQL Server 2008 R2]、[構成ツール]、[Reporting Services 構成マネージャー] の順にクリックします。
    
2. [Reporting Services 構成の接続] ダイアログ ボックスで、Reporting Services コンピューターの名前が [サーバー名] ボックスに表示されていることを確認します。[レポート サーバー インスタンス] ドロップダウン リストから SQL Server インスタンスを選択し、[接続] をクリックします。
    
3. Reporting Services 構成マネージャーで、[レポート マネージャー URL] をクリックします。すると、[レポート マネージャー URL] ウィンドウに 1 つ以上の URL が表示されます。いずれの URL もレポート用 URL として使用できますが、前述のように、ReportingUrl には HTTPS プロトコルを使用することをお勧めします。
    
監視データベースのミラー データベースを設定した場合は、監視レポートをミラー データベースとも関連付ける必要があります。 [ビジネス サーバー 2015 の Skype でミラー データベースを使用して監視レポートを関連付ける](monitoring-reports-with-a-mirror-database.md)詳細についてはこの資料を参照してください。
  

