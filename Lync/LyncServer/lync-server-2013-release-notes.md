---
title: 'Lync Server 2013: リリース ノート'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Release notes
ms:assetid: 9f9e864c-3365-4800-803c-5289bd8fd363
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205120(v=OCS.15)
ms:contentKeyID: 48184930
ms.date: 12/09/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 10961f0a8e59fe1d0dc0268b430f37fd294252b6
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41724387"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="release-notes-for-lync-server-2013"></a>Lync Server 2013 のリリース ノート

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2016-12-08_

Lync Server 2013 のリリースノートへようこそ。 Lync Server 2013 に関する既知の問題については、このファイルを参照してください。

<div>

## <a name="about-this-document"></a>このドキュメントについて

このドキュメントには、Lync Server 2013 を展開して使用する前に知っておく必要がある重要な情報が含まれています。 Lync Server 2013 の詳細については、「 [Microsoft Lync server 2013](microsoft-lync-server-2013.md)のドキュメント」を参照してください。

このドキュメントには、次のセクションが含まれています。

  - Lync 2013 クライアント

  - Lync Server

  - インストール

  - モビリティ

  - 会議

  - エンタープライズ VoIP

  - プレゼンス

  - 応答グループ アプリケーションとコール パーク アプリケーション

  - Lync Server コントロール パネル、トポロジ ビルダー、および計画ツール

  - 版

  - 著作

</div>

<span id="LyncClient"></span>

<div>

## <a name="lync-2013-client"></a>Lync 2013 クライアント

<div>

## <a name="transferring-a-file-in-an-instant-message-fails-if-the-file-is-open-in-another-application"></a>他のアプリケーションでファイルを開いている場合、インスタントメッセージでファイルを転送できない

**点**

別の Lync ユーザーにインスタントメッセージを追加して、Word 文書などのファイルを転送しようとすると、転送は成功したように見えますが、実際にはファイルの転送に失敗することがあります。 ファイルの種類のアイコンは Lync クライアントに表示されますが、目的の受信者がファイルを開くことはできません。 送信に失敗したことを通知するエラーメッセージは表示されません。

**ところ**

この問題を回避するには、インスタントメッセージでファイルを転送する前に、開いている開いているファイルまたはアプリケーションを閉じます。

</div>

</div>

<span id="LyncServer"></span>

<div>

## <a name="lync-server"></a>Lync Server

<div>

## <a name="if-lync-server-storage-service-data-replication-fails-administrators-will-need-to-check-performance-counters-for-stale-storage-service-queue-items"></a>Lync Server ストレージサービスのデータレプリケーションに失敗した場合、管理者は、古いストレージサービスキューアイテムのパフォーマンスカウンターを確認する必要があります。

**点**

Lync Server ストレージサービスは、Windows Fabric を使用してレプリケーションを行います。 プライマリフロントエンドサーバーでデータが削除されたが、セカンダリフロントエンドサーバーでの削除に失敗した場合 (たとえば、フロントエンドサーバーに予期しないシャットダウンまたはエラーが発生した場合)、データを残して、"切り離された" 状態にすることができます。 孤立したデータは、パフォーマンスが低下したり、ドライブの空き領域を浪費したりする可能性があります。

**ところ**

この問題を回避するには、イベント (Id\_=\_32058\_)\_と\_\_"いいね!" の**よう**に、CRITICAL\_(\_id = 32059) が使用されていることがイベントログで生成される場合、管理者は、"指定した期間が**古いキュー項目の数を指定**した名前で、フロントエンドサーバーのパフォーマンスカウンターを確認してください このパフォーマンスカウンターが大きい値 (たとえば、50,000 より大きい値) である場合、管理者は Lync Server 2013 リソースキットで CleanuUpStorageServiceData ツールを実行し、孤立したデータがプールからすべて削除されるようにする必要があります。 このツールの詳細については、「Lync Server 2013 リソースキットドキュメント」を参照してください。

</div>

<div>

## <a name="whenever-the-ip-address-configuration-is-changed-for-a-server-or-pool-lync-server-services-need-to-be-restarted"></a>サーバーまたはプールの IP アドレス構成が変更されるたびに、Lync Server サービスを再起動する必要があります。

**点**

IPv4 からデュアルスタックへの変更、またはデュアルスタックから Ipv6 への変更など、Lync Server 2013 の展開用に IP アドレス構成が変更された場合、すべてのサーバーコンポーネントは、サービスが再起動されるまで構成の変更を選択します。

**ところ**

この問題を回避するには、展開の IP アドレス構成を変更した後で Lync Server サービスを再起動します。 そのためには、Lync Server 管理シェルで次のコマンドレットを実行します。

   ```PowerShell
    Stop-CsWindowsService -graceful
   ```

   ```PowerShell
    Start-CsWindowsService
   ```

</div>

<div>

## <a name="the-dial-in-conferencing-synthetic-transaction-cmdlet-is-no-longer-available-in-the-lync-server-2013-management-pack"></a>ダイヤルイン会議の代理トランザクションコマンドレットは、Lync Server 2013 管理パックでは利用できなくなりました

**点**

ダイヤルイン会議の統合トランザクションコマンドレット**テスト**用の会議は、Lync Server 2013 管理パックでは利用できなくなりました。

**ところ**

ダイヤルイン会議の代理トランザクションコマンドレットの使用**テスト-Csdial In会議**は、社内でのみサポートされます。

トラブルシューティングのために、管理者は Lync Server 管理シェルのコマンドレットを引き続き使用することができます。 必要に応じて、社内でコマンドレットを実行するためのプライベート管理パックを開発することもできます。

</div>

<div>

## <a name="the-centralized-logging-service-stops-if-network-traffic-is-disrupted-when-log-files-are-being-copied-to-network-share"></a>ログファイルがネットワーク共有にコピーされているときに、ネットワークトラフィックが中断されると、一元管理サービスは停止します

**点**

中央集中ログサービスがネットワークパスを使用するよう**に構成さ**れている場合 (CacheFileNetworkFolder パラメーターの値は有効な UNC パスです)、キャッシュされたログファイルはネットワーク共有にコピーされます。 ファイルのコピー中にネットワークトラフィックが中断する場合は、集中化されたログサービスが停止する例外が発生します。

サービスが最大3回自動的に再起動するように構成されているため、サービスは最初の3つの例外から回復します。

**ところ**

この問題の回避策はありません。 問題を特定するには、"Lync Server 集中ログサービスエージェント" サービスが予期せず終了したときにログに記録する "サービスコントロールマネージャー" からイベント7031ログを監視します。 この問題が3回以上発生する場合は、 **Start-CsWindowService**コマンドレットを使用してサービスを手動で再開します。

</div>

<div>

## <a name="storage-service-queue-items-need-to-be-imported-manually"></a>ストレージサービスキューアイテムを手動でインポートする必要がある

**点**

Lync Server 2013 は、アーカイブされたメッセージや通話の詳細記録 (CDR) など、各フロントエンドサーバー上のデータベース上の会議とインスタントメッセージに関するデータを保存します。 指定された宛先に配信される前に、データはデータベースに格納されます。 Lync Server 2013 は、パフォーマンスを向上させるために、長期間に処理されていないローカルデータベースのキューアイテムを定期的にエクスポートし、ファイルストアに保存します。 ファイルストアを使用できない場合は、各フロントエンドサーバーにアイテムが格納されます。 プールのフェールオーバー中にデータが失われないように、同じ操作が発生します。

エクスポート操作の実行中、Lync Server ストレージサービスは、イベント Id (完全なフラッシュ操作が開始されました)、32076 (完全なフラッシュが完了)、32082 (メンテナンスレベルのフラッシュが開始されました) 32075 の各ステージをイベントログに記録し32083ます。完了)、32089 (データベースの読み込みによってフラッシュが発生しました)。 このデータは、処理されて最終的な送信先 (SQL Server または Exchange Server) に配信されるように、システムに自動的にインポートされることはありません。

