---
title: 'Lync Server 2013: 登録テーブル'
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
ms.openlocfilehash: 4c40fddd324cd687b54d0c3317edc533fa559c8d
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48536694"
---
# <a name="registration-table-in-lync-server-2013"></a><span data-ttu-id="1ed2c-102">Lync Server 2013 の登録テーブル</span><span class="sxs-lookup"><span data-stu-id="1ed2c-102">Registration table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1ed2c-103">_**トピックの最終更新日:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="1ed2c-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="1ed2c-104">各レコードは 1 つのユーザー登録イベントを表します。</span><span class="sxs-lookup"><span data-stu-id="1ed2c-104">Each record represents one user registration event.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1ed2c-105">Column</span><span class="sxs-lookup"><span data-stu-id="1ed2c-105">Column</span></span></th>
<th><span data-ttu-id="1ed2c-106">データ型</span><span class="sxs-lookup"><span data-stu-id="1ed2c-106">Data Type</span></span></th>
<th><span data-ttu-id="1ed2c-107">キー/インデックス</span><span class="sxs-lookup"><span data-stu-id="1ed2c-107">Key/Index</span></span></th>
<th><span data-ttu-id="1ed2c-108">詳細</span><span class="sxs-lookup"><span data-stu-id="1ed2c-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1ed2c-109"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="1ed2c-109"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="1ed2c-110">日付型</span><span class="sxs-lookup"><span data-stu-id="1ed2c-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="1ed2c-111">主/プライマリ、外部</span><span class="sxs-lookup"><span data-stu-id="1ed2c-111">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="1ed2c-112">セッション要求の時刻。</span><span class="sxs-lookup"><span data-stu-id="1ed2c-112">Time of session request.</span></span> <span data-ttu-id="1ed2c-113">セッションを一意に識別するために <strong>SessionIdSeq</strong> と併用されます。</span><span class="sxs-lookup"><span data-stu-id="1ed2c-113">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="1ed2c-114">詳細については、「 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 のダイアログテーブル</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1ed2c-114">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1ed2c-115"><strong>Sessionidseq と</strong></span><span class="sxs-lookup"><span data-stu-id="1ed2c-115"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="1ed2c-116">int</span><span class="sxs-lookup"><span data-stu-id="1ed2c-116">int</span></span></p></td>
<td><p><span data-ttu-id="1ed2c-117">主/プライマリ、外部</span><span class="sxs-lookup"><span data-stu-id="1ed2c-117">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="1ed2c-118">セッションを識別するための ID 番号。</span><span class="sxs-lookup"><span data-stu-id="1ed2c-118">ID number to identify the session.</span></span> <span data-ttu-id="1ed2c-119">セッションを一意に識別するために <strong>SessionIdTime</strong> と併用されます。</span><span class="sxs-lookup"><span data-stu-id="1ed2c-119">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.</span></span> <span data-ttu-id="1ed2c-120">詳細については、「 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 のダイアログテーブル</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1ed2c-120">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1ed2c-121"><strong>UserId</strong></span><span class="sxs-lookup"><span data-stu-id="1ed2c-121"><strong>UserId</strong></span></span></p></td>
<td><p><span data-ttu-id="1ed2c-122">int</span><span class="sxs-lookup"><span data-stu-id="1ed2c-122">int</span></span></p></td>
<td><p><span data-ttu-id="1ed2c-123">外部</span><span class="sxs-lookup"><span data-stu-id="1ed2c-123">Foreign</span></span></p></td>
<td><p><span data-ttu-id="1ed2c-124">ユーザー ID。</span><span class="sxs-lookup"><span data-stu-id="1ed2c-124">The user ID.</span></span> <span data-ttu-id="1ed2c-125">詳細については、「 <a href="lync-server-2013-users-table.md">Lync Server 2013 のユーザー</a> 」の表を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1ed2c-125">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1ed2c-126"><strong>EndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="1ed2c-126"><strong>EndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="1ed2c-127">識別子</span><span class="sxs-lookup"><span data-stu-id="1ed2c-127">uniqueidentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1ed2c-p104">登録エンドポイントを識別するための GUID。通常、同じユーザーの同じコンピューターからの登録イベントは、同じエンドポイント ID になります。コンピューターが異なると、エンドポイント ID も異なります。</span><span class="sxs-lookup"><span data-stu-id="1ed2c-p104">A GUID to identify a registration endpoint. Usually the register event from the same computer of the same user will have the same endpoint ID. Different machines have a different endpoint ID.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1ed2c-131"><strong>Endポインター a</strong></span><span class="sxs-lookup"><span data-stu-id="1ed2c-131"><strong>EndpointEra</strong></span></span></p></td>
<td><p><span data-ttu-id="1ed2c-132">識別子</span><span class="sxs-lookup"><span data-stu-id="1ed2c-132">uniqueIdentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1ed2c-133">同じユーザーと同じエンドポイントを含む登録を区別するために使用される ID。</span><span class="sxs-lookup"><span data-stu-id="1ed2c-133">ID used to differentiate registrations that involve the same user and the same endpoint.</span></span></p>
<p><span data-ttu-id="1ed2c-134">このフィールドは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="1ed2c-134">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1ed2c-135"><strong>ClientVersionId</strong></span><span class="sxs-lookup"><span data-stu-id="1ed2c-135"><strong>ClientVersionId</strong></span></span></p></td>
<td><p><span data-ttu-id="1ed2c-136">int</span><span class="sxs-lookup"><span data-stu-id="1ed2c-136">int</span></span></p></td>
<td><p><span data-ttu-id="1ed2c-137">外部</span><span class="sxs-lookup"><span data-stu-id="1ed2c-137">Foreign</span></span></p></td>
<td><p><span data-ttu-id="1ed2c-138">現在のユーザーのクライアントのバージョン。</span><span class="sxs-lookup"><span data-stu-id="1ed2c-138">Client version of current user.</span></span> <span data-ttu-id="1ed2c-139">詳細については、「 <a href="lync-server-2013-clientversions-table.md">Lync Server 2013 の Clientversions</a> 」の表を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1ed2c-139">See the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1ed2c-140"><strong>RegistrarId</strong></span><span class="sxs-lookup"><span data-stu-id="1ed2c-140"><strong>RegistrarId</strong></span></span></p></td>
<td><p><span data-ttu-id="1ed2c-141">int</span><span class="sxs-lookup"><span data-stu-id="1ed2c-141">int</span></span></p></td>
<td><p><span data-ttu-id="1ed2c-142">外部</span><span class="sxs-lookup"><span data-stu-id="1ed2c-142">Foreign</span></span></p></td>
<td><p><span data-ttu-id="1ed2c-143">登録に使用されたレジストラー サーバーの ID。</span><span class="sxs-lookup"><span data-stu-id="1ed2c-143">ID of the Registrar Server used for registration.</span></span> <span data-ttu-id="1ed2c-144">詳細については、「 <a href="lync-server-2013-servers-table.md">Lync Server 2013 のサーバーの表</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1ed2c-144">See the <a href="lync-server-2013-servers-table.md">Servers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1ed2c-145"><strong>PoolId</strong></span><span class="sxs-lookup"><span data-stu-id="1ed2c-145"><strong>PoolId</strong></span></span></p></td>
<td><p><span data-ttu-id="1ed2c-146">int</span><span class="sxs-lookup"><span data-stu-id="1ed2c-146">int</span></span></p></td>
<td><p><span data-ttu-id="1ed2c-147">外部</span><span class="sxs-lookup"><span data-stu-id="1ed2c-147">Foreign</span></span></p></td>
<td><p><span data-ttu-id="1ed2c-148">セッションが取得されたプールの ID。</span><span class="sxs-lookup"><span data-stu-id="1ed2c-148">ID of the pool in which the session was captured.</span></span> <span data-ttu-id="1ed2c-149">詳細については、「 <a href="lync-server-2013-pools-table.md">Lync Server 2013 のプール</a> 」の表を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1ed2c-149">See the <a href="lync-server-2013-pools-table.md">Pools table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1ed2c-150"><strong>EdgeServerId</strong></span><span class="sxs-lookup"><span data-stu-id="1ed2c-150"><strong>EdgeServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="1ed2c-151">int</span><span class="sxs-lookup"><span data-stu-id="1ed2c-151">int</span></span></p></td>
<td><p><span data-ttu-id="1ed2c-152">外部</span><span class="sxs-lookup"><span data-stu-id="1ed2c-152">Foreign</span></span></p></td>
<td><p><span data-ttu-id="1ed2c-153">登録が通過するエッジ サーバー。</span><span class="sxs-lookup"><span data-stu-id="1ed2c-153">Edge Server the registration is going through.</span></span> <span data-ttu-id="1ed2c-154">詳細については、「 <a href="lync-server-2013-edgeservers-table.md">Lync Server 2013 の EdgeServers テーブル</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1ed2c-154">See the <a href="lync-server-2013-edgeservers-table.md">EdgeServers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1ed2c-155"><strong>IsInternal</strong></span><span class="sxs-lookup"><span data-stu-id="1ed2c-155"><strong>IsInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="1ed2c-156">若干</span><span class="sxs-lookup"><span data-stu-id="1ed2c-156">Bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1ed2c-157">ユーザーが内部からログオンしているかどうか。</span><span class="sxs-lookup"><span data-stu-id="1ed2c-157">Whether the user is logged on from internal or not.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1ed2c-158"><strong>IsUserServiceAvailable</strong></span><span class="sxs-lookup"><span data-stu-id="1ed2c-158"><strong>IsUserServiceAvailable</strong></span></span></p></td>
<td><p><span data-ttu-id="1ed2c-159">若干</span><span class="sxs-lookup"><span data-stu-id="1ed2c-159">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1ed2c-160">UserService が利用できるかどうか。</span><span class="sxs-lookup"><span data-stu-id="1ed2c-160">Whether the UserService is available or not.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1ed2c-161"><strong>IsPrimaryRegistrar</strong></span><span class="sxs-lookup"><span data-stu-id="1ed2c-161"><strong>IsPrimaryRegistrar</strong></span></span></p></td>
<td><p><span data-ttu-id="1ed2c-162">若干</span><span class="sxs-lookup"><span data-stu-id="1ed2c-162">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1ed2c-163">プライマリ レジストラーに対する登録かどうか。</span><span class="sxs-lookup"><span data-stu-id="1ed2c-163">Whether register to the primary Registrar or not.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1ed2c-164"><strong>IsPrimaryRegistrarCentral</strong></span><span class="sxs-lookup"><span data-stu-id="1ed2c-164"><strong>IsPrimaryRegistrarCentral</strong></span></span></p></td>
<td><p><span data-ttu-id="1ed2c-165">若干</span><span class="sxs-lookup"><span data-stu-id="1ed2c-165">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1ed2c-166">ユーザーが存続可能ブランチ アプライアンスに登録されているかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="1ed2c-166">Indicates whether or not the user is registered with a survivable branch appliance.</span></span></p>
<p><span data-ttu-id="1ed2c-167">このフィールドは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="1ed2c-167">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1ed2c-168"><strong>RegisterTime</strong></span><span class="sxs-lookup"><span data-stu-id="1ed2c-168"><strong>RegisterTime</strong></span></span></p></td>
<td><p><span data-ttu-id="1ed2c-169">日付型</span><span class="sxs-lookup"><span data-stu-id="1ed2c-169">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1ed2c-170">登録日時。</span><span class="sxs-lookup"><span data-stu-id="1ed2c-170">Registration time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1ed2c-171"><strong>DeRegisterTime</strong></span><span class="sxs-lookup"><span data-stu-id="1ed2c-171"><strong>DeRegisterTime</strong></span></span></p></td>
<td><p><span data-ttu-id="1ed2c-172">日付型</span><span class="sxs-lookup"><span data-stu-id="1ed2c-172">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1ed2c-173">登録解除日時。</span><span class="sxs-lookup"><span data-stu-id="1ed2c-173">De-Registration time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1ed2c-174"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="1ed2c-174"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="1ed2c-175">int</span><span class="sxs-lookup"><span data-stu-id="1ed2c-175">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1ed2c-176">登録要求の応答コード。</span><span class="sxs-lookup"><span data-stu-id="1ed2c-176">Response code of the register request.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1ed2c-177"><strong>DiagnosticId</strong></span><span class="sxs-lookup"><span data-stu-id="1ed2c-177"><strong>DiagnosticId</strong></span></span></p></td>
<td><p><span data-ttu-id="1ed2c-178">int</span><span class="sxs-lookup"><span data-stu-id="1ed2c-178">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1ed2c-p109">登録要求の診断 ID。その診断情報の種類を示します。</span><span class="sxs-lookup"><span data-stu-id="1ed2c-p109">Diagnostic ID of the register request. This indicates that diagnostic information type.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1ed2c-181"><strong>DeviceId</strong></span><span class="sxs-lookup"><span data-stu-id="1ed2c-181"><strong>DeviceId</strong></span></span></p></td>
<td><p><span data-ttu-id="1ed2c-182">int</span><span class="sxs-lookup"><span data-stu-id="1ed2c-182">int</span></span></p></td>
<td><p><span data-ttu-id="1ed2c-183">外部</span><span class="sxs-lookup"><span data-stu-id="1ed2c-183">Foreign</span></span></p></td>
<td><p><span data-ttu-id="1ed2c-184">登録要求の送信元のデバイス。</span><span class="sxs-lookup"><span data-stu-id="1ed2c-184">The device that the register request is coming from.</span></span> <span data-ttu-id="1ed2c-185">詳細については、「 <a href="lync-server-2013-devices-table.md">Lync Server 2013 の Devices table</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1ed2c-185">See the <a href="lync-server-2013-devices-table.md">Devices table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1ed2c-186"><strong>DeRegisterTypeId</strong></span><span class="sxs-lookup"><span data-stu-id="1ed2c-186"><strong>DeRegisterTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="1ed2c-187">tinyint</span><span class="sxs-lookup"><span data-stu-id="1ed2c-187">tinyint</span></span></p></td>
<td><p><span data-ttu-id="1ed2c-188">外部</span><span class="sxs-lookup"><span data-stu-id="1ed2c-188">Foreign</span></span></p></td>
<td><p><span data-ttu-id="1ed2c-189">登録解除の理由 ("ユーザー開始済み"、"登録期限切れ"、"クライアント障害" など)。</span><span class="sxs-lookup"><span data-stu-id="1ed2c-189">The reason of de-register, such as ‘user initiated’, ‘registration expired’, ‘client fail’, and more.</span></span> <span data-ttu-id="1ed2c-190">詳細については、「 <a href="lync-server-2013-deregistertype-table.md">Lync Server 2013 の DeRegisterType テーブル</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1ed2c-190">See the <a href="lync-server-2013-deregistertype-table.md">DeRegisterType table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1ed2c-191"><strong>IPAddress</strong></span><span class="sxs-lookup"><span data-stu-id="1ed2c-191"><strong>IPAddress</strong></span></span></p></td>
<td><p><span data-ttu-id="1ed2c-192">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="1ed2c-192">nvarchar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1ed2c-193">ユーザーが登録されているエンドポイントの IP アドレス。</span><span class="sxs-lookup"><span data-stu-id="1ed2c-193">IP address of the endpoint the user registered with.</span></span> <span data-ttu-id="1ed2c-194">IPv4 アドレスまたは IPv6 アドレスのどちらかになります。</span><span class="sxs-lookup"><span data-stu-id="1ed2c-194">This can be an IPv4 address or an IPv6 address.</span></span></p>
<p><span data-ttu-id="1ed2c-195">このフィールドは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="1ed2c-195">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

