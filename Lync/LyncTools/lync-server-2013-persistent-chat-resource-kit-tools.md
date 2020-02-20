---
title: Lync Server 2013 常設チャットリソースキットツール
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Lync Server 2013 Persistent Chat Resource Kit Tools
ms:assetid: 7a34d2ba-eb25-4e22-92d1-b9baf81b102c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945599(v=OCS.15)
ms:contentKeyID: 51541423
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 726e6bb537a16ece5c2955f005e91872f11f6a79
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42147730"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="lync-server-2013-persistent-chat-resource-kit-tools"></a>Lync Server 2013 常設チャットリソースキットツール

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-02-24_

Lync Server 2013 常設チャットリソースキットツールは、Lync Server 2013 常設チャットサーバーを展開して管理する IT 管理者にとって、日常的な作業を容易にするために役立ちます。 このトピックでは、インストール手順だけでなく、各ツールの目的と使用例についても説明します。

<div>

## <a name="installation-of-the-resource-kit-tools"></a>リソースキットツールのインストール

Lync Server 2013 のリソースキットツールをインストールするには、 **PersistentChatReskit**をダウンロードしてください。 **PersistentChatReskit**を実行して、単純なインストールを実行します。 .Msi は、次のパス\\にあるすべてのツールをインストールします。 **Program Files\\\\ Microsoft Lync server 2013 常設チャットサーバーリソースキット**。 このフォルダーには、自己完結型の実行可能ファイルであるツールがあります。 ファイルが含まれているツールも、それぞれ独自のサブフォルダーにあります。

<div>


> [!IMPORTANT]  
> Lync server 2013 のリソースキットツールをインストールした後、 <STRONG>PsExec</STRONG>をインストールし、 <STRONG>PsExec</STRONG>を次のパスにコピーする必要\\があります。 <STRONG>Program Files \ Microsoft Lync server 2013 \ 常設チャットサーバーリソース Kit\ChatStressTool</STRONG>。 <STRONG>PsExec</STRONG>をコピーしない場合、常設チャットストレスツールはエラー例外をスローし、正しく実行されません。 ツールを実行する前に、この前提条件を満たしていることを確認してください。 <STRONG>PsExec</STRONG>のインストールの詳細については<A href="https://go.microsoft.com/fwlink/p/?linkid=282246">https://go.microsoft.com/fwlink/p/?LinkId=282246</A>、「」を参照してください。



</div>

</div>

<div>

## <a name="supported-environments"></a>サポートされる環境

最適なパフォーマンスを得るために、lync server 2013、リソースキットツールは、Lync Server 2013 に必要なものと同じ環境にインストールする必要があります。

</div>

<div>

## <a name="resource-kit-tools-overview"></a>リソースキットツールの概要

Lync Server 2013 常設チャットリソースキットには、次のツールが用意されています。 次のセクションでは、要件や使用例など、各ツールの説明を示します。

  - 影響チェック

  - ChatMonitoringSummary

  - ChatStress ツール

  - ChatUpgradeVerifier

  - ChatUsageReport

  - ScheduleADSyncforPrincipal

</div>

<div>

## <a name="affcheck"></a>影響チェック

<div>

## <a name="description"></a>説明

このツールは、常設チャットのバックエンドデータベースユーザーとグループの所属レコードが Active Directory ドメインサービスのものと一致することを確認します。

</div>

<div>

## <a name="requirements"></a>Requirements

このツールは、PersistentChatResKit インストーラーを使用してドメインに参加しているコンピューターにインストールされます。

このツールを実行するユーザーアカウントには、常設チャットのバックエンドデータベースと Active Directory ドメインサービスへの読み取りアクセス権が必要です。

</div>

<div>

## <a name="usage"></a>使用方法

構成ファイルの手順に従って、影響チェック .exe ファイルを構成し、コマンドラインパラメーターを指定せずに、影響チェックツールを実行します。 既定の影響の内容は、次のとおりです。

**影響のある .config ファイル:**

