---
title: 'Lync Server 2013: バックアップと復元の要件: データ'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: 'Backup and restoration requirements: data'
ms:assetid: ecfb8e4d-cb4f-476d-9772-4486bd683c04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202194(v=OCS.15)
ms:contentKeyID: 51541526
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a9b9f077e0f9d7c4137844b2cba352b096fdb564
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730427"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="backup-and-restoration-requirements-in-lync-server-2013-data"></a>Lync Server 2013 でのバックアップと復元の要件: データ

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2013-03-26_

Lync Server は、データベースに保存されている設定と構成情報、およびデータベースやファイルストアに保存されているデータを使用します。 このトピックでは、組織で障害や停止が発生した場合に、サービスを復元できるようにするためにバックアップする必要のあるデータについて説明します。また、個別にバックアップする必要がある Lync Server で使用されているデータとコンポーネントも識別します。

<div>

## <a name="settings-and-configuration-requirements"></a>設定と構成の要件

このトピックでは、Lync Server サービスの回復に必要な設定と構成情報をバックアップおよび復元する手順について説明します。 構成情報は、中央管理ストア、または別のバックエンドデータベースまたは Standard Edition サーバーに保存されています。

次の表は、バックアップと復元に必要な設定と構成情報を示しています。

### <a name="settings-and-configuration-data"></a>設定データと構成データ

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>データの種類</th>
<th>保存場所</th>
<th>説明/バックアップするタイミング</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>トポロジ構成情報</p></td>
<td><p>一元管理ストア (データベース: Xds)</p></td>
<td><p>トポロジ、ポリシー、構成の設定。</p>
<p>通常のバックアップでバックアップを作成し、Lync Server コントロールパネルまたはコマンドレットを使用して、構成またはポリシーを変更します。</p></td>
</tr>
<tr class="even">
<td><p>位置情報</p></td>
<td><p>一元管理ストア (データベース: Lis)</p></td>
<td><p>エンタープライズ Voip 拡張 9-1-1 (E9-1) 構成情報。 通常、この情報は静的です。</p>
<p>定期的なバックアップでバックアップを作成します。</p></td>
</tr>
<tr class="odd">
<td><p>応答グループの構成情報</p></td>
<td><p>バックエンドサーバーまたは Standard Edition server (データベース: RgsConfig)</p></td>
<td><p>応答グループのエージェントグループ、キュー、ワークフロー。</p>
<p>定期的なバックアップに加えて、エージェントグループ、キュー、またはワークフローを追加または変更した後でバックアップします。</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="data-requirements"></a>データ要件

障害が発生した場合に Lync Server サービスを復元できるように、バックアップする必要がある Lync Server データの一覧を次に示します。

データの種類によっては、回復には必要ないことに注意してください。 このトピックには、次のような種類のデータをバックアップする手順は含まれていません。

  - エンドポイントとサブスクリプション、アクティブな会議サーバー、一時的な会議の状態などの一時的なユーザーデータ (データベース: RtcDyn)

  - アドレス帳データ (データベース: Rtcab と Rtcab1)。 アドレス帳データベースは、Active Directory ドメインサービスから自動的に再生成されます。

  - コールパークアプリケーションの動的情報 (データベース: CpsDyn)

  - エージェントのサインイン状態や通話待機情報などの一時的応答グループデータ (データベース: RgsDyn)

  - 常設チャットのコンプライアンスデータベース (データベース: の場合は、mdf)。 常設チャットのコンプライアンスを有効にしている場合、データベースから情報を読み取るように構成されたアダプターを使用していて、それを別の形式に変換できる限り、常設チャットのコンプライアンスデータベース内の情報は一時的です。 したがって、常設チャットのコンプライアンスデータベースは一時的なものと見なされます。
    
    Lync Server 2013 常設チャットサーバーには、XML アダプターが付属しています。 このデータを使用するカスタムアダプターをインストールして、Exchange Hosted アーカイブなどの他のソースに移動することもできます。

次の表は、バックアップと復元に必要なデータを示しています。

