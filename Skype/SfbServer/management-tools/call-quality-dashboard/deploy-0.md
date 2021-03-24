---
title: Skype for Business Server の通話品質ダッシュボードの展開
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 287f64f5-0f8a-455a-8979-7b34bf0217bb
description: '概要: 通話品質ダッシュボードの展開プロセスについて説明します。 通話品質ダッシュボードは、Skype for Business Server 用のツールです。'
ms.openlocfilehash: 1f59209575284035fcdca52e4f18220aa05337af
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51114113"
---
# <a name="deploy-call-quality-dashboard-for-skype-for-business-server"></a>Skype for Business Server の通話品質ダッシュボードの展開
 
**概要:** 通話品質ダッシュボードの展開プロセスについて説明します。 通話品質ダッシュボードは、Skype for Business Server 用のツールです。
  
## <a name="deployment-overview"></a>展開の概要

通話品質ダッシュボード (CQD) は、次の 3 つの主要なコンポーネントで構成されます。
  
- **アーカイブ データベース**:QoE (Quality of Experience) データがレプリケートおよび保存されます。
    
- **キューブ**:QoE アーカイブ データベースのデータが集約され、最適化された高速アクセスが可能です。
    
- **ユーザーが** QoE データを簡単にクエリおよび視覚化できるポータル。
    
![CQD コンポーネント](../../media/ef3359b1-c98b-4cc5-a549-c84c6e03c011.png)
  
QoE アーカイブのセットアップ プロセスでは、QoE アーカイブ データベースを作成し、ソース QoE Metrics データベースから QoE アーカイブ データベースにデータを移動する SQL Server ストアド プロシージャを展開し、SQL Server Agent ジョブをセットアップして一定の間隔でストアド プロシージャを実行します。 
  
キューブ展開は、QoE アーカイブが配置されている場所に関する情報をユーザーから取得し、キューブを展開し、定期的にキューブを更新する通常の SQL Server エージェント ジョブを設定します。
  
ポータル インストールでは、CQD ユーザーのマッピングを各ユーザーのレポート/クエリに格納するリポジトリ データベースを作成します。 次に、ユーザーが事前に定義された一連のレポートを表示できるダッシュボードである IIS Web アプリケーションをセットアップし、キューブからのデータを視覚化するための独自のクエリをカスタマイズして作成します。 ポータル インストールでは、ユーザーがプログラムによってリポジトリとキューブにアクセスする API を公開する 2 つの追加の Web アプリケーションが作成されます。 (これらの API は、ダッシュボードでも内部的に使用されます)。
  

