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
ms.openlocfilehash: 2d190d240db85016bd13bfd2480b42b088ca5f88
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48504364"
---
# <a name="defining-your-requirements-for-emergency-calls-in-lync-server-2013"></a><span data-ttu-id="7a320-102">Lync Server 2013 での緊急電話の要件の定義</span><span class="sxs-lookup"><span data-stu-id="7a320-102">Defining your requirements for emergency calls in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7a320-103">_**トピックの最終更新日:** 2012-06-06_</span><span class="sxs-lookup"><span data-stu-id="7a320-103">_**Topic Last Modified:** 2012-06-06_</span></span>

<span data-ttu-id="7a320-104">Microsoft Lync Server 2013 E9-1-1 展開を開始する前に、以下のセクションで説明する質問に回答することができます。</span><span class="sxs-lookup"><span data-stu-id="7a320-104">Before you begin a Microsoft Lync Server 2013 E9-1-1 deployment, you should first be able to answer the questions detailed in the following sections.</span></span> <span data-ttu-id="7a320-105">必要な計画は、展開する E9-1-1 ソリューションの種類 (SIP トランク E9-1-1 サービス プロバイダー、または緊急位置識別番号 (ELIN) ゲートウェイ) によって異なります。</span><span class="sxs-lookup"><span data-stu-id="7a320-105">The planning you need to do depends on the type of E9-1-1 solution that you choose to deploy—a SIP trunk E9-1-1 service provider or an Emergency Location Identification Number (ELIN) gateway.</span></span> <span data-ttu-id="7a320-106">次の表は、この計画ブックで確認する必要があるセクションをソリューションの種類別に示しています。</span><span class="sxs-lookup"><span data-stu-id="7a320-106">The following table identifies the sections in this planning workbook that you’ll need to review for each of those solutions.</span></span>

