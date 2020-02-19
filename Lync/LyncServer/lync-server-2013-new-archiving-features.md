---
title: 'Lync Server 2013: 新しいアーカイブ機能'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: New Archiving features
ms:assetid: c002e367-41ad-498d-9d23-8b117ac435b2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205225(v=OCS.15)
ms:contentKeyID: 48185288
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3e09284d78ead2e8cd4249c2dc54159284ddad43
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42127650"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="new-archiving-features-in-lync-server-2013"></a>Lync Server 2013 の新しいアーカイブ機能

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-10-09_

Lync Server 2013 のアーカイブでは、次の種類のコンテンツをアーカイブできます。

  - ピアツーピア インスタント メッセージ

  - マルチパーティのインスタント メッセージである電話会議 (ミーティング)

  - アップロードされたコンテンツ (配布資料など) およびイベント関連のコンテンツ (参加、退出、アップロード、共有、表示設定の変更など) を含む電話会議コンテンツ

さらに、Lync Server 2013 のアーカイブには、展開と運用の効率を向上させる新機能が用意されています。 これらの新機能には、次のものがあります。

  - **フロントエンドサーバー上のアーカイブの併置。**   Lync server 2013 には、別のアーカイブサーバーの役割がありません。 アーカイブは、Enterprise Edition 展開のすべてのフロントエンド サーバーおよび Standard Edition サーバーにインストールできるオプションの機能であり、プールまたはサイトに対する構成として実装できます。

  - **Microsoft Exchange 統合。**   アーカイブを展開するときに、exchange 2013 に所属していてメールボックスがインプレース保持されているすべてのユーザーに対して、既存の exchange 2013 ストレージとのアーカイブ用のデータストレージを統合することができます。したがって、個別の SQL Server データベースを展開して Lync データをアーカイブする必要はありません。 Exchange 2013 を展開していない場合、または統合しない場合、または Exchange 2013 に所属していない Lync 2013 ユーザーがメールボックスをインプレース保持に設定している場合は、SQL Server を使用して個別のアーカイブデータベースを管理することができます。Lync communications からアーカイブされたデータ。 Microsoft exchange 統合と Lync Server 2013 アーカイブデータベースの両方を使用することができますが、展開内の一部のユーザーに対して Microsoft Exchange 統合を使用する必要があります。 インプレース保持の詳細については、「」の「インプレースホールド」 [https://go.microsoft.com/fwlink/p/?LinkId=267500](https://go.microsoft.com/fwlink/p/?linkid=267500)を参照してください。

  - **SQL ストアのミラーリング。**   アーカイブを展開するときに、アーカイブデータベースに対して SQL Server データベースのミラーリングを有効にすることができます。

  - **ホワイトボードと投票のアーカイブ。**   アーカイブされた会議コンテンツに、会議中に共有されるホワイトボードと投票が含まれるようになりました。

次の種類のコンテンツはアーカイブされません。

  - ピアツーピア ファイル転送

  - ピアツーピア インスタント メッセージおよび電話会議のオーディオ/ビデオ

  - ピアツーピア インスタント メッセージおよび電話会議のアプリケーション共有

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 でのアーカイブの計画](lync-server-2013-planning-for-archiving.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