```XML
    <?xml version="1.0" encoding="utf-8" ?>
    <configuration>
      <appSettings>
        <!--Domain Controller IP Address-->
        <add key="LDAP" value="LDAP://0.0.0.0/"/>
        
        <!-- Domain DN  This is case sensitive, it must match exactly-->
        <add key="DomainComponent" value ="DC=DOMAIN,DC=COM"/>
        
        <!--Domain Administrator Login and Password-->
        <add key="DomainLogin" value="DOMAIN\Administrator"/>
        <add key="DomainPassword" value ="password"/>
        
        <!-- Connection string to Group Chat Database-->
        <add key="ConnectionString" value="data source=SQL_SERVER\INSTANCE;initial catalog=DATABASE_NAME;integrated security=SSPI"/>
        
        <!--Check group affiliations-->
        <add key="CheckGroups" value="true"/>
        
        <!--Check user affilations-->
        <add key="CheckUsers" value="true"/>
        
        <!--List all affiliations if there is a mismatch between database and active directory-->
        <add key="ListAffiliations" value="true"/>
    
        <!--If you need to offset the results of the number of affilations in AD(can be negative to add to AD parent count)-->
        <add key="Offset" value ="0"/>
    
        <!--If you need to ignore certain parents, provide a semi colon delimitted list.-->
        <add key="Ignore" value ="DC=uatest,DC=test,DC=contoso,DC=com;DC=test,DC=contoso,DC=com"/>
      </appSettings>
    </configuration>
  ```
</div>

</div>

<div>

## <a name="chatmonitoringsummary"></a>ChatMonitoringSummary

<div>

## <a name="description"></a>説明

PersistentChatMonitoringSummary ツールは、永続的なチャットの監視情報を監視データベースから、指定された CSV ログファイルに移動します。

CSV ファイルには、セッション数の合計、成功したセッション、予期しないエラー、予期されたエラー、診断 ID、エラーの数、エラーの説明による予期しないエラーの内訳による、常設チャットセッションの内訳が含まれています。

</div>

<div>

## <a name="requirements"></a>Requirements

監視データベースにアクセスできるドメインに参加しているコンピューターに常設チャットリソースキットツールをインストールします。

ツールを実行するユーザーアカウントは、監視データベースに対する読み取りアクセス権を持っている必要があります。

PersistentChatMonitoringSummary ファイルには、監視データベースへの接続文字列を\<定義\>する connectionStrings セクションを含める必要があります。 また、監視データが収集される PersistentChatEndpointUri のキーと、生成される CSV ファイルの場所へのファイルパスも含める必要があります。 インストールされている構成ファイルで例を参照してください。 このファイルは、ツールと同じディレクトリに配置する必要があります。

</div>

<div>

## <a name="usage"></a>使用方法

```Batch
    PersistentChatMonitoringSummary [-StartDateTime <date>] [-EndDateTime <date>]
```

これらのパラメーターは、データの選択を定義します。

**StartDateTime:** オプションで、選択期間の開始日を指定します。 既定値: 1/1/1753 12:00:00 AM

**Enddatetime:** オプションで、選択期間の最後の日付を指定します。 既定値: Now

</div>

<div>

## <a name="example"></a>例

```Batch
    C:\Users\Administrator.VDOMAIN>Desktop\PersistentChatMonitoringSummary.exe
    Reading database connection information, Persistent Chat endpoint uri, and csv output path information from the application config file...
    Connecting to Monitoring database with connection string specified in the application config file...
    Gathering Persistent Chat Session Summary information between "1/1/1753 12:00:00 AM" and "11/19/2012 10:11:25 AM" for Persistent Chat Endpoint Uri "persistentChatEndpointUri@domain.com"...
    Press enter to continue or hit ctr-c if these settings are incorrect...
    
    The summary information about Persistent Chat sessions from the Monitoring database has been output to C:\PersistentChatMonitoring_dd4ace24-4c8a-4a3d-8fd4-591bdfacf47b.csv
    Press enter to exit...
```

</div>

</div>

<div>

## <a name="persistent-chat-stress-tool"></a>常設チャットストレスツール

<div>

## <a name="description"></a>説明

常設チャットストレスツールは、永続的なチャットの使用をシミュレートする簡単な方法を提供します。これにより、さまざまなユーザーモデルを含めて、予想される使用シナリオに合わせて、現実的なパフォーマンスをテストできます。

</div>

<div>

## <a name="requirements"></a>Requirements

常設チャットリソースキットツールを、常設チャットバックエンドデータベースにアクセスできるドメインに参加しているコンピューターにインストールします。