### <a name="planning-steps-by-type-of-e9-1-1-solution"></a><span data-ttu-id="7a320-107">E9-1-1 ソリューションの種類別の計画手順</span><span class="sxs-lookup"><span data-stu-id="7a320-107">Planning Steps by Type of E9-1-1 Solution</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7a320-108">SIP トランク サービス プロバイダー</span><span class="sxs-lookup"><span data-stu-id="7a320-108">SIP trunk service provider</span></span></th>
<th><span data-ttu-id="7a320-109">ELIN ゲートウェイ</span><span class="sxs-lookup"><span data-stu-id="7a320-109">ELIN gateway</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7a320-110"><a href="lync-server-2013-defining-the-scope-of-the-e9-1-1-deployment.md">Lync Server 2013 での E9-1-1 展開の範囲の定義</a></span><span class="sxs-lookup"><span data-stu-id="7a320-110"><a href="lync-server-2013-defining-the-scope-of-the-e9-1-1-deployment.md">Defining the scope of the E9-1-1 deployment in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="7a320-111"><a href="lync-server-2013-defining-the-scope-of-the-e9-1-1-deployment.md">Lync Server 2013 での E9-1-1 展開の範囲の定義</a></span><span class="sxs-lookup"><span data-stu-id="7a320-111"><a href="lync-server-2013-defining-the-scope-of-the-e9-1-1-deployment.md">Defining the scope of the E9-1-1 deployment in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7a320-112"><a href="lync-server-2013-defining-the-network-elements-used-to-determine-location.md">Lync Server 2013 での場所を決定するために使用するネットワーク要素の定義</a></span><span class="sxs-lookup"><span data-stu-id="7a320-112"><a href="lync-server-2013-defining-the-network-elements-used-to-determine-location.md">Defining the network elements used to determine location in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="7a320-113"><a href="lync-server-2013-defining-the-network-elements-used-to-determine-location.md">Lync Server 2013 での場所を決定するために使用するネットワーク要素の定義</a></span><span class="sxs-lookup"><span data-stu-id="7a320-113"><a href="lync-server-2013-defining-the-network-elements-used-to-determine-location.md">Defining the network elements used to determine location in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7a320-114"><a href="lync-server-2013-enabling-users-for-e9-1-1.md">Lync Server 2013 での E9-1-1 のユーザーの有効化</a></span><span class="sxs-lookup"><span data-stu-id="7a320-114"><a href="lync-server-2013-enabling-users-for-e9-1-1.md">Enabling users for E9-1-1 in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="7a320-115"><a href="lync-server-2013-enabling-users-for-e9-1-1.md">Lync Server 2013 での E9-1-1 のユーザーの有効化</a></span><span class="sxs-lookup"><span data-stu-id="7a320-115"><a href="lync-server-2013-enabling-users-for-e9-1-1.md">Enabling users for E9-1-1 in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7a320-116"><a href="lync-server-2013-managing-locations-for-sip-trunk-service-providers.md">Lync Server 2013 での SIP トランクサービスプロバイダーの場所の管理</a></span><span class="sxs-lookup"><span data-stu-id="7a320-116"><a href="lync-server-2013-managing-locations-for-sip-trunk-service-providers.md">Managing locations for SIP trunk service providers in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="7a320-117"><a href="lync-server-2013-managing-locations-for-elin-gateways.md">Lync Server 2013 での ELIN ゲートウェイの場所の管理</a></span><span class="sxs-lookup"><span data-stu-id="7a320-117"><a href="lync-server-2013-managing-locations-for-elin-gateways.md">Managing locations for ELIN gateways in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7a320-118"><a href="lync-server-2013-defining-the-user-experience-for-manually-acquiring-a-location.md">Lync Server 2013 で手動で場所を取得するためのユーザーの作業を定義する</a></span><span class="sxs-lookup"><span data-stu-id="7a320-118"><a href="lync-server-2013-defining-the-user-experience-for-manually-acquiring-a-location.md">Defining the user experience for manually acquiring a location in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="7a320-119"><a href="lync-server-2013-defining-the-user-experience-for-manually-acquiring-a-location.md">Lync Server 2013 で手動で場所を取得するためのユーザーの作業を定義する</a></span><span class="sxs-lookup"><span data-stu-id="7a320-119"><a href="lync-server-2013-defining-the-user-experience-for-manually-acquiring-a-location.md">Defining the user experience for manually acquiring a location in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7a320-120"><a href="lync-server-2013-designing-the-sip-trunk-for-e9-1-1.md">Lync Server 2013 での E9-1-1 の SIP トランクの設計</a></span><span class="sxs-lookup"><span data-stu-id="7a320-120"><a href="lync-server-2013-designing-the-sip-trunk-for-e9-1-1.md">Designing the SIP trunk for E9-1-1 in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="7a320-121"><a href="lync-server-2013-including-the-security-desk.md">Lync Server 2013 にセキュリティデスクを含める</a></span><span class="sxs-lookup"><span data-stu-id="7a320-121"><a href="lync-server-2013-including-the-security-desk.md">Including the security desk in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7a320-122"><a href="lync-server-2013-including-the-security-desk.md">Lync Server 2013 にセキュリティデスクを含める</a></span><span class="sxs-lookup"><span data-stu-id="7a320-122"><a href="lync-server-2013-including-the-security-desk.md">Including the security desk in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="7a320-123"><a href="lync-server-2013-defining-the-location-policy.md">Lync Server 2013 の場所ポリシーの定義</a></span><span class="sxs-lookup"><span data-stu-id="7a320-123"><a href="lync-server-2013-defining-the-location-policy.md">Defining the location policy for Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7a320-124"><a href="lync-server-2013-choosing-an-e9-1-1-service-provider.md">Lync Server 2013 の E9-1-1 サービスプロバイダーの選択</a></span><span class="sxs-lookup"><span data-stu-id="7a320-124"><a href="lync-server-2013-choosing-an-e9-1-1-service-provider.md">Choosing an E9-1-1 service provider for Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="7a320-125"><a href="lync-server-2013-assigning-location-policy-scope.md">Lync Server 2013 での場所ポリシーのスコープの割り当て</a></span><span class="sxs-lookup"><span data-stu-id="7a320-125"><a href="lync-server-2013-assigning-location-policy-scope.md">Assigning location policy scope in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7a320-126"><a href="lync-server-2013-defining-the-location-policy.md">Lync Server 2013 の場所ポリシーの定義</a></span><span class="sxs-lookup"><span data-stu-id="7a320-126"><a href="lync-server-2013-defining-the-location-policy.md">Defining the location policy for Lync Server 2013</a></span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7a320-127"><a href="lync-server-2013-assigning-location-policy-scope.md">Lync Server 2013 での場所ポリシーのスコープの割り当て</a></span><span class="sxs-lookup"><span data-stu-id="7a320-127"><a href="lync-server-2013-assigning-location-policy-scope.md">Assigning location policy scope in Lync Server 2013</a></span></span></p></td>
<td></td>
</tr>
</tbody>
</table>


