---
title: 'Lync Server 2013: スキーマの属性と説明'
description: 'Lync Server 2013: スキーマの属性と説明。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Schema attributes and descriptions
ms:assetid: b009df76-9c22-471d-b57a-bda009a98261
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412841(v=OCS.15)
ms:contentKeyID: 48185083
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 18888d20a772b3e84970e7d874bd6b6964affc75
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48557193"
---
# <a name="schema-attributes-and-descriptions-in-lync-server-2013"></a><span data-ttu-id="1b507-103">Lync Server 2013 のスキーマの属性と説明</span><span class="sxs-lookup"><span data-stu-id="1b507-103">Schema attributes and descriptions in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1b507-104">_**トピックの最終更新日:** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="1b507-104">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="1b507-105">このセクションでは、Lync Server 2013 で使用されるすべてのスキーマ属性について説明します。</span><span class="sxs-lookup"><span data-stu-id="1b507-105">This section describes all the schema attributes used by Lync Server 2013.</span></span> <span data-ttu-id="1b507-106">属性に関連付けられたクラスについては、「 [Lync Server 2013 のクラス別のスキーマ属性](lync-server-2013-schema-attributes-by-class.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1b507-106">For the classes associated with attributes, see [Schema attributes by class in Lync Server 2013](lync-server-2013-schema-attributes-by-class.md).</span></span> <span data-ttu-id="1b507-107">Lync Server 2013 で新しく追加されたクラスと属性の一覧については、「 [Lync server 2013 のスキーマの変更点](lync-server-2013-schema-changes-in-lync-server-2013.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1b507-107">For a list of classes and attributes that are new in Lync Server 2013, see [Schema changes in Lync Server 2013](lync-server-2013-schema-changes-in-lync-server-2013.md).</span></span>

<span data-ttu-id="1b507-108">リンクされたペアの属性は、前方リンクまたは後方リンクとして指定されます。</span><span class="sxs-lookup"><span data-stu-id="1b507-108">Attributes that are linked pairs are specified as forward links or back links.</span></span> <span data-ttu-id="1b507-109">別のオブジェクトを参照する属性は、前方リンクです。最初のオブジェクトを参照する other オブジェクトの属性は、後方リンクです。</span><span class="sxs-lookup"><span data-stu-id="1b507-109">An attribute that refers to another object is a forward link; the attribute of the other object that refers back to the first object is a back link.</span></span> <span data-ttu-id="1b507-110">前方リンクは更新可能で、後方リンクは読み取り専用です。</span><span class="sxs-lookup"><span data-stu-id="1b507-110">Forward links are updatable, while back links are read-only.</span></span>

<span data-ttu-id="1b507-111">一部の属性にはビットマスク値があります。</span><span class="sxs-lookup"><span data-stu-id="1b507-111">Some attributes have a bit-mask value.</span></span> <span data-ttu-id="1b507-112">これらの属性の場合、各設定はビットで表され、表示される10進値はビット位置を表します。</span><span class="sxs-lookup"><span data-stu-id="1b507-112">For these attributes, each setting is represented by a bit, and the displayed decimal value represents the bit position.</span></span> <span data-ttu-id="1b507-113">ビット位置はビット0で始まります。</span><span class="sxs-lookup"><span data-stu-id="1b507-113">Bit positions start with bit 0.</span></span> <span data-ttu-id="1b507-114">たとえば、1 (バイナリ) はビット0セットで、1万 (バイナリ) はビット4セットです。</span><span class="sxs-lookup"><span data-stu-id="1b507-114">For example, 1 (binary) is bit 0 set and 10000 (binary) is bit 4 set.</span></span> <span data-ttu-id="1b507-115">各ビットはプロパティを表します。</span><span class="sxs-lookup"><span data-stu-id="1b507-115">Each bit represents a property.</span></span> <span data-ttu-id="1b507-116">以下はその例です。</span><span class="sxs-lookup"><span data-stu-id="1b507-116">The following are some examples:</span></span>

  - <span data-ttu-id="1b507-117">1万 (バイナリ) の10進値は16です (つまり、ビット4が設定されます)。</span><span class="sxs-lookup"><span data-stu-id="1b507-117">10000 (binary) has a decimal value of 16 (that is, bit 4 is set).</span></span>

  - <span data-ttu-id="1b507-118">1億 (バイナリ) の10進値は256です (つまり、ビット8が設定されます)。</span><span class="sxs-lookup"><span data-stu-id="1b507-118">100000000 (binary) has a decimal value of 256 (that is, bit 8 is set).</span></span>

  - <span data-ttu-id="1b507-119">1100 (バイナリ) の10進値は12です (つまり、ビット2と3が設定され、両方のビットで表されるプロパティが有効になります)。</span><span class="sxs-lookup"><span data-stu-id="1b507-119">1100 (binary) has a decimal value of 12 (that is, bits 2 and 3 are set; properties represented by both bits are enabled).</span></span>

  - <span data-ttu-id="1b507-120">1111000001 (バイナリ) の10進値は961です (つまり、ビット0、6、7、8、9が設定され、これらの各ビットのプロパティが有効になります)。</span><span class="sxs-lookup"><span data-stu-id="1b507-120">1111000001 (binary) has a decimal value of 961 (that is, bits 0, 6, 7, 8, and 9 are set; properties for each of these bits are enabled).</span></span>

<div id="sectionSection0" class="section">

