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
ms.openlocfilehash: 797288428530a055987d8b0a8e1ebf6a9e8b9dcd
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832717"
---
# <a name="deploy-call-quality-dashboard-for-skype-for-business-server"></a>Skype for Business Server の通話品質ダッシュボードの展開
 
**概要:** 通話品質ダッシュボードの展開プロセスについて説明します。 通話品質ダッシュボードは、Skype for Business Server 用のツールです。
  
## <a name="deployment-overview"></a>展開の概要

通話品質ダッシュボード (CQD) は、次の 3 つの主要なコンポーネントで構成されています。
  
- **アーカイブ データベース**。QoE (Quality of Experience) データがレプリケートおよび格納されます。
    
- **キューブ**。QoE アーカイブ データベースからのデータを集約して、最適化された高速アクセスを行います。
    
- **ユーザー** が QoE データのクエリと視覚化を簡単に行えるポータル。
    
![CQD コンポーネント](../../media/ef3359b1-c98b-4cc5-a549-c84c6e03c011.png)
  
QoE アーカイブのセットアップ プロセスでは、QoE アーカイブ データベースを作成し、ソース QoE 指標データベースから QoE アーカイブ データベースにデータを移動する SQL Server ストアド プロシージャを展開し、ストアド プロシージャを一定の間隔で実行する SQL Server エージェント ジョブを設定します。 
  
キューブ展開は、QoE アーカイブが存在する場所に関する情報をユーザーから取得し、キューブを展開し、一定の間隔でキューブを更新する通常の SQL Server エージェント ジョブを設定します。
  
ポータル インストールは、CQD ユーザーと各ユーザーのレポート/クエリのマッピングを格納するリポジトリ データベースを作成します。 次に、ユーザーが事前に定義されたレポートのセットを表示できるダッシュボードである IIS Web アプリケーションをセットアップし、キューブからのデータを視覚化するための独自のクエリをカスタマイズおよび作成します。 ポータル インストールでは、ユーザーがプログラムでリポジトリとキューブにアクセスできる API を公開する 2 つの追加の Web アプリケーションが作成されます。 (これらの API は、ダッシュボードでも内部的に使用されます)。
  

