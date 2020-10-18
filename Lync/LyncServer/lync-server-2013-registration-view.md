---
title: 'Lync Server 2013: 登録ビュー'
description: 'Lync Server 2013: 登録ビュー。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Registration view
ms:assetid: 8a42bc7d-3d4f-43c1-9e15-89b2ee419ade
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688120(v=OCS.15)
ms:contentKeyID: 49733718
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: be169cafc324f89cacedda154ca49a8ff1ff39aa
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48578529"
---
# <a name="registration-view-in-lync-server-2013"></a><span data-ttu-id="31241-103">Lync Server 2013 の登録ビュー</span><span class="sxs-lookup"><span data-stu-id="31241-103">Registration view in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="31241-104">_**トピックの最終更新日:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="31241-104">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="31241-105">登録ビューでは、ユーザー登録に関する情報を格納します。</span><span class="sxs-lookup"><span data-stu-id="31241-105">The Registration view stores information about user registration.</span></span> <span data-ttu-id="31241-106">このビューは、Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="31241-106">This view was introduced in Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="31241-107">Column</span><span class="sxs-lookup"><span data-stu-id="31241-107">Column</span></span></th>
<th><span data-ttu-id="31241-108">データ型</span><span class="sxs-lookup"><span data-stu-id="31241-108">Data Type</span></span></th>
<th><span data-ttu-id="31241-109">詳細</span><span class="sxs-lookup"><span data-stu-id="31241-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="31241-110"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="31241-110"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="31241-111">日付型</span><span class="sxs-lookup"><span data-stu-id="31241-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="31241-112">セッション要求の時間。</span><span class="sxs-lookup"><span data-stu-id="31241-112">Time of session request.</span></span> <span data-ttu-id="31241-113">セッションを一意に識別するために SessionIdSeq と組み合わせて使用されます。</span><span class="sxs-lookup"><span data-stu-id="31241-113">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="31241-114">詳細については、「 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 のダイアログテーブル</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="31241-114">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="31241-115"><strong>Sessionidseq と</strong></span><span class="sxs-lookup"><span data-stu-id="31241-115"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="31241-116">int</span><span class="sxs-lookup"><span data-stu-id="31241-116">int</span></span></p></td>
<td><p><span data-ttu-id="31241-117">セッションを識別するための ID 番号。</span><span class="sxs-lookup"><span data-stu-id="31241-117">ID number to identify the session.</span></span> <span data-ttu-id="31241-118">セッションを一意に識別するために SessionIdTime と組み合わせて使用されます。</span><span class="sxs-lookup"><span data-stu-id="31241-118">Used in conjunction with SessionIdTime to uniquely identify a session.</span></span> <span data-ttu-id="31241-119">詳細については、「 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 のダイアログテーブル</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="31241-119">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="31241-120"><strong>RegisterTime</strong></span><span class="sxs-lookup"><span data-stu-id="31241-120"><strong>RegisterTime</strong></span></span></p></td>
<td><p><span data-ttu-id="31241-121">日付型</span><span class="sxs-lookup"><span data-stu-id="31241-121">datetime</span></span></p></td>
<td><p><span data-ttu-id="31241-122">登録が発生した時間。</span><span class="sxs-lookup"><span data-stu-id="31241-122">Time at which registration occurred.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="31241-123"><strong>UserUri</strong></span><span class="sxs-lookup"><span data-stu-id="31241-123"><strong>UserUri</strong></span></span></p></td>
<td><p><span data-ttu-id="31241-124">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="31241-124">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="31241-125">登録したユーザーの URI</span><span class="sxs-lookup"><span data-stu-id="31241-125">URI of the user who registered.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="31241-126"><strong>Useruritoff</strong></span><span class="sxs-lookup"><span data-stu-id="31241-126"><strong>UserUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="31241-127">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="31241-127">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="31241-128">登録したユーザーの URI の種類。</span><span class="sxs-lookup"><span data-stu-id="31241-128">Type of URI of the user who registered.</span></span> <span data-ttu-id="31241-129">詳細については、「 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013 の UriTypes テーブル</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="31241-129">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="31241-130"><strong>UserTenant</strong></span><span class="sxs-lookup"><span data-stu-id="31241-130"><strong>UserTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="31241-131">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="31241-131">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="31241-132">登録したユーザーのテナント ID。</span><span class="sxs-lookup"><span data-stu-id="31241-132">Tenant of the user who registered.</span></span> <span data-ttu-id="31241-133">詳細については、「 <a href="lync-server-2013-tenants-table.md">Lync Server 2013 のテナントの表</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="31241-133">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="31241-134"><strong>EndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="31241-134"><strong>EndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="31241-135">識別子</span><span class="sxs-lookup"><span data-stu-id="31241-135">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="31241-136">ユーザーの登録に使用するエンドポイントの一意の識別子。</span><span class="sxs-lookup"><span data-stu-id="31241-136">Unique identifier of the endpoint of the user registered with.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="31241-137"><strong>Endポインター a</strong></span><span class="sxs-lookup"><span data-stu-id="31241-137"><strong>EndpointEra</strong></span></span></p></td>
<td><p><span data-ttu-id="31241-138">識別子</span><span class="sxs-lookup"><span data-stu-id="31241-138">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="31241-139">同じユーザーおよび同じエンドポイントが含まれる登録を区別するための一意の識別子。</span><span class="sxs-lookup"><span data-stu-id="31241-139">Unique identifier used to differentiate registrations that involve the same user and the same endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="31241-140"><strong>DeRegisterType</strong></span><span class="sxs-lookup"><span data-stu-id="31241-140"><strong>DeRegisterType</strong></span></span></p></td>
<td><p><span data-ttu-id="31241-141">日付型</span><span class="sxs-lookup"><span data-stu-id="31241-141">datetime</span></span></p></td>
<td><p><span data-ttu-id="31241-142">登録解除が発生した時間。</span><span class="sxs-lookup"><span data-stu-id="31241-142">Time at which deregistration occurred.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="31241-143"><strong>DeRegisterReason</strong></span><span class="sxs-lookup"><span data-stu-id="31241-143"><strong>DeRegisterReason</strong></span></span></p></td>
<td><p><span data-ttu-id="31241-144">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="31241-144">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="31241-145">登録解除の理由。</span><span class="sxs-lookup"><span data-stu-id="31241-145">Reason for deregistration.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="31241-146"><strong>ClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="31241-146"><strong>ClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="31241-147">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="31241-147">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="31241-148">登録したユーザーが使用しているクライアントのバージョン。</span><span class="sxs-lookup"><span data-stu-id="31241-148">Version of client used by the user who registered.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="31241-149"><strong>ClientType</strong></span><span class="sxs-lookup"><span data-stu-id="31241-149"><strong>ClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="31241-150">int</span><span class="sxs-lookup"><span data-stu-id="31241-150">int</span></span></p></td>
<td><p><span data-ttu-id="31241-151">登録したユーザーが使用しているクライアント。</span><span class="sxs-lookup"><span data-stu-id="31241-151">Client used by the user who registered.</span></span> <span data-ttu-id="31241-152">詳細については、「 <a href="lync-server-2013-useragentdef-table.md">Lync Server 2013 の Useragentdef テーブル</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="31241-152">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="31241-153"><strong>ClientCategory</strong></span><span class="sxs-lookup"><span data-stu-id="31241-153"><strong>ClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="31241-154">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="31241-154">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="31241-155">登録したユーザーが使用しているクライアントのカテゴリ。</span><span class="sxs-lookup"><span data-stu-id="31241-155">Category of the client used by the user who registered.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="31241-156"><strong>IpAddress</strong></span><span class="sxs-lookup"><span data-stu-id="31241-156"><strong>IpAddress</strong></span></span></p></td>
<td><p><span data-ttu-id="31241-157">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="31241-157">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="31241-158">ユーザーが登録した IP アドレス。</span><span class="sxs-lookup"><span data-stu-id="31241-158">IP Address the user registered with.</span></span> <span data-ttu-id="31241-159">これは、IPv4 または IPv6 のアドレスである場合があります。</span><span class="sxs-lookup"><span data-stu-id="31241-159">This may be an IPv4 or IPv6 address.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="31241-160"><strong>DialogId</strong></span><span class="sxs-lookup"><span data-stu-id="31241-160"><strong>DialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="31241-161">varstring (775)</span><span class="sxs-lookup"><span data-stu-id="31241-161">varstring(775)</span></span></p></td>
<td><p><span data-ttu-id="31241-p108">SIP ダイアログ ID。形式は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="31241-p108">SIP dialog ID. The format of the is:</span></span></p>
<p><span data-ttu-id="31241-164">dialog、from タグ、およびタグ</span><span class="sxs-lookup"><span data-stu-id="31241-164">dialog;from-tag;to-tag</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="31241-165"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="31241-165"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="31241-166">int</span><span class="sxs-lookup"><span data-stu-id="31241-166">int</span></span></p></td>
<td><p><span data-ttu-id="31241-p109">セッションへの招待に対する SIP 応答コード。このフィールドには通常、セッションの最初の INVITE メッセージから生成されるデータが設定されます。INVITE メッセージがない場合は、フィールドには、最初の関連する SIP メッセージ (BYE、CANCEL、MESSAGE、または INFO) の日時が設定されます。</span><span class="sxs-lookup"><span data-stu-id="31241-p109">SIP response code to the session invitation. This field is typically populated by data generated from the initial INVITE message in the session. If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="31241-170"><strong>DiagnosticId</strong></span><span class="sxs-lookup"><span data-stu-id="31241-170"><strong>DiagnosticId</strong></span></span></p></td>
<td><p><span data-ttu-id="31241-171">int</span><span class="sxs-lookup"><span data-stu-id="31241-171">int</span></span></p></td>
<td><p><span data-ttu-id="31241-172">SIP ヘッダーから取得された診断 ID。</span><span class="sxs-lookup"><span data-stu-id="31241-172">Diagnostic ID captured from SIP header.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="31241-173"><strong>レジストラー</strong></span><span class="sxs-lookup"><span data-stu-id="31241-173"><strong>Registrar</strong></span></span></p></td>
<td><p><span data-ttu-id="31241-174">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="31241-174">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="31241-175">レジストラーの FQDN。</span><span class="sxs-lookup"><span data-stu-id="31241-175">FQDN of the Registrar.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="31241-176"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="31241-176"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="31241-177">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="31241-177">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="31241-178">セッションのデータをキャプチャしたプールの FQDN。</span><span class="sxs-lookup"><span data-stu-id="31241-178">FQDN of the pool that captured the data for the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="31241-179"><strong>EdgeServer</strong></span><span class="sxs-lookup"><span data-stu-id="31241-179"><strong>EdgeServer</strong></span></span></p></td>
<td><p><span data-ttu-id="31241-180">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="31241-180">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="31241-181">登録したユーザーが使用しているエッジ サーバーの FQDN。</span><span class="sxs-lookup"><span data-stu-id="31241-181">FQDN of the Edge Server used by the user who registered.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="31241-182"><strong>IsInternal</strong></span><span class="sxs-lookup"><span data-stu-id="31241-182"><strong>IsInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="31241-183">若干</span><span class="sxs-lookup"><span data-stu-id="31241-183">bit</span></span></p></td>
<td><p><span data-ttu-id="31241-184">ユーザーが内部ネットワークからログオンしているかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="31241-184">Indicates whether the user logged on from the internal network.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="31241-185"><strong>IsUserServiceAvailable</strong></span><span class="sxs-lookup"><span data-stu-id="31241-185"><strong>IsUserServiceAvailable</strong></span></span></p></td>
<td><p><span data-ttu-id="31241-186">若干</span><span class="sxs-lookup"><span data-stu-id="31241-186">bit</span></span></p></td>
<td><p><span data-ttu-id="31241-187">登録時に UserService が使用可能であったかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="31241-187">Indicates whether the UserService was available at registration time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="31241-188"><strong>IsPrimaryRegistrar</strong></span><span class="sxs-lookup"><span data-stu-id="31241-188"><strong>IsPrimaryRegistrar</strong></span></span></p></td>
<td><p><span data-ttu-id="31241-189">若干</span><span class="sxs-lookup"><span data-stu-id="31241-189">bit</span></span></p></td>
<td><p><span data-ttu-id="31241-190">登録がプライマリ レジストラーを使用して行われたかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="31241-190">Indicates whether registration was with the primary Registrar.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="31241-191"><strong>DeviceMacAddress</strong></span><span class="sxs-lookup"><span data-stu-id="31241-191"><strong>DeviceMacAddress</strong></span></span></p></td>
<td><p><span data-ttu-id="31241-192">bigint</span><span class="sxs-lookup"><span data-stu-id="31241-192">bigint</span></span></p></td>
<td><p><span data-ttu-id="31241-193">登録されたデバイスの MAC アドレス。</span><span class="sxs-lookup"><span data-stu-id="31241-193">MAC Address of device registered.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="31241-194"><strong>DeviceManufacturer</strong></span><span class="sxs-lookup"><span data-stu-id="31241-194"><strong>DeviceManufacturer</strong></span></span></p></td>
<td><p><span data-ttu-id="31241-195">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="31241-195">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="31241-196">登録されたデバイスの製造元。</span><span class="sxs-lookup"><span data-stu-id="31241-196">Manufacturer of the device registered.</span></span> <span data-ttu-id="31241-197">詳細については、「 <a href="lync-server-2013-manufacturers-table.md">Lync Server 2013 の製造元</a> 」の表を参照してください。</span><span class="sxs-lookup"><span data-stu-id="31241-197">See the <a href="lync-server-2013-manufacturers-table.md">Manufacturers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="31241-198"><strong>Deviceハードウェアバージョン</strong></span><span class="sxs-lookup"><span data-stu-id="31241-198"><strong>DeviceHardwareVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="31241-199">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="31241-199">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="31241-200">登録されたデバイスのハードウェア バージョン。</span><span class="sxs-lookup"><span data-stu-id="31241-200">Hardware version of the device registered.</span></span> <span data-ttu-id="31241-201">詳細については、「 <a href="lync-server-2013-hardwareversions-table.md">Lync Server 2013 のハードウェアバージョン表</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="31241-201">See the <a href="lync-server-2013-hardwareversions-table.md">HardwareVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