この*コントローラー*コンピューターに加えて、いくつかの*ローダー*マシンが必要になります。 ユーザーモデルの10,000 ユーザーごとに、少なくとも 4 GB の空き RAM がローダーコンピューターに必要になります。 たとえば、80K を使用して実行すると、すべてのローダーコンピューターにまたがる RAM の 32 GB について必要になります。 予想される負荷に関係なく、少なくとも3台のローダーコンピューターを用意することをお勧めします。

ローダーコンピューターには、.NET 4.5 Framework に加えて、Visual C++ 2012 再頒布可能パッケージがインストールされている必要があります。

</div>

<div>

## <a name="configuration"></a>構成

ChatStressTool ファイルをすべてのローダーコンピューターからアクセス可能な共有フォルダーにコピーします。

ストレス実行で使用するユーザーとチャネルを作成します。

  - ユーザーモデルからの呼び出しを行うユーザー数だけ作成し、Lync で有効にして、常設チャットポリシーを有効に設定します。

  - ストレスチャネルのカテゴリを作成し、そのカテゴリで必要なだけのルームを作成します。 カテゴリには、すべてのストレスユーザーが**許可され**たリストに含まれている必要があります (OU を追加することによって)。また、ストレスルームには、プライバシー設定を**開く**必要があります。

  - 特別なストレスルームを作成することをお勧めします。 5万ルームは、次の Windows PowerShell コマンドラインインターフェイスコマンドを使用して作成できます。
    ```Powershell
        for ($i = 0; $i -le 50000; $i++) { New-CsPersistentChatRoom -Category <parent category> -Name "StressChan_$i" -Privacy Open }
    ```    

トポロジに合わせて構成ファイルを編集します。

**LoaderProcess**で、"controller.contoso.com" をコントローラーコンピューターの完全修飾ドメイン名 (FQDN) に変更します。

StressLauncher で、**次のよう**に入力します。

1.  "LoaderBinary" 設定値を共有フォルダーのパスに変更します。

2.  ローダーコンピューターに対する管理者アクセス権を持つ資格情報に、"AdminUser"/"Adminuser" を変更します。

3.  "ChannelCategory" を、ストレスチャネルが作成されたカテゴリの名前に変更します。

4.  ストレスユーザーの資格情報に一致するテンプレートに "UserNamePattern" と "UserPasswordPattern" を変更します。 {0}は、ユーザーのインデックス番号に置き換えられます。

5.  テストトポロジの SIP ドメインに "Domain" を変更します。

6.  常設チャットバックエンドデータベースの接続文字列に "ConnectionString" を変更します。

7.  "UserIndexStart" を最初のストレスユーザーのインデックスに変更します。

8.  "LyncFQDN" をフロントエンドプールの FQDN に変更します。

9.  すべてのローダーコンピューターのコンピューター名を含めるように、"Machines" リストを変更します。

10. サービスエンドポイントの baseAddress (既定値は "controller.contoso.com") を、使用しているコントローラーコンピューターの FQDN に変更します。

</div>

<div>

## <a name="usage"></a>使用方法

構成が完了したら、コントローラマシンで StressLauncher を開きます。 StressLauncher は、任意のユーザーとして起動できます。 ローダーコンピューターでのローダープロセスの開始に使用する資格情報は、構成ファイルで指定する必要があります。 また、常設チャットバックエンドデータベースへの読み取りアクセス権を持つ接続文字列も指定する必要があります。 この接続文字列が統合 Windows 認証を使用している場合は、このアクセス権を持つユーザーとして StressLauncher を起動する必要があります。

必要に応じて、ユーザーモデルの設定を変更します。 [**読み込み開始**] をクリックして、実行を開始します。 1分以上経過すると、ユーザーはサインインし始め、進行状況バーがいっぱいになります。 この時点で、コントローラーマシンは動作し、パフォーマンスの測定を行うことができます。

</div>

</div>

<div>

## <a name="chatupgradeverifier"></a>ChatUpgradeVerifier

<div>

## <a name="description"></a>説明

ChatUpgradeVerifier は、常設チャット固有のデータベース比較ツールです。 このツールでは、グループチャット 2007 R2 またはグループチャット2010データベース (2007/2010Db) を常設チャット2013データベース (2010Db) に比較します。

