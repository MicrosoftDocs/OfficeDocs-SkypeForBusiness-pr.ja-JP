---
title: 'Lync Server 2013: 登録テーブル'
description: 'Lync Server 2013: 登録テーブル。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Registration table
ms:assetid: 05ff9dd3-1aaa-4af0-bd69-8789fb8eaeb3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398114(v=OCS.15)
ms:contentKeyID: 48183298
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 806e1a4e944c9bc04ebdd167c41c80a57fde3f29
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48578530"
---
# <a name="registration-table-in-lync-server-2013"></a><span data-ttu-id="86aae-103">Lync Server 2013 の登録テーブル</span><span class="sxs-lookup"><span data-stu-id="86aae-103">Registration table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="86aae-104">_**トピックの最終更新日:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="86aae-104">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="86aae-105">各レコードは 1 つのユーザー登録イベントを表します。</span><span class="sxs-lookup"><span data-stu-id="86aae-105">Each record represents one user registration event.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="86aae-106">Column</span><span class="sxs-lookup"><span data-stu-id="86aae-106">Column</span></span></th>
<th><span data-ttu-id="86aae-107">データ型</span><span class="sxs-lookup"><span data-stu-id="86aae-107">Data Type</span></span></th>
<th><span data-ttu-id="86aae-108">キー/インデックス</span><span class="sxs-lookup"><span data-stu-id="86aae-108">Key/Index</span></span></th>
<th><span data-ttu-id="86aae-109">詳細</span><span class="sxs-lookup"><span data-stu-id="86aae-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="86aae-110"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="86aae-110"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="86aae-111">日付型</span><span class="sxs-lookup"><span data-stu-id="86aae-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="86aae-112">主/プライマリ、外部</span><span class="sxs-lookup"><span data-stu-id="86aae-112">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="86aae-113">セッション要求の時刻。</span><span class="sxs-lookup"><span data-stu-id="86aae-113">Time of session request.</span></span> <span data-ttu-id="86aae-114">セッションを一意に識別するために <strong>SessionIdSeq</strong> と併用されます。</span><span class="sxs-lookup"><span data-stu-id="86aae-114">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="86aae-115">詳細については、「 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 のダイアログテーブル</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="86aae-115">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="86aae-116"><strong>Sessionidseq と</strong></span><span class="sxs-lookup"><span data-stu-id="86aae-116"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="86aae-117">int</span><span class="sxs-lookup"><span data-stu-id="86aae-117">int</span></span></p></td>
<td><p><span data-ttu-id="86aae-118">主/プライマリ、外部</span><span class="sxs-lookup"><span data-stu-id="86aae-118">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="86aae-119">セッションを識別するための ID 番号。</span><span class="sxs-lookup"><span data-stu-id="86aae-119">ID number to identify the session.</span></span> <span data-ttu-id="86aae-120">セッションを一意に識別するために <strong>SessionIdTime</strong> と併用されます。</span><span class="sxs-lookup"><span data-stu-id="86aae-120">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.</span></span> <span data-ttu-id="86aae-121">詳細については、「 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 のダイアログテーブル</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="86aae-121">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="86aae-122"><strong>UserId</strong></span><span class="sxs-lookup"><span data-stu-id="86aae-122"><strong>UserId</strong></span></span></p></td>
<td><p><span data-ttu-id="86aae-123">int</span><span class="sxs-lookup"><span data-stu-id="86aae-123">int</span></span></p></td>
<td><p><span data-ttu-id="86aae-124">外部</span><span class="sxs-lookup"><span data-stu-id="86aae-124">Foreign</span></span></p></td>
<td><p><span data-ttu-id="86aae-125">ユーザー ID。</span><span class="sxs-lookup"><span data-stu-id="86aae-125">The user ID.</span></span> <span data-ttu-id="86aae-126">詳細については、「 <a href="lync-server-2013-users-table.md">Lync Server 2013 のユーザー</a> 」の表を参照してください。</span><span class="sxs-lookup"><span data-stu-id="86aae-126">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="86aae-127"><strong>EndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="86aae-127"><strong>EndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="86aae-128">識別子</span><span class="sxs-lookup"><span data-stu-id="86aae-128">uniqueidentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="86aae-p104">登録エンドポイントを識別するための GUID。通常、同じユーザーの同じコンピューターからの登録イベントは、同じエンドポイント ID になります。コンピューターが異なると、エンドポイント ID も異なります。</span><span class="sxs-lookup"><span data-stu-id="86aae-p104">A GUID to identify a registration endpoint. Usually the register event from the same computer of the same user will have the same endpoint ID. Different machines have a different endpoint ID.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="86aae-132"><strong>Endポインター a</strong></span><span class="sxs-lookup"><span data-stu-id="86aae-132"><strong>EndpointEra</strong></span></span></p></td>
<td><p><span data-ttu-id="86aae-133">識別子</span><span class="sxs-lookup"><span data-stu-id="86aae-133">uniqueIdentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="86aae-134">同じユーザーと同じエンドポイントを含む登録を区別するために使用される ID。</span><span class="sxs-lookup"><span data-stu-id="86aae-134">ID used to differentiate registrations that involve the same user and the same endpoint.</span></span></p>
<p><span data-ttu-id="86aae-135">このフィールドは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="86aae-135">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="86aae-136"><strong>ClientVersionId</strong></span><span class="sxs-lookup"><span data-stu-id="86aae-136"><strong>ClientVersionId</strong></span></span></p></td>
<td><p><span data-ttu-id="86aae-137">int</span><span class="sxs-lookup"><span data-stu-id="86aae-137">int</span></span></p></td>
<td><p><span data-ttu-id="86aae-138">外部</span><span class="sxs-lookup"><span data-stu-id="86aae-138">Foreign</span></span></p></td>
<td><p><span data-ttu-id="86aae-139">現在のユーザーのクライアントのバージョン。</span><span class="sxs-lookup"><span data-stu-id="86aae-139">Client version of current user.</span></span> <span data-ttu-id="86aae-140">詳細については、「 <a href="lync-server-2013-clientversions-table.md">Lync Server 2013 の Clientversions</a> 」の表を参照してください。</span><span class="sxs-lookup"><span data-stu-id="86aae-140">See the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="86aae-141"><strong>RegistrarId</strong></span><span class="sxs-lookup"><span data-stu-id="86aae-141"><strong>RegistrarId</strong></span></span></p></td>
<td><p><span data-ttu-id="86aae-142">int</span><span class="sxs-lookup"><span data-stu-id="86aae-142">int</span></span></p></td>
<td><p><span data-ttu-id="86aae-143">外部</span><span class="sxs-lookup"><span data-stu-id="86aae-143">Foreign</span></span></p></td>
<td><p><span data-ttu-id="86aae-144">登録に使用されたレジストラー サーバーの ID。</span><span class="sxs-lookup"><span data-stu-id="86aae-144">ID of the Registrar Server used for registration.</span></span> <span data-ttu-id="86aae-145">詳細については、「 <a href="lync-server-2013-servers-table.md">Lync Server 2013 のサーバーの表</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="86aae-145">See the <a href="lync-server-2013-servers-table.md">Servers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="86aae-146"><strong>PoolId</strong></span><span class="sxs-lookup"><span data-stu-id="86aae-146"><strong>PoolId</strong></span></span></p></td>
<td><p><span data-ttu-id="86aae-147">int</span><span class="sxs-lookup"><span data-stu-id="86aae-147">int</span></span></p></td>
<td><p><span data-ttu-id="86aae-148">外部</span><span class="sxs-lookup"><span data-stu-id="86aae-148">Foreign</span></span></p></td>
<td><p><span data-ttu-id="86aae-149">セッションが取得されたプールの ID。</span><span class="sxs-lookup"><span data-stu-id="86aae-149">ID of the pool in which the session was captured.</span></span> <span data-ttu-id="86aae-150">詳細については、「 <a href="lync-server-2013-pools-table.md">Lync Server 2013 のプール</a> 」の表を参照してください。</span><span class="sxs-lookup"><span data-stu-id="86aae-150">See the <a href="lync-server-2013-pools-table.md">Pools table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="86aae-151"><strong>EdgeServerId</strong></span><span class="sxs-lookup"><span data-stu-id="86aae-151"><strong>EdgeServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="86aae-152">int</span><span class="sxs-lookup"><span data-stu-id="86aae-152">int</span></span></p></td>
<td><p><span data-ttu-id="86aae-153">外部</span><span class="sxs-lookup"><span data-stu-id="86aae-153">Foreign</span></span></p></td>
<td><p><span data-ttu-id="86aae-154">登録が通過するエッジ サーバー。</span><span class="sxs-lookup"><span data-stu-id="86aae-154">Edge Server the registration is going through.</span></span> <span data-ttu-id="86aae-155">詳細については、「 <a href="lync-server-2013-edgeservers-table.md">Lync Server 2013 の EdgeServers テーブル</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="86aae-155">See the <a href="lync-server-2013-edgeservers-table.md">EdgeServers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="86aae-156"><strong>IsInternal</strong></span><span class="sxs-lookup"><span data-stu-id="86aae-156"><strong>IsInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="86aae-157">若干</span><span class="sxs-lookup"><span data-stu-id="86aae-157">Bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="86aae-158">ユーザーが内部からログオンしているかどうか。</span><span class="sxs-lookup"><span data-stu-id="86aae-158">Whether the user is logged on from internal or not.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="86aae-159"><strong>IsUserServiceAvailable</strong></span><span class="sxs-lookup"><span data-stu-id="86aae-159"><strong>IsUserServiceAvailable</strong></span></span></p></td>
<td><p><span data-ttu-id="86aae-160">若干</span><span class="sxs-lookup"><span data-stu-id="86aae-160">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="86aae-161">UserService が利用できるかどうか。</span><span class="sxs-lookup"><span data-stu-id="86aae-161">Whether the UserService is available or not.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="86aae-162"><strong>IsPrimaryRegistrar</strong></span><span class="sxs-lookup"><span data-stu-id="86aae-162"><strong>IsPrimaryRegistrar</strong></span></span></p></td>
<td><p><span data-ttu-id="86aae-163">若干</span><span class="sxs-lookup"><span data-stu-id="86aae-163">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="86aae-164">プライマリ レジストラーに対する登録かどうか。</span><span class="sxs-lookup"><span data-stu-id="86aae-164">Whether register to the primary Registrar or not.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="86aae-165"><strong>IsPrimaryRegistrarCentral</strong></span><span class="sxs-lookup"><span data-stu-id="86aae-165"><strong>IsPrimaryRegistrarCentral</strong></span></span></p></td>
<td><p><span data-ttu-id="86aae-166">若干</span><span class="sxs-lookup"><span data-stu-id="86aae-166">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="86aae-167">ユーザーが存続可能ブランチ アプライアンスに登録されているかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="86aae-167">Indicates whether or not the user is registered with a survivable branch appliance.</span></span></p>
<p><span data-ttu-id="86aae-168">このフィールドは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="86aae-168">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="86aae-169"><strong>RegisterTime</strong></span><span class="sxs-lookup"><span data-stu-id="86aae-169"><strong>RegisterTime</strong></span></span></p></td>
<td><p><span data-ttu-id="86aae-170">日付型</span><span class="sxs-lookup"><span data-stu-id="86aae-170">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="86aae-171">登録日時。</span><span class="sxs-lookup"><span data-stu-id="86aae-171">Registration time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="86aae-172"><strong>DeRegisterTime</strong></span><span class="sxs-lookup"><span data-stu-id="86aae-172"><strong>DeRegisterTime</strong></span></span></p></td>
<td><p><span data-ttu-id="86aae-173">日付型</span><span class="sxs-lookup"><span data-stu-id="86aae-173">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="86aae-174">登録解除日時。</span><span class="sxs-lookup"><span data-stu-id="86aae-174">De-Registration time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="86aae-175"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="86aae-175"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="86aae-176">int</span><span class="sxs-lookup"><span data-stu-id="86aae-176">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="86aae-177">登録要求の応答コード。</span><span class="sxs-lookup"><span data-stu-id="86aae-177">Response code of the register request.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="86aae-178"><strong>DiagnosticId</strong></span><span class="sxs-lookup"><span data-stu-id="86aae-178"><strong>DiagnosticId</strong></span></span></p></td>
<td><p><span data-ttu-id="86aae-179">int</span><span class="sxs-lookup"><span data-stu-id="86aae-179">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="86aae-p109">登録要求の診断 ID。その診断情報の種類を示します。</span><span class="sxs-lookup"><span data-stu-id="86aae-p109">Diagnostic ID of the register request. This indicates that diagnostic information type.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="86aae-182"><strong>DeviceId</strong></span><span class="sxs-lookup"><span data-stu-id="86aae-182"><strong>DeviceId</strong></span></span></p></td>
<td><p><span data-ttu-id="86aae-183">int</span><span class="sxs-lookup"><span data-stu-id="86aae-183">int</span></span></p></td>
<td><p><span data-ttu-id="86aae-184">外部</span><span class="sxs-lookup"><span data-stu-id="86aae-184">Foreign</span></span></p></td>
<td><p><span data-ttu-id="86aae-185">登録要求の送信元のデバイス。</span><span class="sxs-lookup"><span data-stu-id="86aae-185">The device that the register request is coming from.</span></span> <span data-ttu-id="86aae-186">詳細については、「 <a href="lync-server-2013-devices-table.md">Lync Server 2013 の Devices table</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="86aae-186">See the <a href="lync-server-2013-devices-table.md">Devices table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="86aae-187"><strong>DeRegisterTypeId</strong></span><span class="sxs-lookup"><span data-stu-id="86aae-187"><strong>DeRegisterTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="86aae-188">tinyint</span><span class="sxs-lookup"><span data-stu-id="86aae-188">tinyint</span></span></p></td>
<td><p><span data-ttu-id="86aae-189">外部</span><span class="sxs-lookup"><span data-stu-id="86aae-189">Foreign</span></span></p></td>
<td><p><span data-ttu-id="86aae-190">登録解除の理由 ("ユーザー開始済み"、"登録期限切れ"、"クライアント障害" など)。</span><span class="sxs-lookup"><span data-stu-id="86aae-190">The reason of de-register, such as ‘user initiated’, ‘registration expired’, ‘client fail’, and more.</span></span> <span data-ttu-id="86aae-191">詳細については、「 <a href="lync-server-2013-deregistertype-table.md">Lync Server 2013 の DeRegisterType テーブル</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="86aae-191">See the <a href="lync-server-2013-deregistertype-table.md">DeRegisterType table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="86aae-192"><strong>IPAddress</strong></span><span class="sxs-lookup"><span data-stu-id="86aae-192"><strong>IPAddress</strong></span></span></p></td>
<td><p><span data-ttu-id="86aae-193">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="86aae-193">nvarchar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="86aae-194">ユーザーが登録されているエンドポイントの IP アドレス。</span><span class="sxs-lookup"><span data-stu-id="86aae-194">IP address of the endpoint the user registered with.</span></span> <span data-ttu-id="86aae-195">IPv4 アドレスまたは IPv6 アドレスのどちらかになります。</span><span class="sxs-lookup"><span data-stu-id="86aae-195">This can be an IPv4 address or an IPv6 address.</span></span></p>
<p><span data-ttu-id="86aae-196">このフィールドは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="86aae-196">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

