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
ms.openlocfilehash: 1f6a48780535960a71a06f2edfcb6c2b8a95d999
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42138828"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="registration-view-in-lync-server-2013"></a><span data-ttu-id="e2bf2-102">Lync Server 2013 の登録ビュー</span><span class="sxs-lookup"><span data-stu-id="e2bf2-102">Registration view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e2bf2-103">_**トピックの最終更新日:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="e2bf2-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="e2bf2-104">登録ビューでは、ユーザー登録に関する情報を格納します。</span><span class="sxs-lookup"><span data-stu-id="e2bf2-104">The Registration view stores information about user registration.</span></span> <span data-ttu-id="e2bf2-105">このビューは、Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="e2bf2-105">This view was introduced in Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e2bf2-106">列</span><span class="sxs-lookup"><span data-stu-id="e2bf2-106">Column</span></span></th>
<th><span data-ttu-id="e2bf2-107">データ型</span><span class="sxs-lookup"><span data-stu-id="e2bf2-107">Data Type</span></span></th>
<th><span data-ttu-id="e2bf2-108">詳細</span><span class="sxs-lookup"><span data-stu-id="e2bf2-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e2bf2-109"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="e2bf2-109"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="e2bf2-110">日付型</span><span class="sxs-lookup"><span data-stu-id="e2bf2-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="e2bf2-111">セッション要求の時間。</span><span class="sxs-lookup"><span data-stu-id="e2bf2-111">Time of session request.</span></span> <span data-ttu-id="e2bf2-112">セッションを一意に識別するために SessionIdSeq と組み合わせて使用されます。</span><span class="sxs-lookup"><span data-stu-id="e2bf2-112">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="e2bf2-113">詳細については、「 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 のダイアログテーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e2bf2-113">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e2bf2-114"><strong>Sessionidseq と</strong></span><span class="sxs-lookup"><span data-stu-id="e2bf2-114"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="e2bf2-115">int</span><span class="sxs-lookup"><span data-stu-id="e2bf2-115">int</span></span></p></td>
<td><p><span data-ttu-id="e2bf2-116">セッションを識別するための ID 番号。</span><span class="sxs-lookup"><span data-stu-id="e2bf2-116">ID number to identify the session.</span></span> <span data-ttu-id="e2bf2-117">セッションを一意に識別するために SessionIdTime と組み合わせて使用されます。</span><span class="sxs-lookup"><span data-stu-id="e2bf2-117">Used in conjunction with SessionIdTime to uniquely identify a session.</span></span> <span data-ttu-id="e2bf2-118">詳細については、「 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 のダイアログテーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e2bf2-118">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e2bf2-119"><strong>RegisterTime</strong></span><span class="sxs-lookup"><span data-stu-id="e2bf2-119"><strong>RegisterTime</strong></span></span></p></td>
<td><p><span data-ttu-id="e2bf2-120">日付型</span><span class="sxs-lookup"><span data-stu-id="e2bf2-120">datetime</span></span></p></td>
<td><p><span data-ttu-id="e2bf2-121">登録が発生した時間。</span><span class="sxs-lookup"><span data-stu-id="e2bf2-121">Time at which registration occurred.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e2bf2-122"><strong>UserUri</strong></span><span class="sxs-lookup"><span data-stu-id="e2bf2-122"><strong>UserUri</strong></span></span></p></td>
<td><p><span data-ttu-id="e2bf2-123">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="e2bf2-123">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="e2bf2-124">登録したユーザーの URI</span><span class="sxs-lookup"><span data-stu-id="e2bf2-124">URI of the user who registered.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e2bf2-125"><strong>Useruritoff</strong></span><span class="sxs-lookup"><span data-stu-id="e2bf2-125"><strong>UserUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="e2bf2-126">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="e2bf2-126">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e2bf2-127">登録したユーザーの URI の種類。</span><span class="sxs-lookup"><span data-stu-id="e2bf2-127">Type of URI of the user who registered.</span></span> <span data-ttu-id="e2bf2-128">詳細については、「 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013 の UriTypes テーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e2bf2-128">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e2bf2-129"><strong>UserTenant</strong></span><span class="sxs-lookup"><span data-stu-id="e2bf2-129"><strong>UserTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="e2bf2-130">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="e2bf2-130">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e2bf2-131">登録したユーザーのテナント ID。</span><span class="sxs-lookup"><span data-stu-id="e2bf2-131">Tenant of the user who registered.</span></span> <span data-ttu-id="e2bf2-132">詳細については、「 <a href="lync-server-2013-tenants-table.md">Lync Server 2013 のテナントの表</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e2bf2-132">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e2bf2-133"><strong>EndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="e2bf2-133"><strong>EndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="e2bf2-134">識別子</span><span class="sxs-lookup"><span data-stu-id="e2bf2-134">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="e2bf2-135">ユーザーの登録に使用するエンドポイントの一意の識別子。</span><span class="sxs-lookup"><span data-stu-id="e2bf2-135">Unique identifier of the endpoint of the user registered with.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e2bf2-136"><strong>Endポインター a</strong></span><span class="sxs-lookup"><span data-stu-id="e2bf2-136"><strong>EndpointEra</strong></span></span></p></td>
<td><p><span data-ttu-id="e2bf2-137">識別子</span><span class="sxs-lookup"><span data-stu-id="e2bf2-137">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="e2bf2-138">同じユーザーおよび同じエンドポイントが含まれる登録を区別するための一意の識別子。</span><span class="sxs-lookup"><span data-stu-id="e2bf2-138">Unique identifier used to differentiate registrations that involve the same user and the same endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e2bf2-139"><strong>DeRegisterType</strong></span><span class="sxs-lookup"><span data-stu-id="e2bf2-139"><strong>DeRegisterType</strong></span></span></p></td>
<td><p><span data-ttu-id="e2bf2-140">日付型</span><span class="sxs-lookup"><span data-stu-id="e2bf2-140">datetime</span></span></p></td>
<td><p><span data-ttu-id="e2bf2-141">登録解除が発生した時間。</span><span class="sxs-lookup"><span data-stu-id="e2bf2-141">Time at which deregistration occurred.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e2bf2-142"><strong>DeRegisterReason</strong></span><span class="sxs-lookup"><span data-stu-id="e2bf2-142"><strong>DeRegisterReason</strong></span></span></p></td>
<td><p><span data-ttu-id="e2bf2-143">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="e2bf2-143">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e2bf2-144">登録解除の理由。</span><span class="sxs-lookup"><span data-stu-id="e2bf2-144">Reason for deregistration.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e2bf2-145"><strong>ClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="e2bf2-145"><strong>ClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="e2bf2-146">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="e2bf2-146">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e2bf2-147">登録したユーザーが使用しているクライアントのバージョン。</span><span class="sxs-lookup"><span data-stu-id="e2bf2-147">Version of client used by the user who registered.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e2bf2-148"><strong>ClientType</strong></span><span class="sxs-lookup"><span data-stu-id="e2bf2-148"><strong>ClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="e2bf2-149">int</span><span class="sxs-lookup"><span data-stu-id="e2bf2-149">int</span></span></p></td>
<td><p><span data-ttu-id="e2bf2-150">登録したユーザーが使用しているクライアント。</span><span class="sxs-lookup"><span data-stu-id="e2bf2-150">Client used by the user who registered.</span></span> <span data-ttu-id="e2bf2-151">詳細については、「 <a href="lync-server-2013-useragentdef-table.md">Lync Server 2013 の Useragentdef テーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e2bf2-151">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e2bf2-152"><strong>ClientCategory</strong></span><span class="sxs-lookup"><span data-stu-id="e2bf2-152"><strong>ClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="e2bf2-153">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="e2bf2-153">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="e2bf2-154">登録したユーザーが使用しているクライアントのカテゴリ。</span><span class="sxs-lookup"><span data-stu-id="e2bf2-154">Category of the client used by the user who registered.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e2bf2-155"><strong>IpAddress</strong></span><span class="sxs-lookup"><span data-stu-id="e2bf2-155"><strong>IpAddress</strong></span></span></p></td>
<td><p><span data-ttu-id="e2bf2-156">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="e2bf2-156">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e2bf2-157">ユーザーが登録した IP アドレス。</span><span class="sxs-lookup"><span data-stu-id="e2bf2-157">IP Address the user registered with.</span></span> <span data-ttu-id="e2bf2-158">これは、IPv4 または IPv6 のアドレスである場合があります。</span><span class="sxs-lookup"><span data-stu-id="e2bf2-158">This may be an IPv4 or IPv6 address.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e2bf2-159"><strong>DialogId</strong></span><span class="sxs-lookup"><span data-stu-id="e2bf2-159"><strong>DialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="e2bf2-160">varstring (775)</span><span class="sxs-lookup"><span data-stu-id="e2bf2-160">varstring(775)</span></span></p></td>
<td><p><span data-ttu-id="e2bf2-p108">SIP ダイアログ ID。形式は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="e2bf2-p108">SIP dialog ID. The format of the is:</span></span></p>
<p><span data-ttu-id="e2bf2-163">dialog、from タグ、およびタグ</span><span class="sxs-lookup"><span data-stu-id="e2bf2-163">dialog;from-tag;to-tag</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e2bf2-164"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="e2bf2-164"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="e2bf2-165">int</span><span class="sxs-lookup"><span data-stu-id="e2bf2-165">int</span></span></p></td>
<td><p><span data-ttu-id="e2bf2-p109">セッションへの招待に対する SIP 応答コード。このフィールドには通常、セッションの最初の INVITE メッセージから生成されるデータが設定されます。INVITE メッセージがない場合は、フィールドには、最初の関連する SIP メッセージ (BYE、CANCEL、MESSAGE、または INFO) の日時が設定されます。</span><span class="sxs-lookup"><span data-stu-id="e2bf2-p109">SIP response code to the session invitation. This field is typically populated by data generated from the initial INVITE message in the session. If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e2bf2-169"><strong>DiagnosticId</strong></span><span class="sxs-lookup"><span data-stu-id="e2bf2-169"><strong>DiagnosticId</strong></span></span></p></td>
<td><p><span data-ttu-id="e2bf2-170">int</span><span class="sxs-lookup"><span data-stu-id="e2bf2-170">int</span></span></p></td>
<td><p><span data-ttu-id="e2bf2-171">SIP ヘッダーから取得された診断 ID。</span><span class="sxs-lookup"><span data-stu-id="e2bf2-171">Diagnostic ID captured from SIP header.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e2bf2-172"><strong>レジストラー</strong></span><span class="sxs-lookup"><span data-stu-id="e2bf2-172"><strong>Registrar</strong></span></span></p></td>
<td><p><span data-ttu-id="e2bf2-173">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="e2bf2-173">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e2bf2-174">レジストラーの FQDN。</span><span class="sxs-lookup"><span data-stu-id="e2bf2-174">FQDN of the Registrar.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e2bf2-175"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="e2bf2-175"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="e2bf2-176">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="e2bf2-176">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e2bf2-177">セッションのデータをキャプチャしたプールの FQDN。</span><span class="sxs-lookup"><span data-stu-id="e2bf2-177">FQDN of the pool that captured the data for the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e2bf2-178"><strong>EdgeServer</strong></span><span class="sxs-lookup"><span data-stu-id="e2bf2-178"><strong>EdgeServer</strong></span></span></p></td>
<td><p><span data-ttu-id="e2bf2-179">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="e2bf2-179">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e2bf2-180">登録したユーザーが使用しているエッジ サーバーの FQDN。</span><span class="sxs-lookup"><span data-stu-id="e2bf2-180">FQDN of the Edge Server used by the user who registered.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e2bf2-181"><strong>IsInternal</strong></span><span class="sxs-lookup"><span data-stu-id="e2bf2-181"><strong>IsInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="e2bf2-182">若干</span><span class="sxs-lookup"><span data-stu-id="e2bf2-182">bit</span></span></p></td>
<td><p><span data-ttu-id="e2bf2-183">ユーザーが内部ネットワークからログオンしているかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="e2bf2-183">Indicates whether the user logged on from the internal network.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e2bf2-184"><strong>IsUserServiceAvailable</strong></span><span class="sxs-lookup"><span data-stu-id="e2bf2-184"><strong>IsUserServiceAvailable</strong></span></span></p></td>
<td><p><span data-ttu-id="e2bf2-185">若干</span><span class="sxs-lookup"><span data-stu-id="e2bf2-185">bit</span></span></p></td>
<td><p><span data-ttu-id="e2bf2-186">登録時に UserService が使用可能であったかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="e2bf2-186">Indicates whether the UserService was available at registration time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e2bf2-187"><strong>IsPrimaryRegistrar</strong></span><span class="sxs-lookup"><span data-stu-id="e2bf2-187"><strong>IsPrimaryRegistrar</strong></span></span></p></td>
<td><p><span data-ttu-id="e2bf2-188">若干</span><span class="sxs-lookup"><span data-stu-id="e2bf2-188">bit</span></span></p></td>
<td><p><span data-ttu-id="e2bf2-189">登録がプライマリ レジストラーを使用して行われたかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="e2bf2-189">Indicates whether registration was with the primary Registrar.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e2bf2-190"><strong>DeviceMacAddress</strong></span><span class="sxs-lookup"><span data-stu-id="e2bf2-190"><strong>DeviceMacAddress</strong></span></span></p></td>
<td><p><span data-ttu-id="e2bf2-191">bigint</span><span class="sxs-lookup"><span data-stu-id="e2bf2-191">bigint</span></span></p></td>
<td><p><span data-ttu-id="e2bf2-192">登録されたデバイスの MAC アドレス。</span><span class="sxs-lookup"><span data-stu-id="e2bf2-192">MAC Address of device registered.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e2bf2-193"><strong>DeviceManufacturer</strong></span><span class="sxs-lookup"><span data-stu-id="e2bf2-193"><strong>DeviceManufacturer</strong></span></span></p></td>
<td><p><span data-ttu-id="e2bf2-194">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="e2bf2-194">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e2bf2-195">登録されたデバイスの製造元。</span><span class="sxs-lookup"><span data-stu-id="e2bf2-195">Manufacturer of the device registered.</span></span> <span data-ttu-id="e2bf2-196">詳細については、「 <a href="lync-server-2013-manufacturers-table.md">Lync Server 2013 の製造元</a>」の表を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e2bf2-196">See the <a href="lync-server-2013-manufacturers-table.md">Manufacturers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e2bf2-197"><strong>Deviceハードウェアバージョン</strong></span><span class="sxs-lookup"><span data-stu-id="e2bf2-197"><strong>DeviceHardwareVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="e2bf2-198">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="e2bf2-198">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e2bf2-199">登録されたデバイスのハードウェア バージョン。</span><span class="sxs-lookup"><span data-stu-id="e2bf2-199">Hardware version of the device registered.</span></span> <span data-ttu-id="e2bf2-200">詳細については、「 <a href="lync-server-2013-hardwareversions-table.md">Lync Server 2013 のハードウェアバージョン表</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e2bf2-200">See the <a href="lync-server-2013-hardwareversions-table.md">HardwareVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

