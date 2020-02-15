---
title: Lync Server 2013 リリースノート
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
ms.openlocfilehash: cc7339b4861fe6e7e93e08d4928f6128916aeea0
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42048798"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="release-notes-for-lync-server-2013"></a>Lync Server 2013 のリリースノート

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2016-12-08_

Lync Server 2013 リリースノートへようこそ。 Lync Server 2013 の既知の問題に関する情報については、このファイルを参照してください。

<div>

## <a name="about-this-document"></a>このドキュメントについて

このドキュメントには、Lync Server 2013 を展開して使用する前に知っておく必要がある重要な情報が含まれています。 Lync Server 2013 の詳細については、「 [Microsoft Lync server 2013](microsoft-lync-server-2013.md)のドキュメント」を参照してください。

このドキュメントは、以下のセクションで構成されています。

  - Lync 2013 クライアント

  - Lync Server

  - インストール

  - 身体

  - 会議

  - 用に構成します

  - プレゼンス

  - 応答グループ アプリケーションおよびコール パーク アプリケーション

  - Lync Server コントロール パネル、トポロジ ビルダー、および計画ツール

  - ローカリゼーション

  - 著作権

</div>

<span id="LyncClient"></span>

<div>

## <a name="lync-2013-client"></a>Lync 2013 クライアント

<div>

## <a name="transferring-a-file-in-an-instant-message-fails-if-the-file-is-open-in-another-application"></a>他のアプリケーションでファイルが開かれている場合に、インスタントメッセージでファイルを転送できない

**問題**

他の Lync ユーザーにインスタントメッセージでファイルを含めることによって、Word 文書などのファイルを転送しようとすると、転送は成功したように見えますが、実際にファイルの転送に失敗する可能性があります。 ファイルの種類のアイコンは Lync クライアントに表示されますが、目的の受信者はそのファイルを開くことができません。 転送が成功しなかったことを通知するエラーメッセージは表示されません。

**回避策**

この問題を回避するには、インスタントメッセージでファイルを転送する前に、開いているファイルまたはアプリケーションを閉じてください。

</div>

</div>

<span id="LyncServer"></span>

<div>

## <a name="lync-server"></a>Lync Server

<div>

## <a name="if-lync-server-storage-service-data-replication-fails-administrators-will-need-to-check-performance-counters-for-stale-storage-service-queue-items"></a>Lync Server ストレージサービスのデータレプリケーションが失敗した場合、管理者は古いストレージサービスキューアイテムのパフォーマンスカウンターをチェックする必要があります。

**問題**

Lync Server ストレージサービスは、レプリケーションに Windows Fabric を使用します。 プライマリフロントエンドサーバーでデータが削除されたが、セカンダリフロントエンドサーバーの削除が失敗した場合 (たとえば、フロントエンドサーバーに予期しないシャットダウンやエラーが発生した場合)、データは残され、"孤立" することがあります。 孤立したデータを使用すると、パフォーマンスが低下し、ドライブ領域が浪費されることがあります。

**回避策**

この問題を回避するには、イベントログに\_"\_イベント\_を\_指定してください" というイベント (\_id\_=\_32058\_) と、その後に重大な (id = 32059) を使用していたデータベーススペースがイベントログに生成されている場合、管理者は、「 **** **LS:** log service API」の下にあるフロントエンドサーバーのパフォーマンスカウンターを このパフォーマンスカウンターに大きな値がある場合 (たとえば、50000より大きい場合)、管理者は Lync Server 2013 リソースキットの CleanuUpStorageServiceData ツールを実行して、孤立したすべてのデータをプールから削除します。 このツールの詳細については、Lync Server 2013 リソースキットのドキュメントを参照してください。

</div>

<div>

## <a name="whenever-the-ip-address-configuration-is-changed-for-a-server-or-pool-lync-server-services-need-to-be-restarted"></a>サーバーまたはプールの IP アドレス構成が変更された場合は、Lync Server サービスを再起動する必要があります。

**問題**

Lync Server 2013 の展開に対して IP アドレス構成が変更された場合 (IPv4 からデュアルスタックへの変更、デュアルスタックから Ipv6 への変更など)、すべてのサーバーコンポーネントは、サービスが再起動されるまで構成変更を選択しません。

**回避策**

この問題を回避するには、展開の IP アドレス構成を変更した後に Lync Server サービスを再起動します。 これを行うには、Lync Server 管理シェルで次のコマンドレットを実行します。

   ```PowerShell
    Stop-CsWindowsService -graceful
   ```

   ```PowerShell
    Start-CsWindowsService
   ```

</div>

<div>

## <a name="the-dial-in-conferencing-synthetic-transaction-cmdlet-is-no-longer-available-in-the-lync-server-2013-management-pack"></a>ダイヤルイン会議代理トランザクションコマンドレットは、Lync Server 2013 管理パックでは使用できなくなりました。

**問題**

ダイヤルイン会議代理トランザクションコマンドレット**Test-csdial In会議**は、Lync Server 2013 管理パックでは使用できなくなりました。

**回避策**

ダイヤルイン会議代理トランザクションコマンドレットの使用**テスト-Csdial Inコンファレンス**は、社内のみでサポートされています。

管理者は、トラブルシューティングの目的で、Lync Server 管理シェルのコマンドレットを引き続き使用できます。 必要に応じて、エンタープライズは、コマンドレットを内部的に実行するためのプライベート管理パックを開発することもできます。

</div>

<div>

## <a name="the-centralized-logging-service-stops-if-network-traffic-is-disrupted-when-log-files-are-being-copied-to-network-share"></a>ログファイルがネットワーク共有にコピーされているときにネットワークトラフィックが中断された場合、集中ログサービスは停止します。

**問題**

集中ログサービスがネットワークパスを使用するように構成さ**れている**場合 (CacheFileNetworkFolder パラメーターの値が有効な UNC パスである)、キャッシュされたログファイルはネットワーク共有にコピーされます。 ファイルのコピー中にネットワークトラフィックで中断が発生すると、集中ログサービスが停止する例外が発生します。

サービスは、3回まで自動的に再起動するように構成されているため、最初の3つの例外から回復します。

**回避策**

この問題の回避策はありません。 この問題を特定するには、"Lync Server 集中ログサービスエージェント" サービスが予期せず終了したときにログに記録されるイベント ID 7031 のイベントログを監視します。 これが3回を超えて発生する場合は、 **Start-CsWindowService**コマンドレットを使用して、サービスを手動で再起動します。

</div>

<div>

## <a name="storage-service-queue-items-need-to-be-imported-manually"></a>ストレージサービスキューアイテムを手動でインポートする必要がある

**問題**

Lync Server 2013 は、アーカイブされたメッセージ、通話詳細記録 (CDR) などの会議やインスタントメッセージングに関するデータを、各フロントエンドサーバー上のデータベースに格納します。 データは、目的の宛先に配信される前に処理されている間、データベースに格納されます。 パフォーマンスを向上させるために、Lync Server 2013 は定期的に処理されないローカルデータベースからキューアイテムをエクスポートし、それをファイルストアに保存します。 ファイルストアが使用できない場合、アイテムは各フロントエンドサーバーに保存されます。 プールフェールオーバー中のデータ損失を防止するために同じ操作が発生します。

エクスポート操作の間に、Lync Server Storage サービスは、イベント Id 32075 のイベント Id (完全なフラッシュ操作が開始されます)、32076 (完全フラッシュを完了)、32082 (メンテナンスレベルのフラッシュが開始)、32083 (メンテナンスレベルのフラッシュ) を使用して、すべてのステージをイベントログに記録します。完了)、32089 (データベースの容量がいっぱいになったため、フラッシュが発生しました)。 このデータは、処理されて最終的な宛先 (SQL Server または Exchange Server) に配信されるように、システムに自動的にインポートされることはありません。

**回避策**