|**フェーズ**|**手順**|**役割とグループ メンバーシップ**|**ドキュメント**|
|:-----|:-----|:-----|:-----|
|前提条件のハードウェアとソフトウェアをインストールします。  <br/> |CQD 構成を決定し、インストールをSQL Serverを選択します。  <br/> |ローカルの Administrators グループのメンバーであるドメイン ユーザー。  <br/> |展開のドキュメントの「インストール前の要件」セクション。  <br/> |
|CQD をインストールします。  <br/> |展開ドキュメントに従って MSI を実行します。  <br/> |セットアップを実行するには、インストール アカウントは、ローカル管理者グループのメンバーであり、監視サーバー上の QoE Metrics データベースへの読み取りアクセス権を持つドメイン ユーザーである必要があります。  <br/> |展開に関するドキュメントの「アカウントと展開の手順」セクション。  <br/> |
|ユーザー アクセスを許可します。  <br/> |ポータルへのユーザー承認を管理するには、IIS 7.0 で導入された URL 承認を使用することをお勧めします。 詳細については [、「IIS 7.0 URL の承認について」を参照してください](https://www.iis.net/learn/manage/configuring-security/understanding-iis-url-authorization)。  <br/> |ローカルの Administrators グループのメンバーであるドメイン ユーザー。  <br/> |展開に関するドキュメントの「ポータルのユーザー アクセスの管理」セクション。  <br/> |
|オプション: サブネット マッピング情報を提供します。  <br/> |QoE アーカイブ データベースにネットワークと構築マッピング テーブルを設定します。  <br/> |QoE アーカイブ データベースへの書き込みアクセス権を持つアカウント。  <br/> |ユーザードキュメントの「サブネット情報の提供」セクション。  <br/> |
   


通話品質ダッシュボードの展開には、インフラストラクチャのセットアップとソフトウェアのインストールが含まれる。 次の手順では、プロセスの概要を示します。
  
## <a name="deployment-steps"></a>展開手順

1. CQD CallQualityDashboard.msiアーカイブ データベース コンポーネントをインストールするコンピューターにコピーします (これは、インストールされているSQL Serverです)。 
    
2. MSI を実行します (Windows は管理者特権で実行するように求めるプロンプトが表示されます。実行します)。 
    
3. EULA を受け入れる。
    
4. [品質ダッシュボードの呼び出し] コンポーネントに関連するファイルが既定の場所にあるか、既定の場所を受け入れる保存先フォルダーを選択します。
    
5. すべての機能を選択します。
    
6. [QoE アーカイブ構成] ページで、次の情報を入力します。
    
   - **QoE のSQL Server:** SQL Server QoE Metrics DB がある場所のインスタンス名を指定します (これはデータ ソースになります)。
    
   - **QoE アーカイブ SQL Server名:** これは読み取り専用フィールドであり、ローカル コンピューターの完全修飾ドメイン名に固定されています。 アーカイブ DB は、ローカル コンピューターにのみインストールできます。
    
   - **QoE アーカイブ SQL Serverインスタンス:** アーカイブ DB SQL Serverするローカル インスタンス名です。 既定のインスタンスを使用SQL Server、このフィールドは空白のままにします。 名前付きインスタンスをSQL Serverするには、インスタンス名 ("の後の名前など) を指定します \" 。
    
   - **QoE アーカイブ データベース:** 既定では、このオプションは "新しいデータベースの作成" に設定されています。 アーカイブ DB のアップグレードはサポートされていないので、"既存のデータベースを使用する" オプションを使用できる唯一の状況は、既存のアーカイブ データベースがインストールするビルドと同じスキーマを持つ場合です。
    
   - **データベース ファイル ディレクトリ:** アーカイブ DB のデータベース ファイル (.mdf と .ldf) を配置する場所へのパス。 これは、OS とは別のドライブ (推奨ハードウェア構成の HDD2) にある必要があります。 ファイル名はインストールで固定されていますので、競合の可能性を回避するために、ファイルがない空のディレクトリを使用してください。
    
   - **複数のパーティションを使用する:** 既定値は "複数パーティション" に設定され、ビジネス インテリジェンス エディションまたはエンタープライズ エディションのビジネス インテリジェンス エディションが必要SQL Server。 [標準エディション] で、[単一パーティション] オプションを選択します。 単一パーティションを使用すると、キューブ処理のパフォーマンスが影響を受け得る場合があります。
    
     > [!NOTE]
     > [複数のパーティションを使用する] オプションの選択は、セットアップが完了すると変更できません。 キューブ機能を変更するには、まずコントロール パネルの [変更] オプションを使用してアンインストールしてから再インストールする必要があります。 
  
   - **パーティション ファイル ディレクトリ:** QoE アーカイブ データベースのパーティションを配置する場所へのパス。 これは、OS ドライブとデータベース ログ ファイル ドライブとは別のドライブ (推奨ハードウェア構成の HDD3) 上SQL必要があります。 ファイル名はインストールで固定されていますので、競合の可能性を回避するために、ファイルがない空のディレクトリを使用してください。
    
   - **SQL エージェント ジョブ ユーザー - ユーザー名 &amp; パスワード:** SQL Server エージェント ジョブの "QoE アーカイブ データ" ステップを実行するために使用されるドメイン サービス アカウント名とパスワード (マスク) (これは、QoE Metrics DB からアーカイブ DB にデータをフェッチするためにストアド プロシージャを実行します。そのため、このアカウントは[アカウント] セクションに示されている QoE Metrics DB への読み取りアクセス権を持っている必要があります。 このアカウントには、QoE アーカイブ サーバー インスタンスにログインSQL Serverがあります)。
    
     > [!NOTE]
     > NT SERVICE\MSSQLSERVER など、SQL Server インスタンスが実行されているアカウントには、インストールが成功するには、上記のディレクトリへのアクセス/アクセス許可が必要です。 詳細については [、「Configure File System Permissions for Database Engine Access」を参照してください。](/previous-versions/sql/sql-server-2012/jj219062(v=sql.110))
  
7. [次へ] をクリックすると、インストーラーは前提条件のチェックを実行し、問題が発生した場合に報告します。 すべての前提条件のチェックが合格すると、インストーラーは [キューブ構成] ページに移動します。 
    
    > [!NOTE]
    > QoE Archive SQL Server インスタンスの SQL Server エージェント サービスが現在実行されていないという警告メッセージがインストーラーに表示される場合は、インストールを続行できますが、インストール後は、SQL エージェント サービスが実行され、スケジュールされたジョブが実行されるスタートアップの種類を [自動] に設定してください。 
  
8. [キューブの構成] ページで、次の情報を入力します。
    
   - **QoE アーカイブ SQL Server名:** これは読み取り専用フィールドであり、ローカル コンピューターの完全修飾ドメイン名に固定されています。 キューブは、QoE アーカイブ データベースを持つコンピューターからのみインストールできます (注。 キューブ自体がリモート コンピューターにインストールされている可能性があります。 以下を参照)
    
   - **QoE アーカイブ SQL Serverインスタンス:** SQL Server Db が保存されているインスタンス名を指定します。 既定のインスタンスを指定SQL Server、このフィールドは空白のままにします。 名前付きインスタンスをSQL Serverするには、インスタンス名 ("の後の名前など) を入力します \" 。 QoE アーカイブ コンポーネントがインストール用に選択されている場合、このフィールドには、[QoE アーカイブ構成] ページに指定された値が事前に入力されます。
    
   - **キューブ分析サーバー:** SQL Server作成する Analysis Service インスタンス名を指定します。 これは別のコンピューターにすることもできますが、インストールユーザーは Analysis Service インスタンスのターゲットサーバー管理者のSQL Server必要があります。
    
     > [!NOTE]
     >  Analysis Services Server 管理者権限の構成の詳細については、「Grant [Server Administrator Permissions (Analysis Services)」を参照してください。](/analysis-services/instances/grant-server-admin-rights-to-an-analysis-services-instance?viewFallbackFrom=sql-server-ver15)
  
   - **複数のパーティションを使用する:** 既定値は "複数パーティション" に設定され、ビジネス インテリジェンス エディションまたはエンタープライズ エディションのビジネス インテリジェンス エディションが必要SQL Server。 [標準エディション] で、[単一パーティション] オプションを選択します。 単一パーティションを使用すると、キューブ処理のパフォーマンスが影響を受け得る場合があります。
    
     > [!NOTE]
     >  [複数のパーティションを使用する] オプションの選択は、セットアップが完了すると変更できません。 キューブ機能を変更するには、まずコントロール パネルの [変更] オプションを使用してアンインストールしてから再インストールする必要があります。
  
   - **キューブ ユーザー - ユーザー名 &amp; パスワード:** キューブ処理をトリガーするドメイン サービス アカウント名とパスワード (マスク)。 QoE アーカイブ コンポーネントがインストール用に選択されている場合、このフィールドには、SQL エージェント ジョブ ユーザーの [アーカイブ構成] ページに指定された値が事前に入力されますが、セットアップで必要な特権を最小に設定できるよう、別のドメイン サービス アカウントを指定することをお勧めします。
    
9. [次へ] をクリックすると、別の検証が実行され、問題が報告されます。 検証が正常に完了すると、インストーラーは [ポータル構成] ページに移動します。 
    
10. [ポータルの構成] ページで、次の情報を入力します。
    
    - **QoE アーカイブ SQL Server:** SQL Server QoE アーカイブ データベースがある場所のインスタンス名を指定します。 [QoE アーカイブ構成] ページと [キューブ構成] ページとは異なり、コンピューター名は固定されていないので、指定する必要があります。 QoE アーカイブ コンポーネントがインストール用に選択されている場合、このフィールドには、[QoE アーカイブ構成] ページに指定された値が事前に入力されます。
    
    - **キューブ分析サーバー:** SQL Server場所の Analysis Service インスタンス名を指定します。 インストールにキューブ コンポーネントが選択されている場合、このフィールドには、[キューブ構成] ページに表示される値が事前に入力されます。
    
    - **リポジトリ SQL Server:** SQL Serverデータベースを作成するインスタンス名を指定します。 QoE アーカイブ データベースがある場所の SQL Server インスタンス名がセットアップの前に (他のコンポーネントで) 提供されている場合、このフィールドには QoE Archive DB SQL Server インスタンス名が事前に入力されます。 これは、任意のインスタンスSQL Serverできます。
    
    - **リポジトリ データベース:** 既定では、オプションは "新しいデータベースの作成" に設定されます。 リポジトリ DB のアップグレードはサポートされていないので、"既存のデータベースを使用する" オプションを使用できる唯一の状況は、既存のリポジトリ DB がインストールするビルドと同じスキーマを持つ場合です。
    
    - **IIS アプリ プール ユーザー - ユーザー名 &amp; パスワード:** IIS アプリケーション プールを実行するアカウント。 組み込みのシステム アカウントが選択されている場合、[ユーザー名] フィールドと [パスワード] フィールドはグレー表示されます。 これらのフィールドは、ユーザーがドメイン サービス アカウント情報を入力できるよう、ドロップダウン ボックスから [その他] が選択されている場合にのみ有効になります。
    
11. [次へ] をクリックすると、検証の最終ラウンドが実行され、SQL Server インスタンスに提供された資格情報を使用してアクセス可能であり、コンピューター上で IIS が使用できます。 検証が正常に完了すると、インストーラーはセットアップを続行します。 
    
インストーラーが完了すると、ほとんどの場合、SQL Serverエージェント ジョブが進行中であり、QoE データの初期負荷とキューブ処理が実行されます。 QoE のデータ量に応じて、ポータルにはまだ表示できるデータがありません。 データの読み込みとキューブ処理の状態を確認するには、に移動します  `http://<machinename>/CQD/#/Health` 。 
> [!NOTE]
> ダウンロード キューブ処理の状態を確認する URL では大文字と小文字が区別されます。 'health' と入力すると、URL は機能しません。 URL の末尾に「Health」と入力し、大文字の H を入力する必要があります。 
  
デバッグ モードが有効になっている場合、詳細なログ メッセージが表示されます。 デバッグ モードを有効にするには **、[%SYSTEMDRIVE%\Program Files\Skype For Business 2015 CQD\QoEDataService\web.config]** に移動し、次の行を更新して値を True に **設定します**。

```xml
<add key="QoEDataLib.DebugMode" value="True" /> 
```

メイン ポータル ページにアクセスするには  `http://<machinename>/CQD` 、 を使用します。 
## <a name="managing-user-access-for-the-portal"></a>ポータルのユーザー アクセスの管理

ポータルへのユーザー承認を管理するには、IIS 7.0 で導入された URL 承認を使用することをお勧めします。 IIS セキュリティの詳細については [、「IIS 7.0 URL の承認について」を参照してください](https://www.iis.net/learn/manage/configuring-security/understanding-iis-url-authorization)。
  
すべての Web サイトまたは Web アプリケーションは、IIS 全体に対して構成されている既定の URL 承認を継承します。通常は "すべてのユーザーを許可する" です。 ポータルへのアクセスを制限する必要がある場合、管理者は"承認ルール" を編集して、特定のユーザー グループにのみアクセス権を付与できます。
  
![通話品質の展開 - IIS の承認ルール](../../media/0da80c28-58fe-4aca-94b4-db684389468c.png)
  
> [!NOTE]
> [承認ルール] アイコンは、[認証ルール] セクションの [".NET 承認" と混同 ASP.NET、これは別の承認メカニズムです。 
  
管理者はまず、継承された "すべてのユーザーを許可する" ルールを削除する必要があります。 これにより、承認されていないユーザーがポータルにアクセスできません。
  
![CQD の展開](../../media/fa17ad19-d303-40f8-8324-d13fd67936ab.png)
  
次に、管理者は新しい [ルールの許可] を追加し、特定のユーザーにポータルへのアクセス許可を与える必要があります。 ユーザーを管理するために、"CQDPortalUsers" というローカル グループを作成する必要があります。
  
![通話品質ダッシュボードの展開](../../media/8cfdc141-ec89-4552-921b-53196f497cbf.png)
  
構成の詳細は、ポータルのweb.configにあるディレクトリに格納されます。
  
```xml
<?xml version="1.0" encoding="UTF-8"?> <configuration> <system.webServer> <security> <authorization> <remove users="*" roles="" verbs="" /> <add accessType="Allow" roles="CQDPortalUsers" /> </authorization> </security> </system.webServer> </configuration> 
```

次の手順では、CQD のダッシュボードを構成します。 IIS によってユーザーが認証されると、Web ポータル コンテンツにアクセスするには、CQD ディレクトリに対するファイルアクセス許可が必要になります。 CQD ディレクトリ プロパティの [セキュリティ] タブを使用して ACL を変更して、個々のユーザーまたはグループを追加できます。ただし、推奨される方法は、ファイルのアクセス許可をそのままにすることです。 代わりに、IIS ワーカー プロセスを使用して CQD ディレクトリにアクセスするために IIS 設定を変更します。認証されたユーザーに関係なく。 
  
> [!IMPORTANT]
> CQD アプリケーションのこの設定のみを変更し、QoEDataService と QoERepositoryService の 2 つの API アプリケーションでは変更することが重要です。 
  
## <a name="configuring-file-access-for-the-cqd-dashboard"></a>CQD のファイル アクセスの構成 (ダッシュボード)

1. CQD の構成エディターを開きます。
    
     ![通話品質ダッシュボードの展開](../../media/544056eb-3090-434e-bae6-321c984029fa.png)
  
2. [セクション] で **、[system.webServer/serverRuntime] を選択します**。
    
     ![通話品質ダッシュボードの展開](../../media/b0af0e56-21b0-45dd-b610-5381b39319d3.png)
  
3. authenticatedUserOverride を **UseWorkerProcessUser に変更します**。
    
     ![通話品質ダッシュボードの展開 - 構成エディター](../../media/a7c127f5-9a90-4710-afba-1d1e588efb37.png)
  
4. ページ **の右側** にある [適用] をクリックします。
    
## <a name="known-issues"></a>既知の問題

### <a name="the-cqd-shows-no-data-after-deployment"></a>CQD は、展開後にデータを表示します

次のエラーが表示される場合があります。

*キューブでクエリを実行している間、クエリを実行できなかった。クエリ エディターを使用してクエリを変更し、問題を修正します。また、キューブにアクセス可能な場所も確認してください。*

つまり、キューブは CQD で使用する前に、SQL Server Analysis Services で処理する必要があります。 これを解決するには、次の手順を実行します。

1. [分析SQL Management Studioを開き **、[Analysis Services] を選択します**。

2. **QoECube オブジェクトを展開** し **、[QoE メトリック**] を選択し、右クリックして、[参照] を **選択します**。 

    これが空のブラウザーを返す場合、キューブはまだ続行されていません。

3. **[QoE** Metric angain] を右クリックし、[プロセス] を **選択します**。

4. 処理が完了したら、もう一度オブジェクトを右クリックし、[参照] を選択して、ブラウザー ページにデータが表示されるのを確認します。 


### <a name="users-have-trouble-logging-in-because-installer-fails-to-create-the-correct-settings-in-iis"></a>インストーラーが IIS で正しい設定を作成できないため、ユーザーのログインに問題が発生する

まれに、インストーラーは IIS で正しい設定を作成できません。 ユーザーが CQD にログインするには、手動で変更する必要があります。 ユーザーがログインに問題がある場合は、次の手順に従ってください。
  
1. IIS マネージャーを開き、[既定の Web サイト] に移動します。
    
     ![通話品質ダッシュボードの展開](../../media/dc6007aa-870b-4d70-867d-32ffd937063b.png)
  
2. [認証] をクリックします。 "匿名認証"、"ASP.NET 偽装"、"フォーム認証"、および "Windows 認証" が以下に示す設定と一致しない場合は、以下の設定に合わせて手動で変更します。 その他のすべての認証メカニズムを無効にする必要があります。
    
     ![通話品質ダッシュボードの展開](../../media/5d9e38fb-8a50-41a2-a423-3ce983a83d0c.png)
  
3. [Windows 認証] の場合は、右側の [詳細設定] をクリックします。
    
     ![通話品質ダッシュボードの展開](../../media/cad29486-df40-4cc9-82f3-bbdaca52d9ca.png)
  
4. [拡張保護] を [承諾] に設定し、[カーネル モード認証を有効にする] ボックスをオンにします。
    
     ![通話品質ダッシュボードの展開](../../media/0ab2dda1-0001-4747-8cfc-072e9368b6cb.png)
  
5. "既定の Web サイト" の下の "CQD"、"QoEDataService"、および "QoERepositoryService" エントリごとに上記の手順を繰り返します。
    
HTTP および HTTPS ポート バインドの場合、インストーラーは既定のポート番号 (HTTP のポート 80、HTTPS のポート 443) にポート バインドを作成します。 これらのバインドを使用する別の Web サイトがコンピューター上にある場合、競合が発生し、IIS の動作を予測できません。 この問題を回避する最善の方法は、CQD をインストールする前に、他の Web サイトがポート 80 および 443 にマップしないようにします。 
  
IIS で SSL/TLS を有効にし、HTTP ではなくセキュリティで保護された HTTPS 経由でユーザーに強制的に接続するには、次の方法を実行します。
  
1. IIS Secure Sockets Layer構成する場合は、「IIS [7 でSecure Sockets Layer構成する」を参照してください](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc771438(v=ws.10))。 完了したら、 に置き  `http` 換える `https` 。
    
2. SQL Server 接続で TLS を有効にする方法については、「Microsoft 管理コンソールを使用して、SQL Serverインスタンスの SSL 暗号化を有効にする方法」を [参照してください](https://support.microsoft.com/kb/316898/)。
    
## <a name="cube-sync-fails"></a>キューブの同期が失敗する

QoEMetrics には、エンド ユーザー のクロックに基づいて無効なレコードが含まれている場合があります。 時間スキューが 60 yrs を超える場合、キューブのインポートは失敗します。
  
 以下の選択を使用して、Min および Max StartTime/EndTime を確認します。 遠い過去と非常に遠い将来のレコードを探して削除すると、無視され、同期プロセスが壊れる可能性があります。
  
- CqdPartitionedStreamView から MIN(StartTime) を選択する
    
- CqdPartitionedStreamView から MAX(StartTime) を選択する
    
- CqdPartitionedStreamView から MIN(EndTime) を選択する
    
- CqdPartitionedStreamView から MAX(EndTime) を選択する
    
## <a name="post-install-tasks"></a>インストール後のタスク

### <a name="importing-buildings-and-networks"></a>建物とネットワークのインポート

CQD のインストール後、次の構成タスクを実行します。
  
1. 建物の種類の定義 (推奨)
    
2. 建物の所有権の種類を定義する (推奨)
    
3. ネットワークの種類の定義 (強くお勧めします)
    
4. 建物のインポート (推奨)
    
5. サブネットのインポート (推奨)
    
### <a name="define-building-types"></a>[建物の種類の定義]

建物の種類は、組織内の異なる建物の定義または種類を記述するために使用されます。 
  
> [!NOTE]
> この手順は省略可能ですが、お勧めします。 
  
例
  
- Headquarters
    
- リモート Office
    
- 合弁の場所
    
  **サンプル SQL構文**
  
```SQL
INSERT INTO
[dbo].[CqdBuildingType]
([BuildingTypeId],
[BuildingTypeDesc])
VALUES
(1, 
'Headquarters')   
```

BuildingTypeId パラメーターと BuildingTypeDesc パラメーターが必要です。
  
### <a name="define-building-ownership-types"></a>建物の所有権の種類を定義する

所有権の種類は、所有資産とリース資産の区別に使用されます。
  
> [!NOTE]
> この手順は省略可能ですが、お勧めします。 
  
例
  
- Contoso リース非 RE &amp; F
    
- Contoso リース RE &amp; F
    
- Contoso 所有
    
- 子会社リース
    
  **サンプル SQL構文**
  
```SQL
INSERT INTO
[dbo].[CqdBuildingOwnershipType]
([OwnershipTypeId],
[OwnershipTypeDesc]
)

VALUES
(1,
'Contoso Owned'
)
```

OwnershipTypeId パラメーターと OwnershipTypeDesc パラメーターが必要です。 
  
### <a name="define-network-names"></a>ネットワーク名の定義

ネットワークの種類は、組織内の異なる種類のネットワークを記述するために使用されます。 これにより、特定のネットワークの種類をフィルター処理 (またはフィルター処理) できます。
  
> [!NOTE]
> ネットワーク名を定義することを強くお勧めしますが、オプションです。 ネットワーク名を定義しない場合は、各 CqdNetwork エントリの BuildingId が 0 である必要があります。 
  
例
  
- VPN
    
- LAB
    
  **サンプル SQL構文**
  
```SQL
INSERT INTO [dbo].[CqdNetworkName] 
( [NetworkName]
,[NetworkType]
 ) 
VALUES
('VPN','VPN') 
```

NetworkNameID パラメーターと NetworkName パラメーターが必要です。NetworkType パラメーターはオプションですが、推奨されます。
  
### <a name="import-buildings"></a>建物のインポート

建物をインポートすると、特定の分析情報 (WiFi/ワイヤードなどの建物ごとの低い呼び出し) を取得できます。 
  
> [!NOTE]
> この手順は省略可能ですが、お勧めします。 
  
新しい建物をインポートする前に、定義済みの BuildingKey が既に識別されている必要があります。 これを行うには、"SELECT MAX(BuildingKey) FROM CqdBuilding" SQL コマンドを発行して、現在の値を特定し、結果に 1 を追加します。
  
 **サンプル SQL構文**
  
```SQL
INSERT INTO [dbo].[CqdBuilding] 
( [BuildingKey]
,[BuildingName]
,[BuildingShortName]
,[OwnershipTypeId],
[BuildingTypeId]
)
VALUES
(2, 'Ann Arbor', 'AA', 0, 0)
```

BuildingKey、BuildingName、BuildingShortName、OwnershipTypeId、BuildingTypeId パラメーターが必要です。他のパラメーターはオプションです。
  
### <a name="import-subnets"></a>サブネットのインポート

建物をインポートすると、特定の分析情報 (WiFi/ワイヤードなどの建物ごとの低い呼び出し) を取得できます。 
  
> [!NOTE]
> この手順は省略可能ですが、お勧めします。
  
サブネットをインポートし、最後の手順でインポートした Buildings にマップします。 NetworkName を設定しない場合は、この表の各エントリで NetworkNameID が 0 を使用することを確認します。 通話品質ダッシュボードのSQLおよびパラメーターの詳細については、「Use Call [Quality Dashboard for Skype for Business Server」を参照してください](./use.md)。
  
 **サンプル SQL構文**
  
```SQL
INSERT INTO [dbo].[CqdNetwork] 
([Network]
,[NetworkRange]
,[NetworkNameID]
,[BuildingKey]
,[UpdatedDate]
)

VALUES
 ('172.16.254.0',32,0,1,'2015-11-11')
```

ネットワーク パラメーターと UpdatedDate パラメーターは必須ですが、他のパラメーターは省略可能です。
  
### <a name="optional-bssid"></a>オプション: BSSID

BSSID 情報を設定すると、コントローラーまたは無線による追加の WiFi ストリームの相関関係が得されます。 これは、構築またはサブネットによるフィルター処理に加えてです。 
  
 **サンプル SQL構文**
  
```SQL
INSERT INTO [dbo].[CqdBssid]
([Ap],
[Bss],
[Building],
[ess],
[phy]
)
VALUES
('AP1','00-00-00-00-00-00','Aruba AP 1','Controller1','bgn')
```

**CqdBssidTable の詳細**

|**CQD に示すように**|**CQDBssid テーブル**|**入力例**|
|:-----|:-----|:-----|
|Ap NName  <br/> |AP  <br/> |AP1  <br/> |
|BBssid  <br/> |BSS  <br/> |00-00-00-00-00-00 (区切られた fformat を使用する必要があります)  <br/> |
|Controller  <br/> |建物  <br/> |アルバ AP 7  <br/> |
|Device  <br/> |ess  <br/> |Controller1  <br/> |
|Radio  <br/> |phy  <br/> |bgn  <br/> |
   
### <a name="processing-the-imported-data"></a>インポートされたデータの処理

既定では、建物/ネットワーク データをインポートした後、その時点以降に生成されたレコードにのみ適用されます。 
  
前のすべてのレコードにこの新しいデータをタグ付けするには、以下に示すように、CqdUpdateBuilding ストアド プロシージャを実行する必要があります。 
  
最初のレコードの日付 (CqdPartitionedStreamView SQL コマンドから MIN(StartTime) を選択する) 、明日の EndDate、最後の 2 つの値の NULL を指定します。
  
データがストリーム データに関連付けられたら、SSIS キューブですべてのレコードを再処理する必要があります。 これは、BSSID/ISP データを一括追加する場合にも適用されます。 [プロセス全体] が選択されている必要があります。