<div>

## <a name="in-this-section"></a><span data-ttu-id="7a320-128">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="7a320-128">In This Section</span></span>

  - [<span data-ttu-id="7a320-129">Lync Server 2013 での E9-1-1 展開の範囲の定義</span><span class="sxs-lookup"><span data-stu-id="7a320-129">Defining the scope of the E9-1-1 deployment in Lync Server 2013</span></span>](lync-server-2013-defining-the-scope-of-the-e9-1-1-deployment.md)

  - [<span data-ttu-id="7a320-130">Lync Server 2013 での場所を決定するために使用するネットワーク要素の定義</span><span class="sxs-lookup"><span data-stu-id="7a320-130">Defining the network elements used to determine location in Lync Server 2013</span></span>](lync-server-2013-defining-the-network-elements-used-to-determine-location.md)

  - [<span data-ttu-id="7a320-131">Lync Server 2013 での E9-1-1 のユーザーの有効化</span><span class="sxs-lookup"><span data-stu-id="7a320-131">Enabling users for E9-1-1 in Lync Server 2013</span></span>](lync-server-2013-enabling-users-for-e9-1-1.md)

  - [<span data-ttu-id="7a320-132">Lync Server 2013 での SIP トランクサービスプロバイダーの場所の管理</span><span class="sxs-lookup"><span data-stu-id="7a320-132">Managing locations for SIP trunk service providers in Lync Server 2013</span></span>](lync-server-2013-managing-locations-for-sip-trunk-service-providers.md)

  - [<span data-ttu-id="7a320-133">Lync Server 2013 での ELIN ゲートウェイの場所の管理</span><span class="sxs-lookup"><span data-stu-id="7a320-133">Managing locations for ELIN gateways in Lync Server 2013</span></span>](lync-server-2013-managing-locations-for-elin-gateways.md)

  - [<span data-ttu-id="7a320-134">Lync Server 2013 で手動で場所を取得するためのユーザーの作業を定義する</span><span class="sxs-lookup"><span data-stu-id="7a320-134">Defining the user experience for manually acquiring a location in Lync Server 2013</span></span>](lync-server-2013-defining-the-user-experience-for-manually-acquiring-a-location.md)

  - [<span data-ttu-id="7a320-135">Lync Server 2013 での E9-1-1 の SIP トランクの設計</span><span class="sxs-lookup"><span data-stu-id="7a320-135">Designing the SIP trunk for E9-1-1 in Lync Server 2013</span></span>](lync-server-2013-designing-the-sip-trunk-for-e9-1-1.md)

  - [<span data-ttu-id="7a320-136">Lync Server 2013 にセキュリティデスクを含める</span><span class="sxs-lookup"><span data-stu-id="7a320-136">Including the security desk in Lync Server 2013</span></span>](lync-server-2013-including-the-security-desk.md)

  - [<span data-ttu-id="7a320-137">Lync Server 2013 の E9-1-1 サービスプロバイダーの選択</span><span class="sxs-lookup"><span data-stu-id="7a320-137">Choosing an E9-1-1 service provider for Lync Server 2013</span></span>](lync-server-2013-choosing-an-e9-1-1-service-provider.md)

  - [<span data-ttu-id="7a320-138">Lync Server 2013 の場所ポリシーの定義</span><span class="sxs-lookup"><span data-stu-id="7a320-138">Defining the location policy for Lync Server 2013</span></span>](lync-server-2013-defining-the-location-policy.md)

  - [<span data-ttu-id="7a320-139">Lync Server 2013 での場所ポリシーのスコープの割り当て</span><span class="sxs-lookup"><span data-stu-id="7a320-139">Assigning location policy scope in Lync Server 2013</span></span>](lync-server-2013-assigning-location-policy-scope.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

