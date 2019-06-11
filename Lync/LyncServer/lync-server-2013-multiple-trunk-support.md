---
title: 'Lync Server 2013: 複数のトランクのサポート'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Multiple trunk support
ms:assetid: a1309c09-ad9a-4c54-9650-4e3f5b2a4a00
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205127(v=OCS.15)
ms:contentKeyID: 48184948
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 156db04ceb26809c7043f30e9e01ea0071e0a31d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34826543"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="multiple-trunk-support-in-lync-server-2013"></a>Lync Server 2013 での複数のトランクのサポート

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-11-01_

Lync Server 2013 機能は、ゲートウェイと仲介サーバー間の複数の関連付けをサポートしています。 これらの関連付けは、仲介サーバープールと公衆交換電話網 (PSTN) ゲートウェイ、セッション境界コントローラー (SBC)、または ip-pbx との間の論理的な関連付けであるトランクを定義することによって行われます。 トポロジビルダーを使用して、ゲートウェイを仲介サーバーに関連付けます (つまり、trunks)。

  - Lync Server 2013 でトランクを割り当てまたは削除するには、まず、トポロジビルダーで樹幹を定義する必要があります。 トランクは、仲介サーバーの完全修飾ドメイン名 (FQDN)、仲介サーバーのリッスンポート、ゲートウェイの FQDN、ゲートウェイのリスニングポートで構成されます。

  - 複数の trunks を構成するために、同じゲートウェイと仲介サーバー間に複数の関連付けを作成することができます。 これにより、エンタープライズ Voip インフラストラクチャのさらなる弾力性が提供されます。これは、プライベート支店交換 (PBX) 間の運用シナリオで特に便利です。

トランクが定義されている場合は、ルートに関連付ける必要があります。 トランクをルートに関連付けるには、トポロジビルダーでトランクの単純な名前を定義します。 この簡易名は、Lync Server コントロールパネルでトランク名として使用されます。ここでは、trunks をルートに関連付けることができます。 簡単なトランク名は、Lync Server 管理シェルからのゲートウェイ名として使用されます。

    New-CsVoiceRoute -Identity <RouteId> -NumberPattern <String> -PstnUsages @{add="<UsageString>"} -PstnGatewayList @{add="<TrunkSimpleName>"}

管理者は、仲介サーバーに関連付けられている既定のトランクを選択する必要があります。 トポロジビルダーで、関連する仲介サーバーを右クリックし、[**プロパティ**] をクリックします。 仲介サーバーの既定のゲートウェイを指定します。

次の図は、各仲介サーバーとゲートウェイに対して定義されている複数の trunks を示しています。

**M-N トランクルーティング**

![複数のトランクの割り当て。](images/JJ205127.c61cd9a7-d8d9-4e02-83b9-ab62519a48c4(OCS.15).jpg "複数のトランクの割り当て。")

</div>

<span> </span>

</div>

</div>

</div>