ツールは、1つずつ、それぞれカテゴリ、常設チャットルーム、および 2007/2010Db のアドインをチェックして、2010Db に表示されているかどうかを確認します。 この比較には、カテゴリ、チャットルーム、またはアドインのすべての設定、カテゴリのスコープ内のプリンシパル、およびカテゴリまたはチャットルームのいずれかのロールのプリンシパルがすべてチェックされます。 カテゴリまたはチャットルームが2013Db で正しく表示されない場合は、競合ファイルにその違いが出力されます。 アップグレードが行われた後、2007/2010Db が変更された後、このツールが実行されると、競合ファイルへの相違が出力されます。 このアプリケーションはデータベース比較ツールにのみ適用され、アップグレードプロセスは検証されないことに注意してください。

</div>

<div>

## <a name="requirements"></a>Requirements

常設チャットリソースキットツールを、常設チャットバックエンドデータベース (常設チャットの場合は以前のバージョンと現在のバージョン) にアクセスできるドメインに参加しているコンピューターにインストールします。

ツールを実行するユーザーアカウントは、常設チャットデータベースへの読み取りアクセス権を持っている必要があります。

ChatUpgradeVerifier ファイルには、適切なグループチャットデータベース (Groupchat 2007R2 または 2010) への接続文字列を含む GroupChat2007R2Db パラメーターまたは GroupChat2010Db パラメーターのいずれかが含まれている必要があります。 また、常設チャット2013データベースへの接続文字列を含む PersistentChat2013Db パラメーターも含める必要があります。

</div>

<div>

## <a name="usage"></a>使用方法

**Chatupgradeverifier**をパラメーターなしで実行します。

</div>

<div>

## <a name="example"></a>例

![ChatUpgradeVerifier を実行しています。](images/JJ945599.4c273bc3-7926-47c7-ade7-34522721ebf9(OCS.15).jpg "ChatUpgradeVerifier を実行しています。")

</div>

</div>

<div>

## <a name="persistent-chat-usage-report"></a>常設チャットの使用レポート

<div>

## <a name="description"></a>説明

ChatUsageReport ツールは、常設チャットサービスの利用状況の HTML レポートを生成します。

</div>

<div>

## <a name="requirements"></a>Requirements

常設チャットリソースキットツールを、常設チャットバックエンドデータベースにアクセスできるドメインに参加しているコンピューターにインストールします。

ツールを実行するユーザーアカウントは、常設チャットのバックエンドデータベースに対する読み取りアクセス権を持っている必要があります。

ChatUsageReport ファイルには、常設チャットバックエンドデータベースへの\<接続\>文字列を定義する connectionStrings セクションを含める必要があります。 既定の構成ファイルの内容は、参照用にここに記載されています。

</div>

<div>

## <a name="usage"></a>使用方法

```Powershell
    ChatUsageReport [-StartDate {date}] [-EndDate {date}] [-TopActiveUsers {n}] [-TopActiveRooms {n}] [-LeastActiveRooms {n}] [-RoomsInactiveSince {Date}] [-OutputFolder {path}]
```
これらのパラメーターは、データの選択を定義します。

**StartDate:** オプションで、選択期間の UTC 開始日を指定します。 既定値: 最も早い日付

**EndDate:** オプションで、選択期間の UTC 終了日を指定します。 既定値: Now

これらのパラメーターは、どのデータをどのように表示するかを定義します。

**Topactiveusers:** この値を指定すると、ユーザーが選択した期間のチャットルームに投稿したメッセージ数に関して、最もアクティブな n 人のユーザーがレポートに含まれます。 既定値: 10

**TopActiveRooms:** この値が指定されている場合、選択された期間の会議室に投稿されたメッセージの数に関して、最もアクティブなチャットルームがレポートに含まれます。 既定値: 10

**LeastActiveRooms:** この値が指定されている場合、選択した期間のチャットルームに投稿されたメッセージ数に関して、少なくとも1個のアクティブなチャットルームがレポートに含まれます。 ルームには、少なくとも1つのメッセージが投稿されます。 既定値: 10

**RoomsInactiveSince:** この指定を指定すると、指定された日付以降に非アクティブになったチャットルームの一覧がレポートに含まれます。 既定値: 時間全体

