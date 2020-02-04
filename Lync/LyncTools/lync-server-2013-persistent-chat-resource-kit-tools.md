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
ms.openlocfilehash: a827892dac61ff88d0527eafb7d94948afa21885
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739417"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="lync-server-2013-persistent-chat-resource-kit-tools"></a>Lync Server 2013 常設チャットリソースキットツール

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2013-02-24_

Lync Server 2013 常設チャットリソースキットツールは、Lync Server 2013 常設チャットサーバーの展開と管理を行う IT 管理者にとって、日常的なタスクを簡単にするのに役立ちます。 このトピックでは、インストール手順に加えて、各ツールの目的とその用途の例について説明します。

<div>

## <a name="installation-of-the-resource-kit-tools"></a>リソース キット ツールのインストール

Lync Server 2013 のリソースキットツールをインストールするには、 **PersistentChatReskit**をダウンロードします。 簡単なインストールを実行するには、 **PersistentChatReskit**を実行します。 .Msi は、次のパスにあるすべてのツールを\\インストールします。 **Program\\ Files\\Microsoft Lync server 2013 常設チャットサーバーリソースキット**。 このフォルダーには、自己完結型のツールの実行可能ファイルが格納されます。 ファイルが自分のサブフォルダーにもあるツール。

<div>


> [!IMPORTANT]  
> Lync server 2013 のリソースキットツールをインストールした後、 <STRONG>PsExec</STRONG>をインストールして、 <STRONG>PsExec</STRONG>を次のパスにコピーする\\必要があります: <STRONG>Program Files \ Lync server 2013 \ 常設チャットサーバーリソース Kit\ChatStressTool</STRONG>。 <STRONG>PsExec</STRONG>をコピーしない場合、常設チャットのストレスツールでエラー例外がスローされ、正しく実行されません。 ツールを実行する前に、必ずこの必須要件を満たしていることを確認してください。 <STRONG>PsExec</STRONG>のインストールの詳細については<A href="http://go.microsoft.com/fwlink/p/?linkid=282246">http://go.microsoft.com/fwlink/p/?LinkId=282246</A>、を参照してください。



</div>

</div>

<div>

## <a name="supported-environments"></a>サポートされる環境

最適なパフォーマンスを実現するには、Lync Server 2013、リソースキットツールを同じ環境にインストールして、Lync Server 2013 で必要とされる仕様と同じようにする必要があります。

</div>

<div>

## <a name="resource-kit-tools-overview"></a>リソース キット ツールの概要

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

このツールは、常設チャットバックエンドデータベースユーザーとグループの所属レコードが Active Directory ドメインサービスのものと一致することを確認します。

</div>

<div>

## <a name="requirements"></a>要件

このツールは、ドメインに参加しているコンピューター上の PersistentChatResKit installer と共にインストールされます。

ツールが実行されるユーザーアカウントには、常設チャットのバックエンドデータベースと Active Directory ドメインサービスへの読み取りアクセス権が必要です。

</div>

<div>

## <a name="usage"></a>使用方法

構成ファイルに記載されている手順に従って、またはコマンドラインパラメーターを指定せずに、操作を実行します。 次に示すのは、既定の影響を示す .exe の内容です。

**影響を確認します。**

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

PersistentChatMonitoringSummary ツールは、一時的なチャット監視情報を監視データベースから指定された CSV ログファイルに移動します。

CSV ファイルには、合計セッション数、成功セッション、予期しないエラー、予期したエラーの数、診断 ID、失敗数、障害の説明による予期しないエラーの内訳が含まれています。

</div>

<div>

## <a name="requirements"></a>要件

固定チャットリソースキットツールを、監視データベースにアクセスできるドメインに参加しているコンピューターにインストールします。

ツールを実行するユーザーアカウントには、監視データベースへの読み取りアクセス権が必要です。