**ところ**

システムにデータをインポートするには、管理者は Lync Server リソースキットの ImportStorageServiceData ツールを使用する必要があります。これにより、システムにデータが追加され、最終的な送信先に配信されます。

</div>

<div>

## <a name="address-book-web-query-searches-will-fail-if-the-default-value-for-usenormalizationrules-is-changed-to-false"></a>UseNormalizationRules の既定値が False に変更されている場合、アドレス帳の Web クエリの検索は失敗します。

**点**

UseNormalizationRules の既定値が False に変更されると、アドレス帳の Web クエリの検索は失敗します。 既定値が変更されると、Lync クライアントユーザーは Lync アドレス帳の web クエリを使ってユーザーを検索することができなくなります。

**ところ**

UseNormalizationRules の既定値が False に設定されている場合に、ユーザーが Lync Server 2013 で定義されている電話番号を使用できるようにするには、次の操作を行ってこの問題を回避します。

1.  Lync Server 管理シェルを起動します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server 管理シェル**] の順にクリックします。

2.  次のいずれかを実行します。
    
      - 展開に Lync Server 2013 サーバーしか含まれていない場合は、次のコマンドレットをグローバルレベルで実行して、UseNormalizationRules と IgnoreGenericRules の値を True に変更します。
        
            Set-CsAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true
    
      - 展開に Lync Server 2013 および Lync Server 2010 または Office Communications Server 2007 R2 の組み合わせが含まれている場合は、次のコマンドレットを実行して、トポロジの各 Lync Server 2013 プールに割り当てます。
        
            new-csAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true

3.  CMS のレプリケーションがすべてのプールで行われるのを待ちます。

4.  展開の電話の正規化規則ファイルを変更して、コンテンツをクリアします。 ファイルは、各 Lync Server 2013 プールのファイル共有にあります。 ファイルが表示されていない場合は、"\_会社電話\_番号\_の正規化\_ルール .txt" という名前の空のファイルを作成します。

5.  すべてのフロントエンドプールが新しいファイルを読み取るまで数分待ちます。

6.  展開の各 Lync Server 2013 プールで次のコマンドレットを実行します。
    
        Update-csAddressBook

</div>

<div>

## <a name="address-book-server-error-event-21054-is-generated-once-daily-for-each-lync-2013-pool"></a>アドレス帳サーバーエラーイベント21054が Lync 2013 プールごとに1回生成される

**点**

Lync Server 2013 アドレス帳サーバーでは、毎日のメンテナンス実行時に、毎日1回エラーイベント21054が生成されます。 また、更新が成功した場合でも、管理者が**csAddressBook**コマンドレットを実行するたびにエラーが生成されます。 ただし、更新が成功した場合は、このエラーイベントを無視しても問題ありません。

**ところ**

このエラーイベントが発生した場合は、次のコマンドレットを実行します。

    Debug-csAddressBookReplication -Poolfqdn <Pool FQDN for which the event was generated>

コマンドレットで、インデックスを作成しない、または破棄されたオブジェクトがないと報告された場合、エラーイベント21054は安全に無視できます。

さらに、System Center Operations Manager では、キー正常性インジケータ (KHI) のアドレス帳のユーザーが正しくインデックス処理されていることを無効にする必要があります。

</div>

<div>

## <a name="requests-may-fail-when-ipv6-is-configured-on-an-edge-pool"></a>エッジプールで IPv6 が構成されていると、要求が失敗することがある

**点**

エッジプールで IPv6 が構成されている場合、エッジプールへの要求が失敗することがあります。

**ところ**

この問題を回避するには、IPv6 でエッジプールを構成しないでください。

</div>

<div>

## <a name="the-invoke-cspoolfailback-cmdlet-may-fail-during-pool-failback"></a>プールのフェイルバック中に csPoolFailback コマンドレットが失敗することがある

**点**

プールをフェイルバックしようとすると、 **csPoolFailback**コマンドレットが失敗することがあります。「再試行後に hydration プロセスを完了できませんでした」というエラーが表示されることがあります。

**ところ**

この問題を回避するには、もう一度コマンドレットを実行し、コマンドレットが正常に完了するまで待ちます。 フェイルバックプロセスが完了するまで数分かかる場合があることに注意してください。 2万ユーザーがいるプールの場合、最大60分かかることがあります。

</div>

<div>

## <a name="data-loss-may-occur-when-you-add-a-front-end-server-to-an-already-established-pool--hybrid-skype-for-business-online"></a>フロントエンドサーバーを既に確立されているプール (ハイブリッド、Skype for Business Online) に追加すると、データが失われることがある

**点**

この問題は、プールに複数のフロントエンドサーバーがある環境で、フロントエンドサーバーの1つを再起動するか、またはプールの一部ではない新しいフロントエンドサーバーを追加することによって発生する場合があります。

データがアーカイブされているユーザーは、プールのデータアーカイブの安定した分布が確立されるまで、データの損失が発生する可能性があります。 このデータ損失の可能性がある期間は、人同士の会話で15分に制限され、会議に30分の通話が可能です。

**ところ**

プール内のフロントエンドサーバーを1つずつ開始する代わりに、管理を実行する場合は、プールを別のプールにフェールオーバーして、サーバーの保守タスクを実行する必要があります。 メンテナンスタスクを実行する前にサービスを利用できないようにすることもできます。メンテナンスが完了したら、空き時間情報を復元することもできます。

</div>

<div>

## <a name="administrators-cannot-get-licensee-count-by-using-the-get-csclientaccesslicense-cmdlet"></a>管理者は、取得-CsClientAccessLicense コマンドレットを使用してライセンシーの数を取得できません

**点**

管理者は、 **CsClientAccessLicense**コマンドレットを使用して、クライアントライセンスの正確な使用状況を取得することはできません。

**ところ**

サーバーのライセンスの種類を確認するには、ユーザーの**取得サービス**コマンドレットを実行して、すべてのデータベースの完全修飾ドメイン名 (FDQNs) を取得します。 フロントエンドサーバーの FQDN がバックエンドデータベースの FQDN と同じである場合、ライセンスは標準エディションライセンスです。 それ以外の場合は、ライセンスは Enterprise edition ライセンスです。

</div>

<div>

## <a name="client-licensee-count-is-not-accurately-reported"></a>クライアントのライセンス数が正確に報告されていない

**点**

クライアントのライセンス数を確認するときに、次のような状況が発生することがあります。

1.  **モバイルユーザーのライセンス数が正しくない**
    
    ライセンス数は、デバイスベースのユーザーの一意の IP アドレスの数に基づいています。 ライセンス数は、次のように制限されています。
    
      - ユーザーの IP アドレスが Lync セッション中に変更されると、ライセンスは過大にカウントされます。 この問題は、ユーザーがデスクトップクライアントで複数の場所から Lync Server に接続したときに発生する可能性があります。
    
      - ユーザーがモバイルクライアントに接続すると、デバイスの IP アドレスを確認できないため、ライセンスはカウントされます。

2.  **ライセンスは、公衆交換電話網 (PSTN) 通話、Lync クライアント、PSTN 回線への Lync クライアント通話、PSTN 回線に転送された Lync 通話に対して2回カウントされます。**
    
    次のシナリオでは、電話番号と Lync ユーザーの両方がカウントされ、使用されているライセンス数が判断されるため、2つの追加ライセンスは1つではなくカウントされます。 正確なライセンスデータを取得するには、電話番号によって生成されたライセンスを手動で削除します。
    
      - Lync への PSTN 電話通話
    
      - PSTN 回線への Lync 通話
    
      - Lync への PSTN 通話。その後、Lync が着信を PSTN 回線に転送します。 いずれかの PSTN 線がカウントされます。

