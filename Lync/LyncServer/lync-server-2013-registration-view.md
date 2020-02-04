---
title: 'Lync Server 2013: 登録ビュー'
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
ms.openlocfilehash: 120f0cb40bb3401a327e495a460db400a9359891
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41746847"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="registration-view-in-lync-server-2013"></a><span data-ttu-id="e5509-102">Lync Server 2013 に表示される登録情報</span><span class="sxs-lookup"><span data-stu-id="e5509-102">Registration view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e5509-103">_**最終更新日:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="e5509-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="e5509-104">登録ビューには、ユーザー登録に関する情報が格納されます。</span><span class="sxs-lookup"><span data-stu-id="e5509-104">The Registration view stores information about user registration.</span></span> <span data-ttu-id="e5509-105">このビューは、Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="e5509-105">This view was introduced in Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e5509-106">列</span><span class="sxs-lookup"><span data-stu-id="e5509-106">Column</span></span></th>
<th><span data-ttu-id="e5509-107">データ型</span><span class="sxs-lookup"><span data-stu-id="e5509-107">Data Type</span></span></th>
<th><span data-ttu-id="e5509-108">詳細</span><span class="sxs-lookup"><span data-stu-id="e5509-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e5509-109"><strong>セッション Id</strong></span><span class="sxs-lookup"><span data-stu-id="e5509-109"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="e5509-110">datetime</span><span class="sxs-lookup"><span data-stu-id="e5509-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="e5509-111">セッション要求の時刻。</span><span class="sxs-lookup"><span data-stu-id="e5509-111">Time of session request.</span></span> <span data-ttu-id="e5509-112">セッションを一意に識別するために SessionIdSeq と組み合わせて使用されます。</span><span class="sxs-lookup"><span data-stu-id="e5509-112">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="e5509-113">詳細については、「 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 のダイアログテーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e5509-113">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5509-114"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="e5509-114"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="e5509-115">int</span><span class="sxs-lookup"><span data-stu-id="e5509-115">int</span></span></p></td>
<td><p><span data-ttu-id="e5509-116">セッションを識別する ID 番号。</span><span class="sxs-lookup"><span data-stu-id="e5509-116">ID number to identify the session.</span></span> <span data-ttu-id="e5509-117">セッションを一意に識別するために SessionIdTime と組み合わせて使用されます。</span><span class="sxs-lookup"><span data-stu-id="e5509-117">Used in conjunction with SessionIdTime to uniquely identify a session.</span></span> <span data-ttu-id="e5509-118">詳細については、「 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 のダイアログテーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e5509-118">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5509-119"><strong>RegisterTime</strong></span><span class="sxs-lookup"><span data-stu-id="e5509-119"><strong>RegisterTime</strong></span></span></p></td>
<td><p><span data-ttu-id="e5509-120">datetime</span><span class="sxs-lookup"><span data-stu-id="e5509-120">datetime</span></span></p></td>
<td><p><span data-ttu-id="e5509-121">登録が発生した時刻。</span><span class="sxs-lookup"><span data-stu-id="e5509-121">Time at which registration occurred.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5509-122"><strong>UserUri</strong></span><span class="sxs-lookup"><span data-stu-id="e5509-122"><strong>UserUri</strong></span></span></p></td>
<td><p><span data-ttu-id="e5509-123">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="e5509-123">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="e5509-124">登録されたユーザーの URI。</span><span class="sxs-lookup"><span data-stu-id="e5509-124">URI of the user who registered.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5509-125"><strong>UserUriType</strong></span><span class="sxs-lookup"><span data-stu-id="e5509-125"><strong>UserUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="e5509-126">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="e5509-126">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e5509-127">登録したユーザーの URI の種類。</span><span class="sxs-lookup"><span data-stu-id="e5509-127">Type of URI of the user who registered.</span></span> <span data-ttu-id="e5509-128">詳細については、「 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013 の UriTypes テーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e5509-128">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5509-129"><strong>UserTenant</strong></span><span class="sxs-lookup"><span data-stu-id="e5509-129"><strong>UserTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="e5509-130">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="e5509-130">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e5509-131">登録したユーザーのテナント。</span><span class="sxs-lookup"><span data-stu-id="e5509-131">Tenant of the user who registered.</span></span> <span data-ttu-id="e5509-132">詳細については、「 <a href="lync-server-2013-tenants-table.md">Lync Server 2013 のテナントの一覧</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e5509-132">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5509-133"><strong>EndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="e5509-133"><strong>EndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="e5509-134">長さ</span><span class="sxs-lookup"><span data-stu-id="e5509-134">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="e5509-135">登録されているユーザーのエンドポイントの一意の識別子。</span><span class="sxs-lookup"><span data-stu-id="e5509-135">Unique identifier of the endpoint of the user registered with.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5509-136"><strong>Endポインタ a</strong></span><span class="sxs-lookup"><span data-stu-id="e5509-136"><strong>EndpointEra</strong></span></span></p></td>
<td><p><span data-ttu-id="e5509-137">長さ</span><span class="sxs-lookup"><span data-stu-id="e5509-137">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="e5509-138">同じユーザーと同じエンドポイントを含む登録を区別するために使用される一意の識別子。</span><span class="sxs-lookup"><span data-stu-id="e5509-138">Unique identifier used to differentiate registrations that involve the same user and the same endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5509-139"><strong>DeRegisterType</strong></span><span class="sxs-lookup"><span data-stu-id="e5509-139"><strong>DeRegisterType</strong></span></span></p></td>
<td><p><span data-ttu-id="e5509-140">datetime</span><span class="sxs-lookup"><span data-stu-id="e5509-140">datetime</span></span></p></td>
<td><p><span data-ttu-id="e5509-141">登録解除が行われた時刻。</span><span class="sxs-lookup"><span data-stu-id="e5509-141">Time at which deregistration occurred.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5509-142"><strong>DeRegisterReason</strong></span><span class="sxs-lookup"><span data-stu-id="e5509-142"><strong>DeRegisterReason</strong></span></span></p></td>
<td><p><span data-ttu-id="e5509-143">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="e5509-143">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e5509-144">登録解除の理由。</span><span class="sxs-lookup"><span data-stu-id="e5509-144">Reason for deregistration.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5509-145"><strong>ClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="e5509-145"><strong>ClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="e5509-146">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="e5509-146">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e5509-147">登録したユーザーによって使用されたクライアントのバージョン。</span><span class="sxs-lookup"><span data-stu-id="e5509-147">Version of client used by the user who registered.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5509-148"><strong>ClientType</strong></span><span class="sxs-lookup"><span data-stu-id="e5509-148"><strong>ClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="e5509-149">int</span><span class="sxs-lookup"><span data-stu-id="e5509-149">int</span></span></p></td>
<td><p><span data-ttu-id="e5509-150">登録したユーザーによって使用されたクライアント。</span><span class="sxs-lookup"><span data-stu-id="e5509-150">Client used by the user who registered.</span></span> <span data-ttu-id="e5509-151">詳細については、「 <a href="lync-server-2013-useragentdef-table.md">Lync Server 2013 の Useragentdef テーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e5509-151">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5509-152"><strong>ClientCategory</strong></span><span class="sxs-lookup"><span data-stu-id="e5509-152"><strong>ClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="e5509-153">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="e5509-153">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="e5509-154">登録されたユーザーによって使用されたクライアントのカテゴリです。</span><span class="sxs-lookup"><span data-stu-id="e5509-154">Category of the client used by the user who registered.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5509-155"><strong>Ip</strong></span><span class="sxs-lookup"><span data-stu-id="e5509-155"><strong>IpAddress</strong></span></span></p></td>
<td><p><span data-ttu-id="e5509-156">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="e5509-156">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e5509-157">ユーザーが登録した IP アドレス。</span><span class="sxs-lookup"><span data-stu-id="e5509-157">IP Address the user registered with.</span></span> <span data-ttu-id="e5509-158">これは IPv4 または IPv6 アドレスである可能性があります。</span><span class="sxs-lookup"><span data-stu-id="e5509-158">This may be an IPv4 or IPv6 address.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5509-159"><strong>この Id</strong></span><span class="sxs-lookup"><span data-stu-id="e5509-159"><strong>DialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="e5509-160">varstring (775)</span><span class="sxs-lookup"><span data-stu-id="e5509-160">varstring(775)</span></span></p></td>
<td><p><span data-ttu-id="e5509-161">SIP ダイアログ ID。</span><span class="sxs-lookup"><span data-stu-id="e5509-161">SIP dialog ID.</span></span> <span data-ttu-id="e5509-162">の形式は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="e5509-162">The format of the is:</span></span></p>
<p><span data-ttu-id="e5509-163">ダイアログ; 開始タグからタグへ</span><span class="sxs-lookup"><span data-stu-id="e5509-163">dialog;from-tag;to-tag</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5509-164"><strong>返信</strong></span><span class="sxs-lookup"><span data-stu-id="e5509-164"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="e5509-165">int</span><span class="sxs-lookup"><span data-stu-id="e5509-165">int</span></span></p></td>
<td><p><span data-ttu-id="e5509-166">セッション招待状への SIP 応答コード。</span><span class="sxs-lookup"><span data-stu-id="e5509-166">SIP response code to the session invitation.</span></span> <span data-ttu-id="e5509-167">通常、このフィールドは、セッションの最初の INVITE メッセージから生成されたデータによって設定されます。</span><span class="sxs-lookup"><span data-stu-id="e5509-167">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="e5509-168">招待メッセージがない場合は、最初に関連する SIP メッセージ (BYE、キャンセル、メッセージ、または情報) の日付と時刻がフィールドに設定されています。</span><span class="sxs-lookup"><span data-stu-id="e5509-168">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5509-169"><strong>DiagnosticId</strong></span><span class="sxs-lookup"><span data-stu-id="e5509-169"><strong>DiagnosticId</strong></span></span></p></td>
<td><p><span data-ttu-id="e5509-170">int</span><span class="sxs-lookup"><span data-stu-id="e5509-170">int</span></span></p></td>
<td><p><span data-ttu-id="e5509-171">SIP ヘッダーからキャプチャされた診断 ID。</span><span class="sxs-lookup"><span data-stu-id="e5509-171">Diagnostic ID captured from SIP header.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5509-172"><strong>レジストラー</strong></span><span class="sxs-lookup"><span data-stu-id="e5509-172"><strong>Registrar</strong></span></span></p></td>
<td><p><span data-ttu-id="e5509-173">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="e5509-173">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e5509-174">レジストラーの FQDN。</span><span class="sxs-lookup"><span data-stu-id="e5509-174">FQDN of the Registrar.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5509-175"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="e5509-175"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="e5509-176">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="e5509-176">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e5509-177">セッションのデータをキャプチャしたプールの FQDN。</span><span class="sxs-lookup"><span data-stu-id="e5509-177">FQDN of the pool that captured the data for the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5509-178"><strong>EdgeServer</strong></span><span class="sxs-lookup"><span data-stu-id="e5509-178"><strong>EdgeServer</strong></span></span></p></td>
<td><p><span data-ttu-id="e5509-179">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="e5509-179">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e5509-180">登録されたユーザーによって使用されたエッジサーバーの FQDN。</span><span class="sxs-lookup"><span data-stu-id="e5509-180">FQDN of the Edge Server used by the user who registered.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5509-181"><strong>IsInternal</strong></span><span class="sxs-lookup"><span data-stu-id="e5509-181"><strong>IsInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="e5509-182">bit</span><span class="sxs-lookup"><span data-stu-id="e5509-182">bit</span></span></p></td>
<td><p><span data-ttu-id="e5509-183">ユーザーが内部ネットワークからログオンしているかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="e5509-183">Indicates whether the user logged on from the internal network.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5509-184"><strong>IsUserServiceAvailable</strong></span><span class="sxs-lookup"><span data-stu-id="e5509-184"><strong>IsUserServiceAvailable</strong></span></span></p></td>
<td><p><span data-ttu-id="e5509-185">bit</span><span class="sxs-lookup"><span data-stu-id="e5509-185">bit</span></span></p></td>
<td><p><span data-ttu-id="e5509-186">登録時に UserService が利用可能であったかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="e5509-186">Indicates whether the UserService was available at registration time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5509-187"><strong>IsPrimaryRegistrar</strong></span><span class="sxs-lookup"><span data-stu-id="e5509-187"><strong>IsPrimaryRegistrar</strong></span></span></p></td>
<td><p><span data-ttu-id="e5509-188">bit</span><span class="sxs-lookup"><span data-stu-id="e5509-188">bit</span></span></p></td>
<td><p><span data-ttu-id="e5509-189">登録がプライマリレジストラーであったかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="e5509-189">Indicates whether registration was with the primary Registrar.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5509-190"><strong>DeviceMacAddress</strong></span><span class="sxs-lookup"><span data-stu-id="e5509-190"><strong>DeviceMacAddress</strong></span></span></p></td>
<td><p><span data-ttu-id="e5509-191">bigint</span><span class="sxs-lookup"><span data-stu-id="e5509-191">bigint</span></span></p></td>
<td><p><span data-ttu-id="e5509-192">登録されているデバイスの MAC アドレス。</span><span class="sxs-lookup"><span data-stu-id="e5509-192">MAC Address of device registered.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5509-193"><strong>DeviceManufacturer</strong></span><span class="sxs-lookup"><span data-stu-id="e5509-193"><strong>DeviceManufacturer</strong></span></span></p></td>
<td><p><span data-ttu-id="e5509-194">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="e5509-194">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e5509-195">登録されているデバイスの製造元。</span><span class="sxs-lookup"><span data-stu-id="e5509-195">Manufacturer of the device registered.</span></span> <span data-ttu-id="e5509-196">詳細については、「 <a href="lync-server-2013-manufacturers-table.md">Lync Server 2013 の製造元の表</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e5509-196">See the <a href="lync-server-2013-manufacturers-table.md">Manufacturers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5509-197"><strong>DeviceHardwareVersion</strong></span><span class="sxs-lookup"><span data-stu-id="e5509-197"><strong>DeviceHardwareVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="e5509-198">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="e5509-198">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e5509-199">登録されているデバイスのハードウェアバージョン。</span><span class="sxs-lookup"><span data-stu-id="e5509-199">Hardware version of the device registered.</span></span> <span data-ttu-id="e5509-200">詳細については、「 <a href="lync-server-2013-hardwareversions-table.md">Lync Server 2013 のハードウェアバージョンの表</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e5509-200">See the <a href="lync-server-2013-hardwareversions-table.md">HardwareVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

