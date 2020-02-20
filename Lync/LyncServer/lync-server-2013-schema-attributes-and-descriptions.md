---
title: 'Lync Server 2013: スキーマの属性と説明'
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
ms.openlocfilehash: c95fa0450a85aea4ffdd53dfcb61ddb5b97ed532
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42144155"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="schema-attributes-and-descriptions-in-lync-server-2013"></a><span data-ttu-id="67ecb-102">Lync Server 2013 のスキーマの属性と説明</span><span class="sxs-lookup"><span data-stu-id="67ecb-102">Schema attributes and descriptions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="67ecb-103">_**トピックの最終更新日:** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="67ecb-103">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="67ecb-104">このセクションでは、Lync Server 2013 で使用されるすべてのスキーマ属性について説明します。</span><span class="sxs-lookup"><span data-stu-id="67ecb-104">This section describes all the schema attributes used by Lync Server 2013.</span></span> <span data-ttu-id="67ecb-105">属性に関連付けられたクラスについては、「 [Lync Server 2013 のクラス別のスキーマ属性](lync-server-2013-schema-attributes-by-class.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="67ecb-105">For the classes associated with attributes, see [Schema attributes by class in Lync Server 2013](lync-server-2013-schema-attributes-by-class.md).</span></span> <span data-ttu-id="67ecb-106">Lync Server 2013 で新しく追加されたクラスと属性の一覧については、「 [Lync server 2013 のスキーマの変更点](lync-server-2013-schema-changes-in-lync-server-2013.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="67ecb-106">For a list of classes and attributes that are new in Lync Server 2013, see [Schema changes in Lync Server 2013](lync-server-2013-schema-changes-in-lync-server-2013.md).</span></span>

<span data-ttu-id="67ecb-107">リンクされたペアの属性は、前方リンクまたは後方リンクとして指定されます。</span><span class="sxs-lookup"><span data-stu-id="67ecb-107">Attributes that are linked pairs are specified as forward links or back links.</span></span> <span data-ttu-id="67ecb-108">別のオブジェクトを参照する属性は、前方リンクです。最初のオブジェクトを参照する other オブジェクトの属性は、後方リンクです。</span><span class="sxs-lookup"><span data-stu-id="67ecb-108">An attribute that refers to another object is a forward link; the attribute of the other object that refers back to the first object is a back link.</span></span> <span data-ttu-id="67ecb-109">前方リンクは更新可能で、後方リンクは読み取り専用です。</span><span class="sxs-lookup"><span data-stu-id="67ecb-109">Forward links are updatable, while back links are read-only.</span></span>

<span data-ttu-id="67ecb-110">一部の属性にはビットマスク値があります。</span><span class="sxs-lookup"><span data-stu-id="67ecb-110">Some attributes have a bit-mask value.</span></span> <span data-ttu-id="67ecb-111">これらの属性の場合、各設定はビットで表され、表示される10進値はビット位置を表します。</span><span class="sxs-lookup"><span data-stu-id="67ecb-111">For these attributes, each setting is represented by a bit, and the displayed decimal value represents the bit position.</span></span> <span data-ttu-id="67ecb-112">ビット位置はビット0で始まります。</span><span class="sxs-lookup"><span data-stu-id="67ecb-112">Bit positions start with bit 0.</span></span> <span data-ttu-id="67ecb-113">たとえば、1 (バイナリ) はビット0セットで、1万 (バイナリ) はビット4セットです。</span><span class="sxs-lookup"><span data-stu-id="67ecb-113">For example, 1 (binary) is bit 0 set and 10000 (binary) is bit 4 set.</span></span> <span data-ttu-id="67ecb-114">各ビットはプロパティを表します。</span><span class="sxs-lookup"><span data-stu-id="67ecb-114">Each bit represents a property.</span></span> <span data-ttu-id="67ecb-115">以下はその例です。</span><span class="sxs-lookup"><span data-stu-id="67ecb-115">The following are some examples:</span></span>

  - <span data-ttu-id="67ecb-116">1万 (バイナリ) の10進値は16です (つまり、ビット4が設定されます)。</span><span class="sxs-lookup"><span data-stu-id="67ecb-116">10000 (binary) has a decimal value of 16 (that is, bit 4 is set).</span></span>

  - <span data-ttu-id="67ecb-117">1億 (バイナリ) の10進値は256です (つまり、ビット8が設定されます)。</span><span class="sxs-lookup"><span data-stu-id="67ecb-117">100000000 (binary) has a decimal value of 256 (that is, bit 8 is set).</span></span>

  - <span data-ttu-id="67ecb-118">1100 (バイナリ) の10進値は12です (つまり、ビット2と3が設定され、両方のビットで表されるプロパティが有効になります)。</span><span class="sxs-lookup"><span data-stu-id="67ecb-118">1100 (binary) has a decimal value of 12 (that is, bits 2 and 3 are set; properties represented by both bits are enabled).</span></span>

  - <span data-ttu-id="67ecb-119">1111000001 (バイナリ) の10進値は961です (つまり、ビット0、6、7、8、9が設定され、これらの各ビットのプロパティが有効になります)。</span><span class="sxs-lookup"><span data-stu-id="67ecb-119">1111000001 (binary) has a decimal value of 961 (that is, bits 0, 6, 7, 8, and 9 are set; properties for each of these bits are enabled).</span></span>

<div id="sectionSection0" class="section">