PersistentChatMonitoringSummary というファイルには、監視データベースへの接続\<文字列\>を定義する connectionStrings セクションが含まれている必要があります。 また、監視データを収集する PersistentChatEndpointUri のキーと、生成される CSV ファイルの場所へのファイルパスが含まれている必要があります。 例については、インストールされている構成ファイルを参照してください。 このファイルは、ツールと同じディレクトリ内に存在する必要があります。

</div>

<div>

## <a name="usage"></a>使用方法

```Batch
    PersistentChatMonitoringSummary [-StartDateTime <date>] [-EndDateTime <date>]
```

次のパラメーターでデータの選択を定義します。

**StartDateTime:** 必要に応じて、選択期間の開始日を指定します。 既定値: 1/1/1753 12:00:00 AM

**Enddatetime:** オプションで、選択期間の最後の日付を指定します。 既定値: 今すぐ

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

## <a name="persistent-chat-stress-tool"></a>常設チャット応力ツール

<div>

## <a name="description"></a>説明

常設チャットのストレスツールでは、継続的なチャットの使用をシミュレートして、さまざまなユーザーモデルを含め、想定される用途のシナリオに合わせてリアルタイムのパフォーマンスをテストすることができます。

</div>

<div>

## <a name="requirements"></a>要件

常設チャットリソースキットツールを、常設チャットのバックエンドデータベースにアクセスできるドメインに参加しているコンピューターにインストールします。

この*コントローラー*マシンに加えて、いくつかの*ローダー*マシンが必要です。 ユーザーモデル内のすべての10K ユーザーに対して、ローダーコンピューターで少なくとも 4 GB の空き RAM が必要です。 たとえば、80K ユーザーとの実行には、すべてのローダーコンピューターで分散した RAM の 32 GB が必要です。 予想される負荷に関係なく、少なくとも3つのローダーコンピューターを持っていることをお勧めします。

ローダーコンピューターには、.NET 4.5 フレームワークに加えて、Visual C++ 2012 再頒布可能パッケージがインストールされている必要があります。

</div>

<div>

## <a name="configuration"></a>構成

すべてのローダーコンピューターからアクセスできる共有フォルダーに ChatStressTool ファイルをコピーします。

ストレスの実行で使用するユーザーとチャネルを作成します。

  - ユーザーモデルを使って通話を発信し、Lync で有効にして、常設チャットポリシーを [有効] に設定します。

  - 応力チャネルのカテゴリを作成し、そのカテゴリに必要なだけのルームを作成します。 カテゴリには、(OU を追加することで)**許可**リスト内のすべてのストレスユーザーを含める必要があります。また、ストレスルームには、 **[開く**] のプライバシー設定が必要です。

  - 追加のストレス会議を作成することをお勧めします。 5万ルームを作成するには、次の Windows PowerShell コマンドラインインターフェイスコマンドを使用します。
    ```Powershell
        for ($i = 0; $i -le 50000; $i++) { New-CsPersistentChatRoom -Category <parent category> -Name "StressChan_$i" -Privacy Open }
    ```    

トポロジに合わせて構成ファイルを編集します。

**LoaderProcess**で、"controller.contoso.com" をコントローラーコンピューターの完全修飾ドメイン名 (FQDN) に変更します。

**StressLauncher で次のよう**になります。

1.  "LoaderBinary" 設定値を共有フォルダーのパスに変更します。

2.  ローダーコンピューターへの管理者アクセス権を持つ資格情報に "AdminUser"/"Adminuser" を変更します。

3.  "ChannelCategory" を、ストレスチャンネルが作成されたカテゴリの名前に変更します。

4.  "UserNamePattern" と "UserPasswordPattern" を、ストレスユーザーの資格情報と一致するテンプレートに変更します。 {0}は、ユーザーのインデックス番号に置き換えられます。

5.  "Domain" をテストトポロジの SIP ドメインに変更します。

6.  "ConnectionString" を永続的なチャットのバックエンドデータベースの接続文字列に変更します。

