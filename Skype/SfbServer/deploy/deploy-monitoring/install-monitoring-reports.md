---
title: Skype for Business Server で監視レポートをインストールする
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 6f417569-b100-442c-ad48-fdd794626cf7
description: '概要: Skype for Business Server で監視レポートを生成するサービスをインストールする方法について説明します。'
ms.openlocfilehash: 6c8b7089a66abc3e0b1dcacb4bfa5c840f57ed36
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41789995"
---
# <a name="install-monitoring-reports-in-skype-for-business-server"></a>Skype for Business Server で監視レポートをインストールする
 
**概要:** Skype for Business Server で監視レポートを生成するサービスをインストールする方法について説明します。
  
Skype for Business Server Monitoring レポートは、組織内で行われる通信セッションの品質と量に関するさまざまな情報を提供します。 
  
## <a name="install-monitoring-reports"></a>監視レポートのインストール

Skype for Business Server をインストールしたときに、レポートの監視が自動的にインストールされません。代わりに、Skype for Business Server がコンピューターにインストールされている場合にのみ、監視レポートを個別にインストールする必要があります。
  
> [!NOTE]
> 監視レポートは、監視データベースがインストールされているのと同じコンピューターにインストールすることをお勧めします。この操作を行うと、レポートへのアクセス許可の割り当てプロセスが簡単になります。監視ストアをホストしているコンピューターに監視レポートをインストールすると、別のコンピューター上で実行されている Reporting Services とデータベースが対話できるようにするためのアクセス許可を構成する必要がなくなります。 
  
Skype for Business Server Monitoring レポートには、会議、ピアツーピア IM セッション、ユーザー登録、応答グループアプリケーションなどの詳細情報を提供するために、30個以上のレポートが含まれています。 2013バージョンでは、Skype for Business Server Monitoring レポートにはいくつかの拡張機能が含まれています。
  
- **新しい音声品質レポート**。 これらの新しいレポートには、 [Skype For Business Server のメディア品質比較レポート](../../manage/health-and-monitoring/comparison.md)が含まれており、さまざまな種類の通話 (たとえば、有線通話とワイヤレス通話の間) の品質を比較できます。[Skype For Business Server の会議参加時間レポート](../../manage/health-and-monitoring/join-time-report.md)と、ユーザーが会議に参加するのに必要な時間に関する情報を提供します。 
    
- **ビデオとアプリケーションの共有セッション両方の分析とトラブルシューティングを行うためのレポートが改善されました。** skype for [Business server のメディア品質の概要レポート](../../manage/health-and-monitoring/summary.md)では、ビデオとアプリケーションの共有通話を分析する方法が提供されます。また、 [Skype for Business Server のサーバーパフォーマンスレポート](../../manage/health-and-monitoring/server-performance.md)は、これらの通話を生成するサーバーのパフォーマンスを詳しく示します。 また、ビデオとアプリケーションの共有メトリックは、skype for [Business server のピアツーピアセッション詳細レポート](../../manage/health-and-monitoring/peer-to-peer-session-detail-report.md)と、 [Skype for Business Server の会議詳細レポート](../../manage/health-and-monitoring/detail-report.md)によって報告されるようになりました。
    
- **レポートのパフォーマンスの向上**: 応答時間とデータ取得時間が短縮され、レポート間の移動をすばやく簡単に行えるようになりました。
    
個々のレポートの詳細については、監視レポートのドキュメントを参照してください。
  
> [!NOTE]
> 別のレポート (QoE 通話の詳細サブレポート) が Skype for Business Server に含まれています。 ただし、このレポートは主に内部用であり、直接アクセスするためのものではありません。 
  
Skype for business Server の監視レポートをインストールするには、次の2つの方法があります。 Skype for Business Server 展開ウィザードを使用するか、Skype for business Server インストールファイルに含まれている Windows PowerShell スクリプトを使用することができます。 どちらの方法でレポートをインストールする場合でも、最初に次のことを確認する必要があります。
  
- 監視データベースのユーザー アカウントにデータベースの役割を追加する権限を持っている。
    
- SQL Server Reporting Services のコンテンツ マネージャーの役割を持っている。この役割では、SQL Server Reporting Services にレポートを展開する権限が付与されます。
    
展開ウィザードを使用して監視レポートをインストールするには、次の手順を実行します。
  
1. [**スタート**] をクリックし、[**すべてのプログラム**] をクリックし、[ **skype for business server**] をクリックして、[ **skype for business server Deployment ウィザード**] をクリックします。
    
2. 展開ウィザードで [**監視レポートの展開**] をクリックして、監視レポートの展開ウィザードを開始します。
    
3. 監視レポートの展開ウィザードの [**監視データベースの指定**] ページで、[**監視データベース**] ドロップダウン リストに、監視ストアをホストしているコンピューターの完全修飾ドメイン名が表示されていることを確認します (複数の監視ストアがある場合は、ドロップダウン リストから適切なサーバーを選択する必要があります)。[**SQL Server Reporting Services (SSRS) インスタンス**] ボックスに正しい SQL Server インスタンス (たとえば **atl-sql-001.litwareinc.com/archinst**) が表示されていることを確認し、[**次へ**] をクリックします。
    
4. [**資格情報の指定**] ページの [**ユーザー名**] ボックスに、監視レポートへのアクセス時に使用するアカウントのドメイン名とユーザー名 (たとえば **litwareinc\kenmyer**) を入力します。この形式 (ドメイン\ユーザー名) を使用しない場合はエラーが発生します。
    
    [**パスワード**] ボックスにユーザー アカウントのパスワードを入力し、[**次へ**] をクリックします。このアカウントに特別な権限は必要ありません。セットアップが完了すると、このアカウントには必要なログオンおよびデータベース アクセス許可が自動的に付与されます。
    
