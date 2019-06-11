---
title: 'Lync Server 2013: Registration テーブル'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Registration table
ms:assetid: 05ff9dd3-1aaa-4af0-bd69-8789fb8eaeb3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398114(v=OCS.15)
ms:contentKeyID: 48183298
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dfee81d83fb58b2fbeccff68a672da47e6770bd6
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823799"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="registration-table-in-lync-server-2013"></a><span data-ttu-id="bdc12-102">Lync Server 2013 の Registration テーブル</span><span class="sxs-lookup"><span data-stu-id="bdc12-102">Registration table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bdc12-103">_**最終更新日:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="bdc12-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="bdc12-104">各レコードは、1つのユーザー登録イベントを表します。</span><span class="sxs-lookup"><span data-stu-id="bdc12-104">Each record represents one user registration event.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="bdc12-105">列</span><span class="sxs-lookup"><span data-stu-id="bdc12-105">Column</span></span></th>
<th><span data-ttu-id="bdc12-106">データ型</span><span class="sxs-lookup"><span data-stu-id="bdc12-106">Data Type</span></span></th>
<th><span data-ttu-id="bdc12-107">キー/インデックス</span><span class="sxs-lookup"><span data-stu-id="bdc12-107">Key/Index</span></span></th>
<th><span data-ttu-id="bdc12-108">詳細</span><span class="sxs-lookup"><span data-stu-id="bdc12-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bdc12-109"><strong>セッション Id</strong></span><span class="sxs-lookup"><span data-stu-id="bdc12-109"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="bdc12-110">datetime</span><span class="sxs-lookup"><span data-stu-id="bdc12-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="bdc12-111">プライマリ、外部</span><span class="sxs-lookup"><span data-stu-id="bdc12-111">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="bdc12-112">セッション要求の時刻。</span><span class="sxs-lookup"><span data-stu-id="bdc12-112">Time of session request.</span></span> <span data-ttu-id="bdc12-113">セッションを一意に識別するために<strong>Sessionidseq</strong>と組み合わせて使用されます。</span><span class="sxs-lookup"><span data-stu-id="bdc12-113">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="bdc12-114">詳細については、「 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 のダイアログテーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bdc12-114">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bdc12-115"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="bdc12-115"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="bdc12-116">int</span><span class="sxs-lookup"><span data-stu-id="bdc12-116">int</span></span></p></td>
<td><p><span data-ttu-id="bdc12-117">プライマリ、外部</span><span class="sxs-lookup"><span data-stu-id="bdc12-117">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="bdc12-118">セッションを識別する ID 番号。</span><span class="sxs-lookup"><span data-stu-id="bdc12-118">ID number to identify the session.</span></span> <span data-ttu-id="bdc12-119">セッションを一意に識別するために<strong>Sessionidtime</strong>と組み合わせて使用されます。</span><span class="sxs-lookup"><span data-stu-id="bdc12-119">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.</span></span> <span data-ttu-id="bdc12-120">詳細については、「 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 のダイアログテーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bdc12-120">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bdc12-121"><strong>UserId</strong></span><span class="sxs-lookup"><span data-stu-id="bdc12-121"><strong>UserId</strong></span></span></p></td>
<td><p><span data-ttu-id="bdc12-122">int</span><span class="sxs-lookup"><span data-stu-id="bdc12-122">int</span></span></p></td>
<td><p><span data-ttu-id="bdc12-123">外部</span><span class="sxs-lookup"><span data-stu-id="bdc12-123">Foreign</span></span></p></td>
<td><p><span data-ttu-id="bdc12-124">ユーザー ID。</span><span class="sxs-lookup"><span data-stu-id="bdc12-124">The user ID.</span></span> <span data-ttu-id="bdc12-125">詳細については、「 <a href="lync-server-2013-users-table.md">Lync Server 2013 のユーザーテーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bdc12-125">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bdc12-126"><strong>EndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="bdc12-126"><strong>EndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="bdc12-127">長さ</span><span class="sxs-lookup"><span data-stu-id="bdc12-127">uniqueidentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="bdc12-128">登録エンドポイントを識別する GUID。</span><span class="sxs-lookup"><span data-stu-id="bdc12-128">A GUID to identify a registration endpoint.</span></span> <span data-ttu-id="bdc12-129">通常、同じユーザーの同じコンピューターの register イベントには、同じエンドポイント ID があります。</span><span class="sxs-lookup"><span data-stu-id="bdc12-129">Usually the register event from the same computer of the same user will have the same endpoint ID.</span></span> <span data-ttu-id="bdc12-130">各コンピューターには、別のエンドポイント ID があります。</span><span class="sxs-lookup"><span data-stu-id="bdc12-130">Different machines have a different endpoint ID.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bdc12-131"><strong>Endポインタ a</strong></span><span class="sxs-lookup"><span data-stu-id="bdc12-131"><strong>EndpointEra</strong></span></span></p></td>
<td><p><span data-ttu-id="bdc12-132">長さ</span><span class="sxs-lookup"><span data-stu-id="bdc12-132">uniqueIdentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="bdc12-133">同じユーザーと同じエンドポイントを含む登録を区別するために使用される ID です。</span><span class="sxs-lookup"><span data-stu-id="bdc12-133">ID used to differentiate registrations that involve the same user and the same endpoint.</span></span></p>
<p><span data-ttu-id="bdc12-134">このフィールドは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="bdc12-134">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bdc12-135"><strong>ClientVersionId</strong></span><span class="sxs-lookup"><span data-stu-id="bdc12-135"><strong>ClientVersionId</strong></span></span></p></td>
<td><p><span data-ttu-id="bdc12-136">int</span><span class="sxs-lookup"><span data-stu-id="bdc12-136">int</span></span></p></td>
<td><p><span data-ttu-id="bdc12-137">外部</span><span class="sxs-lookup"><span data-stu-id="bdc12-137">Foreign</span></span></p></td>
<td><p><span data-ttu-id="bdc12-138">現在のユーザーのクライアントバージョン。</span><span class="sxs-lookup"><span data-stu-id="bdc12-138">Client version of current user.</span></span> <span data-ttu-id="bdc12-139">詳細については、「 <a href="lync-server-2013-clientversions-table.md">Lync Server 2013 の Clientversions の表</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bdc12-139">See the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bdc12-140"><strong>RegistrarId</strong></span><span class="sxs-lookup"><span data-stu-id="bdc12-140"><strong>RegistrarId</strong></span></span></p></td>
<td><p><span data-ttu-id="bdc12-141">int</span><span class="sxs-lookup"><span data-stu-id="bdc12-141">int</span></span></p></td>
<td><p><span data-ttu-id="bdc12-142">外部</span><span class="sxs-lookup"><span data-stu-id="bdc12-142">Foreign</span></span></p></td>
<td><p><span data-ttu-id="bdc12-143">登録に使用されるレジストラーサーバーの ID です。</span><span class="sxs-lookup"><span data-stu-id="bdc12-143">ID of the Registrar Server used for registration.</span></span> <span data-ttu-id="bdc12-144">詳細については、「 <a href="lync-server-2013-servers-table.md">Lync Server 2013 のサーバーの表</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bdc12-144">See the <a href="lync-server-2013-servers-table.md">Servers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bdc12-145"><strong>PoolId</strong></span><span class="sxs-lookup"><span data-stu-id="bdc12-145"><strong>PoolId</strong></span></span></p></td>
<td><p><span data-ttu-id="bdc12-146">int</span><span class="sxs-lookup"><span data-stu-id="bdc12-146">int</span></span></p></td>
<td><p><span data-ttu-id="bdc12-147">外部</span><span class="sxs-lookup"><span data-stu-id="bdc12-147">Foreign</span></span></p></td>
<td><p><span data-ttu-id="bdc12-148">セッションがキャプチャされたプールの ID です。</span><span class="sxs-lookup"><span data-stu-id="bdc12-148">ID of the pool in which the session was captured.</span></span> <span data-ttu-id="bdc12-149">詳細については、「 <a href="lync-server-2013-pools-table.md">Lync Server 2013 のプールテーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bdc12-149">See the <a href="lync-server-2013-pools-table.md">Pools table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bdc12-150"><strong>EdgeServerId</strong></span><span class="sxs-lookup"><span data-stu-id="bdc12-150"><strong>EdgeServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="bdc12-151">int</span><span class="sxs-lookup"><span data-stu-id="bdc12-151">int</span></span></p></td>
<td><p><span data-ttu-id="bdc12-152">外部</span><span class="sxs-lookup"><span data-stu-id="bdc12-152">Foreign</span></span></p></td>
<td><p><span data-ttu-id="bdc12-153">エッジサーバーの登録が進行中です。</span><span class="sxs-lookup"><span data-stu-id="bdc12-153">Edge Server the registration is going through.</span></span> <span data-ttu-id="bdc12-154">詳細については、「 <a href="lync-server-2013-edgeservers-table.md">Lync Server 2013 の EdgeServers テーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bdc12-154">See the <a href="lync-server-2013-edgeservers-table.md">EdgeServers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bdc12-155"><strong>IsInternal</strong></span><span class="sxs-lookup"><span data-stu-id="bdc12-155"><strong>IsInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="bdc12-156">わずか</span><span class="sxs-lookup"><span data-stu-id="bdc12-156">Bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="bdc12-157">ユーザーが内部からログオンしているかどうか。</span><span class="sxs-lookup"><span data-stu-id="bdc12-157">Whether the user is logged on from internal or not.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bdc12-158"><strong>IsUserServiceAvailable</strong></span><span class="sxs-lookup"><span data-stu-id="bdc12-158"><strong>IsUserServiceAvailable</strong></span></span></p></td>
<td><p><span data-ttu-id="bdc12-159">bit</span><span class="sxs-lookup"><span data-stu-id="bdc12-159">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="bdc12-160">UserService が利用できるかどうか。</span><span class="sxs-lookup"><span data-stu-id="bdc12-160">Whether the UserService is available or not.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bdc12-161"><strong>IsPrimaryRegistrar</strong></span><span class="sxs-lookup"><span data-stu-id="bdc12-161"><strong>IsPrimaryRegistrar</strong></span></span></p></td>
<td><p><span data-ttu-id="bdc12-162">bit</span><span class="sxs-lookup"><span data-stu-id="bdc12-162">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="bdc12-163">プライマリレジストラーに登録するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="bdc12-163">Whether register to the primary Registrar or not.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bdc12-164"><strong>IsPrimaryRegistrarCentral</strong></span><span class="sxs-lookup"><span data-stu-id="bdc12-164"><strong>IsPrimaryRegistrarCentral</strong></span></span></p></td>
<td><p><span data-ttu-id="bdc12-165">bit</span><span class="sxs-lookup"><span data-stu-id="bdc12-165">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="bdc12-166">ユーザーが survivable branch アプライアンスに登録されているかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="bdc12-166">Indicates whether or not the user is registered with a survivable branch appliance.</span></span></p>
<p><span data-ttu-id="bdc12-167">このフィールドは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="bdc12-167">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bdc12-168"><strong>RegisterTime</strong></span><span class="sxs-lookup"><span data-stu-id="bdc12-168"><strong>RegisterTime</strong></span></span></p></td>
<td><p><span data-ttu-id="bdc12-169">datetime</span><span class="sxs-lookup"><span data-stu-id="bdc12-169">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="bdc12-170">登録時間。</span><span class="sxs-lookup"><span data-stu-id="bdc12-170">Registration time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bdc12-171"><strong>DeRegisterTime</strong></span><span class="sxs-lookup"><span data-stu-id="bdc12-171"><strong>DeRegisterTime</strong></span></span></p></td>
<td><p><span data-ttu-id="bdc12-172">datetime</span><span class="sxs-lookup"><span data-stu-id="bdc12-172">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="bdc12-173">登録解除時間。</span><span class="sxs-lookup"><span data-stu-id="bdc12-173">De-Registration time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bdc12-174"><strong>返信</strong></span><span class="sxs-lookup"><span data-stu-id="bdc12-174"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="bdc12-175">int</span><span class="sxs-lookup"><span data-stu-id="bdc12-175">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="bdc12-176">Register 要求の応答コード。</span><span class="sxs-lookup"><span data-stu-id="bdc12-176">Response code of the register request.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bdc12-177"><strong>DiagnosticId</strong></span><span class="sxs-lookup"><span data-stu-id="bdc12-177"><strong>DiagnosticId</strong></span></span></p></td>
<td><p><span data-ttu-id="bdc12-178">int</span><span class="sxs-lookup"><span data-stu-id="bdc12-178">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="bdc12-179">Register 要求の診断 ID。</span><span class="sxs-lookup"><span data-stu-id="bdc12-179">Diagnostic ID of the register request.</span></span> <span data-ttu-id="bdc12-180">これにより、診断情報の種類が示されます。</span><span class="sxs-lookup"><span data-stu-id="bdc12-180">This indicates that diagnostic information type.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bdc12-181"><strong>DeviceId</strong></span><span class="sxs-lookup"><span data-stu-id="bdc12-181"><strong>DeviceId</strong></span></span></p></td>
<td><p><span data-ttu-id="bdc12-182">int</span><span class="sxs-lookup"><span data-stu-id="bdc12-182">int</span></span></p></td>
<td><p><span data-ttu-id="bdc12-183">外部</span><span class="sxs-lookup"><span data-stu-id="bdc12-183">Foreign</span></span></p></td>
<td><p><span data-ttu-id="bdc12-184">Register 要求の取得元のデバイス。</span><span class="sxs-lookup"><span data-stu-id="bdc12-184">The device that the register request is coming from.</span></span> <span data-ttu-id="bdc12-185">詳細については、「 <a href="lync-server-2013-devices-table.md">Lync Server 2013 のデバイスの表</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bdc12-185">See the <a href="lync-server-2013-devices-table.md">Devices table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bdc12-186"><strong>DeRegisterTypeId</strong></span><span class="sxs-lookup"><span data-stu-id="bdc12-186"><strong>DeRegisterTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="bdc12-187">tinyint</span><span class="sxs-lookup"><span data-stu-id="bdc12-187">tinyint</span></span></p></td>
<td><p><span data-ttu-id="bdc12-188">外部</span><span class="sxs-lookup"><span data-stu-id="bdc12-188">Foreign</span></span></p></td>
<td><p><span data-ttu-id="bdc12-189">"ユーザーが開始しました"、"登録の期限切れ"、"クライアントが失敗しました" などの de レジスタの理由。</span><span class="sxs-lookup"><span data-stu-id="bdc12-189">The reason of de-register, such as ‘user initiated’, ‘registration expired’, ‘client fail’, and more.</span></span> <span data-ttu-id="bdc12-190">詳細については、「 <a href="lync-server-2013-deregistertype-table.md">Lync Server 2013 の DeRegisterType テーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bdc12-190">See the <a href="lync-server-2013-deregistertype-table.md">DeRegisterType table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bdc12-191"><strong>IPAddress</strong></span><span class="sxs-lookup"><span data-stu-id="bdc12-191"><strong>IPAddress</strong></span></span></p></td>
<td><p><span data-ttu-id="bdc12-192">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="bdc12-192">nvarchar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="bdc12-193">ユーザーが登録したエンドポイントの IP アドレス。</span><span class="sxs-lookup"><span data-stu-id="bdc12-193">IP address of the endpoint the user registered with.</span></span> <span data-ttu-id="bdc12-194">これは IPv4 アドレスまたは IPv6 アドレスにすることができます。</span><span class="sxs-lookup"><span data-stu-id="bdc12-194">This can be an IPv4 address or an IPv6 address.</span></span></p>
<p><span data-ttu-id="bdc12-195">このフィールドは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="bdc12-195">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