システムにデータをインポートするには、管理者は Lync Server リソースキットの ImportStorageServiceData ツールを使用する必要があります。これにより、データがシステムに追加され、処理されて最終的な送信先に配信されます。

</div>

<div>

## <a name="address-book-web-query-searches-will-fail-if-the-default-value-for-usenormalizationrules-is-changed-to-false"></a>UseNormalizationRules の既定値を False に変更すると、アドレス帳 Web クエリの検索が失敗する

**問題**

UseNormalizationRules の既定値を False に変更すると、アドレス帳の Web クエリ検索は失敗します。 既定値が変更されると、Lync クライアントユーザーは Lync アドレス帳 web クエリを使用してユーザーを検索することができなくなります。

**回避策**

UseNormalizationRules の既定値が False に設定されている場合、ユーザーは、Active Directory ドメインサービスで定義されている電話番号を、Lync Server 2013 を使用せずに使用することができます。正規化ルールを適用するには、次の手順を実行してこの問題を回避します。

1.  Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。

2.  次のいずれかの操作を行います。
    
      - 展開に Lync Server 2013 サーバーのみが含まれている場合は、グローバルレベルで次のコマンドレットを実行して、UseNormalizationRules および IgnoreGenericRules の値を True に変更します。
        
            Set-CsAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true
    
      - 展開に Lync Server 2013 と Lync Server 2010 または Office Communications Server 2007 R2 の組み合わせが含まれている場合は、次のコマンドレットを実行して、トポロジ内の各 Lync Server 2013 プールに割り当てます。
        
            new-csAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true

3.  すべてのプールで CMS レプリケーションが行われるのを待ちます。

4.  展開用の電話正規化ルールファイルを変更して、コンテンツをクリアします。 ファイルは、各 Lync Server 2013 プールのファイル共有にあります。 ファイルが\_存在しない場合は、「会社の電話\_番号\_の正規化\_ルール .txt」という名前の空のファイルを作成します。

5.  すべてのフロントエンドプールが新しいファイルを読み取るまで数分待機します。

6.  展開内の各 Lync Server 2013 プールで、次のコマンドレットを実行します。
    
        Update-csAddressBook

</div>

<div>

## <a name="address-book-server-error-event-21054-is-generated-once-daily-for-each-lync-2013-pool"></a>Lync 2013 プールごとに1日1回アドレス帳サーバーエラーイベント21054が生成される

**問題**

Lync Server 2013 アドレス帳サーバーでは、毎日のメンテナンスの実行時に、毎日1回エラーイベント21054が生成されます。 また、更新が成功した場合でも、管理者が**update-csaddressbook**コマンドレットを実行するたびに、このエラーが生成されます。 ただし、更新が成功した場合、このエラーイベントは無視しても問題ありません。

**回避策**

このエラーイベントが発生した場合は、次のコマンドレットを実行します。

    Debug-csAddressBookReplication -Poolfqdn <Pool FQDN for which the event was generated>

コマンドレットで、インデックスが設定されていないオブジェクトまたは破棄されたオブジェクトがないことを報告した場合は、エラーイベント21054を無視しても問題ありません。

また、System Center Operations Manager では、キー正常性インジケーター (KHI) "アドレス帳ユーザーが正しくインデックス処理されています" がオフになっている必要があります。

</div>

<div>

## <a name="requests-may-fail-when-ipv6-is-configured-on-an-edge-pool"></a>エッジプールで IPv6 が構成されていると、要求が失敗する場合がある

**問題**

エッジプールで IPv6 が構成されている場合、エッジプールへの要求が失敗することがあります。

**回避策**

この問題を回避するには、エッジプールを IPv6 で構成しないようにします。

</div>

<div>

## <a name="the-invoke-cspoolfailback-cmdlet-may-fail-during-pool-failback"></a>プールのフェールバック時に Invoke-cspoolfailback コマンドレットが失敗する場合がある

**問題**

プールのフェールバックを試行すると、 **invoke-cspoolfailback**コマンドレットがエラーで失敗することがあります。 "繰り返し試行が行われた後、ハイドロプロセスを完了できませんでした。"

**回避策**

この問題を回避するには、もう一度コマンドレットを実行して、コマンドレットが正常に終了するまで待機します。 フェールバックプロセスが完了するまでに数分かかる場合があることに注意してください。 プールが2万ユーザーの場合、最大60分かかる場合があります。

</div>

<div>

## <a name="data-loss-may-occur-when-you-add-a-front-end-server-to-an-already-established-pool--hybrid-skype-for-business-online"></a>既に確立されているプール (ハイブリッド、Skype for Business Online) にフロントエンドサーバーを追加するとデータが失われることがある

**問題**

プールに複数のフロントエンドサーバーがある環境でこの問題が発生する場合があります。または、フロントエンドサーバーの1つを再起動するか、プールの一部ではない新しいフロントエンドサーバーを追加します。

データがアーカイブされているユーザーは、プールに対して安定したデータアーカイブの配布が確立されるまで、データの損失が発生する可能性があります。 このようなデータ損失が発生する可能性がある期間は、人間会話の場合は15分、電話会議の場合は30分に制限されています。

**回避策**

管理を実行するときは、プール内のフロントエンドサーバーを1つずつ開始するのではなく、プールを別のプールにフェールオーバーして、サーバー上でメンテナンスタスクを実行する必要があります。 メンテナンスタスクを実行する前にサービスを利用できないようにし、メンテナンスが完了したら可用性を復元することもできます。

</div>

<div>

## <a name="administrators-cannot-get-licensee-count-by-using-the-get-csclientaccesslicense-cmdlet"></a>管理者は、Get-help を使用してライセンス認証の数を取得することはできません。

**問題**

管理者は、 **Get-help Clientaccesslicense**コマンドレットを使用して、クライアントライセンスの正確な使用状況を取得できません。

**回避策**

サーバーライセンスの種類を確認するには、 **-CsService**コマンドレットを実行して、すべてのデータベースの完全修飾ドメイン名 (FDQNs) を取得します。 フロントエンドサーバーの FQDN がバックエンドデータベースの FQDN と同じである場合、ライセンスは Standard edition ライセンスです。 それ以外の場合、ライセンスは Enterprise edition ライセンスです。

</div>

<div>

## <a name="client-licensee-count-is-not-accurately-reported"></a>クライアントライセンスの数が正確に報告されない

**問題**

クライアントライセンスの数を決定するときには、次のような状況が発生することがあります。

1.  **モバイルユーザーのライセンス数が正しくない**
    
    ライセンス数は、デバイスベースのユーザーの一意の IP アドレスの数に基づいています。 ライセンス数は、次の方法で制限されます。
    
      - ユーザーの IP アドレスが Lync セッション中に変更されると、ライセンスは過剰にカウントされます。 これは、ユーザーがデスクトップクライアントを使用して複数の場所から Lync Server に接続している場合に発生する可能性があります。
    
      - ユーザーがモバイルクライアントを使用して接続する場合は、デバイスの IP アドレスを特定できないため、ライセンスが過小にカウントされます。

2.  **公衆交換電話網 (PSTN) から Lync クライアントへの通話、Lync クライアントから PSTN 回線への通話、および PSTN 回線に転送された Lync 通話でライセンスが2回カウントされる**
    
    次のシナリオでは、電話番号と Lync ユーザーの両方がカウントされ、使用されているライセンスの数が判別されるため、2つの追加ライセンスは1つではなく、カウントされます。 正確なライセンスデータを取得するには、電話番号によって生成されたライセンスを手動で削除します。
    
      - Lync への PSTN 電話通話
    
      - PSTN 回線への Lync 通話
    
      - Lync への PSTN 通話。 Lync は、通話を PSTN 回線に転送します。 PSTN 回線の1つをカウントします。

