---
title: 'Lync Server 2013: ディスク使用量のチェック'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Checking disk usage
ms:assetid: 0f0cb9bf-3f11-43ff-be10-5c8e1b5c4f08
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720908(v=OCS.15)
ms:contentKeyID: 63969578
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 791f4a0f9db56c38c837fa77b443d5aa6de74bd1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34840571"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="checking-disk-usage-in-lync-server-2013"></a>Lync Server 2013 でディスク使用量を確認する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2014-04-30_

ハードディスクドライブは、Lync Server 2013 展開の重要なコンポーネントです。 十分な空きディスク容量がなくても、オペレーティングシステムと Lync Server 2013 データベースは正しく機能しません。 サーバーのディスク領域が不足しないことを確認し、必要に応じてストレージリソースを追加するための準備として、Lync Server 2013 バックエンドデータベースの統計情報を毎日監視する必要があります。

オペレーティングシステム、プログラムファイル、データベース、トランザクションログ (Lync Server 2013 Back End) をホストしているディスクの空き領域を確認する以外に、次の重要なファイル共有のディスク領域を含むファイルシステムの使用状況を監視する必要があります。データ

  - 会議コンテンツ

  - 会議コンテンツのメタデータ

  - 会議のコンプライアンスログ

  - アプリケーションデータファイル (アプリケーションサーバーコンポーネントによって内部的に使用されます)

  - グループチャットサーバー web サービスとコンプライアンスフォルダ (グループチャット web サービスにアップロードされたファイルを保存する)

  - グループチャットのコンプライアンス XML ファイル (グループチャットのコンプライアンスレコードが含まれています)

  - ファイルを更新する (デバイス更新サービスの場合)

  - アドレス帳ファイル

Lync Server 2013 には、以前に一覧表示されているファイル共有のファイルに加えて、データベースとトランザクションログを保存するためのハードディスク領域が必要です。

記憶域リソースが不足しているため、Lync Server 2013 の展開に悪影響がないことを確認するために、ディスク領域を定期的に監視する必要があります。

Lync Server 2013 の各ボリュームで利用可能なディスク領域に関する統計情報を比較して維持し、データベースおよびトランザクションログファイルの増加量を求めます。 これは、記憶域リソースが必要なときに容量の計画や記憶域の追加を行うのに役立ちます。

トラブルシューティングと障害回復の状況に対応するために、使用可能な空きボリューム領域は、データベースのサイズの 110% 以上にすることをお勧めします。

次の方法を使用して、空きディスク領域を確認できます。

1.  **System center operations manager**   system center operations manager を使用すると、ボリューム領域が制約されている場合に管理者に警告を表示することができます。

2.  **スクリプトを実行**   すると、利用可能なハードディスク領域が 20% を下回った場合にメッセージが送信されるスクリプトが実行され、ディスク領域が監視されます。 TechNet の Microsoft Script Center でサンプルスクリプトを参照してください。次の点を確認してください。[http://gallery.technet.microsoft.com/scriptcenter/site/search?query=hard%20disk%20alert\&f%5B0%5D.Value=hard%20disk%20alert\&f%5B0%5D.Type=SearchText\&ac=5](http://gallery.technet.microsoft.com/scriptcenter/site/search?query=hard+disk+alert%26f%5b0%5d.value=hard+disk+alert%26f%5b0%5d.type=searchtext%26ac=5)

3.  **Windows エクスプローラー**   では、windows エクスプローラーを使用して、Lync Server 2013 のログとデータベースを格納するボリュームのディスク領域を確認します。

</div>

<span> </span>

</div>

</div>

</div>

