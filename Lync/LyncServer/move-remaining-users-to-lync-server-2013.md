---
title: Lync Server 2013 への残りのユーザーの移動
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
ms.openlocfilehash: 4d60b3ba622e88978a8bbf555972c95979e8f8c3
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41743757"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="move-remaining-users-to-lync-server-2013"></a>Lync Server 2013 への残りのユーザーの移動

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-09-29_

Lync Server コントロールパネルまたは Lync Server 管理シェルを使用して、ユーザーを新しい Lync Server 2013 の展開に移動することができます。 Lync Server 2013 にスムーズに移行するためには、いくつかの要件を満たしている必要があります。 このトピックの手順を完了するための前提条件の詳細については、「[移行のためにクライアントを構成](configure-clients-for-migration.md)する」を参照してください。 ユーザーの移動の詳細な手順については、「[フェーズ 4: テストユーザーをパイロットプールに移動する](phase-4-move-test-users-to-the-pilot-pool.md)」を参照してください。

<div>


> [!IMPORTANT]  
> Active Directory ユーザーとコンピューターのスナップインまたは Lync Server 2010 管理ツールを使用して、ユーザーを従来の環境から Lync Server 2013 に移動することはできません。



</div>

ユーザーを Lync Server 2013 プールに移動すると、そのユーザーのデータは、新しいプールに関連付けられているバックエンドデータベースに移動されます。

<div>


> [!IMPORTANT]  
> これには、従来のユーザーによって作成されたアクティブな会議も含まれます。 たとえば、従来のユーザーが<STRONG>会議</STRONG>用の会議を構成している場合は、ユーザーが移動された後も、新しい Lync Server 2013 プールでその会議を利用できます。 会議にアクセスするための詳細は、会議の<STRONG>URL と会議 ID と</STRONG>同じである必要があります。 唯一の違いは、会議が lync server 2013 プールでホストされており、Lync Server 2010 プールではホストされていないことです。



</div>

<div>


> [!NOTE]  
> Lync Server 2013 のホームユーザーは、アップグレードされたクライアントを展開する必要はありません。 新しい機能は、ユーザーが新しいクライアントソフトウェアにアップグレードした場合にのみ利用可能になります。



</div>

<div>

## <a name="post-migration-task"></a>移行後の作業

1.  ユーザーを移動した後、それらに割り当てられている会議ポリシーを確認します。

2.  Lync Server 2013 を使っているユーザーによって開催された会議が、Lync Server 2010 を使用しているフェデレーションユーザーとシームレスに動作するようにするには、移行したユーザーに割り当てられている会議ポリシーで、匿名の参加者を許可する必要があります。

3.  匿名の参加者を許可する会議ポリシーでは、Lync server 2013 コントロールパネルで選択された**匿名ユーザーの招待を許可**することができます。また、Lync Server 管理シェルの**set-csconferencingpolicy**コマンドレットの出力で**AllowAnonymousParticipantsInMeetings**を**True**に設定します。

4.  Lync Server 管理シェルを使用して会議ポリシーを構成する方法の詳細については、「Lync Server 管理シェルドキュメントの[set-csconferencingpolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsConferencingPolicy) 」を参照してください。

</div>

</div>

<span> </span>

</div>

</div>

</div>