|**フェーズ**|**手順**|**ロールとグループ メンバーシップ**|**ドキュメント**|
|:-----|:-----|:-----|:-----|
|必要なハードウェアとソフトウェアをインストールします。  <br/> |CQD 構成を決定し、インストールSQL Serverを選択します。  <br/> |ローカルの Administrators グループのメンバーであるドメイン ユーザー。  <br/> |展開のドキュメントの「インストール前の要件」セクション。  <br/> |
|CQD をインストールします。  <br/> |展開ドキュメントに従って MSI を実行します。  <br/> |セットアップを実行するには、インストール アカウントが、ローカル管理者グループのメンバーであり、監視サーバー上の QoE 指標データベースへの読み取りアクセス権を持つドメイン ユーザーである必要があります。  <br/> |展開のドキュメントの「アカウントと展開手順」セクション。  <br/> |
|ユーザー にアクセス権を付与します。  <br/> |ポータルへのユーザー承認を管理するには、IIS 7.0 で導入された URL 承認を使用することをお勧めします。 詳細については [、「IIS 7.0 URL](https://www.iis.net/learn/manage/configuring-security/understanding-iis-url-authorization)承認について」を参照してください。  <br/> |ローカルの Administrators グループのメンバーであるドメイン ユーザー。  <br/> |展開ドキュメントのポータル セクションのユーザー アクセスの管理。  <br/> |
|オプション: サブネット マッピング情報を提供します。  <br/> |QoE アーカイブ データベースにネットワークおよび構築マッピング テーブルを設定します。  <br/> |QoE アーカイブ データベースへの書き込みアクセス権を持つアカウント。  <br/> |ユーザー ドキュメントの「サブネット情報の提供」セクション。  <br/> |
   


通話品質ダッシュボードの展開には、インフラストラクチャのセットアップとソフトウェアのインストールが含まれる。 次の手順では、プロセスの概要を示します。
  
## <a name="deployment-steps"></a>展開手順

1. CQD CallQualityDashboard.msi データベース コンポーネントをインストールするコンピューターにコピーします (このコンピューターにインストールされているSQL Serverします。 
    
2. MSI を実行します (管理者特権で実行するように求めるメッセージが Windows によって表示されます)。 
    
3. EULA に同意します。
    
4. 通話品質ダッシュボード コンポーネントに関連するファイルが格納される宛先フォルダーを選択するか、既定の場所を受け入れる。
    
5. すべての機能を選択します。
    
6. [QoE アーカイブ構成] ページで、次の情報を入力します。
    
   - **QoE 指標SQL Server:** SQL Serverデータベースが含まれる場所のインスタンス名を指定します (これはデータ ソースになります)。
    
   - **QoE アーカイブ SQL Server名:** これは読み取り専用フィールドであり、ローカル コンピューターの完全修飾ドメイン名に固定されています。 アーカイブ DB は、ローカル コンピューターにのみインストールできます。
    
   - **QoE アーカイブ SQL Server インスタンス:** アーカイブ DB SQL Serverするローカル のインスタンス名。 既定のインスタンスを使用SQL Server、このフィールドは空白のままにします。 名前付きインスタンスをSQL Serverするには、インスタンス名 ("" の後の名前など) を指定します \" 。
    
   - **QoE アーカイブ データベース:** 既定では、このオプションは [新しいデータベースの作成] に設定されています。 アーカイブ DB アップグレードはサポートされていないので、[既存のデータベースを使用する] オプションを使用できるのは、既存のアーカイブ データベースがインストールするビルドと同じスキーマを持つ場合のみです。
    
   - **データベース ファイル ディレクトリ:** アーカイブ DB のデータベース ファイル (.mdf および .ldf) を配置する場所へのパス。 これは、OS とは別のドライブ (推奨ハードウェア構成では HDD2) 上にある必要があります。 ファイル名はインストールで修正され、競合の可能性を回避するために、ファイルを含む空のディレクトリを使用しないようにお勧めします。
    
   - **複数のパーティションを使用する:** 既定値は "複数パーティション" に設定されています。この場合、ビジネス インテリジェンス エディションまたは Enterprise エディションの SQL Server。 Standard Edition の場合は、[単一パーティション] オプションを選択します。 Single Partition を使用すると、キューブ処理のパフォーマンスに影響を与える可能性があります。
    
     > [!NOTE]
     > [複数のパーティションを使用する] オプションは、セットアップが完了すると変更できません。 キューブ機能を変更するには、まずアンインストールしてから、コントロール パネルの [変更] オプションを使用して再インストールする必要があります。 
  
   - **パーティション ファイル ディレクトリ:** QoE アーカイブ データベースのパーティションを配置する場所へのパス。 これは、OS ドライブとデータベース ログ ファイル ドライブとは別のドライブ (推奨ハードウェア構成では HDD3) SQLする必要があります。 ファイル名はインストールで修正され、競合の可能性を回避するために、ファイルを含む空のディレクトリを使用しないようにお勧めします。
    
   - **SQL エージェント ジョブ ユーザー - ユーザー名 &amp; パスワード:** SQL Server エージェント ジョブの "QoE アーカイブ データ" ステップの実行に使用されるドメイン サービス アカウント名とパスワード (マスクされています)。これは、ストアド プロシージャを実行して QoE Metrics DB からアーカイブ DB にデータをフェッチします。そのため、このアカウントは、[アカウント] セクションで示されている QoE Metrics DB への読み取りアクセス権を持っている必要があります。 このアカウントには、QoE アーカイブ サーバー インスタンスにログインSQL Serverがあります。
    
     > [!NOTE]
     > インストールを正常にSQL Server、NT SERVICE\MSSQLSERVER など、SQL Server インスタンスが実行されているアカウントには、上記のディレクトリへのアクセス/アクセス許可が必要です。 詳細については、「データベース エンジン [アクセスのファイル システム権限を構成する」を参照してください。](https://msdn.microsoft.com/library/jj219062%28v=sql.110%29.aspx)
  
7. 次にクリックすると、インストーラーは前提条件の確認を実行し、問題が発生した場合に報告します。 すべての前提条件の確認に合格すると、インストーラーは [キューブの構成] ページに移動します。 
    
    > [!NOTE]
    > QoE アーカイブ SQL Server インスタンスの SQL Server エージェント サービスが現在実行されていないという警告メッセージがインストーラーに表示された場合は、インストールを続行できますが、インストール後に SQL エージェント サービスが実行されている必要があります。スケジュールされたジョブが実行されるのに合わせ、スタートアップの種類を自動に設定してください。 
  
8. [キューブの構成] ページで、次の情報を入力します。
    
   - **QoE アーカイブ SQL Server名:** これは読み取り専用フィールドであり、ローカル コンピューターの完全修飾ドメイン名に固定されています。 キューブは、QoE アーカイブ データベースを持つコンピューターからのみインストールできます (注: キューブ自体は、リモート コンピューターにインストールできます。 下記を参照)
    
   - **QoE アーカイブ SQL Server インスタンス:** SQL Serverアーカイブ DB が保存されている場所のインスタンス名を指定します。 既定のインスタンスを指定SQL Server、このフィールドは空白のままにします。 名前付きインスタンスをSQL Serverするには、インスタンス名 ("" の後の名前など) を入力します \" 。 QoE アーカイブ コンポーネントがインストール用に選択されている場合、このフィールドには QoE アーカイブ構成ページで提供される値が事前に入力されます。
    
   - **キューブ分析サーバー:** SQL Server作成する場所の Analysis Service インスタンス名を指定します。 これは別のコンピューターの場合がありますが、インストールするユーザーは Analysis Service インスタンスのターゲット サーバー管理者のSQL Server必要があります。
    
     > [!NOTE]
     >  Analysis Services サーバーの管理者権限の構成の詳細については [、「Grant Server Administrator Permissions (Analysis Services)」を参照してください。](https://msdn.microsoft.com/library/ms174561.aspx)
  
   - **複数のパーティションを使用する:** 既定値は "複数パーティション" に設定されています。この場合、ビジネス インテリジェンス エディションまたは Enterprise エディションの SQL Server。 Standard Edition の場合は、[単一パーティション] オプションを選択します。 Single Partition を使用すると、キューブ処理のパフォーマンスに影響を与える可能性があります。
    
     > [!NOTE]
     >  [複数のパーティションを使用する] オプションは、セットアップが完了すると変更できません。 キューブ機能を変更するには、まずアンインストールしてから、コントロール パネルの [変更] オプションを使用して再インストールする必要があります。
  
   - **キューブ ユーザー - ユーザー名 &amp; パスワード:** キューブ処理をトリガーするドメイン サービス アカウント名とパスワード (マスク)。 QoE アーカイブ コンポーネントがインストール用に選択されている場合、このフィールドには SQL エージェント ジョブ ユーザーの [アーカイブの構成] ページに表示される値が事前に入力されますが、セットアップが最小の特権を付与できるよう、別のドメイン サービス アカウントを指定することをお勧めします。
    
9. 次にクリックすると、別の検証ラウンドが実行され、問題が報告されます。 検証が正常に完了すると、インストーラーは [ポータルの構成] ページに移動します。 
    
10. [ポータルの構成] ページで、次の情報を入力します。
    
    - **QoE アーカイブ SQL Server:** SQL Serverデータベースが保存されている場所のインスタンス名を指定します。 QoE アーカイブ構成ページや [キューブの構成] ページとは異なり、コンピューター名は固定ではなく、指定する必要があります。 QoE アーカイブ コンポーネントがインストール用に選択されている場合、このフィールドには QoE アーカイブ構成ページで提供される値が事前に入力されます。
    
    - **キューブ分析サーバー:** SQL Serverがある場所の Analysis Service インスタンス名を指定します。 インストール用にキューブ コンポーネントが選択されている場合、このフィールドには [キューブの構成] ページで指定された値が事前に入力されます。
    
    - **リポジトリ SQL Server:** SQL Server作成するインスタンス名を指定します。 QoE アーカイブ データベースが含まれる場所の SQL Server インスタンス名がセットアップの以前のバージョン (他のコンポーネント) で指定されている場合、このフィールドには QoE アーカイブ DB SQL Server インスタンス名が事前に入力されます。 これは、任意のインスタンスSQL Serverできます。
    
    - **リポジトリ データベース:** 既定では、このオプションは [新しいデータベースの作成] に設定されています。 リポジトリ DB のアップグレードはサポートされていないので、[既存のデータベースを使用する] オプションを使用できる唯一の状況は、既存のリポジトリ DB がインストールするビルドと同じスキーマを持つ場合です。
    
    - **IIS アプリ プール ユーザー - ユーザー名 &amp; パスワード:** IIS アプリケーション プールを実行するアカウント。 組み込みのシステム アカウントが選択されている場合、[ユーザー名] フィールドと [パスワード] フィールドは灰色表示されます。 これらのフィールドは、ユーザーがドメイン サービス アカウント情報を入力できるよう、ドロップダウン ボックスから [その他] が選択されている場合にのみ有効になります。
    
11. 次にクリックすると、入力規則の最終ラウンドが実行され、指定された資格情報を使用して SQL Server インスタンスにアクセス可能であり、IIS がコンピューターで使用可能なことを確認します。 検証が正常に完了すると、インストーラーはセットアップを続行します。 
    
インストーラーが完了すると、通常、SQL Server エージェント ジョブが進行中で、QoE データの初期負荷とキューブ処理が行われます。 QoE のデータ量によっては、ポータルで表示できるデータがまだありません。 データの読み込みとキューブ処理の状態を確認するには、次のページに移動します  `http://<machinename>/CQD/#/Health` 。 
> [!NOTE]
> ダウンロード キューブ処理の状態を確認する URL では、大文字と小文字が区別されます。 「health」と入力すると、URL は機能しません。 URL の末尾に「Health」と入力し、大文字の H を入力する必要があります。 
  
デバッグ モードが有効になっている場合、詳細なログ メッセージが表示されます。 デバッグ モードを有効にするには **、%SYSTEMDRIVE%\Program Files\Skype For Business 2015 CQD\QoEDataService\web.config** に移動し、次の行を更新して値を True に設定 **します**。

```xml
<add key="QoEDataLib.DebugMode" value="True" /> 
```

メイン ポータル ページには、次の方法でアクセスできます  `http://<machinename>/CQD` 。 
## <a name="managing-user-access-for-the-portal"></a>ポータルのユーザー アクセスを管理する

ポータルへのユーザー承認を管理するには、IIS 7.0 で導入された URL 承認を使用することをお勧めします。 IIS セキュリティの詳細については [、「IIS 7.0 URL 承認について」を参照してください](https://www.iis.net/learn/manage/configuring-security/understanding-iis-url-authorization)。
  
すべての Web サイトまたは Web アプリケーションは、IIS 全体に対して構成された既定の URL 承認を継承します。通常は、"すべてのユーザーを許可する" です。 ポータルへのアクセスの制限を厳しくする必要がある場合、管理者は"承認ルール" を編集することで、特定のユーザー グループにのみアクセス権を付与できます。
  
![通話品質の展開 - IIS での承認ルール](../../media/0da80c28-58fe-4aca-94b4-db684389468c.png)
  
> [!NOTE]
> [認証規則] アイコンは、異なる承認メカニズムである ASP.NET セクションの ".NET Authorization" と混同しないでください。 
  
管理者はまず、継承された "すべてのユーザーを許可する" ルールを削除する必要があります。 これにより、承認されていないユーザーはポータルにアクセスできません。
  
![CQD の展開](../../media/fa17ad19-d303-40f8-8324-d13fd67936ab.png)
  
次に、管理者は新しい許可ルールを追加し、特定のユーザーにポータルへのアクセス許可を付与する必要があります。 ユーザーを管理するには、"CQDPortalUsers" というローカル グループを作成する必要があります。
  
![通話品質ダッシュボードの展開](../../media/8cfdc141-ec89-4552-921b-53196f497cbf.png)
  
構成の詳細は、ポータルのweb.configにあるディレクトリに格納されます。
  
```xml
<?xml version="1.0" encoding="UTF-8"?> <configuration> <system.webServer> <security> <authorization> <remove users="*" roles="" verbs="" /> <add accessType="Allow" roles="CQDPortalUsers" /> </authorization> </security> </system.webServer> </configuration> 
```

次の手順では、CQD のダッシュボードを構成します。 IIS によって認証されたユーザーは、Web ポータルのコンテンツにアクセスするために CQD ディレクトリに対するファイルアクセス許可を持っている必要があります。 個々のユーザーまたはグループを追加するには、CQD ディレクトリ プロパティの [セキュリティ] タブを使用して ACL を変更できます。ただし、推奨される方法は、ファイルのアクセス許可を変更しない方法です。 代わりに、IIS ワーカー プロセスを使用して、認証されているユーザーに関係なく CQD ディレクトリにアクセスする IIS 設定を変更します。 
  
> [!IMPORTANT]
> この設定は CQD アプリケーションでのみ変更し、QoEDataService と QoERepositoryService の 2 つの API アプリケーションでは変更しないのが重要です。 
  
## <a name="configuring-file-access-for-the-cqd-dashboard"></a>CQD のファイル アクセスを構成する (ダッシュボード)

1. CQD の構成エディターを開きます。
    
     ![通話品質ダッシュボードの展開](../../media/544056eb-3090-434e-bae6-321c984029fa.png)
  
2. [セクション] で **、system.webServer/serverRuntime を選択します**。
    
     ![通話品質ダッシュボードの展開](../../media/b0af0e56-21b0-45dd-b610-5381b39319d3.png)
  
3. authenticatedUserOverride を **UseWorkerProcessUser に変更します**。
    
     ![通話品質ダッシュボードの展開 - 構成エディター](../../media/a7c127f5-9a90-4710-afba-1d1e588efb37.png)
  
4. ページ **の右側** にある [適用] をクリックします。
    
## <a name="known-issues"></a>既知の問題

### <a name="the-cqd-shows-no-data-after-deployment"></a>CQD は展開後にデータを表示しな

次のエラーが表示される場合があります。

*キューブで実行している間、クエリを実行する必要があります。クエリ エディターを使用してクエリを変更し、問題を修正します。また、キューブにアクセス可能な方法も確認してください。*

つまり、キューブを CQD で使用する前にSQL Server Analysis Services で処理する必要があります。 これを解決するには、次の手順を実行します。

1. ファイルをSQL Management Studioし **、[Analysis Services] を選択します**。

2. **QoECube オブジェクトを展開** し **、[QoE メトリック] を** 選択し、右クリックして、[参照] を **選択します**。 

    空のブラウザーが返された場合、キューブはまだ続行されていません。

3. QoE 指標を **右クリックし** 、[プロセス] を **選択します**。

4. 処理が完了したら、もう一度オブジェクトを右クリックし、[参照] を選択してブラウザー ページにデータが表示されるのを確認します。 


### <a name="users-have-trouble-logging-in-because-installer-fails-to-create-the-correct-settings-in-iis"></a>インストーラーが IIS で正しい設定を作成できないので、ユーザーのログインで問題が発生する

まれに、インストーラーが IIS で正しい設定を作成できない場合があります。 ユーザーが CQD にログインするには、手動で変更する必要があります。 ユーザーのログインで問題が発生する場合は、次の手順に従ってください。
  
1. IIS マネージャーを開き、[既定の Web サイト] に移動します。
    
     ![通話品質ダッシュボードの展開](../../media/dc6007aa-870b-4d70-867d-32ffd937063b.png)
  
2. [認証] をクリックします。 "匿名認証"、"ASP.NET 偽装"、"フォーム認証"、および "Windows 認証" が以下の設定と一致しない場合は、以下の設定に合わせて手動で変更します。 その他すべての認証メカニズムを無効にする必要があります。
    
     ![通話品質ダッシュボードの展開](../../media/5d9e38fb-8a50-41a2-a423-3ce983a83d0c.png)
  
3. [Windows 認証] の場合は、右側の [詳細設定] をクリックします。
    
     ![通話品質ダッシュボードの展開](../../media/cad29486-df40-4cc9-82f3-bbdaca52d9ca.png)
  
4. [拡張保護] を [承諾] に設定し、[カーネル モード認証を有効にする] チェック ボックスをオンにします。
    
     ![通話品質ダッシュボードの展開](../../media/0ab2dda1-0001-4747-8cfc-072e9368b6cb.png)
  
5. "既定の Web サイト" の下にある "CQD"、"QoEDataService"、および "QoERepositoryService" エントリごとに上記の手順を繰り返します。
    
HTTP および HTTPS ポート バインドの場合、インストーラーは既定のポート番号 (HTTP の場合はポート 80、HTTPS の場合はポート 443) にポート バインドを作成します。 コンピューター上にこれらのバインドを使用する別の Web サイトがある場合、競合が発生し、IIS の動作を予測できません。 この問題を回避する最善の方法は、CQD をインストールする前に、他の Web サイトがポート 80 とポート 443 にマップされなにかかからなを確認する方法です。 
  
IIS で SSL/TLS を有効にし、ユーザーが HTTP ではなくセキュリティで保護された HTTPS 経由で接続するように強制するには、次の方法を使用します。
  
1. IIS Secure Sockets Layer構成する方法については、「IIS 7 でのSecure Sockets Layer [構成」を参照してください](https://technet.microsoft.com/library/cc771438%28v=ws.10%29.aspx)。 完了したら、次のコードに  `http` 置き換える `https` 必要があります。
    
2. SQL Server 接続で TLS を有効にする手順については、Microsoft 管理コンソールを使用して SQL Server のインスタンスに対して SSL 暗号化を有効にする方法を [参照してください](https://support.microsoft.com/kb/316898/)。
    
## <a name="cube-sync-fails"></a>キューブの同期が失敗する

QoEMetrics には、エンド ユーザーのクロックに基づいて無効なレコードが含まれている場合があります。 時間のスキューが 60 yrs を超える場合、キューブのインポートは失敗します。
  
 次の選択を使用して、Min および Max StartTime/EndTime を確認します。 過去と非常に遠い将来のレコードを検索して削除すると、レコードは無視され、同期プロセスが壊れる可能性があります。
  
- Select MIN(StartTime) FROM CqdPartitionedStreamView
    
- Select MAX(StartTime) FROM CqdPartitionedStreamView
    
- Select MIN(EndTime) FROM CqdPartitionedStreamView
    
- Select MAX(EndTime) FROM CqdPartitionedStreamView
    
## <a name="post-install-tasks"></a>インストール後のタスク

### <a name="importing-buildings-and-networks"></a>建物とネットワークのインポート

CQD をインストールした後、次の構成タスクを実行します。
  
1. 建物の種類を定義する (推奨)
    
2. 建物の所有権の種類を定義する (推奨)
    
3. ネットワークの種類を定義する (強くお勧めします)
    
4. 建物のインポート (推奨)
    
5. サブネットのインポート (推奨)
    
### <a name="define-building-types"></a>建物の種類を定義する

建物の種類は、組織内の異なる建物の定義または種類を記述するために使用されます。 
  
> [!NOTE]
> この手順は省略できますが、お勧めします。 
  
例
  
- Headquarters
    
- リモート Office
    
- 共同で移動する場所
    
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

BuildingTypeId パラメーターと BuildingTypeDesc パラメーターは必須です。
  
### <a name="define-building-ownership-types"></a>建物の所有権の種類を定義する

所有権の種類は、所有資産とリース資産を区別するために使用されます。
  
> [!NOTE]
> この手順は省略できますが、お勧めします。 
  
例
  
- Contoso リース非 RE &amp; F
    
- Contoso Leased RE &amp; F
    
- Contoso Owned
    
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

OwnershipTypeId パラメーターと OwnershipTypeDesc パラメーターは必須です。 
  
### <a name="define-network-names"></a>ネットワーク名の定義

ネットワークの種類は、組織内の異なる種類のネットワークを記述するために使用されます。 これにより、特定のネットワークの種類をフィルター処理 (またはフィルター処理) できます。
  
> [!NOTE]
> ネットワーク名を定義することを強くお勧めしますが、オプションです。 ネットワーク名を定義しない場合は、各 CqdNetwork エントリの BuildingId が 0 に設定されている必要があります。 
  
例
  
- VPN
    
- ラボ
    
  **サンプル SQL構文**
  
```SQL
INSERT INTO [dbo].[CqdNetworkName] 
( [NetworkName]
,[NetworkType]
 ) 
VALUES
('VPN','VPN') 
```

NetworkNameID パラメーターと NetworkName パラメーターは必須ですが、NetworkType パラメーターは省略可能ですが、推奨されます。
  
### <a name="import-buildings"></a>建物のインポート

建物をインポートすると、特定の分析情報 (WiFi/有線の建物ごとの低品質な通話など) を得る機能が提供されます。 
  
> [!NOTE]
> この手順は省略できますが、お勧めします。 
  
新しい建物をインポートする前に、定義済みの BuildingKey が既に識別されている必要があります。 これを行うには、"SELECT MAX(BuildingKey) FROM CqdBuilding" SQL コマンドを発行して現在の値を識別し、結果に 1 を追加します。
  
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

BuildingKey、BuildingName、BuildingShortName、OwnershipTypeId、BuildingTypeId パラメーターは必須です。その他のパラメーターは省略可能です。
  
### <a name="import-subnets"></a>サブネットのインポート

建物をインポートすると、特定の分析情報 (WiFi/有線の建物ごとの低品質通話など) を得る機能が提供されます。 
  
> [!NOTE]
> この手順は省略できますが、お勧めします。
  
サブネットをインポートし、最後の手順でインポートした建物にマップします。 NetworkName を設定しない場合は、この表の各エントリで NetworkNameID が 0 を使用することを確認します。 通話品質ダッシュボードのSQLパラメーターの詳細については [、「Skype for Business Server](https://docs.microsoft.com/skypeforbusiness/management-tools/call-quality-dashboard/use)の通話品質ダッシュボードを使用する」を参照してください。
  
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

Network パラメーターと UpdatedDate パラメーターは必須ですが、他のパラメーターは省略可能です。
  
### <a name="optional-bssid"></a>オプション: BSSID

BSSID 情報を入力すると、コントローラーまたは無線による追加の WiFi ストリームの相関関係が得されます。 これは、構築またはサブネットによるフィルター処理に加えて行います。 
  
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

|**CQD に示すように**|**CQDBssid テーブル**|**入力の例**|
|:-----|:-----|:-----|
|Ap NName  <br/> |AP  <br/> |AP1  <br/> |
|BBssid  <br/> |BSS  <br/> |00-00-00-00-00-00 (区切られた書式を使用する必要があります)  <br/> |
|Controller  <br/> |Building  <br/> |アルバ AP 7  <br/> |
|Device  <br/> |ess  <br/> |Controller1  <br/> |
|Radio  <br/> |phy  <br/> |bgn  <br/> |
   
### <a name="processing-the-imported-data"></a>インポートされたデータの処理

既定では、建物やネットワークのデータをインポートした後は、その時点以降に生成されたレコードにのみ適用されます。 
  
以前のすべてのレコードにこの新しいデータをタグ付けするには、以下に示すように CqdUpdateBuilding ストアド プロシージャを実行する必要があります。 
  
最初のレコードの日付を指定し (Select MIN(StartTime) FROM CqdPartitionedStreamView SQL コマンドを使用して)、明日の EndDate を指定し、最後の 2 つの値に NULL を指定します。
  
データがストリーム データに関連付けられたら、SSIS キューブですべてのレコードを再処理する必要があります。 これは、BSSID/ISP データを一括で追加する場合にも適用されます。 [プロセス全体] が選択されている必要があります。
  

