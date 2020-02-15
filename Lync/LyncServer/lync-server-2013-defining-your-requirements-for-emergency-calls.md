---
title: 'Lync Server 2013: 緊急電話の要件の定義'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Defining your requirements for emergency calls
ms:assetid: 5c12b517-9be6-41d0-83e2-11c78793620c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398404(v=OCS.15)
ms:contentKeyID: 48184276
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 61d388659a747cb8fed339a40a15abd8e33c693e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42032393"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="defining-your-requirements-for-emergency-calls-in-lync-server-2013"></a>Lync Server 2013 での緊急電話の要件の定義

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-06-06_

Microsoft Lync Server 2013 E9-1-1 展開を開始する前に、以下のセクションで説明する質問に回答することができます。 必要な計画は、展開する E9-1-1 ソリューションの種類 (SIP トランク E9-1-1 サービス プロバイダー、または緊急位置識別番号 (ELIN) ゲートウェイ) によって異なります。 次の表は、この計画ブックで確認する必要があるセクションをソリューションの種類別に示しています。

### <a name="planning-steps-by-type-of-e9-1-1-solution"></a>E9-1-1 ソリューションの種類別の計画手順

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>SIP トランク サービス プロバイダー</th>
<th>ELIN ゲートウェイ</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-defining-the-scope-of-the-e9-1-1-deployment.md">Lync Server 2013 での E9-1-1 展開の範囲の定義</a></p></td>
<td><p><a href="lync-server-2013-defining-the-scope-of-the-e9-1-1-deployment.md">Lync Server 2013 での E9-1-1 展開の範囲の定義</a></p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-defining-the-network-elements-used-to-determine-location.md">Lync Server 2013 での場所を決定するために使用するネットワーク要素の定義</a></p></td>
<td><p><a href="lync-server-2013-defining-the-network-elements-used-to-determine-location.md">Lync Server 2013 での場所を決定するために使用するネットワーク要素の定義</a></p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-enabling-users-for-e9-1-1.md">Lync Server 2013 での E9-1-1 のユーザーの有効化</a></p></td>
<td><p><a href="lync-server-2013-enabling-users-for-e9-1-1.md">Lync Server 2013 での E9-1-1 のユーザーの有効化</a></p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-managing-locations-for-sip-trunk-service-providers.md">Lync Server 2013 での SIP トランクサービスプロバイダーの場所の管理</a></p></td>
<td><p><a href="lync-server-2013-managing-locations-for-elin-gateways.md">Lync Server 2013 での ELIN ゲートウェイの場所の管理</a></p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-defining-the-user-experience-for-manually-acquiring-a-location.md">Lync Server 2013 で手動で場所を取得するためのユーザーの作業を定義する</a></p></td>
<td><p><a href="lync-server-2013-defining-the-user-experience-for-manually-acquiring-a-location.md">Lync Server 2013 で手動で場所を取得するためのユーザーの作業を定義する</a></p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-designing-the-sip-trunk-for-e9-1-1.md">Lync Server 2013 での E9-1-1 の SIP トランクの設計</a></p></td>
<td><p><a href="lync-server-2013-including-the-security-desk.md">Lync Server 2013 にセキュリティデスクを含める</a></p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-including-the-security-desk.md">Lync Server 2013 にセキュリティデスクを含める</a></p></td>
<td><p><a href="lync-server-2013-defining-the-location-policy.md">Lync Server 2013 の場所ポリシーの定義</a></p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-choosing-an-e9-1-1-service-provider.md">Lync Server 2013 の E9-1-1 サービスプロバイダーの選択</a></p></td>
<td><p><a href="lync-server-2013-assigning-location-policy-scope.md">Lync Server 2013 での場所ポリシーのスコープの割り当て</a></p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-defining-the-location-policy.md">Lync Server 2013 の場所ポリシーの定義</a></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-assigning-location-policy-scope.md">Lync Server 2013 での場所ポリシーのスコープの割り当て</a></p></td>
<td></td>
</tr>
</tbody>
</table>


<div>

## <a name="in-this-section"></a>このセクションの内容

  - [Lync Server 2013 での E9-1-1 展開の範囲の定義](lync-server-2013-defining-the-scope-of-the-e9-1-1-deployment.md)

  - [Lync Server 2013 での場所を決定するために使用するネットワーク要素の定義](lync-server-2013-defining-the-network-elements-used-to-determine-location.md)

  - [Lync Server 2013 での E9-1-1 のユーザーの有効化](lync-server-2013-enabling-users-for-e9-1-1.md)

  - [Lync Server 2013 での SIP トランクサービスプロバイダーの場所の管理](lync-server-2013-managing-locations-for-sip-trunk-service-providers.md)

  - [Lync Server 2013 での ELIN ゲートウェイの場所の管理](lync-server-2013-managing-locations-for-elin-gateways.md)

  - [Lync Server 2013 で手動で場所を取得するためのユーザーの作業を定義する](lync-server-2013-defining-the-user-experience-for-manually-acquiring-a-location.md)

  - [Lync Server 2013 での E9-1-1 の SIP トランクの設計](lync-server-2013-designing-the-sip-trunk-for-e9-1-1.md)

  - [Lync Server 2013 にセキュリティデスクを含める](lync-server-2013-including-the-security-desk.md)

  - [Lync Server 2013 の E9-1-1 サービスプロバイダーの選択](lync-server-2013-choosing-an-e9-1-1-service-provider.md)

  - [Lync Server 2013 の場所ポリシーの定義](lync-server-2013-defining-the-location-policy.md)

  - [Lync Server 2013 での場所ポリシーのスコープの割り当て](lync-server-2013-assigning-location-policy-scope.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