5. [**読み取り専用グループの指定**] ページの [ユーザー グループ] ボックスに、SQL Server Reporting Services への読み取り専用の管理者アクセス権を付与するセキュリティ グループの名前を入力します。たとえば、レポートへの読み取り専用の管理者アクセス権を付与するには、「**RTCUniversalReadOnlyAdmins**」と入力します。その後、[**次へ**] をクリックします。
    
6. [**コマンドを実行しています**] ページで、[**完了**] をクリックします。
    
また、監視レポートは、「Skype for Business Server 管理シェル」でスクリプトの DeployReports を実行してインストールすることもできます。この Windows PowerShell スクリプトは、 \<インストール場所\>\ Skype for business Server 2015 \ Deployment\Setup フォルダーにあります。 DeployReports. ps1 を使って監視レポートをインストールするには、管理シェルプロンプトで次のようなコマンドを入力します。
  
```powershell
C:\Program Files\Skype for Business Server 2015\Deployment\Setup\DeployReports.ps1 -storedUserName "litwareinc\kenmyer" -storedPassword "p@ssw0rd" -readOnlyGroupName "RTCUniversalReadOnlyAdmins" -reportServerSqlInstance "atl-sql-001.litwareinc.com" -monitoringDatabaseId "MonitoringDatabase:atl-sql-001.litwareinc.com"
```

このコマンドで使用されているパラメーターの説明を次の表に示します。
  
|**パラメーター名**|**必須**|**説明**|
|:-----|:-----|:-----|
|storedUserName  <br/> |はい  <br/> |監視ストアへのアクセスに使用するユーザーアカウント (形式はドメイン\ユーザー名)。次に例を示します。  <br/> ```-storedUserName "litwareinc\kenmyer"```このアカウントには、以前に指定した SQL Server と SQL Server Reporting Services の権限が必要です。また、スクリプトは失敗します。  <br/> |
|storedPassword  <br/> |はい  <br/> |監視ストアへのアクセスに使用するユーザー アカウントのパスワード。  <br/> |
|readOnlyGroupName  <br/> |いいえ  <br/> |監視レポートへの読み取り専用アクセス権を付与するユーザーが属するドメインまたはローカル セキュリティ グループ。指定したグループが存在しない場合、スクリプトは失敗することに注意してください。後でこれらのアクセス権を無効にしたり他のユーザーまたはグループにアクセス権を付与したりする必要が生じた場合は、SQL Service Reporting Services レポート マネージャーを使用して実行できます。  <br/> |
|reportSqlServerInstance  <br/> |いいえ  <br/> |Reporting Service をホストする SQL Server インスタンス。Reporting インスタンスは、レポート サーバーの完全修飾ドメイン名を使用して指定する必要があります。次に例を示します。<br/> ```-reportServerSqlInstance atl-sql-001.litwareinc.com```このパラメーターが含まれていない場合、スクリプトは、監視データベースをホストする同じ SQL Server インスタンスによってレポートサービスがホストされていることを前提としています。  <br/> |
|monitoringDatabaseId  <br/> |いいえ  <br/> |監視データベースのサービス ID。次のコマンドを実行することで、監視データベースの ID を取得できます。<br/> ```Get-CsService -MonitoringDatabase```|
   
監視レポートのインストールが完了したら、New-CsReportingConfiguration コマンドレットを使用して、これらのレポートへのアクセスに使用する URL を構成する必要があります。 このタスクは、次の Windows PowerShell コマンドを実行して、Skype for Business Server 管理シェルから実行できます。 レポート URL の構成時には、必須ではありませんが、HTTPS プロトコルを使用することをお勧めします。
  
```powershell
New-CsReportingConfiguration -Identity 'service:MonitoringDatabase:atl-sql-001.litwareinc.com' -ReportingURL 'https://atl-sql-001.litwareinc.com:443/Reports_ARCHINST'
```

上のコマンドでは、ReportingUrl プロパティを、SQL Server 2008 R2 Reporting Services で使用されているレポート マネージャー URL に設定する必要があります。レポート マネージャー URL は、SQL Server Reporting Services がインストールされているコンピューターで次の手順を実行することで確認できます。
  
1. [スタート]、[すべてのプログラム]、[Microsoft SQL Server 2008 R2]、[構成ツール]、[Reporting Services 構成マネージャー] の順にクリックします。
    
2. [Reporting Services 構成の接続] ダイアログ ボックスで、Reporting Services コンピューターの名前が [サーバー名] ボックスに表示されていることを確認します。[レポート サーバー インスタンス] ドロップダウン リストから SQL Server インスタンスを選択し、[接続] をクリックします。
    
3. Reporting Services 構成マネージャーで、[レポート マネージャー URL] をクリックします。すると、[レポート マネージャー URL] ウィンドウに 1 つ以上の URL が表示されます。いずれの URL もレポート用 URL として使用できますが、前述のように、ReportingUrl には HTTPS プロトコルを使用することをお勧めします。
    
監視データベースのミラー データベースを設定した場合は、監視レポートをミラー データベースとも関連付ける必要があります。 詳細については、「 [Skype For Business Server のミラーデータベースに監視レポートを関連付ける](monitoring-reports-with-a-mirror-database.md)」を参照してください。
  

