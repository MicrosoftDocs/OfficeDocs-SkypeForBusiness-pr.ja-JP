---
title: 'Lync Server 2013: 応答グループエージェントグループの管理'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing Response Group agent groups
ms:assetid: 36084cdc-38f1-4c45-922f-f81c7e86210c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520976(v=OCS.15)
ms:contentKeyID: 48183806
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f791ea6a2091ab50e159b541ef19789ffcde02b4
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2020
ms.locfileid: "41992172"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="managing-response-group-agent-groups-in-lync-server-2013"></a>Lync Server 2013 での応答グループエージェントグループの管理

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-10-01_

エージェント グループは、応答グループへの通話に応答するように指定されているユーザーのグループから構成されます。エージェント グループを作成するときは、そのグループに割り当てるエージェントを選択し、詳細なグループ設定 (ルーティング方法、エージェントがグループにサインイン/サインアウトするかどうかなど) を指定します。

<div>


> [!NOTE]  
> ユーザーをエージェントグループに追加するには、事前にエンタープライズ Voip を有効にする必要があります。 エンタープライズ Voip に対してユーザーを有効にする方法の詳細については、「 <A href="lync-server-2013-enable-users-for-enterprise-voice.md">enable users For Enterprise voice In Lync Server 2013</A>」を参照してください。



</div>

<div>


> [!NOTE]  
> 社内ユーザーのみがエージェントであることができます。エージェントが社内からオンラインに移動した場合、応答グループ呼び出しはそのエージェントに送られません。



</div>

グループにサインインまたは拒否する必要があるエージェント (Lync Server のサインイン時またはログアウト時とは異なる) は、*正式なエージェント*と呼ばれます。 公式エージェントが、グループにルーティングされた着信を受信するには、そのグループにサインインする必要があります。 これは、パートタイム ベースでグループから通話に応答するエージェントには便利な方法です。 正式なエージェント Lync 2013 のメニュー項目をクリックして、Windows Internet Explorer の Internet browser を開き、web ページコンソールを表示することによって、グループにサインインおよびサインアウトします。

グループにサインインしていない、またはグループ外にいるエージェントは、*非公式なエージェント*と呼ばれます。 非公式のエージェントは、Lync Server にサインインするときにグループに自動的にサインインします。グループからサインアウトすることはできません。

<div>


> [!IMPORTANT]  
> ユーザーを応答グループ エージェントとして割り当てる場合、ユーザーがプライバシー モードを有効にしているのであれば、"RGS Presence Watcher" 連絡先を検索して連絡先リストに追加する必要があることを通知してください。プライバシー モードを有効にしているが連絡先リストに RGS Presence Watcher がないエージェントは、応答グループに対する通話を受信できません。プライバシー モードを有効にしていないエージェントは、影響されません。



</div>

<div>

## <a name="in-this-section"></a>このセクションの内容

  - [Lync Server 2013 でエージェントグループを作成または変更する](lync-server-2013-create-or-modify-an-agent-group.md)

  - [Lync Server 2013 でエージェントグループを削除する](lync-server-2013-delete-an-agent-group.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

