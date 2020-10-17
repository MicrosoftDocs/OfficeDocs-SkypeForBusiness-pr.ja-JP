---
title: 残りのユーザーを Lync Server 2013 に移動する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Move remaining users to Lync Server 2013
ms:assetid: 72025e1b-97d1-40e9-8a98-28c018942b48
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688090(v=OCS.15)
ms:contentKeyID: 49733689
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 966182705fd3f18bfa10d1d6042e1c3c94204e9e
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48500214"
---
# <a name="move-remaining-users-to-lync-server-2013"></a>残りのユーザーを Lync Server 2013 に移動する

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-09-29_

Lync Server コントロールパネルまたは Lync Server 管理シェルを使用して、ユーザーを新しい Lync Server 2013 展開に移動することができます。 Lync Server 2013 にスムーズに移行できるようにするには、いくつかの要件を満たす必要があります。 このトピックの手順を完了するための前提条件の詳細については、「 [Configure clients for migration](configure-clients-for-migration.md)」を参照してください。 ユーザーの移動の詳細な手順については、「 [フェーズ 4: テストユーザーをパイロットプールに移動する](phase-4-move-test-users-to-the-pilot-pool.md)」を参照してください。

<div>


> [!IMPORTANT]  
> Active Directory ユーザーとコンピュータースナップインまたは Lync Server 2010 管理ツールを使用して、レガシ環境から Lync Server 2013 にユーザーを移動することはできません。



</div>

ユーザーを Lync Server 2013 プールに移動すると、そのユーザーのデータは、新しいプールに関連付けられたバックエンドデータベースに移動されます。

<div>


> [!IMPORTANT]  
> これには、レガシ ユーザーによって作成されたアクティブな会議が含まれます。 たとえば、従来のユーザーが <STRONG>会議</STRONG> の会議を構成している場合は、ユーザーが移動された後も、新しい Lync Server 2013 プールでその会議を利用できます。 会議へのアクセスに使用する<STRONG>会議 URL と電話会議 ID</STRONG> も同じです。 唯一の違いは、会議が lync server 2010 プールではなく Lync Server 2013 プールでホストされるようになったことです。



</div>

<div>


> [!NOTE]  
> Lync Server 2013 上のホームユーザーは、アップグレードされたクライアントを同時に展開する必要はありません。 クライアントが新しいクライアント ソフトウェアにアップグレードされている場合に限り、ユーザーは新しい機能を使用できます。



</div>

<div>

## <a name="post-migration-task"></a>移行後のタスク

1.  ユーザーを移動した後、ユーザーに割り当てられている会議ポリシーを確認します。

2.  Lync server 2013 に所属するユーザーによって開催された会議が、Lync Server 2010 に所属しているフェデレーションユーザーとシームレスに機能するようにするには、移行したユーザーに割り当てられている会議ポリシーで匿名の参加者を許可する必要があります。

3.  匿名参加者に許可されている会議ポリシーによって、Lync server 2013 コントロールパネルで選択した**匿名ユーザーの招待を参加者に許可**し、Lync Server 管理シェルの**get-csconferencingpolicy**コマンドレットの出力で**AllowAnonymousParticipantsInMeetings**を**True**に設定しました。

4.  Lync Server 管理シェルを使用した会議ポリシーの構成の詳細については、「Lync Server Management Shell」のドキュメントの「 [get-csconferencingpolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsConferencingPolicy) 」を参照してください。

</div>

</div>

<span> </span>

</div>

</div>

</div>