7.  "UserIndexStart" を最初のストレスユーザーのインデックスに変更します。

8.  "LyncFQDN" をフロントエンドプールの FQDN に変更します。

9.  [マシン] の一覧を変更して、すべてのローダーコンピューターにコンピューター名を含めます。

10. サービスエンドポイントの baseAddress (既定は "controller.contoso.com") をコントローラーコンピューターの FQDN に変更します。

</div>

<div>

## <a name="usage"></a>使用方法

構成が完了したら、コントローラーコンピューターで StressLauncher を開きます。 StressLauncher は、任意のユーザーとして起動できます。 ローダーコンピューターで開始されるローダープロセスの資格情報は、構成ファイルで指定する必要があります。 また、常設チャットバックエンドデータベースへの読み取りアクセス権を持つ接続文字列も指定する必要があります。 この接続文字列で統合 Windows 認証を使っている場合は、このアクセス権を持つユーザーとして StressLauncher を起動する必要があります。

必要に応じて、ユーザーモデルの設定を変更します。 [**読み込みの開始**] をクリックして実行を開始します。 1分以上経過すると、ユーザーはサインインを開始し、進行状況バーの入力が開始されます。 この時点で、コントローラーマシンは動作し、パフォーマンスの測定を行うことができます。

</div>

</div>

<div>

## <a name="chatupgradeverifier"></a>ChatUpgradeVerifier

<div>

## <a name="description"></a>説明

ChatUpgradeVerifier は、常設チャット固有のデータベース比較ツールです。 このツールは、グループチャット 2007 R2 またはグループチャット2010データベース (2007/2010Db) を常設 Chat 2013 データベース (2010Db) に比較します。

ツールは、1つずつ、各カテゴリ、常設チャットルーム、および 2007/2010Db のアドインをチェックして、2010Db に表示されているかどうかを確認します。 比較では、カテゴリ、チャットルーム、アドイン、カテゴリの範囲に含まれるすべてのプリンシパル、カテゴリまたはチャットルームのいずれかのプリンシパルのすべての設定を確認することができます。 カテゴリまたはチャットルームが2013Db で正しく表示されない場合、相違点は競合ファイルに出力されます。 アップグレードが行われた後に、2007/2010Db が変更され、このツールが実行されると、競合ファイルへの相違点が出力されます。 このアプリケーションはデータベースの比較ツールにすぎないことに注意してください。アップグレードプロセスを検証しません。

</div>

<div>

## <a name="requirements"></a>要件

常設チャットリソースキットツールは、常設チャットのバックエンドデータベースにアクセスできるドメインに参加しているコンピューターにインストールします (これは、常設チャット用の以前のバージョンと現在のバージョンになります)。

ツールを実行するユーザーアカウントには、常設チャットデータベースへの読み取りアクセス権が必要です。

ChatUpgradeVerifier ファイルには、適切なグループチャットデータベース (Groupchat 2007R2 または 2010) への接続文字列を含む、GroupChat2007R2Db パラメーターまたは GroupChat2010Db パラメーターのいずれかが含まれている必要があります。 また、常設 Chat 2013 データベースへの接続文字列を持つ PersistentChat2013Db パラメーターも含まれている必要があります。

</div>

<div>

## <a name="usage"></a>使用方法

パラメーターなしで**Chatupgradeverifier**を実行します。

</div>

<div>

## <a name="example"></a>例

![ChatUpgradeVerifier.exe の実行](images/JJ945599.4c273bc3-7926-47c7-ade7-34522721ebf9(OCS.15).jpg "ChatUpgradeVerifier.exe の実行")

</div>

</div>

<div>

## <a name="persistent-chat-usage-report"></a>常設チャットの使用状況レポート

<div>

## <a name="description"></a>説明

ChatUsageReport ツールは、常設チャットサービスの利用状況に関する HTML レポートを生成します。

</div>

<div>

## <a name="requirements"></a>要件

