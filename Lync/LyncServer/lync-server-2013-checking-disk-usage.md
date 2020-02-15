---
title: 'Lync Server 2013: ディスク使用状況のチェック'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Checking disk usage
ms:assetid: 0f0cb9bf-3f11-43ff-be10-5c8e1b5c4f08
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720908(v=OCS.15)
ms:contentKeyID: 63969578
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8532b15ac45033d966c772e6ab23403d709ed790
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42045679"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="checking-disk-usage-in-lync-server-2013"></a>Lync Server 2013 でのディスク使用率のチェック

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2014-04-30_

ハードディスクドライブは、Lync Server 2013 展開の重要なコンポーネントです。 十分な空きディスクボリュームがない場合は、オペレーティングシステムと Lync Server 2013 データベースのどちらも正常に機能しません。 サーバーのディスク領域が不足しないようにするため、および必要に応じてストレージリソースを追加する準備を行うには、Lync Server 2013 バックエンドデータベース統計を毎日監視する必要があります。

オペレーティングシステム、プログラムファイル、データベース、およびトランザクションログ (Lync Server 2013 のバックエンド) をホストしているディスクの領域をチェックする以外に、次の重要なファイル共有のディスク領域を含むファイルシステムの使用状況を監視する必要があります。情報

  - ミーティング コンテンツ

  - 会議コンテンツのメタデータ

  - 会議のコンプライアンスログ

  - アプリケーションデータファイル (アプリケーションサーバーコンポーネントによって内部で使用される)

  - グループチャットサーバーの web サービスおよびコンプライアンスフォルダー (グループチャット web サービスにアップロードされたファイルを格納する)

  - グループチャットコンプライアンス XML ファイル (グループチャットコンプライアンスレコードを含む)

  - ファイルを更新する (デバイス更新サービスの場合)

  - アドレス帳ファイル

Lync Server 2013 には、以前に一覧表示されているファイル共有上のファイルに加えて、そのデータベースとトランザクションログを格納するためのハードディスクの空き領域が必要です。

ディスク領域を定期的に監視して、ストレージリソースが不足しているために Lync Server 2013 の展開が悪影響を受けないようにする必要があります。

各 Lync Server 2013 ボリューム、およびデータベースとトランザクションログファイルの予想される容量の増加に関する統計情報を比較して管理します。 これにより、ストレージリソースが必要になったときの容量計画とストレージの追加に役立てることができます。

トラブルシューティングと障害復旧の状況に対応するために、使用可能な空きボリューム容量は、データベースのサイズの110% 以上にすることをお勧めします。

次の方法を使用して、空きディスク領域を確認できます。

1.  **System center operations manager**   system center operations manager を使用して、ボリューム容量が制限されている場合に管理者に警告を発することができます。

2.  **スクリプトを実行**   して、使用可能なハードディスクの空き容量が20% を下回った場合にメッセージを送信するスクリプトを実行することによって、ディスク領域を監視します。 TechNet の Microsoft Script Center でサンプルスクリプトを確認するには、次の点を確認してください。[http://gallery.technet.microsoft.com/scriptcenter/site/search?query=hard%20disk%20alert\&f%5B0%5D.Value=hard%20disk%20alert\&f%5B0%5D.Type=SearchText\&ac=5](http://gallery.technet.microsoft.com/scriptcenter/site/search?query=hard+disk+alert%26f%5b0%5d.value=hard+disk+alert%26f%5b0%5d.type=searchtext%26ac=5)

3.  **エクスプローラーで**   は、windows エクスプローラーを使用して、Lync Server 2013 のログおよびデータベースを格納するボリューム上のディスク領域をチェックします。

</div>

<span> </span>

</div>

</div>

</div>