3.  **ログオンしている Lync 携帯電話のライセンスはカウントされません**
    
    ユーザーが Lync 認定電話を使用している場合、電話のログイン後も接続されたままで、ログイン状態が維持されている場合は、ライセンスの照会が電話のログイン後に行われると、電話はライセンスを使用しているものとしてカウントされません。

4.  **電話会議に参加している PSTN 電話にカウントされたライセンス**
    
    ユーザーが PSTN 電話を使って会議に参加すると、会議に参加するためのライセンスが誤ってカウントされます。 ただし、PSTN 電話を使って会議に参加する場合はライセンスは必要ありません。

**ところ**

1.  **モバイルユーザーのライセンス数が正しくない**
    
      - 同じデバイスに属している IP アドレスを手動で特定して、ライセンス数のいずれかを削除することができます。
    
      - この問題の回避策は、Lync クライアントで接続しているモバイルデバイスには対応していません。

2.  **ライセンスは、Lync クライアントへの PSTN 通話、PSTN 回線への Lync クライアント通話、PSTN 回線への lync 通話の転送について2回カウントされます。**
    
    PSTN 電話番号を手動で特定し、生成されたライセンス数を削除する必要があります。

3.  **ログインしている Lync 携帯電話のライセンスはカウントされません**
    
    Lync 携帯電話を設定して、ログオフした後、3ヶ月ごとに定期的にログオンすることができます。

4.  **電話会議に参加している PSTN 電話にカウントされたライセンス**
    
    電話会議に参加するために使用される PSTN 電話番号を手動で特定して、電話番号によって生成されたライセンスを削除することができます。

</div>

<div>

## <a name="the-lync-server-control-panel-stops-working-in-a-vmware-environment-after-upgrading-to-silverlight-5"></a>Silverlight 5 にアップグレードした後、Lync Server コントロールパネルが VMware 環境で動作しなくなります。

**点**

VMware 環境で Lync Server コントロールパネルを使用すると、Microsoft Silverlight をバージョン5にアップグレードした後に Lync Server コントロールパネルが機能しなくなることがあります。

**ところ**