常設チャットリソースキットツールは、常設チャットのバックエンドデータベースにアクセスできるドメインに参加しているコンピューターにインストールします。

ツールが実行されるユーザーアカウントには、常設チャットのバックエンドデータベースへの読み取りアクセス権が必要です。

ChatUsageReport というファイルには、常設チャットバックエンドデータベース\<へ\>の接続文字列を定義する connectionStrings セクションが含まれている必要があります。 既定の構成ファイルの内容は、参照用にここに記載されています。

</div>

<div>

## <a name="usage"></a>使用方法

```Powershell
    ChatUsageReport [-StartDate {date}] [-EndDate {date}] [-TopActiveUsers {n}] [-TopActiveRooms {n}] [-LeastActiveRooms {n}] [-RoomsInactiveSince {Date}] [-OutputFolder {path}]
```
次のパラメーターでデータの選択を定義します。

**StartDate:** オプションで、選択期間の UTC 開始日を指定します。 既定値: 最も古い日付

終了日 **:** オプションで、選択期間の UTC の終了日を指定します。 既定値: 今すぐ

これらのパラメーターは、どのように表示されるかを定義します。

**Topactiveusers:** この値が指定されている場合、レポートには、選択した期間にユーザーがチャットルームに投稿したメッセージの数に基づいて、最もアクティブな n 人のユーザーが含まれます。 既定値:10

**TopActiveRooms:** この値が指定されている場合、レポートには、選択した期間のルームに投稿されたメッセージ数に基づいて、最もアクティブなチャットルームが含まれます。 既定値:10

**LeastActiveRooms:** この値を指定すると、選択した期間のチャットルームに投稿されたメッセージ数に基づいて、アクティブなチャットルームが少なくとも1つ含まれます。 ルームには、少なくとも1つのメッセージが投稿されます。 既定値:10

**RoomsInactiveSince:** 指定した場合、レポートには、指定した日付以降に無効になっているチャットルームのリストが含まれます。 既定値: 時間全体

**Outputfolder:** ChatUsageReport とグラフ画像が配置されているフォルダー。 これは、構成ファイルまたはコマンドラインで定義されている必要があります。

すべてのコマンドラインパラメーターの値は、ツールと同じディレクトリにある ChatUsageReport ファイルで指定することもできます。 構成ファイルとコマンドラインの両方でいずれかの値が指定されている場合、コマンドライン値は構成ファイルの値を上書きします。

</div>

<div>

## <a name="output"></a>出力

レポートには、常に次の出力が含まれます。

  - 選択された期間のメッセージ投稿数に基づいて、最もアクティブなチャットルームの上位 n 個。

  - 選択した期間のメッセージ投稿数に基づいて、最もアクティブなユーザーの上位 n 個。

  - 選択された期間のメッセージ投稿数の多い、最もアクティブなチャットルーム。

  - データベースの全期間にわたって、または指定した日付以降、非アクティブなチャットルーム。

  - 選択された期間の毎日のメッセージ投稿の傾向。

  - 選択された期間の毎週のメッセージ投稿の傾向。

  - 選択された期間の月次メッセージ投稿のトレンド。

  - 選択された期間のメッセージ投稿の合計数です。

  - 有効なルームの合計数です。

</div>

<div>

## <a name="example"></a>例

次の例では、2001年全体の利用状況レポートを生成し、ChatUsageReport で指定された OutputFolder にレポートを配置します。

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

ScheduleADSyncForPrincipal は、常設チャットバックエンドデータベースに接続しているときに、SQL Server Management Studio 内から直接実行する必要がある Microsoft SQL Server 2012 スクリプトです。 このスクリプトを使用すると、強制チャットによって、スケジュールされた同期時間を待つのではなく、Active Directory ドメインサービスのユーザーのレコードを同期することができます。

</div>

<div>

## <a name="requirements"></a>要件

スクリプトが実行されるユーザーアカウントには、常設チャットバックエンドデータベースへの所有者アクセス権が必要です。

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

