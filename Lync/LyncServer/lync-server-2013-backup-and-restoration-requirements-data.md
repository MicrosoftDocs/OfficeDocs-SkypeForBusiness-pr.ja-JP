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
ms.openlocfilehash: 5ca6823c1f3e8265f7b06ea0d175b58d42ef4a08
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42135744"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="backup-and-restoration-requirements-in-lync-server-2013-data"></a>Lync Server 2013 のバックアップと復元の要件: データ

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-03-26_

Lync Server は、データベースに格納されている設定と構成情報、およびデータベースおよびファイルストアに格納されているデータを使用します。 このトピックでは、組織で障害や停止が発生した場合にサービスを復元できるようにするためにバックアップする必要のあるデータについて説明します。また、個別にバックアップする必要がある Lync Server で使用されているデータとコンポーネントも識別します。

<div>

## <a name="settings-and-configuration-requirements"></a>設定と構成の要件

このトピックでは、Lync Server サービスの復旧に必要な設定と構成情報をバックアップおよび復元する手順について説明します。 構成情報は、中央管理ストアまたは別のバックエンドデータベースまたは Standard Edition サーバーにあります。

次の表に、バックアップと復元に必要な設定と構成情報を示します。

### <a name="settings-and-configuration-data"></a>設定と構成データ

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
<th>説明 / バックアップするタイミング</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>トポロジ構成情報</p></td>
<td><p>中央管理ストア (データベース: Xds)</p></td>
<td><p>トポロジ、ポリシー、および構成の設定。</p>
<p>通常のバックアップを使用してバックアップを行い、Lync Server コントロールパネルまたはコマンドレットを使用して構成またはポリシーを変更します。</p></td>
</tr>
<tr class="even">
<td><p>場所情報</p></td>
<td><p>中央管理ストア (データベース: Lis)</p></td>
<td><p>エンタープライズ VoIP Enhanced 9-1-1 (E9-1-1) 構成情報。この情報は一般に静的です。</p>
<p>定期的なバックアップによってバックアップします。</p></td>
</tr>
<tr class="odd">
<td><p>応答グループの構成情報</p></td>
<td><p>バックエンドサーバーまたは Standard Edition サーバー (データベース: RgsConfig)</p></td>
<td><p>応答グループのエージェントグループ、キュー、およびワークフロー。</p>
<p>定期的なバックアップのとき、およびエージェント グループ、キュー、またはワークフローを追加または変更した後でバックアップします。</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="data-requirements"></a>データの要件

ここでは、障害が発生した場合に Lync Server サービスを復元できるように、バックアップする必要がある Lync Server データの一覧を示します。

データの種類によっては、回復に必要でないものがあることに注意してください。 このトピックには、次のような種類のデータをバックアップする手順は含まれていません。

  - エンドポイントとサブスクリプション、アクティブな会議サーバー、一時的な会議状態など、一時的なユーザー データ (データベース: RtcDyn.mdf)

  - アドレス帳のデータ (データベース: Rtcab .mdf および Rtcab1.mdf)。 アドレス帳データベースは、Active Directory ドメインサービスから自動的に再生成されます。

  - コールパークアプリケーションの動的情報 (データベース: Cpsdyn.mdf)

  - エージェントのサインイン状態や通話待機情報 (データベース: Rgsdyn.mdf) など、一時的な応答グループのデータ

  - 常設チャット (データベース: お使いの場合) のコンプライアンスデータベース。 常設チャットコンプライアンスが有効になっている場合、データベースから情報を読み取って別の形式に変換するように構成されているアダプターを使用している限り、常設チャットコンプライアンスデータベースの情報は一時的なものになります。 そのため、常設チャットのコンプライアンスデータベースは一時的なものと見なされます。
    
    Lync Server 2013 常設チャットサーバーには、XML アダプターが付属しています。 また、このデータを受け取り、Exchange Hosted アーカイブなどの他のソースに移動するカスタムアダプターをインストールすることもできます。