**Outputfolder:** ChatUsageReport およびグラフ画像が配置されるフォルダー。 これは、config ファイルまたはコマンドラインで定義されている必要があります。

すべてのコマンドラインパラメーターの値は、ツールと同じディレクトリにある ChatUsageReport ファイルで指定することもできます。 構成ファイルとコマンドラインの両方でいずれかの値が指定されている場合、コマンドラインの値は構成ファイルの値より優先されます。

</div>

<div>

## <a name="output"></a>出力

レポートには、常に次の出力が含まれます。

  - 選択した期間のメッセージ投稿数ごとの最もアクティブなチャットルームの上位 n 個。

  - 選択した期間のメッセージ投稿数ごとの上位 n 個のアクティブユーザー。

  - 選択した期間のメッセージ投稿数ごとの、最もアクティブでないチャットルームの上位 n 個。

  - データベースの全期間または指定された日付以降に非アクティブなチャットルーム。

  - 選択した期間の毎日のメッセージ投稿の傾向。

  - 選択した期間の週単位のメッセージ投稿の傾向。

  - 選択された期間のメッセージ投稿の月単位の傾向。

  - 選択した期間のメッセージ投稿の合計数。

  - 有効になっているルームの合計数。

</div>

<div>

## <a name="example"></a>例

次の例では、2001年全体の利用状況レポートを生成し、ChatUsageReport で指定されている OutputFolder にレポートを配置します。

```Powershell
    ChatUsageReport -RoomsInactiveSince 06-20-2010
```
ChatUsageReport:

```XML
    <?xml version="1.0" encoding="utf-8" ?>
    <configuration>
      <connectionStrings>
        <!-- The PersistentChat connection string must be defined in this file. -->
        <add name="PersistentChat" connectionString="Data Source=contoso.com\RTC;Initial Catalog=mgc;Integrated Security=SSPI"/>
      </connectionStrings>
      <appSettings>
        <!-- The OutputFolder must be defined here or on the command line. -->
        <add key="OutputFolder" value="."/>
        <!-- The values below are the same as the application defaults. -->
        <add key="StartDate" value="01/01/0001"/>
        <add key="EndDate" value="12/31/9999"/>
        <add key="TopActiveUsers" value="10"/>
        <add key="TopActiveRooms" value="10"/>
        <add key="LeastActiveRooms" value="10"/>
        <add key="RoomsInactiveSince" value="01/01/0001"/>
      </appSettings>
    </configuration></configuration>
```
</div>

</div>

<div>

## <a name="scheduleadsyncforprincipal"></a>ScheduleADSyncForPrincipal

<div>

## <a name="description"></a>説明

ScheduleADSyncForPrincipal は、常設チャットバックエンドデータベースに接続されている場合に SQL Server Management Studio 内から直接実行する必要がある Microsoft SQL Server 2012 スクリプトです。 このスクリプトを使用すると、永続的なチャットを強制して、スケジュールされた同期時間を待つのではなく、ユーザーのレコードを Active Directory ドメインサービスのレコードと同期させることができます。

</div>

<div>

## <a name="requirements"></a>Requirements

スクリプトを実行するユーザーアカウントは、常設チャットのバックエンドデータベースに対する所有者アクセス権を持っている必要があります。

</div>

<div>

## <a name="usage"></a>使用方法

既定のスクリプトの内容は次のとおりです。

```Powershell
    /*
    This script will schedule a principal for a forced AD synchronization cycle
    
    If you're using Sql Server Management Studio, pressing Ctrl+Shift+M will 
    allow you to specify values for the template parameter.
    */
    
        insert into
          tblPrincipalMeta
          (
           prinID
          ,prinAffiliationsDirty
          ,prinAttributesDirty
          ,prinDeleted
          )
          select
            prinID
           ,1
           ,1
           ,0
          from
            tblPrincipal
          where
            prinID not in (select prinID from tblPrincipalMeta) and
            prinID = <PrinID,int,0>
     
        update
          tblPrincipalMeta
        set
          prinAffiliationsDirty = 1
         ,prinAttributesDirty = 1
         ,tryCount = 0
         ,nextTry = null
        where
         prinID = <PrinID,int,0>
```

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

