---
title: 'Lync Server 2013: 登録ビュー'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Registration view
ms:assetid: 8a42bc7d-3d4f-43c1-9e15-89b2ee419ade
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688120(v=OCS.15)
ms:contentKeyID: 49733718
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fe1b01b748204d3d4365b6f28ae4480d3632b35a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823827"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="registration-view-in-lync-server-2013"></a><span data-ttu-id="2ed82-102">Lync Server 2013 に表示される登録情報</span><span class="sxs-lookup"><span data-stu-id="2ed82-102">Registration view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2ed82-103">_**最終更新日:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="2ed82-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="2ed82-104">登録ビューには、ユーザー登録に関する情報が格納されます。</span><span class="sxs-lookup"><span data-stu-id="2ed82-104">The Registration view stores information about user registration.</span></span> <span data-ttu-id="2ed82-105">このビューは、Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="2ed82-105">This view was introduced in Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2ed82-106">列</span><span class="sxs-lookup"><span data-stu-id="2ed82-106">Column</span></span></th>
<th><span data-ttu-id="2ed82-107">データ型</span><span class="sxs-lookup"><span data-stu-id="2ed82-107">Data Type</span></span></th>
<th><span data-ttu-id="2ed82-108">詳細</span><span class="sxs-lookup"><span data-stu-id="2ed82-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2ed82-109"><strong>セッション Id</strong></span><span class="sxs-lookup"><span data-stu-id="2ed82-109"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="2ed82-110">datetime</span><span class="sxs-lookup"><span data-stu-id="2ed82-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="2ed82-111">セッション要求の時刻。</span><span class="sxs-lookup"><span data-stu-id="2ed82-111">Time of session request.</span></span> <span data-ttu-id="2ed82-112">セッションを一意に識別するために SessionIdSeq と組み合わせて使用されます。</span><span class="sxs-lookup"><span data-stu-id="2ed82-112">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="2ed82-113">詳細については、「 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 のダイアログテーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2ed82-113">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2ed82-114"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="2ed82-114"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="2ed82-115">int</span><span class="sxs-lookup"><span data-stu-id="2ed82-115">int</span></span></p></td>
<td><p><span data-ttu-id="2ed82-116">セッションを識別する ID 番号。</span><span class="sxs-lookup"><span data-stu-id="2ed82-116">ID number to identify the session.</span></span> <span data-ttu-id="2ed82-117">セッションを一意に識別するために SessionIdTime と組み合わせて使用されます。</span><span class="sxs-lookup"><span data-stu-id="2ed82-117">Used in conjunction with SessionIdTime to uniquely identify a session.</span></span> <span data-ttu-id="2ed82-118">詳細については、「 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 のダイアログテーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2ed82-118">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2ed82-119"><strong>RegisterTime</strong></span><span class="sxs-lookup"><span data-stu-id="2ed82-119"><strong>RegisterTime</strong></span></span></p></td>
<td><p><span data-ttu-id="2ed82-120">datetime</span><span class="sxs-lookup"><span data-stu-id="2ed82-120">datetime</span></span></p></td>
<td><p><span data-ttu-id="2ed82-121">登録が発生した時刻。</span><span class="sxs-lookup"><span data-stu-id="2ed82-121">Time at which registration occurred.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2ed82-122"><strong>UserUri</strong></span><span class="sxs-lookup"><span data-stu-id="2ed82-122"><strong>UserUri</strong></span></span></p></td>
<td><p><span data-ttu-id="2ed82-123">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="2ed82-123">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="2ed82-124">登録されたユーザーの URI。</span><span class="sxs-lookup"><span data-stu-id="2ed82-124">URI of the user who registered.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2ed82-125"><strong>UserUriType</strong></span><span class="sxs-lookup"><span data-stu-id="2ed82-125"><strong>UserUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="2ed82-126">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="2ed82-126">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="2ed82-127">登録したユーザーの URI の種類。</span><span class="sxs-lookup"><span data-stu-id="2ed82-127">Type of URI of the user who registered.</span></span> <span data-ttu-id="2ed82-128">詳細については、「 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013 の UriTypes テーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2ed82-128">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2ed82-129"><strong>UserTenant</strong></span><span class="sxs-lookup"><span data-stu-id="2ed82-129"><strong>UserTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="2ed82-130">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="2ed82-130">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="2ed82-131">登録したユーザーのテナント。</span><span class="sxs-lookup"><span data-stu-id="2ed82-131">Tenant of the user who registered.</span></span> <span data-ttu-id="2ed82-132">詳細については、「 <a href="lync-server-2013-tenants-table.md">Lync Server 2013 のテナントの一覧</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2ed82-132">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2ed82-133"><strong>EndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="2ed82-133"><strong>EndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="2ed82-134">長さ</span><span class="sxs-lookup"><span data-stu-id="2ed82-134">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="2ed82-135">登録されているユーザーのエンドポイントの一意の識別子。</span><span class="sxs-lookup"><span data-stu-id="2ed82-135">Unique identifier of the endpoint of the user registered with.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2ed82-136"><strong>Endポインタ a</strong></span><span class="sxs-lookup"><span data-stu-id="2ed82-136"><strong>EndpointEra</strong></span></span></p></td>
<td><p><span data-ttu-id="2ed82-137">長さ</span><span class="sxs-lookup"><span data-stu-id="2ed82-137">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="2ed82-138">同じユーザーと同じエンドポイントを含む登録を区別するために使用される一意の識別子。</span><span class="sxs-lookup"><span data-stu-id="2ed82-138">Unique identifier used to differentiate registrations that involve the same user and the same endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2ed82-139"><strong>DeRegisterType</strong></span><span class="sxs-lookup"><span data-stu-id="2ed82-139"><strong>DeRegisterType</strong></span></span></p></td>
<td><p><span data-ttu-id="2ed82-140">datetime</span><span class="sxs-lookup"><span data-stu-id="2ed82-140">datetime</span></span></p></td>
<td><p><span data-ttu-id="2ed82-141">登録解除が行われた時刻。</span><span class="sxs-lookup"><span data-stu-id="2ed82-141">Time at which deregistration occurred.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2ed82-142"><strong>DeRegisterReason</strong></span><span class="sxs-lookup"><span data-stu-id="2ed82-142"><strong>DeRegisterReason</strong></span></span></p></td>
<td><p><span data-ttu-id="2ed82-143">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="2ed82-143">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="2ed82-144">登録解除の理由。</span><span class="sxs-lookup"><span data-stu-id="2ed82-144">Reason for deregistration.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2ed82-145"><strong>ClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="2ed82-145"><strong>ClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="2ed82-146">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="2ed82-146">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="2ed82-147">登録したユーザーによって使用されたクライアントのバージョン。</span><span class="sxs-lookup"><span data-stu-id="2ed82-147">Version of client used by the user who registered.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2ed82-148"><strong>ClientType</strong></span><span class="sxs-lookup"><span data-stu-id="2ed82-148"><strong>ClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="2ed82-149">int</span><span class="sxs-lookup"><span data-stu-id="2ed82-149">int</span></span></p></td>
<td><p><span data-ttu-id="2ed82-150">登録したユーザーによって使用されたクライアント。</span><span class="sxs-lookup"><span data-stu-id="2ed82-150">Client used by the user who registered.</span></span> <span data-ttu-id="2ed82-151">詳細については、「 <a href="lync-server-2013-useragentdef-table.md">Lync Server 2013 の Useragentdef テーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2ed82-151">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2ed82-152"><strong>ClientCategory</strong></span><span class="sxs-lookup"><span data-stu-id="2ed82-152"><strong>ClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="2ed82-153">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="2ed82-153">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="2ed82-154">登録されたユーザーによって使用されたクライアントのカテゴリです。</span><span class="sxs-lookup"><span data-stu-id="2ed82-154">Category of the client used by the user who registered.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2ed82-155"><strong>Ip</strong></span><span class="sxs-lookup"><span data-stu-id="2ed82-155"><strong>IpAddress</strong></span></span></p></td>
<td><p><span data-ttu-id="2ed82-156">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="2ed82-156">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="2ed82-157">ユーザーが登録した IP アドレス。</span><span class="sxs-lookup"><span data-stu-id="2ed82-157">IP Address the user registered with.</span></span> <span data-ttu-id="2ed82-158">これは IPv4 または IPv6 アドレスである可能性があります。</span><span class="sxs-lookup"><span data-stu-id="2ed82-158">This may be an IPv4 or IPv6 address.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2ed82-159"><strong>この Id</strong></span><span class="sxs-lookup"><span data-stu-id="2ed82-159"><strong>DialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="2ed82-160">varstring (775)</span><span class="sxs-lookup"><span data-stu-id="2ed82-160">varstring(775)</span></span></p></td>
<td><p><span data-ttu-id="2ed82-161">SIP ダイアログ ID。</span><span class="sxs-lookup"><span data-stu-id="2ed82-161">SIP dialog ID.</span></span> <span data-ttu-id="2ed82-162">の形式は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="2ed82-162">The format of the is:</span></span></p>
<p><span data-ttu-id="2ed82-163">ダイアログ; 開始タグからタグへ</span><span class="sxs-lookup"><span data-stu-id="2ed82-163">dialog;from-tag;to-tag</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2ed82-164"><strong>返信</strong></span><span class="sxs-lookup"><span data-stu-id="2ed82-164"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="2ed82-165">int</span><span class="sxs-lookup"><span data-stu-id="2ed82-165">int</span></span></p></td>
<td><p><span data-ttu-id="2ed82-166">セッション招待状への SIP 応答コード。</span><span class="sxs-lookup"><span data-stu-id="2ed82-166">SIP response code to the session invitation.</span></span> <span data-ttu-id="2ed82-167">通常、このフィールドは、セッションの最初の INVITE メッセージから生成されたデータによって設定されます。</span><span class="sxs-lookup"><span data-stu-id="2ed82-167">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="2ed82-168">招待メッセージがない場合は、最初に関連する SIP メッセージ (BYE、キャンセル、メッセージ、または情報) の日付と時刻がフィールドに設定されています。</span><span class="sxs-lookup"><span data-stu-id="2ed82-168">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2ed82-169"><strong>DiagnosticId</strong></span><span class="sxs-lookup"><span data-stu-id="2ed82-169"><strong>DiagnosticId</strong></span></span></p></td>
<td><p><span data-ttu-id="2ed82-170">int</span><span class="sxs-lookup"><span data-stu-id="2ed82-170">int</span></span></p></td>
<td><p><span data-ttu-id="2ed82-171">SIP ヘッダーからキャプチャされた診断 ID。</span><span class="sxs-lookup"><span data-stu-id="2ed82-171">Diagnostic ID captured from SIP header.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2ed82-172"><strong>レジストラー</strong></span><span class="sxs-lookup"><span data-stu-id="2ed82-172"><strong>Registrar</strong></span></span></p></td>
<td><p><span data-ttu-id="2ed82-173">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="2ed82-173">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="2ed82-174">レジストラーの FQDN。</span><span class="sxs-lookup"><span data-stu-id="2ed82-174">FQDN of the Registrar.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2ed82-175"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="2ed82-175"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="2ed82-176">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="2ed82-176">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="2ed82-177">セッションのデータをキャプチャしたプールの FQDN。</span><span class="sxs-lookup"><span data-stu-id="2ed82-177">FQDN of the pool that captured the data for the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2ed82-178"><strong>EdgeServer</strong></span><span class="sxs-lookup"><span data-stu-id="2ed82-178"><strong>EdgeServer</strong></span></span></p></td>
<td><p><span data-ttu-id="2ed82-179">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="2ed82-179">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="2ed82-180">登録されたユーザーによって使用されたエッジサーバーの FQDN。</span><span class="sxs-lookup"><span data-stu-id="2ed82-180">FQDN of the Edge Server used by the user who registered.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2ed82-181"><strong>IsInternal</strong></span><span class="sxs-lookup"><span data-stu-id="2ed82-181"><strong>IsInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="2ed82-182">bit</span><span class="sxs-lookup"><span data-stu-id="2ed82-182">bit</span></span></p></td>
<td><p><span data-ttu-id="2ed82-183">ユーザーが内部ネットワークからログオンしているかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="2ed82-183">Indicates whether the user logged on from the internal network.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2ed82-184"><strong>IsUserServiceAvailable</strong></span><span class="sxs-lookup"><span data-stu-id="2ed82-184"><strong>IsUserServiceAvailable</strong></span></span></p></td>
<td><p><span data-ttu-id="2ed82-185">bit</span><span class="sxs-lookup"><span data-stu-id="2ed82-185">bit</span></span></p></td>
<td><p><span data-ttu-id="2ed82-186">登録時に UserService が利用可能であったかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="2ed82-186">Indicates whether the UserService was available at registration time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2ed82-187"><strong>IsPrimaryRegistrar</strong></span><span class="sxs-lookup"><span data-stu-id="2ed82-187"><strong>IsPrimaryRegistrar</strong></span></span></p></td>
<td><p><span data-ttu-id="2ed82-188">bit</span><span class="sxs-lookup"><span data-stu-id="2ed82-188">bit</span></span></p></td>
<td><p><span data-ttu-id="2ed82-189">登録がプライマリレジストラーであったかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="2ed82-189">Indicates whether registration was with the primary Registrar.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2ed82-190"><strong>DeviceMacAddress</strong></span><span class="sxs-lookup"><span data-stu-id="2ed82-190"><strong>DeviceMacAddress</strong></span></span></p></td>
<td><p><span data-ttu-id="2ed82-191">bigint</span><span class="sxs-lookup"><span data-stu-id="2ed82-191">bigint</span></span></p></td>
<td><p><span data-ttu-id="2ed82-192">登録されているデバイスの MAC アドレス。</span><span class="sxs-lookup"><span data-stu-id="2ed82-192">MAC Address of device registered.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2ed82-193"><strong>DeviceManufacturer</strong></span><span class="sxs-lookup"><span data-stu-id="2ed82-193"><strong>DeviceManufacturer</strong></span></span></p></td>
<td><p><span data-ttu-id="2ed82-194">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="2ed82-194">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="2ed82-195">登録されているデバイスの製造元。</span><span class="sxs-lookup"><span data-stu-id="2ed82-195">Manufacturer of the device registered.</span></span> <span data-ttu-id="2ed82-196">詳細については、「 <a href="lync-server-2013-manufacturers-table.md">Lync Server 2013 の製造元の表</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2ed82-196">See the <a href="lync-server-2013-manufacturers-table.md">Manufacturers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2ed82-197"><strong>DeviceHardwareVersion</strong></span><span class="sxs-lookup"><span data-stu-id="2ed82-197"><strong>DeviceHardwareVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="2ed82-198">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="2ed82-198">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="2ed82-199">登録されているデバイスのハードウェアバージョン。</span><span class="sxs-lookup"><span data-stu-id="2ed82-199">Hardware version of the device registered.</span></span> <span data-ttu-id="2ed82-200">詳細については、「 <a href="lync-server-2013-hardwareversions-table.md">Lync Server 2013 のハードウェアバージョンの表</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2ed82-200">See the <a href="lync-server-2013-hardwareversions-table.md">HardwareVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

