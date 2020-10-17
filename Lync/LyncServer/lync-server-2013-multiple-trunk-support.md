---
title: 'Lync Server 2013: 複数のトランクのサポート'
description: 'Lync Server 2013: 複数のトランクのサポート。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Multiple trunk support
ms:assetid: a1309c09-ad9a-4c54-9650-4e3f5b2a4a00
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205127(v=OCS.15)
ms:contentKeyID: 48184948
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3bbabb90405b3fdae47a59ba8a0798743943216d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48552423"
---
# <a name="multiple-trunk-support-in-lync-server-2013"></a>Lync Server 2013 での複数トランクのサポート

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-11-01_

Lync Server 2013 機能は、ゲートウェイと仲介サーバー間の複数の関連付けをサポートします。 これらの関連付けは、仲介サーバープールと公衆交換電話網 (PSTN) ゲートウェイ、セッションボーダーコントローラー (SBC)、または ip-pbx との間の論理的な関連付けであるトランクを定義することによって行われます。 トポロジビルダーを使用して、ゲートウェイを仲介サーバー (つまり、トランク) に関連付けます。

  - Lync Server 2013 でトランクを割り当てるまたは削除するには、まず、トポロジビルダーでトランクを定義する必要があります。 トランクは、仲介サーバーの完全修飾ドメイン名 (FQDN)、仲介サーバーのリッスンポート、ゲートウェイ FQDN、ゲートウェイリッスンポートという関連付けで構成されます。

  - 複数のトランクを構成するには、同じゲートウェイと仲介サーバーの間に複数の関連付けを作成できます。 これにより、エンタープライズ Voip インフラストラクチャの弾力性が向上します。これは、構内交換 (PBX) 間の運用シナリオで特に役立ちます。

トランクが定義されている場合は、ルートに関連付けられている必要があります。 トランクをルートに関連付けるには、トポロジビルダーでトランクの簡単な名前を定義します。 この単純な名前は、Lync Server コントロールパネルでのトランク名として使用されます。ここで、トランクはルートに関連付けることができます。 単純なトランク名は、Lync Server 管理シェルからのゲートウェイ名として使用されます。

    New-CsVoiceRoute -Identity <RouteId> -NumberPattern <String> -PstnUsages @{add="<UsageString>"} -PstnGatewayList @{add="<TrunkSimpleName>"}

管理者は、仲介サーバーに関連付けられている既定のトランクを選択する必要があります。 トポロジビルダーで、関連付けられている仲介サーバーを右クリックし、[ **プロパティ**] をクリックします。 仲介サーバーの既定のゲートウェイを指定します。

次の図は、各仲介サーバーとゲートウェイに対して定義されている複数のトランクを示しています。

**M-N トランクルーティング**

![複数のトランクの割り当て。](images/JJ205127.c61cd9a7-d8d9-4e02-83b9-ab62519a48c4(OCS.15).jpg "複数のトランクの割り当て。")

</div>

<span> </span>

</div>

</div>

</div>