この問題を回避するには、次のいずれかの操作を行います。

  - Silverlight 5 をアンインストールし、から[https://go.microsoft.com/fwlink/p/?LinkID=149156](https://go.microsoft.com/fwlink/p/?linkid=149156)silverlight 4 をインストールします。

  - Lync Server コントロールパネルに、VMware 仮想コンピューターではないコンピューターからアクセスします。
    
    Lync server の管理ツールがコンピューターにインストールされている場合は、サーバーの Windows の [**スタート**] メニューから Lync Server コントロールパネルを起動することができます。
    
    Lync Server コントロールパネルには、web ブラウザーを使用してアクセスすることもできます。 この URL\<は https://フロントエンド\_プール\_の fqdn\>に似ています/cscp.

</div>

<div>

## <a name="user-information-in-the-address-book-service-is-not-updated-after-the-distinguished-name-for-the-user-is-modified-in-active-directory"></a>ユーザーの識別名が Active Directory で変更された後、アドレス帳サービスのユーザー情報が更新されない

**点**

Active Directory ドメインサービスでユーザーの識別名 (DN とも呼ばれます) が変更された場合、アドレス帳サービス (ABS) では、追加の変更は更新されません。 この操作を行っても、ユーザーのサインインやプレゼンスには影響はありませんが、SIP アドレスが変更された場合、ユーザーは、古い SIP アドレスを返します。

**ところ**

この問題を回避するには、ユーザーの DN を変更しないでください。 ユーザーの DN を以前の値に戻した場合、更新はアドレス帳サービスに反映されます。

</div>

</div>

<span id="Installation"></span>

<div>

## <a name="installation"></a>インストール

<div>

## <a name="using-non-ascii-characters-may-result-in-lync-server-failing-to-start"></a>ASCII 以外の文字を使用すると、Lync server が起動しない場合がある

**点**

エクスポート先のフォルダー名に ASCII 以外の文字 (UNICODE、2バイト文字セット (DBCS)、UTF-8、UTF-16 など) が含まれている場合、セットアップは失敗します。 また、セットアップは成功しますが、ASCII 以外の文字が次のいずれかに含まれている場合は、サーバーが起動しません。

  - コンピューター名

  - ドメイン名

  - ユーザー名

  - ユーザー SIP URI

  - サービスアカウント名

**ところ**

目的のフォルダー名、コンピューター名、ドメイン名、ユーザー名、ユーザー SIP URI、およびサービスアカウント名には ASCII 文字のみを使用します。

</div>

<div>

## <a name="the-hotfix-for-heap-corruption-occurs-when-a-module-calls-the-insertentitybody-method-in-iis-75-must-be-installed-prior-to-installing-lync-server-2013"></a>"ヒープの破損" の修正プログラムは、Lync Server 2013 をインストールする前に、モジュールが IIS 7.5 の InsertEntityBody メソッドをインストールする必要がある場合に発生します。

**点**

"ヒープの破損" の修正プログラムは、「モジュールが IIS 7.5 で InsertEntityBody メソッドを[https://go.microsoft.com/fwlink/p/?LinkId=268602](https://go.microsoft.com/fwlink/p/?linkid=268602)呼び出すときに発生します。」 (264886[https://go.microsoft.com/fwlink/p/?LinkId=268603](https://go.microsoft.com/fwlink/p/?linkid=268603)) は、Lync Server 2013 をインストールする前にインストールする必要があります。

**ところ**

Microsoft ダウンロードセンターから修正プログラムをダウンロードしてインストール[https://go.microsoft.com/fwlink/p/?LinkId=268602](https://go.microsoft.com/fwlink/p/?linkid=268602)します。

</div>

<div>

## <a name="lync-server-2013-fails-to-install-on-ita-windows-server-2012-os-rtm-version"></a>Lync Server 2013 が ITA Windows Server 2012 OS RTM バージョンでインストールできない

**点**

Windows Fabric のインストールに失敗したため、ITA Windows Server 2012 で Lync Server 2013 のインストールが失敗します。

ファブリックトレースは、HH: MM: SS という時刻形式で作成されるため、Windows ファブリックインストールが失敗します。 ただし、ITA Windows Server では、時刻の形式は HH です。MM.SS。

**ところ**

この問題を回避するには、Lync Server 2013 をインストールする前にシステムレジストリを更新します。 更新する必要があるレジストリキーは、HKEY\_ユーザー\\です。既定\\のコントロール\\パネル\\国際形式の書式。 次のように Windows PowerShell コマンドラインインターフェイスを使用して、"s" 形式の値を HH: mm: ss に変更します。

1.  Windows PowerShell を起動し、次のコマンドレットを実行します。
    
       ```PowerShell
        New-PSDrive -Name HKU -PSProvider Registry -Root HKEY_USERS
       ```
    
       ```PowerShell
        $a="HKU:\.Default\Control Panel\International"
       ```

2.  現在の値を表示するには、次のコマンドレットを実行します。
    
        Get-itemproperty $a -Name sTimeFormat
    
    インストールの完了後に復元できるように、現在の形式の値をメモしておきます。

3.  新しい値に設定するには、次のコマンドレットを実行します。
    
        Set-ItemProperty $a -Name sTimeFormat -Value "HH:mm:ss"

4.  Lync Server 2013 が正常にインストールされた後、次のコマンドレットを実行して、その形式の元の値を復元します。
    
        - Set-ItemProperty $a-Name という <の値について、手順3でメモした値を表示します。 上の> "

</div>

</div>

<span id="Mobility"></span>

<div>

## <a name="mobility"></a>モビリティ

<div>

## <a name="issues-for-mobile-clients-during-the-server-failover-process"></a>サーバーのフェールオーバープロセス中のモバイルクライアントの問題

**点**

Lync サーバーに障害が発生してフェールオーバープロセスが開始されると、次の問題がモバイルクライアントユーザーに影響を与える可能性があります。

  - フェールオーバーの開始後、最長10分間、Lync の着信またはシグナルがありません。

  - 着信チャット要求を受け入れることができません

  - 障害が発生したサーバーがユーザーのホームサーバーである場合、会議に参加できない

**ところ**

この問題の回避策はありません。 フェールオーバープロセスが完了すると、通常の機能が復元されます。

</div>

<div>

## <a name="if-a-mobile-user-declines-an-incoming-call-from-another-lync-endpoint-the-call-is-displayed-as-a-missed-conversion-on-lync-mobile-clients"></a>モバイルユーザーが別の Lync エンドポイントからの着信を拒否した場合、その通話は Lync モバイルクライアントでの不在着信として表示されます。

**点**

モバイルユーザーが着信を拒否した場合に、別の Lync エンドポイントから発信された通話は、デバイス呼び出しリストの電話ではなく、Lync モバイルクライアントで不在着信した会話として表示されます。

**ところ**

この問題の回避策はありません。

</div>

<div>

## <a name="the-mobile-client-may-not-display-a-federated-contacts-display-name-when-searching-for-contacts"></a>連絡先を検索するときに、モバイルクライアントでフェデレーション連絡先の表示名が表示されない場合がある

**点**

フェデレーションされた連絡先の表示名は、連絡先リストでフェデレーション連絡先を検索する場合など、一部のシナリオでは表示されない場合があります。 この問題は、Lync モバイルクライアントからの連絡先に対してアクティブなプレゼンスサブスクリプションがない場合に発生することがあります。

**ところ**

この問題の回避策はありません。

</div>

<div>

## <a name="in-the-mobile-client-invitee-and-timestamp-information-are-missing-from-a-missed-conversation-that-is-an-invitation-to-a-conference"></a>モバイルクライアントでは、会議に招待された不在着信した会話に出席者とタイムスタンプ情報が含まれていない

**点**

モバイルクライアントで、不在着信した会話が会議に招待された場合、不在着信した会話メッセージに出席者とタイムスタンプ情報が表示されません。

**ところ**

この問題の回避策はありません。

</div>

<div>

## <a name="mobile-client-users-making-calls-using-voip-are-not-be-able-to-leave-voice-mail-for-users-whose-voice-mail-is-configured-in-exchange-2010-or-earlier-versions"></a>VoIP を使用して電話をかけるモバイルクライアントユーザーが、Exchange 2010 以前のバージョンでボイスメールを構成しているユーザーのボイスメールを残すことができない

**点**

モバイルクライアントユーザーが VoIP を使用して通話を発信している場合、ユーザーは、Microsoft Exchange Server 2007 または Microsoft Exchange Server 2010 でボイスメールを使用するように構成されたユーザーのボイスメールメッセージを残すことはできません。

**ところ**

この問題を回避するには、Exchange 2010 と SP1 以降のバージョンの Microsoft Exchange Server を使用します。

</div>

<div>

## <a name="when-using-block-with-url-for-client-version-configuration-on-mobile-clients-an-incorrect-error-message-may-be-displayed"></a>モバイルクライアントでクライアントのバージョン構成の URL がブロックされていると、誤ったエラーメッセージが表示されることがある

**点**

モバイルクライアントでクライアントバージョン構成の**URL をブロック**すると、クライアントバージョンがサポートされていない場合に誤ったエラーメッセージが表示されることがあります。

**ところ**

この問題を回避するには、 **URL を**指定して block の代わりに**block**を使うようにクライアントのバージョン構成を構成します。

</div>

</div>

<span id="Conferencing"></span>

<div>

## <a name="conferencing"></a>会議

<div>

## <a name="antivirus-software-running-on-lync-server-2013front-end-servers-can-cause-application-domain-recycling-which-temporarily-interrupts-service-for-lync-web-app-2013-lync-mobile-2010-and-lync-mobile-2013-clients"></a>Lync Server 2013 フロントエンドサーバーで実行されているウイルス対策ソフトウェアが原因で、アプリケーションドメインのリサイクルが発生し、Lync Web App 2013、Lync Mobile 2010、Lync Mobile 2013 クライアントのサービスが一時的に停止することがあります。

**点**

ウイルス対策ソフトウェアを使用すると、アプリケーションドメインを再起動することができます。これにより、Lync Mobility Service 2013 および統合通信 (UC) Web API クライアントアプリケーション (Lync Web App 2013、Lync Mobile 2010、Lync Mobile 2013) が状態を失います。

**ところ**

この問題を回避するには、Web コンポーネントと .NET framework を含むフォルダーをウイルススキャンで除外します。 詳細については、「Microsoft サポート技術情報の記事 312592 "PRB: ASP.NET で" アプリケーションが再起動します "と[http://go.microsoft.com/fwlink/p/?linkid=3052\&kbid=312592](http://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=312592)いうエラーが表示されています。

次のフォルダーを除外する必要があります。

  - % ProgramFiles%\\Microsoft Lync Server 2013\\Web コンポーネント\\mcx\\Ext

  - % ProgramFiles%\\Microsoft Lync Server 2013\\Web コンポーネント\\mcx\\Int

  - % ProgramFiles%\\Microsoft Lync Server 2013\\Web コンポーネント\\ucwa\\Int

  - % ProgramFiles%\\Microsoft Lync Server 2013\\Web コンポーネント\\ucwa\\Ext

  - % Windir%\\Microsoft.NET\\Framework64\\v 4.0.30319\\Config

</div>

<div>

## <a name="activex-controls-or-native-xmlhttp-support-must-be-enabled-in-windows-internet-explorer-to-successfully-join-conferences"></a>会議に参加するには、Windows Internet Explorer で ActiveX コントロールまたはネイティブ XMLHTTP のサポートが有効になっている必要があります。

**点**

Windows Internet Explorer の Internet browser 設定で、ユーザーが ActiveX コントロールとネイティブ XMLHTTP のサポートを無効にしている場合、Internet Explorer が既定のブラウザーとして選択されていると、ユーザーは会議に参加できません。

**ところ**

Internet Explorer で ActiveX コントロールまたは "ネイティブ XMLHTTP サポート" を有効にします。

</div>

<div>

## <a name="lync-server-web-conferencing-service-cannot-recover-from-critical-mode"></a>Lync Server Web 会議サービスが、重要なモードから復元できない

**点**

システム障害が発生した場合に、クリティカルモードが有効になっていると、重要モードが開始され、会議が参加者に対して機能しなくなります。 管理者がシステムエラー (データベースの問題を修正するなど) を修正した後、データ会議サービスは自動的に回復しません。また、管理者は会議サービスを手動で再開して会議を再開する必要があります。

**ところ**

システム障害が修正された後、管理者は会議サービスを手動で再起動する必要があります。

</div>

<div>

## <a name="web-conferencing-service-ignores-the-http-proxy-for-external-office-web-app-servers"></a>外部の Office Web App サーバーの HTTP プロキシを無視する web 会議サービス

**点**

Web 会議サービスの外部に Office Web Apps サーバーを展開している場合 (つまり、社内ネットワークに接続されていないサーバーである)、インターネット、境界ネットワーク、Web 会議サービスに接続するには、次のような HTTP プロキシが必要です。Office Web Apps サーバーの検出は失敗します。 Web 会議サービスでは、[Office Web Apps サーバーセットアップ] の [トポロジビルダー] で定義されている HTTP プロキシ設定を無視します。 この結果、Lync クライアントは、会議の他の参加者と Microsoft PowerPoint 2010 共有を行うことができなくなります。 オンプレミスの Lync Server をインストールしていて、内部ネットワークで Office Web Apps サーバーがオンプレミスにも構成されている場合、プロキシ構成は必要ありません。

**ところ**

唯一の回避策は、外部の Office Web Apps サーバーとの通信に HTTP プロキシを使用する必要がある展開構成を持たないことです。

</div>

<div>

## <a name="adding-video-to-an-audio-conferencing-provider-conference-is-not-supported"></a>電話会議プロバイダーの会議へのビデオの追加はサポートされていません

**点**

ユーザーが音声会議プロバイダーの電話会議に参加している場合、ビデオの追加はサポートされません。

**ところ**

この問題の回避策はありません。

</div>

<div>

## <a name="topologies-with-ipv6-enabled-force-the-lync-web-app-silverlight-plug-in-auto-update-to-ensure-screen-sharing-functionality-can-work-from-lync-web-app"></a>IPv6 が有効になっているトポロジ lync Web App Silverlight プラグインを自動更新して、Lync Web App から画面共有機能を使用できるようにする

**点**

IPv6 を有効にしてトポロジを構成すると、以前のバージョンの画面共有プラグインが既にインストールされている場合、ユーザーは Lync Web App クライアントから画面を共有することはできません。

**ところ**

Lync Web App を使って会議に参加するときに、画面共有プラグインの最新バージョンに更新するには、次の2つ**のファイル**で "4.0.7457.0" から "4.0.7577.380" に変更します。

  - % ProgramFiles%\\Microsoft Lync Server 15\\Web コンポーネント\\は\\、\\Int\\クライアント\\プラグイン ReachAppShPluginProperties にアクセスします

  - % ProgramFiles%\\Microsoft Lync Server 15\\Web コンポーネント\\は\\Ext\\クライアント\\プラグイン\\ReachAppShPluginProperties に到達します。

</div>

</div>

<span id="EnterpriseVoice"></span>

<div>

## <a name="enterprise-voice"></a>エンタープライズ VoIP

<div>

## <a name="in-some-cases-a-lync-client-running-on-a-computer-configured-to-use-ipv4-and-ipv6-dual-stack-might-not-support-capabilities-that-rely-in-the-ip-subnet-of-the-computer-such-as-e911-media-bypass-call-admission-control-and-location-based-routing"></a>場合によっては、IPv4 と IPv6 を使用するように構成されているコンピューターで実行されている Lync クライアントで、E911、メディアのバイパス、通話受付制御、位置ベースのルーティングなど、コンピューターの IP サブネットに依存する機能がサポートされていないことがあります。

<div class="">


> [!NOTE]  
> このセクションの情報は Lync Server 2013 の累積的な更新プログラム: 2013 年 2 月に関係します。



</div>

**点**

使用しているコンピューターで、IPv4 および IPv6 デュアルスタックが有効になっていて、プロキシサーバーの DNS 解決に基づいている場合、クライアントはコンピューターの IPv6 アドレスを使ってサインインすることができます。 この操作を行うと、Lync クライアントは IPv6 でサポートされている機能のみをサポートします。これにより、E911、メディアバイパス、通話受付制御、位置情報に基づくルーティングが除外されます。

**ところ**

この問題を回避するには、クライアントコンピューターで IPv6 サポートを無効にします。

</div>

<div>

## <a name="if-enterprise-voice-is-not-configured-for-a-user-the-user-will-need-to-use-e164-format-to-dial-out-from-a-conference"></a>エンタープライズ Voip がユーザーに対して構成されていない場合、ユーザーは [E164] 形式を使用して電話会議からダイヤルアウトする必要があります。

**点**

エンタープライズボイスがユーザーに対して構成されていない場合は、ユーザーは [E164] 形式を使用して会議からのダイヤルアウトを成功させる必要があります。 E164 形式が使用されていない場合、ユーザーは電話会議からダイヤルアウトすることはできません。

**ところ**

この問題を回避するために、エンタープライズボイスを有効にしていないユーザーは、E164 形式の数字を使って会議からダイヤルアウトする必要があります。

</div>

</div>

<span id="Presence"></span>

<div>

## <a name="presence"></a>プレゼンス

<div>

## <a name="if-a-user-has-selected-block-all-invites-and-communications-while-the-unified-contact-store-is-turned-on-for-the-user-presence-status-is-not-rejected-when-it-should-be"></a>ユーザーが [すべての招待と通信をブロックする] をオンにした場合、統合連絡先ストアが有効になっているときにプレゼンス状態が拒否されない

**点**

ユーザーが [すべての招待と通信をブロックする] をオンにした場合、統合連絡先ストアが有効になっている間、プレゼンス状態は拒否されません。

**ところ**

この問題を回避するには、ユーザーに対してユニファイド連絡先ストアを無効にすることができます。 そのためには、次のコマンドレットを実行します。

    Set-CsUserServicesPolicy -Identity "<user display name>" -UcsAllowed $False

次に例を示します。

    Set-CsUserServicesPolicy -Identity "Ken Myer" -UcsAllowed $False

</div>

<div>

## <a name="office-communications-server-2007-r2-users-homed-on-premises-are-not-able-to-see-the-presence-status-of-skype-for-business-online-users-in-hybrid-deployments---hybrid"></a>Office Communications Server 2007 R2 をオンプレミスで使用している場合、ハイブリッド展開での Skype for Business Online ユーザーのプレゼンス状態の表示はできません。ハイブリッド

**点**

この問題は、Lync Server 2013 ディレクターを使用している場合にハイブリッド展開で発生する可能性があります。

Skype for Business Online を使用しているユーザーのプレゼンス状態は、オンプレミスのユーザーに対して不明なプレゼンスとして表示されます。 また、Skype for Business Online をホームとして使用しているユーザーは、Office Communications Server R2 オンプレミスユーザーのプレゼンス状態を表示することはできません。

**ところ**

この問題を部分的に回避するには、Lync Server 2013 ディレクターではなく、Lync Server 2013 のオンプレミスプールをポイントするように、Skype for Business Online ユーザーのホームサーバー (msrtcsip-userenabled true presencehomeserver) を変更します。 オンプレミスフロントエンドサーバーでこの設定を変更できます。

この回避策では、Office Communications Server 2007 R2 に所属しているユーザーのプレゼンス状態が Skype for Business Online ユーザーに正しく表示されます。

</div>

</div>

<span id="ResponseGroup"></span>

<div>

## <a name="response-group-application-call-park-application-and-group-call-pickup"></a>応答グループアプリケーション、コールパークアプリケーション、グループ通話のピックアップ

<div>

## <a name="a-caller-might-hear-one-second-of-music-on-hold-during-the-establishment-of-a-call-with-the-retrieving-party"></a>発信者は、相手を検索して通話を発信するときに、1秒間音楽の再生待ちを聞くことができます。

<div class="">


> [!NOTE]  
> このセクションの情報は Lync Server 2013 の累積的な更新プログラム: 2013 年 2 月に関係します。



</div>

**点**

グループ通話の集配を使用して通話を取得すると、発信者は、取得側で通話を発信するときに、1秒間音楽を保留にすることができます。

**ところ**

この問題の回避策はありません。

</div>

<div>

## <a name="a-response-group-agent-can-sign-in-and-sign-out-through-a-lync-server-2010-agent-console-to-lync-server-2010-formal-agent-groups-only"></a>応答グループエージェントは、Lync Server 2010 エージェントコンソールを使用して、Lync Server 2010 の正式なエージェントグループのみにサインインしてサインアウトすることができます。

**点**

Lync server 2013 応答グループエージェントは、lync Server 2010 エージェントコンソールを使用して、lync server 2010 正式なエージェントグループに対してのみサインインし、サインアウトすることができます。 Lync Server 2010 エージェントコンソールでは、ユーザーが所属している Lync Server の2010応答グループのみを表示できます。 自分が属している Lync Server 2013 応答グループを表示することはできません。

**ところ**

応答グループエージェントが Lync Server 2013 ユーザーであり、Lync Server 2013 の正式なエージェントグループの一部である場合、ユーザーはブラウザーの web リンクを通じて直接 Lync Server 2013 エージェントコンソールにアクセスし、Lync Server 2013 エージェントグループにサインインしてサインアウトする必要があります。

</div>

<div>

## <a name="a-lync-server-2010response-group-agent-cannot-place-calls-on-behalf-of-a-lync-server-2013response-group"></a>Lync server 2010 応答グループエージェントは、Lync Server 2013 応答グループの代理として通話を発信することはできません

**点**

Lync server 2013 応答グループのエージェントである Lync Server 2010 ユーザーは、応答グループの代理として通話を発信できません。 Lync Server 2013 応答グループは、通話を発信するために Lync クライアントでは利用できません。

**ところ**

この問題を回避するには、Lync Server 2010 ユーザーを Lync Server 2013 に移動する必要があります。

</div>

<div>

## <a name="removing-a-response-group-from-lync-server-2010-after-it-has-been-migrated-to-lync-server-2013-will-prevent-the-response-group-from-accepting-any-incoming-calls"></a>Lync server 2013 に移行された後に、Lync Server 2010 から応答グループを削除すると、応答グループが着信を受け付けることができなくなります。

**点**

Lync server 2010 から Lync server 2013 に移行された応答グループが lync server の [コントロールパネル] または [Lync Server 管理シェル] から2010削除された場合、Lync Server 2013 の応答グループは、着信の受信を停止します。

**ところ**

この問題を回避するには、Lync Server 2010 から Lync Server 2013 に移行された返信グループを Lync server 2010 から削除しないようにします。

応答グループが既に削除されている場合は、Lync Server 2013 で再展開する必要があります。

</div>

<div>

## <a name="when-a-new-managed-workflow-is-set-to-inactive-when-created-deployment-of-the-workflow-will-fail"></a>作成時に新しいマネージワークフローが非アクティブに設定されると、ワークフローの展開に失敗します。

**点**

作成時に新しいマネージワークフローが非アクティブに設定されると、ワークフローの展開が失敗します。 この問題は、作成時にワークフローが [非アクティブ] に設定されているときに発生しますが、展開された後に [非アクティブ] に設定するように編集されたワークフローには影響しません。

**ところ**

ワークフローを作成して展開するときに、ワークフローをアクティブとして設定し、展開します。 ワークフローが正常に展開されると、ワークフローが編集可能になり、[非アクティブ] に設定されます。

</div>

<div>

## <a name="removing-a-response-group-from-the-owner-pool-will-prevent-the-response-group-of-the-backup-pool-from-accepting-any-incoming-calls-during-failover-if-the-response-group-has-been-imported-to-the-backup-pool"></a>所有者プールから応答グループを削除すると、バックアッププールの応答グループがバックアッププールにインポートされた場合に、フェールオーバー中に着信を受け付けることができなくなります。

**点**

所有者を上書きせずに、プライマリプールによって所有されている応答グループがバックアッププールにインポートされていて、所有者プールから応答グループが削除された場合、バックアッププール内の応答グループは、フェールオーバー中に着信通話を受け入れません。

**ところ**

プライマリプールで応答グループを再展開する必要があります。 次に、プライマリプールから応答グループの構成をエクスポートして、もう一度バックアッププールにインポートする必要があります。

バックアッププールで応答グループを再作成することもできます。 この場合、バックアッププールは応答グループの所有者プールになります。

</div>

<div>

## <a name="a-parked-call-cant-be-retrieved-from-the-call-park-application-if-the-retrieve-request-is-done-on-behalf-of-a-response-group"></a>受信要求が応答グループの代理として実行されている場合は、保留中の通話をコールパークアプリケーションから取得できない

**点**

次の条件が満たされている場合は、保留中の通話の取得要求が失敗します。

  - エージェントが匿名応答グループの一部である

  - エージェントは、匿名応答グループを通じて、コールパークアプリケーションから保留中の通話を取得しようとします。

  - エージェントは、[代理人として呼び出し] オプションを通じて、または Lync アテンダントクライアントで同じオプションを使用して、軌道番号にダイヤルすることで、通話を取得しようとします。

**ところ**

この問題の回避策はありません。 保留中の呼び出しは、応答グループに代わって取得する必要があります。

</div>

</div>

<span id="TopoBuilder"></span>

<div>

## <a name="lync-server-control-panel-topology-builder-and-planning-tool"></a>Lync Server コントロール パネル、トポロジ ビルダー、および計画ツール

<div>

## <a name="planning-tool-limitations"></a>計画ツールの制限

<div class="">


> [!NOTE]  
> このセクションの情報は Lync Server 2013 の累積的な更新プログラム: 2013 年 2 月に関係します。



</div>

**点**

展開を計画する場合、計画ツールには次の制限があります。

  - サポートされる最大10個のセントラルサイトがあります

  - 各セントラルサイトは、最大で14個のブランチサイトを持つことができます。

  - 各セントラルサイトには、最大24万ユーザーを含めることができます。

また、推奨されるトポロジを計算するときに、計画ツールには次の値は含まれません。

  - オンラインになっているユーザーの数

  - XMPP フェデレーションが有効になっているユーザーのパーセンテージ

  - Lync Web App を使用しているユーザーのパーセンテージ

**ところ**

この問題の回避策はありません。 計画ツールの詳細については、「[計画ツールを使用して Lync Server 2013 のトポロジを設計](lync-server-2013-designing-the-topology-by-using-the-planning-tool.md)する」を参照してください。

</div>

<div>

## <a name="planning-tool-may-not-use-previously-defined-ip-addresses-for-the-edge-network-when-updating-options"></a>オプションを更新するときに、計画ツールで、エッジネットワークに事前に定義された IP アドレスを使用できない場合がある

**点**

計画ツールを使用して設計を完了した後、エッジネットワークのオプションを変更すると、既存の IP アドレスを更新する代わりに、追加の IP アドレスを設計に追加することができます。 この問題は、Edge ネットワーク図の詳細を表示しているときに、[**ここをクリックしてオプションを更新する**] を選択し、[構成オプション] ダイアログで、[edge ネットワーク] を選択します。 [**同じ fqdn と IP アドレスを使用しますが、エッジサーバー上のエッジサービスには異なるポートを使用**します] を選びます。 変更を適用すると、新しい IP アドレスとエッジサーバーがデザインに追加されることがあります。

**ところ**

現時点では、この問題の回避策はありません。

</div>

<div>

## <a name="in-lync-server-control-panel-move-all-users-to-pool-may-not-work-as-expected"></a>Lync Server コントロールパネルの [すべてのユーザーをプールに移動] が期待どおりに動作しない場合がある

**点**

Lync Server コントロールパネルを使用して、1つのプールから、複数のドメインコントローラーと親/子ドメインを含む複雑な Active Directory 環境内の別のプールにすべてのユーザーを移動する場合、エラーメッセージが表示されることがあります。 "指定されたユーザーはレガシユーザーではありません。" これは、複雑な Active Directory 環境でのレプリケーション時間が長くなったためです。

**ところ**

この問題を回避するには、次のいずれかの操作を行います。

  - Lync Server コントロールパネルで [フィルター] を使用して、従来のユーザーを検索し、それらのユーザーを選択して、[**すべてのユーザーをプールに**移動] ではなく、[**選択したユーザーをプールに移動] コマンド**を使用します。

  - Lync server 管理シェルを使用して、Lync Server コマンドレットを使用して、従来のユーザーをまとめて移動します。

</div>

<div>

## <a name="the-lync-server-control-panel-stops-working-in-a-vmware-environment-after-the-microsoft-silverlight-browser-plug-in-is-updated-to-version-5"></a>Microsoft Silverlight ブラウザープラグインをバージョン5に更新した後に、Lync Server コントロールパネルが VMware 環境で動作を停止する

**点**

VMware 環境で Lync Server コントロールパネルを使用すると、Silverlight をバージョン5にアップグレードした後に Lync Server コントロールパネルが機能しなくなることがあります。

**ところ**

この問題を回避するには、次のいずれかの操作を行います。

  - Silverlight 5 をアンインストールしてから、Silverlight 4 [https://go.microsoft.com/fwlink/p/?LinkID=149156\&v=4.0](https://go.microsoft.com/fwlink/p/?linkid=149156%26v=4.0)をからインストールします。

  - Lync Server コントロールパネルを、VMware 仮想コンピューターではないコンピューターから開きます。
    
    リモートコンピューターから Lync Server コントロールパネルを開くには、コンピューターに Lync Server 管理ツールをインストールして、Windows の [**スタート**] メニューから Lync Server コントロールパネルを起動します。
    
    Web ブラウザーで URL を入力して、Lync Server コントロールパネルを開くこともできます。 この URL\<は https://フロントエンド\_プール\_の fqdn\>に似ています/cscp.

</div>

<div>

## <a name="an-administrator-cannot-run-the-uninstall-csmirrordb-cmdlet-after-removing-the-mirroring-database-in-topology-builder"></a>トポロジビルダーでミラーリングデータベースを削除した後に、管理者がアンインストール-csMirrorDB コマンドレットを実行できない

**点**

管理者がトポロジビルダーでミラーリングデータベースを無効にして、トポロジビルダーでミラーリングデータベースを削除すると、管理者が**csMirrorDatabase**コマンドレットを実行して SQL Server からミラーリングを削除するようにメッセージが表示されます。 管理者がコマンドレットを実行しようとすると、失敗します。

**ところ**

トポロジビルダーでプールの SQL ミラーリングを削除するには、最初にコマンドレットを使用して、SQL Server のミラーを削除する必要があります。 次に、トポロジ ビルダーを使用して、トポロジからミラーを削除できます。 SQL Server でミラーを削除するには、次のコマンドレットを使用します。

    Uninstall-CsMirrorDatabase -SqlServerFqdn <SQLServer FQDN> [-SqlInstanceName <SQLServer instance name>] -DatabaseType <Application | Archiving | CentralMgmt | Monitoring | User | BIStaging | PersistentChat | PersistentChatCompliance> [-DropExistingDatabasesOnMirror] [-Verbose]

たとえば、ミラーリングを削除してユーザーデータベースのデータベースをドロップするには、次のように入力します。

    Uninstall-CsMirrorDatabase -SqlServerFqdn primaryBE.contoso.com -SqlInstanceName rtc -Verbose -DatabaseType User -DropExistingDatabasesOnMirror

*Dropexistingdatabases Onmirror*パラメーターを使うと、影響を受けたデータベースがミラーから削除されます。 その後、トポロジからミラーを削除するために次の操作を行います。

1.  トポロジ ビルダーで、プールを右クリックし、[**プロパティの編集**] をクリックします。

2.  [ **SQL ストアミラーリングを有効にする**] をオフにし、[ **OK]** をクリックします。

3.  トポロジを公開します。

<div class="">


> [!IMPORTANT]  
> バックエンドデータベースミラーリングの関係を変更する場合は、必ずプール内のすべてのフロントエンドサーバーを再起動する必要があります。



</div>

</div>

<div>

## <a name="validation-errors-are-returned-in-topology-builder-when-an-administrator-attempts-to-remove-a-deployment-with-a-front-end-pool-that-has-an-associated-witness-store"></a>管理者が、関連付けられている監視ストアを持つフロントエンドプールを使用して展開を削除しようとすると、検証エラーがトポロジビルダーで返される

**点**

管理者が、関連付けられている監視ストアでフロントエンドプールを含む展開を削除するために、管理者がトポロジビルダーで [**展開の削除**] を使用しようとした場合、トポロジビルダーに検証エラーが表示され、操作は続行されません。

**ところ**

この問題を回避するには、次のいずれかの操作を行います。

  - 展開を削除する前に、監視ストアを削除します。

  - フロントエンドプールの監視ストアを追加してから、削除します。

</div>

<div>

## <a name="persistent-chat-server-deployment-information-is-inconsistent-between-the-planning-tool-and-topology-builder"></a>計画ツールとトポロジビルダーとの間の常設チャットサーバーの展開情報に一貫性がない

**点**

Lync Server 2013 の計画ツールで、障害回復が有効になっている常設チャットサーバーの展開用のサイトトポロジ図を出力すると、サイトトポロジ図には複数の (物理) サイトが含まれており、それぞれに常設チャットサーバーが均等に割り当てられています。サービス. Topology Builder では、すべての常設チャットサーバーは1つの (論理) サイトに属しているものとして表され、同じ常設チャットサーバープールノードの下に表示されます。

**ところ**

現時点では、この問題の回避策はありません。 ユーザーは、常設チャットサーバー展開の計画ツールの出力を分析し、特定のニーズに合わせてプランを変更する必要があります。

</div>

</div>

<span id="Localization"></span>

<div>

## <a name="localization"></a>版

<div>

## <a name="monitoring"></a>監視

<div>

## <a name="the-deploy-monitoring-reports-wizard-displays-incorrect-characters-under-certain-circumstances-when-using-the-east-asian-version-of-lync-server"></a>東アジアバージョンの Lync Server を使用すると、監視レポートの展開ウィザードで特定の状況で誤った文字が表示される

**点**

東アジアバージョンの Lync Server 2013 (中国語 (簡体字)、中国語 (繁体字)、日本語、韓国語など) を使用している場合、システムロケールが東アジア言語に設定されていないオペレーティングシステムでは、[監視レポートの展開] ウィザードが表示されます。ローカライズされたメッセージではなく、疑問符などの文字を表示します。

**ところ**

この問題を解決するには、オペレーティングシステムと Lync Server 2013 のロケールを同じ言語に設定します。これにより、すべてのメッセージが正しく表示されます。

</div>

</div>

<div>

## <a name="lync-server-control-panel"></a>Lync Server コントロール パネル

<div>

## <a name="in-certain-cases-the-first-item-in-the-top-navigation-bar-on-a-page-of-lync-server-control-panel-disappears-when-the-last-item-in-the-top-navigation-bar-is-clicked"></a>特定の状況では、トップナビゲーションバーの最後のアイテムがクリックされると、Lync Server コントロールパネルのページ上のトップナビゲーションバーの最初のアイテムが表示されなくなります。

**点**

Lync Server コントロールパネルのページの上部にあるナビゲーションバーで最後のアイテムをクリックすると、トップナビゲーションバーの最初のアイテムが非表示になるという3つの既知の場合があります。

  - フランス語版のページ "Féderation et accès externe" で、"Partenaires d'accès XMPP" がクリックされると、"項目" Stratégie externe fédérés "が表示されなくなります。

  - ドイツ語版の [クライアント] ページで、"Pushbenachrichtigungskonfiguration" がクリックされると、"Clientversionskonfiguration" 項目が表示されなくなります。

  - ロシア語版の "Конфигурациясети" ページでは、"Маршрутрегиона" がクリックされると、項目 "Глобально" が表示されなくなります。

**ところ**

この問題を回避するには、ブラウザーで Lync Server コントロールパネルのページを更新します。 ページは、上部のナビゲーションバーに表示されているすべてのアイテムと共にブラウザーに読み込まれます。

</div>

</div>

<div>

## <a name="address-book"></a>アドレス帳

<div>

## <a name="indexing-in-the-address-book-does-not-work-as-expected-in-some-languages"></a>一部の言語で、アドレス帳のインデックス処理が予期したとおりに機能しない

<div class="">


> [!NOTE]  
> このセクションの情報は Lync Server 2013 の累積的な更新プログラム: 2013 年 2 月に関係します。



</div>

ユーザーのプロパティにインデックス付きフィールドが含まれており、そのフィールドにインデックスを作成できない文字しか含まれていない場合、そのユーザーはアドレス帳で実行された検索には表示されません。

次の文字とロケールのインデックスを作成することはできません。

  - 大文字のキリル文字、ギリシャ文字、およびアルメニア文字

  - 大文字アクセント記号付き文字

  - タイ語

  - ラオス

  - ビルマ

  - バナー

  - 語

  - 語

  - ベンガル語

  - グジャラート語

  - テルグ語

  - その他のすべてのインド系言語スクリプト

</div>

</div>

<div>

## <a name="lync-web-app-web-scheduler-and-web-components"></a>Lync Web App、Web Scheduler、Web コンポーネント

<div>

## <a name="language-fallback-for-certain-languages-in-lync-web-scheduler-dial-in-join-launcher-persistent-chat-room-management-and-octab-might-not-work-as-expected"></a>Lync Web Scheduler、ダイヤルイン、参加起動ツール、常設チャットルーム管理、および OCTab の一部の言語の言語のフォールバックは、期待どおりに動作しないことがあります。

**点**

Web ブラウザーでニュートラルロケールを選択する場合 (Internet Explorer の場合) たとえば、言語、スクリプト、ロケール ("ノルウェー語、 \[ブークモール\](ノルウェー語) \[nb-いいえ\]" など) を指定しない言語名は、Lync Web Scheduler、ダイヤルイン、参加起動ツール、常設チャットルーム管理、および octab の特定の言語に対して予期しない表示動作を引き起こす可能性があります。 たとえば、次のいずれかの言語が選択されている場合、ユーザーに英語のページが表示されることがあります。

  - ノルウェー語

  - ポルトガル語

  - セルビア語

**ところ**

ニュートラルロケールの言語を選択する場合は、ブラウザーの [言語設定] ボックスの一覧で、特定のロケール (スクリプトおよび国コードを含む) の言語も追加であることを必ず確認してください。

</div>

<div>

## <a name="there-is-limited-support-for-azeri-and-uzbek-locales-when-using-lync-web-scheduler-dial-in-join-launcher-persistent-chat-room-management-and-octab-in-some-web-browsers"></a>Lync Web Scheduler、ダイヤルイン、参加起動ツール、常設チャットルーム管理、および一部の Web ブラウザーでの OCTab を使用している場合、アゼルバイジャン語とウズベク語のサポートは制限されています。

<div class="">


> [!NOTE]  
> このセクションの情報は Lync Server 2013 の累積的な更新プログラム: 2013 年 2 月に関係します。



</div>

**点**

Internet Explorer 8 または Internet Explorer 9 を使用して、ブラウザーの言語をアゼルバイジャン語 (ラテン) またはウズベク語 (ラテン) に設定すると、ダイヤルインと参加起動ツールのページは、英語またはブラウザーで設定した言語で表示されます。

Firefox または Chrome ブラウザーを使用しているときに、ブラウザーの言語を [アゼルバイジャン (ラテン)] または [ウズベク語 (ラテン)] に設定すると、Lync Web App、Lync Web Scheduler、および RGS OCTab が、英語で表示されるか、ブラウザーの優先言語セットとして表示されます。

Safari ブラウザーでは、ウズベク語 (ラテン) ロケールはサポートされていません。

**ところ**

この問題の回避策はありません。

</div>

</div>

<div>

## <a name="the-drop-down-arrow-is-missing-for-join-meeting-from-list-in-the-romanian-version-of-lync-web-app"></a>ルーマニア語版の Lync Web App の [会議に参加する] リストのドロップダウン矢印が表示されない

**点**

ルーマニア語版の Lync Web App を使用しているユーザーが次の手順を実行すると、ドロップダウンリストに**会議に参加**するためのドロップダウン矢印が表示されません。

1.  [**全般**] タブの [**このコンピューター上でパスワードを記憶**する] を選択します。

2.  [**電話**] タブを選択します。

3.  [**会議に参加**する] のドロップダウンリストをクリックします。
    
    ユーザーには、既定の**Lync Web App**よりも多くのオプションが含まれていることを示す矢印が表示されません。これには、**オーディオに参加しない**(ルーマニア語、"ニュー se asociaža la componenta Audio") と**新しい番号**"(ルーマニア語で" Număr nou ") が含まれます。

**ところ**

このドロップダウンリストの矢印が表示されていない場合でも、ユーザーは既定値をクリックして、リスト内の追加の設定を選ぶことができます。

</div>

<div>

## <a name="when-using-the-turkish-version-of-lync-web-scheduler-a-meeting-cannot-be-saved-when-using-the-people-i-choose-option-under-who-is-a-presenter"></a>トルコ語版の Lync Web Scheduler を使用している場合、[発表者になる人] の下にある [選択したユーザー] オプションを使用すると、会議を保存できません。

**点**

トルコ語版の Lync Web Scheduler で会議を作成または編集している場合、[発表者になるユーザー] の下の [選択したユーザー] オプションはサポートされません。 このオプションが選択されている場合、会議を保存することはできません。 代わりに、1人以上のユーザーが発表者を作成できないことを示すエラーメッセージが表示されます。

**ところ**

この問題を回避するために、ユーザーは、"社内のユーザー" の既定のオプション、または [開催者のみ] や [社外のユーザーを含むすべてのユーザー] などの任意の選択肢を使用できます。 開催者は、会議に参加した後で、後でユーザーを適切なロールに降格または昇格させることができます。

または、別の言語を理解しているユーザーは、ブラウザーでの言語の選択を、サポートされている他の43言語のいずれかに変更して、[選択したユーザー] オプションを使用しようとすることができます。

</div>

</div>

<span id="Copyright"></span>

<div>

## <a name="copyright"></a>著作

このドキュメントでは、最終的な商用リリースの前に実質的に変更される可能性があるソフトウェア製品の暫定的なリリースをサポートしています。また、Microsoft Corporation の機密情報でもあります。 この情報は、受信者と Microsoft との間の非開示契約に基づいて公開されます。 このドキュメントは、情報提供のみを目的として提供されています。このドキュメントでは、Microsoft は明示または黙示のいずれの保証も行いません。 このドキュメントに記載されている情報 (URL などのインターネット web サイトへの参照を含む) は、予告なしに変更される可能性があります。 このドキュメントの使用、またはこのドキュメントの使用による結果のすべてのリスクは、ユーザーに残ります。 特に記載がない限り、ここに記載されている会社、組織、製品、ドメイン名、メールアドレス、ロゴ、人物、場所、およびイベントは架空のものです。 実際の会社、組織、製品、ドメイン名、メールアドレス、ロゴ、人物、場所、またはイベントに関連するものではありません。 すべての該当する著作権法を遵守することは、ユーザーにとっての責任となります。 著作権の下にある権利を制限することなく、このドキュメントの一部は、どの形式または任意の形態 (電子的、機械的、複写、レコーディングなど) またはその他の手段 (電子的、機械、複写、記録など) でも、または送信される可能性があります。Microsoft Corporation の書面による明示的な許可がない場合。

Microsoft には、このドキュメントの内容について、特許、特許申請、商標、著作権、またはその他の知的財産権が含まれている場合があります。 Microsoft の書面によるライセンス契約で明示的に記載されている場合を除き、このドキュメントの提供により、これらの特許、商標、著作権、またはその他の知的財産権の許諾を得ることはできません。

© 2012 Microsoft Corporation。 All rights reserved.

Microsoft、Windows、Windows Live、Active Directory、Internet Explorer、MSN、Outlook、および SQL Server は、米国およびその他の国/地域で、Microsoft Corporation の登録商標または商標です。

その他のすべての商標は、各所有者の財産権を持っています。

</div>

</div>

<span> </span>

</div>

</div>

</div>