### <a name="data-stored-in-databases"></a>データベースに格納されているデータ

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>データの種類</th>
<th>保存場所</th>
<th>説明/バックアップするタイミング</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>固定ユーザーデータ</p></td>
<td><p>バックエンドサーバーまたは Standard Edition server (データベース: RTCXDS. mdf)</p></td>
<td><p>ユーザー権限、ユーザーの連絡先リスト、サーバーまたはプールのデータ、スケジュールされた会議など。 このユーザーデータには、会議にアップロードされたコンテンツは含まれません。</p>
<p>定期的なバックアップでバックアップを作成します。 この情報は動的ですが、最新の定期的なバックアップに復元する必要がある場合は、更新が失われることはありません。 連絡先リストが組織にとって重要である場合は、このデータをより頻繁にバックアップできます。</p></td>
</tr>
<tr class="even">
<td><p>データをアーカイブする</p></td>
<td><p>アーカイブデータベース (データベース: LcsLog)</p>
<p>このデータは、Microsoft Exchange 統合オプションを有効にしている場合、Exchange 2013 に保存される可能性があります。 そうしないと、このデータは Lync Server アーカイブデータベースに保存されます。これは、別の Lync Server データベースと併置されているか、別のデータベースサーバー上でスタンドアロンである可能性があります。</p></td>
<td><p>インスタントメッセージング (IM) と会議の内容。</p>
<p>このデータは、Lync Server にとっては重要ではありませんが、規制を目的として組織にとって重要な場合があります。 必要に応じてバックアップスケジュールを決定します。</p></td>
</tr>
<tr class="odd">
<td><p>データの監視</p></td>
<td><p>監視データベース (LcsCDR と QoeMetrics)</p>
<p>これらのデータベースは、別の Lync Server データベースと併置されている場合や、別のデータベースサーバー上でスタンドアロンである場合があります。</p></td>
<td><p>通話の詳細レコード (LcsCDR .mdf) と Quality of Experience (QoE) メトリック (QoeMetrics)。</p>
<p>通話の詳細レコードは動的であり、ビジネスにとって重要である可能性があります。 規制上の理由からこれらのレコードが必要かどうかを考慮して、バックアップのスケジュールを決定します。</p>
<p>エクスペリエンスの品質情報は動的です。 QoE データの損失は、Lync Server の運用には重要ではありませんが、ビジネスにとって重要な場合があります。 この情報が組織にとって重要であるかどうかに基づいて、バックアップのスケジュールを決定します。</p></td>
</tr>
<tr class="even">
<td><p>常設チャットデータ</p></td>
<td><p>常設チャットデータベース (持っています)。</p>
<p>このデータベースは、別の Lync Server データベースと併置されている場合や、別のデータベースサーバー上でスタンドアロンである場合があります。</p></td>
<td><p>常設チャットデータは、チャットルームに投稿された実際のチャットコンテンツです。 このデータは、多くの場合、ビジネスクリティカルです。</p>
<p>Lync Server に用意されている<strong>CsPersistentChatData</strong>コマンドレットを使用して、SQL Server バックアップを使用するか、データベースをエクスポートするかを選ぶことができます。 データを回復するには、最後の完全バックアップの時点までデータベースをインポートして復元することができます。つまり、障害が発生した時点にデータベースを復元することはできません。</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="file-store-data-requirements"></a>ファイルストアのデータ要件

Enterprise Edition の展開では、Lync Server ファイルストアは通常、ファイルサーバー上にあります。 Standard Edition の展開では、Lync Server ファイルストアは既定で Standard Edition サーバー上に配置されています。 通常、サイトで共有される Lync Server ファイルストアは1つです。 常設チャットファイルストアでは、Lync Server ファイルストアと同じファイル共有が使用されます。

ファイルストアの場所は、 \\ \\サーバー\\の共有名として識別されます。 ファイルストアの特定の場所を検索するには、[トポロジビルダー] を開き、[**ファイルストア**] ノードを確認します。