3.  **ログオンしている Lync 電話のライセンスがカウントされない**
    
    ユーザーが Lync 認定電話を使用している場合、電話がログインしていて、接続を維持すると、電話がログインした後にライセンスのクエリが発生した場合、その電話はライセンスを使用したものとしてカウントされません。

4.  **電話会議に参加している PSTN 電話に対してカウントされたライセンス**
    
    ユーザーが PSTN 電話機を使用して電話会議に参加すると、電話会議への参加のためのライセンスが不正確にカウントされます。 ただし、PSTN 電話で会議に参加するためにライセンスは必要ありません。

**回避策**

1.  **モバイルユーザーのライセンス数が正しくない**
    
      - 同じデバイスに属する IP アドレスを手動で特定し、そのうちの1つをライセンス数で削除することができます。
    
      - Lync クライアントを使用して接続するモバイルデバイスでこの問題を回避する方法はありません。

2.  **Lync クライアントへの PSTN 通話、Lync クライアントから PSTN 回線への通話、および PSTN 回線に転送された Lync 通話でライセンスが2回カウントされる**
    
    PSTN 電話番号を手動で特定し、その番号に対して生成されたライセンス数を削除する必要があります。

3.  **ログインしている Lync 電話のライセンスがカウントされない**
    
    ユーザーがログオフするように Lync phone を構成し、定期的に (3 か月ごとなど) ログオンし直すことができます。

4.  **電話会議に参加している PSTN 電話に対してカウントされたライセンス**
    
    電話会議への参加に使用される PSTN 電話番号を手動で特定し、その電話番号によって生成されたライセンスを削除することができます。

</div>

<div>

## <a name="the-lync-server-control-panel-stops-working-in-a-vmware-environment-after-upgrading-to-silverlight-5"></a>Lync Server コントロールパネルは、Silverlight 5 へのアップグレード後の VMware 環境での動作を停止します。

**問題**

VMware 環境で Lync Server コントロールパネルを使用すると、Microsoft Silverlight をバージョン5にアップグレードした後、Lync Server コントロールパネルが機能しなくなることがあります。

**回避策**