次の表に、バックアップと復元に必要なデータを示します。

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
<th>説明 / バックアップするタイミング</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>永続的なユーザー データ</p></td>
<td><p>バックエンドサーバーまたは Standard Edition サーバー (データベース: RTCXDS. .mdf)</p></td>
<td><p>ユーザーの権限、ユーザーの連絡先リスト、サーバーまたはプール データ、予約された電話会議など。 このユーザー データには、会議にアップロードされたコンテンツは含まれません。</p>
<p>定期的なバックアップによってバックアップします。 この情報は動的ですが、最新の正規バックアップに復元する必要がある場合は、更新の損失が Lync Server にとって重大ではありません。 連絡先リストの重要性が高い組織では、このデータのバックアップの頻度を高めることができます。</p></td>
</tr>
<tr class="even">
<td><p>アーカイブ データ</p></td>
<td><p>アーカイブ データベース (データベース: LcsLog.mdf)</p>
<p>このデータは、Microsoft Exchange 統合オプションが有効になっている場合、Exchange 2013 に保存される場合があります。 それ以外の場合、このデータは Lync Server アーカイブデータベースに保持されます。これは、別の Lync Server データベースと併置されることもあれば、別のデータベースサーバー上にあるスタンドアロンでもかまいません。</p></td>
<td><p>インスタント メッセージング (IM) と会議のコンテンツ。</p>
<p>このデータは Lync Server にとって重要ではありませんが、規制を目的として組織にとって重要な場合があります。 適切にバックアップのスケジュールを判断します。</p></td>
</tr>
<tr class="odd">
<td><p>監視データ</p></td>
<td><p>監視データベース (LcsCDR.mdf および QoeMetrics.mdf)</p>
<p>これらのデータベースは、別の Lync Server データベースに併置されている場合もあれば、スタンドアロンの場合は別のデータベースサーバーに共存することもあります。</p></td>
<td><p>通話詳細レコード (LcsCDR .mdf) および QoE (Quality of Experience) 指標 (QoeMetrics)。</p>
<p>詳細通話記録は動的で、ビジネスにとって重大な場合があります。法令上の理由でこれらの記録が必要かどうかをふまえて、バックアップ スケジュールを判断します。</p>
<p>QoE 情報は動的です。 QoE データの損失は、Lync Server の操作にとって重要ではありませんが、ビジネスにとって重要な場合があります。 この情報が組織にとってどの程度重大かに基づいて、バックアップ スケジュールを判断します。</p></td>
</tr>
<tr class="even">
<td><p>常設チャットデータ</p></td>
<td><p>常設チャットデータベース (お持ちの場合)。</p>
<p>このデータベースは、別の Lync Server データベースと併置されている場合もあれば、独立したデータベースサーバーにスタンドアロンである場合もあります。</p></td>
<td><p>常設チャットデータは、チャットルームに投稿される実際のチャットコンテンツです。 このデータは、多くの場合、ビジネス上非常に重要です。</p>
<p>Lync Server に用意されている<strong>export-cspersistentchatdata</strong>コマンドレットを使用して、SQL Server バックアップを使用するか、データベースをエクスポートするかを選択できます。 データを回復するには、最後の完全バックアップの時点までデータベースをインポートして復元することができます。これは、データベースを障害点まで復元できないことを意味します。</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="file-store-data-requirements"></a>ファイル ストア データの要件

Enterprise Edition の展開では、Lync Server ファイルストアは通常、ファイルサーバー上にあります。 Standard Edition の展開では、Lync Server ファイルストアは既定で Standard Edition サーバーに配置されます。 通常、サイトに対して共有される Lync Server ファイルストアは1つです。 常設チャットのファイルストアは、Lync Server ファイルストアと同じファイル共有を使用します。

ファイルストアの場所は、 \\ \\サーバー\\共有名として識別されます。 ファイルストアの特定の場所を検索するには、トポロジビルダーを開き、[**ファイルストア**] ノードを探します。

