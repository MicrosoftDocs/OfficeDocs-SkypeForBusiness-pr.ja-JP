---
title: 'Lync Server 2013: 応答グループエージェントグループを管理する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Managing Response Group agent groups
ms:assetid: 36084cdc-38f1-4c45-922f-f81c7e86210c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520976(v=OCS.15)
ms:contentKeyID: 48183806
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c6cbea3b1a0d6638206a022ce5aded610dd60f23
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34827845"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="managing-response-group-agent-groups-in-lync-server-2013"></a>Lync Server 2013 での応答グループエージェントグループの管理

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-10-01_

エージェントグループは、応答グループへの通話に応答するように指定されているユーザーのグループで構成されます。 エージェントグループを作成するときは、グループに割り当てられているエージェントを選択し、ルーティング方法や、エージェントがグループに対してサインインまたはサインアウトできるかどうかなど、その他のグループ設定を指定します。

<div>


> [!NOTE]  
> ユーザーをエージェントグループに追加する前に、ユーザーをエンタープライズ Voip 用に有効にしておく必要があります。 エンタープライズ Voip のユーザーを有効にする方法の詳細については、「 <A href="lync-server-2013-enable-users-for-enterprise-voice.md">Lync Server 2013 でエンタープライズ voip のユーザーを有効</A>にする」を参照してください。



</div>

<div>


> [!NOTE]  
> エージェントにできるのは社内ユーザーのみです。 エージェントがオンプレミスからオンラインに移行された場合、応答グループの呼び出しはそのエージェントにルーティングされません。



</div>

グループからサインアウトする必要があるエージェントは、Lync Server のサインインまたはサインアウトとは異なり、*正式なエージェント*と呼ばれます。 正式なエージェントは、グループに転送された通話を受信する前に、グループにサインインしている必要があります。 これは、パートタイム ベースでグループから通話に応答するエージェントには便利な方法です。 正式なエージェントは、Lync 2013 のメニュー項目をクリックして、Windows Internet Explorer のインターネットブラウザーを開き、web ページ本体を表示することによって、グループにサインインおよびサインアウトします。

グループにサインインしていないか、グループからサインアウトしていないエージェントは、"*非公式のエージェント*" と呼ばれます。 非公式のエージェントは、Lync Server へのサインイン時にグループに自動的にサインインされ、グループからサインアウトすることはできません。

<div>


> [!IMPORTANT]  
> ユーザーを応答グループ エージェントとして割り当てる場合、ユーザーがプライバシー モードを有効にしているのであれば、"RGS Presence Watcher" 連絡先を検索して連絡先リストに追加する必要があることを伝えてください。プライバシー モードを有効にしているが連絡先リストに RGS Presence Watcher がないエージェントは、応答グループに対する通話を受信できません。プライバシー モードを有効にしていないエージェントは、影響されません。



</div>

<div>

## <a name="in-this-section"></a>このセクション中

  - [Lync Server 2013 でエージェントグループを作成または変更する](lync-server-2013-create-or-modify-an-agent-group.md)

  - [Lync Server 2013 でエージェントグループを削除する](lync-server-2013-delete-an-agent-group.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

