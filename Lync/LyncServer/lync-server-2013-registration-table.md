---
title: 'Lync Server 2013: Registration テーブル'
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
ms.openlocfilehash: 0bc19c35893b12aae7842be5fc474f7831b7f979
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41724397"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="registration-table-in-lync-server-2013"></a><span data-ttu-id="a3e37-102">Lync Server 2013 の Registration テーブル</span><span class="sxs-lookup"><span data-stu-id="a3e37-102">Registration table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a3e37-103">_**最終更新日:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="a3e37-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="a3e37-104">各レコードは、1つのユーザー登録イベントを表します。</span><span class="sxs-lookup"><span data-stu-id="a3e37-104">Each record represents one user registration event.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a3e37-105">列</span><span class="sxs-lookup"><span data-stu-id="a3e37-105">Column</span></span></th>
<th><span data-ttu-id="a3e37-106">データ型</span><span class="sxs-lookup"><span data-stu-id="a3e37-106">Data Type</span></span></th>
<th><span data-ttu-id="a3e37-107">キー/インデックス</span><span class="sxs-lookup"><span data-stu-id="a3e37-107">Key/Index</span></span></th>
<th><span data-ttu-id="a3e37-108">詳細</span><span class="sxs-lookup"><span data-stu-id="a3e37-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a3e37-109"><strong>セッション Id</strong></span><span class="sxs-lookup"><span data-stu-id="a3e37-109"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="a3e37-110">datetime</span><span class="sxs-lookup"><span data-stu-id="a3e37-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="a3e37-111">プライマリ、外部</span><span class="sxs-lookup"><span data-stu-id="a3e37-111">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="a3e37-112">セッション要求の時刻。</span><span class="sxs-lookup"><span data-stu-id="a3e37-112">Time of session request.</span></span> <span data-ttu-id="a3e37-113">セッションを一意に識別するために<strong>Sessionidseq</strong>と組み合わせて使用されます。</span><span class="sxs-lookup"><span data-stu-id="a3e37-113">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="a3e37-114">詳細については、「 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 のダイアログテーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a3e37-114">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a3e37-115"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="a3e37-115"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="a3e37-116">int</span><span class="sxs-lookup"><span data-stu-id="a3e37-116">int</span></span></p></td>
<td><p><span data-ttu-id="a3e37-117">プライマリ、外部</span><span class="sxs-lookup"><span data-stu-id="a3e37-117">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="a3e37-118">セッションを識別する ID 番号。</span><span class="sxs-lookup"><span data-stu-id="a3e37-118">ID number to identify the session.</span></span> <span data-ttu-id="a3e37-119">セッションを一意に識別するために<strong>Sessionidtime</strong>と組み合わせて使用されます。</span><span class="sxs-lookup"><span data-stu-id="a3e37-119">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.</span></span> <span data-ttu-id="a3e37-120">詳細については、「 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 のダイアログテーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a3e37-120">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a3e37-121"><strong>UserId</strong></span><span class="sxs-lookup"><span data-stu-id="a3e37-121"><strong>UserId</strong></span></span></p></td>
<td><p><span data-ttu-id="a3e37-122">int</span><span class="sxs-lookup"><span data-stu-id="a3e37-122">int</span></span></p></td>
<td><p><span data-ttu-id="a3e37-123">外部</span><span class="sxs-lookup"><span data-stu-id="a3e37-123">Foreign</span></span></p></td>
<td><p><span data-ttu-id="a3e37-124">ユーザー ID。</span><span class="sxs-lookup"><span data-stu-id="a3e37-124">The user ID.</span></span> <span data-ttu-id="a3e37-125">詳細については、「 <a href="lync-server-2013-users-table.md">Lync Server 2013 のユーザーテーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a3e37-125">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a3e37-126"><strong>EndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="a3e37-126"><strong>EndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="a3e37-127">長さ</span><span class="sxs-lookup"><span data-stu-id="a3e37-127">uniqueidentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a3e37-128">登録エンドポイントを識別する GUID。</span><span class="sxs-lookup"><span data-stu-id="a3e37-128">A GUID to identify a registration endpoint.</span></span> <span data-ttu-id="a3e37-129">通常、同じユーザーの同じコンピューターの register イベントには、同じエンドポイント ID があります。</span><span class="sxs-lookup"><span data-stu-id="a3e37-129">Usually the register event from the same computer of the same user will have the same endpoint ID.</span></span> <span data-ttu-id="a3e37-130">各コンピューターには、別のエンドポイント ID があります。</span><span class="sxs-lookup"><span data-stu-id="a3e37-130">Different machines have a different endpoint ID.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a3e37-131"><strong>Endポインタ a</strong></span><span class="sxs-lookup"><span data-stu-id="a3e37-131"><strong>EndpointEra</strong></span></span></p></td>
<td><p><span data-ttu-id="a3e37-132">長さ</span><span class="sxs-lookup"><span data-stu-id="a3e37-132">uniqueIdentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a3e37-133">同じユーザーと同じエンドポイントを含む登録を区別するために使用される ID です。</span><span class="sxs-lookup"><span data-stu-id="a3e37-133">ID used to differentiate registrations that involve the same user and the same endpoint.</span></span></p>
<p><span data-ttu-id="a3e37-134">このフィールドは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="a3e37-134">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a3e37-135"><strong>ClientVersionId</strong></span><span class="sxs-lookup"><span data-stu-id="a3e37-135"><strong>ClientVersionId</strong></span></span></p></td>
<td><p><span data-ttu-id="a3e37-136">int</span><span class="sxs-lookup"><span data-stu-id="a3e37-136">int</span></span></p></td>
<td><p><span data-ttu-id="a3e37-137">外部</span><span class="sxs-lookup"><span data-stu-id="a3e37-137">Foreign</span></span></p></td>
<td><p><span data-ttu-id="a3e37-138">現在のユーザーのクライアントバージョン。</span><span class="sxs-lookup"><span data-stu-id="a3e37-138">Client version of current user.</span></span> <span data-ttu-id="a3e37-139">詳細については、「 <a href="lync-server-2013-clientversions-table.md">Lync Server 2013 の Clientversions の表</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a3e37-139">See the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a3e37-140"><strong>RegistrarId</strong></span><span class="sxs-lookup"><span data-stu-id="a3e37-140"><strong>RegistrarId</strong></span></span></p></td>
<td><p><span data-ttu-id="a3e37-141">int</span><span class="sxs-lookup"><span data-stu-id="a3e37-141">int</span></span></p></td>
<td><p><span data-ttu-id="a3e37-142">外部</span><span class="sxs-lookup"><span data-stu-id="a3e37-142">Foreign</span></span></p></td>
<td><p><span data-ttu-id="a3e37-143">登録に使用されるレジストラーサーバーの ID です。</span><span class="sxs-lookup"><span data-stu-id="a3e37-143">ID of the Registrar Server used for registration.</span></span> <span data-ttu-id="a3e37-144">詳細については、「 <a href="lync-server-2013-servers-table.md">Lync Server 2013 のサーバーの表</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a3e37-144">See the <a href="lync-server-2013-servers-table.md">Servers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a3e37-145"><strong>PoolId</strong></span><span class="sxs-lookup"><span data-stu-id="a3e37-145"><strong>PoolId</strong></span></span></p></td>
<td><p><span data-ttu-id="a3e37-146">int</span><span class="sxs-lookup"><span data-stu-id="a3e37-146">int</span></span></p></td>
<td><p><span data-ttu-id="a3e37-147">外部</span><span class="sxs-lookup"><span data-stu-id="a3e37-147">Foreign</span></span></p></td>
<td><p><span data-ttu-id="a3e37-148">セッションがキャプチャされたプールの ID です。</span><span class="sxs-lookup"><span data-stu-id="a3e37-148">ID of the pool in which the session was captured.</span></span> <span data-ttu-id="a3e37-149">詳細については、「 <a href="lync-server-2013-pools-table.md">Lync Server 2013 のプールテーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a3e37-149">See the <a href="lync-server-2013-pools-table.md">Pools table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a3e37-150"><strong>EdgeServerId</strong></span><span class="sxs-lookup"><span data-stu-id="a3e37-150"><strong>EdgeServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="a3e37-151">int</span><span class="sxs-lookup"><span data-stu-id="a3e37-151">int</span></span></p></td>
<td><p><span data-ttu-id="a3e37-152">外部</span><span class="sxs-lookup"><span data-stu-id="a3e37-152">Foreign</span></span></p></td>
<td><p><span data-ttu-id="a3e37-153">エッジサーバーの登録が進行中です。</span><span class="sxs-lookup"><span data-stu-id="a3e37-153">Edge Server the registration is going through.</span></span> <span data-ttu-id="a3e37-154">詳細については、「 <a href="lync-server-2013-edgeservers-table.md">Lync Server 2013 の EdgeServers テーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a3e37-154">See the <a href="lync-server-2013-edgeservers-table.md">EdgeServers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a3e37-155"><strong>IsInternal</strong></span><span class="sxs-lookup"><span data-stu-id="a3e37-155"><strong>IsInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="a3e37-156">わずか</span><span class="sxs-lookup"><span data-stu-id="a3e37-156">Bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a3e37-157">ユーザーが内部からログオンしているかどうか。</span><span class="sxs-lookup"><span data-stu-id="a3e37-157">Whether the user is logged on from internal or not.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a3e37-158"><strong>IsUserServiceAvailable</strong></span><span class="sxs-lookup"><span data-stu-id="a3e37-158"><strong>IsUserServiceAvailable</strong></span></span></p></td>
<td><p><span data-ttu-id="a3e37-159">bit</span><span class="sxs-lookup"><span data-stu-id="a3e37-159">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a3e37-160">UserService が利用できるかどうか。</span><span class="sxs-lookup"><span data-stu-id="a3e37-160">Whether the UserService is available or not.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a3e37-161"><strong>IsPrimaryRegistrar</strong></span><span class="sxs-lookup"><span data-stu-id="a3e37-161"><strong>IsPrimaryRegistrar</strong></span></span></p></td>
<td><p><span data-ttu-id="a3e37-162">bit</span><span class="sxs-lookup"><span data-stu-id="a3e37-162">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a3e37-163">プライマリレジストラーに登録するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="a3e37-163">Whether register to the primary Registrar or not.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a3e37-164"><strong>IsPrimaryRegistrarCentral</strong></span><span class="sxs-lookup"><span data-stu-id="a3e37-164"><strong>IsPrimaryRegistrarCentral</strong></span></span></p></td>
<td><p><span data-ttu-id="a3e37-165">bit</span><span class="sxs-lookup"><span data-stu-id="a3e37-165">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a3e37-166">ユーザーが survivable branch アプライアンスに登録されているかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="a3e37-166">Indicates whether or not the user is registered with a survivable branch appliance.</span></span></p>
<p><span data-ttu-id="a3e37-167">このフィールドは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="a3e37-167">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a3e37-168"><strong>RegisterTime</strong></span><span class="sxs-lookup"><span data-stu-id="a3e37-168"><strong>RegisterTime</strong></span></span></p></td>
<td><p><span data-ttu-id="a3e37-169">datetime</span><span class="sxs-lookup"><span data-stu-id="a3e37-169">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a3e37-170">登録時間。</span><span class="sxs-lookup"><span data-stu-id="a3e37-170">Registration time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a3e37-171"><strong>DeRegisterTime</strong></span><span class="sxs-lookup"><span data-stu-id="a3e37-171"><strong>DeRegisterTime</strong></span></span></p></td>
<td><p><span data-ttu-id="a3e37-172">datetime</span><span class="sxs-lookup"><span data-stu-id="a3e37-172">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a3e37-173">登録解除時間。</span><span class="sxs-lookup"><span data-stu-id="a3e37-173">De-Registration time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a3e37-174"><strong>返信</strong></span><span class="sxs-lookup"><span data-stu-id="a3e37-174"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="a3e37-175">int</span><span class="sxs-lookup"><span data-stu-id="a3e37-175">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a3e37-176">Register 要求の応答コード。</span><span class="sxs-lookup"><span data-stu-id="a3e37-176">Response code of the register request.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a3e37-177"><strong>DiagnosticId</strong></span><span class="sxs-lookup"><span data-stu-id="a3e37-177"><strong>DiagnosticId</strong></span></span></p></td>
<td><p><span data-ttu-id="a3e37-178">int</span><span class="sxs-lookup"><span data-stu-id="a3e37-178">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a3e37-179">Register 要求の診断 ID。</span><span class="sxs-lookup"><span data-stu-id="a3e37-179">Diagnostic ID of the register request.</span></span> <span data-ttu-id="a3e37-180">これにより、診断情報の種類が示されます。</span><span class="sxs-lookup"><span data-stu-id="a3e37-180">This indicates that diagnostic information type.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a3e37-181"><strong>DeviceId</strong></span><span class="sxs-lookup"><span data-stu-id="a3e37-181"><strong>DeviceId</strong></span></span></p></td>
<td><p><span data-ttu-id="a3e37-182">int</span><span class="sxs-lookup"><span data-stu-id="a3e37-182">int</span></span></p></td>
<td><p><span data-ttu-id="a3e37-183">外部</span><span class="sxs-lookup"><span data-stu-id="a3e37-183">Foreign</span></span></p></td>
<td><p><span data-ttu-id="a3e37-184">Register 要求の取得元のデバイス。</span><span class="sxs-lookup"><span data-stu-id="a3e37-184">The device that the register request is coming from.</span></span> <span data-ttu-id="a3e37-185">詳細については、「 <a href="lync-server-2013-devices-table.md">Lync Server 2013 のデバイスの表</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a3e37-185">See the <a href="lync-server-2013-devices-table.md">Devices table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a3e37-186"><strong>DeRegisterTypeId</strong></span><span class="sxs-lookup"><span data-stu-id="a3e37-186"><strong>DeRegisterTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="a3e37-187">tinyint</span><span class="sxs-lookup"><span data-stu-id="a3e37-187">tinyint</span></span></p></td>
<td><p><span data-ttu-id="a3e37-188">外部</span><span class="sxs-lookup"><span data-stu-id="a3e37-188">Foreign</span></span></p></td>
<td><p><span data-ttu-id="a3e37-189">"ユーザーが開始しました"、"登録の期限切れ"、"クライアントが失敗しました" などの de レジスタの理由。</span><span class="sxs-lookup"><span data-stu-id="a3e37-189">The reason of de-register, such as ‘user initiated’, ‘registration expired’, ‘client fail’, and more.</span></span> <span data-ttu-id="a3e37-190">詳細については、「 <a href="lync-server-2013-deregistertype-table.md">Lync Server 2013 の DeRegisterType テーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a3e37-190">See the <a href="lync-server-2013-deregistertype-table.md">DeRegisterType table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a3e37-191"><strong>IPAddress</strong></span><span class="sxs-lookup"><span data-stu-id="a3e37-191"><strong>IPAddress</strong></span></span></p></td>
<td><p><span data-ttu-id="a3e37-192">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="a3e37-192">nvarchar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a3e37-193">ユーザーが登録したエンドポイントの IP アドレス。</span><span class="sxs-lookup"><span data-stu-id="a3e37-193">IP address of the endpoint the user registered with.</span></span> <span data-ttu-id="a3e37-194">これは IPv4 アドレスまたは IPv6 アドレスにすることができます。</span><span class="sxs-lookup"><span data-stu-id="a3e37-194">This can be an IPv4 address or an IPv6 address.</span></span></p>
<p><span data-ttu-id="a3e37-195">このフィールドは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="a3e37-195">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