### <a name="schema-attributes-for-lync-server-2013"></a><span data-ttu-id="67ecb-120">Lync Server 2013 のスキーマの属性</span><span class="sxs-lookup"><span data-stu-id="67ecb-120">Schema Attributes for Lync Server 2013</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="67ecb-121">属性</span><span class="sxs-lookup"><span data-stu-id="67ecb-121">Attribute</span></span></th>
<th><span data-ttu-id="67ecb-122">説明</span><span class="sxs-lookup"><span data-stu-id="67ecb-122">Description</span></span></th>
<th><span data-ttu-id="67ecb-123">コメント</span><span class="sxs-lookup"><span data-stu-id="67ecb-123">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="67ecb-124">dnsHostName</span><span class="sxs-lookup"><span data-stu-id="67ecb-124">dnsHostName</span></span></p></td>
<td><p><span data-ttu-id="67ecb-125"><strong>MsRTCSIP</strong>と msRTCSIP の両方の<strong>サーバー</strong>クラスに関連付けられた、Active Directory ドメインサービスの既存の属性。</span><span class="sxs-lookup"><span data-stu-id="67ecb-125">An existing attribute in Active Directory Domain Services that is now associated with the <strong>msRTCSIP-Pool</strong> and <strong>msRTCSIP-MonitoringServer</strong> classes.</span></span> <span data-ttu-id="67ecb-126">この属性は、プールまたは監視サーバーの完全修飾ドメイン名 (FQDN) を指定します。</span><span class="sxs-lookup"><span data-stu-id="67ecb-126">This attribute specifies the fully qualified domain name (FQDN) of a pool or Monitoring Server.</span></span></p>
<p><span data-ttu-id="67ecb-127">各セグメントの有効な値は、63文字です。FQDN 全体の有効な値は、255文字です。</span><span class="sxs-lookup"><span data-stu-id="67ecb-127">A valid value for each segment is 63 characters; a valid value for the entire FQDN is 255 characters.</span></span></p></td>
<td><p><span data-ttu-id="67ecb-128">Microsoft Office Live Communications Server 2005 の新製品。</span><span class="sxs-lookup"><span data-stu-id="67ecb-128">New in Microsoft Office Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="67ecb-129">Msds-sourceobjectdn</span><span class="sxs-lookup"><span data-stu-id="67ecb-129">msDS-SourceObjectDN</span></span></p></td>
<td><p><span data-ttu-id="67ecb-130">この属性には、このオブジェクトに対応する別のフォレスト内のオブジェクトの識別名 (DN) の文字列表現が含まれています。</span><span class="sxs-lookup"><span data-stu-id="67ecb-130">This attribute contains the string representation of the distinguished name (DN) of the object in another forest that corresponds to this object.</span></span> <span data-ttu-id="67ecb-131">この属性は、配布グループの展開および自動出席に使用されます。</span><span class="sxs-lookup"><span data-stu-id="67ecb-131">This attribute is used for distribution group expansion and auto attendance.</span></span> <span data-ttu-id="67ecb-132">この属性は、Windows Server 2003 R2 用の既定の Active Directory スキーマで定義されています。</span><span class="sxs-lookup"><span data-stu-id="67ecb-132">This attribute is defined in the default Active Directory schema for Windows Server 2003 R2.</span></span></p>
<p><span data-ttu-id="67ecb-133">AD DS を Windows Server 2003 R2 にアップグレードしなくて済むように、Active Directory スキーマの準備により、Windows Server 2003 スキーマがこの属性定義で拡張されます。</span><span class="sxs-lookup"><span data-stu-id="67ecb-133">To avoid requiring an upgrade of AD DS to Windows Server 2003 R2, Active Directory schema preparation extends the Windows Server 2003 schema with this attribute definition.</span></span></p></td>
<td><p><span data-ttu-id="67ecb-134">Microsoft Office Communications Server 2007 の新製品。</span><span class="sxs-lookup"><span data-stu-id="67ecb-134">New in Microsoft Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="67ecb-135">msExchUCVoiceMailSettings</span><span class="sxs-lookup"><span data-stu-id="67ecb-135">msExchUCVoiceMailSettings</span></span></p></td>
<td><p><span data-ttu-id="67ecb-136">この複数値属性は、ボイスメール設定を保持します。</span><span class="sxs-lookup"><span data-stu-id="67ecb-136">This multi-valued attribute holds voice mail settings.</span></span> <span data-ttu-id="67ecb-137">この属性は、Exchange ユニファイドメッセージング (UM) と共有されます。</span><span class="sxs-lookup"><span data-stu-id="67ecb-137">This attribute is shared with Exchange Unified Messaging (UM).</span></span></p></td>
<td><p><span data-ttu-id="67ecb-138">Microsoft Lync Server 2010 の新製品。</span><span class="sxs-lookup"><span data-stu-id="67ecb-138">New in Microsoft Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="67ecb-139">msExchUserHoldPolicies</span><span class="sxs-lookup"><span data-stu-id="67ecb-139">msExchUserHoldPolicies</span></span></p></td>
<td><p><span data-ttu-id="67ecb-140">この複数値の属性には、ユーザーに適用される保持ポリシーの識別子が保持されます。</span><span class="sxs-lookup"><span data-stu-id="67ecb-140">This multi-value attribute holds identifiers for hold policies that apply to the user.</span></span> <span data-ttu-id="67ecb-141">この保持の間は、ユーザーのメールボックス アイテムが保持ポリシーに保存されます。</span><span class="sxs-lookup"><span data-stu-id="67ecb-141">Hold policies preserve mailbox items for the user for the duration of the hold.</span></span> <span data-ttu-id="67ecb-142">この属性は、Exchange 2013 と共有されます。</span><span class="sxs-lookup"><span data-stu-id="67ecb-142">This attribute is shared with Exchange 2013.</span></span></p></td>
<td><p><span data-ttu-id="67ecb-143">Lync Server 2013 の新。</span><span class="sxs-lookup"><span data-stu-id="67ecb-143">New in Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="67ecb-144">msRTCSIP-AcpInfo</span><span class="sxs-lookup"><span data-stu-id="67ecb-144">msRTCSIP-AcpInfo</span></span></p></td>
<td><p><span data-ttu-id="67ecb-145">この属性は、ユーザーの電話会議プロバイダーの情報を格納します。</span><span class="sxs-lookup"><span data-stu-id="67ecb-145">This attribute stores audio conferencing provider information for a user.</span></span></p></td>
<td><p><span data-ttu-id="67ecb-146">Lync Server 2010 の新。</span><span class="sxs-lookup"><span data-stu-id="67ecb-146">New in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="67ecb-147">msRTCSIP-ApplicationDestination</span><span class="sxs-lookup"><span data-stu-id="67ecb-147">msRTCSIP-ApplicationDestination</span></span></p></td>
<td><p><span data-ttu-id="67ecb-148">この属性は、アプリケーションの連絡先の信頼済みサービスエントリを指します。</span><span class="sxs-lookup"><span data-stu-id="67ecb-148">This attribute points to the trusted service entry for the application contact.</span></span></p></td>
<td><p><span data-ttu-id="67ecb-149">Microsoft Office Communications Server 2007 R2 の新製品。</span><span class="sxs-lookup"><span data-stu-id="67ecb-149">New in Microsoft Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="67ecb-150">msRTCSIP-ApplicationList</span><span class="sxs-lookup"><span data-stu-id="67ecb-150">msRTCSIP-ApplicationList</span></span></p></td>
<td><p><span data-ttu-id="67ecb-151">この属性には、アプリケーションサーバー上のホストされているアプリケーションの一覧が含まれています。</span><span class="sxs-lookup"><span data-stu-id="67ecb-151">This attribute contains a list of hosted applications on the application server.</span></span></p></td>
<td><p><span data-ttu-id="67ecb-152">Office Communications Server 2007 R2 の新製品。</span><span class="sxs-lookup"><span data-stu-id="67ecb-152">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="67ecb-153">msRTCSIP-ApplicationOptions</span><span class="sxs-lookup"><span data-stu-id="67ecb-153">msRTCSIP-ApplicationOptions</span></span></p></td>
<td><p><span data-ttu-id="67ecb-154">この属性は、アプリケーションの連絡先のオプションを指定します。</span><span class="sxs-lookup"><span data-stu-id="67ecb-154">This attribute specifies the options for the application contact.</span></span></p></td>
<td><p><span data-ttu-id="67ecb-155">Office Communications Server 2007 R2 の新製品。</span><span class="sxs-lookup"><span data-stu-id="67ecb-155">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="67ecb-156">msRTCSIP-ApplicationPrimaryLanguage</span><span class="sxs-lookup"><span data-stu-id="67ecb-156">msRTCSIP-ApplicationPrimaryLanguage</span></span></p></td>
<td><p><span data-ttu-id="67ecb-157">この属性には、アプリケーションの連絡先の第1言語が含まれています。</span><span class="sxs-lookup"><span data-stu-id="67ecb-157">This attribute contains the primary language for the application contact.</span></span></p></td>
<td><p><span data-ttu-id="67ecb-158">Office Communications Server 2007 R2 の新製品。</span><span class="sxs-lookup"><span data-stu-id="67ecb-158">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="67ecb-159">msRTCSIP-ApplicationSecondaryLanguages</span><span class="sxs-lookup"><span data-stu-id="67ecb-159">msRTCSIP-ApplicationSecondaryLanguages</span></span></p></td>
<td><p><span data-ttu-id="67ecb-160">この複数値の属性には、アプリケーションの連絡先の第2言語が含まれています。</span><span class="sxs-lookup"><span data-stu-id="67ecb-160">This multiple value attribute contains the secondary languages for the application contact.</span></span></p></td>
<td><p><span data-ttu-id="67ecb-161">Office Communications Server 2007 R2 の新製品。</span><span class="sxs-lookup"><span data-stu-id="67ecb-161">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="67ecb-162">msRTCSIP-ApplicationServerBL</span><span class="sxs-lookup"><span data-stu-id="67ecb-162">msRTCSIP-ApplicationServerBL</span></span></p></td>
<td><p><span data-ttu-id="67ecb-163">この属性には、このプールに属するアプリケーションサーバーの一覧が含まれています。</span><span class="sxs-lookup"><span data-stu-id="67ecb-163">This attribute contains a list of application servers that belong to this pool.</span></span> <span data-ttu-id="67ecb-164">この後方リンク属性への対応する転送リンクは、 <strong>MsRTCSIP Serverpoollink</strong>です。</span><span class="sxs-lookup"><span data-stu-id="67ecb-164">The corresponding forward link to this back link attribute is <strong>msRTCSIP-ApplicationServerPoolLink</strong>.</span></span></p></td>
<td><p><span data-ttu-id="67ecb-165">Office Communications Server 2007 R2 の新製品。</span><span class="sxs-lookup"><span data-stu-id="67ecb-165">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="67ecb-166">msRTCSIP-ApplicationServerPoolLink</span><span class="sxs-lookup"><span data-stu-id="67ecb-166">msRTCSIP-ApplicationServerPoolLink</span></span></p></td>
<td><p><span data-ttu-id="67ecb-167">この属性は、このアプリケーションサーバーが属するプールを指します。</span><span class="sxs-lookup"><span data-stu-id="67ecb-167">This attribute points to the pool to which this application server belongs.</span></span> <span data-ttu-id="67ecb-168">これは、前方リンクです。</span><span class="sxs-lookup"><span data-stu-id="67ecb-168">This is the forward link.</span></span> <span data-ttu-id="67ecb-169">対応する後方リンクは、 <strong>MsRTCSIP Serverbl</strong>です。</span><span class="sxs-lookup"><span data-stu-id="67ecb-169">The corresponding backward link is <strong>msRTCSIP-ApplicationServerBL</strong>.</span></span></p></td>
<td><p><span data-ttu-id="67ecb-170">Office Communications Server 2007 R2 の新製品。</span><span class="sxs-lookup"><span data-stu-id="67ecb-170">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="67ecb-171">msRTCSIP-アーカイブ既定 (現在不使用)</span><span class="sxs-lookup"><span data-stu-id="67ecb-171">msRTCSIP-ArchiveDefault (obsolete)</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="67ecb-172">Live Communications Server 2005 の新しいもの。</span><span class="sxs-lookup"><span data-stu-id="67ecb-172">New in Live Communications Server 2005.</span></span></p>
<p><span data-ttu-id="67ecb-173">Office Communications Server 2007 では廃止されました。</span><span class="sxs-lookup"><span data-stu-id="67ecb-173">Obsolete in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="67ecb-174">msRTCSIP-アーカイブ Defaultflags (現在不使用)</span><span class="sxs-lookup"><span data-stu-id="67ecb-174">msRTCSIP-ArchiveDefaultFlags (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="67ecb-175">この属性は、すべてのユーザー通信をアーカイブするためのフォレスト境界内でのグローバルな既定値を指定します。</span><span class="sxs-lookup"><span data-stu-id="67ecb-175">This attribute specifies the global default within the forest boundary for archiving all user communications.</span></span> <span data-ttu-id="67ecb-176">これは、アーカイブエージェントレイヤーによって適用されます。</span><span class="sxs-lookup"><span data-stu-id="67ecb-176">This is enforced by the archiving agent layer.</span></span> <span data-ttu-id="67ecb-177">この属性の値の範囲は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="67ecb-177">The range of values for this attribute is as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="67ecb-178"><strong>TRUE</strong>: すべてのユーザーをアーカイブする</span><span class="sxs-lookup"><span data-stu-id="67ecb-178"><strong>TRUE</strong>: Archive all users</span></span></p></li>
<li><p><span data-ttu-id="67ecb-179"><strong>FALSE</strong>: すべてのユーザーをアーカイブしない</span><span class="sxs-lookup"><span data-stu-id="67ecb-179"><strong>FALSE</strong>: Do not archive all users</span></span></p></li>
</ul>
<p><span data-ttu-id="67ecb-180">この属性は、内部ネットワーク内でのユーザー通信のアーカイブ方法をフォレスト境界内でグローバルに制御します。</span><span class="sxs-lookup"><span data-stu-id="67ecb-180">This attribute globally controls, within the forest boundary, how user communications within an internal network are archived.</span></span></p>
<p><span data-ttu-id="67ecb-181"><strong>Live Communications Server 2005 の動作 (現在は廃止)</strong></span><span class="sxs-lookup"><span data-stu-id="67ecb-181"><strong>Live Communications Server 2005 behavior (now retired)</strong></span></span></p>
<p><span data-ttu-id="67ecb-182">この属性の値の範囲は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="67ecb-182">The range of values for this attribute is as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="67ecb-183">0: メッセージ本文をアーカイブする [ビット 0]</span><span class="sxs-lookup"><span data-stu-id="67ecb-183">0: Archive the message body [bit 0]</span></span></p></li>
<li><p><span data-ttu-id="67ecb-184">1: メッセージ本文をアーカイブしない [ビット 0]</span><span class="sxs-lookup"><span data-stu-id="67ecb-184">1: Do not archive the message body [bit 0]</span></span></p></li>
</ul>
<p><span data-ttu-id="67ecb-185"><strong>Office Communications Server 2007 の動作</strong></span><span class="sxs-lookup"><span data-stu-id="67ecb-185"><strong>Office Communications Server 2007 behavior</strong></span></span></p>
<p><span data-ttu-id="67ecb-186">この属性の値の範囲は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="67ecb-186">The range of values for this attribute is as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="67ecb-187">0: ArchiveFederationDefaultWithoutBody (廃止)</span><span class="sxs-lookup"><span data-stu-id="67ecb-187">0: ArchiveFederationDefaultWithoutBody (retired)</span></span></p></li>
<li><p><span data-ttu-id="67ecb-188">1-2: アーカイブ Internalcommunications</span><span class="sxs-lookup"><span data-stu-id="67ecb-188">1-2: ArchiveInternalCommunications</span></span></p></li>
<li><p><span data-ttu-id="67ecb-189">3-4: ArchiveFederatedCommunications</span><span class="sxs-lookup"><span data-stu-id="67ecb-189">3-4: ArchiveFederatedCommunications</span></span></p></li>
<li><p><span data-ttu-id="67ecb-190">5: RecordPresenceRegistrations</span><span class="sxs-lookup"><span data-stu-id="67ecb-190">5: RecordPresenceRegistrations</span></span></p></li>
<li><p><span data-ttu-id="67ecb-191">6: RecordIMCallDetails</span><span class="sxs-lookup"><span data-stu-id="67ecb-191">6: RecordIMCallDetails</span></span></p></li>
<li><p><span data-ttu-id="67ecb-192">7: RecordGroupIMCallDetails</span><span class="sxs-lookup"><span data-stu-id="67ecb-192">7: RecordGroupIMCallDetails</span></span></p></li>
<li><p><span data-ttu-id="67ecb-193">8: RecordFileTransferInstances</span><span class="sxs-lookup"><span data-stu-id="67ecb-193">8: RecordFileTransferInstances</span></span></p></li>
<li><p><span data-ttu-id="67ecb-194">9: RecordAudioCallDetails</span><span class="sxs-lookup"><span data-stu-id="67ecb-194">9: RecordAudioCallDetails</span></span></p></li>
<li><p><span data-ttu-id="67ecb-195">10: RecordVideoCallDetails</span><span class="sxs-lookup"><span data-stu-id="67ecb-195">10: RecordVideoCallDetails</span></span></p></li>
<li><p><span data-ttu-id="67ecb-196">11: RecordRemoteAssistanceCallDetails</span><span class="sxs-lookup"><span data-stu-id="67ecb-196">11: RecordRemoteAssistanceCallDetails</span></span></p></li>
<li><p><span data-ttu-id="67ecb-197">12: RecordApplicationSharingDetails</span><span class="sxs-lookup"><span data-stu-id="67ecb-197">12: RecordApplicationSharingDetails</span></span></p></li>
<li><p><span data-ttu-id="67ecb-198">13: レコードの会議のインスタンス化</span><span class="sxs-lookup"><span data-stu-id="67ecb-198">13: RecordMeetingInstantiations</span></span></p></li>
<li><p><span data-ttu-id="67ecb-199">14: レコード会議の結合</span><span class="sxs-lookup"><span data-stu-id="67ecb-199">14: RecordMeetingJoins</span></span></p></li>
<li><p><span data-ttu-id="67ecb-200">15: RecordDataJoins</span><span class="sxs-lookup"><span data-stu-id="67ecb-200">15: RecordDataJoins</span></span></p></li>
<li><p><span data-ttu-id="67ecb-201">16: RecordAVJoins</span><span class="sxs-lookup"><span data-stu-id="67ecb-201">16: RecordAVJoins</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="67ecb-202">Live Communications Server 2005 の新しいもの。</span><span class="sxs-lookup"><span data-stu-id="67ecb-202">New in Live Communications Server 2005.</span></span></p>
<p><span data-ttu-id="67ecb-203">Lync Server 2010 では廃止されました。</span><span class="sxs-lookup"><span data-stu-id="67ecb-203">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="67ecb-204">msRTCSIP-Msrtcsip-archivefederationdefault (現在不使用)</span><span class="sxs-lookup"><span data-stu-id="67ecb-204">msRTCSIP-ArchiveFederationDefault (obsolete)</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="67ecb-205">Live Communications Server 2005 の新しいもの。</span><span class="sxs-lookup"><span data-stu-id="67ecb-205">New in Live Communications Server 2005.</span></span></p>
<p><span data-ttu-id="67ecb-206">Office Communications Server 2007 では廃止されました。</span><span class="sxs-lookup"><span data-stu-id="67ecb-206">Obsolete in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="67ecb-207">msRTCSIP-Msrtcsip-archivefederationdefaultflags (現在不使用)</span><span class="sxs-lookup"><span data-stu-id="67ecb-207">msRTCSIP-ArchiveFederationDefaultFlags (obsolete)</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="67ecb-208">Live Communications Server 2005 の新しいもの。</span><span class="sxs-lookup"><span data-stu-id="67ecb-208">New in Live Communications Server 2005.</span></span></p>
<p><span data-ttu-id="67ecb-209">Office Communications Server 2007 では廃止されました。</span><span class="sxs-lookup"><span data-stu-id="67ecb-209">Obsolete in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="67ecb-210">msRTCSIP-ArchivingEnabled</span><span class="sxs-lookup"><span data-stu-id="67ecb-210">msRTCSIP-ArchivingEnabled</span></span></p></td>
<td><p><span data-ttu-id="67ecb-211">この属性は、1人のユーザーの通信をアーカイブするかどうかを制御するためのビットフィールドとして使用される整数です。</span><span class="sxs-lookup"><span data-stu-id="67ecb-211">This attribute is an integer used as a bit field to control whether a single user’s communications are to be archived.</span></span> <span data-ttu-id="67ecb-212">このコントロールは、アーカイブエージェントレイヤーによって適用されます。</span><span class="sxs-lookup"><span data-stu-id="67ecb-212">This control is enforced by the archiving agent layer.</span></span> <span data-ttu-id="67ecb-213">グローバルカタログレプリケーションのマークが付いています。</span><span class="sxs-lookup"><span data-stu-id="67ecb-213">It is marked for global catalog replication.</span></span></p>
<p><span data-ttu-id="67ecb-214">この属性のスコープは、1人のユーザーまたは連絡先に固有です。</span><span class="sxs-lookup"><span data-stu-id="67ecb-214">The scope of this attribute is specific to a single user or contact.</span></span> <span data-ttu-id="67ecb-215">Lync Server での有効な値 (および関連するビット位置) は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="67ecb-215">The valid values (and associated bit positions) in Lync Server are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="67ecb-216">0: アーカイブしない (ビットセットなし)</span><span class="sxs-lookup"><span data-stu-id="67ecb-216">0: Do not archive (no bit set)</span></span></p></li>
<li><p><span data-ttu-id="67ecb-217">1: 廃止 (ビット位置 0)</span><span class="sxs-lookup"><span data-stu-id="67ecb-217">1: Retired (bit position 0)</span></span></p></li>
<li><p><span data-ttu-id="67ecb-218">2: 廃止 (ビット位置 1)</span><span class="sxs-lookup"><span data-stu-id="67ecb-218">2: Retired (bit position 1)</span></span></p></li>
<li><p><span data-ttu-id="67ecb-219">4: 内部通信のアーカイブ (ビット位置 2)</span><span class="sxs-lookup"><span data-stu-id="67ecb-219">4: Archive internal communications (bit position 2)</span></span></p></li>
<li><p><span data-ttu-id="67ecb-220">8: フェデレーション通信のアーカイブ (ビット位置 3)</span><span class="sxs-lookup"><span data-stu-id="67ecb-220">8: Archive federated communications (bit position 3)</span></span></p></li>
</ul>
<p><span data-ttu-id="67ecb-221">Live Communications Server 2005 の以前の有効な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="67ecb-221">Previously valid values in Live Communications Server 2005 are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="67ecb-222">0: <strong>msRTCSIP</strong>によって定義されている既定値<strong>を使用</strong>します。既定値は、この優先順位に従っています。</span><span class="sxs-lookup"><span data-stu-id="67ecb-222">0:Use the default value defined by <strong>msRTCSIP-ArchiveDefault</strong> and <strong>msRTCSIP-ArchiveFederation</strong> in this order of precedence:</span></span></p>
<ul>
<li><p><span data-ttu-id="67ecb-223">1: アーカイブ</span><span class="sxs-lookup"><span data-stu-id="67ecb-223">1: Archive</span></span></p></li>
<li><p><span data-ttu-id="67ecb-224">2: アーカイブしない</span><span class="sxs-lookup"><span data-stu-id="67ecb-224">2: Do not archive</span></span></p></li>
<li><p><span data-ttu-id="67ecb-225">3: メッセージ本文を含まないアーカイブ</span><span class="sxs-lookup"><span data-stu-id="67ecb-225">3: Archive without the message body</span></span></p></li>
</ul></li>
</ul></td>
<td><p><span data-ttu-id="67ecb-226">Live Communications Server 2005 の新しいもの。</span><span class="sxs-lookup"><span data-stu-id="67ecb-226">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="67ecb-227">msRTCSIP-Msrtcsip-archivingserverdata (現在不使用)</span><span class="sxs-lookup"><span data-stu-id="67ecb-227">msRTCSIP-ArchivingServerData (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="67ecb-228">この属性は、今後の使用のために予約されています。</span><span class="sxs-lookup"><span data-stu-id="67ecb-228">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="67ecb-229">Lync Server 2010 では廃止されました。</span><span class="sxs-lookup"><span data-stu-id="67ecb-229">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="67ecb-230">msRTCSIP-Msrtcsip-archivingserverversion (現在不使用)</span><span class="sxs-lookup"><span data-stu-id="67ecb-230">msRTCSIP-ArchivingServerVersion (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="67ecb-231">この属性は、アーカイブサービスのバージョンを定義します。</span><span class="sxs-lookup"><span data-stu-id="67ecb-231">This attribute defines the version of the Archiving service.</span></span> <span data-ttu-id="67ecb-232">この属性は、公式の製品リリースごとにインクリメントする monotonously 増加整数型です。</span><span class="sxs-lookup"><span data-stu-id="67ecb-232">This attribute is a monotonously increasing integer type that increments with each official product release.</span></span> <span data-ttu-id="67ecb-233">有効な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="67ecb-233">The possible valid values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="67ecb-234">Undefined: Live Communications Server 2003</span><span class="sxs-lookup"><span data-stu-id="67ecb-234">Undefined: Live Communications Server 2003</span></span></p>
<p><span data-ttu-id="67ecb-235">                 Live Communications Server 2005</span><span class="sxs-lookup"><span data-stu-id="67ecb-235">                 Live Communications Server 2005</span></span></p>
<p><span data-ttu-id="67ecb-236">                 Live Communications Server 2005 with SP1</span><span class="sxs-lookup"><span data-stu-id="67ecb-236">                 Live Communications Server 2005 with SP1</span></span></p></li>
<li><p><span data-ttu-id="67ecb-237">3: Office Communications Server 2007</span><span class="sxs-lookup"><span data-stu-id="67ecb-237">3: Office Communications Server 2007</span></span></p></li>
<li><p><span data-ttu-id="67ecb-238">4: Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="67ecb-238">4: Office Communications Server 2007 R2</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="67ecb-239">Office Communications Server 2007 の新製品。</span><span class="sxs-lookup"><span data-stu-id="67ecb-239">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="67ecb-240">Lync Server 2010 では廃止されました。</span><span class="sxs-lookup"><span data-stu-id="67ecb-240">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="67ecb-241">msRTCSIP-BackEndServer</span><span class="sxs-lookup"><span data-stu-id="67ecb-241">msRTCSIP-BackEndServer</span></span></p></td>
<td><p><span data-ttu-id="67ecb-242">この属性は、プールのバックエンドサーバーの FQDN を指定します。</span><span class="sxs-lookup"><span data-stu-id="67ecb-242">This attribute specifies the FQDN of the Back End Server of the pool.</span></span> <span data-ttu-id="67ecb-243">プールごとに1つのバックエンドサーバーしか存在できないため、これは単一値の属性です。</span><span class="sxs-lookup"><span data-stu-id="67ecb-243">Because there can only be a single Back End Server per pool, this is a single-valued attribute.</span></span></p>
<p><span data-ttu-id="67ecb-244">各セグメントの有効な値は、63文字です。FQDN 全体の有効な値は255文字です。</span><span class="sxs-lookup"><span data-stu-id="67ecb-244">The valid value for each segment is 63 characters; the valid value for the entire FQDN is 255 characters.</span></span></p></td>
<td><p><span data-ttu-id="67ecb-245">Live Communications Server 2005 の新しいもの。</span><span class="sxs-lookup"><span data-stu-id="67ecb-245">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="67ecb-246">msRTCSIP-ConferenceDirectoryHomePool</span><span class="sxs-lookup"><span data-stu-id="67ecb-246">msRTCSIP-ConferenceDirectoryHomePool</span></span></p></td>
<td><p><span data-ttu-id="67ecb-247">この属性には、会議ディレクトリをホストするプールの識別子が含まれます。</span><span class="sxs-lookup"><span data-stu-id="67ecb-247">This attribute contains the identifier of the pool that hosts the conference directory.</span></span></p></td>
<td><p><span data-ttu-id="67ecb-248">Office Communications Server 2007 R2 の新製品。</span><span class="sxs-lookup"><span data-stu-id="67ecb-248">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="67ecb-249">msRTCSIP-ConferenceDirectoryId</span><span class="sxs-lookup"><span data-stu-id="67ecb-249">msRTCSIP-ConferenceDirectoryId</span></span></p></td>
<td><p><span data-ttu-id="67ecb-250">この属性には、会議ディレクトリの識別子が含まれています。</span><span class="sxs-lookup"><span data-stu-id="67ecb-250">This attribute contains the identifier of a conference directory.</span></span></p></td>
<td><p><span data-ttu-id="67ecb-251">Office Communications Server 2007 R2 の新製品。</span><span class="sxs-lookup"><span data-stu-id="67ecb-251">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="67ecb-252">msRTCSIP-ConferenceDirectoryTargetPool</span><span class="sxs-lookup"><span data-stu-id="67ecb-252">msRTCSIP-ConferenceDirectoryTargetPool</span></span></p></td>
<td><p><span data-ttu-id="67ecb-253">この属性には、会議ディレクトリの移動先のプールの識別子が含まれます。</span><span class="sxs-lookup"><span data-stu-id="67ecb-253">This attribute contains the identifier of the pool to which the conference directory is being moved.</span></span></p></td>
<td><p><span data-ttu-id="67ecb-254">Office Communications Server 2007 R2 の新製品。</span><span class="sxs-lookup"><span data-stu-id="67ecb-254">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="67ecb-255">msRTCSIP-既定値</span><span class="sxs-lookup"><span data-stu-id="67ecb-255">msRTCSIP-Default</span></span></p></td>
<td><p><span data-ttu-id="67ecb-256">このブール値属性は、電話の使用法が既定の使用方法であるかどうかを定義します。</span><span class="sxs-lookup"><span data-stu-id="67ecb-256">This Boolean attribute defines whether the phone usage is a default usage.</span></span> <span data-ttu-id="67ecb-257">この属性が<strong>TRUE</strong>に設定されている場合、電話使用法は既定の使用方法であり、管理者が削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="67ecb-257">If this attribute is set to <strong>TRUE</strong>, the phone usage is a default usage and cannot be deleted by the administrator.</span></span> <span data-ttu-id="67ecb-258">この属性が<strong>FALSE</strong>に設定されている場合は、使用法を削除できます。</span><span class="sxs-lookup"><span data-stu-id="67ecb-258">If this attribute is set to <strong>FALSE</strong>, the usage can be deleted.</span></span></p></td>
<td><p><span data-ttu-id="67ecb-259">Office Communications Server 2007 の新製品。</span><span class="sxs-lookup"><span data-stu-id="67ecb-259">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="67ecb-260">msRTCSIP-DefaultCWAExternalURL</span><span class="sxs-lookup"><span data-stu-id="67ecb-260">msRTCSIP-DefaultCWAExternalURL</span></span></p></td>
<td><p><span data-ttu-id="67ecb-261">この属性は、組織外のユーザーの Communicator Web Access URL を識別します。</span><span class="sxs-lookup"><span data-stu-id="67ecb-261">This attribute identifies the Communicator Web Access URL for users who are outside the organization.</span></span></p></td>
<td><p><span data-ttu-id="67ecb-262">Office Communications Server 2007 R2 の新製品。</span><span class="sxs-lookup"><span data-stu-id="67ecb-262">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="67ecb-263">msRTCSIP-DefaultCWAInternalURL</span><span class="sxs-lookup"><span data-stu-id="67ecb-263">msRTCSIP-DefaultCWAInternalURL</span></span></p></td>
<td><p><span data-ttu-id="67ecb-264">この属性は、組織内のユーザーの Communicator Web Access URL を識別します。</span><span class="sxs-lookup"><span data-stu-id="67ecb-264">This attribute identifies the Communicator Web Access URL for users who are inside the organization.</span></span></p></td>
<td><p><span data-ttu-id="67ecb-265">Office Communications Server 2007 R2 の新製品。</span><span class="sxs-lookup"><span data-stu-id="67ecb-265">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="67ecb-266">msRTCSIP-DefaultLocationProfileLink (現在不使用)</span><span class="sxs-lookup"><span data-stu-id="67ecb-266">msRTCSIP-DefaultLocationProfileLink (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="67ecb-267">この単一値属性には、割り当てられている場所プロファイルクラスオブジェクトの識別名 (DN) が含まれています。</span><span class="sxs-lookup"><span data-stu-id="67ecb-267">This single-valued attribute contains the distinguished name (DN) of a location profile class object assigned to it.</span></span></p>
<p><span data-ttu-id="67ecb-268">前方リンク:<strong>リンク ID 11036</strong></span><span class="sxs-lookup"><span data-stu-id="67ecb-268">Forward link: <strong>Link ID 11036</strong></span></span></p>
<p><span data-ttu-id="67ecb-269">対応する後方リンクは、 <strong>msRTCSIP-ServerReferenceBL</strong>です。</span><span class="sxs-lookup"><span data-stu-id="67ecb-269">The corresponding backward link is <strong>msRTCSIP-ServerReferenceBL</strong>.</span></span></p></td>
<td><p><span data-ttu-id="67ecb-270">Lync Server 2010 では廃止されました。</span><span class="sxs-lookup"><span data-stu-id="67ecb-270">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="67ecb-271">msRTCSIP-DefaultPolicy (現在不使用)</span><span class="sxs-lookup"><span data-stu-id="67ecb-271">msRTCSIP-DefaultPolicy (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="67ecb-272">このブール属性は、ポリシーが既定のポリシーであるかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="67ecb-272">This Boolean attribute specifies whether the policy is a default policy.</span></span> <span data-ttu-id="67ecb-273">ポリシーは、 <strong>TRUE</strong>に設定されている場合の既定のポリシーです。</span><span class="sxs-lookup"><span data-stu-id="67ecb-273">The policy is a default policy when set to <strong>TRUE</strong>.</span></span></p></td>
<td><p><span data-ttu-id="67ecb-274">Office Communications Server 2007 の新製品</span><span class="sxs-lookup"><span data-stu-id="67ecb-274">New in Office Communications Server 2007</span></span></p>
<p><span data-ttu-id="67ecb-275">Lync Server 2010 では廃止されました。</span><span class="sxs-lookup"><span data-stu-id="67ecb-275">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="67ecb-276">msRTCSIP-Msrtcsip-defaultroutetoedgeproxy (現在不使用)</span><span class="sxs-lookup"><span data-stu-id="67ecb-276">msRTCSIP-DefaultRouteToEdgeProxy (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="67ecb-277">この属性は、アクセスエッジサービスを実行しているエッジサーバーの FQDN、アクセス可能な場合は、アクセスエッジサービスを実行しているサーバーのプールのハードウェアロードバランサーの FQDN を指定します。</span><span class="sxs-lookup"><span data-stu-id="67ecb-277">This attribute specifies the FQDN of either the Edge Server running the Access Edge service, if it can be accessed directly, or of the hardware load balancer for a pool of servers running Access Edge service.</span></span> <span data-ttu-id="67ecb-278">アクセスエッジサービスを実行しているサーバーが1つまたは複数のディレクターを介してのみアクセスできる場合は、この属性によって、ディレクターの FQDN、およびオプションとして、ディレクタープールを提供するディレクターまたはハードウェアロードバランサーのポート番号が指定されます。</span><span class="sxs-lookup"><span data-stu-id="67ecb-278">If the servers running Access Edge service can be accessed only through one or more Directors, this attribute specifies the FQDN and, optionally, the port number of the Director or of the hardware load balancer serving a Director pool.</span></span></p>
<p><span data-ttu-id="67ecb-279">各セグメントの有効な値は、63文字です。FQDN 全体の有効な値は255文字です。</span><span class="sxs-lookup"><span data-stu-id="67ecb-279">The valid value for each segment is 63 characters; the valid value for the entire FQDN is 255 characters.</span></span></p></td>
<td><p><span data-ttu-id="67ecb-280">Live Communications Server 2005 の新しいもの。</span><span class="sxs-lookup"><span data-stu-id="67ecb-280">New in Live Communications Server 2005.</span></span></p>
<p><span data-ttu-id="67ecb-281">Lync Server 2010 では廃止されました。</span><span class="sxs-lookup"><span data-stu-id="67ecb-281">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="67ecb-282">msRTCSIP-Msrtcsip-defaultroutetoedgeproxyport (現在不使用)</span><span class="sxs-lookup"><span data-stu-id="67ecb-282">msRTCSIP-DefaultRouteToEdgeProxyPort (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="67ecb-283">この属性は、アクセスエッジサービスを実行しているサーバーに接続するために使用されるポート番号を表します。</span><span class="sxs-lookup"><span data-stu-id="67ecb-283">This attribute represents the port number that should be used to connect to the server running Access Edge service.</span></span></p>
<p><span data-ttu-id="67ecb-284">有効な値は、使用するポートを指定する整数型 (integer) の値です。</span><span class="sxs-lookup"><span data-stu-id="67ecb-284">The valid value is an integer value specifying the port to be used.</span></span> <span data-ttu-id="67ecb-285">既定値は 5061 です。</span><span class="sxs-lookup"><span data-stu-id="67ecb-285">The default value is 5061.</span></span></p></td>
<td><p><span data-ttu-id="67ecb-286">Live Communications Server 2005 の新しいもの。</span><span class="sxs-lookup"><span data-stu-id="67ecb-286">New in Live Communications Server 2005.</span></span></p>
<p><span data-ttu-id="67ecb-287">Lync Server 2010 では廃止されました。</span><span class="sxs-lookup"><span data-stu-id="67ecb-287">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="67ecb-288">msRTCSIP-Msrtcsip-defpresencesubscriptiontimeout (現在不使用)</span><span class="sxs-lookup"><span data-stu-id="67ecb-288">msRTCSIP-DefPresenceSubscriptionTimeout (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="67ecb-289">既定のプレゼンスサブスクリプションタイムアウト期間を表す属性です。</span><span class="sxs-lookup"><span data-stu-id="67ecb-289">This attribute represents the default presence subscription time-out period.</span></span></p></td>
<td><p><span data-ttu-id="67ecb-290">Lync Server 2010 では廃止されました。</span><span class="sxs-lookup"><span data-stu-id="67ecb-290">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="67ecb-291">msRTCSIP-DefRegistrationTimeout (obsolete)</span><span class="sxs-lookup"><span data-stu-id="67ecb-291">msRTCSIP-DefRegistrationTimeout (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="67ecb-292">既定の登録タイムアウト期間を表す属性です。</span><span class="sxs-lookup"><span data-stu-id="67ecb-292">This attribute represents the default registration time-out window.</span></span></p></td>
<td><p><span data-ttu-id="67ecb-293">Lync Server 2010 では廃止されました。</span><span class="sxs-lookup"><span data-stu-id="67ecb-293">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="67ecb-294">msRTCSIP-Msrtcsip-defroamingdatasubscriptiontimeout (現在不使用)</span><span class="sxs-lookup"><span data-stu-id="67ecb-294">msRTCSIP-DefRoamingDataSubscriptionTimeout (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="67ecb-295">既定の移動データサブスクリプションタイムアウト期間を表す属性です。</span><span class="sxs-lookup"><span data-stu-id="67ecb-295">This attribute represents the default roaming data subscription time-out window.</span></span></p></td>
<td><p><span data-ttu-id="67ecb-296">Lync Server 2010 では廃止されました。</span><span class="sxs-lookup"><span data-stu-id="67ecb-296">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="67ecb-297">msRTCSIP-DeploymentLocator</span><span class="sxs-lookup"><span data-stu-id="67ecb-297">msRTCSIP-DeploymentLocator</span></span></p></td>
<td><p><span data-ttu-id="67ecb-298">この属性は、分割ドメイントポロジで使用され、完全修飾ドメイン名 (FQDN) を含みます。</span><span class="sxs-lookup"><span data-stu-id="67ecb-298">This attribute is used in a split domain topology and contains a fully qualified domain name (FQDN).</span></span></p></td>
<td><p><span data-ttu-id="67ecb-299">Lync Server 2010 の新。</span><span class="sxs-lookup"><span data-stu-id="67ecb-299">New in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="67ecb-300">msRTCSIP-Description (現在不使用)</span><span class="sxs-lookup"><span data-stu-id="67ecb-300">msRTCSIP-Description (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="67ecb-301">この電話ルートまたは正規化ルールのわかりやすい説明を含む単一値の UNICODE 文字列属性です。</span><span class="sxs-lookup"><span data-stu-id="67ecb-301">This single-valued UNICODE string attribute contains a friendly description of this phone route or normalization rule.</span></span></p></td>
<td><p><span data-ttu-id="67ecb-302">Office Communications Server 2007 の新製品。</span><span class="sxs-lookup"><span data-stu-id="67ecb-302">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="67ecb-303">Lync Server 2010 では廃止されました。</span><span class="sxs-lookup"><span data-stu-id="67ecb-303">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="67ecb-304">msRTCSIP-DomainData</span><span class="sxs-lookup"><span data-stu-id="67ecb-304">msRTCSIP-DomainData</span></span></p></td>
<td><p><span data-ttu-id="67ecb-305">この属性は、今後の使用のために予約されています。</span><span class="sxs-lookup"><span data-stu-id="67ecb-305">This attribute is reserved for future use.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="67ecb-306">msRTCSIP-DomainName</span><span class="sxs-lookup"><span data-stu-id="67ecb-306">msRTCSIP-DomainName</span></span></p></td>
<td><p><span data-ttu-id="67ecb-307">レジストラーに対して構成されたドメインを表す属性です。</span><span class="sxs-lookup"><span data-stu-id="67ecb-307">This attribute represents a domain configured for the Registrar.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="67ecb-308">msRTCSIP-EdgeProxyData</span><span class="sxs-lookup"><span data-stu-id="67ecb-308">msRTCSIP-EdgeProxyData</span></span></p></td>
<td><p><span data-ttu-id="67ecb-309">この属性は、今後の使用のために予約されています。</span><span class="sxs-lookup"><span data-stu-id="67ecb-309">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="67ecb-310">Live Communications Server 2005 の新しいもの。</span><span class="sxs-lookup"><span data-stu-id="67ecb-310">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="67ecb-311">msRTCSIP-EdgeProxyFQDN</span><span class="sxs-lookup"><span data-stu-id="67ecb-311">msRTCSIP-EdgeProxyFQDN</span></span></p></td>
<td><p><span data-ttu-id="67ecb-312">この属性は、アクセスエッジサービスを実行しているサーバーの FQDN を指定します。</span><span class="sxs-lookup"><span data-stu-id="67ecb-312">This attribute specifies the FQDN of the server running Access Edge service.</span></span></p>
<p><span data-ttu-id="67ecb-313">各セグメントの有効な値は、63文字です。FQDN 全体の有効な値は255文字です。</span><span class="sxs-lookup"><span data-stu-id="67ecb-313">The valid value for each segment is 63 characters; the valid value for the entire FQDN is 255 characters.</span></span></p></td>
<td><p><span data-ttu-id="67ecb-314">Live Communications Server 2005 の新しいもの。</span><span class="sxs-lookup"><span data-stu-id="67ecb-314">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="67ecb-315">msRTCSIP-Msrtcsip-enablebesteffortnotify (現在不使用)</span><span class="sxs-lookup"><span data-stu-id="67ecb-315">msRTCSIP-EnableBestEffortNotify (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="67ecb-316">この属性は、クライアントからのサブスクライブ要求に対する応答として、サーバーが NOTIFY 要求ではなく、Best エフォート NOTIFY (BENOTIFY) 要求を生成するかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="67ecb-316">This attribute controls whether a server generates a Best Effort NOTIFY (BENOTIFY) request, instead of a NOTIFY request, in response to a SUBSCRIBE request from a client.</span></span> <span data-ttu-id="67ecb-317">BENOTIFY は、定期的な NOTIFY 要求ではなく、サーバーが BENOTIFY 要求を生成するサブスクライブ通知ハンドシェイクに対して、パフォーマンスが強化された拡張機能です。</span><span class="sxs-lookup"><span data-stu-id="67ecb-317">BENOTIFY is a performance-enhancing extension to the subscribe notification handshake where the server generates BENOTIFY requests, instead of regular NOTIFY requests.</span></span> <span data-ttu-id="67ecb-318">パフォーマンス上の利点として、NOTIFY 要求と同様に、BENOTIFY 要求でクライアントから 200 OK 応答が要求されないことが挙げられます。</span><span class="sxs-lookup"><span data-stu-id="67ecb-318">The performance benefit is that a BENOTIFY request does not require a 200 OK response from the client as the NOTIFY request does.</span></span></p>
<p><span data-ttu-id="67ecb-319">有効な値は、 <strong>TRUE</strong>または<strong>FALSE</strong>です。</span><span class="sxs-lookup"><span data-stu-id="67ecb-319">The valid values are <strong>TRUE</strong> or <strong>FALSE</strong>.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="67ecb-320">Live Communications Server 2003 は、BENOTIFY 要求をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="67ecb-320">Live Communications Server 2003 does not support BENOTIFY requests.</span></span> <span data-ttu-id="67ecb-321">Live Communications Server 2005 およびサードパーティ製サーバーで実行されている Live Communications Server 2003 サーバー API を使用して記述されたサーバーアプリケーションと相互運用するには、BENOTIFY 要求の値を<STRONG>FALSE</STRONG>に設定することで無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="67ecb-321">To interoperate with server applications written with the Live Communications Server 2003 server API running on Live Communications Server 2005 and third-party servers, BENOTIFY requests can be disabled by setting its value to <STRONG>FALSE</STRONG>.</span></span> <span data-ttu-id="67ecb-322">現時点では、BENOTIFY は、IETF (インターネットエンジニアリングのタスクフォース) SIP 標準化プロセスの一部ではありません。</span><span class="sxs-lookup"><span data-stu-id="67ecb-322">BENOTIFY is not currently part of the IETF (Internet Engineering Task Force) SIP standardization process.</span></span>


</div></td>
<td><p><span data-ttu-id="67ecb-323">Live Communications Server 2005 の新しいもの。</span><span class="sxs-lookup"><span data-stu-id="67ecb-323">New in Live Communications Server 2005.</span></span></p>
<p><span data-ttu-id="67ecb-324">Lync Server 2010 では廃止されました。</span><span class="sxs-lookup"><span data-stu-id="67ecb-324">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="67ecb-325">msRTCSIP-EnableFederation (現在不使用)</span><span class="sxs-lookup"><span data-stu-id="67ecb-325">msRTCSIP-EnableFederation (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="67ecb-326">この属性は、ユーザーが他の組織のユーザーとの通信を許可されているかどうかを構成するために IT 管理者が使用するグローバルスイッチです。</span><span class="sxs-lookup"><span data-stu-id="67ecb-326">This attribute is a global switch that IT administrators use to configure whether users are allowed to communicate with users from other organizations.</span></span> <span data-ttu-id="67ecb-327">これにより、管理者は個々のユーザーの<strong>FederationEnabled</strong>属性を上書きすることができます。</span><span class="sxs-lookup"><span data-stu-id="67ecb-327">It enables an administrator to overwrite an individual user’s <strong>FederationEnabled</strong> attribute.</span></span> <span data-ttu-id="67ecb-328">この属性は、ワーム、ウイルス、または社内への攻撃によって発生する可能性があるインターネット攻撃から内部ネットワークを保護するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="67ecb-328">This attribute can be useful to help protect the internal network from Internet attacks that may be caused by worms, viruses, or targeted attacks on the company.</span></span></p>
<p><span data-ttu-id="67ecb-329">有効な値 (および関連するビット位置) は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="67ecb-329">The valid values (and associated bit positions) are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="67ecb-330">1: パブリック IM 接続が有効 (ビット位置 0)</span><span class="sxs-lookup"><span data-stu-id="67ecb-330">1: Enabled for public IM connectivity (bit position 0)</span></span></p></li>
<li><p><span data-ttu-id="67ecb-331">2: 予約済み (ビット位置 1)</span><span class="sxs-lookup"><span data-stu-id="67ecb-331">2: Reserved (bit position 1)</span></span></p></li>
<li><p><span data-ttu-id="67ecb-332">4: 予約済み (ビット位置 2)</span><span class="sxs-lookup"><span data-stu-id="67ecb-332">4: Reserved (bit position 2)</span></span></p></li>
<li><p><span data-ttu-id="67ecb-333">8: 予約済み (ビット位置 3)</span><span class="sxs-lookup"><span data-stu-id="67ecb-333">8: Reserved (bit position 3)</span></span></p></li>
<li><p><span data-ttu-id="67ecb-334">16: リモート通話コントロールが有効 [テレフォニー] (ビット位置 4)</span><span class="sxs-lookup"><span data-stu-id="67ecb-334">16: Remote call control Enabled [Telephony] (bit position 4)</span></span></p></li>
<li><p><span data-ttu-id="67ecb-335">64: AllowOrganizeMeetingWithAnonymousParticipants (ユーザーが匿名ユーザーを会議に招待できるようにする (ビット位置 6)</span><span class="sxs-lookup"><span data-stu-id="67ecb-335">64: AllowOrganizeMeetingWithAnonymousParticipants (allow users to invite anonymous users to meetings (bit position 6)</span></span></p></li>
<li><p><span data-ttu-id="67ecb-336">128: UCEnabled (ユーザーに対して統合コミュニケーションを有効にする) (ビット位置 7)</span><span class="sxs-lookup"><span data-stu-id="67ecb-336">128: UCEnabled (enable users for unified communications) (bit position 7)</span></span></p></li>
<li><p><span data-ttu-id="67ecb-337">256: EnabledForEnhancedPresence (ユーザーに対してパブリック IM 接続を有効にする) (ビット位置 8)</span><span class="sxs-lookup"><span data-stu-id="67ecb-337">256: EnabledForEnhancedPresence (enable user for public IM connectivity) (bit position 8)</span></span></p></li>
<li><p><span data-ttu-id="67ecb-338">512: RemoteCallControlDualMode (ビット位置 9)</span><span class="sxs-lookup"><span data-stu-id="67ecb-338">512: RemoteCallControlDualMode (bit position 9)</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="67ecb-339">Live Communications Server 2005 の新しいもの。</span><span class="sxs-lookup"><span data-stu-id="67ecb-339">New in Live Communications Server 2005.</span></span></p>
<p><span data-ttu-id="67ecb-340">Lync Server 2010 では廃止されました。</span><span class="sxs-lookup"><span data-stu-id="67ecb-340">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="67ecb-341">msRTCSIP-EnterpriseServices</span><span class="sxs-lookup"><span data-stu-id="67ecb-341">msRTCSIP-EnterpriseServices</span></span></p></td>
<td><p><span data-ttu-id="67ecb-342">この属性は、指定されたサーバーにエンタープライズサービスが読み込まれているかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="67ecb-342">This attribute indicates whether the Enterprise Services are loaded on the given server.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="67ecb-343">msRTCSIP-ExtensionData</span><span class="sxs-lookup"><span data-stu-id="67ecb-343">msRTCSIP-ExtensionData</span></span></p></td>
<td><p><span data-ttu-id="67ecb-344">この属性は、今後の使用のために予約されています。</span><span class="sxs-lookup"><span data-stu-id="67ecb-344">This attribute is reserved for future use.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="67ecb-345">msRTCSIP-ExternalAccessCode</span><span class="sxs-lookup"><span data-stu-id="67ecb-345">msRTCSIP-ExternalAccessCode</span></span></p></td>
<td><p><span data-ttu-id="67ecb-346">外部アクセスのダイヤルコードを含む属性です。</span><span class="sxs-lookup"><span data-stu-id="67ecb-346">This attribute contains the dial code for external access.</span></span></p></td>
<td><p><span data-ttu-id="67ecb-347">Office Communications Server 2007 R2 の新製品。</span><span class="sxs-lookup"><span data-stu-id="67ecb-347">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="67ecb-348">msRTCSIP-FederationEnabled</span><span class="sxs-lookup"><span data-stu-id="67ecb-348">msRTCSIP-FederationEnabled</span></span></p></td>
<td><p><span data-ttu-id="67ecb-349">この属性は、1人のユーザーがフェデレーションを有効にするかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="67ecb-349">This attribute controls whether a single user is enabled for federation.</span></span> <span data-ttu-id="67ecb-350">エンタープライズサービス層によって適用されます。</span><span class="sxs-lookup"><span data-stu-id="67ecb-350">It is enforced by the Enterprise Services layer.</span></span> <span data-ttu-id="67ecb-351">グローバルカタログレプリケーションのマークが付いています。</span><span class="sxs-lookup"><span data-stu-id="67ecb-351">It is marked for global catalog replication.</span></span></p>
<p><span data-ttu-id="67ecb-352">有効な値は、 <strong>TRUE</strong>または<strong>FALSE</strong>です。</span><span class="sxs-lookup"><span data-stu-id="67ecb-352">The valid values are <strong>TRUE</strong> or <strong>FALSE</strong>.</span></span></p></td>
<td><p><span data-ttu-id="67ecb-353">Live Communications Server 2005 の新しいもの。</span><span class="sxs-lookup"><span data-stu-id="67ecb-353">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="67ecb-354">msRTCSIP-FrontEndServers</span><span class="sxs-lookup"><span data-stu-id="67ecb-354">msRTCSIP-FrontEndServers</span></span></p></td>
<td><p><span data-ttu-id="67ecb-355">この属性は、プールに関連付けられているすべての Enterprise Edition サーバーのドメイン名の複数値を持つリストです。</span><span class="sxs-lookup"><span data-stu-id="67ecb-355">This attribute is a multi-valued list of the domain names of all Enterprise Edition servers associated with a pool.</span></span></p>
<p><span data-ttu-id="67ecb-356">後方リンク:<strong>リンク ID 11023</strong></span><span class="sxs-lookup"><span data-stu-id="67ecb-356">Back link: <strong>Link ID 11023</strong></span></span></p>
<p><span data-ttu-id="67ecb-357">この後方リンクへの対応する転送リンクは、 <strong>msRTCSIP-PoolAddress</strong>です。</span><span class="sxs-lookup"><span data-stu-id="67ecb-357">The corresponding forward link to this back link is <strong>msRTCSIP-PoolAddress</strong>.</span></span></p></td>
<td><p><span data-ttu-id="67ecb-358">Live Communications Server 2005 の新しいもの。</span><span class="sxs-lookup"><span data-stu-id="67ecb-358">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="67ecb-359">msRTCSIP-ゲートウェイ (obsolete)</span><span class="sxs-lookup"><span data-stu-id="67ecb-359">msRTCSIP-Gateways (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="67ecb-360">ゲートウェイとポート (ゲートウェイごと) の一覧を含む複数値の文字列属性です。</span><span class="sxs-lookup"><span data-stu-id="67ecb-360">This multi-valued string attribute contains a list of gateways and ports (per gateway).</span></span></p></td>
<td><p><span data-ttu-id="67ecb-361">Lync Server 2010 では廃止されました。</span><span class="sxs-lookup"><span data-stu-id="67ecb-361">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="67ecb-362">msRTCSIP-GlobalSettingsData (現在不使用)</span><span class="sxs-lookup"><span data-stu-id="67ecb-362">msRTCSIP-GlobalSettingsData (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="67ecb-363">この属性には、名前と値のペアが格納されます。</span><span class="sxs-lookup"><span data-stu-id="67ecb-363">This attribute stores name:value pairs.</span></span> <span data-ttu-id="67ecb-364">既に定義されている名前: 値のペアは、<strong>プレゼンス設定のポーリングを許可</strong>するためのものです。</span><span class="sxs-lookup"><span data-stu-id="67ecb-364">The already-defined name:value pair is for the <strong>allow polling for presence</strong> setting.</span></span></p></td>
<td><p><span data-ttu-id="67ecb-365">Lync Server 2010 では廃止されました。</span><span class="sxs-lookup"><span data-stu-id="67ecb-365">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="67ecb-366">msRTCSIP-GroupingID</span><span class="sxs-lookup"><span data-stu-id="67ecb-366">msRTCSIP-GroupingID</span></span></p></td>
<td><p><span data-ttu-id="67ecb-367">この属性は、アドレス帳のエントリをグループ化するために使用されるグループの一意の識別子です。</span><span class="sxs-lookup"><span data-stu-id="67ecb-367">This attribute is a unique identifier of a group that is used to group address book entries.</span></span></p></td>
<td><p><span data-ttu-id="67ecb-368">Lync Server 2010 の新。</span><span class="sxs-lookup"><span data-stu-id="67ecb-368">New in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="67ecb-369">msRTCSIP-Msrtcsip-homeserver (現在不使用)</span><span class="sxs-lookup"><span data-stu-id="67ecb-369">msRTCSIP-HomeServer (obsolete)</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="67ecb-370">Live Communications Server 2003 (使用されていません) の新。</span><span class="sxs-lookup"><span data-stu-id="67ecb-370">New in Live Communications Server 2003 (not used).</span></span></p>
<p><span data-ttu-id="67ecb-371">現在、Live Communications Server 2005 では使用されていません。</span><span class="sxs-lookup"><span data-stu-id="67ecb-371">Obsolete in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="67ecb-372">msRTCSIP-Msrtcsip-homeserverstring (現在不使用)</span><span class="sxs-lookup"><span data-stu-id="67ecb-372">msRTCSIP-HomeServerString (obsolete)</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="67ecb-373">Live Communications Server 2003 の新しいもの。</span><span class="sxs-lookup"><span data-stu-id="67ecb-373">New in Live Communications Server 2003.</span></span></p>
<p><span data-ttu-id="67ecb-374">現在、Live Communications Server 2005 では使用されていません。</span><span class="sxs-lookup"><span data-stu-id="67ecb-374">Obsolete in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="67ecb-375">msRTCSIP-ホームユーザー (現在不使用)</span><span class="sxs-lookup"><span data-stu-id="67ecb-375">msRTCSIP-HomeUsers (obsolete)</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="67ecb-376">Live Communications Server 2003 (使用されていません) の新。</span><span class="sxs-lookup"><span data-stu-id="67ecb-376">New in Live Communications Server 2003 (not used).</span></span></p>
<p><span data-ttu-id="67ecb-377">現在、Live Communications Server 2005 では使用されていません。</span><span class="sxs-lookup"><span data-stu-id="67ecb-377">Obsolete in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="67ecb-378">msRTCSIP-InternetAccessEnabled</span><span class="sxs-lookup"><span data-stu-id="67ecb-378">msRTCSIP-InternetAccessEnabled</span></span></p></td>
<td><p><span data-ttu-id="67ecb-379">この属性は、単一のユーザーが外部ユーザーアクセスを有効にしているかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="67ecb-379">This attribute controls whether a single user is enabled for outside user access.</span></span> <span data-ttu-id="67ecb-380">エンタープライズサービス層によって適用されます。</span><span class="sxs-lookup"><span data-stu-id="67ecb-380">It is enforced by the Enterprise Services layer.</span></span> <span data-ttu-id="67ecb-381">グローバルカタログレプリケーションのマークが付いています。</span><span class="sxs-lookup"><span data-stu-id="67ecb-381">It is marked for global catalog replication.</span></span></p>
<p><span data-ttu-id="67ecb-382">有効な値は、 <strong>TRUE</strong>または<strong>FALSE</strong>です。</span><span class="sxs-lookup"><span data-stu-id="67ecb-382">The valid values are <strong>TRUE</strong> or <strong>FALSE</strong>.</span></span></p></td>
<td><p><span data-ttu-id="67ecb-383">Live Communications Server 2005 の新しいもの。</span><span class="sxs-lookup"><span data-stu-id="67ecb-383">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="67ecb-384">msRTCSIP-IsMaster (現在不使用)</span><span class="sxs-lookup"><span data-stu-id="67ecb-384">msRTCSIP-IsMaster (obsolete)</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="67ecb-385">Live Communications Server の新サービス2003</span><span class="sxs-lookup"><span data-stu-id="67ecb-385">New in Live Communications Server 2003</span></span></p>
<p><span data-ttu-id="67ecb-386">現在、Live Communications Server 2005 では使用されていません。</span><span class="sxs-lookup"><span data-stu-id="67ecb-386">Obsolete in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="67ecb-387">msRTCSIP</span><span class="sxs-lookup"><span data-stu-id="67ecb-387">msRTCSIP-Line</span></span></p></td>
<td><p><span data-ttu-id="67ecb-388">この単一値の属性には、テレフォニーで Lync で使用されるデバイス ID (SIP URI またはユーザーが制御する電話の TEL URI) が含まれています。</span><span class="sxs-lookup"><span data-stu-id="67ecb-388">This single-valued attribute contains the device ID (either the SIP URI or the TEL URI of the phone the user controls) used by Lync for telephony.</span></span> <span data-ttu-id="67ecb-389">この属性は、グローバルカタログレプリケーションのマークが付いており、インデックスが作成されます。</span><span class="sxs-lookup"><span data-stu-id="67ecb-389">This attribute is marked for Global Catalog replication and is indexed.</span></span> <span data-ttu-id="67ecb-390">ユーザーがエンタープライズ Voip に対して有効になっている場合、この属性はユーザーの電話番号の e.164 正規化されたバージョンを格納します。</span><span class="sxs-lookup"><span data-stu-id="67ecb-390">If a user is enabled for Enterprise Voice, this attribute stores the E.164 normalized version of the user’s phone number.</span></span></p></td>
<td><p><span data-ttu-id="67ecb-391">Microsoft Office Live Communications Server 2005 SP1 の新技術情報</span><span class="sxs-lookup"><span data-stu-id="67ecb-391">New in Microsoft Office Live Communications Server 2005 with SP1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="67ecb-392">msRTCSIP</span><span class="sxs-lookup"><span data-stu-id="67ecb-392">msRTCSIP-LineServer</span></span></p></td>
<td><p><span data-ttu-id="67ecb-393">CSTA-SIP ゲートウェイサーバーの SIP URI を含む単一値の属性です。</span><span class="sxs-lookup"><span data-stu-id="67ecb-393">This single-valued attribute contains the SIP URI of the CSTA-SIP gateway server.</span></span> <span data-ttu-id="67ecb-394">この属性には、グローバルカタログレプリケーションのマークが付いていますが、インデックスは作成されません。</span><span class="sxs-lookup"><span data-stu-id="67ecb-394">This attribute is marked for Global Catalog replication but is not indexed.</span></span></p></td>
<td><p><span data-ttu-id="67ecb-395">Microsoft Office Live Communications Server 2005 SP1 の新技術情報</span><span class="sxs-lookup"><span data-stu-id="67ecb-395">New in Microsoft Office Live Communications Server 2005 with SP1</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="67ecb-396">msRTCSIP-LocalNormalizationData (現在不使用)</span><span class="sxs-lookup"><span data-stu-id="67ecb-396">msRTCSIP-LocalNormalizationData (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="67ecb-397">この属性は、今後の使用のために予約されています。</span><span class="sxs-lookup"><span data-stu-id="67ecb-397">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="67ecb-398">Office Communications Server 2007 の新製品。</span><span class="sxs-lookup"><span data-stu-id="67ecb-398">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="67ecb-399">Lync Server 2010 では廃止されました。</span><span class="sxs-lookup"><span data-stu-id="67ecb-399">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="67ecb-400">msRTCSIP-LocalNormalizationLinks (現在不使用)</span><span class="sxs-lookup"><span data-stu-id="67ecb-400">msRTCSIP-LocalNormalizationLinks (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="67ecb-401">この複数値属性には、この場所プロファイルに関連付けられているローカル正規化識別名 (DN) の一覧が含まれています。</span><span class="sxs-lookup"><span data-stu-id="67ecb-401">This multi-valued attribute contains a list of local normalization distinguished names (DN) associated with this location profile.</span></span> <span data-ttu-id="67ecb-402">この属性の型は、DN binary です。</span><span class="sxs-lookup"><span data-stu-id="67ecb-402">The type of this attribute is a DN binary.</span></span> <span data-ttu-id="67ecb-403">場所プロファイルとローカル正規化ルールの間には、一対多の関係があります。</span><span class="sxs-lookup"><span data-stu-id="67ecb-403">There is a one-to-many relationship between location profile and local normalization rules.</span></span> <span data-ttu-id="67ecb-404">ローカル正規化 DNs の一覧の順序は、管理者によって指定された順序で維持される必要があります。</span><span class="sxs-lookup"><span data-stu-id="67ecb-404">The ordering of the list of local normalization DNs must be maintained in the order specified by the administrator.</span></span> <span data-ttu-id="67ecb-405">順序の保持は、DN binary の2進部分によって維持されます。これにより、注文インデックスが指定されます。</span><span class="sxs-lookup"><span data-stu-id="67ecb-405">The preservation of order is maintained by the binary portion of the DN binary, which specifies the order index.</span></span></p>
<p><span data-ttu-id="67ecb-406">前方リンク:<strong>リンク ID 11034</strong></span><span class="sxs-lookup"><span data-stu-id="67ecb-406">Forward link: <strong>Link ID 11034</strong></span></span></p>
<p><span data-ttu-id="67ecb-407">この転送リンク属性への対応する後方リンクは、 <strong>msRTCSIP-LocationProfileBL</strong>です。</span><span class="sxs-lookup"><span data-stu-id="67ecb-407">The corresponding back link to this forward link attribute is <strong>msRTCSIP-LocationProfileBL</strong>.</span></span></p></td>
<td><p><span data-ttu-id="67ecb-408">Office Communications Server 2007 の新製品。</span><span class="sxs-lookup"><span data-stu-id="67ecb-408">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="67ecb-409">Lync Server 2010 では廃止されました。</span><span class="sxs-lookup"><span data-stu-id="67ecb-409">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="67ecb-410">msRTCSIP-LocalNormalizationOptions</span><span class="sxs-lookup"><span data-stu-id="67ecb-410">msRTCSIP-LocalNormalizationOptions</span></span></p></td>
<td><p><span data-ttu-id="67ecb-411">この属性には、正規化ルールのオプションの一覧が含まれています。</span><span class="sxs-lookup"><span data-stu-id="67ecb-411">This attribute contains a list of options for the normalization rule.</span></span></p></td>
<td><p><span data-ttu-id="67ecb-412">Office Communications Server 2007 R2 の新製品。</span><span class="sxs-lookup"><span data-stu-id="67ecb-412">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="67ecb-413">msRTCSIP-LocationName (現在不使用)</span><span class="sxs-lookup"><span data-stu-id="67ecb-413">msRTCSIP-LocationName (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="67ecb-414">この単一値の属性には、このプロファイルが表す場所を示す場所のプロファイルのフレンドリ名が含まれています。</span><span class="sxs-lookup"><span data-stu-id="67ecb-414">This single-valued attribute contains a friendly name for the location profile that indicates which location this profile represents.</span></span> <span data-ttu-id="67ecb-415">複数の場所プロファイルが存在する可能性があるため、管理者は異なるプロファイルを区別するための方法が必要です。</span><span class="sxs-lookup"><span data-stu-id="67ecb-415">Because there can be multiple location profiles, the administrator needs a way to distinguish between different profiles.</span></span></p></td>
<td><p><span data-ttu-id="67ecb-416">Office Communications Server 2007 の新製品。</span><span class="sxs-lookup"><span data-stu-id="67ecb-416">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="67ecb-417">Lync Server 2010 では廃止されました。</span><span class="sxs-lookup"><span data-stu-id="67ecb-417">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="67ecb-418">msRTCSIP-locationProfileBL (obsolete)</span><span class="sxs-lookup"><span data-stu-id="67ecb-418">msRTCSIP-locationProfileBL (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="67ecb-419">この複数値属性には、場所プロファイル識別名の一覧が含まれています。</span><span class="sxs-lookup"><span data-stu-id="67ecb-419">This multi-valued attribute contains a list of location profile distinguished names.</span></span> <span data-ttu-id="67ecb-420">この属性は、1つ以上の場所プロファイルへの後方リンクを指定します。</span><span class="sxs-lookup"><span data-stu-id="67ecb-420">This attribute specifies the back link to one or more location profiles.</span></span></p>
<p><span data-ttu-id="67ecb-421">後方リンク:<strong>リンク ID 11035</strong></span><span class="sxs-lookup"><span data-stu-id="67ecb-421">Back link: <strong>Link ID 11035</strong></span></span></p>
<p><span data-ttu-id="67ecb-422">この属性は、前方リンク<strong>msRTCSIP-LocalNormalizationLinks</strong>に対応しています。</span><span class="sxs-lookup"><span data-stu-id="67ecb-422">This attribute corresponds to the forward link <strong>msRTCSIP-LocalNormalizationLinks</strong>.</span></span></p></td>
<td><p><span data-ttu-id="67ecb-423">Office Communications Server 2007 の新製品。</span><span class="sxs-lookup"><span data-stu-id="67ecb-423">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="67ecb-424">Lync Server 2010 では廃止されました。</span><span class="sxs-lookup"><span data-stu-id="67ecb-424">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="67ecb-425">msRTCSIP-LocationProfileData (現在不使用)</span><span class="sxs-lookup"><span data-stu-id="67ecb-425">msRTCSIP-LocationProfileData (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="67ecb-426">この属性は、今後の使用のために予約されています。</span><span class="sxs-lookup"><span data-stu-id="67ecb-426">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="67ecb-427">Office Communications Server 2007 の新製品。</span><span class="sxs-lookup"><span data-stu-id="67ecb-427">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="67ecb-428">Lync Server 2010 では廃止されました。</span><span class="sxs-lookup"><span data-stu-id="67ecb-428">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="67ecb-429">msRTCSIP-LocationProfileOptions</span><span class="sxs-lookup"><span data-stu-id="67ecb-429">msRTCSIP-LocationProfileOptions</span></span></p></td>
<td><p><span data-ttu-id="67ecb-430">この属性には、場所のプロファイルのオプションが含まれています。</span><span class="sxs-lookup"><span data-stu-id="67ecb-430">This attribute contains the options for the location profile.</span></span></p></td>
<td><p><span data-ttu-id="67ecb-431">Office Communications Server 2007 R2 の新製品。</span><span class="sxs-lookup"><span data-stu-id="67ecb-431">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="67ecb-432">msRTCSIP-MappingContact</span><span class="sxs-lookup"><span data-stu-id="67ecb-432">msRTCSIP-MappingContact</span></span></p></td>
<td><p><span data-ttu-id="67ecb-433">この複数値属性は、アプリケーションの連絡先のリストを保持します。</span><span class="sxs-lookup"><span data-stu-id="67ecb-433">This multiple-value attribute holds a list of application contacts.</span></span></p></td>
<td><p><span data-ttu-id="67ecb-434">Office Communications Server 2007 R2 の新製品。</span><span class="sxs-lookup"><span data-stu-id="67ecb-434">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="67ecb-435">msRTCSIP-MappingLocation</span><span class="sxs-lookup"><span data-stu-id="67ecb-435">msRTCSIP-MappingLocation</span></span></p></td>
<td><p><span data-ttu-id="67ecb-436">この複数値属性は、場所のプロファイルの一覧を保持します。</span><span class="sxs-lookup"><span data-stu-id="67ecb-436">This multiple-value attribute holds a list of location profiles.</span></span></p></td>
<td><p><span data-ttu-id="67ecb-437">Office Communications Server 2007 R2 の新製品。</span><span class="sxs-lookup"><span data-stu-id="67ecb-437">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="67ecb-438">msRTCSIP-Maxnumoutingsearchperserver (現在不使用)</span><span class="sxs-lookup"><span data-stu-id="67ecb-438">msRTCSIP-MaxNumOutstandingSearchPerServer (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="67ecb-439">この属性は、サーバーごとの未処理の検索要求の最大数を表します。</span><span class="sxs-lookup"><span data-stu-id="67ecb-439">This attribute represents the maximum number of outstanding search requests per server.</span></span></p></td>
<td><p><span data-ttu-id="67ecb-440">Lync Server 2010 では廃止されました。</span><span class="sxs-lookup"><span data-stu-id="67ecb-440">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="67ecb-441">msRTCSIP-MaxNumSubscriptionsPerUser (現在不使用)</span><span class="sxs-lookup"><span data-stu-id="67ecb-441">msRTCSIP-MaxNumSubscriptionsPerUser (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="67ecb-442">ユーザーごとのサブスクリプションの最大数を表す属性です。</span><span class="sxs-lookup"><span data-stu-id="67ecb-442">The attribute represents the maximum number of subscriptions per user.</span></span></p></td>
<td><p><span data-ttu-id="67ecb-443">Lync Server 2010 では廃止されました。</span><span class="sxs-lookup"><span data-stu-id="67ecb-443">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="67ecb-444">msRTCSIP-Msrtcsip-maxpresencesubscriptiontimeout (現在不使用)</span><span class="sxs-lookup"><span data-stu-id="67ecb-444">msRTCSIP-MaxPresenceSubscriptionTimeout (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="67ecb-445">サブスクリプションタイムアウト期間の最大値を表す属性です。</span><span class="sxs-lookup"><span data-stu-id="67ecb-445">This attribute represents the maximum subscription time-out window.</span></span></p></td>
<td><p><span data-ttu-id="67ecb-446">Lync Server 2010 では廃止されました。</span><span class="sxs-lookup"><span data-stu-id="67ecb-446">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="67ecb-447">msRTCSIP-Msrtcsip-maxregistrationstimeout (現在不使用)</span><span class="sxs-lookup"><span data-stu-id="67ecb-447">msRTCSIP-MaxRegistrationsTimeout (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="67ecb-448">この属性は、最大登録タイムアウト時間枠を表します。</span><span class="sxs-lookup"><span data-stu-id="67ecb-448">This attribute represents the maximum registrations time-out window.</span></span></p></td>
<td><p><span data-ttu-id="67ecb-449">Lync Server 2010 では廃止されました。</span><span class="sxs-lookup"><span data-stu-id="67ecb-449">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="67ecb-450">msRTCSIP-Msrtcsip-maxroamingdatasubscriptiontimeout (現在不使用)</span><span class="sxs-lookup"><span data-stu-id="67ecb-450">msRTCSIP-MaxRoamingDataSubscriptionTimeout (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="67ecb-451">この属性は、[移動データサブスクリプションの最大タイムアウト] ウィンドウを表します。</span><span class="sxs-lookup"><span data-stu-id="67ecb-451">This attribute represents the maximum roaming data subscriptions time-out window.</span></span></p></td>
<td><p><span data-ttu-id="67ecb-452">Lync Server 2010 では廃止されました。</span><span class="sxs-lookup"><span data-stu-id="67ecb-452">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="67ecb-453">msRTCSIP-MCUData</span><span class="sxs-lookup"><span data-stu-id="67ecb-453">msRTCSIP-MCUData</span></span></p></td>
<td><p><span data-ttu-id="67ecb-454">この属性は、今後の使用のために予約されています。</span><span class="sxs-lookup"><span data-stu-id="67ecb-454">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="67ecb-455">Office Communications Server 2007 の新製品。</span><span class="sxs-lookup"><span data-stu-id="67ecb-455">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="67ecb-456">msRTCSIP-Msrtcsip-mcufactoryaddress です</span><span class="sxs-lookup"><span data-stu-id="67ecb-456">msRTCSIP-MCUFactoryAddress</span></span></p></td>
<td><p><span data-ttu-id="67ecb-457">この属性は、属している multipoint control unit (MCU) ファクトリへのリンクを指定するコンピュータークラス下のサービスコントロールポイント属性です。</span><span class="sxs-lookup"><span data-stu-id="67ecb-457">This attribute is a service control point attribute under the computer class that specifies a link back to the multipoint control unit (MCU) Factory to which it belongs.</span></span> <span data-ttu-id="67ecb-458">このサービスコントロールポイントと属性は、Microsoft MCU ごとに作成されます。</span><span class="sxs-lookup"><span data-stu-id="67ecb-458">This service control point and attribute is created for every Microsoft MCU.</span></span> <span data-ttu-id="67ecb-459">各 Microsoft MCU は、プールレベルの設定を取得するために、属しているプールのバックエンドサーバーを検索する必要があります。</span><span class="sxs-lookup"><span data-stu-id="67ecb-459">Each Microsoft MCU must find the Back End Server of the pool to which it belongs, in order to retrieve pool-level settings from it.</span></span></p>
<p><span data-ttu-id="67ecb-460">この属性の値は、MCU ファクトリの識別名 (DN) です。</span><span class="sxs-lookup"><span data-stu-id="67ecb-460">The value of this attribute is the distinguished name (DN) of the MCU Factory.</span></span> <span data-ttu-id="67ecb-461">これは単一値の属性で、グローバルカタログレプリケーションのマークが付けられています。</span><span class="sxs-lookup"><span data-stu-id="67ecb-461">This is a single-valued attribute and marked for global catalog replication.</span></span></p>
<p><span data-ttu-id="67ecb-462">前方リンク:<strong>リンク ID 11026</strong></span><span class="sxs-lookup"><span data-stu-id="67ecb-462">Forward link: <strong>Link ID 11026</strong></span></span></p>
<p><span data-ttu-id="67ecb-463">この転送リンク属性への対応する後方リンクは、 <strong>msRTCSIP</strong>ともなります。</span><span class="sxs-lookup"><span data-stu-id="67ecb-463">The corresponding back link to this forward link attribute is <strong>msRTCSIP-MCUServers</strong>.</span></span></p></td>
<td><p><span data-ttu-id="67ecb-464">Office Communications Server 2007 の新製品。</span><span class="sxs-lookup"><span data-stu-id="67ecb-464">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="67ecb-465">msRTCSIP-MCUFactoryData</span><span class="sxs-lookup"><span data-stu-id="67ecb-465">msRTCSIP-MCUFactoryData</span></span></p></td>
<td><p><span data-ttu-id="67ecb-466">これは複数文字列の予約済み属性です。</span><span class="sxs-lookup"><span data-stu-id="67ecb-466">This is a multi-string reserved attribute.</span></span> <span data-ttu-id="67ecb-467">この属性に格納されている設定は、名前 = 値のペアとして表されます。</span><span class="sxs-lookup"><span data-stu-id="67ecb-467">Settings stored in this attribute are represented as name=value pairs.</span></span> <span data-ttu-id="67ecb-468">現在定義されている名前 = 値のペアは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="67ecb-468">Currently defined name=value pairs are:</span></span></p>
<ul>
<li><p><span data-ttu-id="67ecb-469">FactoryURL = &lt;URL&gt;</span><span class="sxs-lookup"><span data-stu-id="67ecb-469">FactoryURL = &lt;URL&gt;</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="67ecb-470">Office Communications Server 2007 の新製品。</span><span class="sxs-lookup"><span data-stu-id="67ecb-470">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="67ecb-471">msRTCSIP-Msrtcsip-mcufactorypath</span><span class="sxs-lookup"><span data-stu-id="67ecb-471">msRTCSIP-MCUFactoryPath</span></span></p></td>
<td><p><span data-ttu-id="67ecb-472">これは、プールに関連付けられた1つの MCU ファクトリの識別名 (DN) を含む単一値の属性です。</span><span class="sxs-lookup"><span data-stu-id="67ecb-472">This is a single-valued attribute that contains the distinguished name (DN) of a single MCU factory associated with a pool.</span></span></p>
<p><span data-ttu-id="67ecb-473">前方リンク:<strong>リンク ID 11024</strong></span><span class="sxs-lookup"><span data-stu-id="67ecb-473">Forward link: <strong>Link ID 11024</strong></span></span></p>
<p><span data-ttu-id="67ecb-474">この転送リンク属性への対応する後方リンクは、 <strong>MsRTCSIP アドレス</strong>です。</span><span class="sxs-lookup"><span data-stu-id="67ecb-474">The corresponding back link to this forward link attribute is <strong>msRTCSIP-PoolAddresses</strong>.</span></span></p></td>
<td><p><span data-ttu-id="67ecb-475">Office Communications Server 2007 の新製品。</span><span class="sxs-lookup"><span data-stu-id="67ecb-475">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="67ecb-476">msRTCSIP-MCUFactoryProviderID</span><span class="sxs-lookup"><span data-stu-id="67ecb-476">msRTCSIP-MCUFactoryProviderID</span></span></p></td>
<td><p><span data-ttu-id="67ecb-477">この属性は、MCU ファクトリプロバイダーの GUID を指定する単一値の文字列です。</span><span class="sxs-lookup"><span data-stu-id="67ecb-477">This attribute is a single-valued string that specifies the GUID of the MCU factory provider.</span></span> <span data-ttu-id="67ecb-478">この GUID 値に基づいて、MCU ファクトリプロセスは、この MCU の種類をサービスするかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="67ecb-478">Based on the GUID value, the MCU factory process determines whether to service this MCU type.</span></span> <span data-ttu-id="67ecb-479">GUID 値が<strong>{F0810510-424F-46ef-84FE-6CC720DF1791}</strong>の場合、MCU ファクトリプロセス (Lync Server では既定で利用可能) によって処理されます。</span><span class="sxs-lookup"><span data-stu-id="67ecb-479">If the GUID value is <strong>{F0810510-424F-46ef-84FE-6CC720DF1791}</strong>, then the MCU factory process (available by default in Lync Server) will process it.</span></span> <span data-ttu-id="67ecb-480">その他の GUID 値の場合、MCU ファクトリプロセスは MCU の種類をサービスしません。</span><span class="sxs-lookup"><span data-stu-id="67ecb-480">For any other GUID value, the MCU factory process will not service the MCU type.</span></span></p></td>
<td><p><span data-ttu-id="67ecb-481">Office Communications Server 2007 の新製品。</span><span class="sxs-lookup"><span data-stu-id="67ecb-481">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="67ecb-482">msRTCSIP-MCUServers ユーザー</span><span class="sxs-lookup"><span data-stu-id="67ecb-482">msRTCSIP-MCUServers</span></span></p></td>
<td><p><span data-ttu-id="67ecb-483">この属性は、複数値を持つ識別名 (DN) のリストです。</span><span class="sxs-lookup"><span data-stu-id="67ecb-483">This attribute is a multi-valued list of distinguished names (DN).</span></span> <span data-ttu-id="67ecb-484">この属性には、この MCU ファクトリに関連付けられている同じ種類およびベンダーのすべての MCU サーバーの一覧が含まれています。</span><span class="sxs-lookup"><span data-stu-id="67ecb-484">This attribute contains a list of all MCU servers of the same type and vendor associated with this MCU factory.</span></span> <span data-ttu-id="67ecb-485">各セグメントの有効な値は、63文字です。FQDN 全体の有効な値は255文字です。</span><span class="sxs-lookup"><span data-stu-id="67ecb-485">The valid value for each segment is 63 characters; the valid value for the entire FQDN is 255 characters.</span></span></p>
<p><span data-ttu-id="67ecb-486">後方リンク: リンク ID 11027</span><span class="sxs-lookup"><span data-stu-id="67ecb-486">Back link: Link ID 11027</span></span></p>
<p><span data-ttu-id="67ecb-487">この後方リンクへの対応する転送リンクは、 <strong>msRTCSIP-msrtcsip-mcufactoryaddress です</strong>です。</span><span class="sxs-lookup"><span data-stu-id="67ecb-487">The corresponding forward link to this back link is <strong>msRTCSIP-MCUFactoryAddress</strong>.</span></span></p></td>
<td><p><span data-ttu-id="67ecb-488">Office Communications Server 2007 の新製品。</span><span class="sxs-lookup"><span data-stu-id="67ecb-488">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="67ecb-489">msRTCSIP-MCUType</span><span class="sxs-lookup"><span data-stu-id="67ecb-489">msRTCSIP-MCUType</span></span></p></td>
<td><p><span data-ttu-id="67ecb-490">この属性は、MCU が処理できるメディアを指定する単一値の文字列です。</span><span class="sxs-lookup"><span data-stu-id="67ecb-490">This attribute is a single-valued string that specifies the medium the MCU can handle.</span></span></p>
<p><span data-ttu-id="67ecb-491">サポートされている有効な種類は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="67ecb-491">Supported valid types are:</span></span></p>
<ul>
<li><p><span data-ttu-id="67ecb-492">定期的</span><span class="sxs-lookup"><span data-stu-id="67ecb-492">meeting</span></span></p></li>
<li><p><span data-ttu-id="67ecb-493">音声ビデオ</span><span class="sxs-lookup"><span data-stu-id="67ecb-493">audio-video</span></span></p></li>
<li><p><span data-ttu-id="67ecb-494">チャット</span><span class="sxs-lookup"><span data-stu-id="67ecb-494">chat</span></span></p></li>
<li><p><span data-ttu-id="67ecb-495">電話-conf</span><span class="sxs-lookup"><span data-stu-id="67ecb-495">phone-conf</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="67ecb-496">Office Communications Server 2007 の新製品。</span><span class="sxs-lookup"><span data-stu-id="67ecb-496">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="67ecb-497">msRTCSIP-MCUVendor</span><span class="sxs-lookup"><span data-stu-id="67ecb-497">msRTCSIP-MCUVendor</span></span></p></td>
<td><p><span data-ttu-id="67ecb-498">この属性は、MCU ベンダーの名前を指定する単一値の文字列です。</span><span class="sxs-lookup"><span data-stu-id="67ecb-498">This attribute is a single-valued string that specifies an MCU vendor’s name.</span></span> <span data-ttu-id="67ecb-499">すべての Microsoft Mcu は、この属性を<strong>Microsoft Corporation</strong>に指定します。</span><span class="sxs-lookup"><span data-stu-id="67ecb-499">All Microsoft MCUs will specify this attribute to be <strong>Microsoft Corporation</strong>.</span></span></p></td>
<td><p><span data-ttu-id="67ecb-500">Office Communications Server 2007 の新製品。</span><span class="sxs-lookup"><span data-stu-id="67ecb-500">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="67ecb-501">msRTCSIP-会議フラグ (不使用)</span><span class="sxs-lookup"><span data-stu-id="67ecb-501">msRTCSIP-MeetingFlags (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="67ecb-502">この属性は、すべてのユーザーまたは連絡先オブジェクトに対してグローバルに有効になる、さまざまな会議オプションを定義します。</span><span class="sxs-lookup"><span data-stu-id="67ecb-502">This attribute defines different meeting options that are enabled globally for all users or contact objects.</span></span> <span data-ttu-id="67ecb-503">この属性は、整数型のビットマスク値です。</span><span class="sxs-lookup"><span data-stu-id="67ecb-503">This attribute is a bit-mask value of integer type.</span></span></p>
<p><span data-ttu-id="67ecb-504">有効な値 (および関連するビット位置) は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="67ecb-504">The valid values (and associated bit positions) are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="67ecb-505">0: AllowOrganizeMeetingWithAnonymousParticipants が None (会議への匿名ユーザーの招待をユーザーに許可しない) (ビットが設定されていない)</span><span class="sxs-lookup"><span data-stu-id="67ecb-505">0: AllowOrganizeMeetingWithAnonymousParticipants is None (do not allow users to invite anonymous users to meetings) (no bits set)</span></span></p></li>
<li><p><span data-ttu-id="67ecb-506">4: AllowOrganizeMeetingWithAnonymousParticipants はすべてのユーザー (すべてのユーザーが、会議への匿名ユーザーの招待を許可する) (ビット位置 2)</span><span class="sxs-lookup"><span data-stu-id="67ecb-506">4: AllowOrganizeMeetingWithAnonymousParticipants is Everyone (allow all users to invite anonymous users to meetings) (bit position 2)</span></span></p></li>
<li><p><span data-ttu-id="67ecb-507">8: AllowOrganizeMeetingWithAnonymousParticipants が UsePerUserSetting (ユーザーごとの設定に基づいてユーザーに匿名ユーザーの会議への招待を許可する) (ビット位置 3)</span><span class="sxs-lookup"><span data-stu-id="67ecb-507">8: AllowOrganizeMeetingWithAnonymousParticipants is UsePerUserSetting (allow users to invite anonymous users to meetings based on per user setting) (bit position 3)</span></span></p></li>
<li><p><span data-ttu-id="67ecb-508">16: Userperusermeeting Policy (ユーザーごとに会議ポリシーが定義されます) (ビット位置 4)</span><span class="sxs-lookup"><span data-stu-id="67ecb-508">16: UserPerUserMeetingPolicy (meeting policy is defined per user) (bit position 4)</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="67ecb-509">Office Communications Server 2007 の新製品。</span><span class="sxs-lookup"><span data-stu-id="67ecb-509">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="67ecb-510">Lync Server 2010 では廃止されました。</span><span class="sxs-lookup"><span data-stu-id="67ecb-510">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="67ecb-511">msRTCSIP-会議ポリシー (不使用)</span><span class="sxs-lookup"><span data-stu-id="67ecb-511">msRTCSIP-MeetingPolicy (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="67ecb-512">この属性は、管理者がこのユーザーに割り当てたポリシーの識別名 (DN) を単一値属性として指定します。</span><span class="sxs-lookup"><span data-stu-id="67ecb-512">This attribute specifies the distinguished name (DN) of the policy the administrator has assigned for this user as a single-valued attribute.</span></span></p></td>
<td><p><span data-ttu-id="67ecb-513">Office Communications Server 2007 の新製品。</span><span class="sxs-lookup"><span data-stu-id="67ecb-513">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="67ecb-514">Lync Server 2010 では廃止されました。</span><span class="sxs-lookup"><span data-stu-id="67ecb-514">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="67ecb-515">msRTCSIP-Msrtcsip-minpresencesubscriptiontimeout (現在不使用)</span><span class="sxs-lookup"><span data-stu-id="67ecb-515">msRTCSIP-MinPresenceSubscriptionTimeout (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="67ecb-516">この属性は、最小プレゼンスサブスクリプションタイムアウト期間を表します。</span><span class="sxs-lookup"><span data-stu-id="67ecb-516">This attribute represents the minimum presence subscription time-out window.</span></span></p></td>
<td><p><span data-ttu-id="67ecb-517">Lync Server 2010 では廃止されました。</span><span class="sxs-lookup"><span data-stu-id="67ecb-517">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="67ecb-518">msRTCSIP-MinRegistrationTimeout (obsolete)</span><span class="sxs-lookup"><span data-stu-id="67ecb-518">msRTCSIP-MinRegistrationTimeout (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="67ecb-519">この属性は、最小登録タイムアウト時間枠を表します。</span><span class="sxs-lookup"><span data-stu-id="67ecb-519">This attribute represents the minimum registration time-out window.</span></span></p></td>
<td><p><span data-ttu-id="67ecb-520">Office Communications Server 2007 の新製品。</span><span class="sxs-lookup"><span data-stu-id="67ecb-520">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="67ecb-521">Lync Server 2010 では廃止されました。</span><span class="sxs-lookup"><span data-stu-id="67ecb-521">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="67ecb-522">msRTCSIP-Msrtcsip-minroamingdatasubscriptiontimeout (現在不使用)</span><span class="sxs-lookup"><span data-stu-id="67ecb-522">msRTCSIP-MinRoamingDataSubscriptionTimeout (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="67ecb-523">この属性は、移動データサブスクリプションタイムアウト期間の最小値を表します。</span><span class="sxs-lookup"><span data-stu-id="67ecb-523">This attribute represents the minimum roaming data subscription time-out window.</span></span></p></td>
<td><p><span data-ttu-id="67ecb-524">Office Communications Server 2007 の新製品。</span><span class="sxs-lookup"><span data-stu-id="67ecb-524">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="67ecb-525">Lync Server 2010 では廃止されました。</span><span class="sxs-lookup"><span data-stu-id="67ecb-525">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="67ecb-526">msRTCSIP-MirrorBackEndServer</span><span class="sxs-lookup"><span data-stu-id="67ecb-526">msRTCSIP-MirrorBackEndServer</span></span></p></td>
<td><p><span data-ttu-id="67ecb-527">この属性は、フロントエンドプールで使用されるミラーリングされた SQL Server バックエンドを格納するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="67ecb-527">This attribute is used to store the mirrored SQL Server backend used by the Front End pool.</span></span></p></td>
<td><p><span data-ttu-id="67ecb-528">Lync Server 2013 の新。</span><span class="sxs-lookup"><span data-stu-id="67ecb-528">New in Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="67ecb-529">msRTCSIP-MobilityFlags</span><span class="sxs-lookup"><span data-stu-id="67ecb-529">msRTCSIP-MobilityFlags</span></span></p></td>
<td><p><span data-ttu-id="67ecb-530">この属性には、モビリティ設定を定義するオプションとフラグが含まれています。</span><span class="sxs-lookup"><span data-stu-id="67ecb-530">This attribute contains options and flags that define mobility settings.</span></span></p></td>
<td><p><span data-ttu-id="67ecb-531">Office Communications Server 2007 R2 の新製品。</span><span class="sxs-lookup"><span data-stu-id="67ecb-531">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="67ecb-532">msRTCSIP-MobilityPolicy</span><span class="sxs-lookup"><span data-stu-id="67ecb-532">msRTCSIP-MobilityPolicy</span></span></p></td>
<td><p><span data-ttu-id="67ecb-533">モビリティポリシーオブジェクトの DN を含む属性です。</span><span class="sxs-lookup"><span data-stu-id="67ecb-533">This attribute contains the DN for a mobility policy object.</span></span></p></td>
<td><p><span data-ttu-id="67ecb-534">Office Communications Server 2007 R2 の新製品。</span><span class="sxs-lookup"><span data-stu-id="67ecb-534">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="67ecb-535">msRTCSIP-Msrtcsip-numdevicesperuser (現在不使用)</span><span class="sxs-lookup"><span data-stu-id="67ecb-535">msRTCSIP-NumDevicesPerUser (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="67ecb-536">ユーザーが SIP コミュニケーション用に登録し、プレゼンスにサブスクライブできるデバイスの許容数を表す属性です。</span><span class="sxs-lookup"><span data-stu-id="67ecb-536">This attribute represents the allowed number of devices on which a user can register for SIP communications and subscribe to presence.</span></span></p></td>
<td><p><span data-ttu-id="67ecb-537">Office Communications Server 2007 の新製品。</span><span class="sxs-lookup"><span data-stu-id="67ecb-537">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="67ecb-538">Lync Server 2010 では廃止されました。</span><span class="sxs-lookup"><span data-stu-id="67ecb-538">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="67ecb-539">msRTCSIP-OptionFlags</span><span class="sxs-lookup"><span data-stu-id="67ecb-539">msRTCSIP-OptionFlags</span></span></p></td>
<td><p><span data-ttu-id="67ecb-540">この属性は、ユーザーまたは連絡先オブジェクトに対して有効になっているオプションを指定します。</span><span class="sxs-lookup"><span data-stu-id="67ecb-540">This attribute specifies the options that are enabled for the user or contact object.</span></span> <span data-ttu-id="67ecb-541">この属性は、integer 型のビットマスク値です。</span><span class="sxs-lookup"><span data-stu-id="67ecb-541">This attribute is a bit-mask value of type integer.</span></span> <span data-ttu-id="67ecb-542">各オプションはビットで表されます。</span><span class="sxs-lookup"><span data-stu-id="67ecb-542">Each option is represented by a bit.</span></span> <span data-ttu-id="67ecb-543">この属性には、グローバルカタログレプリケーションのマークが付いています。</span><span class="sxs-lookup"><span data-stu-id="67ecb-543">This attribute is marked for global catalog replication.</span></span></p>
<p><span data-ttu-id="67ecb-544">有効な値 (および関連するビット位置) は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="67ecb-544">The valid values (and associated bit positions) are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="67ecb-545">1: パブリックインスタントメッセージング (IM) 接続が有効 (ビット位置 0)</span><span class="sxs-lookup"><span data-stu-id="67ecb-545">1: Enabled for public instant messaging (IM) connectivity (bit position 0)</span></span></p></li>
<li><p><span data-ttu-id="67ecb-546">2: 予約済み (ビット位置 1)</span><span class="sxs-lookup"><span data-stu-id="67ecb-546">2: Reserved (bit position 1)</span></span></p></li>
<li><p><span data-ttu-id="67ecb-547">4: 予約済み (ビット位置 2)</span><span class="sxs-lookup"><span data-stu-id="67ecb-547">4: Reserved (bit position 2)</span></span></p></li>
<li><p><span data-ttu-id="67ecb-548">8: 予約済み (ビット位置 3)</span><span class="sxs-lookup"><span data-stu-id="67ecb-548">8: Reserved (bit position 3)</span></span></p></li>
<li><p><span data-ttu-id="67ecb-549">16: リモート通話コントロールが有効 [テレフォニー] (ビット位置 4)</span><span class="sxs-lookup"><span data-stu-id="67ecb-549">16: Remote call control Enabled [Telephony] (bit position 4)</span></span></p></li>
<li><p><span data-ttu-id="67ecb-550">64: AllowOrganizeMeetingWithAnonymousParticipants (ユーザーが匿名ユーザーを会議に招待できるようにする (ビット位置 6)</span><span class="sxs-lookup"><span data-stu-id="67ecb-550">64: AllowOrganizeMeetingWithAnonymousParticipants (allow users to invite anonymous users to meetings (bit position 6)</span></span></p></li>
<li><p><span data-ttu-id="67ecb-551">128: UCEnabled (UC に対してユーザーを有効にする) (ビット位置 7)</span><span class="sxs-lookup"><span data-stu-id="67ecb-551">128: UCEnabled (enable users for UC) (bit position 7)</span></span></p></li>
<li><p><span data-ttu-id="67ecb-552">256: EnabledForEnhancedPresence (ユーザーに対してパブリック IM 接続を有効にする) (ビット位置 8)</span><span class="sxs-lookup"><span data-stu-id="67ecb-552">256: EnabledForEnhancedPresence (enable user for public IM connectivity) (bit position 8)</span></span></p></li>
<li><p><span data-ttu-id="67ecb-553">512: RemoteCallControlDualMode (ビット位置 9)</span><span class="sxs-lookup"><span data-stu-id="67ecb-553">512: RemoteCallControlDualMode (bit position 9)</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="67ecb-554">Live Communications Server 2005 SP1 で導入されています。</span><span class="sxs-lookup"><span data-stu-id="67ecb-554">New in Live Communications Server 2005 with SP1.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="67ecb-555">msRTCSIP-の場合は、Sid</span><span class="sxs-lookup"><span data-stu-id="67ecb-555">msRTCSIP-OriginatorSID</span></span></p></td>
<td><p><span data-ttu-id="67ecb-556">この属性は、ユーザーの ObjectSID が Windows NT Server プリンシパルアカウントから、リソースまたは中央フォレスト内の対応するユーザーまたは連絡先オブジェクトの属性にコピーされるときにシングルサインオンを有効にするために、リソースおよび中央フォレストのトポロジで使用されます。</span><span class="sxs-lookup"><span data-stu-id="67ecb-556">This attribute is used in resource and central forest topologies to enable single sign-on when a user’s ObjectSID from the Windows NT Server principal account is copied into this attribute of the corresponding user or contact object in the resource or central forest.</span></span> <span data-ttu-id="67ecb-557">Communicator Web Access は、この属性またはユーザーの ObjectSID を使用して、AD DS 内のユーザーを検索します。</span><span class="sxs-lookup"><span data-stu-id="67ecb-557">Communicator Web Access searches for a user in AD DS using this attribute or the user’s ObjectSID.</span></span> <span data-ttu-id="67ecb-558">この属性には、グローバルカタログレプリケーションのマークが付いています。</span><span class="sxs-lookup"><span data-stu-id="67ecb-558">This attribute is marked for global catalog replication.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="67ecb-559">msRTCSIP-OwnerUrn</span><span class="sxs-lookup"><span data-stu-id="67ecb-559">msRTCSIP-OwnerUrn</span></span></p></td>
<td><p><span data-ttu-id="67ecb-560">この属性は、アプリケーション連絡先の所有者の Uniform Resource Name (URN) です。</span><span class="sxs-lookup"><span data-stu-id="67ecb-560">This attribute is the Uniform Resource Name (URN) of the owner for an application contact.</span></span></p></td>
<td><p><span data-ttu-id="67ecb-561">Lync Server 2010 の新。</span><span class="sxs-lookup"><span data-stu-id="67ecb-561">New in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="67ecb-562">msRTCSIP-パターン (obsolete)</span><span class="sxs-lookup"><span data-stu-id="67ecb-562">msRTCSIP-Pattern (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="67ecb-563">この単一値の文字列属性には、ダイヤル番号を e.164 形式に一致させるために使用するパターンが含まれています。</span><span class="sxs-lookup"><span data-stu-id="67ecb-563">This single-valued string attribute contains a pattern used for matching dial numbers into E.164 format.</span></span> <span data-ttu-id="67ecb-564">ダイヤル番号がこのパターンと一致する場合は、ダイヤル番号に変換が適用されます。</span><span class="sxs-lookup"><span data-stu-id="67ecb-564">If the dial number matches this pattern, the translation is applied to the dialed number.</span></span></p></td>
<td><p><span data-ttu-id="67ecb-565">Office Communications Server 2007 の新製品。</span><span class="sxs-lookup"><span data-stu-id="67ecb-565">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="67ecb-566">Lync Server 2010 では廃止されました。</span><span class="sxs-lookup"><span data-stu-id="67ecb-566">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="67ecb-567">msRTCSIP-Msrtcsip-phoneroutebl です (現在不使用)</span><span class="sxs-lookup"><span data-stu-id="67ecb-567">msRTCSIP-PhoneRouteBL (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="67ecb-568">この複数値属性には、電話ルート識別名 (DN) の一覧が含まれています。</span><span class="sxs-lookup"><span data-stu-id="67ecb-568">This multi-valued attribute contains a list of phone route distinguished names (DN).</span></span> <span data-ttu-id="67ecb-569">この属性は、1つまたは複数の電話ルートへの後方リンクを指定します。</span><span class="sxs-lookup"><span data-stu-id="67ecb-569">This attribute specifies the back link to one or more phone routes.</span></span></p>
<p><span data-ttu-id="67ecb-570">後方リンク:<strong>リンク ID 11033</strong></span><span class="sxs-lookup"><span data-stu-id="67ecb-570">Back link: <strong>Link ID 11033</strong></span></span></p>
<p><span data-ttu-id="67ecb-571">この属性は、Msrtcsip-routeusagelinks の前方リンク<strong>msRTCSIP</strong>に対応します。</span><span class="sxs-lookup"><span data-stu-id="67ecb-571">This attribute corresponds to the forward link <strong>msRTCSIP-RouteUsageLinks</strong>.</span></span></p></td>
<td><p><span data-ttu-id="67ecb-572">Office Communications Server 2007 の新製品。</span><span class="sxs-lookup"><span data-stu-id="67ecb-572">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="67ecb-573">Lync Server 2010 では廃止されました。</span><span class="sxs-lookup"><span data-stu-id="67ecb-573">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="67ecb-574">msRTCSIP-Msrtcsip-phoneroutedata (現在不使用)</span><span class="sxs-lookup"><span data-stu-id="67ecb-574">msRTCSIP-PhoneRouteData (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="67ecb-575">この属性は、今後の使用のために予約されています。</span><span class="sxs-lookup"><span data-stu-id="67ecb-575">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="67ecb-576">Lync Server 2010 では廃止されました。</span><span class="sxs-lookup"><span data-stu-id="67ecb-576">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="67ecb-577">msRTCSIP-Msrtcsip-phoneroutename (現在不使用)</span><span class="sxs-lookup"><span data-stu-id="67ecb-577">msRTCSIP-PhoneRouteName (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="67ecb-578">この単一値の UNICODE 文字列属性は、電話ルートのフレンドリ名を指定します。これにより、管理者が簡単に参照できるようになります。</span><span class="sxs-lookup"><span data-stu-id="67ecb-578">This single valued UNICODE string attribute specifies the friendly name of the phone route, so it can easily be referenced by the administrator.</span></span></p></td>
<td><p><span data-ttu-id="67ecb-579">Lync Server 2010 では廃止されました。</span><span class="sxs-lookup"><span data-stu-id="67ecb-579">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="67ecb-580">msRTCSIP-電話での使用データ (obsolete)</span><span class="sxs-lookup"><span data-stu-id="67ecb-580">msRTCSIP-PhoneUsageData (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="67ecb-581">この属性は、今後の使用のために予約されています。</span><span class="sxs-lookup"><span data-stu-id="67ecb-581">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="67ecb-582">Office Communications Server 2007 の新製品。</span><span class="sxs-lookup"><span data-stu-id="67ecb-582">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="67ecb-583">Lync Server 2010 では廃止されました。</span><span class="sxs-lookup"><span data-stu-id="67ecb-583">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="67ecb-584">msRTCSIP-PolicyContent (現在不使用)</span><span class="sxs-lookup"><span data-stu-id="67ecb-584">msRTCSIP-PolicyContent (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="67ecb-585">この属性は、単一の値を持つ Unicode 文字列です。</span><span class="sxs-lookup"><span data-stu-id="67ecb-585">This attribute is a single-valued Unicode string.</span></span> <span data-ttu-id="67ecb-586">この文字列属性には、ポリシー定義が XML 形式で含まれています。</span><span class="sxs-lookup"><span data-stu-id="67ecb-586">This string attribute contains the policy definition in XML format.</span></span> <span data-ttu-id="67ecb-587">XML スキーマ定義はさまざまなポリシーの種類に共通していますが、ポリシーの種類ごとに設定のみが異なります。</span><span class="sxs-lookup"><span data-stu-id="67ecb-587">The XML schema definition is common across different policy types, only the settings are different for each policy type.</span></span></p>
<p><span data-ttu-id="67ecb-588">XML スキーマ定義 (XSD) は次のように定義されています。</span><span class="sxs-lookup"><span data-stu-id="67ecb-588">The XML schema definition (XSD) is defined as follows:</span></span></p>
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
<td><p><span data-ttu-id="67ecb-589">Office Communications Server 2007 の新製品。</span><span class="sxs-lookup"><span data-stu-id="67ecb-589">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="67ecb-590">Lync Server 2010 では廃止されました。</span><span class="sxs-lookup"><span data-stu-id="67ecb-590">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="67ecb-591">msRTCSIP-PolicyData (現在不使用)</span><span class="sxs-lookup"><span data-stu-id="67ecb-591">msRTCSIP-PolicyData (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="67ecb-592">この属性は、今後の使用のために予約されています。</span><span class="sxs-lookup"><span data-stu-id="67ecb-592">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="67ecb-593">Office Communications Server 2007 の新製品。</span><span class="sxs-lookup"><span data-stu-id="67ecb-593">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="67ecb-594">Lync Server 2010 では廃止されました。</span><span class="sxs-lookup"><span data-stu-id="67ecb-594">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="67ecb-595">msRTCSIP-Msrtcsip-policytype (現在不使用)</span><span class="sxs-lookup"><span data-stu-id="67ecb-595">msRTCSIP-PolicyType (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="67ecb-596">この単一値の Unicode 文字列属性には、ポリシーの種類が含まれています。</span><span class="sxs-lookup"><span data-stu-id="67ecb-596">This single-valued Unicode string attribute contains the policy type.</span></span> <span data-ttu-id="67ecb-597">有効なポリシーの種類は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="67ecb-597">Valid policy types are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="67ecb-598">定期的</span><span class="sxs-lookup"><span data-stu-id="67ecb-598">meeting</span></span></p></li>
<li><p><span data-ttu-id="67ecb-599">網</span><span class="sxs-lookup"><span data-stu-id="67ecb-599">telephony</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="67ecb-600">Office Communications Server 2007 の新製品。</span><span class="sxs-lookup"><span data-stu-id="67ecb-600">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="67ecb-601">Lync Server 2010 では廃止されました。</span><span class="sxs-lookup"><span data-stu-id="67ecb-601">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="67ecb-602">msRTCSIP-PoolAddress</span><span class="sxs-lookup"><span data-stu-id="67ecb-602">msRTCSIP-PoolAddress</span></span></p></td>
<td><p><span data-ttu-id="67ecb-603">この属性は、コンピューターが属するプールに戻るリンクを指定します。</span><span class="sxs-lookup"><span data-stu-id="67ecb-603">This attribute specifies a link back to the pool to which a computer belongs.</span></span> <span data-ttu-id="67ecb-604">この属性は、コンピューターでの Lync Server の Standard Edition または Enterprise Edition のどちらが実行されているかに関係なく設定されます。</span><span class="sxs-lookup"><span data-stu-id="67ecb-604">This attribute is set regardless of whether the computer is running the Standard Edition or the Enterprise Edition of Lync Server.</span></span> <span data-ttu-id="67ecb-605">この属性には、グローバルカタログレプリケーションのマークが付いています。</span><span class="sxs-lookup"><span data-stu-id="67ecb-605">This attribute is marked for global catalog replication.</span></span></p>
<p><span data-ttu-id="67ecb-606">有効な値はプールのドメイン名です。</span><span class="sxs-lookup"><span data-stu-id="67ecb-606">The valid value is the domain name of the pool.</span></span></p>
<p><span data-ttu-id="67ecb-607">前方リンク:<strong>リンク ID 11022</strong></span><span class="sxs-lookup"><span data-stu-id="67ecb-607">Forward link: <strong>Link ID 11022</strong></span></span></p>
<p><span data-ttu-id="67ecb-608">この転送リンク属性への対応する後方リンクは、 <strong>msRTCSIP-FrontEndServers</strong>です。</span><span class="sxs-lookup"><span data-stu-id="67ecb-608">The corresponding back link to this forward link attribute is <strong>msRTCSIP-FrontEndServers</strong>.</span></span></p></td>
<td><p><span data-ttu-id="67ecb-609">Live Communications Server 2005 の新しいもの。</span><span class="sxs-lookup"><span data-stu-id="67ecb-609">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="67ecb-610">msRTCSIP-PoolAddresses</span><span class="sxs-lookup"><span data-stu-id="67ecb-610">msRTCSIP-PoolAddresses</span></span></p></td>
<td><p><span data-ttu-id="67ecb-611">これは、MCU ファクトリが関連付けられているプールの識別名 (DN) のリストを含む複数値の属性です。</span><span class="sxs-lookup"><span data-stu-id="67ecb-611">This is a multi-valued attribute that contains a list of the distinguished names (DN) of pools with which the MCU factory is associated.</span></span></p>
<p><span data-ttu-id="67ecb-612">後方リンク:<strong>リンク ID 11025</strong></span><span class="sxs-lookup"><span data-stu-id="67ecb-612">Back link: <strong>Link ID 11025</strong></span></span></p>
<p><span data-ttu-id="67ecb-613">この後方リンクへの対応する転送リンクは、 <strong>msRTCSIP-msrtcsip-mcufactorypath</strong>です。</span><span class="sxs-lookup"><span data-stu-id="67ecb-613">The corresponding forward link to this back link is <strong>msRTCSIP-MCUFactoryPath</strong>.</span></span></p></td>
<td><p><span data-ttu-id="67ecb-614">Office Communications Server 2007 の新製品。</span><span class="sxs-lookup"><span data-stu-id="67ecb-614">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="67ecb-615">msRTCSIP-PoolData</span><span class="sxs-lookup"><span data-stu-id="67ecb-615">msRTCSIP-PoolData</span></span></p></td>
<td><p><span data-ttu-id="67ecb-616">この属性は、今後の使用のために予約されています。</span><span class="sxs-lookup"><span data-stu-id="67ecb-616">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="67ecb-617">Live Communications Server 2005 SP1 で導入されています。</span><span class="sxs-lookup"><span data-stu-id="67ecb-617">New in Live Communications Server 2005 with SP1.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="67ecb-618">msRTCSIP-PoolDisplayName</span><span class="sxs-lookup"><span data-stu-id="67ecb-618">msRTCSIP-PoolDisplayName</span></span></p></td>
<td><p><span data-ttu-id="67ecb-619">この属性は、管理コンソールによって表示されるプールの任意の名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="67ecb-619">This attribute specifies an arbitrary name for a pool that is displayed by the management console.</span></span> <span data-ttu-id="67ecb-620">この名前は、管理者が変更できます。</span><span class="sxs-lookup"><span data-stu-id="67ecb-620">This name can be changed by the administrator.</span></span></p>
<p><span data-ttu-id="67ecb-621">有効な値は、プールの名前を表す文字列です。</span><span class="sxs-lookup"><span data-stu-id="67ecb-621">The valid value is a string representing the name of a pool.</span></span></p></td>
<td><p><span data-ttu-id="67ecb-622">Live Communications Server 2005 の新しいもの。</span><span class="sxs-lookup"><span data-stu-id="67ecb-622">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="67ecb-623">msRTCSIP-PoolDomainFQDN</span><span class="sxs-lookup"><span data-stu-id="67ecb-623">msRTCSIP-PoolDomainFQDN</span></span></p></td>
<td><p><span data-ttu-id="67ecb-624">この属性は、単一値の文字列型 (string) の値です。</span><span class="sxs-lookup"><span data-stu-id="67ecb-624">This attribute is a single-valued string value.</span></span> <span data-ttu-id="67ecb-625">この属性の値は、フロントエンドプールが作成された Active Directory ドメイン構造 (SIP など) に準拠していない FQDN を持つフロントエンドプールを管理者が作成する場合に、プールのドメイン FQDN を表します。名前空間はドメインネームシステム (DNS) 名前空間から分離しています。</span><span class="sxs-lookup"><span data-stu-id="67ecb-625">The value of this attribute, when present, represents the pool’s domain FQDN if the administrator wants to create a Front End pool with an FQDN that does not conform to the Active Directory domain structure in which the Front End pool is created (for example, a SIP namespace disjoined from Domain Name System (DNS) namespace).</span></span></p>
<p><span data-ttu-id="67ecb-626">プールが存在する Active Directory ドメインとして、フロントエンドプールのドメイン FQDN をドメイン名部分にマップすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="67ecb-626">We recommend that you map the Front End pool domain FQDN to the domain name portion as the Active Directory domain in which the pool resides.</span></span> <span data-ttu-id="67ecb-627">そのため、この属性に値が指定されていない場合、フロントエンドプールの FQDN は、 <strong>dnsHostName</strong>属性によって示される Active Directory ドメイン名構造に既定で設定されます。</span><span class="sxs-lookup"><span data-stu-id="67ecb-627">Therefore, when no value is present in this attribute, the Front End pool FQDN will default to the Active Directory domain name structure, as denoted by the <strong>dnsHostName</strong> attribute.</span></span></p></td>
<td><p><span data-ttu-id="67ecb-628">Office Communications Server 2007 の新製品。</span><span class="sxs-lookup"><span data-stu-id="67ecb-628">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="67ecb-629">msRTCSIP-PoolFunctionality</span><span class="sxs-lookup"><span data-stu-id="67ecb-629">msRTCSIP-PoolFunctionality</span></span></p></td>
<td><p><span data-ttu-id="67ecb-630">プールに関連付けられたすべての Lync Server、Enterprise Edition サーバーのドメイン名の複数値リスト。</span><span class="sxs-lookup"><span data-stu-id="67ecb-630">A multi-valued list of the domain names of all Lync Server, Enterprise Edition servers associated with a pool.</span></span> <span data-ttu-id="67ecb-631">Integer 型の属性は、プールがインスタントメッセージング (IM) とプレゼンス、および会議をサポートするかどうかを定義します。</span><span class="sxs-lookup"><span data-stu-id="67ecb-631">This attribute of type integer defines whether the pool is capable of instant messaging (IM) and presence, and meetings.</span></span></p>
<p><span data-ttu-id="67ecb-632">有効な値の種類は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="67ecb-632">The possible valid value types are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="67ecb-633">未定義: IM およびプレゼンスサービス (Live Communications Server 2005 および 2003)</span><span class="sxs-lookup"><span data-stu-id="67ecb-633">Undefined: IM and Presence Service (Live Communications Server 2005 and 2003)</span></span></p></li>
<li><p><span data-ttu-id="67ecb-634">1: IM およびプレゼンスサービス (Lync Server)</span><span class="sxs-lookup"><span data-stu-id="67ecb-634">1: IM and Presence Service (Lync Server)</span></span></p></li>
<li><p><span data-ttu-id="67ecb-635">2: IM とプレゼンスおよび会議サービス (Lync Server)</span><span class="sxs-lookup"><span data-stu-id="67ecb-635">2: IM and Presence and Meeting Service (Lync Server)</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="67ecb-636">Office Communications Server 2007 の新製品。</span><span class="sxs-lookup"><span data-stu-id="67ecb-636">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="67ecb-637">msRTCSIP-PoolType</span><span class="sxs-lookup"><span data-stu-id="67ecb-637">msRTCSIP-PoolType</span></span></p></td>
<td><p><span data-ttu-id="67ecb-638">この属性は、サーバープールで Standard Edition サーバーまたは Enterprise Edition サーバーが実行されているかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="67ecb-638">This attribute specifies whether a server pool is running Standard Edition server or Enterprise Edition server.</span></span> <span data-ttu-id="67ecb-639">この属性は、integer 型のビットマスク値です。</span><span class="sxs-lookup"><span data-stu-id="67ecb-639">This attribute is a bit-mask value of type integer.</span></span> <span data-ttu-id="67ecb-640">各オプションはビットで表されます。</span><span class="sxs-lookup"><span data-stu-id="67ecb-640">Each option is represented by a bit.</span></span></p>
<p><span data-ttu-id="67ecb-641">有効な値 (および関連するビット位置) は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="67ecb-641">The valid values (and associated bit positions) are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="67ecb-642">1: Standard Edition サーバー、ユーザーをホストする (ビット位置 0)</span><span class="sxs-lookup"><span data-stu-id="67ecb-642">1: Standard Edition server, hosts users (bit position 0)</span></span></p></li>
<li><p><span data-ttu-id="67ecb-643">2: Enterprise Edition サーバー、ユーザーをホストする (ビット位置 1)</span><span class="sxs-lookup"><span data-stu-id="67ecb-643">2: Enterprise Edition server, hosts users (bit position 1)</span></span></p></li>
<li><p><span data-ttu-id="67ecb-644">4: Standard Edition サーバー、ホストアプリケーション (ビット位置 2)</span><span class="sxs-lookup"><span data-stu-id="67ecb-644">4: Standard Edition server, hosts applications (bit position 2)</span></span></p></li>
<li><p><span data-ttu-id="67ecb-645">8: Enterprise Edition サーバー、ホストアプリケーション (ビット位置 3)</span><span class="sxs-lookup"><span data-stu-id="67ecb-645">8: Enterprise Edition server, hosts applications (bit position 3)</span></span></p></li>
</ul>
<p><span data-ttu-id="67ecb-646">Lync Server はアプリケーションのみをホストするプールをサポートしていないため、有効な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="67ecb-646">Because Lync Server does not support pools that host only applications, the only valid values are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="67ecb-647">5: Standard Edition サーバー、ユーザーとアプリケーションをホストする (ビット位置0および 2)</span><span class="sxs-lookup"><span data-stu-id="67ecb-647">5: Standard Edition server, hosts users and applications (bit positions 0 and 2)</span></span></p></li>
<li><p><span data-ttu-id="67ecb-648">10: Enterprise Edition サーバー、ユーザーとアプリケーションをホストする (ビット位置1および 3)</span><span class="sxs-lookup"><span data-stu-id="67ecb-648">10: Enterprise Edition server, hosts users and applications (bit positions 1 and 3)</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="67ecb-649">Live Communications Server 2005 の新しいもの。</span><span class="sxs-lookup"><span data-stu-id="67ecb-649">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="67ecb-650">msRTCSIP-PoolVersion</span><span class="sxs-lookup"><span data-stu-id="67ecb-650">msRTCSIP-PoolVersion</span></span></p></td>
<td><p><span data-ttu-id="67ecb-651">プールバージョンを定義する属性です。</span><span class="sxs-lookup"><span data-stu-id="67ecb-651">This attribute defines the pool version.</span></span> <span data-ttu-id="67ecb-652">これは、主な製品リリースごとにインクリメントされる整数型です。</span><span class="sxs-lookup"><span data-stu-id="67ecb-652">It is an integer type that is incremented with each major product release.</span></span></p>
<p><span data-ttu-id="67ecb-653">有効な値の種類は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="67ecb-653">The possible valid value types are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="67ecb-654">0: Live Communications Server 2003</span><span class="sxs-lookup"><span data-stu-id="67ecb-654">0: Live Communications Server 2003</span></span></p></li>
<li><p><span data-ttu-id="67ecb-655">1: Live Communications Server 2005</span><span class="sxs-lookup"><span data-stu-id="67ecb-655">1: Live Communications Server 2005</span></span></p></li>
<li><p><span data-ttu-id="67ecb-656">2: Live Communications Server 2005 SP1</span><span class="sxs-lookup"><span data-stu-id="67ecb-656">2: Live Communications Server 2005 with SP1</span></span></p></li>
<li><p><span data-ttu-id="67ecb-657">3: Office Communications Server 2007</span><span class="sxs-lookup"><span data-stu-id="67ecb-657">3: Office Communications Server 2007</span></span></p></li>
<li><p><span data-ttu-id="67ecb-658">4: Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="67ecb-658">4: Office Communications Server 2007 R2</span></span></p></li>
<li><p><span data-ttu-id="67ecb-659">5: Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="67ecb-659">5: Lync Server 2010</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="67ecb-660">Live Communications Server 2005 SP1</span><span class="sxs-lookup"><span data-stu-id="67ecb-660">Live Communications Server 2005 with SP1.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="67ecb-661">msRTCSIP-PresenceFlags</span><span class="sxs-lookup"><span data-stu-id="67ecb-661">msRTCSIP-PresenceFlags</span></span></p></td>
<td><p><span data-ttu-id="67ecb-662">この属性には、プレゼンス設定を定義するオプションとフラグが含まれます。</span><span class="sxs-lookup"><span data-stu-id="67ecb-662">This attribute contains options and flags that define presence settings.</span></span></p></td>
<td><p><span data-ttu-id="67ecb-663">Office Communications Server 2007 R2 の新製品。</span><span class="sxs-lookup"><span data-stu-id="67ecb-663">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="67ecb-664">msRTCSIP-PresencePolicy</span><span class="sxs-lookup"><span data-stu-id="67ecb-664">msRTCSIP-PresencePolicy</span></span></p></td>
<td><p><span data-ttu-id="67ecb-665">この属性には、プレゼンスポリシーオブジェクトの DN が含まれています。</span><span class="sxs-lookup"><span data-stu-id="67ecb-665">This attribute contains the DN for a presence policy object.</span></span></p></td>
<td><p><span data-ttu-id="67ecb-666">Office Communications Server 2007 R2 の新製品。</span><span class="sxs-lookup"><span data-stu-id="67ecb-666">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="67ecb-667">msRTCSIP-Msrtcsip-primaryhomeserver</span><span class="sxs-lookup"><span data-stu-id="67ecb-667">msRTCSIP-PrimaryHomeServer</span></span></p></td>
<td><p><span data-ttu-id="67ecb-668">この属性は、SIP メッセージングのユーザーまたは連絡先を有効にします。</span><span class="sxs-lookup"><span data-stu-id="67ecb-668">This attribute enables a user or contact for SIP messaging.</span></span> <span data-ttu-id="67ecb-669">中央フォレストトポロジでは、ユーザーオブジェクトではなく連絡先オブジェクトが SIP が有効になっているため、連絡先クラスに追加されます。</span><span class="sxs-lookup"><span data-stu-id="67ecb-669">It is added to the contact class because in the central forest topology, contact objects, not user objects, are SIP enabled.</span></span></p>
<p><span data-ttu-id="67ecb-670">有効な値は、ユーザーが所属する Standard Edition サーバーまたは Enterprise Edition フロントエンドプールの DN です。</span><span class="sxs-lookup"><span data-stu-id="67ecb-670">The valid value is the DN of the Standard Edition server or Enterprise Edition Front End pool where a user is homed.</span></span></p></td>
<td><p><span data-ttu-id="67ecb-671">Live Communications Server 2005 の新しいもの。</span><span class="sxs-lookup"><span data-stu-id="67ecb-671">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="67ecb-672">msRTCSIP-PrimaryUserAddress</span><span class="sxs-lookup"><span data-stu-id="67ecb-672">msRTCSIP-PrimaryUserAddress</span></span></p></td>
<td><p><span data-ttu-id="67ecb-673">この属性には、指定されたユーザーの SIP アドレスが含まれます。</span><span class="sxs-lookup"><span data-stu-id="67ecb-673">This attribute contains the SIP address of a given user.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="67ecb-674">msRTCSIP-PrivateLine</span><span class="sxs-lookup"><span data-stu-id="67ecb-674">msRTCSIP-PrivateLine</span></span></p></td>
<td><p><span data-ttu-id="67ecb-675">プライベート回線デバイスのデバイス ID を含む属性です。</span><span class="sxs-lookup"><span data-stu-id="67ecb-675">This attribute contains the device ID of the private line device.</span></span></p></td>
<td><p><span data-ttu-id="67ecb-676">Lync Server 2010 の新。</span><span class="sxs-lookup"><span data-stu-id="67ecb-676">New in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="67ecb-677">msRTCSIP ルーティング可能</span><span class="sxs-lookup"><span data-stu-id="67ecb-677">msRTCSIP-Routable</span></span></p></td>
<td><p><span data-ttu-id="67ecb-678">この属性は、Lync Server が GRUU アドレスを使用してこのサービスにルーティングすることを承認されているかどうかを判断するために使用されるブール型の属性です。</span><span class="sxs-lookup"><span data-stu-id="67ecb-678">This attribute is a Boolean attribute used to determine whether Lync Server is authorized to route to this service using its GRUU address.</span></span> <span data-ttu-id="67ecb-679">この値が<strong>TRUE</strong>に設定されている場合、Lync Server はこのサービスへのルーティングを承認されています。</span><span class="sxs-lookup"><span data-stu-id="67ecb-679">If this value is set to <strong>TRUE</strong>, Lync Server is authorized to route to this service.</span></span> <span data-ttu-id="67ecb-680">この値が<strong>FALSE</strong>に設定されている場合、Lync Server はこのサービスへのルーティングを承認されていません。</span><span class="sxs-lookup"><span data-stu-id="67ecb-680">If this value is set to <strong>FALSE</strong>, Lync Server is not authorized to route to this service.</span></span></p></td>
<td><p><span data-ttu-id="67ecb-681">Office Communications Server 2007 の新製品。</span><span class="sxs-lookup"><span data-stu-id="67ecb-681">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="67ecb-682">msRTCSIP-Msrtcsip-routeusageattribute (現在不使用)</span><span class="sxs-lookup"><span data-stu-id="67ecb-682">msRTCSIP-RouteUsageAttribute (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="67ecb-683">この単一値の UNICODE 文字列属性は、電話ルートの使用を限定する属性を定義します。</span><span class="sxs-lookup"><span data-stu-id="67ecb-683">This single-valued UNICODE string attribute defines an attribute that qualifies the usage for a phone route.</span></span> <span data-ttu-id="67ecb-684">電話ルートの選択は、2つの要素、つまり、電話ルートに割り当てられる usage 属性と、発信者に許可されているポリシー使用法属性に基づいて決定されます。</span><span class="sxs-lookup"><span data-stu-id="67ecb-684">Selection of a phone route is determined based on two elements: the usage attribute assigned to the phone route and the caller’s allowed policy usage attributes.</span></span> <span data-ttu-id="67ecb-685">発信者の許可された使用法に一致する使用法属性を持つ最初の電話ルートが選択されています。</span><span class="sxs-lookup"><span data-stu-id="67ecb-685">The first phone route with a usage attribute that matches the caller’s allowed usage is selected.</span></span></p></td>
<td><p><span data-ttu-id="67ecb-686">Office Communications Server 2007 の新製品。</span><span class="sxs-lookup"><span data-stu-id="67ecb-686">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="67ecb-687">Lync Server 2010 では廃止されました。</span><span class="sxs-lookup"><span data-stu-id="67ecb-687">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="67ecb-688">msRTCSIP-Msrtcsip-routeusagelinks (現在不使用)</span><span class="sxs-lookup"><span data-stu-id="67ecb-688">msRTCSIP-RouteUsageLinks (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="67ecb-689">この複数値の識別名 (DN) 属性には、ルート使用法の識別名の一覧が含まれています。</span><span class="sxs-lookup"><span data-stu-id="67ecb-689">This multi-valued distinguished name (DN) attribute contains a list of route usage distinguished names.</span></span></p>
<p><span data-ttu-id="67ecb-690">前方リンク:<strong>リンク ID 11032</strong></span><span class="sxs-lookup"><span data-stu-id="67ecb-690">Forward link: <strong>Link ID 11032</strong></span></span></p>
<p><span data-ttu-id="67ecb-691">この属性は、対応する後方リンク<strong>msRTCSIP-msrtcsip-phoneroutebl です</strong>への転送リンクです。</span><span class="sxs-lookup"><span data-stu-id="67ecb-691">This attribute is a forward link to the corresponding back link <strong>msRTCSIP-PhoneRouteBL</strong>.</span></span></p></td>
<td><p><span data-ttu-id="67ecb-692">Lync Server 2010 では廃止されました。</span><span class="sxs-lookup"><span data-stu-id="67ecb-692">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="67ecb-693">msRTCSIP-RoutingPoolDN</span><span class="sxs-lookup"><span data-stu-id="67ecb-693">msRTCSIP-RoutingPoolDN</span></span></p></td>
<td><p><span data-ttu-id="67ecb-694">この MCU または信頼済みサービス宛てのすべての SIP トラフィックが通過する必要のあるプールを指す DN を含む属性です。</span><span class="sxs-lookup"><span data-stu-id="67ecb-694">This attribute contains the DN that points to the pool that all SIP traffic addressed to this MCU or Trusted Service must go through.</span></span></p></td>
<td><p><span data-ttu-id="67ecb-695">Office Communications Server 2007 R2 の新製品。</span><span class="sxs-lookup"><span data-stu-id="67ecb-695">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="67ecb-696">msRTCSIP-RuleName (現在不使用)</span><span class="sxs-lookup"><span data-stu-id="67ecb-696">msRTCSIP-RuleName (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="67ecb-697">正規化ルールのフレンドリ名を指定する単一値の UNICODE 文字列属性は、管理者が簡単に参照できるようにします。</span><span class="sxs-lookup"><span data-stu-id="67ecb-697">This single-valued UNICODE string attribute specifies the friendly name of the normalization rule, so it can easily be referenced by an administrator.</span></span></p></td>
<td><p><span data-ttu-id="67ecb-698">Office Communications Server 2007 の新製品。</span><span class="sxs-lookup"><span data-stu-id="67ecb-698">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="67ecb-699">Lync Server 2010 では廃止されました。</span><span class="sxs-lookup"><span data-stu-id="67ecb-699">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="67ecb-700">msRTCSIP-SchemaVersion</span><span class="sxs-lookup"><span data-stu-id="67ecb-700">msRTCSIP-SchemaVersion</span></span></p></td>
<td><p><span data-ttu-id="67ecb-701">この属性は、組織に現在展開されているスキーマのバージョンを表します。</span><span class="sxs-lookup"><span data-stu-id="67ecb-701">This attribute represents the schema version currently deployed in the organization.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="67ecb-702">msRTCSIP-SearchMaxRequests (obsolete)</span><span class="sxs-lookup"><span data-stu-id="67ecb-702">msRTCSIP-SearchMaxRequests (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="67ecb-703">ユーザーが Communicator を使用して連絡先を検索するときにディレクトリ検索から返される検索結果の数を制限する属性です。</span><span class="sxs-lookup"><span data-stu-id="67ecb-703">This attribute limits the number of search results to be returned from a directory search when a user searches for a contact using Communicator.</span></span> <span data-ttu-id="67ecb-704">この属性は、クライアントによって指定された値より優先されます。</span><span class="sxs-lookup"><span data-stu-id="67ecb-704">This attribute will override the value provided by the client.</span></span></p></td>
<td><p><span data-ttu-id="67ecb-705">Lync Server 2010 では廃止されました。</span><span class="sxs-lookup"><span data-stu-id="67ecb-705">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="67ecb-706">msRTCSIP-SearchMaxResults (現在不使用)</span><span class="sxs-lookup"><span data-stu-id="67ecb-706">msRTCSIP-SearchMaxResults (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="67ecb-707">この属性は、返される検索要求の数を制限します。</span><span class="sxs-lookup"><span data-stu-id="67ecb-707">This attribute limits the number of search requests returned.</span></span></p></td>
<td><p><span data-ttu-id="67ecb-708">Lync Server 2010 では廃止されました。</span><span class="sxs-lookup"><span data-stu-id="67ecb-708">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="67ecb-709">msRTCSIP-ServerBL</span><span class="sxs-lookup"><span data-stu-id="67ecb-709">msRTCSIP-ServerBL</span></span></p></td>
<td><p><span data-ttu-id="67ecb-710">この複数値属性は、識別名 (DN) の一覧を含む後方リンクです。</span><span class="sxs-lookup"><span data-stu-id="67ecb-710">This multi-valued attribute is a back link that contains a list of distinguished names (DN).</span></span> <span data-ttu-id="67ecb-711">これらの DNs は、プールまたは<strong>Trustedservice</strong>オブジェクトを指します。</span><span class="sxs-lookup"><span data-stu-id="67ecb-711">These DNs point to a pool or <strong>TrustedService</strong> object.</span></span></p>
<p><span data-ttu-id="67ecb-712">この属性は、Msrtcsip-trustedservicelinks ですの前方リンク<strong>msRTCSIP</strong>に対応します。</span><span class="sxs-lookup"><span data-stu-id="67ecb-712">This attribute corresponds to the forward link <strong>msRTCSIP-TrustedServiceLinks</strong>.</span></span></p></td>
<td><p><span data-ttu-id="67ecb-713">Office Communications Server 2007 の新製品。</span><span class="sxs-lookup"><span data-stu-id="67ecb-713">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="67ecb-714">msRTCSIP-ServerData</span><span class="sxs-lookup"><span data-stu-id="67ecb-714">msRTCSIP-ServerData</span></span></p></td>
<td><p><span data-ttu-id="67ecb-715">この属性は、今後の使用のために予約されています。</span><span class="sxs-lookup"><span data-stu-id="67ecb-715">This attribute is reserved for future use.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="67ecb-716">msRTCSIP-ServerReferenceBL (obsolete)</span><span class="sxs-lookup"><span data-stu-id="67ecb-716">msRTCSIP-ServerReferenceBL (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="67ecb-717">この複数値属性には、識別名の一覧が含まれています。</span><span class="sxs-lookup"><span data-stu-id="67ecb-717">This multi-valued attribute contains a list of distinguished names.</span></span> <span data-ttu-id="67ecb-718">これらの識別名は、既定の場所のプロファイルを割り当てることができる他のサーバーオブジェクトを参照する後方リンクです。</span><span class="sxs-lookup"><span data-stu-id="67ecb-718">These distinguished names are back links that reference other server objects that can be assigned a default location profile.</span></span></p>
<p><span data-ttu-id="67ecb-719">後方リンク:<strong>リンク ID 11037</strong></span><span class="sxs-lookup"><span data-stu-id="67ecb-719">Back link: <strong>Link ID 11037</strong></span></span></p>
<p><span data-ttu-id="67ecb-720">この後方リンクへの対応する転送リンクは<strong>msRTCSIP-DefaultLocationProfileLink</strong>です。</span><span class="sxs-lookup"><span data-stu-id="67ecb-720">The corresponding forward link to this back link is <strong>msRTCSIP-DefaultLocationProfileLink</strong>.</span></span></p>
<p><span data-ttu-id="67ecb-721">この後方リンク属性は、プールと仲介サーバーのみを参照します。</span><span class="sxs-lookup"><span data-stu-id="67ecb-721">This back link attribute references pools and Mediation Servers only.</span></span></p></td>
<td><p><span data-ttu-id="67ecb-722">Office Communications Server 2007 の新製品。</span><span class="sxs-lookup"><span data-stu-id="67ecb-722">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="67ecb-723">Lync Server 2010 では廃止されました。</span><span class="sxs-lookup"><span data-stu-id="67ecb-723">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="67ecb-724">msRTCSIP-ServerVersion</span><span class="sxs-lookup"><span data-stu-id="67ecb-724">msRTCSIP-ServerVersion</span></span></p></td>
<td><p><span data-ttu-id="67ecb-725">この属性は、サーバーのバージョン情報を定義します。</span><span class="sxs-lookup"><span data-stu-id="67ecb-725">This attribute defines the version information of the server.</span></span> <span data-ttu-id="67ecb-726">このバージョン番号は、すべてのサーバーの役割に適用されます。</span><span class="sxs-lookup"><span data-stu-id="67ecb-726">This version number applies to all server roles.</span></span> <span data-ttu-id="67ecb-727">これは、公式の製品リリースごとに増加する、monotonously の整数です。</span><span class="sxs-lookup"><span data-stu-id="67ecb-727">It is a monotonously increasing integer that increments with each official product release.</span></span></p>
<p><span data-ttu-id="67ecb-728">有効な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="67ecb-728">The possible valid values are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="67ecb-729">Undefined: Live Communications Server 2003</span><span class="sxs-lookup"><span data-stu-id="67ecb-729">Undefined: Live Communications Server 2003</span></span></p>
<p><span data-ttu-id="67ecb-730">                 Live Communications Server 2005</span><span class="sxs-lookup"><span data-stu-id="67ecb-730">                 Live Communications Server 2005</span></span></p>
<p><span data-ttu-id="67ecb-731">                 Live Communications Server 2005 with SP1</span><span class="sxs-lookup"><span data-stu-id="67ecb-731">                 Live Communications Server 2005 with SP1</span></span></p></li>
<li><p><span data-ttu-id="67ecb-732">3: Office Communications Server 2007</span><span class="sxs-lookup"><span data-stu-id="67ecb-732">3: Office Communications Server 2007</span></span></p></li>
<li><p><span data-ttu-id="67ecb-733">4: Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="67ecb-733">4: Office Communications Server 2007 R2</span></span></p></li>
<li><p><span data-ttu-id="67ecb-734">5: Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="67ecb-734">5: Lync Server 2010</span></span></p></li>
<li><p><span data-ttu-id="67ecb-735">6: Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="67ecb-735">6: Lync Server 2013</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="67ecb-736">Office Communications Server 2007 の新製品。</span><span class="sxs-lookup"><span data-stu-id="67ecb-736">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="67ecb-737">msRTCSIP-SourceObjectType</span><span class="sxs-lookup"><span data-stu-id="67ecb-737">msRTCSIP-SourceObjectType</span></span></p></td>
<td><p><span data-ttu-id="67ecb-738">次に示すように、integer 型のこの単一値属性は、 <strong>msds-sourceobjectdn</strong>が指すオブジェクトの種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="67ecb-738">This single-valued attribute of integer type specifies the type of object the <strong>msDS-SourceObjectDN</strong> points to, as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="67ecb-739">null |0x00000001: 別のフォレストの Windows NT Server プリンシパルユーザーオブジェクトを表します。</span><span class="sxs-lookup"><span data-stu-id="67ecb-739">null | 0x00000001: Represents a Windows NT Server principal user object from a different forest</span></span></p></li>
<li><p><span data-ttu-id="67ecb-740">次の属性は、配布グループ拡張のための別のフォレストのグループの種類を表します。</span><span class="sxs-lookup"><span data-stu-id="67ecb-740">The following attributes represent a group type from a different forest for distribution group expansion:</span></span></p>
<ul>
<li><p><span data-ttu-id="67ecb-741">0x00000002: ADS_GROUP_TYPE_GLOBAL_GROUP</span><span class="sxs-lookup"><span data-stu-id="67ecb-741">0x00000002: ADS_GROUP_TYPE_GLOBAL_GROUP</span></span></p></li>
<li><p><span data-ttu-id="67ecb-742">0x00000004: ADS_GROUP_TYPE_DOMAIN_LOCAL_GROUP</span><span class="sxs-lookup"><span data-stu-id="67ecb-742">0x00000004: ADS_GROUP_TYPE_DOMAIN_LOCAL_GROUP</span></span></p></li>
<li><p><span data-ttu-id="67ecb-743">0x00000004: ADS_GROUP_TYPE_LOCAL_GROUP</span><span class="sxs-lookup"><span data-stu-id="67ecb-743">0x00000004: ADS_GROUP_TYPE_LOCAL_GROUP</span></span></p></li>
<li><p><span data-ttu-id="67ecb-744">0x00000008: ADS_GROUP_TYPE_UNIVERSAL_GROUP</span><span class="sxs-lookup"><span data-stu-id="67ecb-744">0x00000008: ADS_GROUP_TYPE_UNIVERSAL_GROUP</span></span></p></li>
<li><p><span data-ttu-id="67ecb-745">0x80000000: ADS_GROUP_TYPE_SECURITY_ENABLED</span><span class="sxs-lookup"><span data-stu-id="67ecb-745">0x80000000: ADS_GROUP_TYPE_SECURITY_ENABLED</span></span></p></li>
<li><p><span data-ttu-id="67ecb-746">0x90000000: 同じフォレストまたは別のフォレストからの自動応答またはサブスクライバーアクセスオブジェクトを表します。</span><span class="sxs-lookup"><span data-stu-id="67ecb-746">0x90000000: Represents an Auto-Attendant or subscriber access object from the same forest or a different forest</span></span></p></li>
</ul></li>
</ul></td>
<td><p><span data-ttu-id="67ecb-747">Office Communications Server 2007 の新製品。</span><span class="sxs-lookup"><span data-stu-id="67ecb-747">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="67ecb-748">msRTCSIP-SubscriptionAuthRequired (obsolete)</span><span class="sxs-lookup"><span data-stu-id="67ecb-748">msRTCSIP-SubscriptionAuthRequired (obsolete)</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="67ecb-749">Live Communications Server 2003 の新しいもの。</span><span class="sxs-lookup"><span data-stu-id="67ecb-749">New in Live Communications Server 2003.</span></span></p>
<p><span data-ttu-id="67ecb-750">現在、Live Communications Server 2005 では使用されていません。</span><span class="sxs-lookup"><span data-stu-id="67ecb-750">Obsolete in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="67ecb-751">msRTCSIP-Targethoの場合</span><span class="sxs-lookup"><span data-stu-id="67ecb-751">msRTCSIP-TargetHomeServer</span></span></p></td>
<td><p><span data-ttu-id="67ecb-752">この属性を使用すると、1つの Lync Server プールから別のユーザーまたは連絡先オブジェクトを移動することができます。</span><span class="sxs-lookup"><span data-stu-id="67ecb-752">This attribute enables you to move a user or contact object from one Lync Server pool to another.</span></span> <span data-ttu-id="67ecb-753">この属性は contact クラスに追加されます。中央フォレストのトポロジでは、ユーザーオブジェクトではなく連絡先オブジェクトが SIP が有効になっているためです。</span><span class="sxs-lookup"><span data-stu-id="67ecb-753">This attribute is added to the contact class, because in the central forest topology, contact objects, not user objects, are SIP enabled.</span></span></p>
<p><span data-ttu-id="67ecb-754">有効な値は、ユーザーの移動先の Standard Edition サーバーまたはフロントエンドプールの DN です。</span><span class="sxs-lookup"><span data-stu-id="67ecb-754">The valid value is the DN of the destination Standard Edition server or Front End pool to which a user is to be moved.</span></span></p></td>
<td><p><span data-ttu-id="67ecb-755">Live Communications Server 2005 の新しいもの。</span><span class="sxs-lookup"><span data-stu-id="67ecb-755">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="67ecb-756">msRTCSIP-Msrtcsip-targetphonenumber (現在不使用)</span><span class="sxs-lookup"><span data-stu-id="67ecb-756">msRTCSIP-TargetPhoneNumber (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="67ecb-757"><strong>MsRTCSIP</strong>で定義されている特定のゲートウェイにルーティングする電話番号のパターンまたは範囲を含む単一値の文字列属性です。</span><span class="sxs-lookup"><span data-stu-id="67ecb-757">This single-valued string attribute contains a phone number pattern or range to route to the specified gateways defined in <strong>msRTCSIP-Gateways</strong>.</span></span></p></td>
<td><p><span data-ttu-id="67ecb-758">Lync Server 2010 では廃止されました。</span><span class="sxs-lookup"><span data-stu-id="67ecb-758">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="67ecb-759">msRTCSIP-TargetUserPolicies</span><span class="sxs-lookup"><span data-stu-id="67ecb-759">msRTCSIP-TargetUserPolicies</span></span></p></td>
<td><p><span data-ttu-id="67ecb-760">この属性は、Lync Server ユーザーのターゲットポリシーの名前と値のペアを格納します。</span><span class="sxs-lookup"><span data-stu-id="67ecb-760">This attribute stores name-value pairs for target policies for Lync Server users.</span></span></p></td>
<td><p><span data-ttu-id="67ecb-761">Lync Server 2010 の新。</span><span class="sxs-lookup"><span data-stu-id="67ecb-761">New in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="67ecb-762">msRTCSIP-TenantId</span><span class="sxs-lookup"><span data-stu-id="67ecb-762">msRTCSIP-TenantId</span></span></p></td>
<td><p><span data-ttu-id="67ecb-763">テナントの一意識別子を格納する属性です。</span><span class="sxs-lookup"><span data-stu-id="67ecb-763">This attribute stores the unique identifier for a tenant.</span></span></p></td>
<td><p><span data-ttu-id="67ecb-764">Lync Server 2010 の新。</span><span class="sxs-lookup"><span data-stu-id="67ecb-764">New in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="67ecb-765">msRTCSIP-変換 (現在不使用)</span><span class="sxs-lookup"><span data-stu-id="67ecb-765">msRTCSIP-Translation (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="67ecb-766">この属性は、Lync Server の音声機能によって使用され、一致が見つかった場合にダイヤル番号に適用する変換文字列を格納します。</span><span class="sxs-lookup"><span data-stu-id="67ecb-766">This attribute is used by the voice feature of Lync Server and contains the translation string to apply on the dialed number, if a match is found.</span></span></p></td>
<td><p><span data-ttu-id="67ecb-767">Office Communications Server 2007 の新製品。</span><span class="sxs-lookup"><span data-stu-id="67ecb-767">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="67ecb-768">Lync Server 2010 では廃止されました。</span><span class="sxs-lookup"><span data-stu-id="67ecb-768">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="67ecb-769">msRTCSIP-TrustedMCUData</span><span class="sxs-lookup"><span data-stu-id="67ecb-769">msRTCSIP-TrustedMCUData</span></span></p></td>
<td><p><span data-ttu-id="67ecb-770">この属性は、今後の使用のために予約されています。</span><span class="sxs-lookup"><span data-stu-id="67ecb-770">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="67ecb-771">Office Communications Server 2007 の新製品。</span><span class="sxs-lookup"><span data-stu-id="67ecb-771">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="67ecb-772">msRTCSIP-TrustedMCUFQDN</span><span class="sxs-lookup"><span data-stu-id="67ecb-772">msRTCSIP-TrustedMCUFQDN</span></span></p></td>
<td><p><span data-ttu-id="67ecb-773">この属性は、MCU の FQDN を含む文字列型 (string) の値です。</span><span class="sxs-lookup"><span data-stu-id="67ecb-773">This attribute is a string value that contains the FQDN of the MCU.</span></span> <span data-ttu-id="67ecb-774">これは単一値の属性です。</span><span class="sxs-lookup"><span data-stu-id="67ecb-774">This is a single-valued attribute.</span></span> <span data-ttu-id="67ecb-775">各セグメントの有効な値は、63文字です。FQDN 全体の有効な値は255文字です。</span><span class="sxs-lookup"><span data-stu-id="67ecb-775">The valid value for each segment is 63 characters; the valid value for the entire FQDN is 255 characters.</span></span></p></td>
<td><p><span data-ttu-id="67ecb-776">Office Communications Server 2007 の新製品。</span><span class="sxs-lookup"><span data-stu-id="67ecb-776">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="67ecb-777">msRTCSIP-TrustedProxyData</span><span class="sxs-lookup"><span data-stu-id="67ecb-777">msRTCSIP-TrustedProxyData</span></span></p></td>
<td><p><span data-ttu-id="67ecb-778">この属性は、今後の使用のために予約されています。</span><span class="sxs-lookup"><span data-stu-id="67ecb-778">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="67ecb-779">Office Communications Server 2007 の新製品。</span><span class="sxs-lookup"><span data-stu-id="67ecb-779">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="67ecb-780">msRTCSIP-TrustedProxyFQDN</span><span class="sxs-lookup"><span data-stu-id="67ecb-780">msRTCSIP-TrustedProxyFQDN</span></span></p></td>
<td><p><span data-ttu-id="67ecb-781">この属性は、プロキシサーバーを実行しているサーバーの FQDN を含む文字列型 (string) の値です。</span><span class="sxs-lookup"><span data-stu-id="67ecb-781">This attribute is a string value that contains the FQDN of the server running Proxy Server.</span></span> <span data-ttu-id="67ecb-782">この属性は単一値です。</span><span class="sxs-lookup"><span data-stu-id="67ecb-782">This attribute is single-valued.</span></span> <span data-ttu-id="67ecb-783">各セグメントの有効な値は、63文字です。FQDN 全体の有効な値は255文字です。</span><span class="sxs-lookup"><span data-stu-id="67ecb-783">The valid value for each segment is 63 characters; the valid value for the entire FQDN is 255 characters.</span></span></p></td>
<td><p><span data-ttu-id="67ecb-784">Office Communications Server 2007 の新製品。</span><span class="sxs-lookup"><span data-stu-id="67ecb-784">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="67ecb-785">msRTCSIP-TrustedServerData</span><span class="sxs-lookup"><span data-stu-id="67ecb-785">msRTCSIP-TrustedServerData</span></span></p></td>
<td><p><span data-ttu-id="67ecb-786">この属性は、今後の使用のために予約されています。</span><span class="sxs-lookup"><span data-stu-id="67ecb-786">This attribute is reserved for future use.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="67ecb-787">msRTCSIP-TrustedServerFQDN</span><span class="sxs-lookup"><span data-stu-id="67ecb-787">msRTCSIP-TrustedServerFQDN</span></span></p></td>
<td><p><span data-ttu-id="67ecb-788">この属性は、信頼済みサーバーの FQDN を表す単一値の属性です。</span><span class="sxs-lookup"><span data-stu-id="67ecb-788">This attribute is a single-valued attribute that represents the FQDN of a trusted server.</span></span></p></td>
<td><p><span data-ttu-id="67ecb-789">Live Communications Server 2005 の新しいもの。</span><span class="sxs-lookup"><span data-stu-id="67ecb-789">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="67ecb-790">msRTCSIP-TrustedServerVersion</span><span class="sxs-lookup"><span data-stu-id="67ecb-790">msRTCSIP-TrustedServerVersion</span></span></p></td>
<td><p><span data-ttu-id="67ecb-791">この属性は、信頼済みサーバーの一覧のサーバーのバージョン番号を指定します。</span><span class="sxs-lookup"><span data-stu-id="67ecb-791">This attribute specifies the version number of a server in the trusted server list.</span></span></p>
<p><span data-ttu-id="67ecb-792">有効な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="67ecb-792">The possible valid values are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="67ecb-793">NULL: Live Communications Server 2003</span><span class="sxs-lookup"><span data-stu-id="67ecb-793">NULL: Live Communications Server 2003</span></span></p></li>
<li><p><span data-ttu-id="67ecb-794">2: Live Communications Server 2005</span><span class="sxs-lookup"><span data-stu-id="67ecb-794">2: Live Communications Server 2005</span></span></p></li>
<li><p><span data-ttu-id="67ecb-795">3: Office Communications Server 2007</span><span class="sxs-lookup"><span data-stu-id="67ecb-795">3: Office Communications Server 2007</span></span></p></li>
<li><p><span data-ttu-id="67ecb-796">4: Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="67ecb-796">4: Office Communications Server 2007 R2</span></span></p></li>
<li><p><span data-ttu-id="67ecb-797">5: Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="67ecb-797">5: Lync Server 2010</span></span></p></li>
<li><p><span data-ttu-id="67ecb-798">6: Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="67ecb-798">6: Lync Server 2013</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="67ecb-799">Live Communications Server 2005 の新しいもの。</span><span class="sxs-lookup"><span data-stu-id="67ecb-799">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="67ecb-800">msRTCSIP-TrustedServiceFlags</span><span class="sxs-lookup"><span data-stu-id="67ecb-800">msRTCSIP-TrustedServiceFlags</span></span></p></td>
<td><p><span data-ttu-id="67ecb-801">この属性は、信頼済みサービスに対して有効になるオプションを定義します。</span><span class="sxs-lookup"><span data-stu-id="67ecb-801">This attribute defines the options that are enabled for the trusted service.</span></span></p></td>
<td><p><span data-ttu-id="67ecb-802">Office Communications Server 2007 R2 の新製品。</span><span class="sxs-lookup"><span data-stu-id="67ecb-802">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="67ecb-803">msRTCSIP-Msrtcsip-trustedservicelinks です</span><span class="sxs-lookup"><span data-stu-id="67ecb-803">msRTCSIP-TrustedServiceLinks</span></span></p></td>
<td><p><span data-ttu-id="67ecb-804">この複数値属性には、メディアリレー認証サービスなど、信頼されたサービスオブジェクトを参照する識別名 (DN) の一覧が含まれています。</span><span class="sxs-lookup"><span data-stu-id="67ecb-804">This multi-valued attribute contains a list of distinguished names (DN) that reference a trusted service object, such as a Media Relay Authentication Service.</span></span> <span data-ttu-id="67ecb-805">メディアリレー認証サービス (音声ビデオ会議サービスを実行しているエッジサーバーに物理的に併置されている) は、リモートユーザーのオーディオシナリオをサポートするために、プールに関連付けられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="67ecb-805">A Media Relay Authentication Service (physically collocated on the Edge Server running the A/V Conferencing service) must be associated with a pool to support audio scenarios for remote users.</span></span></p>
<p><span data-ttu-id="67ecb-806">この転送リンク属性への対応する後方リンクは、 <strong>msRTCSIP-ServerBL</strong>です。</span><span class="sxs-lookup"><span data-stu-id="67ecb-806">The corresponding back link to this forward link attribute is <strong>msRTCSIP-ServerBL</strong>.</span></span></p></td>
<td><p><span data-ttu-id="67ecb-807">UC</span><span class="sxs-lookup"><span data-stu-id="67ecb-807">UC</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="67ecb-808">msRTCSIP-TrustedServicePort</span><span class="sxs-lookup"><span data-stu-id="67ecb-808">msRTCSIP-TrustedServicePort</span></span></p></td>
<td><p><span data-ttu-id="67ecb-809">この GRUU サービスへの接続に使用するポート番号を定義する整数の属性です。</span><span class="sxs-lookup"><span data-stu-id="67ecb-809">This attribute is an integer that defines the port number used to connect to this GRUU service.</span></span></p></td>
<td><p><span data-ttu-id="67ecb-810">Office Communications Server 2007 の新製品。</span><span class="sxs-lookup"><span data-stu-id="67ecb-810">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="67ecb-811">msRTCSIP-TrustedServiceType</span><span class="sxs-lookup"><span data-stu-id="67ecb-811">msRTCSIP-TrustedServiceType</span></span></p></td>
<td><p><span data-ttu-id="67ecb-812">この属性は、それが表す GRUU サービスの種類を定義する文字列型 (string) の値です。</span><span class="sxs-lookup"><span data-stu-id="67ecb-812">This attribute is a string value that defines the type of GRUU service it represents.</span></span></p>
<p><span data-ttu-id="67ecb-813">有効な GRUU サービスの種類は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="67ecb-813">The valid GRUU service types are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="67ecb-814">MediationServer</span><span class="sxs-lookup"><span data-stu-id="67ecb-814">MediationServer</span></span></p></li>
<li><p><span data-ttu-id="67ecb-815">ゲートウェイ</span><span class="sxs-lookup"><span data-stu-id="67ecb-815">Gateway</span></span></p></li>
<li><p><span data-ttu-id="67ecb-816">メディアリレー認証サービス (MRAS)</span><span class="sxs-lookup"><span data-stu-id="67ecb-816">Media Relay Authentication Service (MRAS)</span></span></p></li>
<li><p><span data-ttu-id="67ecb-817">QoSM</span><span class="sxs-lookup"><span data-stu-id="67ecb-817">QoSM</span></span></p></li>
<li><p><span data-ttu-id="67ecb-818">msRTCSIP-UserExtension NM-CWA-NO-VERSION</span><span class="sxs-lookup"><span data-stu-id="67ecb-818">msRTCSIP-UserExtension CWA</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="67ecb-819">Office Communications Server 2007 の新製品。</span><span class="sxs-lookup"><span data-stu-id="67ecb-819">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="67ecb-820">msRTCSIP-Trustedwebコンポーネント Serverdata</span><span class="sxs-lookup"><span data-stu-id="67ecb-820">msRTCSIP-TrustedWebComponentsServerData</span></span></p></td>
<td><p><span data-ttu-id="67ecb-821">この属性は、今後の使用のために予約されています。</span><span class="sxs-lookup"><span data-stu-id="67ecb-821">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="67ecb-822">Office Communications Server 2007 の新製品。</span><span class="sxs-lookup"><span data-stu-id="67ecb-822">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="67ecb-823">msRTCSIP-Trustedwebコンポーネント Serverfqdn</span><span class="sxs-lookup"><span data-stu-id="67ecb-823">msRTCSIP-TrustedWebComponentsServerFQDN</span></span></p></td>
<td><p><span data-ttu-id="67ecb-824">この属性は、Lync Server Web サービスを実行している IIS の FQDN を含む文字列型 (string) の値です。</span><span class="sxs-lookup"><span data-stu-id="67ecb-824">This attribute is a string value that contains the FQDN of the IIS running Lync Server Web Services.</span></span> <span data-ttu-id="67ecb-825">これは単一値の属性です。</span><span class="sxs-lookup"><span data-stu-id="67ecb-825">This is a single-valued attribute.</span></span> <span data-ttu-id="67ecb-826">各セグメントの有効な値は、63文字です。FQDN 全体の有効な値は255文字です。</span><span class="sxs-lookup"><span data-stu-id="67ecb-826">The valid value for each segment is 63 characters; the valid value for the entire FQDN is 255 characters.</span></span></p></td>
<td><p><span data-ttu-id="67ecb-827">Office Communications Server 2007 の新製品。</span><span class="sxs-lookup"><span data-stu-id="67ecb-827">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="67ecb-828">msRTCSIP-UCFlags (obsolete)</span><span class="sxs-lookup"><span data-stu-id="67ecb-828">msRTCSIP-UCFlags (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="67ecb-829">この属性は、すべてのユーザーオブジェクトまたは連絡先オブジェクトに対してグローバルに有効になっているさまざまな UC オプションを定義します。</span><span class="sxs-lookup"><span data-stu-id="67ecb-829">This attribute defines different UC options that are enabled globally to all user or contact objects.</span></span> <span data-ttu-id="67ecb-830">この属性は、整数型のビットマスク値です。</span><span class="sxs-lookup"><span data-stu-id="67ecb-830">This attribute is a bit-mask value of integer type.</span></span> <span data-ttu-id="67ecb-831">各オプションは、ビットがあるかどうかで表されます。</span><span class="sxs-lookup"><span data-stu-id="67ecb-831">Each option is represented by the presence of a bit.</span></span></p>
<p><span data-ttu-id="67ecb-832">有効な値 (および関連するビット位置) は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="67ecb-832">The possible valid value (and associated bit position) are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="67ecb-833">4: UsePerUserUCPolicy (ビット位置 2)</span><span class="sxs-lookup"><span data-stu-id="67ecb-833">4: UsePerUserUCPolicy (bit position 2)</span></span></p></li>
</ul>
<p><span data-ttu-id="67ecb-834">このビットが設定されている場合、UC ポリシーはユーザーごとに定義されます。</span><span class="sxs-lookup"><span data-stu-id="67ecb-834">When this bit is set, the UC policy is defined per user.</span></span></p></td>
<td><p><span data-ttu-id="67ecb-835">Lync Server 2010 では廃止されました。</span><span class="sxs-lookup"><span data-stu-id="67ecb-835">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="67ecb-836">msRTCSIP-UCPolicy (現在不使用)</span><span class="sxs-lookup"><span data-stu-id="67ecb-836">msRTCSIP-UCPolicy (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="67ecb-837">この単一値の属性には、管理者がこのユーザーに対して割り当てた UC ポリシーの識別名 (DN) が含まれています。</span><span class="sxs-lookup"><span data-stu-id="67ecb-837">This single-valued attribute contains the distinguished name (DN) of the UC policy that the administrator has assigned for this user.</span></span></p></td>
<td><p><span data-ttu-id="67ecb-838">Lync Server 2010 では廃止されました。</span><span class="sxs-lookup"><span data-stu-id="67ecb-838">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="67ecb-839">msRTCSIP-UserDomainList (obsolete)</span><span class="sxs-lookup"><span data-stu-id="67ecb-839">msRTCSIP-UserDomainList (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="67ecb-840">この属性は、SIP が有効なユーザーをホストするフォレスト内のすべてのドメインの一覧を提供します。</span><span class="sxs-lookup"><span data-stu-id="67ecb-840">This attribute provides a list of all the domains in a forest that host SIP-enabled users.</span></span> <span data-ttu-id="67ecb-841">既定値は空のリストで、フォレスト内のすべてのドメインの SIP が有効になっていることを示します。</span><span class="sxs-lookup"><span data-stu-id="67ecb-841">The default is an empty list, indicating that all domains in the forest are SIP-enabled.</span></span></p>
<p><span data-ttu-id="67ecb-842">有効な値は、個々のドメインのドメイン名を表す複数の文字列です。</span><span class="sxs-lookup"><span data-stu-id="67ecb-842">Valid values are multiple strings representing the domain names of individual domains.</span></span></p></td>
<td><p><span data-ttu-id="67ecb-843">Live Communications Server 2005 の新しいもの。</span><span class="sxs-lookup"><span data-stu-id="67ecb-843">New in Live Communications Server 2005.</span></span></p>
<p><span data-ttu-id="67ecb-844">Lync Server 2010 では廃止されました。</span><span class="sxs-lookup"><span data-stu-id="67ecb-844">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="67ecb-845">msRTCSIP-UserEnabled</span><span class="sxs-lookup"><span data-stu-id="67ecb-845">msRTCSIP-UserEnabled</span></span></p></td>
<td><p><span data-ttu-id="67ecb-846">この属性は、ユーザーが Lync Server に対して現在有効になっているかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="67ecb-846">This attribute determines whether the user is currently enabled for Lync Server.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="67ecb-847">msRTCSIP-UserExtension</span><span class="sxs-lookup"><span data-stu-id="67ecb-847">msRTCSIP-UserExtension</span></span></p></td>
<td><p><span data-ttu-id="67ecb-848">Name = value の&quot;形式の名前と値のペアの一覧を含む複数値の属性です。&quot;この属性には、グローバルカタログレプリケーションのマークが付いています。</span><span class="sxs-lookup"><span data-stu-id="67ecb-848">This multi-valued attribute contains a list of name-value pairs in the format of &quot;name=value.&quot; This attribute is marked for global catalog replication.</span></span></p></td>
<td><p><span data-ttu-id="67ecb-849">Live Communications Server 2005 SP1 で導入されています。</span><span class="sxs-lookup"><span data-stu-id="67ecb-849">New in Live Communications Server 2005 with SP1.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="67ecb-850">msRTCSIP-UserLocationProfile</span><span class="sxs-lookup"><span data-stu-id="67ecb-850">msRTCSIP-UserLocationProfile</span></span></p></td>
<td><p><span data-ttu-id="67ecb-851">この属性には、場所のプロファイルオブジェクトを指す識別名 (DN) が含まれています。</span><span class="sxs-lookup"><span data-stu-id="67ecb-851">This attribute contains the distinguished name (DN) that points to a location profile object.</span></span></p></td>
<td><p><span data-ttu-id="67ecb-852">Office Communications Server 2007 R2 の新製品。</span><span class="sxs-lookup"><span data-stu-id="67ecb-852">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="67ecb-853">msRTCSIP-UserPolicies</span><span class="sxs-lookup"><span data-stu-id="67ecb-853">msRTCSIP-UserPolicies</span></span></p></td>
<td><p><span data-ttu-id="67ecb-854">この属性は、ユーザーポリシーの名前と値のペアを格納します。</span><span class="sxs-lookup"><span data-stu-id="67ecb-854">This attribute stores name-value pairs for user policies.</span></span></p></td>
<td><p><span data-ttu-id="67ecb-855">Lync Server 2010 の新。</span><span class="sxs-lookup"><span data-stu-id="67ecb-855">New in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="67ecb-856">msRTCSIP-UserPolicy</span><span class="sxs-lookup"><span data-stu-id="67ecb-856">msRTCSIP-UserPolicy</span></span></p></td>
<td><p><span data-ttu-id="67ecb-857">これは、異なる種類のグローバルユーザーポリシーをポイントするバイナリ (DN_WITH_BINARY) を含む複数値の属性です。</span><span class="sxs-lookup"><span data-stu-id="67ecb-857">This is a multi-valued attribute containing a list of distinguished names with binary (DN_WITH_BINARY) pointing to global user policies of different types.</span></span> <span data-ttu-id="67ecb-858">Binary 部分は、DN 部分が指すポリシーの種類を示します。</span><span class="sxs-lookup"><span data-stu-id="67ecb-858">The binary part indicates the type of policy to which the DN portion points.</span></span></p>
<p><span data-ttu-id="67ecb-859">有効なバイナリ値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="67ecb-859">The valid binary values are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="67ecb-860">0x00000001: 会議ポリシー</span><span class="sxs-lookup"><span data-stu-id="67ecb-860">0x00000001: Meeting policy</span></span></p></li>
<li><p><span data-ttu-id="67ecb-861">0x00000002: UC ポリシー</span><span class="sxs-lookup"><span data-stu-id="67ecb-861">0x00000002: UC policy</span></span></p></li>
<li><p><span data-ttu-id="67ecb-862">0x00000005: プレゼンスポリシー</span><span class="sxs-lookup"><span data-stu-id="67ecb-862">0x00000005: Presence policy</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="67ecb-863">Office Communications Server 2007 の新製品。</span><span class="sxs-lookup"><span data-stu-id="67ecb-863">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="67ecb-864">msRTCSIP-UserRoutingGroupId</span><span class="sxs-lookup"><span data-stu-id="67ecb-864">msRTCSIP-UserRoutingGroupId</span></span></p></td>
<td><p><span data-ttu-id="67ecb-p165">SIP ルーティング グループ ID。同じグループのユーザーは、同じフロントエンド サーバーに登録します。</span><span class="sxs-lookup"><span data-stu-id="67ecb-p165">This is the SIP routing group ID. Users in the same group will register to the same Front End Server.</span></span></p></td>
<td><p><span data-ttu-id="67ecb-867">Lync Server 2013 の新。</span><span class="sxs-lookup"><span data-stu-id="67ecb-867">New in Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="67ecb-868">msRTCSIP-Webコンポーネントデータ</span><span class="sxs-lookup"><span data-stu-id="67ecb-868">msRTCSIP-WebComponentsData</span></span></p></td>
<td><p><span data-ttu-id="67ecb-869">これは複数値の属性です。</span><span class="sxs-lookup"><span data-stu-id="67ecb-869">This is a multi-valued attribute.</span></span> <span data-ttu-id="67ecb-870">この属性は、今後の使用のために予約されています。</span><span class="sxs-lookup"><span data-stu-id="67ecb-870">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="67ecb-871">Office Communications Server 2007 の新製品。</span><span class="sxs-lookup"><span data-stu-id="67ecb-871">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="67ecb-872">msRTCSIP-Msrtcsip-webcomponentspooladdress</span><span class="sxs-lookup"><span data-stu-id="67ecb-872">msRTCSIP-WebComponentsPoolAddress</span></span></p></td>
<td><p><span data-ttu-id="67ecb-873">Web コンポーネントが属するプールまたは Standard Edition サーバーを示す単一値の属性です。</span><span class="sxs-lookup"><span data-stu-id="67ecb-873">This single-valued attribute points to the pool or Standard Edition server to which the web components belong.</span></span></p>
<p><span data-ttu-id="67ecb-874">前方リンク:<strong>リンク ID 11028</strong></span><span class="sxs-lookup"><span data-stu-id="67ecb-874">Forward link: <strong>Link ID 11028</strong></span></span></p>
<p><span data-ttu-id="67ecb-875">この転送リンク属性への対応する後方リンクは、 <strong>msRTCSIP-Webコンポーネントサーバー</strong>です。</span><span class="sxs-lookup"><span data-stu-id="67ecb-875">The corresponding back link to this forward link attribute is <strong>msRTCSIP-WebComponentsServers</strong>.</span></span></p></td>
<td><p><span data-ttu-id="67ecb-876">Office Communications Server 2007 の新製品。</span><span class="sxs-lookup"><span data-stu-id="67ecb-876">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="67ecb-877">msRTCSIP-Webコンポーネントサーバー</span><span class="sxs-lookup"><span data-stu-id="67ecb-877">msRTCSIP-WebComponentsServers</span></span></p></td>
<td><p><span data-ttu-id="67ecb-878">この属性は、複数値を持つ識別名の一覧です。</span><span class="sxs-lookup"><span data-stu-id="67ecb-878">This attribute is a multi-valued list of distinguished names.</span></span> <span data-ttu-id="67ecb-879">この属性には、このプールに関連付けられているすべての Web サーバーの一覧が含まれています。</span><span class="sxs-lookup"><span data-stu-id="67ecb-879">This attribute contains a list of all Web servers associated with this pool.</span></span></p>
<p><span data-ttu-id="67ecb-880">後方リンク:<strong>リンク ID 11029</strong></span><span class="sxs-lookup"><span data-stu-id="67ecb-880">Back link: <strong>Link ID 11029</strong></span></span></p>
<p><span data-ttu-id="67ecb-881">この後方リンクへの対応する転送リンクは、 <strong>msRTCSIP-msrtcsip-webcomponentspooladdress</strong>です。</span><span class="sxs-lookup"><span data-stu-id="67ecb-881">The corresponding forward link to this back link is <strong>msRTCSIP-WebComponentsPoolAddress</strong>.</span></span></p></td>
<td><p><span data-ttu-id="67ecb-882">Office Communications Server 2007 の新製品。</span><span class="sxs-lookup"><span data-stu-id="67ecb-882">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="67ecb-883">msRTCSIP (現在不使用)</span><span class="sxs-lookup"><span data-stu-id="67ecb-883">msRTCSIP-WMIInstanceId (obsolete)</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="67ecb-884">Live Communications Server 2003 の新しいもの。</span><span class="sxs-lookup"><span data-stu-id="67ecb-884">New in Live Communications Server 2003.</span></span></p>
<p><span data-ttu-id="67ecb-885">現在、Live Communications Server 2005 では使用されていません。</span><span class="sxs-lookup"><span data-stu-id="67ecb-885">Obsolete in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="67ecb-886">OtherIPPhone</span><span class="sxs-lookup"><span data-stu-id="67ecb-886">OtherIPPhone</span></span></p></td>
<td><p><span data-ttu-id="67ecb-887">この既存の Active Directory 属性は、テレフォニーが電話の代替 TCP/IP アドレスの一覧を指定するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="67ecb-887">This existing Active Directory attribute is used by telephony to specify the list of alternate TCP/IP addresses for a phone.</span></span></p></td>
<td><p><span data-ttu-id="67ecb-888">Windows Server 2008 オペレーティングシステムの新機能。</span><span class="sxs-lookup"><span data-stu-id="67ecb-888">New in Windows Server 2008 operating system.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="67ecb-889">電話電話 (その他)</span><span class="sxs-lookup"><span data-stu-id="67ecb-889">PhoneOfficeOther</span></span></p></td>
<td><p><span data-ttu-id="67ecb-890">この既存の Active Directory 属性は、Lync Server の音声コンポーネントによって使用されます。連絡先オブジェクトの場合は、ユニファイドメッセージングの自動応答およびサブスクライバーアクセス番号への呼び出しをルーティングすることを目的としています。</span><span class="sxs-lookup"><span data-stu-id="67ecb-890">This existing Active Directory attribute is used by the voice components in Lync Server, for contact objects only, for the purpose of routing calls to the unified messaging auto-attendant and subscriber access numbers.</span></span> <span data-ttu-id="67ecb-891">無条件着信転送アドレスは、この複数値属性に格納されます。</span><span class="sxs-lookup"><span data-stu-id="67ecb-891">The unconditional call forwarding address is stored in this multi-valued attribute.</span></span> <span data-ttu-id="67ecb-892">このアカウントは、自動応答およびサブスクライバーアクセスの特定の目的のために作成されます。</span><span class="sxs-lookup"><span data-stu-id="67ecb-892">This account is created for the specific purpose of auto-attendant and subscriber access.</span></span> <span data-ttu-id="67ecb-893">このアカウントの属性は、管理者が変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="67ecb-893">This account’s attributes should not be modified by administrators.</span></span></p></td>
<td><p><span data-ttu-id="67ecb-894">Windows 2000 オペレーティングシステムの新機能。</span><span class="sxs-lookup"><span data-stu-id="67ecb-894">New in Windows 2000 operating system.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="67ecb-895">ProxyAddresses</span><span class="sxs-lookup"><span data-stu-id="67ecb-895">ProxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="67ecb-896">この既存の Active Directory 複数値属性は、Windows 2000 で導入された base Active Directory スキーマの一部です。</span><span class="sxs-lookup"><span data-stu-id="67ecb-896">This existing Active Directory multi-valued attribute is part of the base Active Directory schema introduced in Windows 2000.</span></span> <span data-ttu-id="67ecb-897">この属性には、ユーザーの電子メールのさまざまな X400、X500、および SMTP アドレスが含まれています。</span><span class="sxs-lookup"><span data-stu-id="67ecb-897">This attribute contains the various X400, X500, and SMTP addresses of the user’s email.</span></span> <span data-ttu-id="67ecb-898">Live Communications Server 2003 以降では、 &quot;sip:&quot;タグを使用して、ユーザーの sip URI がこのリストに追加されます。</span><span class="sxs-lookup"><span data-stu-id="67ecb-898">In Live Communications Server 2003 and later, the user’s SIP URI is added to this list, using the &quot;sip:&quot; tag.</span></span></p>
<p><span data-ttu-id="67ecb-899">次のアプリケーションは、この属性からユーザーの SIP URI を検索します。</span><span class="sxs-lookup"><span data-stu-id="67ecb-899">The following applications search the user’s SIP URI from this attribute:</span></span></p>
<ul>
<li><p><span data-ttu-id="67ecb-900">Microsoft Office Outlook 2003 メッセージングおよびコラボレーションクライアント</span><span class="sxs-lookup"><span data-stu-id="67ecb-900">Microsoft Office Outlook 2003 messaging and collaboration client</span></span></p></li>
<li><p><span data-ttu-id="67ecb-901">Microsoft Office SharePoint Server 2007</span><span class="sxs-lookup"><span data-stu-id="67ecb-901">Microsoft Office SharePoint Server 2007</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="67ecb-902">Windows 2000 オペレーティングシステムの新機能。</span><span class="sxs-lookup"><span data-stu-id="67ecb-902">New in Windows 2000 operating system.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="67ecb-903">TelephoneNumber</span><span class="sxs-lookup"><span data-stu-id="67ecb-903">TelephoneNumber</span></span></p></td>
<td><p><span data-ttu-id="67ecb-904">この既存の Active Directory 属性には、ユーザーの電話番号が含まれています。</span><span class="sxs-lookup"><span data-stu-id="67ecb-904">This existing Active Directory attribute contains the telephone number for the user.</span></span></p></td>
<td><p><span data-ttu-id="67ecb-905">Windows 2000 オペレーティングシステムの新機能。</span><span class="sxs-lookup"><span data-stu-id="67ecb-905">New in Windows 2000 operating system.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