次の表は、バックアップと復元を行う必要があるファイルストアを示しています。

### <a name="file-stores"></a>ファイルストア

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>データの種類</th>
<th>保存場所</th>
<th>説明/バックアップするタイミング</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lync Server ファイルストア</p></td>
<td><p>通常は、ファイルサーバー、ファイルクラスター、または Standard Edition サーバー</p></td>
<td><p>会議コンテンツ、会議コンテンツメタデータ、会議のコンプライアンスログ、アプリケーションデータファイル、デバイス更新のためのファイルの更新、応答グループのオーディオファイル、コールパーク、およびお知らせアプリケーション、および常設チャットルームに投稿されたファイル。</p>
<p>定期的なバックアップでバックアップを作成します。</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="additional-backup-requirements"></a>その他のバックアップ要件

障害が発生した場合に Lync Server サービスを復元できるようにするために、Lync Server 自体の一部ではない必要なコンポーネントをバックアップする必要があります。 このドキュメントで説明されている Lync Server バックアップと復元プロセスの一環として、次のコンポーネントはバックアップまたは復元されません。

  - **Active directory ドメインサービス**   Lync Server のバックアップと同時に active directory ツールを使用して、AD DS のバックアップを作成する必要があります。 Ad ds と Lync Server の同期を維持することが重要です。この問題は、Lync Server で、AD DS で一致しない連絡先オブジェクトが想定されている場合に発生する可能性のある問題を回避することをお勧めします。 AD DS には、Lync Server によって使用される次の設定が保存されます。
    
      - ユーザー SIP URI とその他のユーザー設定。
    
      - 応答グループ、会議アテンダントなどのアプリケーションの連絡先オブジェクト。
    
      - 中央管理ストアへのポインター。
    
      - Kerberos 認証アカウント (オプションのコンピューターオブジェクト) と Lync Server セキュリティグループ。
    
    Windows Server 2008 での AD DS のバックアップと復元の詳細については、「AD DS のバックアップと回復のステップバイステップ[http://go.microsoft.com/fwlink/p/?linkId=209105](http://go.microsoft.com/fwlink/p/?linkid=209105)ガイド」を参照してください。

  - **証明機関と証明書**   証明機関 (CA) と証明書のバックアップに組織のポリシーを使用します。 エクスポート可能な秘密キーを使用している場合は、このドキュメントの手順を使用して Lync Server を復元すると、証明書と秘密キーをバックアップし、エクスポートすることができます。 内部 CA を使用している場合、Lync Server を復元する必要がある場合は、再登録することができます。 コンピューターに障害が発生した場合に使用できるように、セキュリティで保護された場所で秘密キーを保持することが重要です。

  - **System center operations**   manager microsoft System center operations manager (以前の microsoft Operations manager) を使って lync server の展開を監視している場合は、lync server を監視している間に、必要に応じて、作成したデータをバックアップすることができます。 標準の SQL Server バックアッププロセスを使用して System Center Operations Manager ファイルをバックアップします。 これらのファイルは、回復時に復元されません。

  - **公衆交換電話網 (PSTN) ゲートウェイの構成**   エンタープライズ voip または Survivable Branch アプライアンスを使用している場合は、pstn ゲートウェイ構成をバックアップする必要があります。 PSTN ゲートウェイの構成のバックアップと復元の詳細については、ベンダーにお問い合わせください。

  - **共存バージョンの lync server または office communications server**   lync server 2013 の展開が lync server 2010 または以前のバージョンの office communications server を使用して coexists されている場合、このドキュメントに記載されている手順を使用して、以前のバージョンをバックアップまたは復元することはできません。 代わりに、以前のバージョンに対して特別に記載されているバックアップと復元の手順を使用する必要があります。 Lync Server 2010 のバックアップと復元の詳細について[http://go.microsoft.com/fwlink/p/?linkId=265417](http://go.microsoft.com/fwlink/p/?linkid=265417)は、を参照してください。 Microsoft Office Communications Server 2007 R2 のバックアップと復元の詳細について[http://go.microsoft.com/fwlink/p/?linkId=168162](http://go.microsoft.com/fwlink/p/?linkid=168162)は、を参照してください。

  - **インフラストラクチャ情報**   ファイアウォール構成、負荷分散構成、インターネットインフォメーションサービス (IIS) 構成、ドメインネームシステム (DNS) レコードと IP アドレス、動的ホスト構成プロトコル (DHCP) 構成など、インフラストラクチャに関する情報をバックアップする必要があります。 これらのコンポーネントのバックアップの詳細については、それぞれのベンダーに確認してください。

  - **Microsoft exchange と exchange ユニファイドメッセージング (UM)**   microsoft exchange のドキュメントで説明されているように、microsoft exchange と exchange UM をバックアップして復元します。 Exchange Server 2013 のバックアップと復元の詳細について[http://go.microsoft.com/fwlink/?LinkId=285384](http://go.microsoft.com/fwlink/?linkid=285384)は、を参照してください。 Exchange Server 2010 のバックアップと復元の詳細について[http://go.microsoft.com/fwlink/p/?linkId=209179](http://go.microsoft.com/fwlink/p/?linkid=209179)は、を参照してください。
    
    Lync Server 2013 では、ユーザーの連絡先リスト、高解像度のユーザー写真、および Exchange 2013 に保存されているデータをアーカイブする機能が導入されています。 これらの種類のデータをバックアップする方法については、次の一覧を参照してください。
    
      - **高精細写真**は、Exchange Server バックアップの一部としてバックアップされています。
    
      - **統合連絡先ストア**は、Lync Server 2013 で導入されています。 ユニファイド連絡先ストアを使用すると、ユーザーは Exchange 2013 ですべての連絡先情報を保存できます。
        
        ユーザーの連絡先がユニファイド連絡先ストアと Lync バックエンドサーバーのどちらに保存されているかについて、ユーザーが確実にバックアップを行う必要があります。 次のシナリオでは、ユーザーの連絡先を統合連絡先ストアに移行することによって、バックアップと復元プロセスの問題が発生する可能性があります。
        
        **シナリオ 1:** ユーザーの連絡先はユニファイド連絡先ストアに移行され、ユーザーの連絡先の移行前に使用した Lync Server バックアップから復元が実行されます。 このシナリオでは、Lync Server の移行タスクがユーザーの連絡先を Exchange に移行し始めるまで、ユーザーは最長で1日後に最新の連絡先の状態になります。 (ユーザーの連絡先は以前にユニファイド連絡先ストアに移行されたため、Exchange の連絡先情報が使用されることに注意してください)。 このシナリオでは、管理者の介入は必要ありません。
        
        **シナリオ 2:** ユーザーの連絡先は、以前はユニファイド連絡先ストアに保存されていましたが、ロールバックされました。 復元は、ユーザーの連絡先がユニファイド連絡先ストアに保存されているときに行われた Lync Server バックアップから実行されます。 このシナリオでは、クライアントまたは`Error: Incorrect Exchange Version`サーバーのログにエラーメッセージが表示されることがあります。これは問題として示される場合があります。 ユーザーは、Exchange から直接 Lync 2013 の連絡先リストにアクセスできますが、クライアントの状態は Lync Server の状態と一致しません。 この問題を解決するには、管理者が、影響を受けるユーザーに対して**CsUCSRollback**コマンドレットを実行する必要があります。
    
      - **アーカイブデータ**は Exchange 2013 に保存できます。 このデータは、Lync Server にとっては重要ではありませんが、規制を目的として組織にとって重要な場合があります。 アーカイブデータが Exchange に保存されており、組織にとって重要な場合は、Exchange のバックアップと復元の手順に従います。 Exchange に保存されているアーカイブデータは、Lync Server に戻すことができないことに注意してください。 さらに、Lync アーカイブデータベースに既に保存されているデータを Exchange に移動する方法はありません。

</div>

</div>

<span> </span>

</div>

</div>

</div>