次の表に、バックアップおよび復元する必要があるファイル ストアを示します。

### <a name="file-stores"></a>ファイル ストア

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
<th>説明 / バックアップするタイミング</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lync Server ファイル ストア</p></td>
<td><p>通常、ファイルサーバー、ファイルクラスター、または Standard Edition サーバー上で</p></td>
<td><p>会議コンテンツ、会議コンテンツのメタデータ、会議のコンプライアンスログ、アプリケーションデータファイル、デバイス更新のためのファイルの更新、応答グループのオーディオファイル、コールパーク、アナウンスアプリケーション、および常設チャットルームに投稿されたファイル。</p>
<p>定期的なバックアップによってバックアップします。</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="additional-backup-requirements"></a>追加のバックアップの要件

障害が発生した場合に Lync Server サービスを復元できるようにするには、Lync Server 自体に含まれていないいくつかの必要なコンポーネントをバックアップする必要があります。 次のコンポーネントは、このドキュメントで説明する Lync Server のバックアップと復元のプロセスの一環としてバックアップまたは復元されません。

  - **Active directory ドメインサービス**   Lync Server をバックアップするときに、active directory ツールを使用して AD DS をバックアップする必要があります。 Ad DS と Lync Server を同期させておくことが重要です。これは、Lync Server が AD DS 内の連絡先オブジェクトと一致しない場合に発生する問題を回避するためです。 AD DS は、Lync Server で使用される次の設定を格納します。
    
      - ユーザーの SIP URI と他のユーザー設定。
    
      - 応答グループや会議アテンダントなどのアプリケーションの連絡先オブジェクト。
    
      - 中央管理ストアへのポインター。
    
      - Kerberos 認証アカウント (オプションのコンピューターオブジェクト) と Lync Server セキュリティグループ。
    
    Windows Server 2008 での AD DS のバックアップと復元の詳細については、「」の「AD DS のバックアップと復元の[https://go.microsoft.com/fwlink/p/?linkId=209105](https://go.microsoft.com/fwlink/p/?linkid=209105)ステップバイステップガイド」を参照してください。

  - **証明機関と証明書**   は、組織のポリシーを使用して、証明機関 (CA) と証明書をバックアップします。 エクスポート可能な秘密キーを使用している場合は、証明書と秘密キーをバックアップしてから、このドキュメントの手順を使用して Lync Server を復元する場合は、それらをエクスポートすることができます。 内部 CA を使用している場合は、Lync Server を復元する必要がある場合に再登録できます。 秘密キーは、コンピューターで障害が発生した場合に使用できる安全な場所に保持しておくことが重要です。

  - **System center operations manager**   microsoft System center operations manager (旧称 microsoft Operations manager) を使用して lync server の展開を監視している場合は、lync server を監視している間に、必要に応じて、作成したデータをバックアップすることができます。 標準の SQL Server バックアッププロセスを使用して、System Center Operations Manager ファイルをバックアップします。 これらのファイルは復旧の際に復元されません。

  - **公衆交換電話網 (PSTN) ゲートウェイの構成**   エンタープライズ voip または存続可能ブランチアプライアンスを使用する場合は、PSTN ゲートウェイ構成をバックアップする必要があります。 PSTN ゲートウェイ構成のバックアップと復元の詳細については、ベンダーに確認してください。

  - **共存する lync server または office communications server**   のバージョン lync server 2013 の展開 coexists で lync server 2010 または以前のバージョンの office communications server が使用されている場合、このドキュメントの手順を使用して以前のバージョンのバックアップまたは復元を行うことはできません。 代わりに、該当のバージョンのドキュメントにあるバックアップと復元の手順に従う必要があります。 Lync Server 2010 のバックアップと復元の詳細について[https://go.microsoft.com/fwlink/p/?linkId=265417](https://go.microsoft.com/fwlink/p/?linkid=265417)は、「」を参照してください。 Microsoft Office Communications Server 2007 R2 のバックアップと復元の詳細について[https://go.microsoft.com/fwlink/p/?linkId=168162](https://go.microsoft.com/fwlink/p/?linkid=168162)は、「」を参照してください。

  - **インフラストラクチャ情報**   インフラストラクチャの構成、負荷分散の構成、インターネットインフォメーションサービス (IIS) の構成、ドメインネームシステム (DNS) レコードおよび IP アドレス、動的ホスト構成プロトコル (DHCP) の構成など、インフラストラクチャに関する情報をバックアップする必要があります。 これらのコンポーネントのバックアップの詳細については、それぞれのベンダーに確認してください。

  - ****   Microsoft exchange のドキュメントで説明されているように、microsoft exchange と exchange ユニファイドメッセージング (UM) のバックアップを行い、microsoft exchange と exchange UM を復元します。 Exchange Server 2013 のバックアップと復元の詳細について[https://go.microsoft.com/fwlink/?LinkId=285384](https://go.microsoft.com/fwlink/?linkid=285384)は、「」を参照してください。 Exchange Server 2010 のバックアップと復元の詳細について[https://go.microsoft.com/fwlink/p/?linkId=209179](https://go.microsoft.com/fwlink/p/?linkid=209179)は、「」を参照してください。
    
    Lync Server 2013 では、ユーザーの連絡先リスト、高精細定義のユーザー写真、および Exchange 2013 に格納されているアーカイブデータを持つことができることに注意してください。 これらの種類のデータをバックアップする方法については、次のリストを参照してください。
    
      - **高品位写真**は、Exchange Server バックアップの一部としてバックアップされます。
    
      - **統合連絡先ストア**は、Lync Server 2013 で導入されています。 統合連絡先ストアによって、ユーザーは Exchange 2013 ですべての連絡先情報を保持できます。
        
        ユーザーの連絡先が統合連絡先ストアまたは Lync バックエンドサーバーに保存されているかどうかに関して、バックアップが最新の状態になっていることを確認する必要があります。 次のシナリオでは、ユーザーの連絡先を統合連絡先ストアに移行すると、バックアップと復元のプロセスで問題が発生する可能性があることを示しています。
        
        **シナリオ 1:** ユーザーの連絡先が統合連絡先ストアに移行され、ユーザーの連絡先を移行する前に行われた Lync Server バックアップから復元を実行します。 このシナリオでは、Lync Server 移行タスクでユーザーの連絡先の Exchange への移行が開始されるまで、ユーザーは最大で1日前の状態になっています。 (ユーザーの連絡先は既に統合連絡先ストアに移行されているため、Exchange の連絡先情報が使用されることに注意してください)。 このシナリオでは、管理者の介入は必要ありません。
        
        **シナリオ 2:** ユーザーの連絡先は、以前に統合連絡先ストアに保存されていて、ロールバックされています。 ユーザーの連絡先が統合連絡先ストアに格納されている場合に実行される Lync Server バックアップから復元を実行します。 このシナリオでは、クライアントまたは`Error: Incorrect Exchange Version`その他の ss サーバーログでエラーメッセージが表示され、これが問題として示されることがあります。 ユーザーは、Exchange から直接 Lync 2013 の連絡先リストにアクセスできますが、クライアントの状態は Lync Server の状態とは一致しません。 この問題を解決するには、管理者は影響を受けるユーザーに対して**invoke-csucsrollback**コマンドレットを実行する必要があります。
    
      - **アーカイブデータ**は、Exchange 2013 に保存できます。 このデータは Lync Server にとって重要ではありませんが、規制を目的として組織にとって重要な場合があります。 アーカイブデータが Exchange に保存されており、組織にとって重要な場合は、Exchange のバックアップと復元の手順に従います。 Exchange に保存されているアーカイブデータを Lync Server に戻すことはできないことに注意してください。 また、Lync アーカイブデータベースに既に格納されているデータを Exchange に移動する方法はありません。

</div>

</div>

<span> </span>

</div>

</div>

</div>