### <a name="schema-attributes-for-lync-server-2013"></a><span data-ttu-id="1b507-121">Lync Server 2013 のスキーマの属性</span><span class="sxs-lookup"><span data-stu-id="1b507-121">Schema Attributes for Lync Server 2013</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1b507-122">属性</span><span class="sxs-lookup"><span data-stu-id="1b507-122">Attribute</span></span></th>
<th><span data-ttu-id="1b507-123">説明</span><span class="sxs-lookup"><span data-stu-id="1b507-123">Description</span></span></th>
<th><span data-ttu-id="1b507-124">Comments</span><span class="sxs-lookup"><span data-stu-id="1b507-124">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1b507-125">dnsHostName</span><span class="sxs-lookup"><span data-stu-id="1b507-125">dnsHostName</span></span></p></td>
<td><p><span data-ttu-id="1b507-126"><strong>MsRTCSIP</strong>と msRTCSIP の両方の<strong>サーバー</strong>クラスに関連付けられた、Active Directory ドメインサービスの既存の属性。</span><span class="sxs-lookup"><span data-stu-id="1b507-126">An existing attribute in Active Directory Domain Services that is now associated with the <strong>msRTCSIP-Pool</strong> and <strong>msRTCSIP-MonitoringServer</strong> classes.</span></span> <span data-ttu-id="1b507-127">この属性は、プールまたは監視サーバーの完全修飾ドメイン名 (FQDN) を指定します。</span><span class="sxs-lookup"><span data-stu-id="1b507-127">This attribute specifies the fully qualified domain name (FQDN) of a pool or Monitoring Server.</span></span></p>
<p><span data-ttu-id="1b507-128">各セグメントの有効な値は、63文字です。FQDN 全体の有効な値は、255文字です。</span><span class="sxs-lookup"><span data-stu-id="1b507-128">A valid value for each segment is 63 characters; a valid value for the entire FQDN is 255 characters.</span></span></p></td>
<td><p><span data-ttu-id="1b507-129">Microsoft Office Live Communications Server 2005 の新製品。</span><span class="sxs-lookup"><span data-stu-id="1b507-129">New in Microsoft Office Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b507-130">Msds-sourceobjectdn</span><span class="sxs-lookup"><span data-stu-id="1b507-130">msDS-SourceObjectDN</span></span></p></td>
<td><p><span data-ttu-id="1b507-131">この属性には、このオブジェクトに対応する別のフォレスト内のオブジェクトの識別名 (DN) の文字列表現が含まれています。</span><span class="sxs-lookup"><span data-stu-id="1b507-131">This attribute contains the string representation of the distinguished name (DN) of the object in another forest that corresponds to this object.</span></span> <span data-ttu-id="1b507-132">この属性は、配布グループの展開および自動出席に使用されます。</span><span class="sxs-lookup"><span data-stu-id="1b507-132">This attribute is used for distribution group expansion and auto attendance.</span></span> <span data-ttu-id="1b507-133">この属性は、Windows Server 2003 R2 用の既定の Active Directory スキーマで定義されています。</span><span class="sxs-lookup"><span data-stu-id="1b507-133">This attribute is defined in the default Active Directory schema for Windows Server 2003 R2.</span></span></p>
<p><span data-ttu-id="1b507-134">AD DS を Windows Server 2003 R2 にアップグレードしなくて済むように、Active Directory スキーマの準備により、Windows Server 2003 スキーマがこの属性定義で拡張されます。</span><span class="sxs-lookup"><span data-stu-id="1b507-134">To avoid requiring an upgrade of AD DS to Windows Server 2003 R2, Active Directory schema preparation extends the Windows Server 2003 schema with this attribute definition.</span></span></p></td>
<td><p><span data-ttu-id="1b507-135">Microsoft Office Communications Server 2007 の新製品。</span><span class="sxs-lookup"><span data-stu-id="1b507-135">New in Microsoft Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b507-136">msExchUCVoiceMailSettings</span><span class="sxs-lookup"><span data-stu-id="1b507-136">msExchUCVoiceMailSettings</span></span></p></td>
<td><p><span data-ttu-id="1b507-137">この複数値属性は、ボイスメール設定を保持します。</span><span class="sxs-lookup"><span data-stu-id="1b507-137">This multi-valued attribute holds voice mail settings.</span></span> <span data-ttu-id="1b507-138">この属性は、Exchange ユニファイドメッセージング (UM) と共有されます。</span><span class="sxs-lookup"><span data-stu-id="1b507-138">This attribute is shared with Exchange Unified Messaging (UM).</span></span></p></td>
<td><p><span data-ttu-id="1b507-139">Microsoft Lync Server 2010 の新製品。</span><span class="sxs-lookup"><span data-stu-id="1b507-139">New in Microsoft Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b507-140">msExchUserHoldPolicies</span><span class="sxs-lookup"><span data-stu-id="1b507-140">msExchUserHoldPolicies</span></span></p></td>
<td><p><span data-ttu-id="1b507-141">この複数値の属性には、ユーザーに適用される保持ポリシーの識別子が保持されます。</span><span class="sxs-lookup"><span data-stu-id="1b507-141">This multi-value attribute holds identifiers for hold policies that apply to the user.</span></span> <span data-ttu-id="1b507-142">この保持の間は、ユーザーのメールボックス アイテムが保持ポリシーに保存されます。</span><span class="sxs-lookup"><span data-stu-id="1b507-142">Hold policies preserve mailbox items for the user for the duration of the hold.</span></span> <span data-ttu-id="1b507-143">この属性は、Exchange 2013 と共有されます。</span><span class="sxs-lookup"><span data-stu-id="1b507-143">This attribute is shared with Exchange 2013.</span></span></p></td>
<td><p><span data-ttu-id="1b507-144">Lync Server 2013 の新。</span><span class="sxs-lookup"><span data-stu-id="1b507-144">New in Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b507-145">msRTCSIP-AcpInfo</span><span class="sxs-lookup"><span data-stu-id="1b507-145">msRTCSIP-AcpInfo</span></span></p></td>
<td><p><span data-ttu-id="1b507-146">この属性は、ユーザーの電話会議プロバイダーの情報を格納します。</span><span class="sxs-lookup"><span data-stu-id="1b507-146">This attribute stores audio conferencing provider information for a user.</span></span></p></td>
<td><p><span data-ttu-id="1b507-147">Lync Server 2010 の新。</span><span class="sxs-lookup"><span data-stu-id="1b507-147">New in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b507-148">msRTCSIP-ApplicationDestination</span><span class="sxs-lookup"><span data-stu-id="1b507-148">msRTCSIP-ApplicationDestination</span></span></p></td>
<td><p><span data-ttu-id="1b507-149">この属性は、アプリケーションの連絡先の信頼済みサービスエントリを指します。</span><span class="sxs-lookup"><span data-stu-id="1b507-149">This attribute points to the trusted service entry for the application contact.</span></span></p></td>
<td><p><span data-ttu-id="1b507-150">Microsoft Office Communications Server 2007 R2 の新製品。</span><span class="sxs-lookup"><span data-stu-id="1b507-150">New in Microsoft Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b507-151">msRTCSIP-ApplicationList</span><span class="sxs-lookup"><span data-stu-id="1b507-151">msRTCSIP-ApplicationList</span></span></p></td>
<td><p><span data-ttu-id="1b507-152">この属性には、アプリケーションサーバー上のホストされているアプリケーションの一覧が含まれています。</span><span class="sxs-lookup"><span data-stu-id="1b507-152">This attribute contains a list of hosted applications on the application server.</span></span></p></td>
<td><p><span data-ttu-id="1b507-153">Office Communications Server 2007 R2 の新製品。</span><span class="sxs-lookup"><span data-stu-id="1b507-153">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b507-154">msRTCSIP-ApplicationOptions</span><span class="sxs-lookup"><span data-stu-id="1b507-154">msRTCSIP-ApplicationOptions</span></span></p></td>
<td><p><span data-ttu-id="1b507-155">この属性は、アプリケーションの連絡先のオプションを指定します。</span><span class="sxs-lookup"><span data-stu-id="1b507-155">This attribute specifies the options for the application contact.</span></span></p></td>
<td><p><span data-ttu-id="1b507-156">Office Communications Server 2007 R2 の新製品。</span><span class="sxs-lookup"><span data-stu-id="1b507-156">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b507-157">msRTCSIP-ApplicationPrimaryLanguage</span><span class="sxs-lookup"><span data-stu-id="1b507-157">msRTCSIP-ApplicationPrimaryLanguage</span></span></p></td>
<td><p><span data-ttu-id="1b507-158">この属性には、アプリケーションの連絡先の第1言語が含まれています。</span><span class="sxs-lookup"><span data-stu-id="1b507-158">This attribute contains the primary language for the application contact.</span></span></p></td>
<td><p><span data-ttu-id="1b507-159">Office Communications Server 2007 R2 の新製品。</span><span class="sxs-lookup"><span data-stu-id="1b507-159">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b507-160">msRTCSIP-ApplicationSecondaryLanguages</span><span class="sxs-lookup"><span data-stu-id="1b507-160">msRTCSIP-ApplicationSecondaryLanguages</span></span></p></td>
<td><p><span data-ttu-id="1b507-161">この複数値の属性には、アプリケーションの連絡先の第2言語が含まれています。</span><span class="sxs-lookup"><span data-stu-id="1b507-161">This multiple value attribute contains the secondary languages for the application contact.</span></span></p></td>
<td><p><span data-ttu-id="1b507-162">Office Communications Server 2007 R2 の新製品。</span><span class="sxs-lookup"><span data-stu-id="1b507-162">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b507-163">msRTCSIP-ApplicationServerBL</span><span class="sxs-lookup"><span data-stu-id="1b507-163">msRTCSIP-ApplicationServerBL</span></span></p></td>
<td><p><span data-ttu-id="1b507-164">この属性には、このプールに属するアプリケーションサーバーの一覧が含まれています。</span><span class="sxs-lookup"><span data-stu-id="1b507-164">This attribute contains a list of application servers that belong to this pool.</span></span> <span data-ttu-id="1b507-165">この後方リンク属性への対応する転送リンクは、 <strong>MsRTCSIP Serverpoollink</strong>です。</span><span class="sxs-lookup"><span data-stu-id="1b507-165">The corresponding forward link to this back link attribute is <strong>msRTCSIP-ApplicationServerPoolLink</strong>.</span></span></p></td>
<td><p><span data-ttu-id="1b507-166">Office Communications Server 2007 R2 の新製品。</span><span class="sxs-lookup"><span data-stu-id="1b507-166">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b507-167">msRTCSIP-ApplicationServerPoolLink</span><span class="sxs-lookup"><span data-stu-id="1b507-167">msRTCSIP-ApplicationServerPoolLink</span></span></p></td>
<td><p><span data-ttu-id="1b507-168">この属性は、このアプリケーションサーバーが属するプールを指します。</span><span class="sxs-lookup"><span data-stu-id="1b507-168">This attribute points to the pool to which this application server belongs.</span></span> <span data-ttu-id="1b507-169">これは、前方リンクです。</span><span class="sxs-lookup"><span data-stu-id="1b507-169">This is the forward link.</span></span> <span data-ttu-id="1b507-170">対応する後方リンクは、 <strong>MsRTCSIP Serverbl</strong>です。</span><span class="sxs-lookup"><span data-stu-id="1b507-170">The corresponding backward link is <strong>msRTCSIP-ApplicationServerBL</strong>.</span></span></p></td>
<td><p><span data-ttu-id="1b507-171">Office Communications Server 2007 R2 の新製品。</span><span class="sxs-lookup"><span data-stu-id="1b507-171">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b507-172">msRTCSIP-アーカイブ既定 (現在不使用)</span><span class="sxs-lookup"><span data-stu-id="1b507-172">msRTCSIP-ArchiveDefault (obsolete)</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="1b507-173">Live Communications Server 2005 の新しいもの。</span><span class="sxs-lookup"><span data-stu-id="1b507-173">New in Live Communications Server 2005.</span></span></p>
<p><span data-ttu-id="1b507-174">Office Communications Server 2007 では廃止されました。</span><span class="sxs-lookup"><span data-stu-id="1b507-174">Obsolete in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b507-175">msRTCSIP-アーカイブ Defaultflags (現在不使用)</span><span class="sxs-lookup"><span data-stu-id="1b507-175">msRTCSIP-ArchiveDefaultFlags (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="1b507-176">この属性は、すべてのユーザー通信をアーカイブするためのフォレスト境界内でのグローバルな既定値を指定します。</span><span class="sxs-lookup"><span data-stu-id="1b507-176">This attribute specifies the global default within the forest boundary for archiving all user communications.</span></span> <span data-ttu-id="1b507-177">これは、アーカイブエージェントレイヤーによって適用されます。</span><span class="sxs-lookup"><span data-stu-id="1b507-177">This is enforced by the archiving agent layer.</span></span> <span data-ttu-id="1b507-178">この属性の値の範囲は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="1b507-178">The range of values for this attribute is as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="1b507-179"><strong>TRUE</strong>: すべてのユーザーをアーカイブする</span><span class="sxs-lookup"><span data-stu-id="1b507-179"><strong>TRUE</strong>: Archive all users</span></span></p></li>
<li><p><span data-ttu-id="1b507-180"><strong>FALSE</strong>: すべてのユーザーをアーカイブしない</span><span class="sxs-lookup"><span data-stu-id="1b507-180"><strong>FALSE</strong>: Do not archive all users</span></span></p></li>
</ul>
<p><span data-ttu-id="1b507-181">この属性は、内部ネットワーク内でのユーザー通信のアーカイブ方法をフォレスト境界内でグローバルに制御します。</span><span class="sxs-lookup"><span data-stu-id="1b507-181">This attribute globally controls, within the forest boundary, how user communications within an internal network are archived.</span></span></p>
<p><span data-ttu-id="1b507-182"><strong>Live Communications Server 2005 の動作 (現在は廃止)</strong></span><span class="sxs-lookup"><span data-stu-id="1b507-182"><strong>Live Communications Server 2005 behavior (now retired)</strong></span></span></p>
<p><span data-ttu-id="1b507-183">この属性の値の範囲は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="1b507-183">The range of values for this attribute is as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="1b507-184">0: メッセージ本文をアーカイブする [ビット 0]</span><span class="sxs-lookup"><span data-stu-id="1b507-184">0: Archive the message body [bit 0]</span></span></p></li>
<li><p><span data-ttu-id="1b507-185">1: メッセージ本文をアーカイブしない [ビット 0]</span><span class="sxs-lookup"><span data-stu-id="1b507-185">1: Do not archive the message body [bit 0]</span></span></p></li>
</ul>
<p><span data-ttu-id="1b507-186"><strong>Office Communications Server 2007 の動作</strong></span><span class="sxs-lookup"><span data-stu-id="1b507-186"><strong>Office Communications Server 2007 behavior</strong></span></span></p>
<p><span data-ttu-id="1b507-187">この属性の値の範囲は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="1b507-187">The range of values for this attribute is as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="1b507-188">0: ArchiveFederationDefaultWithoutBody (廃止)</span><span class="sxs-lookup"><span data-stu-id="1b507-188">0: ArchiveFederationDefaultWithoutBody (retired)</span></span></p></li>
<li><p><span data-ttu-id="1b507-189">1-2: アーカイブ Internalcommunications</span><span class="sxs-lookup"><span data-stu-id="1b507-189">1-2: ArchiveInternalCommunications</span></span></p></li>
<li><p><span data-ttu-id="1b507-190">3-4: ArchiveFederatedCommunications</span><span class="sxs-lookup"><span data-stu-id="1b507-190">3-4: ArchiveFederatedCommunications</span></span></p></li>
<li><p><span data-ttu-id="1b507-191">5: RecordPresenceRegistrations</span><span class="sxs-lookup"><span data-stu-id="1b507-191">5: RecordPresenceRegistrations</span></span></p></li>
<li><p><span data-ttu-id="1b507-192">6: RecordIMCallDetails</span><span class="sxs-lookup"><span data-stu-id="1b507-192">6: RecordIMCallDetails</span></span></p></li>
<li><p><span data-ttu-id="1b507-193">7: RecordGroupIMCallDetails</span><span class="sxs-lookup"><span data-stu-id="1b507-193">7: RecordGroupIMCallDetails</span></span></p></li>
<li><p><span data-ttu-id="1b507-194">8: RecordFileTransferInstances</span><span class="sxs-lookup"><span data-stu-id="1b507-194">8: RecordFileTransferInstances</span></span></p></li>
<li><p><span data-ttu-id="1b507-195">9: RecordAudioCallDetails</span><span class="sxs-lookup"><span data-stu-id="1b507-195">9: RecordAudioCallDetails</span></span></p></li>
<li><p><span data-ttu-id="1b507-196">10: RecordVideoCallDetails</span><span class="sxs-lookup"><span data-stu-id="1b507-196">10: RecordVideoCallDetails</span></span></p></li>
<li><p><span data-ttu-id="1b507-197">11: RecordRemoteAssistanceCallDetails</span><span class="sxs-lookup"><span data-stu-id="1b507-197">11: RecordRemoteAssistanceCallDetails</span></span></p></li>
<li><p><span data-ttu-id="1b507-198">12: RecordApplicationSharingDetails</span><span class="sxs-lookup"><span data-stu-id="1b507-198">12: RecordApplicationSharingDetails</span></span></p></li>
<li><p><span data-ttu-id="1b507-199">13: レコードの会議のインスタンス化</span><span class="sxs-lookup"><span data-stu-id="1b507-199">13: RecordMeetingInstantiations</span></span></p></li>
<li><p><span data-ttu-id="1b507-200">14: レコード会議の結合</span><span class="sxs-lookup"><span data-stu-id="1b507-200">14: RecordMeetingJoins</span></span></p></li>
<li><p><span data-ttu-id="1b507-201">15: RecordDataJoins</span><span class="sxs-lookup"><span data-stu-id="1b507-201">15: RecordDataJoins</span></span></p></li>
<li><p><span data-ttu-id="1b507-202">16: RecordAVJoins</span><span class="sxs-lookup"><span data-stu-id="1b507-202">16: RecordAVJoins</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="1b507-203">Live Communications Server 2005 の新しいもの。</span><span class="sxs-lookup"><span data-stu-id="1b507-203">New in Live Communications Server 2005.</span></span></p>
<p><span data-ttu-id="1b507-204">Lync Server 2010 では廃止されました。</span><span class="sxs-lookup"><span data-stu-id="1b507-204">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b507-205">msRTCSIP-Msrtcsip-archivefederationdefault (現在不使用)</span><span class="sxs-lookup"><span data-stu-id="1b507-205">msRTCSIP-ArchiveFederationDefault (obsolete)</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="1b507-206">Live Communications Server 2005 の新しいもの。</span><span class="sxs-lookup"><span data-stu-id="1b507-206">New in Live Communications Server 2005.</span></span></p>
<p><span data-ttu-id="1b507-207">Office Communications Server 2007 では廃止されました。</span><span class="sxs-lookup"><span data-stu-id="1b507-207">Obsolete in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b507-208">msRTCSIP-Msrtcsip-archivefederationdefaultflags (現在不使用)</span><span class="sxs-lookup"><span data-stu-id="1b507-208">msRTCSIP-ArchiveFederationDefaultFlags (obsolete)</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="1b507-209">Live Communications Server 2005 の新しいもの。</span><span class="sxs-lookup"><span data-stu-id="1b507-209">New in Live Communications Server 2005.</span></span></p>
<p><span data-ttu-id="1b507-210">Office Communications Server 2007 では廃止されました。</span><span class="sxs-lookup"><span data-stu-id="1b507-210">Obsolete in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b507-211">msRTCSIP-ArchivingEnabled</span><span class="sxs-lookup"><span data-stu-id="1b507-211">msRTCSIP-ArchivingEnabled</span></span></p></td>
<td><p><span data-ttu-id="1b507-212">この属性は、1人のユーザーの通信をアーカイブするかどうかを制御するためのビットフィールドとして使用される整数です。</span><span class="sxs-lookup"><span data-stu-id="1b507-212">This attribute is an integer used as a bit field to control whether a single user’s communications are to be archived.</span></span> <span data-ttu-id="1b507-213">このコントロールは、アーカイブエージェントレイヤーによって適用されます。</span><span class="sxs-lookup"><span data-stu-id="1b507-213">This control is enforced by the archiving agent layer.</span></span> <span data-ttu-id="1b507-214">グローバルカタログレプリケーションのマークが付いています。</span><span class="sxs-lookup"><span data-stu-id="1b507-214">It is marked for global catalog replication.</span></span></p>
<p><span data-ttu-id="1b507-215">この属性のスコープは、1人のユーザーまたは連絡先に固有です。</span><span class="sxs-lookup"><span data-stu-id="1b507-215">The scope of this attribute is specific to a single user or contact.</span></span> <span data-ttu-id="1b507-216">Lync Server での有効な値 (および関連するビット位置) は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="1b507-216">The valid values (and associated bit positions) in Lync Server are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="1b507-217">0: アーカイブしない (ビットセットなし)</span><span class="sxs-lookup"><span data-stu-id="1b507-217">0: Do not archive (no bit set)</span></span></p></li>
<li><p><span data-ttu-id="1b507-218">1: 廃止 (ビット位置 0)</span><span class="sxs-lookup"><span data-stu-id="1b507-218">1: Retired (bit position 0)</span></span></p></li>
<li><p><span data-ttu-id="1b507-219">2: 廃止 (ビット位置 1)</span><span class="sxs-lookup"><span data-stu-id="1b507-219">2: Retired (bit position 1)</span></span></p></li>
<li><p><span data-ttu-id="1b507-220">4: 内部通信のアーカイブ (ビット位置 2)</span><span class="sxs-lookup"><span data-stu-id="1b507-220">4: Archive internal communications (bit position 2)</span></span></p></li>
<li><p><span data-ttu-id="1b507-221">8: フェデレーション通信のアーカイブ (ビット位置 3)</span><span class="sxs-lookup"><span data-stu-id="1b507-221">8: Archive federated communications (bit position 3)</span></span></p></li>
</ul>
<p><span data-ttu-id="1b507-222">Live Communications Server 2005 の以前の有効な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="1b507-222">Previously valid values in Live Communications Server 2005 are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="1b507-223">0: <strong>msRTCSIP</strong> によって定義されている既定値 <strong>を使用</strong> します。既定値は、この優先順位に従っています。</span><span class="sxs-lookup"><span data-stu-id="1b507-223">0:Use the default value defined by <strong>msRTCSIP-ArchiveDefault</strong> and <strong>msRTCSIP-ArchiveFederation</strong> in this order of precedence:</span></span></p>
<ul>
<li><p><span data-ttu-id="1b507-224">1: アーカイブ</span><span class="sxs-lookup"><span data-stu-id="1b507-224">1: Archive</span></span></p></li>
<li><p><span data-ttu-id="1b507-225">2: アーカイブしない</span><span class="sxs-lookup"><span data-stu-id="1b507-225">2: Do not archive</span></span></p></li>
<li><p><span data-ttu-id="1b507-226">3: メッセージ本文を含まないアーカイブ</span><span class="sxs-lookup"><span data-stu-id="1b507-226">3: Archive without the message body</span></span></p></li>
</ul></li>
</ul></td>
<td><p><span data-ttu-id="1b507-227">Live Communications Server 2005 の新しいもの。</span><span class="sxs-lookup"><span data-stu-id="1b507-227">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b507-228">msRTCSIP-Msrtcsip-archivingserverdata (現在不使用)</span><span class="sxs-lookup"><span data-stu-id="1b507-228">msRTCSIP-ArchivingServerData (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="1b507-229">この属性は、今後の使用のために予約されています。</span><span class="sxs-lookup"><span data-stu-id="1b507-229">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="1b507-230">Lync Server 2010 では廃止されました。</span><span class="sxs-lookup"><span data-stu-id="1b507-230">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b507-231">msRTCSIP-Msrtcsip-archivingserverversion (現在不使用)</span><span class="sxs-lookup"><span data-stu-id="1b507-231">msRTCSIP-ArchivingServerVersion (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="1b507-232">この属性は、アーカイブサービスのバージョンを定義します。</span><span class="sxs-lookup"><span data-stu-id="1b507-232">This attribute defines the version of the Archiving service.</span></span> <span data-ttu-id="1b507-233">この属性は、公式の製品リリースごとにインクリメントする monotonously 増加整数型です。</span><span class="sxs-lookup"><span data-stu-id="1b507-233">This attribute is a monotonously increasing integer type that increments with each official product release.</span></span> <span data-ttu-id="1b507-234">有効な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="1b507-234">The possible valid values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="1b507-235">Undefined: Live Communications Server 2003</span><span class="sxs-lookup"><span data-stu-id="1b507-235">Undefined: Live Communications Server 2003</span></span></p>
<p><span data-ttu-id="1b507-236">                 Live Communications Server 2005</span><span class="sxs-lookup"><span data-stu-id="1b507-236">                 Live Communications Server 2005</span></span></p>
<p><span data-ttu-id="1b507-237">                 Live Communications Server 2005 with SP1</span><span class="sxs-lookup"><span data-stu-id="1b507-237">                 Live Communications Server 2005 with SP1</span></span></p></li>
<li><p><span data-ttu-id="1b507-238">3: Office Communications Server 2007</span><span class="sxs-lookup"><span data-stu-id="1b507-238">3: Office Communications Server 2007</span></span></p></li>
<li><p><span data-ttu-id="1b507-239">4: Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="1b507-239">4: Office Communications Server 2007 R2</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="1b507-240">Office Communications Server 2007 の新製品。</span><span class="sxs-lookup"><span data-stu-id="1b507-240">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="1b507-241">Lync Server 2010 では廃止されました。</span><span class="sxs-lookup"><span data-stu-id="1b507-241">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b507-242">msRTCSIP-BackEndServer</span><span class="sxs-lookup"><span data-stu-id="1b507-242">msRTCSIP-BackEndServer</span></span></p></td>
<td><p><span data-ttu-id="1b507-243">この属性は、プールのバックエンドサーバーの FQDN を指定します。</span><span class="sxs-lookup"><span data-stu-id="1b507-243">This attribute specifies the FQDN of the Back End Server of the pool.</span></span> <span data-ttu-id="1b507-244">プールごとに1つのバックエンドサーバーしか存在できないため、これは単一値の属性です。</span><span class="sxs-lookup"><span data-stu-id="1b507-244">Because there can only be a single Back End Server per pool, this is a single-valued attribute.</span></span></p>
<p><span data-ttu-id="1b507-245">各セグメントの有効な値は、63文字です。FQDN 全体の有効な値は255文字です。</span><span class="sxs-lookup"><span data-stu-id="1b507-245">The valid value for each segment is 63 characters; the valid value for the entire FQDN is 255 characters.</span></span></p></td>
<td><p><span data-ttu-id="1b507-246">Live Communications Server 2005 の新しいもの。</span><span class="sxs-lookup"><span data-stu-id="1b507-246">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b507-247">msRTCSIP-ConferenceDirectoryHomePool</span><span class="sxs-lookup"><span data-stu-id="1b507-247">msRTCSIP-ConferenceDirectoryHomePool</span></span></p></td>
<td><p><span data-ttu-id="1b507-248">この属性には、会議ディレクトリをホストするプールの識別子が含まれます。</span><span class="sxs-lookup"><span data-stu-id="1b507-248">This attribute contains the identifier of the pool that hosts the conference directory.</span></span></p></td>
<td><p><span data-ttu-id="1b507-249">Office Communications Server 2007 R2 の新製品。</span><span class="sxs-lookup"><span data-stu-id="1b507-249">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b507-250">msRTCSIP-ConferenceDirectoryId</span><span class="sxs-lookup"><span data-stu-id="1b507-250">msRTCSIP-ConferenceDirectoryId</span></span></p></td>
<td><p><span data-ttu-id="1b507-251">この属性には、会議ディレクトリの識別子が含まれています。</span><span class="sxs-lookup"><span data-stu-id="1b507-251">This attribute contains the identifier of a conference directory.</span></span></p></td>
<td><p><span data-ttu-id="1b507-252">Office Communications Server 2007 R2 の新製品。</span><span class="sxs-lookup"><span data-stu-id="1b507-252">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b507-253">msRTCSIP-ConferenceDirectoryTargetPool</span><span class="sxs-lookup"><span data-stu-id="1b507-253">msRTCSIP-ConferenceDirectoryTargetPool</span></span></p></td>
<td><p><span data-ttu-id="1b507-254">この属性には、会議ディレクトリの移動先のプールの識別子が含まれます。</span><span class="sxs-lookup"><span data-stu-id="1b507-254">This attribute contains the identifier of the pool to which the conference directory is being moved.</span></span></p></td>
<td><p><span data-ttu-id="1b507-255">Office Communications Server 2007 R2 の新製品。</span><span class="sxs-lookup"><span data-stu-id="1b507-255">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b507-256">msRTCSIP-既定値</span><span class="sxs-lookup"><span data-stu-id="1b507-256">msRTCSIP-Default</span></span></p></td>
<td><p><span data-ttu-id="1b507-257">このブール値属性は、電話の使用法が既定の使用方法であるかどうかを定義します。</span><span class="sxs-lookup"><span data-stu-id="1b507-257">This Boolean attribute defines whether the phone usage is a default usage.</span></span> <span data-ttu-id="1b507-258">この属性が <strong>TRUE</strong>に設定されている場合、電話使用法は既定の使用方法であり、管理者が削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="1b507-258">If this attribute is set to <strong>TRUE</strong>, the phone usage is a default usage and cannot be deleted by the administrator.</span></span> <span data-ttu-id="1b507-259">この属性が <strong>FALSE</strong>に設定されている場合は、使用法を削除できます。</span><span class="sxs-lookup"><span data-stu-id="1b507-259">If this attribute is set to <strong>FALSE</strong>, the usage can be deleted.</span></span></p></td>
<td><p><span data-ttu-id="1b507-260">Office Communications Server 2007 の新製品。</span><span class="sxs-lookup"><span data-stu-id="1b507-260">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b507-261">msRTCSIP-DefaultCWAExternalURL</span><span class="sxs-lookup"><span data-stu-id="1b507-261">msRTCSIP-DefaultCWAExternalURL</span></span></p></td>
<td><p><span data-ttu-id="1b507-262">この属性は、組織外のユーザーの Communicator Web Access URL を識別します。</span><span class="sxs-lookup"><span data-stu-id="1b507-262">This attribute identifies the Communicator Web Access URL for users who are outside the organization.</span></span></p></td>
<td><p><span data-ttu-id="1b507-263">Office Communications Server 2007 R2 の新製品。</span><span class="sxs-lookup"><span data-stu-id="1b507-263">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b507-264">msRTCSIP-DefaultCWAInternalURL</span><span class="sxs-lookup"><span data-stu-id="1b507-264">msRTCSIP-DefaultCWAInternalURL</span></span></p></td>
<td><p><span data-ttu-id="1b507-265">この属性は、組織内のユーザーの Communicator Web Access URL を識別します。</span><span class="sxs-lookup"><span data-stu-id="1b507-265">This attribute identifies the Communicator Web Access URL for users who are inside the organization.</span></span></p></td>
<td><p><span data-ttu-id="1b507-266">Office Communications Server 2007 R2 の新製品。</span><span class="sxs-lookup"><span data-stu-id="1b507-266">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b507-267">msRTCSIP-DefaultLocationProfileLink (現在不使用)</span><span class="sxs-lookup"><span data-stu-id="1b507-267">msRTCSIP-DefaultLocationProfileLink (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="1b507-268">この単一値属性には、割り当てられている場所プロファイルクラスオブジェクトの識別名 (DN) が含まれています。</span><span class="sxs-lookup"><span data-stu-id="1b507-268">This single-valued attribute contains the distinguished name (DN) of a location profile class object assigned to it.</span></span></p>
<p><span data-ttu-id="1b507-269">前方リンク: <strong>リンク ID 11036</strong></span><span class="sxs-lookup"><span data-stu-id="1b507-269">Forward link: <strong>Link ID 11036</strong></span></span></p>
<p><span data-ttu-id="1b507-270">対応する後方リンクは、 <strong>msRTCSIP-ServerReferenceBL</strong>です。</span><span class="sxs-lookup"><span data-stu-id="1b507-270">The corresponding backward link is <strong>msRTCSIP-ServerReferenceBL</strong>.</span></span></p></td>
<td><p><span data-ttu-id="1b507-271">Lync Server 2010 では廃止されました。</span><span class="sxs-lookup"><span data-stu-id="1b507-271">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b507-272">msRTCSIP-DefaultPolicy (現在不使用)</span><span class="sxs-lookup"><span data-stu-id="1b507-272">msRTCSIP-DefaultPolicy (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="1b507-273">このブール属性は、ポリシーが既定のポリシーであるかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="1b507-273">This Boolean attribute specifies whether the policy is a default policy.</span></span> <span data-ttu-id="1b507-274">ポリシーは、 <strong>TRUE</strong>に設定されている場合の既定のポリシーです。</span><span class="sxs-lookup"><span data-stu-id="1b507-274">The policy is a default policy when set to <strong>TRUE</strong>.</span></span></p></td>
<td><p><span data-ttu-id="1b507-275">Office Communications Server 2007 の新製品</span><span class="sxs-lookup"><span data-stu-id="1b507-275">New in Office Communications Server 2007</span></span></p>
<p><span data-ttu-id="1b507-276">Lync Server 2010 では廃止されました。</span><span class="sxs-lookup"><span data-stu-id="1b507-276">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b507-277">msRTCSIP-Msrtcsip-defaultroutetoedgeproxy (現在不使用)</span><span class="sxs-lookup"><span data-stu-id="1b507-277">msRTCSIP-DefaultRouteToEdgeProxy (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="1b507-278">この属性は、アクセスエッジサービスを実行しているエッジサーバーの FQDN、アクセス可能な場合は、アクセスエッジサービスを実行しているサーバーのプールのハードウェアロードバランサーの FQDN を指定します。</span><span class="sxs-lookup"><span data-stu-id="1b507-278">This attribute specifies the FQDN of either the Edge Server running the Access Edge service, if it can be accessed directly, or of the hardware load balancer for a pool of servers running Access Edge service.</span></span> <span data-ttu-id="1b507-279">アクセスエッジサービスを実行しているサーバーが1つまたは複数のディレクターを介してのみアクセスできる場合は、この属性によって、ディレクターの FQDN、およびオプションとして、ディレクタープールを提供するディレクターまたはハードウェアロードバランサーのポート番号が指定されます。</span><span class="sxs-lookup"><span data-stu-id="1b507-279">If the servers running Access Edge service can be accessed only through one or more Directors, this attribute specifies the FQDN and, optionally, the port number of the Director or of the hardware load balancer serving a Director pool.</span></span></p>
<p><span data-ttu-id="1b507-280">各セグメントの有効な値は、63文字です。FQDN 全体の有効な値は255文字です。</span><span class="sxs-lookup"><span data-stu-id="1b507-280">The valid value for each segment is 63 characters; the valid value for the entire FQDN is 255 characters.</span></span></p></td>
<td><p><span data-ttu-id="1b507-281">Live Communications Server 2005 の新しいもの。</span><span class="sxs-lookup"><span data-stu-id="1b507-281">New in Live Communications Server 2005.</span></span></p>
<p><span data-ttu-id="1b507-282">Lync Server 2010 では廃止されました。</span><span class="sxs-lookup"><span data-stu-id="1b507-282">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b507-283">msRTCSIP-Msrtcsip-defaultroutetoedgeproxyport (現在不使用)</span><span class="sxs-lookup"><span data-stu-id="1b507-283">msRTCSIP-DefaultRouteToEdgeProxyPort (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="1b507-284">この属性は、アクセスエッジサービスを実行しているサーバーに接続するために使用されるポート番号を表します。</span><span class="sxs-lookup"><span data-stu-id="1b507-284">This attribute represents the port number that should be used to connect to the server running Access Edge service.</span></span></p>
<p><span data-ttu-id="1b507-285">有効な値は、使用するポートを指定する整数型 (integer) の値です。</span><span class="sxs-lookup"><span data-stu-id="1b507-285">The valid value is an integer value specifying the port to be used.</span></span> <span data-ttu-id="1b507-286">既定値は 5061 です。</span><span class="sxs-lookup"><span data-stu-id="1b507-286">The default value is 5061.</span></span></p></td>
<td><p><span data-ttu-id="1b507-287">Live Communications Server 2005 の新しいもの。</span><span class="sxs-lookup"><span data-stu-id="1b507-287">New in Live Communications Server 2005.</span></span></p>
<p><span data-ttu-id="1b507-288">Lync Server 2010 では廃止されました。</span><span class="sxs-lookup"><span data-stu-id="1b507-288">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b507-289">msRTCSIP-Msrtcsip-defpresencesubscriptiontimeout (現在不使用)</span><span class="sxs-lookup"><span data-stu-id="1b507-289">msRTCSIP-DefPresenceSubscriptionTimeout (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="1b507-290">既定のプレゼンスサブスクリプションタイムアウト期間を表す属性です。</span><span class="sxs-lookup"><span data-stu-id="1b507-290">This attribute represents the default presence subscription time-out period.</span></span></p></td>
<td><p><span data-ttu-id="1b507-291">Lync Server 2010 では廃止されました。</span><span class="sxs-lookup"><span data-stu-id="1b507-291">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b507-292">msRTCSIP-DefRegistrationTimeout (obsolete)</span><span class="sxs-lookup"><span data-stu-id="1b507-292">msRTCSIP-DefRegistrationTimeout (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="1b507-293">既定の登録タイムアウト期間を表す属性です。</span><span class="sxs-lookup"><span data-stu-id="1b507-293">This attribute represents the default registration time-out window.</span></span></p></td>
<td><p><span data-ttu-id="1b507-294">Lync Server 2010 では廃止されました。</span><span class="sxs-lookup"><span data-stu-id="1b507-294">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b507-295">msRTCSIP-Msrtcsip-defroamingdatasubscriptiontimeout (現在不使用)</span><span class="sxs-lookup"><span data-stu-id="1b507-295">msRTCSIP-DefRoamingDataSubscriptionTimeout (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="1b507-296">既定の移動データサブスクリプションタイムアウト期間を表す属性です。</span><span class="sxs-lookup"><span data-stu-id="1b507-296">This attribute represents the default roaming data subscription time-out window.</span></span></p></td>
<td><p><span data-ttu-id="1b507-297">Lync Server 2010 では廃止されました。</span><span class="sxs-lookup"><span data-stu-id="1b507-297">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b507-298">msRTCSIP-DeploymentLocator</span><span class="sxs-lookup"><span data-stu-id="1b507-298">msRTCSIP-DeploymentLocator</span></span></p></td>
<td><p><span data-ttu-id="1b507-299">この属性は、分割ドメイントポロジで使用され、完全修飾ドメイン名 (FQDN) を含みます。</span><span class="sxs-lookup"><span data-stu-id="1b507-299">This attribute is used in a split domain topology and contains a fully qualified domain name (FQDN).</span></span></p></td>
<td><p><span data-ttu-id="1b507-300">Lync Server 2010 の新。</span><span class="sxs-lookup"><span data-stu-id="1b507-300">New in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b507-301">msRTCSIP-Description (現在不使用)</span><span class="sxs-lookup"><span data-stu-id="1b507-301">msRTCSIP-Description (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="1b507-302">この電話ルートまたは正規化ルールのわかりやすい説明を含む単一値の UNICODE 文字列属性です。</span><span class="sxs-lookup"><span data-stu-id="1b507-302">This single-valued UNICODE string attribute contains a friendly description of this phone route or normalization rule.</span></span></p></td>
<td><p><span data-ttu-id="1b507-303">Office Communications Server 2007 の新製品。</span><span class="sxs-lookup"><span data-stu-id="1b507-303">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="1b507-304">Lync Server 2010 では廃止されました。</span><span class="sxs-lookup"><span data-stu-id="1b507-304">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b507-305">msRTCSIP-DomainData</span><span class="sxs-lookup"><span data-stu-id="1b507-305">msRTCSIP-DomainData</span></span></p></td>
<td><p><span data-ttu-id="1b507-306">この属性は、今後の使用のために予約されています。</span><span class="sxs-lookup"><span data-stu-id="1b507-306">This attribute is reserved for future use.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b507-307">msRTCSIP-DomainName</span><span class="sxs-lookup"><span data-stu-id="1b507-307">msRTCSIP-DomainName</span></span></p></td>
<td><p><span data-ttu-id="1b507-308">レジストラーに対して構成されたドメインを表す属性です。</span><span class="sxs-lookup"><span data-stu-id="1b507-308">This attribute represents a domain configured for the Registrar.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b507-309">msRTCSIP-EdgeProxyData</span><span class="sxs-lookup"><span data-stu-id="1b507-309">msRTCSIP-EdgeProxyData</span></span></p></td>
<td><p><span data-ttu-id="1b507-310">この属性は、今後の使用のために予約されています。</span><span class="sxs-lookup"><span data-stu-id="1b507-310">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="1b507-311">Live Communications Server 2005 の新しいもの。</span><span class="sxs-lookup"><span data-stu-id="1b507-311">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b507-312">msRTCSIP-EdgeProxyFQDN</span><span class="sxs-lookup"><span data-stu-id="1b507-312">msRTCSIP-EdgeProxyFQDN</span></span></p></td>
<td><p><span data-ttu-id="1b507-313">この属性は、アクセスエッジサービスを実行しているサーバーの FQDN を指定します。</span><span class="sxs-lookup"><span data-stu-id="1b507-313">This attribute specifies the FQDN of the server running Access Edge service.</span></span></p>
<p><span data-ttu-id="1b507-314">各セグメントの有効な値は、63文字です。FQDN 全体の有効な値は255文字です。</span><span class="sxs-lookup"><span data-stu-id="1b507-314">The valid value for each segment is 63 characters; the valid value for the entire FQDN is 255 characters.</span></span></p></td>
<td><p><span data-ttu-id="1b507-315">Live Communications Server 2005 の新しいもの。</span><span class="sxs-lookup"><span data-stu-id="1b507-315">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b507-316">msRTCSIP-Msrtcsip-enablebesteffortnotify (現在不使用)</span><span class="sxs-lookup"><span data-stu-id="1b507-316">msRTCSIP-EnableBestEffortNotify (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="1b507-317">この属性は、クライアントからのサブスクライブ要求に対する応答として、サーバーが NOTIFY 要求ではなく、Best エフォート NOTIFY (BENOTIFY) 要求を生成するかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="1b507-317">This attribute controls whether a server generates a Best Effort NOTIFY (BENOTIFY) request, instead of a NOTIFY request, in response to a SUBSCRIBE request from a client.</span></span> <span data-ttu-id="1b507-318">BENOTIFY は、定期的な NOTIFY 要求ではなく、サーバーが BENOTIFY 要求を生成するサブスクライブ通知ハンドシェイクに対して、パフォーマンスが強化された拡張機能です。</span><span class="sxs-lookup"><span data-stu-id="1b507-318">BENOTIFY is a performance-enhancing extension to the subscribe notification handshake where the server generates BENOTIFY requests, instead of regular NOTIFY requests.</span></span> <span data-ttu-id="1b507-319">パフォーマンス上の利点として、NOTIFY 要求と同様に、BENOTIFY 要求でクライアントから 200 OK 応答が要求されないことが挙げられます。</span><span class="sxs-lookup"><span data-stu-id="1b507-319">The performance benefit is that a BENOTIFY request does not require a 200 OK response from the client as the NOTIFY request does.</span></span></p>
<p><span data-ttu-id="1b507-320">有効な値は、 <strong>TRUE</strong> または <strong>FALSE</strong>です。</span><span class="sxs-lookup"><span data-stu-id="1b507-320">The valid values are <strong>TRUE</strong> or <strong>FALSE</strong>.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="1b507-321">Live Communications Server 2003 は、BENOTIFY 要求をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="1b507-321">Live Communications Server 2003 does not support BENOTIFY requests.</span></span> <span data-ttu-id="1b507-322">Live Communications Server 2005 およびサードパーティ製サーバーで実行されている Live Communications Server 2003 サーバー API を使用して記述されたサーバーアプリケーションと相互運用するには、BENOTIFY 要求の値を <STRONG>FALSE</STRONG>に設定することで無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="1b507-322">To interoperate with server applications written with the Live Communications Server 2003 server API running on Live Communications Server 2005 and third-party servers, BENOTIFY requests can be disabled by setting its value to <STRONG>FALSE</STRONG>.</span></span> <span data-ttu-id="1b507-323">現時点では、BENOTIFY は、IETF (インターネットエンジニアリングのタスクフォース) SIP 標準化プロセスの一部ではありません。</span><span class="sxs-lookup"><span data-stu-id="1b507-323">BENOTIFY is not currently part of the IETF (Internet Engineering Task Force) SIP standardization process.</span></span>


</div></td>
<td><p><span data-ttu-id="1b507-324">Live Communications Server 2005 の新しいもの。</span><span class="sxs-lookup"><span data-stu-id="1b507-324">New in Live Communications Server 2005.</span></span></p>
<p><span data-ttu-id="1b507-325">Lync Server 2010 では廃止されました。</span><span class="sxs-lookup"><span data-stu-id="1b507-325">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b507-326">msRTCSIP-EnableFederation (現在不使用)</span><span class="sxs-lookup"><span data-stu-id="1b507-326">msRTCSIP-EnableFederation (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="1b507-327">この属性は、ユーザーが他の組織のユーザーとの通信を許可されているかどうかを構成するために IT 管理者が使用するグローバルスイッチです。</span><span class="sxs-lookup"><span data-stu-id="1b507-327">This attribute is a global switch that IT administrators use to configure whether users are allowed to communicate with users from other organizations.</span></span> <span data-ttu-id="1b507-328">これにより、管理者は個々のユーザーの <strong>FederationEnabled</strong> 属性を上書きすることができます。</span><span class="sxs-lookup"><span data-stu-id="1b507-328">It enables an administrator to overwrite an individual user’s <strong>FederationEnabled</strong> attribute.</span></span> <span data-ttu-id="1b507-329">この属性は、ワーム、ウイルス、または社内への攻撃によって発生する可能性があるインターネット攻撃から内部ネットワークを保護するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="1b507-329">This attribute can be useful to help protect the internal network from Internet attacks that may be caused by worms, viruses, or targeted attacks on the company.</span></span></p>
<p><span data-ttu-id="1b507-330">有効な値 (および関連するビット位置) は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="1b507-330">The valid values (and associated bit positions) are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="1b507-331">1: パブリック IM 接続が有効 (ビット位置 0)</span><span class="sxs-lookup"><span data-stu-id="1b507-331">1: Enabled for public IM connectivity (bit position 0)</span></span></p></li>
<li><p><span data-ttu-id="1b507-332">2: 予約済み (ビット位置 1)</span><span class="sxs-lookup"><span data-stu-id="1b507-332">2: Reserved (bit position 1)</span></span></p></li>
<li><p><span data-ttu-id="1b507-333">4: 予約済み (ビット位置 2)</span><span class="sxs-lookup"><span data-stu-id="1b507-333">4: Reserved (bit position 2)</span></span></p></li>
<li><p><span data-ttu-id="1b507-334">8: 予約済み (ビット位置 3)</span><span class="sxs-lookup"><span data-stu-id="1b507-334">8: Reserved (bit position 3)</span></span></p></li>
<li><p><span data-ttu-id="1b507-335">16: リモート通話コントロールが有効 [テレフォニー] (ビット位置 4)</span><span class="sxs-lookup"><span data-stu-id="1b507-335">16: Remote call control Enabled [Telephony] (bit position 4)</span></span></p></li>
<li><p><span data-ttu-id="1b507-336">64: AllowOrganizeMeetingWithAnonymousParticipants (ユーザーが匿名ユーザーを会議に招待できるようにする (ビット位置 6)</span><span class="sxs-lookup"><span data-stu-id="1b507-336">64: AllowOrganizeMeetingWithAnonymousParticipants (allow users to invite anonymous users to meetings (bit position 6)</span></span></p></li>
<li><p><span data-ttu-id="1b507-337">128: UCEnabled (ユーザーに対して統合コミュニケーションを有効にする) (ビット位置 7)</span><span class="sxs-lookup"><span data-stu-id="1b507-337">128: UCEnabled (enable users for unified communications) (bit position 7)</span></span></p></li>
<li><p><span data-ttu-id="1b507-338">256: EnabledForEnhancedPresence (ユーザーに対してパブリック IM 接続を有効にする) (ビット位置 8)</span><span class="sxs-lookup"><span data-stu-id="1b507-338">256: EnabledForEnhancedPresence (enable user for public IM connectivity) (bit position 8)</span></span></p></li>
<li><p><span data-ttu-id="1b507-339">512: RemoteCallControlDualMode (ビット位置 9)</span><span class="sxs-lookup"><span data-stu-id="1b507-339">512: RemoteCallControlDualMode (bit position 9)</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="1b507-340">Live Communications Server 2005 の新しいもの。</span><span class="sxs-lookup"><span data-stu-id="1b507-340">New in Live Communications Server 2005.</span></span></p>
<p><span data-ttu-id="1b507-341">Lync Server 2010 では廃止されました。</span><span class="sxs-lookup"><span data-stu-id="1b507-341">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b507-342">msRTCSIP-EnterpriseServices</span><span class="sxs-lookup"><span data-stu-id="1b507-342">msRTCSIP-EnterpriseServices</span></span></p></td>
<td><p><span data-ttu-id="1b507-343">この属性は、指定されたサーバーにエンタープライズサービスが読み込まれているかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="1b507-343">This attribute indicates whether the Enterprise Services are loaded on the given server.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b507-344">msRTCSIP-ExtensionData</span><span class="sxs-lookup"><span data-stu-id="1b507-344">msRTCSIP-ExtensionData</span></span></p></td>
<td><p><span data-ttu-id="1b507-345">この属性は、今後の使用のために予約されています。</span><span class="sxs-lookup"><span data-stu-id="1b507-345">This attribute is reserved for future use.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b507-346">msRTCSIP-ExternalAccessCode</span><span class="sxs-lookup"><span data-stu-id="1b507-346">msRTCSIP-ExternalAccessCode</span></span></p></td>
<td><p><span data-ttu-id="1b507-347">外部アクセスのダイヤルコードを含む属性です。</span><span class="sxs-lookup"><span data-stu-id="1b507-347">This attribute contains the dial code for external access.</span></span></p></td>
<td><p><span data-ttu-id="1b507-348">Office Communications Server 2007 R2 の新製品。</span><span class="sxs-lookup"><span data-stu-id="1b507-348">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b507-349">msRTCSIP-FederationEnabled</span><span class="sxs-lookup"><span data-stu-id="1b507-349">msRTCSIP-FederationEnabled</span></span></p></td>
<td><p><span data-ttu-id="1b507-350">この属性は、1人のユーザーがフェデレーションを有効にするかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="1b507-350">This attribute controls whether a single user is enabled for federation.</span></span> <span data-ttu-id="1b507-351">エンタープライズサービス層によって適用されます。</span><span class="sxs-lookup"><span data-stu-id="1b507-351">It is enforced by the Enterprise Services layer.</span></span> <span data-ttu-id="1b507-352">グローバルカタログレプリケーションのマークが付いています。</span><span class="sxs-lookup"><span data-stu-id="1b507-352">It is marked for global catalog replication.</span></span></p>
<p><span data-ttu-id="1b507-353">有効な値は、 <strong>TRUE</strong> または <strong>FALSE</strong>です。</span><span class="sxs-lookup"><span data-stu-id="1b507-353">The valid values are <strong>TRUE</strong> or <strong>FALSE</strong>.</span></span></p></td>
<td><p><span data-ttu-id="1b507-354">Live Communications Server 2005 の新しいもの。</span><span class="sxs-lookup"><span data-stu-id="1b507-354">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b507-355">msRTCSIP-FrontEndServers</span><span class="sxs-lookup"><span data-stu-id="1b507-355">msRTCSIP-FrontEndServers</span></span></p></td>
<td><p><span data-ttu-id="1b507-356">この属性は、プールに関連付けられているすべての Enterprise Edition サーバーのドメイン名の複数値を持つリストです。</span><span class="sxs-lookup"><span data-stu-id="1b507-356">This attribute is a multi-valued list of the domain names of all Enterprise Edition servers associated with a pool.</span></span></p>
<p><span data-ttu-id="1b507-357">後方リンク: <strong>リンク ID 11023</strong></span><span class="sxs-lookup"><span data-stu-id="1b507-357">Back link: <strong>Link ID 11023</strong></span></span></p>
<p><span data-ttu-id="1b507-358">この後方リンクへの対応する転送リンクは、 <strong>msRTCSIP-PoolAddress</strong>です。</span><span class="sxs-lookup"><span data-stu-id="1b507-358">The corresponding forward link to this back link is <strong>msRTCSIP-PoolAddress</strong>.</span></span></p></td>
<td><p><span data-ttu-id="1b507-359">Live Communications Server 2005 の新しいもの。</span><span class="sxs-lookup"><span data-stu-id="1b507-359">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b507-360">msRTCSIP-ゲートウェイ (obsolete)</span><span class="sxs-lookup"><span data-stu-id="1b507-360">msRTCSIP-Gateways (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="1b507-361">ゲートウェイとポート (ゲートウェイごと) の一覧を含む複数値の文字列属性です。</span><span class="sxs-lookup"><span data-stu-id="1b507-361">This multi-valued string attribute contains a list of gateways and ports (per gateway).</span></span></p></td>
<td><p><span data-ttu-id="1b507-362">Lync Server 2010 では廃止されました。</span><span class="sxs-lookup"><span data-stu-id="1b507-362">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b507-363">msRTCSIP-GlobalSettingsData (現在不使用)</span><span class="sxs-lookup"><span data-stu-id="1b507-363">msRTCSIP-GlobalSettingsData (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="1b507-364">この属性には、名前と値のペアが格納されます。</span><span class="sxs-lookup"><span data-stu-id="1b507-364">This attribute stores name:value pairs.</span></span> <span data-ttu-id="1b507-365">既に定義されている名前: 値のペアは、 <strong>プレゼンス設定のポーリングを許可</strong> するためのものです。</span><span class="sxs-lookup"><span data-stu-id="1b507-365">The already-defined name:value pair is for the <strong>allow polling for presence</strong> setting.</span></span></p></td>
<td><p><span data-ttu-id="1b507-366">Lync Server 2010 では廃止されました。</span><span class="sxs-lookup"><span data-stu-id="1b507-366">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b507-367">msRTCSIP-GroupingID</span><span class="sxs-lookup"><span data-stu-id="1b507-367">msRTCSIP-GroupingID</span></span></p></td>
<td><p><span data-ttu-id="1b507-368">この属性は、アドレス帳のエントリをグループ化するために使用されるグループの一意の識別子です。</span><span class="sxs-lookup"><span data-stu-id="1b507-368">This attribute is a unique identifier of a group that is used to group address book entries.</span></span></p></td>
<td><p><span data-ttu-id="1b507-369">Lync Server 2010 の新。</span><span class="sxs-lookup"><span data-stu-id="1b507-369">New in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b507-370">msRTCSIP-Msrtcsip-homeserver (現在不使用)</span><span class="sxs-lookup"><span data-stu-id="1b507-370">msRTCSIP-HomeServer (obsolete)</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="1b507-371">Live Communications Server 2003 (使用されていません) の新。</span><span class="sxs-lookup"><span data-stu-id="1b507-371">New in Live Communications Server 2003 (not used).</span></span></p>
<p><span data-ttu-id="1b507-372">現在、Live Communications Server 2005 では使用されていません。</span><span class="sxs-lookup"><span data-stu-id="1b507-372">Obsolete in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b507-373">msRTCSIP-Msrtcsip-homeserverstring (現在不使用)</span><span class="sxs-lookup"><span data-stu-id="1b507-373">msRTCSIP-HomeServerString (obsolete)</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="1b507-374">Live Communications Server 2003 の新しいもの。</span><span class="sxs-lookup"><span data-stu-id="1b507-374">New in Live Communications Server 2003.</span></span></p>
<p><span data-ttu-id="1b507-375">現在、Live Communications Server 2005 では使用されていません。</span><span class="sxs-lookup"><span data-stu-id="1b507-375">Obsolete in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b507-376">msRTCSIP-ホームユーザー (現在不使用)</span><span class="sxs-lookup"><span data-stu-id="1b507-376">msRTCSIP-HomeUsers (obsolete)</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="1b507-377">Live Communications Server 2003 (使用されていません) の新。</span><span class="sxs-lookup"><span data-stu-id="1b507-377">New in Live Communications Server 2003 (not used).</span></span></p>
<p><span data-ttu-id="1b507-378">現在、Live Communications Server 2005 では使用されていません。</span><span class="sxs-lookup"><span data-stu-id="1b507-378">Obsolete in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b507-379">msRTCSIP-InternetAccessEnabled</span><span class="sxs-lookup"><span data-stu-id="1b507-379">msRTCSIP-InternetAccessEnabled</span></span></p></td>
<td><p><span data-ttu-id="1b507-380">この属性は、単一のユーザーが外部ユーザーアクセスを有効にしているかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="1b507-380">This attribute controls whether a single user is enabled for outside user access.</span></span> <span data-ttu-id="1b507-381">エンタープライズサービス層によって適用されます。</span><span class="sxs-lookup"><span data-stu-id="1b507-381">It is enforced by the Enterprise Services layer.</span></span> <span data-ttu-id="1b507-382">グローバルカタログレプリケーションのマークが付いています。</span><span class="sxs-lookup"><span data-stu-id="1b507-382">It is marked for global catalog replication.</span></span></p>
<p><span data-ttu-id="1b507-383">有効な値は、 <strong>TRUE</strong> または <strong>FALSE</strong>です。</span><span class="sxs-lookup"><span data-stu-id="1b507-383">The valid values are <strong>TRUE</strong> or <strong>FALSE</strong>.</span></span></p></td>
<td><p><span data-ttu-id="1b507-384">Live Communications Server 2005 の新しいもの。</span><span class="sxs-lookup"><span data-stu-id="1b507-384">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b507-385">msRTCSIP-IsMaster (現在不使用)</span><span class="sxs-lookup"><span data-stu-id="1b507-385">msRTCSIP-IsMaster (obsolete)</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="1b507-386">Live Communications Server の新サービス2003</span><span class="sxs-lookup"><span data-stu-id="1b507-386">New in Live Communications Server 2003</span></span></p>
<p><span data-ttu-id="1b507-387">現在、Live Communications Server 2005 では使用されていません。</span><span class="sxs-lookup"><span data-stu-id="1b507-387">Obsolete in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b507-388">msRTCSIP-Line</span><span class="sxs-lookup"><span data-stu-id="1b507-388">msRTCSIP-Line</span></span></p></td>
<td><p><span data-ttu-id="1b507-389">この単一値の属性には、テレフォニーで Lync で使用されるデバイス ID (SIP URI またはユーザーが制御する電話の TEL URI) が含まれています。</span><span class="sxs-lookup"><span data-stu-id="1b507-389">This single-valued attribute contains the device ID (either the SIP URI or the TEL URI of the phone the user controls) used by Lync for telephony.</span></span> <span data-ttu-id="1b507-390">この属性は、グローバルカタログレプリケーションのマークが付いており、インデックスが作成されます。</span><span class="sxs-lookup"><span data-stu-id="1b507-390">This attribute is marked for Global Catalog replication and is indexed.</span></span> <span data-ttu-id="1b507-391">ユーザーがエンタープライズ Voip に対して有効になっている場合、この属性はユーザーの電話番号の e.164 正規化されたバージョンを格納します。</span><span class="sxs-lookup"><span data-stu-id="1b507-391">If a user is enabled for Enterprise Voice, this attribute stores the E.164 normalized version of the user’s phone number.</span></span></p></td>
<td><p><span data-ttu-id="1b507-392">Microsoft Office Live Communications Server 2005 SP1 の新技術情報</span><span class="sxs-lookup"><span data-stu-id="1b507-392">New in Microsoft Office Live Communications Server 2005 with SP1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b507-393">msRTCSIP</span><span class="sxs-lookup"><span data-stu-id="1b507-393">msRTCSIP-LineServer</span></span></p></td>
<td><p><span data-ttu-id="1b507-394">CSTA-SIP ゲートウェイサーバーの SIP URI を含む単一値の属性です。</span><span class="sxs-lookup"><span data-stu-id="1b507-394">This single-valued attribute contains the SIP URI of the CSTA-SIP gateway server.</span></span> <span data-ttu-id="1b507-395">この属性には、グローバルカタログレプリケーションのマークが付いていますが、インデックスは作成されません。</span><span class="sxs-lookup"><span data-stu-id="1b507-395">This attribute is marked for Global Catalog replication but is not indexed.</span></span></p></td>
<td><p><span data-ttu-id="1b507-396">Microsoft Office Live Communications Server 2005 SP1 の新技術情報</span><span class="sxs-lookup"><span data-stu-id="1b507-396">New in Microsoft Office Live Communications Server 2005 with SP1</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b507-397">msRTCSIP-LocalNormalizationData (現在不使用)</span><span class="sxs-lookup"><span data-stu-id="1b507-397">msRTCSIP-LocalNormalizationData (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="1b507-398">この属性は、今後の使用のために予約されています。</span><span class="sxs-lookup"><span data-stu-id="1b507-398">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="1b507-399">Office Communications Server 2007 の新製品。</span><span class="sxs-lookup"><span data-stu-id="1b507-399">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="1b507-400">Lync Server 2010 では廃止されました。</span><span class="sxs-lookup"><span data-stu-id="1b507-400">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b507-401">msRTCSIP-LocalNormalizationLinks (現在不使用)</span><span class="sxs-lookup"><span data-stu-id="1b507-401">msRTCSIP-LocalNormalizationLinks (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="1b507-402">この複数値属性には、この場所プロファイルに関連付けられているローカル正規化識別名 (DN) の一覧が含まれています。</span><span class="sxs-lookup"><span data-stu-id="1b507-402">This multi-valued attribute contains a list of local normalization distinguished names (DN) associated with this location profile.</span></span> <span data-ttu-id="1b507-403">この属性の型は、DN binary です。</span><span class="sxs-lookup"><span data-stu-id="1b507-403">The type of this attribute is a DN binary.</span></span> <span data-ttu-id="1b507-404">場所プロファイルとローカル正規化ルールの間には、一対多の関係があります。</span><span class="sxs-lookup"><span data-stu-id="1b507-404">There is a one-to-many relationship between location profile and local normalization rules.</span></span> <span data-ttu-id="1b507-405">ローカル正規化 DNs の一覧の順序は、管理者によって指定された順序で維持される必要があります。</span><span class="sxs-lookup"><span data-stu-id="1b507-405">The ordering of the list of local normalization DNs must be maintained in the order specified by the administrator.</span></span> <span data-ttu-id="1b507-406">順序の保持は、DN binary の2進部分によって維持されます。これにより、注文インデックスが指定されます。</span><span class="sxs-lookup"><span data-stu-id="1b507-406">The preservation of order is maintained by the binary portion of the DN binary, which specifies the order index.</span></span></p>
<p><span data-ttu-id="1b507-407">前方リンク: <strong>リンク ID 11034</strong></span><span class="sxs-lookup"><span data-stu-id="1b507-407">Forward link: <strong>Link ID 11034</strong></span></span></p>
<p><span data-ttu-id="1b507-408">この転送リンク属性への対応する後方リンクは、 <strong>msRTCSIP-LocationProfileBL</strong>です。</span><span class="sxs-lookup"><span data-stu-id="1b507-408">The corresponding back link to this forward link attribute is <strong>msRTCSIP-LocationProfileBL</strong>.</span></span></p></td>
<td><p><span data-ttu-id="1b507-409">Office Communications Server 2007 の新製品。</span><span class="sxs-lookup"><span data-stu-id="1b507-409">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="1b507-410">Lync Server 2010 では廃止されました。</span><span class="sxs-lookup"><span data-stu-id="1b507-410">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b507-411">msRTCSIP-LocalNormalizationOptions</span><span class="sxs-lookup"><span data-stu-id="1b507-411">msRTCSIP-LocalNormalizationOptions</span></span></p></td>
<td><p><span data-ttu-id="1b507-412">この属性には、正規化ルールのオプションの一覧が含まれています。</span><span class="sxs-lookup"><span data-stu-id="1b507-412">This attribute contains a list of options for the normalization rule.</span></span></p></td>
<td><p><span data-ttu-id="1b507-413">Office Communications Server 2007 R2 の新製品。</span><span class="sxs-lookup"><span data-stu-id="1b507-413">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b507-414">msRTCSIP-LocationName (現在不使用)</span><span class="sxs-lookup"><span data-stu-id="1b507-414">msRTCSIP-LocationName (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="1b507-415">この単一値の属性には、このプロファイルが表す場所を示す場所のプロファイルのフレンドリ名が含まれています。</span><span class="sxs-lookup"><span data-stu-id="1b507-415">This single-valued attribute contains a friendly name for the location profile that indicates which location this profile represents.</span></span> <span data-ttu-id="1b507-416">複数の場所プロファイルが存在する可能性があるため、管理者は異なるプロファイルを区別するための方法が必要です。</span><span class="sxs-lookup"><span data-stu-id="1b507-416">Because there can be multiple location profiles, the administrator needs a way to distinguish between different profiles.</span></span></p></td>
<td><p><span data-ttu-id="1b507-417">Office Communications Server 2007 の新製品。</span><span class="sxs-lookup"><span data-stu-id="1b507-417">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="1b507-418">Lync Server 2010 では廃止されました。</span><span class="sxs-lookup"><span data-stu-id="1b507-418">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b507-419">msRTCSIP-locationProfileBL (obsolete)</span><span class="sxs-lookup"><span data-stu-id="1b507-419">msRTCSIP-locationProfileBL (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="1b507-420">この複数値属性には、場所プロファイル識別名の一覧が含まれています。</span><span class="sxs-lookup"><span data-stu-id="1b507-420">This multi-valued attribute contains a list of location profile distinguished names.</span></span> <span data-ttu-id="1b507-421">この属性は、1つ以上の場所プロファイルへの後方リンクを指定します。</span><span class="sxs-lookup"><span data-stu-id="1b507-421">This attribute specifies the back link to one or more location profiles.</span></span></p>
<p><span data-ttu-id="1b507-422">後方リンク: <strong>リンク ID 11035</strong></span><span class="sxs-lookup"><span data-stu-id="1b507-422">Back link: <strong>Link ID 11035</strong></span></span></p>
<p><span data-ttu-id="1b507-423">この属性は、前方リンク <strong>msRTCSIP-LocalNormalizationLinks</strong>に対応しています。</span><span class="sxs-lookup"><span data-stu-id="1b507-423">This attribute corresponds to the forward link <strong>msRTCSIP-LocalNormalizationLinks</strong>.</span></span></p></td>
<td><p><span data-ttu-id="1b507-424">Office Communications Server 2007 の新製品。</span><span class="sxs-lookup"><span data-stu-id="1b507-424">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="1b507-425">Lync Server 2010 では廃止されました。</span><span class="sxs-lookup"><span data-stu-id="1b507-425">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b507-426">msRTCSIP-LocationProfileData (現在不使用)</span><span class="sxs-lookup"><span data-stu-id="1b507-426">msRTCSIP-LocationProfileData (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="1b507-427">この属性は、今後の使用のために予約されています。</span><span class="sxs-lookup"><span data-stu-id="1b507-427">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="1b507-428">Office Communications Server 2007 の新製品。</span><span class="sxs-lookup"><span data-stu-id="1b507-428">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="1b507-429">Lync Server 2010 では廃止されました。</span><span class="sxs-lookup"><span data-stu-id="1b507-429">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b507-430">msRTCSIP-LocationProfileOptions</span><span class="sxs-lookup"><span data-stu-id="1b507-430">msRTCSIP-LocationProfileOptions</span></span></p></td>
<td><p><span data-ttu-id="1b507-431">この属性には、場所のプロファイルのオプションが含まれています。</span><span class="sxs-lookup"><span data-stu-id="1b507-431">This attribute contains the options for the location profile.</span></span></p></td>
<td><p><span data-ttu-id="1b507-432">Office Communications Server 2007 R2 の新製品。</span><span class="sxs-lookup"><span data-stu-id="1b507-432">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b507-433">msRTCSIP-MappingContact</span><span class="sxs-lookup"><span data-stu-id="1b507-433">msRTCSIP-MappingContact</span></span></p></td>
<td><p><span data-ttu-id="1b507-434">この複数値属性は、アプリケーションの連絡先のリストを保持します。</span><span class="sxs-lookup"><span data-stu-id="1b507-434">This multiple-value attribute holds a list of application contacts.</span></span></p></td>
<td><p><span data-ttu-id="1b507-435">Office Communications Server 2007 R2 の新製品。</span><span class="sxs-lookup"><span data-stu-id="1b507-435">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b507-436">msRTCSIP-MappingLocation</span><span class="sxs-lookup"><span data-stu-id="1b507-436">msRTCSIP-MappingLocation</span></span></p></td>
<td><p><span data-ttu-id="1b507-437">この複数値属性は、場所のプロファイルの一覧を保持します。</span><span class="sxs-lookup"><span data-stu-id="1b507-437">This multiple-value attribute holds a list of location profiles.</span></span></p></td>
<td><p><span data-ttu-id="1b507-438">Office Communications Server 2007 R2 の新製品。</span><span class="sxs-lookup"><span data-stu-id="1b507-438">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b507-439">msRTCSIP-Maxnumoutingsearchperserver (現在不使用)</span><span class="sxs-lookup"><span data-stu-id="1b507-439">msRTCSIP-MaxNumOutstandingSearchPerServer (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="1b507-440">この属性は、サーバーごとの未処理の検索要求の最大数を表します。</span><span class="sxs-lookup"><span data-stu-id="1b507-440">This attribute represents the maximum number of outstanding search requests per server.</span></span></p></td>
<td><p><span data-ttu-id="1b507-441">Lync Server 2010 では廃止されました。</span><span class="sxs-lookup"><span data-stu-id="1b507-441">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b507-442">msRTCSIP-MaxNumSubscriptionsPerUser (現在不使用)</span><span class="sxs-lookup"><span data-stu-id="1b507-442">msRTCSIP-MaxNumSubscriptionsPerUser (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="1b507-443">ユーザーごとのサブスクリプションの最大数を表す属性です。</span><span class="sxs-lookup"><span data-stu-id="1b507-443">The attribute represents the maximum number of subscriptions per user.</span></span></p></td>
<td><p><span data-ttu-id="1b507-444">Lync Server 2010 では廃止されました。</span><span class="sxs-lookup"><span data-stu-id="1b507-444">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b507-445">msRTCSIP-Msrtcsip-maxpresencesubscriptiontimeout (現在不使用)</span><span class="sxs-lookup"><span data-stu-id="1b507-445">msRTCSIP-MaxPresenceSubscriptionTimeout (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="1b507-446">サブスクリプションタイムアウト期間の最大値を表す属性です。</span><span class="sxs-lookup"><span data-stu-id="1b507-446">This attribute represents the maximum subscription time-out window.</span></span></p></td>
<td><p><span data-ttu-id="1b507-447">Lync Server 2010 では廃止されました。</span><span class="sxs-lookup"><span data-stu-id="1b507-447">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b507-448">msRTCSIP-Msrtcsip-maxregistrationstimeout (現在不使用)</span><span class="sxs-lookup"><span data-stu-id="1b507-448">msRTCSIP-MaxRegistrationsTimeout (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="1b507-449">この属性は、最大登録タイムアウト時間枠を表します。</span><span class="sxs-lookup"><span data-stu-id="1b507-449">This attribute represents the maximum registrations time-out window.</span></span></p></td>
<td><p><span data-ttu-id="1b507-450">Lync Server 2010 では廃止されました。</span><span class="sxs-lookup"><span data-stu-id="1b507-450">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b507-451">msRTCSIP-Msrtcsip-maxroamingdatasubscriptiontimeout (現在不使用)</span><span class="sxs-lookup"><span data-stu-id="1b507-451">msRTCSIP-MaxRoamingDataSubscriptionTimeout (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="1b507-452">この属性は、[移動データサブスクリプションの最大タイムアウト] ウィンドウを表します。</span><span class="sxs-lookup"><span data-stu-id="1b507-452">This attribute represents the maximum roaming data subscriptions time-out window.</span></span></p></td>
<td><p><span data-ttu-id="1b507-453">Lync Server 2010 では廃止されました。</span><span class="sxs-lookup"><span data-stu-id="1b507-453">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b507-454">msRTCSIP-MCUData</span><span class="sxs-lookup"><span data-stu-id="1b507-454">msRTCSIP-MCUData</span></span></p></td>
<td><p><span data-ttu-id="1b507-455">この属性は、今後の使用のために予約されています。</span><span class="sxs-lookup"><span data-stu-id="1b507-455">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="1b507-456">Office Communications Server 2007 の新製品。</span><span class="sxs-lookup"><span data-stu-id="1b507-456">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b507-457">msRTCSIP-Msrtcsip-mcufactoryaddress です</span><span class="sxs-lookup"><span data-stu-id="1b507-457">msRTCSIP-MCUFactoryAddress</span></span></p></td>
<td><p><span data-ttu-id="1b507-458">この属性は、属している multipoint control unit (MCU) ファクトリへのリンクを指定するコンピュータークラス下のサービスコントロールポイント属性です。</span><span class="sxs-lookup"><span data-stu-id="1b507-458">This attribute is a service control point attribute under the computer class that specifies a link back to the multipoint control unit (MCU) Factory to which it belongs.</span></span> <span data-ttu-id="1b507-459">このサービスコントロールポイントと属性は、Microsoft MCU ごとに作成されます。</span><span class="sxs-lookup"><span data-stu-id="1b507-459">This service control point and attribute is created for every Microsoft MCU.</span></span> <span data-ttu-id="1b507-460">各 Microsoft MCU は、プールレベルの設定を取得するために、属しているプールのバックエンドサーバーを検索する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1b507-460">Each Microsoft MCU must find the Back End Server of the pool to which it belongs, in order to retrieve pool-level settings from it.</span></span></p>
<p><span data-ttu-id="1b507-461">この属性の値は、MCU ファクトリの識別名 (DN) です。</span><span class="sxs-lookup"><span data-stu-id="1b507-461">The value of this attribute is the distinguished name (DN) of the MCU Factory.</span></span> <span data-ttu-id="1b507-462">これは単一値の属性で、グローバルカタログレプリケーションのマークが付けられています。</span><span class="sxs-lookup"><span data-stu-id="1b507-462">This is a single-valued attribute and marked for global catalog replication.</span></span></p>
<p><span data-ttu-id="1b507-463">前方リンク: <strong>リンク ID 11026</strong></span><span class="sxs-lookup"><span data-stu-id="1b507-463">Forward link: <strong>Link ID 11026</strong></span></span></p>
<p><span data-ttu-id="1b507-464">この転送リンク属性への対応する後方リンクは、 <strong>msRTCSIP</strong>ともなります。</span><span class="sxs-lookup"><span data-stu-id="1b507-464">The corresponding back link to this forward link attribute is <strong>msRTCSIP-MCUServers</strong>.</span></span></p></td>
<td><p><span data-ttu-id="1b507-465">Office Communications Server 2007 の新製品。</span><span class="sxs-lookup"><span data-stu-id="1b507-465">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b507-466">msRTCSIP-MCUFactoryData</span><span class="sxs-lookup"><span data-stu-id="1b507-466">msRTCSIP-MCUFactoryData</span></span></p></td>
<td><p><span data-ttu-id="1b507-467">これは複数文字列の予約済み属性です。</span><span class="sxs-lookup"><span data-stu-id="1b507-467">This is a multi-string reserved attribute.</span></span> <span data-ttu-id="1b507-468">この属性に格納されている設定は、名前 = 値のペアとして表されます。</span><span class="sxs-lookup"><span data-stu-id="1b507-468">Settings stored in this attribute are represented as name=value pairs.</span></span> <span data-ttu-id="1b507-469">現在定義されている名前 = 値のペアは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="1b507-469">Currently defined name=value pairs are:</span></span></p>
<ul>
<li><p><span data-ttu-id="1b507-470">FactoryURL = &lt; URL&gt;</span><span class="sxs-lookup"><span data-stu-id="1b507-470">FactoryURL = &lt;URL&gt;</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="1b507-471">Office Communications Server 2007 の新製品。</span><span class="sxs-lookup"><span data-stu-id="1b507-471">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b507-472">msRTCSIP-Msrtcsip-mcufactorypath</span><span class="sxs-lookup"><span data-stu-id="1b507-472">msRTCSIP-MCUFactoryPath</span></span></p></td>
<td><p><span data-ttu-id="1b507-473">これは、プールに関連付けられた1つの MCU ファクトリの識別名 (DN) を含む単一値の属性です。</span><span class="sxs-lookup"><span data-stu-id="1b507-473">This is a single-valued attribute that contains the distinguished name (DN) of a single MCU factory associated with a pool.</span></span></p>
<p><span data-ttu-id="1b507-474">前方リンク: <strong>リンク ID 11024</strong></span><span class="sxs-lookup"><span data-stu-id="1b507-474">Forward link: <strong>Link ID 11024</strong></span></span></p>
<p><span data-ttu-id="1b507-475">この転送リンク属性への対応する後方リンクは、 <strong>MsRTCSIP アドレス</strong>です。</span><span class="sxs-lookup"><span data-stu-id="1b507-475">The corresponding back link to this forward link attribute is <strong>msRTCSIP-PoolAddresses</strong>.</span></span></p></td>
<td><p><span data-ttu-id="1b507-476">Office Communications Server 2007 の新製品。</span><span class="sxs-lookup"><span data-stu-id="1b507-476">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b507-477">msRTCSIP-MCUFactoryProviderID</span><span class="sxs-lookup"><span data-stu-id="1b507-477">msRTCSIP-MCUFactoryProviderID</span></span></p></td>
<td><p><span data-ttu-id="1b507-478">この属性は、MCU ファクトリプロバイダーの GUID を指定する単一値の文字列です。</span><span class="sxs-lookup"><span data-stu-id="1b507-478">This attribute is a single-valued string that specifies the GUID of the MCU factory provider.</span></span> <span data-ttu-id="1b507-479">この GUID 値に基づいて、MCU ファクトリプロセスは、この MCU の種類をサービスするかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="1b507-479">Based on the GUID value, the MCU factory process determines whether to service this MCU type.</span></span> <span data-ttu-id="1b507-480">GUID 値が <strong>{F0810510-424F-46ef-84FE-6CC720DF1791}</strong>の場合、MCU ファクトリプロセス (Lync Server では既定で利用可能) によって処理されます。</span><span class="sxs-lookup"><span data-stu-id="1b507-480">If the GUID value is <strong>{F0810510-424F-46ef-84FE-6CC720DF1791}</strong>, then the MCU factory process (available by default in Lync Server) will process it.</span></span> <span data-ttu-id="1b507-481">その他の GUID 値の場合、MCU ファクトリプロセスは MCU の種類をサービスしません。</span><span class="sxs-lookup"><span data-stu-id="1b507-481">For any other GUID value, the MCU factory process will not service the MCU type.</span></span></p></td>
<td><p><span data-ttu-id="1b507-482">Office Communications Server 2007 の新製品。</span><span class="sxs-lookup"><span data-stu-id="1b507-482">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b507-483">msRTCSIP-MCUServers ユーザー</span><span class="sxs-lookup"><span data-stu-id="1b507-483">msRTCSIP-MCUServers</span></span></p></td>
<td><p><span data-ttu-id="1b507-484">この属性は、複数値を持つ識別名 (DN) のリストです。</span><span class="sxs-lookup"><span data-stu-id="1b507-484">This attribute is a multi-valued list of distinguished names (DN).</span></span> <span data-ttu-id="1b507-485">この属性には、この MCU ファクトリに関連付けられている同じ種類およびベンダーのすべての MCU サーバーの一覧が含まれています。</span><span class="sxs-lookup"><span data-stu-id="1b507-485">This attribute contains a list of all MCU servers of the same type and vendor associated with this MCU factory.</span></span> <span data-ttu-id="1b507-486">各セグメントの有効な値は、63文字です。FQDN 全体の有効な値は255文字です。</span><span class="sxs-lookup"><span data-stu-id="1b507-486">The valid value for each segment is 63 characters; the valid value for the entire FQDN is 255 characters.</span></span></p>
<p><span data-ttu-id="1b507-487">後方リンク: リンク ID 11027</span><span class="sxs-lookup"><span data-stu-id="1b507-487">Back link: Link ID 11027</span></span></p>
<p><span data-ttu-id="1b507-488">この後方リンクへの対応する転送リンクは、 <strong>msRTCSIP-msrtcsip-mcufactoryaddress です</strong>です。</span><span class="sxs-lookup"><span data-stu-id="1b507-488">The corresponding forward link to this back link is <strong>msRTCSIP-MCUFactoryAddress</strong>.</span></span></p></td>
<td><p><span data-ttu-id="1b507-489">Office Communications Server 2007 の新製品。</span><span class="sxs-lookup"><span data-stu-id="1b507-489">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b507-490">msRTCSIP-MCUType</span><span class="sxs-lookup"><span data-stu-id="1b507-490">msRTCSIP-MCUType</span></span></p></td>
<td><p><span data-ttu-id="1b507-491">この属性は、MCU が処理できるメディアを指定する単一値の文字列です。</span><span class="sxs-lookup"><span data-stu-id="1b507-491">This attribute is a single-valued string that specifies the medium the MCU can handle.</span></span></p>
<p><span data-ttu-id="1b507-492">サポートされている有効な種類は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="1b507-492">Supported valid types are:</span></span></p>
<ul>
<li><p><span data-ttu-id="1b507-493">定期的</span><span class="sxs-lookup"><span data-stu-id="1b507-493">meeting</span></span></p></li>
<li><p><span data-ttu-id="1b507-494">音声ビデオ</span><span class="sxs-lookup"><span data-stu-id="1b507-494">audio-video</span></span></p></li>
<li><p><span data-ttu-id="1b507-495">チャット</span><span class="sxs-lookup"><span data-stu-id="1b507-495">chat</span></span></p></li>
<li><p><span data-ttu-id="1b507-496">電話-conf</span><span class="sxs-lookup"><span data-stu-id="1b507-496">phone-conf</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="1b507-497">Office Communications Server 2007 の新製品。</span><span class="sxs-lookup"><span data-stu-id="1b507-497">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b507-498">msRTCSIP-MCUVendor</span><span class="sxs-lookup"><span data-stu-id="1b507-498">msRTCSIP-MCUVendor</span></span></p></td>
<td><p><span data-ttu-id="1b507-499">この属性は、MCU ベンダーの名前を指定する単一値の文字列です。</span><span class="sxs-lookup"><span data-stu-id="1b507-499">This attribute is a single-valued string that specifies an MCU vendor’s name.</span></span> <span data-ttu-id="1b507-500">すべての Microsoft Mcu は、この属性を <strong>Microsoft Corporation</strong>に指定します。</span><span class="sxs-lookup"><span data-stu-id="1b507-500">All Microsoft MCUs will specify this attribute to be <strong>Microsoft Corporation</strong>.</span></span></p></td>
<td><p><span data-ttu-id="1b507-501">Office Communications Server 2007 の新製品。</span><span class="sxs-lookup"><span data-stu-id="1b507-501">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b507-502">msRTCSIP-会議フラグ (不使用)</span><span class="sxs-lookup"><span data-stu-id="1b507-502">msRTCSIP-MeetingFlags (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="1b507-503">この属性は、すべてのユーザーまたは連絡先オブジェクトに対してグローバルに有効になる、さまざまな会議オプションを定義します。</span><span class="sxs-lookup"><span data-stu-id="1b507-503">This attribute defines different meeting options that are enabled globally for all users or contact objects.</span></span> <span data-ttu-id="1b507-504">この属性は、整数型のビットマスク値です。</span><span class="sxs-lookup"><span data-stu-id="1b507-504">This attribute is a bit-mask value of integer type.</span></span></p>
<p><span data-ttu-id="1b507-505">有効な値 (および関連するビット位置) は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="1b507-505">The valid values (and associated bit positions) are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="1b507-506">0: AllowOrganizeMeetingWithAnonymousParticipants が None (会議への匿名ユーザーの招待をユーザーに許可しない) (ビットが設定されていない)</span><span class="sxs-lookup"><span data-stu-id="1b507-506">0: AllowOrganizeMeetingWithAnonymousParticipants is None (do not allow users to invite anonymous users to meetings) (no bits set)</span></span></p></li>
<li><p><span data-ttu-id="1b507-507">4: AllowOrganizeMeetingWithAnonymousParticipants はすべてのユーザー (すべてのユーザーが、会議への匿名ユーザーの招待を許可する) (ビット位置 2)</span><span class="sxs-lookup"><span data-stu-id="1b507-507">4: AllowOrganizeMeetingWithAnonymousParticipants is Everyone (allow all users to invite anonymous users to meetings) (bit position 2)</span></span></p></li>
<li><p><span data-ttu-id="1b507-508">8: AllowOrganizeMeetingWithAnonymousParticipants が UsePerUserSetting (ユーザーごとの設定に基づいてユーザーに匿名ユーザーの会議への招待を許可する) (ビット位置 3)</span><span class="sxs-lookup"><span data-stu-id="1b507-508">8: AllowOrganizeMeetingWithAnonymousParticipants is UsePerUserSetting (allow users to invite anonymous users to meetings based on per user setting) (bit position 3)</span></span></p></li>
<li><p><span data-ttu-id="1b507-509">16: Userperusermeeting Policy (ユーザーごとに会議ポリシーが定義されます) (ビット位置 4)</span><span class="sxs-lookup"><span data-stu-id="1b507-509">16: UserPerUserMeetingPolicy (meeting policy is defined per user) (bit position 4)</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="1b507-510">Office Communications Server 2007 の新製品。</span><span class="sxs-lookup"><span data-stu-id="1b507-510">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="1b507-511">Lync Server 2010 では廃止されました。</span><span class="sxs-lookup"><span data-stu-id="1b507-511">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b507-512">msRTCSIP-会議ポリシー (不使用)</span><span class="sxs-lookup"><span data-stu-id="1b507-512">msRTCSIP-MeetingPolicy (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="1b507-513">この属性は、管理者がこのユーザーに割り当てたポリシーの識別名 (DN) を単一値属性として指定します。</span><span class="sxs-lookup"><span data-stu-id="1b507-513">This attribute specifies the distinguished name (DN) of the policy the administrator has assigned for this user as a single-valued attribute.</span></span></p></td>
<td><p><span data-ttu-id="1b507-514">Office Communications Server 2007 の新製品。</span><span class="sxs-lookup"><span data-stu-id="1b507-514">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="1b507-515">Lync Server 2010 では廃止されました。</span><span class="sxs-lookup"><span data-stu-id="1b507-515">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b507-516">msRTCSIP-Msrtcsip-minpresencesubscriptiontimeout (現在不使用)</span><span class="sxs-lookup"><span data-stu-id="1b507-516">msRTCSIP-MinPresenceSubscriptionTimeout (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="1b507-517">この属性は、最小プレゼンスサブスクリプションタイムアウト期間を表します。</span><span class="sxs-lookup"><span data-stu-id="1b507-517">This attribute represents the minimum presence subscription time-out window.</span></span></p></td>
<td><p><span data-ttu-id="1b507-518">Lync Server 2010 では廃止されました。</span><span class="sxs-lookup"><span data-stu-id="1b507-518">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b507-519">msRTCSIP-MinRegistrationTimeout (obsolete)</span><span class="sxs-lookup"><span data-stu-id="1b507-519">msRTCSIP-MinRegistrationTimeout (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="1b507-520">この属性は、最小登録タイムアウト時間枠を表します。</span><span class="sxs-lookup"><span data-stu-id="1b507-520">This attribute represents the minimum registration time-out window.</span></span></p></td>
<td><p><span data-ttu-id="1b507-521">Office Communications Server 2007 の新製品。</span><span class="sxs-lookup"><span data-stu-id="1b507-521">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="1b507-522">Lync Server 2010 では廃止されました。</span><span class="sxs-lookup"><span data-stu-id="1b507-522">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b507-523">msRTCSIP-Msrtcsip-minroamingdatasubscriptiontimeout (現在不使用)</span><span class="sxs-lookup"><span data-stu-id="1b507-523">msRTCSIP-MinRoamingDataSubscriptionTimeout (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="1b507-524">この属性は、移動データサブスクリプションタイムアウト期間の最小値を表します。</span><span class="sxs-lookup"><span data-stu-id="1b507-524">This attribute represents the minimum roaming data subscription time-out window.</span></span></p></td>
<td><p><span data-ttu-id="1b507-525">Office Communications Server 2007 の新製品。</span><span class="sxs-lookup"><span data-stu-id="1b507-525">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="1b507-526">Lync Server 2010 では廃止されました。</span><span class="sxs-lookup"><span data-stu-id="1b507-526">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b507-527">msRTCSIP-MirrorBackEndServer</span><span class="sxs-lookup"><span data-stu-id="1b507-527">msRTCSIP-MirrorBackEndServer</span></span></p></td>
<td><p><span data-ttu-id="1b507-528">この属性は、フロントエンドプールで使用されるミラーリングされた SQL Server バックエンドを格納するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="1b507-528">This attribute is used to store the mirrored SQL Server backend used by the Front End pool.</span></span></p></td>
<td><p><span data-ttu-id="1b507-529">Lync Server 2013 の新。</span><span class="sxs-lookup"><span data-stu-id="1b507-529">New in Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b507-530">msRTCSIP-MobilityFlags</span><span class="sxs-lookup"><span data-stu-id="1b507-530">msRTCSIP-MobilityFlags</span></span></p></td>
<td><p><span data-ttu-id="1b507-531">この属性には、モビリティ設定を定義するオプションとフラグが含まれています。</span><span class="sxs-lookup"><span data-stu-id="1b507-531">This attribute contains options and flags that define mobility settings.</span></span></p></td>
<td><p><span data-ttu-id="1b507-532">Office Communications Server 2007 R2 の新製品。</span><span class="sxs-lookup"><span data-stu-id="1b507-532">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b507-533">msRTCSIP-MobilityPolicy</span><span class="sxs-lookup"><span data-stu-id="1b507-533">msRTCSIP-MobilityPolicy</span></span></p></td>
<td><p><span data-ttu-id="1b507-534">モビリティポリシーオブジェクトの DN を含む属性です。</span><span class="sxs-lookup"><span data-stu-id="1b507-534">This attribute contains the DN for a mobility policy object.</span></span></p></td>
<td><p><span data-ttu-id="1b507-535">Office Communications Server 2007 R2 の新製品。</span><span class="sxs-lookup"><span data-stu-id="1b507-535">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b507-536">msRTCSIP-Msrtcsip-numdevicesperuser (現在不使用)</span><span class="sxs-lookup"><span data-stu-id="1b507-536">msRTCSIP-NumDevicesPerUser (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="1b507-537">ユーザーが SIP コミュニケーション用に登録し、プレゼンスにサブスクライブできるデバイスの許容数を表す属性です。</span><span class="sxs-lookup"><span data-stu-id="1b507-537">This attribute represents the allowed number of devices on which a user can register for SIP communications and subscribe to presence.</span></span></p></td>
<td><p><span data-ttu-id="1b507-538">Office Communications Server 2007 の新製品。</span><span class="sxs-lookup"><span data-stu-id="1b507-538">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="1b507-539">Lync Server 2010 では廃止されました。</span><span class="sxs-lookup"><span data-stu-id="1b507-539">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b507-540">msRTCSIP-OptionFlags</span><span class="sxs-lookup"><span data-stu-id="1b507-540">msRTCSIP-OptionFlags</span></span></p></td>
<td><p><span data-ttu-id="1b507-541">この属性は、ユーザーまたは連絡先オブジェクトに対して有効になっているオプションを指定します。</span><span class="sxs-lookup"><span data-stu-id="1b507-541">This attribute specifies the options that are enabled for the user or contact object.</span></span> <span data-ttu-id="1b507-542">この属性は、integer 型のビットマスク値です。</span><span class="sxs-lookup"><span data-stu-id="1b507-542">This attribute is a bit-mask value of type integer.</span></span> <span data-ttu-id="1b507-543">各オプションはビットで表されます。</span><span class="sxs-lookup"><span data-stu-id="1b507-543">Each option is represented by a bit.</span></span> <span data-ttu-id="1b507-544">この属性には、グローバルカタログレプリケーションのマークが付いています。</span><span class="sxs-lookup"><span data-stu-id="1b507-544">This attribute is marked for global catalog replication.</span></span></p>
<p><span data-ttu-id="1b507-545">有効な値 (および関連するビット位置) は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="1b507-545">The valid values (and associated bit positions) are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="1b507-546">1: パブリックインスタントメッセージング (IM) 接続が有効 (ビット位置 0)</span><span class="sxs-lookup"><span data-stu-id="1b507-546">1: Enabled for public instant messaging (IM) connectivity (bit position 0)</span></span></p></li>
<li><p><span data-ttu-id="1b507-547">2: 予約済み (ビット位置 1)</span><span class="sxs-lookup"><span data-stu-id="1b507-547">2: Reserved (bit position 1)</span></span></p></li>
<li><p><span data-ttu-id="1b507-548">4: 予約済み (ビット位置 2)</span><span class="sxs-lookup"><span data-stu-id="1b507-548">4: Reserved (bit position 2)</span></span></p></li>
<li><p><span data-ttu-id="1b507-549">8: 予約済み (ビット位置 3)</span><span class="sxs-lookup"><span data-stu-id="1b507-549">8: Reserved (bit position 3)</span></span></p></li>
<li><p><span data-ttu-id="1b507-550">16: リモート通話コントロールが有効 [テレフォニー] (ビット位置 4)</span><span class="sxs-lookup"><span data-stu-id="1b507-550">16: Remote call control Enabled [Telephony] (bit position 4)</span></span></p></li>
<li><p><span data-ttu-id="1b507-551">64: AllowOrganizeMeetingWithAnonymousParticipants (ユーザーが匿名ユーザーを会議に招待できるようにする (ビット位置 6)</span><span class="sxs-lookup"><span data-stu-id="1b507-551">64: AllowOrganizeMeetingWithAnonymousParticipants (allow users to invite anonymous users to meetings (bit position 6)</span></span></p></li>
<li><p><span data-ttu-id="1b507-552">128: UCEnabled (UC に対してユーザーを有効にする) (ビット位置 7)</span><span class="sxs-lookup"><span data-stu-id="1b507-552">128: UCEnabled (enable users for UC) (bit position 7)</span></span></p></li>
<li><p><span data-ttu-id="1b507-553">256: EnabledForEnhancedPresence (ユーザーに対してパブリック IM 接続を有効にする) (ビット位置 8)</span><span class="sxs-lookup"><span data-stu-id="1b507-553">256: EnabledForEnhancedPresence (enable user for public IM connectivity) (bit position 8)</span></span></p></li>
<li><p><span data-ttu-id="1b507-554">512: RemoteCallControlDualMode (ビット位置 9)</span><span class="sxs-lookup"><span data-stu-id="1b507-554">512: RemoteCallControlDualMode (bit position 9)</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="1b507-555">Live Communications Server 2005 SP1 で導入されています。</span><span class="sxs-lookup"><span data-stu-id="1b507-555">New in Live Communications Server 2005 with SP1.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b507-556">msRTCSIP-の場合は、Sid</span><span class="sxs-lookup"><span data-stu-id="1b507-556">msRTCSIP-OriginatorSID</span></span></p></td>
<td><p><span data-ttu-id="1b507-557">この属性は、ユーザーの ObjectSID が Windows NT Server プリンシパルアカウントから、リソースまたは中央フォレスト内の対応するユーザーまたは連絡先オブジェクトの属性にコピーされるときにシングルサインオンを有効にするために、リソースおよび中央フォレストのトポロジで使用されます。</span><span class="sxs-lookup"><span data-stu-id="1b507-557">This attribute is used in resource and central forest topologies to enable single sign-on when a user’s ObjectSID from the Windows NT Server principal account is copied into this attribute of the corresponding user or contact object in the resource or central forest.</span></span> <span data-ttu-id="1b507-558">Communicator Web Access は、この属性またはユーザーの ObjectSID を使用して、AD DS 内のユーザーを検索します。</span><span class="sxs-lookup"><span data-stu-id="1b507-558">Communicator Web Access searches for a user in AD DS using this attribute or the user’s ObjectSID.</span></span> <span data-ttu-id="1b507-559">この属性には、グローバルカタログレプリケーションのマークが付いています。</span><span class="sxs-lookup"><span data-stu-id="1b507-559">This attribute is marked for global catalog replication.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b507-560">msRTCSIP-OwnerUrn</span><span class="sxs-lookup"><span data-stu-id="1b507-560">msRTCSIP-OwnerUrn</span></span></p></td>
<td><p><span data-ttu-id="1b507-561">この属性は、アプリケーション連絡先の所有者の Uniform Resource Name (URN) です。</span><span class="sxs-lookup"><span data-stu-id="1b507-561">This attribute is the Uniform Resource Name (URN) of the owner for an application contact.</span></span></p></td>
<td><p><span data-ttu-id="1b507-562">Lync Server 2010 の新。</span><span class="sxs-lookup"><span data-stu-id="1b507-562">New in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b507-563">msRTCSIP-パターン (obsolete)</span><span class="sxs-lookup"><span data-stu-id="1b507-563">msRTCSIP-Pattern (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="1b507-564">この単一値の文字列属性には、ダイヤル番号を e.164 形式に一致させるために使用するパターンが含まれています。</span><span class="sxs-lookup"><span data-stu-id="1b507-564">This single-valued string attribute contains a pattern used for matching dial numbers into E.164 format.</span></span> <span data-ttu-id="1b507-565">ダイヤル番号がこのパターンと一致する場合は、ダイヤル番号に変換が適用されます。</span><span class="sxs-lookup"><span data-stu-id="1b507-565">If the dial number matches this pattern, the translation is applied to the dialed number.</span></span></p></td>
<td><p><span data-ttu-id="1b507-566">Office Communications Server 2007 の新製品。</span><span class="sxs-lookup"><span data-stu-id="1b507-566">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="1b507-567">Lync Server 2010 では廃止されました。</span><span class="sxs-lookup"><span data-stu-id="1b507-567">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b507-568">msRTCSIP-Msrtcsip-phoneroutebl です (現在不使用)</span><span class="sxs-lookup"><span data-stu-id="1b507-568">msRTCSIP-PhoneRouteBL (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="1b507-569">この複数値属性には、電話ルート識別名 (DN) の一覧が含まれています。</span><span class="sxs-lookup"><span data-stu-id="1b507-569">This multi-valued attribute contains a list of phone route distinguished names (DN).</span></span> <span data-ttu-id="1b507-570">この属性は、1つまたは複数の電話ルートへの後方リンクを指定します。</span><span class="sxs-lookup"><span data-stu-id="1b507-570">This attribute specifies the back link to one or more phone routes.</span></span></p>
<p><span data-ttu-id="1b507-571">後方リンク: <strong>リンク ID 11033</strong></span><span class="sxs-lookup"><span data-stu-id="1b507-571">Back link: <strong>Link ID 11033</strong></span></span></p>
<p><span data-ttu-id="1b507-572">この属性は、Msrtcsip-routeusagelinks の前方リンク <strong>msRTCSIP</strong>に対応します。</span><span class="sxs-lookup"><span data-stu-id="1b507-572">This attribute corresponds to the forward link <strong>msRTCSIP-RouteUsageLinks</strong>.</span></span></p></td>
<td><p><span data-ttu-id="1b507-573">Office Communications Server 2007 の新製品。</span><span class="sxs-lookup"><span data-stu-id="1b507-573">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="1b507-574">Lync Server 2010 では廃止されました。</span><span class="sxs-lookup"><span data-stu-id="1b507-574">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b507-575">msRTCSIP-Msrtcsip-phoneroutedata (現在不使用)</span><span class="sxs-lookup"><span data-stu-id="1b507-575">msRTCSIP-PhoneRouteData (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="1b507-576">この属性は、今後の使用のために予約されています。</span><span class="sxs-lookup"><span data-stu-id="1b507-576">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="1b507-577">Lync Server 2010 では廃止されました。</span><span class="sxs-lookup"><span data-stu-id="1b507-577">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b507-578">msRTCSIP-Msrtcsip-phoneroutename (現在不使用)</span><span class="sxs-lookup"><span data-stu-id="1b507-578">msRTCSIP-PhoneRouteName (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="1b507-579">この単一値の UNICODE 文字列属性は、電話ルートのフレンドリ名を指定します。これにより、管理者が簡単に参照できるようになります。</span><span class="sxs-lookup"><span data-stu-id="1b507-579">This single valued UNICODE string attribute specifies the friendly name of the phone route, so it can easily be referenced by the administrator.</span></span></p></td>
<td><p><span data-ttu-id="1b507-580">Lync Server 2010 では廃止されました。</span><span class="sxs-lookup"><span data-stu-id="1b507-580">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b507-581">msRTCSIP-電話での使用データ (obsolete)</span><span class="sxs-lookup"><span data-stu-id="1b507-581">msRTCSIP-PhoneUsageData (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="1b507-582">この属性は、今後の使用のために予約されています。</span><span class="sxs-lookup"><span data-stu-id="1b507-582">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="1b507-583">Office Communications Server 2007 の新製品。</span><span class="sxs-lookup"><span data-stu-id="1b507-583">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="1b507-584">Lync Server 2010 では廃止されました。</span><span class="sxs-lookup"><span data-stu-id="1b507-584">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b507-585">msRTCSIP-PolicyContent (現在不使用)</span><span class="sxs-lookup"><span data-stu-id="1b507-585">msRTCSIP-PolicyContent (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="1b507-586">この属性は、単一の値を持つ Unicode 文字列です。</span><span class="sxs-lookup"><span data-stu-id="1b507-586">This attribute is a single-valued Unicode string.</span></span> <span data-ttu-id="1b507-587">この文字列属性には、ポリシー定義が XML 形式で含まれています。</span><span class="sxs-lookup"><span data-stu-id="1b507-587">This string attribute contains the policy definition in XML format.</span></span> <span data-ttu-id="1b507-588">XML スキーマ定義はさまざまなポリシーの種類に共通していますが、ポリシーの種類ごとに設定のみが異なります。</span><span class="sxs-lookup"><span data-stu-id="1b507-588">The XML schema definition is common across different policy types, only the settings are different for each policy type.</span></span></p>
<p><span data-ttu-id="1b507-589">XML スキーマ定義 (XSD) は次のように定義されています。</span><span class="sxs-lookup"><span data-stu-id="1b507-589">The XML schema definition (XSD) is defined as follows:</span></span></p>
<pre><code>&lt;?xml version=&quot;1.0&quot; encoding=&quot;utf-8&quot;?&gt;
&lt;xs:schema id=&quot;instance&quot; xmlns=&quot;&quot; xmlns:xs=&quot;http://www.w3.org/2001/XMLSchema&quot; xmlns:msdata=&quot;urn:schemas-microsoft-com:xml-msdata&quot;&gt;
  &lt;xs:element name=&quot;instance&quot; msdata:IsDataSet=&quot;true&quot;&gt;
    &lt;xs:complexType&gt;
      &lt;xs:choice maxOccurs=&quot;unbounded&quot;&gt;
        &lt;xs:element name=&quot;property&quot; nillable=&quot;true&quot;&gt;
          &lt;xs:complexType&gt;
            &lt;xs:simpleContent msdata:ColumnName=&quot;property_Text&quot; msdata:Ordinal=&quot;1&quot;&gt;
              &lt;xs:extension base=&quot;xs:string&quot;&gt;
                &lt;xs:attribute name=&quot;name&quot; type=&quot;xs:string&quot; /&gt;
              &lt;/xs:extension&gt;
            &lt;/xs:simpleContent&gt;
          &lt;/xs:complexType&gt;
        &lt;/xs:element&gt;
      &lt;/xs:choice&gt;
    &lt;/xs:complexType&gt;
  &lt;/xs:element&gt;
&lt;/xs:schema&gt;</code></pre></td>
<td><p><span data-ttu-id="1b507-590">Office Communications Server 2007 の新製品。</span><span class="sxs-lookup"><span data-stu-id="1b507-590">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="1b507-591">Lync Server 2010 では廃止されました。</span><span class="sxs-lookup"><span data-stu-id="1b507-591">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b507-592">msRTCSIP-PolicyData (現在不使用)</span><span class="sxs-lookup"><span data-stu-id="1b507-592">msRTCSIP-PolicyData (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="1b507-593">この属性は、今後の使用のために予約されています。</span><span class="sxs-lookup"><span data-stu-id="1b507-593">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="1b507-594">Office Communications Server 2007 の新製品。</span><span class="sxs-lookup"><span data-stu-id="1b507-594">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="1b507-595">Lync Server 2010 では廃止されました。</span><span class="sxs-lookup"><span data-stu-id="1b507-595">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b507-596">msRTCSIP-Msrtcsip-policytype (現在不使用)</span><span class="sxs-lookup"><span data-stu-id="1b507-596">msRTCSIP-PolicyType (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="1b507-597">この単一値の Unicode 文字列属性には、ポリシーの種類が含まれています。</span><span class="sxs-lookup"><span data-stu-id="1b507-597">This single-valued Unicode string attribute contains the policy type.</span></span> <span data-ttu-id="1b507-598">有効なポリシーの種類は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="1b507-598">Valid policy types are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="1b507-599">定期的</span><span class="sxs-lookup"><span data-stu-id="1b507-599">meeting</span></span></p></li>
<li><p><span data-ttu-id="1b507-600">網</span><span class="sxs-lookup"><span data-stu-id="1b507-600">telephony</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="1b507-601">Office Communications Server 2007 の新製品。</span><span class="sxs-lookup"><span data-stu-id="1b507-601">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="1b507-602">Lync Server 2010 では廃止されました。</span><span class="sxs-lookup"><span data-stu-id="1b507-602">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b507-603">msRTCSIP-PoolAddress</span><span class="sxs-lookup"><span data-stu-id="1b507-603">msRTCSIP-PoolAddress</span></span></p></td>
<td><p><span data-ttu-id="1b507-604">この属性は、コンピューターが属するプールに戻るリンクを指定します。</span><span class="sxs-lookup"><span data-stu-id="1b507-604">This attribute specifies a link back to the pool to which a computer belongs.</span></span> <span data-ttu-id="1b507-605">この属性は、コンピューターでの Lync Server の Standard Edition または Enterprise Edition のどちらが実行されているかに関係なく設定されます。</span><span class="sxs-lookup"><span data-stu-id="1b507-605">This attribute is set regardless of whether the computer is running the Standard Edition or the Enterprise Edition of Lync Server.</span></span> <span data-ttu-id="1b507-606">この属性には、グローバルカタログレプリケーションのマークが付いています。</span><span class="sxs-lookup"><span data-stu-id="1b507-606">This attribute is marked for global catalog replication.</span></span></p>
<p><span data-ttu-id="1b507-607">有効な値はプールのドメイン名です。</span><span class="sxs-lookup"><span data-stu-id="1b507-607">The valid value is the domain name of the pool.</span></span></p>
<p><span data-ttu-id="1b507-608">前方リンク: <strong>リンク ID 11022</strong></span><span class="sxs-lookup"><span data-stu-id="1b507-608">Forward link: <strong>Link ID 11022</strong></span></span></p>
<p><span data-ttu-id="1b507-609">この転送リンク属性への対応する後方リンクは、 <strong>msRTCSIP-FrontEndServers</strong>です。</span><span class="sxs-lookup"><span data-stu-id="1b507-609">The corresponding back link to this forward link attribute is <strong>msRTCSIP-FrontEndServers</strong>.</span></span></p></td>
<td><p><span data-ttu-id="1b507-610">Live Communications Server 2005 の新しいもの。</span><span class="sxs-lookup"><span data-stu-id="1b507-610">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b507-611">msRTCSIP-PoolAddresses</span><span class="sxs-lookup"><span data-stu-id="1b507-611">msRTCSIP-PoolAddresses</span></span></p></td>
<td><p><span data-ttu-id="1b507-612">これは、MCU ファクトリが関連付けられているプールの識別名 (DN) のリストを含む複数値の属性です。</span><span class="sxs-lookup"><span data-stu-id="1b507-612">This is a multi-valued attribute that contains a list of the distinguished names (DN) of pools with which the MCU factory is associated.</span></span></p>
<p><span data-ttu-id="1b507-613">後方リンク: <strong>リンク ID 11025</strong></span><span class="sxs-lookup"><span data-stu-id="1b507-613">Back link: <strong>Link ID 11025</strong></span></span></p>
<p><span data-ttu-id="1b507-614">この後方リンクへの対応する転送リンクは、 <strong>msRTCSIP-msrtcsip-mcufactorypath</strong>です。</span><span class="sxs-lookup"><span data-stu-id="1b507-614">The corresponding forward link to this back link is <strong>msRTCSIP-MCUFactoryPath</strong>.</span></span></p></td>
<td><p><span data-ttu-id="1b507-615">Office Communications Server 2007 の新製品。</span><span class="sxs-lookup"><span data-stu-id="1b507-615">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b507-616">msRTCSIP-PoolData</span><span class="sxs-lookup"><span data-stu-id="1b507-616">msRTCSIP-PoolData</span></span></p></td>
<td><p><span data-ttu-id="1b507-617">この属性は、今後の使用のために予約されています。</span><span class="sxs-lookup"><span data-stu-id="1b507-617">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="1b507-618">Live Communications Server 2005 SP1 で導入されています。</span><span class="sxs-lookup"><span data-stu-id="1b507-618">New in Live Communications Server 2005 with SP1.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b507-619">msRTCSIP-PoolDisplayName</span><span class="sxs-lookup"><span data-stu-id="1b507-619">msRTCSIP-PoolDisplayName</span></span></p></td>
<td><p><span data-ttu-id="1b507-620">この属性は、管理コンソールによって表示されるプールの任意の名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="1b507-620">This attribute specifies an arbitrary name for a pool that is displayed by the management console.</span></span> <span data-ttu-id="1b507-621">この名前は、管理者が変更できます。</span><span class="sxs-lookup"><span data-stu-id="1b507-621">This name can be changed by the administrator.</span></span></p>
<p><span data-ttu-id="1b507-622">有効な値は、プールの名前を表す文字列です。</span><span class="sxs-lookup"><span data-stu-id="1b507-622">The valid value is a string representing the name of a pool.</span></span></p></td>
<td><p><span data-ttu-id="1b507-623">Live Communications Server 2005 の新しいもの。</span><span class="sxs-lookup"><span data-stu-id="1b507-623">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b507-624">msRTCSIP-PoolDomainFQDN</span><span class="sxs-lookup"><span data-stu-id="1b507-624">msRTCSIP-PoolDomainFQDN</span></span></p></td>
<td><p><span data-ttu-id="1b507-625">この属性は、単一値の文字列型 (string) の値です。</span><span class="sxs-lookup"><span data-stu-id="1b507-625">This attribute is a single-valued string value.</span></span> <span data-ttu-id="1b507-626">この属性の値は、フロントエンドプールが作成された Active Directory ドメイン構造 (ドメインネームシステム (DNS) 名前空間から分離した SIP 名前空間など) に準拠していない FQDN を持つフロントエンドプールを管理者が作成する場合に、プールのドメイン FQDN を表します。</span><span class="sxs-lookup"><span data-stu-id="1b507-626">The value of this attribute, when present, represents the pool’s domain FQDN if the administrator wants to create a Front End pool with an FQDN that does not conform to the Active Directory domain structure in which the Front End pool is created (for example, a SIP namespace disjoined from Domain Name System (DNS) namespace).</span></span></p>
<p><span data-ttu-id="1b507-627">プールが存在する Active Directory ドメインとして、フロントエンドプールのドメイン FQDN をドメイン名部分にマップすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="1b507-627">We recommend that you map the Front End pool domain FQDN to the domain name portion as the Active Directory domain in which the pool resides.</span></span> <span data-ttu-id="1b507-628">そのため、この属性に値が指定されていない場合、フロントエンドプールの FQDN は、 <strong>dnsHostName</strong> 属性によって示される Active Directory ドメイン名構造に既定で設定されます。</span><span class="sxs-lookup"><span data-stu-id="1b507-628">Therefore, when no value is present in this attribute, the Front End pool FQDN will default to the Active Directory domain name structure, as denoted by the <strong>dnsHostName</strong> attribute.</span></span></p></td>
<td><p><span data-ttu-id="1b507-629">Office Communications Server 2007 の新製品。</span><span class="sxs-lookup"><span data-stu-id="1b507-629">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b507-630">msRTCSIP-PoolFunctionality</span><span class="sxs-lookup"><span data-stu-id="1b507-630">msRTCSIP-PoolFunctionality</span></span></p></td>
<td><p><span data-ttu-id="1b507-631">プールに関連付けられたすべての Lync Server、Enterprise Edition サーバーのドメイン名の複数値リスト。</span><span class="sxs-lookup"><span data-stu-id="1b507-631">A multi-valued list of the domain names of all Lync Server, Enterprise Edition servers associated with a pool.</span></span> <span data-ttu-id="1b507-632">Integer 型の属性は、プールがインスタントメッセージング (IM) とプレゼンス、および会議をサポートするかどうかを定義します。</span><span class="sxs-lookup"><span data-stu-id="1b507-632">This attribute of type integer defines whether the pool is capable of instant messaging (IM) and presence, and meetings.</span></span></p>
<p><span data-ttu-id="1b507-633">有効な値の種類は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="1b507-633">The possible valid value types are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="1b507-634">未定義: IM およびプレゼンスサービス (Live Communications Server 2005 および 2003)</span><span class="sxs-lookup"><span data-stu-id="1b507-634">Undefined: IM and Presence Service (Live Communications Server 2005 and 2003)</span></span></p></li>
<li><p><span data-ttu-id="1b507-635">1: IM およびプレゼンスサービス (Lync Server)</span><span class="sxs-lookup"><span data-stu-id="1b507-635">1: IM and Presence Service (Lync Server)</span></span></p></li>
<li><p><span data-ttu-id="1b507-636">2: IM とプレゼンスおよび会議サービス (Lync Server)</span><span class="sxs-lookup"><span data-stu-id="1b507-636">2: IM and Presence and Meeting Service (Lync Server)</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="1b507-637">Office Communications Server 2007 の新製品。</span><span class="sxs-lookup"><span data-stu-id="1b507-637">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b507-638">msRTCSIP-PoolType</span><span class="sxs-lookup"><span data-stu-id="1b507-638">msRTCSIP-PoolType</span></span></p></td>
<td><p><span data-ttu-id="1b507-639">この属性は、サーバープールで Standard Edition サーバーまたは Enterprise Edition サーバーが実行されているかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="1b507-639">This attribute specifies whether a server pool is running Standard Edition server or Enterprise Edition server.</span></span> <span data-ttu-id="1b507-640">この属性は、integer 型のビットマスク値です。</span><span class="sxs-lookup"><span data-stu-id="1b507-640">This attribute is a bit-mask value of type integer.</span></span> <span data-ttu-id="1b507-641">各オプションはビットで表されます。</span><span class="sxs-lookup"><span data-stu-id="1b507-641">Each option is represented by a bit.</span></span></p>
<p><span data-ttu-id="1b507-642">有効な値 (および関連するビット位置) は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="1b507-642">The valid values (and associated bit positions) are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="1b507-643">1: Standard Edition サーバー、ユーザーをホストする (ビット位置 0)</span><span class="sxs-lookup"><span data-stu-id="1b507-643">1: Standard Edition server, hosts users (bit position 0)</span></span></p></li>
<li><p><span data-ttu-id="1b507-644">2: Enterprise Edition サーバー、ユーザーをホストする (ビット位置 1)</span><span class="sxs-lookup"><span data-stu-id="1b507-644">2: Enterprise Edition server, hosts users (bit position 1)</span></span></p></li>
<li><p><span data-ttu-id="1b507-645">4: Standard Edition サーバー、ホストアプリケーション (ビット位置 2)</span><span class="sxs-lookup"><span data-stu-id="1b507-645">4: Standard Edition server, hosts applications (bit position 2)</span></span></p></li>
<li><p><span data-ttu-id="1b507-646">8: Enterprise Edition サーバー、ホストアプリケーション (ビット位置 3)</span><span class="sxs-lookup"><span data-stu-id="1b507-646">8: Enterprise Edition server, hosts applications (bit position 3)</span></span></p></li>
</ul>
<p><span data-ttu-id="1b507-647">Lync Server はアプリケーションのみをホストするプールをサポートしていないため、有効な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="1b507-647">Because Lync Server does not support pools that host only applications, the only valid values are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="1b507-648">5: Standard Edition サーバー、ユーザーとアプリケーションをホストする (ビット位置0および 2)</span><span class="sxs-lookup"><span data-stu-id="1b507-648">5: Standard Edition server, hosts users and applications (bit positions 0 and 2)</span></span></p></li>
<li><p><span data-ttu-id="1b507-649">10: Enterprise Edition サーバー、ユーザーとアプリケーションをホストする (ビット位置1および 3)</span><span class="sxs-lookup"><span data-stu-id="1b507-649">10: Enterprise Edition server, hosts users and applications (bit positions 1 and 3)</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="1b507-650">Live Communications Server 2005 の新しいもの。</span><span class="sxs-lookup"><span data-stu-id="1b507-650">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b507-651">msRTCSIP-PoolVersion</span><span class="sxs-lookup"><span data-stu-id="1b507-651">msRTCSIP-PoolVersion</span></span></p></td>
<td><p><span data-ttu-id="1b507-652">プールバージョンを定義する属性です。</span><span class="sxs-lookup"><span data-stu-id="1b507-652">This attribute defines the pool version.</span></span> <span data-ttu-id="1b507-653">これは、主な製品リリースごとにインクリメントされる整数型です。</span><span class="sxs-lookup"><span data-stu-id="1b507-653">It is an integer type that is incremented with each major product release.</span></span></p>
<p><span data-ttu-id="1b507-654">有効な値の種類は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="1b507-654">The possible valid value types are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="1b507-655">0: Live Communications Server 2003</span><span class="sxs-lookup"><span data-stu-id="1b507-655">0: Live Communications Server 2003</span></span></p></li>
<li><p><span data-ttu-id="1b507-656">1: Live Communications Server 2005</span><span class="sxs-lookup"><span data-stu-id="1b507-656">1: Live Communications Server 2005</span></span></p></li>
<li><p><span data-ttu-id="1b507-657">2: Live Communications Server 2005 SP1</span><span class="sxs-lookup"><span data-stu-id="1b507-657">2: Live Communications Server 2005 with SP1</span></span></p></li>
<li><p><span data-ttu-id="1b507-658">3: Office Communications Server 2007</span><span class="sxs-lookup"><span data-stu-id="1b507-658">3: Office Communications Server 2007</span></span></p></li>
<li><p><span data-ttu-id="1b507-659">4: Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="1b507-659">4: Office Communications Server 2007 R2</span></span></p></li>
<li><p><span data-ttu-id="1b507-660">5: Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="1b507-660">5: Lync Server 2010</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="1b507-661">Live Communications Server 2005 SP1</span><span class="sxs-lookup"><span data-stu-id="1b507-661">Live Communications Server 2005 with SP1.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b507-662">msRTCSIP-PresenceFlags</span><span class="sxs-lookup"><span data-stu-id="1b507-662">msRTCSIP-PresenceFlags</span></span></p></td>
<td><p><span data-ttu-id="1b507-663">この属性には、プレゼンス設定を定義するオプションとフラグが含まれます。</span><span class="sxs-lookup"><span data-stu-id="1b507-663">This attribute contains options and flags that define presence settings.</span></span></p></td>
<td><p><span data-ttu-id="1b507-664">Office Communications Server 2007 R2 の新製品。</span><span class="sxs-lookup"><span data-stu-id="1b507-664">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b507-665">msRTCSIP-PresencePolicy</span><span class="sxs-lookup"><span data-stu-id="1b507-665">msRTCSIP-PresencePolicy</span></span></p></td>
<td><p><span data-ttu-id="1b507-666">この属性には、プレゼンスポリシーオブジェクトの DN が含まれています。</span><span class="sxs-lookup"><span data-stu-id="1b507-666">This attribute contains the DN for a presence policy object.</span></span></p></td>
<td><p><span data-ttu-id="1b507-667">Office Communications Server 2007 R2 の新製品。</span><span class="sxs-lookup"><span data-stu-id="1b507-667">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b507-668">msRTCSIP-Msrtcsip-primaryhomeserver</span><span class="sxs-lookup"><span data-stu-id="1b507-668">msRTCSIP-PrimaryHomeServer</span></span></p></td>
<td><p><span data-ttu-id="1b507-669">この属性は、SIP メッセージングのユーザーまたは連絡先を有効にします。</span><span class="sxs-lookup"><span data-stu-id="1b507-669">This attribute enables a user or contact for SIP messaging.</span></span> <span data-ttu-id="1b507-670">中央フォレストトポロジでは、ユーザーオブジェクトではなく連絡先オブジェクトが SIP が有効になっているため、連絡先クラスに追加されます。</span><span class="sxs-lookup"><span data-stu-id="1b507-670">It is added to the contact class because in the central forest topology, contact objects, not user objects, are SIP enabled.</span></span></p>
<p><span data-ttu-id="1b507-671">有効な値は、ユーザーが所属する Standard Edition サーバーまたは Enterprise Edition フロントエンドプールの DN です。</span><span class="sxs-lookup"><span data-stu-id="1b507-671">The valid value is the DN of the Standard Edition server or Enterprise Edition Front End pool where a user is homed.</span></span></p></td>
<td><p><span data-ttu-id="1b507-672">Live Communications Server 2005 の新しいもの。</span><span class="sxs-lookup"><span data-stu-id="1b507-672">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b507-673">msRTCSIP-PrimaryUserAddress</span><span class="sxs-lookup"><span data-stu-id="1b507-673">msRTCSIP-PrimaryUserAddress</span></span></p></td>
<td><p><span data-ttu-id="1b507-674">この属性には、指定されたユーザーの SIP アドレスが含まれます。</span><span class="sxs-lookup"><span data-stu-id="1b507-674">This attribute contains the SIP address of a given user.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b507-675">msRTCSIP-PrivateLine</span><span class="sxs-lookup"><span data-stu-id="1b507-675">msRTCSIP-PrivateLine</span></span></p></td>
<td><p><span data-ttu-id="1b507-676">プライベート回線デバイスのデバイス ID を含む属性です。</span><span class="sxs-lookup"><span data-stu-id="1b507-676">This attribute contains the device ID of the private line device.</span></span></p></td>
<td><p><span data-ttu-id="1b507-677">Lync Server 2010 の新。</span><span class="sxs-lookup"><span data-stu-id="1b507-677">New in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b507-678">msRTCSIP ルーティング可能</span><span class="sxs-lookup"><span data-stu-id="1b507-678">msRTCSIP-Routable</span></span></p></td>
<td><p><span data-ttu-id="1b507-679">この属性は、Lync Server が GRUU アドレスを使用してこのサービスにルーティングすることを承認されているかどうかを判断するために使用されるブール型の属性です。</span><span class="sxs-lookup"><span data-stu-id="1b507-679">This attribute is a Boolean attribute used to determine whether Lync Server is authorized to route to this service using its GRUU address.</span></span> <span data-ttu-id="1b507-680">この値が <strong>TRUE</strong>に設定されている場合、Lync Server はこのサービスへのルーティングを承認されています。</span><span class="sxs-lookup"><span data-stu-id="1b507-680">If this value is set to <strong>TRUE</strong>, Lync Server is authorized to route to this service.</span></span> <span data-ttu-id="1b507-681">この値が <strong>FALSE</strong>に設定されている場合、Lync Server はこのサービスへのルーティングを承認されていません。</span><span class="sxs-lookup"><span data-stu-id="1b507-681">If this value is set to <strong>FALSE</strong>, Lync Server is not authorized to route to this service.</span></span></p></td>
<td><p><span data-ttu-id="1b507-682">Office Communications Server 2007 の新製品。</span><span class="sxs-lookup"><span data-stu-id="1b507-682">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b507-683">msRTCSIP-Msrtcsip-routeusageattribute (現在不使用)</span><span class="sxs-lookup"><span data-stu-id="1b507-683">msRTCSIP-RouteUsageAttribute (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="1b507-684">この単一値の UNICODE 文字列属性は、電話ルートの使用を限定する属性を定義します。</span><span class="sxs-lookup"><span data-stu-id="1b507-684">This single-valued UNICODE string attribute defines an attribute that qualifies the usage for a phone route.</span></span> <span data-ttu-id="1b507-685">電話ルートの選択は、2つの要素、つまり、電話ルートに割り当てられる usage 属性と、発信者に許可されているポリシー使用法属性に基づいて決定されます。</span><span class="sxs-lookup"><span data-stu-id="1b507-685">Selection of a phone route is determined based on two elements: the usage attribute assigned to the phone route and the caller’s allowed policy usage attributes.</span></span> <span data-ttu-id="1b507-686">発信者の許可された使用法に一致する使用法属性を持つ最初の電話ルートが選択されています。</span><span class="sxs-lookup"><span data-stu-id="1b507-686">The first phone route with a usage attribute that matches the caller’s allowed usage is selected.</span></span></p></td>
<td><p><span data-ttu-id="1b507-687">Office Communications Server 2007 の新製品。</span><span class="sxs-lookup"><span data-stu-id="1b507-687">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="1b507-688">Lync Server 2010 では廃止されました。</span><span class="sxs-lookup"><span data-stu-id="1b507-688">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b507-689">msRTCSIP-Msrtcsip-routeusagelinks (現在不使用)</span><span class="sxs-lookup"><span data-stu-id="1b507-689">msRTCSIP-RouteUsageLinks (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="1b507-690">この複数値の識別名 (DN) 属性には、ルート使用法の識別名の一覧が含まれています。</span><span class="sxs-lookup"><span data-stu-id="1b507-690">This multi-valued distinguished name (DN) attribute contains a list of route usage distinguished names.</span></span></p>
<p><span data-ttu-id="1b507-691">前方リンク: <strong>リンク ID 11032</strong></span><span class="sxs-lookup"><span data-stu-id="1b507-691">Forward link: <strong>Link ID 11032</strong></span></span></p>
<p><span data-ttu-id="1b507-692">この属性は、対応する後方リンク <strong>msRTCSIP-msrtcsip-phoneroutebl です</strong>への転送リンクです。</span><span class="sxs-lookup"><span data-stu-id="1b507-692">This attribute is a forward link to the corresponding back link <strong>msRTCSIP-PhoneRouteBL</strong>.</span></span></p></td>
<td><p><span data-ttu-id="1b507-693">Lync Server 2010 では廃止されました。</span><span class="sxs-lookup"><span data-stu-id="1b507-693">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b507-694">msRTCSIP-RoutingPoolDN</span><span class="sxs-lookup"><span data-stu-id="1b507-694">msRTCSIP-RoutingPoolDN</span></span></p></td>
<td><p><span data-ttu-id="1b507-695">この MCU または信頼済みサービス宛てのすべての SIP トラフィックが通過する必要のあるプールを指す DN を含む属性です。</span><span class="sxs-lookup"><span data-stu-id="1b507-695">This attribute contains the DN that points to the pool that all SIP traffic addressed to this MCU or Trusted Service must go through.</span></span></p></td>
<td><p><span data-ttu-id="1b507-696">Office Communications Server 2007 R2 の新製品。</span><span class="sxs-lookup"><span data-stu-id="1b507-696">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b507-697">msRTCSIP-RuleName (現在不使用)</span><span class="sxs-lookup"><span data-stu-id="1b507-697">msRTCSIP-RuleName (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="1b507-698">正規化ルールのフレンドリ名を指定する単一値の UNICODE 文字列属性は、管理者が簡単に参照できるようにします。</span><span class="sxs-lookup"><span data-stu-id="1b507-698">This single-valued UNICODE string attribute specifies the friendly name of the normalization rule, so it can easily be referenced by an administrator.</span></span></p></td>
<td><p><span data-ttu-id="1b507-699">Office Communications Server 2007 の新製品。</span><span class="sxs-lookup"><span data-stu-id="1b507-699">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="1b507-700">Lync Server 2010 では廃止されました。</span><span class="sxs-lookup"><span data-stu-id="1b507-700">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b507-701">msRTCSIP-SchemaVersion</span><span class="sxs-lookup"><span data-stu-id="1b507-701">msRTCSIP-SchemaVersion</span></span></p></td>
<td><p><span data-ttu-id="1b507-702">この属性は、組織に現在展開されているスキーマのバージョンを表します。</span><span class="sxs-lookup"><span data-stu-id="1b507-702">This attribute represents the schema version currently deployed in the organization.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b507-703">msRTCSIP-SearchMaxRequests (obsolete)</span><span class="sxs-lookup"><span data-stu-id="1b507-703">msRTCSIP-SearchMaxRequests (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="1b507-704">ユーザーが Communicator を使用して連絡先を検索するときにディレクトリ検索から返される検索結果の数を制限する属性です。</span><span class="sxs-lookup"><span data-stu-id="1b507-704">This attribute limits the number of search results to be returned from a directory search when a user searches for a contact using Communicator.</span></span> <span data-ttu-id="1b507-705">この属性は、クライアントによって指定された値より優先されます。</span><span class="sxs-lookup"><span data-stu-id="1b507-705">This attribute will override the value provided by the client.</span></span></p></td>
<td><p><span data-ttu-id="1b507-706">Lync Server 2010 では廃止されました。</span><span class="sxs-lookup"><span data-stu-id="1b507-706">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b507-707">msRTCSIP-SearchMaxResults (現在不使用)</span><span class="sxs-lookup"><span data-stu-id="1b507-707">msRTCSIP-SearchMaxResults (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="1b507-708">この属性は、返される検索要求の数を制限します。</span><span class="sxs-lookup"><span data-stu-id="1b507-708">This attribute limits the number of search requests returned.</span></span></p></td>
<td><p><span data-ttu-id="1b507-709">Lync Server 2010 では廃止されました。</span><span class="sxs-lookup"><span data-stu-id="1b507-709">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b507-710">msRTCSIP-ServerBL</span><span class="sxs-lookup"><span data-stu-id="1b507-710">msRTCSIP-ServerBL</span></span></p></td>
<td><p><span data-ttu-id="1b507-711">この複数値属性は、識別名 (DN) の一覧を含む後方リンクです。</span><span class="sxs-lookup"><span data-stu-id="1b507-711">This multi-valued attribute is a back link that contains a list of distinguished names (DN).</span></span> <span data-ttu-id="1b507-712">これらの DNs は、プールまたは <strong>Trustedservice</strong> オブジェクトを指します。</span><span class="sxs-lookup"><span data-stu-id="1b507-712">These DNs point to a pool or <strong>TrustedService</strong> object.</span></span></p>
<p><span data-ttu-id="1b507-713">この属性は、Msrtcsip-trustedservicelinks ですの前方リンク <strong>msRTCSIP</strong>に対応します。</span><span class="sxs-lookup"><span data-stu-id="1b507-713">This attribute corresponds to the forward link <strong>msRTCSIP-TrustedServiceLinks</strong>.</span></span></p></td>
<td><p><span data-ttu-id="1b507-714">Office Communications Server 2007 の新製品。</span><span class="sxs-lookup"><span data-stu-id="1b507-714">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b507-715">msRTCSIP-ServerData</span><span class="sxs-lookup"><span data-stu-id="1b507-715">msRTCSIP-ServerData</span></span></p></td>
<td><p><span data-ttu-id="1b507-716">この属性は、今後の使用のために予約されています。</span><span class="sxs-lookup"><span data-stu-id="1b507-716">This attribute is reserved for future use.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b507-717">msRTCSIP-ServerReferenceBL (obsolete)</span><span class="sxs-lookup"><span data-stu-id="1b507-717">msRTCSIP-ServerReferenceBL (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="1b507-718">この複数値属性には、識別名の一覧が含まれています。</span><span class="sxs-lookup"><span data-stu-id="1b507-718">This multi-valued attribute contains a list of distinguished names.</span></span> <span data-ttu-id="1b507-719">これらの識別名は、既定の場所のプロファイルを割り当てることができる他のサーバーオブジェクトを参照する後方リンクです。</span><span class="sxs-lookup"><span data-stu-id="1b507-719">These distinguished names are back links that reference other server objects that can be assigned a default location profile.</span></span></p>
<p><span data-ttu-id="1b507-720">後方リンク: <strong>リンク ID 11037</strong></span><span class="sxs-lookup"><span data-stu-id="1b507-720">Back link: <strong>Link ID 11037</strong></span></span></p>
<p><span data-ttu-id="1b507-721">この後方リンクへの対応する転送リンクは <strong>msRTCSIP-DefaultLocationProfileLink</strong>です。</span><span class="sxs-lookup"><span data-stu-id="1b507-721">The corresponding forward link to this back link is <strong>msRTCSIP-DefaultLocationProfileLink</strong>.</span></span></p>
<p><span data-ttu-id="1b507-722">この後方リンク属性は、プールと仲介サーバーのみを参照します。</span><span class="sxs-lookup"><span data-stu-id="1b507-722">This back link attribute references pools and Mediation Servers only.</span></span></p></td>
<td><p><span data-ttu-id="1b507-723">Office Communications Server 2007 の新製品。</span><span class="sxs-lookup"><span data-stu-id="1b507-723">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="1b507-724">Lync Server 2010 では廃止されました。</span><span class="sxs-lookup"><span data-stu-id="1b507-724">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b507-725">msRTCSIP-ServerVersion</span><span class="sxs-lookup"><span data-stu-id="1b507-725">msRTCSIP-ServerVersion</span></span></p></td>
<td><p><span data-ttu-id="1b507-726">この属性は、サーバーのバージョン情報を定義します。</span><span class="sxs-lookup"><span data-stu-id="1b507-726">This attribute defines the version information of the server.</span></span> <span data-ttu-id="1b507-727">このバージョン番号は、すべてのサーバーの役割に適用されます。</span><span class="sxs-lookup"><span data-stu-id="1b507-727">This version number applies to all server roles.</span></span> <span data-ttu-id="1b507-728">これは、公式の製品リリースごとに増加する、monotonously の整数です。</span><span class="sxs-lookup"><span data-stu-id="1b507-728">It is a monotonously increasing integer that increments with each official product release.</span></span></p>
<p><span data-ttu-id="1b507-729">有効な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="1b507-729">The possible valid values are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="1b507-730">Undefined: Live Communications Server 2003</span><span class="sxs-lookup"><span data-stu-id="1b507-730">Undefined: Live Communications Server 2003</span></span></p>
<p><span data-ttu-id="1b507-731">                 Live Communications Server 2005</span><span class="sxs-lookup"><span data-stu-id="1b507-731">                 Live Communications Server 2005</span></span></p>
<p><span data-ttu-id="1b507-732">                 Live Communications Server 2005 with SP1</span><span class="sxs-lookup"><span data-stu-id="1b507-732">                 Live Communications Server 2005 with SP1</span></span></p></li>
<li><p><span data-ttu-id="1b507-733">3: Office Communications Server 2007</span><span class="sxs-lookup"><span data-stu-id="1b507-733">3: Office Communications Server 2007</span></span></p></li>
<li><p><span data-ttu-id="1b507-734">4: Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="1b507-734">4: Office Communications Server 2007 R2</span></span></p></li>
<li><p><span data-ttu-id="1b507-735">5: Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="1b507-735">5: Lync Server 2010</span></span></p></li>
<li><p><span data-ttu-id="1b507-736">6: Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1b507-736">6: Lync Server 2013</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="1b507-737">Office Communications Server 2007 の新製品。</span><span class="sxs-lookup"><span data-stu-id="1b507-737">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b507-738">msRTCSIP-SourceObjectType</span><span class="sxs-lookup"><span data-stu-id="1b507-738">msRTCSIP-SourceObjectType</span></span></p></td>
<td><p><span data-ttu-id="1b507-739">次に示すように、integer 型のこの単一値属性は、 <strong>msds-sourceobjectdn</strong> が指すオブジェクトの種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="1b507-739">This single-valued attribute of integer type specifies the type of object the <strong>msDS-SourceObjectDN</strong> points to, as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="1b507-740">null |0x00000001: 別のフォレストの Windows NT Server プリンシパルユーザーオブジェクトを表します。</span><span class="sxs-lookup"><span data-stu-id="1b507-740">null | 0x00000001: Represents a Windows NT Server principal user object from a different forest</span></span></p></li>
<li><p><span data-ttu-id="1b507-741">次の属性は、配布グループ拡張のための別のフォレストのグループの種類を表します。</span><span class="sxs-lookup"><span data-stu-id="1b507-741">The following attributes represent a group type from a different forest for distribution group expansion:</span></span></p>
<ul>
<li><p><span data-ttu-id="1b507-742">0x00000002: ADS_GROUP_TYPE_GLOBAL_GROUP</span><span class="sxs-lookup"><span data-stu-id="1b507-742">0x00000002: ADS_GROUP_TYPE_GLOBAL_GROUP</span></span></p></li>
<li><p><span data-ttu-id="1b507-743">0x00000004: ADS_GROUP_TYPE_DOMAIN_LOCAL_GROUP</span><span class="sxs-lookup"><span data-stu-id="1b507-743">0x00000004: ADS_GROUP_TYPE_DOMAIN_LOCAL_GROUP</span></span></p></li>
<li><p><span data-ttu-id="1b507-744">0x00000004: ADS_GROUP_TYPE_LOCAL_GROUP</span><span class="sxs-lookup"><span data-stu-id="1b507-744">0x00000004: ADS_GROUP_TYPE_LOCAL_GROUP</span></span></p></li>
<li><p><span data-ttu-id="1b507-745">0x00000008: ADS_GROUP_TYPE_UNIVERSAL_GROUP</span><span class="sxs-lookup"><span data-stu-id="1b507-745">0x00000008: ADS_GROUP_TYPE_UNIVERSAL_GROUP</span></span></p></li>
<li><p><span data-ttu-id="1b507-746">0x80000000: ADS_GROUP_TYPE_SECURITY_ENABLED</span><span class="sxs-lookup"><span data-stu-id="1b507-746">0x80000000: ADS_GROUP_TYPE_SECURITY_ENABLED</span></span></p></li>
<li><p><span data-ttu-id="1b507-747">0x90000000: 同じフォレストまたは別のフォレストからの自動応答またはサブスクライバーアクセスオブジェクトを表します。</span><span class="sxs-lookup"><span data-stu-id="1b507-747">0x90000000: Represents an Auto-Attendant or subscriber access object from the same forest or a different forest</span></span></p></li>
</ul></li>
</ul></td>
<td><p><span data-ttu-id="1b507-748">Office Communications Server 2007 の新製品。</span><span class="sxs-lookup"><span data-stu-id="1b507-748">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b507-749">msRTCSIP-SubscriptionAuthRequired (obsolete)</span><span class="sxs-lookup"><span data-stu-id="1b507-749">msRTCSIP-SubscriptionAuthRequired (obsolete)</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="1b507-750">Live Communications Server 2003 の新しいもの。</span><span class="sxs-lookup"><span data-stu-id="1b507-750">New in Live Communications Server 2003.</span></span></p>
<p><span data-ttu-id="1b507-751">現在、Live Communications Server 2005 では使用されていません。</span><span class="sxs-lookup"><span data-stu-id="1b507-751">Obsolete in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b507-752">msRTCSIP-Targethoの場合</span><span class="sxs-lookup"><span data-stu-id="1b507-752">msRTCSIP-TargetHomeServer</span></span></p></td>
<td><p><span data-ttu-id="1b507-753">この属性を使用すると、1つの Lync Server プールから別のユーザーまたは連絡先オブジェクトを移動することができます。</span><span class="sxs-lookup"><span data-stu-id="1b507-753">This attribute enables you to move a user or contact object from one Lync Server pool to another.</span></span> <span data-ttu-id="1b507-754">この属性は contact クラスに追加されます。中央フォレストのトポロジでは、ユーザーオブジェクトではなく連絡先オブジェクトが SIP が有効になっているためです。</span><span class="sxs-lookup"><span data-stu-id="1b507-754">This attribute is added to the contact class, because in the central forest topology, contact objects, not user objects, are SIP enabled.</span></span></p>
<p><span data-ttu-id="1b507-755">有効な値は、ユーザーの移動先の Standard Edition サーバーまたはフロントエンドプールの DN です。</span><span class="sxs-lookup"><span data-stu-id="1b507-755">The valid value is the DN of the destination Standard Edition server or Front End pool to which a user is to be moved.</span></span></p></td>
<td><p><span data-ttu-id="1b507-756">Live Communications Server 2005 の新しいもの。</span><span class="sxs-lookup"><span data-stu-id="1b507-756">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b507-757">msRTCSIP-Msrtcsip-targetphonenumber (現在不使用)</span><span class="sxs-lookup"><span data-stu-id="1b507-757">msRTCSIP-TargetPhoneNumber (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="1b507-758"><strong>MsRTCSIP</strong>で定義されている特定のゲートウェイにルーティングする電話番号のパターンまたは範囲を含む単一値の文字列属性です。</span><span class="sxs-lookup"><span data-stu-id="1b507-758">This single-valued string attribute contains a phone number pattern or range to route to the specified gateways defined in <strong>msRTCSIP-Gateways</strong>.</span></span></p></td>
<td><p><span data-ttu-id="1b507-759">Lync Server 2010 では廃止されました。</span><span class="sxs-lookup"><span data-stu-id="1b507-759">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b507-760">msRTCSIP-TargetUserPolicies</span><span class="sxs-lookup"><span data-stu-id="1b507-760">msRTCSIP-TargetUserPolicies</span></span></p></td>
<td><p><span data-ttu-id="1b507-761">この属性は、Lync Server ユーザーのターゲットポリシーの名前と値のペアを格納します。</span><span class="sxs-lookup"><span data-stu-id="1b507-761">This attribute stores name-value pairs for target policies for Lync Server users.</span></span></p></td>
<td><p><span data-ttu-id="1b507-762">Lync Server 2010 の新。</span><span class="sxs-lookup"><span data-stu-id="1b507-762">New in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b507-763">msRTCSIP-TenantId</span><span class="sxs-lookup"><span data-stu-id="1b507-763">msRTCSIP-TenantId</span></span></p></td>
<td><p><span data-ttu-id="1b507-764">テナントの一意識別子を格納する属性です。</span><span class="sxs-lookup"><span data-stu-id="1b507-764">This attribute stores the unique identifier for a tenant.</span></span></p></td>
<td><p><span data-ttu-id="1b507-765">Lync Server 2010 の新。</span><span class="sxs-lookup"><span data-stu-id="1b507-765">New in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b507-766">msRTCSIP-変換 (現在不使用)</span><span class="sxs-lookup"><span data-stu-id="1b507-766">msRTCSIP-Translation (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="1b507-767">この属性は、Lync Server の音声機能によって使用され、一致が見つかった場合にダイヤル番号に適用する変換文字列を格納します。</span><span class="sxs-lookup"><span data-stu-id="1b507-767">This attribute is used by the voice feature of Lync Server and contains the translation string to apply on the dialed number, if a match is found.</span></span></p></td>
<td><p><span data-ttu-id="1b507-768">Office Communications Server 2007 の新製品。</span><span class="sxs-lookup"><span data-stu-id="1b507-768">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="1b507-769">Lync Server 2010 では廃止されました。</span><span class="sxs-lookup"><span data-stu-id="1b507-769">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b507-770">msRTCSIP-TrustedMCUData</span><span class="sxs-lookup"><span data-stu-id="1b507-770">msRTCSIP-TrustedMCUData</span></span></p></td>
<td><p><span data-ttu-id="1b507-771">この属性は、今後の使用のために予約されています。</span><span class="sxs-lookup"><span data-stu-id="1b507-771">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="1b507-772">Office Communications Server 2007 の新製品。</span><span class="sxs-lookup"><span data-stu-id="1b507-772">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b507-773">msRTCSIP-TrustedMCUFQDN</span><span class="sxs-lookup"><span data-stu-id="1b507-773">msRTCSIP-TrustedMCUFQDN</span></span></p></td>
<td><p><span data-ttu-id="1b507-774">この属性は、MCU の FQDN を含む文字列型 (string) の値です。</span><span class="sxs-lookup"><span data-stu-id="1b507-774">This attribute is a string value that contains the FQDN of the MCU.</span></span> <span data-ttu-id="1b507-775">これは単一値の属性です。</span><span class="sxs-lookup"><span data-stu-id="1b507-775">This is a single-valued attribute.</span></span> <span data-ttu-id="1b507-776">各セグメントの有効な値は、63文字です。FQDN 全体の有効な値は255文字です。</span><span class="sxs-lookup"><span data-stu-id="1b507-776">The valid value for each segment is 63 characters; the valid value for the entire FQDN is 255 characters.</span></span></p></td>
<td><p><span data-ttu-id="1b507-777">Office Communications Server 2007 の新製品。</span><span class="sxs-lookup"><span data-stu-id="1b507-777">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b507-778">msRTCSIP-TrustedProxyData</span><span class="sxs-lookup"><span data-stu-id="1b507-778">msRTCSIP-TrustedProxyData</span></span></p></td>
<td><p><span data-ttu-id="1b507-779">この属性は、今後の使用のために予約されています。</span><span class="sxs-lookup"><span data-stu-id="1b507-779">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="1b507-780">Office Communications Server 2007 の新製品。</span><span class="sxs-lookup"><span data-stu-id="1b507-780">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b507-781">msRTCSIP-TrustedProxyFQDN</span><span class="sxs-lookup"><span data-stu-id="1b507-781">msRTCSIP-TrustedProxyFQDN</span></span></p></td>
<td><p><span data-ttu-id="1b507-782">この属性は、プロキシサーバーを実行しているサーバーの FQDN を含む文字列型 (string) の値です。</span><span class="sxs-lookup"><span data-stu-id="1b507-782">This attribute is a string value that contains the FQDN of the server running Proxy Server.</span></span> <span data-ttu-id="1b507-783">この属性は単一値です。</span><span class="sxs-lookup"><span data-stu-id="1b507-783">This attribute is single-valued.</span></span> <span data-ttu-id="1b507-784">各セグメントの有効な値は、63文字です。FQDN 全体の有効な値は255文字です。</span><span class="sxs-lookup"><span data-stu-id="1b507-784">The valid value for each segment is 63 characters; the valid value for the entire FQDN is 255 characters.</span></span></p></td>
<td><p><span data-ttu-id="1b507-785">Office Communications Server 2007 の新製品。</span><span class="sxs-lookup"><span data-stu-id="1b507-785">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b507-786">msRTCSIP-TrustedServerData</span><span class="sxs-lookup"><span data-stu-id="1b507-786">msRTCSIP-TrustedServerData</span></span></p></td>
<td><p><span data-ttu-id="1b507-787">この属性は、今後の使用のために予約されています。</span><span class="sxs-lookup"><span data-stu-id="1b507-787">This attribute is reserved for future use.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b507-788">msRTCSIP-TrustedServerFQDN</span><span class="sxs-lookup"><span data-stu-id="1b507-788">msRTCSIP-TrustedServerFQDN</span></span></p></td>
<td><p><span data-ttu-id="1b507-789">この属性は、信頼済みサーバーの FQDN を表す単一値の属性です。</span><span class="sxs-lookup"><span data-stu-id="1b507-789">This attribute is a single-valued attribute that represents the FQDN of a trusted server.</span></span></p></td>
<td><p><span data-ttu-id="1b507-790">Live Communications Server 2005 の新しいもの。</span><span class="sxs-lookup"><span data-stu-id="1b507-790">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b507-791">msRTCSIP-TrustedServerVersion</span><span class="sxs-lookup"><span data-stu-id="1b507-791">msRTCSIP-TrustedServerVersion</span></span></p></td>
<td><p><span data-ttu-id="1b507-792">この属性は、信頼済みサーバーの一覧のサーバーのバージョン番号を指定します。</span><span class="sxs-lookup"><span data-stu-id="1b507-792">This attribute specifies the version number of a server in the trusted server list.</span></span></p>
<p><span data-ttu-id="1b507-793">有効な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="1b507-793">The possible valid values are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="1b507-794">NULL: Live Communications Server 2003</span><span class="sxs-lookup"><span data-stu-id="1b507-794">NULL: Live Communications Server 2003</span></span></p></li>
<li><p><span data-ttu-id="1b507-795">2: Live Communications Server 2005</span><span class="sxs-lookup"><span data-stu-id="1b507-795">2: Live Communications Server 2005</span></span></p></li>
<li><p><span data-ttu-id="1b507-796">3: Office Communications Server 2007</span><span class="sxs-lookup"><span data-stu-id="1b507-796">3: Office Communications Server 2007</span></span></p></li>
<li><p><span data-ttu-id="1b507-797">4: Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="1b507-797">4: Office Communications Server 2007 R2</span></span></p></li>
<li><p><span data-ttu-id="1b507-798">5: Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="1b507-798">5: Lync Server 2010</span></span></p></li>
<li><p><span data-ttu-id="1b507-799">6: Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1b507-799">6: Lync Server 2013</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="1b507-800">Live Communications Server 2005 の新しいもの。</span><span class="sxs-lookup"><span data-stu-id="1b507-800">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b507-801">msRTCSIP-TrustedServiceFlags</span><span class="sxs-lookup"><span data-stu-id="1b507-801">msRTCSIP-TrustedServiceFlags</span></span></p></td>
<td><p><span data-ttu-id="1b507-802">この属性は、信頼済みサービスに対して有効になるオプションを定義します。</span><span class="sxs-lookup"><span data-stu-id="1b507-802">This attribute defines the options that are enabled for the trusted service.</span></span></p></td>
<td><p><span data-ttu-id="1b507-803">Office Communications Server 2007 R2 の新製品。</span><span class="sxs-lookup"><span data-stu-id="1b507-803">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b507-804">msRTCSIP-Msrtcsip-trustedservicelinks です</span><span class="sxs-lookup"><span data-stu-id="1b507-804">msRTCSIP-TrustedServiceLinks</span></span></p></td>
<td><p><span data-ttu-id="1b507-805">この複数値属性には、メディアリレー認証サービスなど、信頼されたサービスオブジェクトを参照する識別名 (DN) の一覧が含まれています。</span><span class="sxs-lookup"><span data-stu-id="1b507-805">This multi-valued attribute contains a list of distinguished names (DN) that reference a trusted service object, such as a Media Relay Authentication Service.</span></span> <span data-ttu-id="1b507-806">メディアリレー認証サービス (音声ビデオ会議サービスを実行しているエッジサーバーに物理的に併置されている) は、リモートユーザーのオーディオシナリオをサポートするために、プールに関連付けられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="1b507-806">A Media Relay Authentication Service (physically collocated on the Edge Server running the A/V Conferencing service) must be associated with a pool to support audio scenarios for remote users.</span></span></p>
<p><span data-ttu-id="1b507-807">この転送リンク属性への対応する後方リンクは、 <strong>msRTCSIP-ServerBL</strong>です。</span><span class="sxs-lookup"><span data-stu-id="1b507-807">The corresponding back link to this forward link attribute is <strong>msRTCSIP-ServerBL</strong>.</span></span></p></td>
<td><p><span data-ttu-id="1b507-808">UC</span><span class="sxs-lookup"><span data-stu-id="1b507-808">UC</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b507-809">msRTCSIP-TrustedServicePort</span><span class="sxs-lookup"><span data-stu-id="1b507-809">msRTCSIP-TrustedServicePort</span></span></p></td>
<td><p><span data-ttu-id="1b507-810">この GRUU サービスへの接続に使用するポート番号を定義する整数の属性です。</span><span class="sxs-lookup"><span data-stu-id="1b507-810">This attribute is an integer that defines the port number used to connect to this GRUU service.</span></span></p></td>
<td><p><span data-ttu-id="1b507-811">Office Communications Server 2007 の新製品。</span><span class="sxs-lookup"><span data-stu-id="1b507-811">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b507-812">msRTCSIP-TrustedServiceType</span><span class="sxs-lookup"><span data-stu-id="1b507-812">msRTCSIP-TrustedServiceType</span></span></p></td>
<td><p><span data-ttu-id="1b507-813">この属性は、それが表す GRUU サービスの種類を定義する文字列型 (string) の値です。</span><span class="sxs-lookup"><span data-stu-id="1b507-813">This attribute is a string value that defines the type of GRUU service it represents.</span></span></p>
<p><span data-ttu-id="1b507-814">有効な GRUU サービスの種類は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="1b507-814">The valid GRUU service types are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="1b507-815">MediationServer</span><span class="sxs-lookup"><span data-stu-id="1b507-815">MediationServer</span></span></p></li>
<li><p><span data-ttu-id="1b507-816">ゲートウェイ</span><span class="sxs-lookup"><span data-stu-id="1b507-816">Gateway</span></span></p></li>
<li><p><span data-ttu-id="1b507-817">メディアリレー認証サービス (MRAS)</span><span class="sxs-lookup"><span data-stu-id="1b507-817">Media Relay Authentication Service (MRAS)</span></span></p></li>
<li><p><span data-ttu-id="1b507-818">QoSM</span><span class="sxs-lookup"><span data-stu-id="1b507-818">QoSM</span></span></p></li>
<li><p><span data-ttu-id="1b507-819">msRTCSIP-UserExtension NM-CWA-NO-VERSION</span><span class="sxs-lookup"><span data-stu-id="1b507-819">msRTCSIP-UserExtension CWA</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="1b507-820">Office Communications Server 2007 の新製品。</span><span class="sxs-lookup"><span data-stu-id="1b507-820">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b507-821">msRTCSIP-Trustedwebコンポーネント Serverdata</span><span class="sxs-lookup"><span data-stu-id="1b507-821">msRTCSIP-TrustedWebComponentsServerData</span></span></p></td>
<td><p><span data-ttu-id="1b507-822">この属性は、今後の使用のために予約されています。</span><span class="sxs-lookup"><span data-stu-id="1b507-822">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="1b507-823">Office Communications Server 2007 の新製品。</span><span class="sxs-lookup"><span data-stu-id="1b507-823">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b507-824">msRTCSIP-Trustedwebコンポーネント Serverfqdn</span><span class="sxs-lookup"><span data-stu-id="1b507-824">msRTCSIP-TrustedWebComponentsServerFQDN</span></span></p></td>
<td><p><span data-ttu-id="1b507-825">この属性は、Lync Server Web サービスを実行している IIS の FQDN を含む文字列型 (string) の値です。</span><span class="sxs-lookup"><span data-stu-id="1b507-825">This attribute is a string value that contains the FQDN of the IIS running Lync Server Web Services.</span></span> <span data-ttu-id="1b507-826">これは単一値の属性です。</span><span class="sxs-lookup"><span data-stu-id="1b507-826">This is a single-valued attribute.</span></span> <span data-ttu-id="1b507-827">各セグメントの有効な値は、63文字です。FQDN 全体の有効な値は255文字です。</span><span class="sxs-lookup"><span data-stu-id="1b507-827">The valid value for each segment is 63 characters; the valid value for the entire FQDN is 255 characters.</span></span></p></td>
<td><p><span data-ttu-id="1b507-828">Office Communications Server 2007 の新製品。</span><span class="sxs-lookup"><span data-stu-id="1b507-828">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b507-829">msRTCSIP-UCFlags (obsolete)</span><span class="sxs-lookup"><span data-stu-id="1b507-829">msRTCSIP-UCFlags (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="1b507-830">この属性は、すべてのユーザーオブジェクトまたは連絡先オブジェクトに対してグローバルに有効になっているさまざまな UC オプションを定義します。</span><span class="sxs-lookup"><span data-stu-id="1b507-830">This attribute defines different UC options that are enabled globally to all user or contact objects.</span></span> <span data-ttu-id="1b507-831">この属性は、整数型のビットマスク値です。</span><span class="sxs-lookup"><span data-stu-id="1b507-831">This attribute is a bit-mask value of integer type.</span></span> <span data-ttu-id="1b507-832">各オプションは、ビットがあるかどうかで表されます。</span><span class="sxs-lookup"><span data-stu-id="1b507-832">Each option is represented by the presence of a bit.</span></span></p>
<p><span data-ttu-id="1b507-833">有効な値 (および関連するビット位置) は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="1b507-833">The possible valid value (and associated bit position) are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="1b507-834">4: UsePerUserUCPolicy (ビット位置 2)</span><span class="sxs-lookup"><span data-stu-id="1b507-834">4: UsePerUserUCPolicy (bit position 2)</span></span></p></li>
</ul>
<p><span data-ttu-id="1b507-835">このビットが設定されている場合、UC ポリシーはユーザーごとに定義されます。</span><span class="sxs-lookup"><span data-stu-id="1b507-835">When this bit is set, the UC policy is defined per user.</span></span></p></td>
<td><p><span data-ttu-id="1b507-836">Lync Server 2010 では廃止されました。</span><span class="sxs-lookup"><span data-stu-id="1b507-836">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b507-837">msRTCSIP-UCPolicy (現在不使用)</span><span class="sxs-lookup"><span data-stu-id="1b507-837">msRTCSIP-UCPolicy (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="1b507-838">この単一値の属性には、管理者がこのユーザーに対して割り当てた UC ポリシーの識別名 (DN) が含まれています。</span><span class="sxs-lookup"><span data-stu-id="1b507-838">This single-valued attribute contains the distinguished name (DN) of the UC policy that the administrator has assigned for this user.</span></span></p></td>
<td><p><span data-ttu-id="1b507-839">Lync Server 2010 では廃止されました。</span><span class="sxs-lookup"><span data-stu-id="1b507-839">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b507-840">msRTCSIP-UserDomainList (obsolete)</span><span class="sxs-lookup"><span data-stu-id="1b507-840">msRTCSIP-UserDomainList (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="1b507-841">この属性は、SIP が有効なユーザーをホストするフォレスト内のすべてのドメインの一覧を提供します。</span><span class="sxs-lookup"><span data-stu-id="1b507-841">This attribute provides a list of all the domains in a forest that host SIP-enabled users.</span></span> <span data-ttu-id="1b507-842">既定値は空のリストで、フォレスト内のすべてのドメインの SIP が有効になっていることを示します。</span><span class="sxs-lookup"><span data-stu-id="1b507-842">The default is an empty list, indicating that all domains in the forest are SIP-enabled.</span></span></p>
<p><span data-ttu-id="1b507-843">有効な値は、個々のドメインのドメイン名を表す複数の文字列です。</span><span class="sxs-lookup"><span data-stu-id="1b507-843">Valid values are multiple strings representing the domain names of individual domains.</span></span></p></td>
<td><p><span data-ttu-id="1b507-844">Live Communications Server 2005 の新しいもの。</span><span class="sxs-lookup"><span data-stu-id="1b507-844">New in Live Communications Server 2005.</span></span></p>
<p><span data-ttu-id="1b507-845">Lync Server 2010 では廃止されました。</span><span class="sxs-lookup"><span data-stu-id="1b507-845">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b507-846">msRTCSIP-UserEnabled</span><span class="sxs-lookup"><span data-stu-id="1b507-846">msRTCSIP-UserEnabled</span></span></p></td>
<td><p><span data-ttu-id="1b507-847">この属性は、ユーザーが Lync Server に対して現在有効になっているかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="1b507-847">This attribute determines whether the user is currently enabled for Lync Server.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b507-848">msRTCSIP-UserExtension</span><span class="sxs-lookup"><span data-stu-id="1b507-848">msRTCSIP-UserExtension</span></span></p></td>
<td><p><span data-ttu-id="1b507-849">Name = value の形式の名前と値のペアの一覧を含む複数値の属性 &quot; です。 &quot; この属性には、グローバルカタログレプリケーションのマークが付いています。</span><span class="sxs-lookup"><span data-stu-id="1b507-849">This multi-valued attribute contains a list of name-value pairs in the format of &quot;name=value.&quot; This attribute is marked for global catalog replication.</span></span></p></td>
<td><p><span data-ttu-id="1b507-850">Live Communications Server 2005 SP1 で導入されています。</span><span class="sxs-lookup"><span data-stu-id="1b507-850">New in Live Communications Server 2005 with SP1.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b507-851">msRTCSIP-UserLocationProfile</span><span class="sxs-lookup"><span data-stu-id="1b507-851">msRTCSIP-UserLocationProfile</span></span></p></td>
<td><p><span data-ttu-id="1b507-852">この属性には、場所のプロファイルオブジェクトを指す識別名 (DN) が含まれています。</span><span class="sxs-lookup"><span data-stu-id="1b507-852">This attribute contains the distinguished name (DN) that points to a location profile object.</span></span></p></td>
<td><p><span data-ttu-id="1b507-853">Office Communications Server 2007 R2 の新製品。</span><span class="sxs-lookup"><span data-stu-id="1b507-853">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b507-854">msRTCSIP-UserPolicies</span><span class="sxs-lookup"><span data-stu-id="1b507-854">msRTCSIP-UserPolicies</span></span></p></td>
<td><p><span data-ttu-id="1b507-855">この属性は、ユーザーポリシーの名前と値のペアを格納します。</span><span class="sxs-lookup"><span data-stu-id="1b507-855">This attribute stores name-value pairs for user policies.</span></span></p></td>
<td><p><span data-ttu-id="1b507-856">Lync Server 2010 の新。</span><span class="sxs-lookup"><span data-stu-id="1b507-856">New in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b507-857">msRTCSIP-UserPolicy</span><span class="sxs-lookup"><span data-stu-id="1b507-857">msRTCSIP-UserPolicy</span></span></p></td>
<td><p><span data-ttu-id="1b507-858">これは、異なる種類のグローバルユーザーポリシーをポイントするバイナリ (DN_WITH_BINARY) を含む複数値の属性です。</span><span class="sxs-lookup"><span data-stu-id="1b507-858">This is a multi-valued attribute containing a list of distinguished names with binary (DN_WITH_BINARY) pointing to global user policies of different types.</span></span> <span data-ttu-id="1b507-859">Binary 部分は、DN 部分が指すポリシーの種類を示します。</span><span class="sxs-lookup"><span data-stu-id="1b507-859">The binary part indicates the type of policy to which the DN portion points.</span></span></p>
<p><span data-ttu-id="1b507-860">有効なバイナリ値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="1b507-860">The valid binary values are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="1b507-861">0x00000001: 会議ポリシー</span><span class="sxs-lookup"><span data-stu-id="1b507-861">0x00000001: Meeting policy</span></span></p></li>
<li><p><span data-ttu-id="1b507-862">0x00000002: UC ポリシー</span><span class="sxs-lookup"><span data-stu-id="1b507-862">0x00000002: UC policy</span></span></p></li>
<li><p><span data-ttu-id="1b507-863">0x00000005: プレゼンスポリシー</span><span class="sxs-lookup"><span data-stu-id="1b507-863">0x00000005: Presence policy</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="1b507-864">Office Communications Server 2007 の新製品。</span><span class="sxs-lookup"><span data-stu-id="1b507-864">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b507-865">msRTCSIP-UserRoutingGroupId</span><span class="sxs-lookup"><span data-stu-id="1b507-865">msRTCSIP-UserRoutingGroupId</span></span></p></td>
<td><p><span data-ttu-id="1b507-p165">SIP ルーティング グループ ID。同じグループのユーザーは、同じフロントエンド サーバーに登録します。</span><span class="sxs-lookup"><span data-stu-id="1b507-p165">This is the SIP routing group ID. Users in the same group will register to the same Front End Server.</span></span></p></td>
<td><p><span data-ttu-id="1b507-868">Lync Server 2013 の新。</span><span class="sxs-lookup"><span data-stu-id="1b507-868">New in Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b507-869">msRTCSIP-Webコンポーネントデータ</span><span class="sxs-lookup"><span data-stu-id="1b507-869">msRTCSIP-WebComponentsData</span></span></p></td>
<td><p><span data-ttu-id="1b507-870">これは複数値の属性です。</span><span class="sxs-lookup"><span data-stu-id="1b507-870">This is a multi-valued attribute.</span></span> <span data-ttu-id="1b507-871">この属性は、今後の使用のために予約されています。</span><span class="sxs-lookup"><span data-stu-id="1b507-871">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="1b507-872">Office Communications Server 2007 の新製品。</span><span class="sxs-lookup"><span data-stu-id="1b507-872">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b507-873">msRTCSIP-Msrtcsip-webcomponentspooladdress</span><span class="sxs-lookup"><span data-stu-id="1b507-873">msRTCSIP-WebComponentsPoolAddress</span></span></p></td>
<td><p><span data-ttu-id="1b507-874">Web コンポーネントが属するプールまたは Standard Edition サーバーを示す単一値の属性です。</span><span class="sxs-lookup"><span data-stu-id="1b507-874">This single-valued attribute points to the pool or Standard Edition server to which the web components belong.</span></span></p>
<p><span data-ttu-id="1b507-875">前方リンク: <strong>リンク ID 11028</strong></span><span class="sxs-lookup"><span data-stu-id="1b507-875">Forward link: <strong>Link ID 11028</strong></span></span></p>
<p><span data-ttu-id="1b507-876">この転送リンク属性への対応する後方リンクは、 <strong>msRTCSIP-Webコンポーネントサーバー</strong>です。</span><span class="sxs-lookup"><span data-stu-id="1b507-876">The corresponding back link to this forward link attribute is <strong>msRTCSIP-WebComponentsServers</strong>.</span></span></p></td>
<td><p><span data-ttu-id="1b507-877">Office Communications Server 2007 の新製品。</span><span class="sxs-lookup"><span data-stu-id="1b507-877">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b507-878">msRTCSIP-Webコンポーネントサーバー</span><span class="sxs-lookup"><span data-stu-id="1b507-878">msRTCSIP-WebComponentsServers</span></span></p></td>
<td><p><span data-ttu-id="1b507-879">この属性は、複数値を持つ識別名の一覧です。</span><span class="sxs-lookup"><span data-stu-id="1b507-879">This attribute is a multi-valued list of distinguished names.</span></span> <span data-ttu-id="1b507-880">この属性には、このプールに関連付けられているすべての Web サーバーの一覧が含まれています。</span><span class="sxs-lookup"><span data-stu-id="1b507-880">This attribute contains a list of all Web servers associated with this pool.</span></span></p>
<p><span data-ttu-id="1b507-881">後方リンク: <strong>リンク ID 11029</strong></span><span class="sxs-lookup"><span data-stu-id="1b507-881">Back link: <strong>Link ID 11029</strong></span></span></p>
<p><span data-ttu-id="1b507-882">この後方リンクへの対応する転送リンクは、 <strong>msRTCSIP-msrtcsip-webcomponentspooladdress</strong>です。</span><span class="sxs-lookup"><span data-stu-id="1b507-882">The corresponding forward link to this back link is <strong>msRTCSIP-WebComponentsPoolAddress</strong>.</span></span></p></td>
<td><p><span data-ttu-id="1b507-883">Office Communications Server 2007 の新製品。</span><span class="sxs-lookup"><span data-stu-id="1b507-883">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b507-884">msRTCSIP (現在不使用)</span><span class="sxs-lookup"><span data-stu-id="1b507-884">msRTCSIP-WMIInstanceId (obsolete)</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="1b507-885">Live Communications Server 2003 の新しいもの。</span><span class="sxs-lookup"><span data-stu-id="1b507-885">New in Live Communications Server 2003.</span></span></p>
<p><span data-ttu-id="1b507-886">現在、Live Communications Server 2005 では使用されていません。</span><span class="sxs-lookup"><span data-stu-id="1b507-886">Obsolete in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b507-887">OtherIPPhone</span><span class="sxs-lookup"><span data-stu-id="1b507-887">OtherIPPhone</span></span></p></td>
<td><p><span data-ttu-id="1b507-888">この既存の Active Directory 属性は、テレフォニーが電話の代替 TCP/IP アドレスの一覧を指定するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="1b507-888">This existing Active Directory attribute is used by telephony to specify the list of alternate TCP/IP addresses for a phone.</span></span></p></td>
<td><p><span data-ttu-id="1b507-889">Windows Server 2008 オペレーティングシステムの新機能。</span><span class="sxs-lookup"><span data-stu-id="1b507-889">New in Windows Server 2008 operating system.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b507-890">電話電話 (その他)</span><span class="sxs-lookup"><span data-stu-id="1b507-890">PhoneOfficeOther</span></span></p></td>
<td><p><span data-ttu-id="1b507-891">この既存の Active Directory 属性は、Lync Server の音声コンポーネントによって使用されます。連絡先オブジェクトの場合は、ユニファイドメッセージングの自動応答およびサブスクライバーアクセス番号への呼び出しをルーティングすることを目的としています。</span><span class="sxs-lookup"><span data-stu-id="1b507-891">This existing Active Directory attribute is used by the voice components in Lync Server, for contact objects only, for the purpose of routing calls to the unified messaging auto-attendant and subscriber access numbers.</span></span> <span data-ttu-id="1b507-892">無条件着信転送アドレスは、この複数値属性に格納されます。</span><span class="sxs-lookup"><span data-stu-id="1b507-892">The unconditional call forwarding address is stored in this multi-valued attribute.</span></span> <span data-ttu-id="1b507-893">このアカウントは、自動応答およびサブスクライバーアクセスの特定の目的のために作成されます。</span><span class="sxs-lookup"><span data-stu-id="1b507-893">This account is created for the specific purpose of auto-attendant and subscriber access.</span></span> <span data-ttu-id="1b507-894">このアカウントの属性は、管理者が変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="1b507-894">This account’s attributes should not be modified by administrators.</span></span></p></td>
<td><p><span data-ttu-id="1b507-895">Windows 2000 オペレーティングシステムの新機能。</span><span class="sxs-lookup"><span data-stu-id="1b507-895">New in Windows 2000 operating system.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b507-896">ProxyAddresses</span><span class="sxs-lookup"><span data-stu-id="1b507-896">ProxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="1b507-897">この既存の Active Directory 複数値属性は、Windows 2000 で導入された base Active Directory スキーマの一部です。</span><span class="sxs-lookup"><span data-stu-id="1b507-897">This existing Active Directory multi-valued attribute is part of the base Active Directory schema introduced in Windows 2000.</span></span> <span data-ttu-id="1b507-898">この属性には、ユーザーの電子メールのさまざまな X400、X500、および SMTP アドレスが含まれています。</span><span class="sxs-lookup"><span data-stu-id="1b507-898">This attribute contains the various X400, X500, and SMTP addresses of the user’s email.</span></span> <span data-ttu-id="1b507-899">Live Communications Server 2003 以降では、sip: タグを使用して、ユーザーの SIP URI がこのリストに追加されます &quot; &quot; 。</span><span class="sxs-lookup"><span data-stu-id="1b507-899">In Live Communications Server 2003 and later, the user’s SIP URI is added to this list, using the &quot;sip:&quot; tag.</span></span></p>
<p><span data-ttu-id="1b507-900">次のアプリケーションは、この属性からユーザーの SIP URI を検索します。</span><span class="sxs-lookup"><span data-stu-id="1b507-900">The following applications search the user’s SIP URI from this attribute:</span></span></p>
<ul>
<li><p><span data-ttu-id="1b507-901">Microsoft Office Outlook 2003 メッセージングおよびコラボレーションクライアント</span><span class="sxs-lookup"><span data-stu-id="1b507-901">Microsoft Office Outlook 2003 messaging and collaboration client</span></span></p></li>
<li><p><span data-ttu-id="1b507-902">Microsoft Office SharePoint Server 2007</span><span class="sxs-lookup"><span data-stu-id="1b507-902">Microsoft Office SharePoint Server 2007</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="1b507-903">Windows 2000 オペレーティングシステムの新機能。</span><span class="sxs-lookup"><span data-stu-id="1b507-903">New in Windows 2000 operating system.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b507-904">TelephoneNumber</span><span class="sxs-lookup"><span data-stu-id="1b507-904">TelephoneNumber</span></span></p></td>
<td><p><span data-ttu-id="1b507-905">この既存の Active Directory 属性には、ユーザーの電話番号が含まれています。</span><span class="sxs-lookup"><span data-stu-id="1b507-905">This existing Active Directory attribute contains the telephone number for the user.</span></span></p></td>
<td><p><span data-ttu-id="1b507-906">Windows 2000 オペレーティングシステムの新機能。</span><span class="sxs-lookup"><span data-stu-id="1b507-906">New in Windows 2000 operating system.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

