---
title: 'Lync Server 2013: アーカイブの新機能'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: New Archiving features
ms:assetid: c002e367-41ad-498d-9d23-8b117ac435b2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205225(v=OCS.15)
ms:contentKeyID: 48185288
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d736e823892aa6d6edcc5ab90df900a5c6b7ac79
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34826291"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="new-archiving-features-in-lync-server-2013"></a>Lync Server 2013 のアーカイブの新機能

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-10-09_

Lync Server 2013 でアーカイブすると、次の種類のコンテンツをアーカイブできます。

  - ピアツーピアのインスタント メッセージ

  - マルチパーティのインスタントメッセージである会議 (会議)

  - アップロードされたコンテンツ (配付資料など) およびイベント関連のコンテンツ (参加、退席、アップロード、共有、表示設定の変更など) を含む会議コンテンツ

さらに、Lync Server 2013 でアーカイブすると、展開と運用の効率を向上させるための新機能が提供されます。 次の新機能が含まれています。

  - **フロントエンドサーバー上のアーカイブの collocation。**   Lync server 2013 には、別のアーカイブサーバーの役割がありません。 アーカイブは、Enterprise Edition の展開におけるすべてのフロントエンドサーバーと、プールまたはサイト用に構成できる標準エディションのサーバーで利用できるオプションの機能です。

  - **Microsoft Exchange の統合。**   アーカイブを展開するときに、exchange 2013 を使用しているすべてのユーザーに対して、既存の exchange 2013 ストレージを使用してアーカイブするデータストレージを統合することができます。そのため、別の SQL Server を展開する必要はありません。Lync データをアーカイブするデータベース。 Exchange 2013 を展開していない場合、または統合したくない場合、または、Exchange 2013 を使用していない Lync 2013 ユーザーがメールボックスをインプレースホールドしている場合は、SQL Server を使用して別のアーカイブデータベースを展開することができます。e Lync コミュニケーションからデータをアーカイブします。 Microsoft exchange 統合と Lync Server 2013 アーカイブデータベースの両方を使用できますが、展開内のすべてのユーザーに対して、Microsoft Exchange 統合を使用することができます。 インプレースホールドの詳細については、「インプレースホールド」を参照し[http://go.microsoft.com/fwlink/p/?LinkId=267500](http://go.microsoft.com/fwlink/p/?linkid=267500)てください。

  - **SQL ストアのミラーリング。**   アーカイブを展開するときに、アーカイブデータベースに対して SQL Server データベースのミラーリングを有効にすることができます。

  - **ホワイトボードと投票のアーカイブ。**   アーカイブされた会議コンテンツには、会議中に共有されるホワイトボードと投票が含まれるようになりました。

次の種類のコンテンツはアーカイブされません。

  - ピアツーピアのファイル転送

  - ピアツーピアのインスタント メッセージおよび会議の音声ビデオ

  - ピアツーピアインスタントメッセージ (im) と会議のアプリケーション共有

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 のアーカイブの計画](lync-server-2013-planning-for-archiving.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