この問題を回避するには、次のいずれかの操作を行います。

  - Silverlight 5 をアンインストールし、から[https://go.microsoft.com/fwlink/p/?LinkID=149156](https://go.microsoft.com/fwlink/p/?linkid=149156)silverlight 4 をインストールします。

  - VMware 仮想コンピューターではないコンピューターから Lync Server コントロールパネルにアクセスします。
    
    そのためには、lync Server 管理ツールがコンピューターにインストールされている場合は、サーバーの Windows**スタート**メニューから Lync Server コントロールパネルを起動できます。
    
    Web ブラウザーを使用して Lync Server コントロールパネルにアクセスすることもできます。 この URL\<は https://フロントエンド\_プール\_の fqdn\>に似ています。/cscp.

</div>

<div>

## <a name="user-information-in-the-address-book-service-is-not-updated-after-the-distinguished-name-for-the-user-is-modified-in-active-directory"></a>Active Directory でユーザーの識別名が変更されても、アドレス帳サービスのユーザー情報が更新されない

**問題**

Active Directory ドメインサービスでユーザーの識別名 (DN とも言う) が変更された場合、アドレス帳サービス (ABS) 内の追加の変更は更新されません。 これは、ユーザーのサインインまたはプレゼンスには影響を与えませんが、検索によって古い SIP アドレスが返されるため、SIP アドレスも変更された場合にユーザーの通信ができなくなります。

**回避策**

この問題を回避するには、ユーザーの DN を変更しないようにします。 ユーザーの DN を以前の値に戻すと、アドレス帳サービスに更新が反映されます。

</div>

</div>

<span id="Installation"></span>

<div>

## <a name="installation"></a>インストール

<div>

## <a name="using-non-ascii-characters-may-result-in-lync-server-failing-to-start"></a>非 ASCII 文字を使用すると、Lync server の起動が失敗することがあります。

**問題**

宛先フォルダーの名前に ASCII 以外の文字 (UNICODE、2バイト文字セット (DBCS)、UTF-8、UTF-16 を含む) が含まれている場合、セットアップは失敗します。 さらに、セットアップは成功する可能性がありますが、次のいずれかに ASCII 以外の文字が含まれていると、サーバーは起動しません。

  - コンピューター名

  - ドメイン名

  - ユーザー名

  - ユーザー SIP URI

  - サービスアカウント名

**回避策**

移動先のフォルダー名、コンピューター名、ドメイン名、ユーザー名、ユーザーの SIP URI、およびサービスアカウント名には ASCII 文字のみを使用します。

</div>

<div>

## <a name="the-hotfix-for-heap-corruption-occurs-when-a-module-calls-the-insertentitybody-method-in-iis-75-must-be-installed-prior-to-installing-lync-server-2013"></a>"ヒープの破損" という修正プログラムは、Lync Server 2013 をインストールする前に、モジュールが InsertEntityBody メソッドを IIS 7.5 で呼び出したときに発生します。

**問題**

「モジュールが IIS 7.5 で InsertEntityBody メソッドを呼び出すときに発生するヒープの破損」 ([https://go.microsoft.com/fwlink/p/?LinkId=268602](https://go.microsoft.com/fwlink/p/?linkid=268602)) については、「Microsoft サポート技術[https://go.microsoft.com/fwlink/p/?LinkId=268603](https://go.microsoft.com/fwlink/p/?linkid=268603)情報の記事 264886 ()」を参照してください。 Lync Server 2013 をインストールする前に、をインストールする必要があります。

**回避策**

「Microsoft ダウンロードセンター」から修正プログラムをダウンロードし[https://go.microsoft.com/fwlink/p/?LinkId=268602](https://go.microsoft.com/fwlink/p/?linkid=268602)てインストールします。

</div>

<div>

## <a name="lync-server-2013-fails-to-install-on-ita-windows-server-2012-os-rtm-version"></a>Lync Server 2013 のインストールが ITA Windows Server 2012 OS RTM バージョンに失敗する

**問題**

Windows Fabric のインストールに失敗したため、ITA Windows Server 2012 で Lync Server 2013 のインストールが失敗します。

Fabric トレースは、時間形式 HH: MM: SS で作成されるため、Windows Fabric のインストールに失敗します。 ただし、ITA Windows Server では、時間の形式は HH です。MM.SS。

**回避策**

この問題を回避するには、Lync Server 2013 をインストールする前に、システムレジストリを更新します。 更新する必要のあるレジストリキーは次のとおり\_です\\。 HKEY ユーザー。既定\\のコントロール\\パネル\\インターナショナルの形式。 Windows PowerShell コマンドラインインターフェイスを使用して、次に示すように、[形式] の値を HH: mm: ss に変更します。

1.  Windows PowerShell を起動し、次のコマンドレットを実行します。
    
       ```PowerShell
        New-PSDrive -Name HKU -PSProvider Registry -Root HKEY_USERS
       ```
    
       ```PowerShell
        $a="HKU:\.Default\Control Panel\International"
       ```

2.  現在の値を表示するには、次のコマンドレットを実行します。
    
        Get-itemproperty $a -Name sTimeFormat
    
    インストールの完了後に復元できるように、このプロパティの現在の値をメモしておいてください。

3.  新しい値を設定するには、次のコマンドレットを実行します。
    
        Set-ItemProperty $a -Name sTimeFormat -Value "HH:mm:ss"

4.  Lync Server 2013 が正常にインストールされた後、次のコマンドレットを実行して、この形式の元の値を復元します。
    
        - ItemProperty $a-Name の場合は、手順3でメモした値の <します。 上記の> "

</div>

</div>

<span id="Mobility"></span>

<div>

## <a name="mobility"></a>身体

<div>

## <a name="issues-for-mobile-clients-during-the-server-failover-process"></a>サーバーフェールオーバープロセス中のモバイルクライアントの問題

**問題**

Lync Server に障害が発生し、フェールオーバープロセスが開始されると、次の問題がモバイルクライアントユーザーに影響を与える可能性があります。

  - フェールオーバーの開始から最大10分間、Lync 通話または着信通知がありません。

  - 着信チャット要求を受け入れることができない

  - 障害が発生したサーバーがユーザーのホームサーバーの場合、会議に参加できない

**回避策**

この問題の回避策はありません。 フェールオーバープロセスが完了すると、通常の機能が復元されます。

</div>

<div>

## <a name="if-a-mobile-user-declines-an-incoming-call-from-another-lync-endpoint-the-call-is-displayed-as-a-missed-conversion-on-lync-mobile-clients"></a>モバイルユーザーが別の Lync エンドポイントからの着信呼び出しを拒否した場合、その通話は Lync Mobile クライアントに不在時の変換として表示されます。

**問題**

モバイルユーザーが着信呼び出しを拒否し、別の Lync エンドポイントから発信された通話は、デバイス呼び出しリストの呼び出しではなく、Lync Mobile クライアントで不在着信として表示されます。

**回避策**

この問題の回避策はありません。

</div>

<div>

## <a name="the-mobile-client-may-not-display-a-federated-contacts-display-name-when-searching-for-contacts"></a>モバイルクライアントが連絡先を検索するときに、フェデレーションの連絡先の表示名が表示されない場合がある

**問題**

フェデレーション連絡先の表示名は、連絡先リストでフェデレーション連絡先を検索する場合など、一部のシナリオでは表示されない場合があります。 これは、Lync mobile クライアントからの連絡先に対してアクティブなプレゼンスサブスクリプションが存在しない場合に発生する可能性があります。

**回避策**

この問題の回避策はありません。

</div>

<div>

## <a name="in-the-mobile-client-invitee-and-timestamp-information-are-missing-from-a-missed-conversation-that-is-an-invitation-to-a-conference"></a>モバイルクライアントでは、会議への招待である不在着信した会話から招待者とタイムスタンプ情報が欠落しています。

**問題**

モバイルクライアントでは、不在着信した会話が会議への招待である場合、不在着信した会話メッセージに招待者とタイムスタンプ情報が含まれていません。

**回避策**

この問題の回避策はありません。

</div>

<div>

## <a name="mobile-client-users-making-calls-using-voip-are-not-be-able-to-leave-voice-mail-for-users-whose-voice-mail-is-configured-in-exchange-2010-or-earlier-versions"></a>VoIP を使用して通話を行うモバイルクライアントユーザーは、Exchange 2010 またはそれ以前のバージョンでボイスメールが構成されているユーザーにボイスメールを残すことができません。

**問題**

モバイルクライアントユーザーが VoIP を使用して通話を発信している場合、ユーザーは、Microsoft Exchange Server 2007 または Microsoft Exchange Server 2010 でボイスメールを使用するように構成されたユーザーにボイスメールメッセージを残すことはできません。

**回避策**

この問題を回避するには、Exchange 2010 SP1 以降のバージョンの Microsoft Exchange Server を使用します。

</div>

<div>

## <a name="when-using-block-with-url-for-client-version-configuration-on-mobile-clients-an-incorrect-error-message-may-be-displayed"></a>モバイルクライアントでクライアントバージョン構成に URL を指定して Block を使用すると、正しくないエラーメッセージが表示される場合があります。

**問題**

モバイルクライアントでクライアントバージョン構成に**URL を**指定したブロックを使用する場合、クライアントバージョンがサポートされていないと、正しくないエラーメッセージが表示されることがあります。

**回避策**

この問題を回避するには、 **URL を使用して block**ではなく**ブロック**を使用するようにクライアントバージョン構成を構成します。

</div>

</div>

<span id="Conferencing"></span>

<div>

## <a name="conferencing"></a>会議

<div>

## <a name="antivirus-software-running-on-lync-server-2013front-end-servers-can-cause-application-domain-recycling-which-temporarily-interrupts-service-for-lync-web-app-2013-lync-mobile-2010-and-lync-mobile-2013-clients"></a>Lync Server 2013 のフロントエンドサーバー上で実行されているウイルス対策ソフトウェアは、アプリケーションドメインのリサイクルを発生させることがあります。これにより、Lync Web App 2013、Lync Mobile 2010、Lync Mobile 2013 クライアントのサービスが一時的に中断されます。

**問題**

ウイルス対策ソフトウェアは、アプリケーションドメインの再起動をトリガーすることができます。これにより、Lync Mobility Service 2013 および統合コミュニケーション (UC) Web API クライアントアプリケーション (Lync Web App 2013、Lync Mobile 2010、および Lync Mobile 2013) の状態が失われる可能性があります。

**回避策**

この問題を回避するには、Web コンポーネントと .NET framework を含むフォルダーをウイルス対策スキャン対象から除外します。 詳細については、「Microsoft サポート技術情報の記事312592、「PRB: ASP.NET で、アプリケーションが再起動[http://go.microsoft.com/fwlink/p/?linkid=3052\&kbid=312592](http://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=312592)しています」というエラーを参照してください。

次のフォルダーを除外する必要があります。

  - % ProgramFiles%\\Microsoft Lync Server 2013\\Web コンポーネント\\mcx\\Ext

  - % ProgramFiles%\\Microsoft Lync Server 2013\\Web コンポーネント\\mcx\\Int

  - % ProgramFiles%\\Microsoft Lync Server 2013\\Web コンポーネント\\ucwa\\Int

  - % ProgramFiles%\\Microsoft Lync Server 2013\\Web コンポーネント\\ucwa\\Ext

  - % Windir%\\Microsoft.NET\\Framework64\\v v4.0.30319\\Config

</div>

<div>

## <a name="activex-controls-or-native-xmlhttp-support-must-be-enabled-in-windows-internet-explorer-to-successfully-join-conferences"></a>会議に参加するには、Windows Internet Explorer で ActiveX コントロールまたはネイティブ XMLHTTP サポートを有効にする必要があります。

**問題**

ユーザーが Windows Internet Explorer のインターネットブラウザー設定で ActiveX コントロールとネイティブ XMLHTTP サポートの両方を無効にしている場合、Internet Explorer が既定のブラウザーとして選択されていると、ユーザーは会議に参加できません。

**回避策**

Internet Explorer で、ActiveX コントロールまたは "ネイティブ XMLHTTP サポート" を有効にします。

</div>

<div>

## <a name="lync-server-web-conferencing-service-cannot-recover-from-critical-mode"></a>Lync Server Web 会議サービスが重要なモードから回復できない

**問題**

重要モードでアーカイブが有効になっている場合、システム障害が発生すると、重要モードが開始され、会議は参加者に対して機能しなくなります。 管理者がシステム障害 (データベース問題の修正など) を修正した後、データ会議サービスは自動的には回復しないため、管理者は会議サービスを再開するために手動で再起動する必要があります。

**回避策**

システム障害が修正された後、管理者は、会議サービスを手動で再起動する必要があります。

</div>

<div>

## <a name="web-conferencing-service-ignores-the-http-proxy-for-external-office-web-app-servers"></a>Web 会議サービスが外部の Office Web App サーバーの HTTP プロキシを無視する

**問題**

Web 会議サービスの外部にある Office Web Apps サーバー (内部の企業ネットワークにはないサーバー) をインターネット、境界ネットワーク、および Web 会議サービスに展開している場合、これに接続するには HTTP プロキシが必要です。Office Web Apps サーバーの検出は失敗します。 Web 会議サービスは、「Office Web Apps Server セットアップのトポロジビルダー」で定義されているように、HTTP プロキシ設定を無視します。 その結果、Lync クライアントは、会議の他の参加者と Microsoft PowerPoint 2010 の共有を行うことができなくなります。 内部ネットワークで Lync Server をオンプレミスでインストールし、オンプレミスの Office Web Apps サーバーを構成する場合、プロキシ構成は必要ありません。

**回避策**

唯一の回避策は、外部の Office Web Apps サーバーとの通信に HTTP プロキシを使用する必要がある展開構成を行わないことです。

</div>

<div>

## <a name="adding-video-to-an-audio-conferencing-provider-conference-is-not-supported"></a>電話会議プロバイダーの会議へのビデオの追加はサポートされていません

**問題**

ユーザーが音声会議プロバイダーの電話会議に参加している場合、ビデオの追加はサポートされていません。

**回避策**

この問題の回避策はありません。

</div>

<div>

## <a name="topologies-with-ipv6-enabled-force-the-lync-web-app-silverlight-plug-in-auto-update-to-ensure-screen-sharing-functionality-can-work-from-lync-web-app"></a>IPv6 が有効になっているトポロジ lync web App Silverlight プラグイン自動更新を強制して、画面共有機能が Lync Web App から機能できるようにします。

**問題**

IPv6 が有効な状態でトポロジを構成すると、以前のバージョンの画面共有プラグインが既にインストールされている場合、ユーザーは Lync Web App クライアントから画面を共有できません。

**回避策**

Lync Web App を使用して会議に参加するときに、最新バージョンの画面共有プラグインを強制的に更新するには、次の両方のファイルで**Minsupportedbuildversion**の値を "4.0.7457.0" から "4.0.7577.380" に変更します。

  - % ProgramFiles%\\Microsoft Lync Server 15\\Web コンポーネント\\は\\、\\Int\\クライアント\\プラグイン ReachAppShPluginProperties に到達します。

  - % ProgramFiles%\\Microsoft Lync Server 15\\Web コンポーネント\\は\\Ext\\クライアント\\プラグイン\\ReachAppShPluginProperties に到達します。

</div>

</div>

<span id="EnterpriseVoice"></span>

<div>

## <a name="enterprise-voice"></a>用に構成します

<div>

## <a name="in-some-cases-a-lync-client-running-on-a-computer-configured-to-use-ipv4-and-ipv6-dual-stack-might-not-support-capabilities-that-rely-in-the-ip-subnet-of-the-computer-such-as-e911-media-bypass-call-admission-control-and-location-based-routing"></a>場合によっては、IPv4 と IPv6 デュアルスタックを使用するように構成されたコンピューター上で実行されている Lync クライアントが、E911、メディアバイパス、通話受付管理、場所ベースのルーティングなどのコンピューターの IP サブネットに依存する機能をサポートしていないことがあります。

<div class="">


> [!NOTE]  
> このセクションの情報は、Lync Server 2013 の累積的な更新プログラム (2013 年2月) に関連します。



</div>

**問題**

Lync クライアントが、IPv4 と IPv6 のデュアルスタックが有効になっていて、プロキシサーバーの DNS 解決に基づいてコンピューター上で実行されている場合、クライアントはコンピューターの IPv6 アドレスを使用してサインインすることができます。 その後、Lync クライアントは IPv6 に対してサポートされている機能のみをサポートします。これにより、E911、メディアバイパス、通話受付管理、および場所ベースのルーティングが除外されます。

**回避策**

この問題を回避するには、クライアントコンピューター上で IPv6 サポートを無効にします。

</div>

<div>

## <a name="if-enterprise-voice-is-not-configured-for-a-user-the-user-will-need-to-use-e164-format-to-dial-out-from-a-conference"></a>エンタープライズ Voip がユーザーに対して構成されていない場合、ユーザーは、電話会議からダイヤルアウトするために E164 形式を使用する必要があります。

**問題**

エンタープライズ Voip がユーザーに対して構成されていない場合、そのユーザーは、E164 形式を使用して会議からのダイヤルアウトを成功させる必要があります。 E164 形式が使用されていない場合、ユーザーは会議からダイヤルアウトできません。

**回避策**

この問題を回避するには、エンタープライズ Voip が有効になっていないユーザーは、E164 形式の番号を使用して電話会議からダイヤルアウトする必要があります。

</div>

</div>

<span id="Presence"></span>

<div>

## <a name="presence"></a>プレゼンス

<div>

## <a name="if-a-user-has-selected-block-all-invites-and-communications-while-the-unified-contact-store-is-turned-on-for-the-user-presence-status-is-not-rejected-when-it-should-be"></a>統合連絡先ストアがユーザーに対して有効になっているときに、ユーザーが "招待と通信をすべてブロックする" を選択している場合、プレゼンス状態が拒否されている必要があります。

**問題**

統合連絡先ストアがユーザーに対して有効になっているときに、ユーザーが "招待と通信をすべてブロックする" を選択した場合、プレゼンス状態が拒否されないはずです。

**回避策**

この問題を回避するには、ユーザーの統合連絡先ストアを無効にすることができます。 これを行うには、次のコマンドレットを実行します。

    Set-CsUserServicesPolicy -Identity "<user display name>" -UcsAllowed $False

例:

    Set-CsUserServicesPolicy -Identity "Ken Myer" -UcsAllowed $False

</div>

<div>

## <a name="office-communications-server-2007-r2-users-homed-on-premises-are-not-able-to-see-the-presence-status-of-skype-for-business-online-users-in-hybrid-deployments---hybrid"></a>Office Communications Server 2007 R2 オンプレミスのユーザーが、ハイブリッド展開で Skype for Business Online ユーザーのプレゼンス状態を表示できない-ハイブリッド

**問題**

この問題は、Lync Server 2013 ディレクターを使用している場合に、ハイブリッド展開で発生することがあります。

Skype for Business Online に所属するユーザーのプレゼンス状態は、オンプレミスユーザーのプレゼンス不明として表示されます。 また、Skype for Business Online に所属しているユーザーは、Office Communications Server R2 オンプレミスユーザーのプレゼンス状態を表示できません。

**回避策**

この問題を部分的に回避するには、Skype for Business Online ユーザーのホームサーバー (msrtcsip) を、Lync Server 2013 ディレクターではなく、Lync Server 2013 社内プールを指すように変更します。 この設定は、オンプレミスのフロントエンドサーバーで変更できます。

この回避策では、Office Communications Server 2007 R2 に所属するユーザーのプレゼンス状態が Skype for Business Online ユーザーに正しく表示されます。

</div>

</div>

<span id="ResponseGroup"></span>

<div>

## <a name="response-group-application-call-park-application-and-group-call-pickup"></a>応答グループアプリケーション、コールパークアプリケーション、グループ通話ピックアップ

<div>

## <a name="a-caller-might-hear-one-second-of-music-on-hold-during-the-establishment-of-a-call-with-the-retrieving-party"></a>発信者は、取得側で通話を発信している間、保留音の1秒間を聞くことができます。

<div class="">


> [!NOTE]  
> このセクションの情報は、Lync Server 2013 の累積的な更新プログラム (2013 年2月) に関連します。



</div>

**問題**

グループ通話ピックアップを使用して通話を取得した場合、発信者は取得側で通話を確立している間、保留音の1秒間を聞くことができます。

**回避策**

この問題の回避策はありません。

</div>

<div>

## <a name="a-response-group-agent-can-sign-in-and-sign-out-through-a-lync-server-2010-agent-console-to-lync-server-2010-formal-agent-groups-only"></a>応答グループエージェントは、Lync Server 2010 エージェントコンソールを使用して Lync server 2010 の正式なエージェントグループのみにサインインしてサインアウトすることができます。

**問題**

Lync Server 2013 応答グループエージェントは、lync server 2010 エージェントコンソールを使用して、lync server 2010 の正式なエージェントグループのみにサインインしてサインアウトすることができます。 Lync Server 2010 エージェントコンソールでは、ユーザーは自分が属している Lync Server 2010 応答グループのみを表示できます。 自分が属している Lync Server 2013 応答グループを表示することはできません。

**回避策**

応答グループエージェントが Lync Server 2013 ユーザーであり、Lync Server 2013 の正式なエージェントグループの一部である場合、ユーザーは、ブラウザーの web リンクを介して直接 Lync Server 2013 エージェントコンソールにアクセスし、Lync Server の2013エージェントグループにサインインしてサインアウトする必要があります。

</div>

<div>

## <a name="a-lync-server-2010response-group-agent-cannot-place-calls-on-behalf-of-a-lync-server-2013response-group"></a>Lync Server 2010 応答グループエージェントは、Lync Server 2013 応答グループの代理として通話を行うことができません

**問題**

Lync Server 2010 Lync Server 2013 応答グループのエージェントであるユーザーは、応答グループの代わりに通話を行うことができません。 Lync Server 2013 応答グループは、通話を行うために Lync クライアントで使用することはできません。

**回避策**

この問題を回避するには、Lync Server 2010 ユーザーを Lync Server 2013 に移動する必要があります。

</div>

<div>

## <a name="removing-a-response-group-from-lync-server-2010-after-it-has-been-migrated-to-lync-server-2013-will-prevent-the-response-group-from-accepting-any-incoming-calls"></a>Lync server 2013 に移行された後で Lync Server 2010 から応答グループを削除すると、応答グループは着信呼び出しを受け付けなくなります。

**問題**

Lync server 2010 から Lync Server 2013 に移行された応答グループが lync server の [コントロールパネル] または [Lync Server 管理シェル] から2010削除された場合、Lync Server 2013 の応答グループは着信呼び出しの受信を停止します。

**回避策**

この問題を回避するには、lync server 2010 から Lync Server 2013 に移行された Lync Server 2010 から応答グループを削除しないようにします。

応答グループが既に削除されている場合は、Lync Server 2013 に再展開する必要があります。

</div>

<div>

## <a name="when-a-new-managed-workflow-is-set-to-inactive-when-created-deployment-of-the-workflow-will-fail"></a>新しい管理ワークフローを作成時に非アクティブに設定すると、ワークフローの展開に失敗します。

**問題**

新しい管理ワークフローを作成時に非アクティブに設定すると、ワークフローの展開は失敗します。 この問題は、作成時にワークフローが非アクティブに設定されている場合に発生しますが、が展開された後に非アクティブに設定するように編集されたワークフローには影響しません。

**回避策**

ワークフローを作成して展開するときは、ワークフローをアクティブに設定して展開します。 ワークフローが正常に展開された後、ワークフローを編集して非アクティブに設定できます。

</div>

<div>

## <a name="removing-a-response-group-from-the-owner-pool-will-prevent-the-response-group-of-the-backup-pool-from-accepting-any-incoming-calls-during-failover-if-the-response-group-has-been-imported-to-the-backup-pool"></a>応答グループがバックアッププールにインポートされている場合、所有者プールから応答グループを削除すると、フェールオーバー中のすべての着信呼び出しがバックアッププールの応答グループによって受け付けられなくなります。

**問題**

プライマリプールに所有されている応答グループが所有者を上書きせずにバックアッププールにインポートされ、所有者プールから応答グループが削除された場合、バックアッププールの応答グループは、フェールオーバー中に着信呼び出しを受け付けません。

**回避策**

プライマリプールに応答グループを再展開する必要があります。 その後、プライマリプールから応答グループの構成をエクスポートして、もう一度バックアッププールにインポートする必要があります。

バックアッププールで応答グループを再作成することもできます。 この場合、バックアッププールは応答グループの所有者プールになります。

</div>

<div>

## <a name="a-parked-call-cant-be-retrieved-from-the-call-park-application-if-the-retrieve-request-is-done-on-behalf-of-a-response-group"></a>応答グループの代理として取得要求が行われた場合、コールパークアプリケーションから保留中の通話を取得することはできません

**問題**

次の条件に該当する場合、保留中の通話の取得要求は失敗します。

  - エージェントが匿名応答グループに含まれている

  - エージェントは、呼び出しパークアプリケーションからの保留中の呼び出しを匿名応答グループを介して取得しようとします。

  - エージェントは、[代理人として呼び出し] オプションまたは Lync アテンダントクライアントの同じオプションを使用して、オービット番号をダイヤルして通話を取得しようとしています。

**回避策**

この問題の回避策はありません。 保留中の呼び出しは、応答グループの代理としてではなく、取得する必要があります。

</div>

</div>

<span id="TopoBuilder"></span>

<div>

## <a name="lync-server-control-panel-topology-builder-and-planning-tool"></a>Lync Server コントロール パネル、トポロジ ビルダー、および計画ツール

<div>

## <a name="planning-tool-limitations"></a>計画ツールの制限事項

<div class="">


> [!NOTE]  
> このセクションの情報は、Lync Server 2013 の累積的な更新プログラム (2013 年2月) に関連します。



</div>

**問題**

展開を計画する場合、計画ツールには次の制限があります。

  - 最大10個の中央サイトがサポートされています。

  - 各中央サイトには、最大14個のブランチサイトを含めることができます。

  - 各中央サイトには、最大24万ユーザーを含めることができます。

また、計画ツールでは、推奨されるトポロジを計算する際に、次の値は含まれません。

  - オンラインに所属しているユーザーの数

  - XMPP フェデレーションが有効になっているユーザーの割合

  - Lync Web App を使用しているユーザーの割合

**回避策**

これらの問題の回避策はありません。 計画ツールの詳細については、「[計画ツールを使用して Lync Server 2013 のトポロジを設計](lync-server-2013-designing-the-topology-by-using-the-planning-tool.md)する」を参照してください。

</div>

<div>

## <a name="planning-tool-may-not-use-previously-defined-ip-addresses-for-the-edge-network-when-updating-options"></a>計画ツールでオプションを更新するときに、エッジネットワークに対して定義済みの IP アドレスが使用されないことがある

**問題**

計画ツールを使用して設計を完了した後、エッジネットワークオプションを変更すると、既存の IP アドレスを更新するのではなく、追加の IP アドレスが設計に追加されることがあります。 これは、エッジネットワークダイアグラムの詳細を表示しているときに、 **[ここをクリックしてオプションを更新**します] を選択し、[構成オプション] ダイアログボックスの [エッジネットワーク] を選択します。 [**同じ fqdn および IP アドレスを使用するが、エッジサーバー上のエッジサービスに異なるポートを使用**する] を選択します。 変更を適用すると、新しい IP アドレスとエッジサーバーが設計に追加されることがあります。

**回避策**

現時点では、この問題を回避する方法はありません。

</div>

<div>

## <a name="in-lync-server-control-panel-move-all-users-to-pool-may-not-work-as-expected"></a>Lync Server コントロールパネルで、[すべてのユーザーをプールに移動] が期待どおりに機能しない場合があります。

**問題**

Lync Server コントロールパネルを使用して、あるプールから、複数のドメインコントローラーや親/子ドメインなど、複雑な Active Directory 環境にある別のプールにすべてのユーザーを移動する場合、エラーメッセージが返されることがあります。 "指定されたユーザーはレガシユーザーではなく、Move-CsUser コマンドレットを使用します。" 複雑な Active Directory 環境では、レプリケーション時間が長くなります。

**回避策**

この問題を回避するには、次のいずれかの操作を行います。

  - Lync Server コントロールパネルのフィルターを使用して、レガシユーザーを検索し、それらのユーザーを選択してから、[**選択したユーザーをプールに移動] コマンド**を使用して、**すべてのユーザーをプールに移動**します。

  - Lync server のコマンドレットを使用して、バッチで従来のユーザーを移動するには、Lync Server 管理シェルを使用します。

</div>

<div>

## <a name="the-lync-server-control-panel-stops-working-in-a-vmware-environment-after-the-microsoft-silverlight-browser-plug-in-is-updated-to-version-5"></a>Microsoft Silverlight ブラウザープラグインがバージョン5に更新された後、Lync Server コントロールパネルが VMware 環境で機能しなくなる

**問題**

VMware 環境で Lync Server コントロールパネルを使用すると、Silverlight をバージョン5にアップグレードした後、Lync Server コントロールパネルが機能しなくなることがあります。

**回避策**

この問題を回避するには、次のいずれかの操作を行います。

  - Silverlight 5 をアンインストールし、から[https://go.microsoft.com/fwlink/p/?LinkID=149156\&v=4.0](https://go.microsoft.com/fwlink/p/?linkid=149156%26v=4.0)silverlight 4 をインストールします。

  - VMware 仮想コンピューターではないコンピューターから Lync Server コントロールパネルを開きます。
    
    リモートコンピューターから Lync server コントロールパネルを開くには、コンピューターに Lync Server 管理ツールをインストールしてから、Windows の [**スタート**] メニューから Lync Server コントロールパネルを起動します。
    
    Web ブラウザーに URL を入力して、Lync Server コントロールパネルを開くこともできます。 この URL\<は https://フロントエンド\_プール\_の fqdn\>に似ています。/cscp.

</div>

<div>

## <a name="an-administrator-cannot-run-the-uninstall-csmirrordb-cmdlet-after-removing-the-mirroring-database-in-topology-builder"></a>トポロジビルダーでミラーリングデータベースを削除した後、管理者がアンインストール-csMirrorDB コマンドレットを実行できない

**問題**

管理者がトポロジビルダーでミラーリングデータベースを無効にした後、トポロジビルダーでミラーリングデータベースを削除すると、管理者が**install-csmirrordatabase**コマンドレットを実行して SQL Server からミラーリングを削除するように、メッセージが [タスク] 一覧に表示されます。 管理者がコマンドレットを実行しようとすると、失敗します。

**回避策**

トポロジビルダーでプールの SQL ミラーリングを削除するには、最初にコマンドレットを使用して、SQL Server でミラーを削除する必要があります。 次に、トポロジ ビルダーを使用して、トポロジからミラーを削除できます。 SQL Server でミラーを削除するには、次のコマンドレットを使用します。

    Uninstall-CsMirrorDatabase -SqlServerFqdn <SQLServer FQDN> [-SqlInstanceName <SQLServer instance name>] -DatabaseType <Application | Archiving | CentralMgmt | Monitoring | User | BIStaging | PersistentChat | PersistentChatCompliance> [-DropExistingDatabasesOnMirror] [-Verbose]

たとえば、ミラーリングを削除してユーザーデータベースのデータベースをドロップするには、次のように入力します。

    Uninstall-CsMirrorDatabase -SqlServerFqdn primaryBE.contoso.com -SqlInstanceName rtc -Verbose -DatabaseType User -DropExistingDatabasesOnMirror

*Dropexistingdatabases Onmirror*パラメーターを指定すると、影響を受けるデータベースがミラーから削除されます。 次に、トポロジからミラーを削除するには、次の操作を行います。

1.  トポロジ ビルダーで、プールを右クリックし、[**プロパティの編集**] をクリックします。

2.  [ **SQL ストアミラーリングの有効化**] をオフにして、[ **OK]** をクリックします。

3.  トポロジを公開します。

<div class="">


> [!IMPORTANT]  
> バックエンドデータベースミラーリング関係を変更するたびに、プール内のすべてのフロントエンドサーバーを再起動する必要があります。



</div>

</div>

<div>

## <a name="validation-errors-are-returned-in-topology-builder-when-an-administrator-attempts-to-remove-a-deployment-with-a-front-end-pool-that-has-an-associated-witness-store"></a>管理者が関連付けられた監視ストアを持つフロントエンドプールを使用して展開を削除しようとすると、トポロジビルダーで検証エラーが返される

**問題**

管理者がトポロジビルダーの [**展開の削除**] コマンドを使用して、関連付けられた監視ストアを持つフロントエンドプールを含む展開を削除しようとすると、検証エラーがトポロジビルダーに表示され、操作は続行されません。

**回避策**

この問題を回避するには、次のいずれかの操作を行います。

  - 展開を削除する前に、ミラーリング監視ストアを削除します。

  - フロントエンドプールのミラーリング監視ストアを追加し、削除します。

</div>

<div>

## <a name="persistent-chat-server-deployment-information-is-inconsistent-between-the-planning-tool-and-topology-builder"></a>計画ツールとトポロジビルダーの間で常設チャットサーバーの展開情報が矛盾している

**問題**

Lync Server 2013 (Planning Tool) が障害復旧を有効にした状態で常設チャットサーバーの展開のためのサイトトポロジ図を出力すると、サイトトポロジの図には複数の (物理的な) サイトが含まれており、それぞれに常設チャットサーバーが均等に割り当てられています。サイト. トポロジビルダーでは、すべての常設チャットサーバーは、1つの (論理的な) サイトに属するものとして表され、同じ常設チャットサーバープールノードの下に一覧表示されます。

**回避策**

現時点では、この問題の回避策はありません。 常設チャットサーバーの展開の計画ツールの出力を分析し、特定のニーズに合わせて計画を変更する必要があります。

</div>

</div>

<span id="Localization"></span>

<div>

## <a name="localization"></a>ローカリゼーション

<div>

## <a name="monitoring"></a>監視

<div>

## <a name="the-deploy-monitoring-reports-wizard-displays-incorrect-characters-under-certain-circumstances-when-using-the-east-asian-version-of-lync-server"></a>日本語版の Lync Server を使用している場合、監視レポートの展開ウィザードで、特定の状況で誤った文字が表示される

**問題**

システムロケールが東アジア言語に設定されていないオペレーティングシステムで、中国語 (簡体字)、中国語 (繁体字)、日本語、韓国語などの東アジアバージョンの Lync Server 2013 を使用している場合、監視レポートの展開ウィザードはローカライズされたメッセージではなく、疑問符または他の文字を表示します。

**回避策**

この問題を解決するには、オペレーティングシステムと Lync Server 2013 のロケールを同じ言語に設定して、すべてのメッセージが正しく表示されるようにします。

</div>

</div>

<div>

## <a name="lync-server-control-panel"></a>Lync Server コントロール パネル

<div>

## <a name="in-certain-cases-the-first-item-in-the-top-navigation-bar-on-a-page-of-lync-server-control-panel-disappears-when-the-last-item-in-the-top-navigation-bar-is-clicked"></a>場合によっては、トップナビゲーションバーのページ上のトップナビゲーションバーの最初の項目が表示されなくなると、トップナビゲーションバーの最後の項目がクリックされます。

**問題**

次の3つの既知のケースでは、Lync Server コントロールパネルのページにあるトップナビゲーションバーの最後の項目をクリックすると、トップナビゲーションバーの最初の項目が非表示になります。

  - フランス語版のページ "Féderation et accès externe" では、"Partenaires d'accès XMPP" がクリックされたときに "Stratégie externe fédérés" という項目が表示されなくなります。

  - ドイツ語版の "Clients" ページで "クリックすると" がクリックされると、アイテム "Clientversionskonfiguration" が表示されなくなります。

  - ロシア語版の "Конфигурациясети" ページで "Маршрутрегиона" をクリックすると、"Глобально" という項目が表示されなくなります。

**回避策**

この問題を回避するには、ブラウザーで Lync Server コントロールパネルのページを更新します。 トップナビゲーションバーに表示されるすべてのアイテムと共に、ページがブラウザーに読み込まれます。

</div>

</div>

<div>

## <a name="address-book"></a>アドレス帳

<div>

## <a name="indexing-in-the-address-book-does-not-work-as-expected-in-some-languages"></a>一部の言語で、アドレス帳のインデックス処理が期待どおりに機能しない

<div class="">


> [!NOTE]  
> このセクションの情報は、Lync Server 2013 の累積的な更新プログラム (2013 年2月) に関連します。



</div>

ユーザーのプロパティにインデックスフィールドが含まれており、そのフィールドにインデックスを作成できない文字のみが含まれている場合、そのユーザーはアドレス帳で実行される検索には表示されません。

次の文字とロケールのインデックスを作成することはできません。

  - 大文字のキリル文字、ギリシャ文字、およびアルメニア文字

  - 大文字のアクセント記号付き文字

  - タイ語

  - ラオス語

  - ミャンマー

  - デバナガリ

  - エチオピア

  - チベット語

  - ベンガル語

  - グジャラート語

  - テルグ語

  - 他のすべてのインド諸語スクリプト

</div>

</div>

<div>

## <a name="lync-web-app-web-scheduler-and-web-components"></a>Lync Web App、Web Scheduler、および Web コンポーネント

<div>

## <a name="language-fallback-for-certain-languages-in-lync-web-scheduler-dial-in-join-launcher-persistent-chat-room-management-and-octab-might-not-work-as-expected"></a>Lync Web Scheduler、ダイヤルイン、参加起動ツール、常設チャットルーム管理、および OCTab の特定の言語の言語フォールバックが期待どおりに機能しないことがあります。

**問題**

Web ブラウザーでニュートラルロケールを選択する (Internet Explorer の場合) たとえば、言語、スクリプト、およびロケール ("ノルウェー語、 \[ブークモール\](ノルウェー) \[nb-いいえ\]" など) を指定するロケールの代わりに、"ノルウェー no" のような仕様のない言語名は、Lync Web Scheduler、ダイヤルイン、参加起動ツール、常設チャットルーム管理、および [octab] タブの特定の言語に対して予期しない表示動作を たとえば、次の言語のいずれかが選択されている場合、ユーザーには英語のページが表示されることがあります。

  - ノルウェー語

  - ポルトガル語

  - セルビア語

**回避策**

ニュートラルロケールの言語を選択する場合は、ブラウザーの言語設定一覧で、特定のロケール (スクリプトや国コードを含む) が追加言語として追加されていることを必ず確認してください。

</div>

<div>

## <a name="there-is-limited-support-for-azeri-and-uzbek-locales-when-using-lync-web-scheduler-dial-in-join-launcher-persistent-chat-room-management-and-octab-in-some-web-browsers"></a>一部の web ブラウザーでは、Lync Web Scheduler、ダイヤルイン、参加起動ツール、常設チャットルーム管理、および OCTab を使用する場合に、アゼルバイジャンおよびウズベク語のサポートが制限されています。

<div class="">


> [!NOTE]  
> このセクションの情報は、Lync Server 2013 の累積的な更新プログラム (2013 年2月) に関連します。



</div>

**問題**

Internet Explorer 8 または Internet Explorer 9 を使用していて、ブラウザーの言語をアゼルバイジャン語 (ラテン) またはウズベク語 (ラテン) に設定すると、ダイヤルインページと参加起動ツールページが英語で表示されるか、ブラウザーで優先言語セットとして表示されます。

Firefox または Chrome ブラウザーを使用している場合、ブラウザーの言語をアゼルバイジャン語 (ラテン) またはウズベク語 (ラテン) に設定すると、Lync Web App、Lync Web Scheduler、および RGS OCTab が英語で表示されるか、ブラウザーの優先言語セットとして表示されます。

Safari ブラウザーでは、ウズベク語 (ラテン) ロケールはサポートされていません。

**回避策**

これらの問題を回避する方法はありません。

</div>

</div>

<div>

## <a name="the-drop-down-arrow-is-missing-for-join-meeting-from-list-in-the-romanian-version-of-lync-web-app"></a>ルーマニア語版の Lync Web App の [会議に参加] リストにドロップダウン矢印が表示されない

**問題**

ルーマニア語版の Lync Web App を使用しているユーザーが次の手順を実行すると、[**会議に参加**] ドロップダウンリストにドロップダウン矢印が表示されません。

1.  [**全般**] タブの [**このコンピューターにあるメールを記憶**する] を選択します。

2.  [**電話**] タブを選択します。

3.  [**会議に参加**する] のドロップダウンリストをクリックします。
    
    ユーザーには、既定の**Lync Web App**より多くのオプションがあることを示す矢印は表示されません。これには、[**オーディオに参加しない**] (ルーマニア語、"ニュー se asociaža la componenta audio")、および [**新しい番号**] (ルーマニア語、"Număr nou") が含まれます。

**回避策**

このドロップダウンリストの矢印は表示されませんが、ユーザーは既定値をクリックして、リスト内の追加の設定を選択することもできます。

</div>

<div>

## <a name="when-using-the-turkish-version-of-lync-web-scheduler-a-meeting-cannot-be-saved-when-using-the-people-i-choose-option-under-who-is-a-presenter"></a>トルコ語版の Lync Web Scheduler を使用している場合、[発表者となるユーザー] の [選択したユーザー] オプションを使用すると、会議を保存できません。

**問題**

トルコ語版の Lync Web Scheduler で会議を作成または編集する場合、[発表者となるユーザー] の [選択したユーザー] オプションはサポートされていません。 このオプションを選択すると、会議を保存できません。 代わりに、1人以上のユーザーがプレゼンターを作成できないことを示すエラーメッセージが表示されます。

**回避策**

この問題を回避するには、ユーザーは "会社のユーザーからの人"、または "会社外の人を含むすべての人を含むすべてのユーザー" の既定のオプションを使用できます。 開催者は後で会議に参加した後で、ユーザーを適切な役割に降格または昇格させることができます。

別の言語を理解しているユーザーは、ブラウザーでの言語の選択を他の43でサポートされている言語のいずれかに変更し、"ユーザーが選択した" オプションを使用することができます。

</div>

</div>

<span id="Copyright"></span>

<div>

## <a name="copyright"></a>著作権

このドキュメントでは、最終的な商用リリースの前に実質的に変更される可能性があるソフトウェア製品の予備リリースがサポートされています。また、Microsoft Corporation の機密情報でもあります。 これは、受信者と Microsoft との間の機密保持契約に基づいて開示されます。 このドキュメントは情報提供のみを目的として提供されており、このドキュメントでは明示的にも黙示的にもいかなる保証も行いません。 このドキュメントに記載されている情報 (URL やその他のインターネット web サイトへの参照を含む) は、将来予告なしに変更される可能性があります。 このドキュメントを使用した場合のリスク全体またはその結果は、ユーザーによって保持されます。 別途記載されていない限り、このドキュメントで使用している会社、組織、製品、ドメイン名、電子メールアドレス、ロゴ、人物、場所、およびイベントは架空のものです。 実在する会社、組織、製品、ドメイン名、電子メールアドレス、ロゴ、人物、場所、またはイベントには、意図されていないか、または推論する必要がありません。 該当するすべての著作権法の順守は、ユーザー側の責任となります。 著作権法の範囲に限定されることなく、米国 Microsoft Corporation の書面による明示的な許諾なしに、このドキュメントのいかなる部分も、いかなる形式または手段 (電子的、機械的、コピー複写、記録、またはその他の方法) で、またはいかなる目的でも、複製、保存、検索システム導入、または転送することはできません。

マイクロソフトは、このドキュメントに記載されている内容に関し、特許、特許申請、商標、著作権、またはその他の無体財産権を有する場合があります。別途マイクロソフトのライセンス契約上に明示の規定のない限り、このドキュメントはこれらの特許、商標、著作権、またはその他の無体財産権に関する権利をお客様に許諾するものではありません。

c 2012 Microsoft Corporation. All rights reserved.

Microsoft、Windows、Windows Live、Active Directory、Internet Explorer、MSN、Outlook、および SQL Server は、米国 Microsoft Corporation の米国およびその他の国/地域における登録商標または商標です。

その他すべての商標は各社が所有しています。

</div>

</div>

<span> </span>

</div>

</div>

</div>

