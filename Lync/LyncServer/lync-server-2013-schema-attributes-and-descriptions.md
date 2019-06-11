---
title: 'Lync Server 2013: スキーマの属性と説明'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Schema attributes and descriptions
ms:assetid: b009df76-9c22-471d-b57a-bda009a98261
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412841(v=OCS.15)
ms:contentKeyID: 48185083
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fc18b4b074302ba3c233670f21fd8479bbd0b0f8
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34822644"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="schema-attributes-and-descriptions-in-lync-server-2013"></a><span data-ttu-id="75952-102">Lync Server 2013 でのスキーマの属性と説明</span><span class="sxs-lookup"><span data-stu-id="75952-102">Schema attributes and descriptions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="75952-103">_**最終更新日:** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="75952-103">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="75952-104">このセクションでは、Lync Server 2013 で使用されるすべてのスキーマ属性について説明します。</span><span class="sxs-lookup"><span data-stu-id="75952-104">This section describes all the schema attributes used by Lync Server 2013.</span></span> <span data-ttu-id="75952-105">属性に関連付けられているクラスについては、「 [Lync Server 2013 のクラス別のスキーマ属性](lync-server-2013-schema-attributes-by-class.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="75952-105">For the classes associated with attributes, see [Schema attributes by class in Lync Server 2013](lync-server-2013-schema-attributes-by-class.md).</span></span> <span data-ttu-id="75952-106">Lync Server 2013 で新しく追加されたクラスと属性の一覧については、「 [Lync server 2013 でのスキーマの変更](lync-server-2013-schema-changes-in-lync-server-2013.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="75952-106">For a list of classes and attributes that are new in Lync Server 2013, see [Schema changes in Lync Server 2013](lync-server-2013-schema-changes-in-lync-server-2013.md).</span></span>

<span data-ttu-id="75952-107">リンクペアの属性は、転送リンクまたは戻るリンクとして指定します。</span><span class="sxs-lookup"><span data-stu-id="75952-107">Attributes that are linked pairs are specified as forward links or back links.</span></span> <span data-ttu-id="75952-108">別のオブジェクトを参照する属性は、転送リンクです。最初のオブジェクトを参照する他のオブジェクトの属性は、[戻る] リンクです。</span><span class="sxs-lookup"><span data-stu-id="75952-108">An attribute that refers to another object is a forward link; the attribute of the other object that refers back to the first object is a back link.</span></span> <span data-ttu-id="75952-109">前方リンクは更新可能で、戻るリンクは読み取り専用です。</span><span class="sxs-lookup"><span data-stu-id="75952-109">Forward links are updatable, while back links are read-only.</span></span>

<span data-ttu-id="75952-110">一部の属性にはビットマスク値があります。</span><span class="sxs-lookup"><span data-stu-id="75952-110">Some attributes have a bit-mask value.</span></span> <span data-ttu-id="75952-111">これらの属性の場合、各設定は1ビットで表され、表示される10進値はビット位置を表します。</span><span class="sxs-lookup"><span data-stu-id="75952-111">For these attributes, each setting is represented by a bit, and the displayed decimal value represents the bit position.</span></span> <span data-ttu-id="75952-112">ビット位置はビット0から始まります。</span><span class="sxs-lookup"><span data-stu-id="75952-112">Bit positions start with bit 0.</span></span> <span data-ttu-id="75952-113">たとえば、1 (binary) はビット0に設定され、1万 (binary) はビット4で設定されています。</span><span class="sxs-lookup"><span data-stu-id="75952-113">For example, 1 (binary) is bit 0 set and 10000 (binary) is bit 4 set.</span></span> <span data-ttu-id="75952-114">各ビットはプロパティを表します。</span><span class="sxs-lookup"><span data-stu-id="75952-114">Each bit represents a property.</span></span> <span data-ttu-id="75952-115">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="75952-115">The following are some examples:</span></span>

  - <span data-ttu-id="75952-116">1万 (binary) の10進数は16です (つまり、ビット4が設定されています)。</span><span class="sxs-lookup"><span data-stu-id="75952-116">10000 (binary) has a decimal value of 16 (that is, bit 4 is set).</span></span>

  - <span data-ttu-id="75952-117">1億 (binary) の小数点以下の値は 256 (ビット8が設定されている) です。</span><span class="sxs-lookup"><span data-stu-id="75952-117">100000000 (binary) has a decimal value of 256 (that is, bit 8 is set).</span></span>

  - <span data-ttu-id="75952-118">1100 (binary) の10進数の値は12です (つまり、ビット2と3は設定され、両方のビットで表されるプロパティは有効です)。</span><span class="sxs-lookup"><span data-stu-id="75952-118">1100 (binary) has a decimal value of 12 (that is, bits 2 and 3 are set; properties represented by both bits are enabled).</span></span>

  - <span data-ttu-id="75952-119">1111000001 (binary) には、10進数の 961 (ビット0、6、7、8、および9の値が設定されています。これらの各ビットのプロパティは有効です)。</span><span class="sxs-lookup"><span data-stu-id="75952-119">1111000001 (binary) has a decimal value of 961 (that is, bits 0, 6, 7, 8, and 9 are set; properties for each of these bits are enabled).</span></span>

<div id="sectionSection0" class="section">

### <a name="schema-attributes-for-lync-server-2013"></a><span data-ttu-id="75952-120">Lync Server 2013 のスキーマ属性</span><span class="sxs-lookup"><span data-stu-id="75952-120">Schema Attributes for Lync Server 2013</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="75952-121">属性</span><span class="sxs-lookup"><span data-stu-id="75952-121">Attribute</span></span></th>
<th><span data-ttu-id="75952-122">説明</span><span class="sxs-lookup"><span data-stu-id="75952-122">Description</span></span></th>
<th><span data-ttu-id="75952-123">コメント</span><span class="sxs-lookup"><span data-stu-id="75952-123">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="75952-124">dnsHostName</span><span class="sxs-lookup"><span data-stu-id="75952-124">dnsHostName</span></span></p></td>
<td><p><span data-ttu-id="75952-125"><strong>Msrtcsip-userenabled true</strong>と<strong>msrtcsip-userenabled true の</strong>両方のサーバークラスに関連付けられている、Active Directory ドメインサービス内の既存の属性。</span><span class="sxs-lookup"><span data-stu-id="75952-125">An existing attribute in Active Directory Domain Services that is now associated with the <strong>msRTCSIP-Pool</strong> and <strong>msRTCSIP-MonitoringServer</strong> classes.</span></span> <span data-ttu-id="75952-126">この属性は、プールまたは監視サーバーの完全修飾ドメイン名 (FQDN) を指定します。</span><span class="sxs-lookup"><span data-stu-id="75952-126">This attribute specifies the fully qualified domain name (FQDN) of a pool or Monitoring Server.</span></span></p>
<p><span data-ttu-id="75952-127">各セグメントの有効な値は、63文字です。FQDN 全体の有効な値は、255文字です。</span><span class="sxs-lookup"><span data-stu-id="75952-127">A valid value for each segment is 63 characters; a valid value for the entire FQDN is 255 characters.</span></span></p></td>
<td><p><span data-ttu-id="75952-128">Microsoft Office Live Communications Server 2005 の新製品。</span><span class="sxs-lookup"><span data-stu-id="75952-128">New in Microsoft Office Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="75952-129">SourceObjectDN</span><span class="sxs-lookup"><span data-stu-id="75952-129">msDS-SourceObjectDN</span></span></p></td>
<td><p><span data-ttu-id="75952-130">この属性には、このオブジェクトに対応する別のフォレストのオブジェクトの識別名 (DN) の文字列表現が含まれます。</span><span class="sxs-lookup"><span data-stu-id="75952-130">This attribute contains the string representation of the distinguished name (DN) of the object in another forest that corresponds to this object.</span></span> <span data-ttu-id="75952-131">この属性は、配布グループの展開と自動参加に使用されます。</span><span class="sxs-lookup"><span data-stu-id="75952-131">This attribute is used for distribution group expansion and auto attendance.</span></span> <span data-ttu-id="75952-132">この属性は、Windows Server 2003 R2 の既定の Active Directory スキーマで定義されています。</span><span class="sxs-lookup"><span data-stu-id="75952-132">This attribute is defined in the default Active Directory schema for Windows Server 2003 R2.</span></span></p>
<p><span data-ttu-id="75952-133">AD DS から Windows Server 2003 R2 へのアップグレードを必要としないように、Active Directory スキーマの準備では、Windows Server 2003 スキーマがこの属性定義で拡張されます。</span><span class="sxs-lookup"><span data-stu-id="75952-133">To avoid requiring an upgrade of AD DS to Windows Server 2003 R2, Active Directory schema preparation extends the Windows Server 2003 schema with this attribute definition.</span></span></p></td>
<td><p><span data-ttu-id="75952-134">Microsoft Office Communications Server 2007 の新製品。</span><span class="sxs-lookup"><span data-stu-id="75952-134">New in Microsoft Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="75952-135">msExchUCVoiceMailSettings</span><span class="sxs-lookup"><span data-stu-id="75952-135">msExchUCVoiceMailSettings</span></span></p></td>
<td><p><span data-ttu-id="75952-136">この複数値属性はボイスメールの設定を保持します。</span><span class="sxs-lookup"><span data-stu-id="75952-136">This multi-valued attribute holds voice mail settings.</span></span> <span data-ttu-id="75952-137">この属性は、Exchange ユニファイドメッセージング (UM) と共有されます。</span><span class="sxs-lookup"><span data-stu-id="75952-137">This attribute is shared with Exchange Unified Messaging (UM).</span></span></p></td>
<td><p><span data-ttu-id="75952-138">Microsoft Lync Server 2010 の新製品です。</span><span class="sxs-lookup"><span data-stu-id="75952-138">New in Microsoft Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="75952-139">msExchUserHoldPolicies</span><span class="sxs-lookup"><span data-stu-id="75952-139">msExchUserHoldPolicies</span></span></p></td>
<td><p><span data-ttu-id="75952-140">このマルチバリュー属性は、ユーザーに適用される保留ポリシーの識別子を保持します。</span><span class="sxs-lookup"><span data-stu-id="75952-140">This multi-value attribute holds identifiers for hold policies that apply to the user.</span></span> <span data-ttu-id="75952-141">保留ポリシーは、保留中のユーザーのメールボックスアイテムを保持します。</span><span class="sxs-lookup"><span data-stu-id="75952-141">Hold policies preserve mailbox items for the user for the duration of the hold.</span></span> <span data-ttu-id="75952-142">この属性は Exchange 2013 と共有されます。</span><span class="sxs-lookup"><span data-stu-id="75952-142">This attribute is shared with Exchange 2013.</span></span></p></td>
<td><p><span data-ttu-id="75952-143">Lync Server 2013 の新サービスです。</span><span class="sxs-lookup"><span data-stu-id="75952-143">New in Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="75952-144">Msrtcsip-userenabled true-AcpInfo</span><span class="sxs-lookup"><span data-stu-id="75952-144">msRTCSIP-AcpInfo</span></span></p></td>
<td><p><span data-ttu-id="75952-145">この属性は、ユーザーに対して電話会議プロバイダーの情報を格納します。</span><span class="sxs-lookup"><span data-stu-id="75952-145">This attribute stores audio conferencing provider information for a user.</span></span></p></td>
<td><p><span data-ttu-id="75952-146">Lync Server 2010 の新サービスです。</span><span class="sxs-lookup"><span data-stu-id="75952-146">New in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="75952-147">Msrtcsip-userenabled true-ApplicationDestination</span><span class="sxs-lookup"><span data-stu-id="75952-147">msRTCSIP-ApplicationDestination</span></span></p></td>
<td><p><span data-ttu-id="75952-148">この属性は、アプリケーションの連絡先に対して信頼されているサービスエントリを指します。</span><span class="sxs-lookup"><span data-stu-id="75952-148">This attribute points to the trusted service entry for the application contact.</span></span></p></td>
<td><p><span data-ttu-id="75952-149">Microsoft Office Communications Server 2007 R2 の新製品。</span><span class="sxs-lookup"><span data-stu-id="75952-149">New in Microsoft Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="75952-150">Msrtcsip-userenabled true-ApplicationList</span><span class="sxs-lookup"><span data-stu-id="75952-150">msRTCSIP-ApplicationList</span></span></p></td>
<td><p><span data-ttu-id="75952-151">この属性には、アプリケーションサーバー上でホストされているアプリケーションの一覧が含まれます。</span><span class="sxs-lookup"><span data-stu-id="75952-151">This attribute contains a list of hosted applications on the application server.</span></span></p></td>
<td><p><span data-ttu-id="75952-152">Office Communications Server 2007 R2 の新製品。</span><span class="sxs-lookup"><span data-stu-id="75952-152">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="75952-153">Msrtcsip-userenabled true-ApplicationOptions</span><span class="sxs-lookup"><span data-stu-id="75952-153">msRTCSIP-ApplicationOptions</span></span></p></td>
<td><p><span data-ttu-id="75952-154">この属性は、アプリケーションの連絡先のオプションを指定します。</span><span class="sxs-lookup"><span data-stu-id="75952-154">This attribute specifies the options for the application contact.</span></span></p></td>
<td><p><span data-ttu-id="75952-155">Office Communications Server 2007 R2 の新製品。</span><span class="sxs-lookup"><span data-stu-id="75952-155">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="75952-156">Msrtcsip-userenabled true-ApplicationPrimaryLanguage</span><span class="sxs-lookup"><span data-stu-id="75952-156">msRTCSIP-ApplicationPrimaryLanguage</span></span></p></td>
<td><p><span data-ttu-id="75952-157">この属性には、アプリケーションの連絡先の第一言語が含まれます。</span><span class="sxs-lookup"><span data-stu-id="75952-157">This attribute contains the primary language for the application contact.</span></span></p></td>
<td><p><span data-ttu-id="75952-158">Office Communications Server 2007 R2 の新製品。</span><span class="sxs-lookup"><span data-stu-id="75952-158">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="75952-159">Msrtcsip-userenabled true-ApplicationSecondaryLanguages</span><span class="sxs-lookup"><span data-stu-id="75952-159">msRTCSIP-ApplicationSecondaryLanguages</span></span></p></td>
<td><p><span data-ttu-id="75952-160">この複数の値の属性には、アプリケーションの連絡先のセカンダリ言語が含まれています。</span><span class="sxs-lookup"><span data-stu-id="75952-160">This multiple value attribute contains the secondary languages for the application contact.</span></span></p></td>
<td><p><span data-ttu-id="75952-161">Office Communications Server 2007 R2 の新製品。</span><span class="sxs-lookup"><span data-stu-id="75952-161">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="75952-162">Msrtcsip-userenabled true-ApplicationServerBL</span><span class="sxs-lookup"><span data-stu-id="75952-162">msRTCSIP-ApplicationServerBL</span></span></p></td>
<td><p><span data-ttu-id="75952-163">この属性には、このプールに属しているアプリケーションサーバーの一覧が含まれます。</span><span class="sxs-lookup"><span data-stu-id="75952-163">This attribute contains a list of application servers that belong to this pool.</span></span> <span data-ttu-id="75952-164">このバックリンク属性への対応する前方リンクは<strong>Msrtcsip-userenabled true Serverpoollink</strong>です。</span><span class="sxs-lookup"><span data-stu-id="75952-164">The corresponding forward link to this back link attribute is <strong>msRTCSIP-ApplicationServerPoolLink</strong>.</span></span></p></td>
<td><p><span data-ttu-id="75952-165">Office Communications Server 2007 R2 の新製品。</span><span class="sxs-lookup"><span data-stu-id="75952-165">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="75952-166">Msrtcsip-userenabled true-ApplicationServerPoolLink</span><span class="sxs-lookup"><span data-stu-id="75952-166">msRTCSIP-ApplicationServerPoolLink</span></span></p></td>
<td><p><span data-ttu-id="75952-167">この属性は、このアプリケーションサーバーが属しているプールを指します。</span><span class="sxs-lookup"><span data-stu-id="75952-167">This attribute points to the pool to which this application server belongs.</span></span> <span data-ttu-id="75952-168">これは、転送リンクです。</span><span class="sxs-lookup"><span data-stu-id="75952-168">This is the forward link.</span></span> <span data-ttu-id="75952-169">対応する後方リンクは、 <strong>Msrtcsip-userenabled true Serverbl</strong>です。</span><span class="sxs-lookup"><span data-stu-id="75952-169">The corresponding backward link is <strong>msRTCSIP-ApplicationServerBL</strong>.</span></span></p></td>
<td><p><span data-ttu-id="75952-170">Office Communications Server 2007 R2 の新製品。</span><span class="sxs-lookup"><span data-stu-id="75952-170">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="75952-171">Msrtcsip-userenabled true-アーカイブの既定値 (廃止)</span><span class="sxs-lookup"><span data-stu-id="75952-171">msRTCSIP-ArchiveDefault (obsolete)</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="75952-172">Live Communications Server 2005 の新サービスです。</span><span class="sxs-lookup"><span data-stu-id="75952-172">New in Live Communications Server 2005.</span></span></p>
<p><span data-ttu-id="75952-173">Office Communications Server 2007 で廃止されます。</span><span class="sxs-lookup"><span data-stu-id="75952-173">Obsolete in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="75952-174">Msrtcsip-userenabled true-アーカイブ Defaultflags (廃止)</span><span class="sxs-lookup"><span data-stu-id="75952-174">msRTCSIP-ArchiveDefaultFlags (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="75952-175">この属性は、すべてのユーザーの通信をアーカイブするために、フォレストの境界内でグローバルな既定値を指定します。</span><span class="sxs-lookup"><span data-stu-id="75952-175">This attribute specifies the global default within the forest boundary for archiving all user communications.</span></span> <span data-ttu-id="75952-176">これは、アーカイブエージェントレイヤーによって適用されます。</span><span class="sxs-lookup"><span data-stu-id="75952-176">This is enforced by the archiving agent layer.</span></span> <span data-ttu-id="75952-177">この属性の値の範囲は、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="75952-177">The range of values for this attribute is as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="75952-178"><strong>TRUE</strong>: すべてのユーザーをアーカイブする</span><span class="sxs-lookup"><span data-stu-id="75952-178"><strong>TRUE</strong>: Archive all users</span></span></p></li>
<li><p><span data-ttu-id="75952-179"><strong>FALSE</strong>: すべてのユーザーをアーカイブしない</span><span class="sxs-lookup"><span data-stu-id="75952-179"><strong>FALSE</strong>: Do not archive all users</span></span></p></li>
</ul>
<p><span data-ttu-id="75952-180">この属性は、フォレストの境界内でのグローバルコントロールであり、内部ネットワーク内でのユーザーの通信はどのようにアーカイブされますか。</span><span class="sxs-lookup"><span data-stu-id="75952-180">This attribute globally controls, within the forest boundary, how user communications within an internal network are archived.</span></span></p>
<p><span data-ttu-id="75952-181"><strong>Live Communications Server 2005 の動作 (現在は廃止)</strong></span><span class="sxs-lookup"><span data-stu-id="75952-181"><strong>Live Communications Server 2005 behavior (now retired)</strong></span></span></p>
<p><span data-ttu-id="75952-182">この属性の値の範囲は、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="75952-182">The range of values for this attribute is as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="75952-183">0: メッセージ本文をアーカイブする [ビット 0]</span><span class="sxs-lookup"><span data-stu-id="75952-183">0: Archive the message body [bit 0]</span></span></p></li>
<li><p><span data-ttu-id="75952-184">1: メッセージ本文をアーカイブしない [ビット 0]</span><span class="sxs-lookup"><span data-stu-id="75952-184">1: Do not archive the message body [bit 0]</span></span></p></li>
</ul>
<p><span data-ttu-id="75952-185"><strong>Office Communications Server 2007 の動作</strong></span><span class="sxs-lookup"><span data-stu-id="75952-185"><strong>Office Communications Server 2007 behavior</strong></span></span></p>
<p><span data-ttu-id="75952-186">この属性の値の範囲は、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="75952-186">The range of values for this attribute is as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="75952-187">0: ArchiveFederationDefaultWithoutBody (廃止)</span><span class="sxs-lookup"><span data-stu-id="75952-187">0: ArchiveFederationDefaultWithoutBody (retired)</span></span></p></li>
<li><p><span data-ttu-id="75952-188">1-2: アーカイブ内部通信</span><span class="sxs-lookup"><span data-stu-id="75952-188">1-2: ArchiveInternalCommunications</span></span></p></li>
<li><p><span data-ttu-id="75952-189">3-4: ArchiveFederatedCommunications</span><span class="sxs-lookup"><span data-stu-id="75952-189">3-4: ArchiveFederatedCommunications</span></span></p></li>
<li><p><span data-ttu-id="75952-190">5: RecordPresenceRegistrations</span><span class="sxs-lookup"><span data-stu-id="75952-190">5: RecordPresenceRegistrations</span></span></p></li>
<li><p><span data-ttu-id="75952-191">6: RecordIMCallDetails</span><span class="sxs-lookup"><span data-stu-id="75952-191">6: RecordIMCallDetails</span></span></p></li>
<li><p><span data-ttu-id="75952-192">7: RecordGroupIMCallDetails</span><span class="sxs-lookup"><span data-stu-id="75952-192">7: RecordGroupIMCallDetails</span></span></p></li>
<li><p><span data-ttu-id="75952-193">8: RecordFileTransferInstances</span><span class="sxs-lookup"><span data-stu-id="75952-193">8: RecordFileTransferInstances</span></span></p></li>
<li><p><span data-ttu-id="75952-194">9: RecordAudioCallDetails</span><span class="sxs-lookup"><span data-stu-id="75952-194">9: RecordAudioCallDetails</span></span></p></li>
<li><p><span data-ttu-id="75952-195">10: RecordVideoCallDetails</span><span class="sxs-lookup"><span data-stu-id="75952-195">10: RecordVideoCallDetails</span></span></p></li>
<li><p><span data-ttu-id="75952-196">11: RecordRemoteAssistanceCallDetails</span><span class="sxs-lookup"><span data-stu-id="75952-196">11: RecordRemoteAssistanceCallDetails</span></span></p></li>
<li><p><span data-ttu-id="75952-197">12: RecordApplicationSharingDetails</span><span class="sxs-lookup"><span data-stu-id="75952-197">12: RecordApplicationSharingDetails</span></span></p></li>
<li><p><span data-ttu-id="75952-198">13: Record会議のインスタンス化</span><span class="sxs-lookup"><span data-stu-id="75952-198">13: RecordMeetingInstantiations</span></span></p></li>
<li><p><span data-ttu-id="75952-199">14: Record会議の結合</span><span class="sxs-lookup"><span data-stu-id="75952-199">14: RecordMeetingJoins</span></span></p></li>
<li><p><span data-ttu-id="75952-200">15: RecordDataJoins</span><span class="sxs-lookup"><span data-stu-id="75952-200">15: RecordDataJoins</span></span></p></li>
<li><p><span data-ttu-id="75952-201">16: RecordAVJoins</span><span class="sxs-lookup"><span data-stu-id="75952-201">16: RecordAVJoins</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="75952-202">Live Communications Server 2005 の新サービスです。</span><span class="sxs-lookup"><span data-stu-id="75952-202">New in Live Communications Server 2005.</span></span></p>
<p><span data-ttu-id="75952-203">Lync Server 2010 では廃止されています。</span><span class="sxs-lookup"><span data-stu-id="75952-203">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="75952-204">Msrtcsip-userenabled true-ArchiveFederationDefault (廃止)</span><span class="sxs-lookup"><span data-stu-id="75952-204">msRTCSIP-ArchiveFederationDefault (obsolete)</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="75952-205">Live Communications Server 2005 の新サービスです。</span><span class="sxs-lookup"><span data-stu-id="75952-205">New in Live Communications Server 2005.</span></span></p>
<p><span data-ttu-id="75952-206">Office Communications Server 2007 で廃止されます。</span><span class="sxs-lookup"><span data-stu-id="75952-206">Obsolete in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="75952-207">Msrtcsip-userenabled true-ArchiveFederationDefaultFlags (廃止)</span><span class="sxs-lookup"><span data-stu-id="75952-207">msRTCSIP-ArchiveFederationDefaultFlags (obsolete)</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="75952-208">Live Communications Server 2005 の新サービスです。</span><span class="sxs-lookup"><span data-stu-id="75952-208">New in Live Communications Server 2005.</span></span></p>
<p><span data-ttu-id="75952-209">Office Communications Server 2007 で廃止されます。</span><span class="sxs-lookup"><span data-stu-id="75952-209">Obsolete in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="75952-210">Msrtcsip-userenabled true-ArchivingEnabled</span><span class="sxs-lookup"><span data-stu-id="75952-210">msRTCSIP-ArchivingEnabled</span></span></p></td>
<td><p><span data-ttu-id="75952-211">この属性は、1人のユーザーの通信がアーカイブされるかどうかを制御するためのビットフィールドとして使用される整数です。</span><span class="sxs-lookup"><span data-stu-id="75952-211">This attribute is an integer used as a bit field to control whether a single user’s communications are to be archived.</span></span> <span data-ttu-id="75952-212">このコントロールは、アーカイブエージェントレイヤーによって適用されます。</span><span class="sxs-lookup"><span data-stu-id="75952-212">This control is enforced by the archiving agent layer.</span></span> <span data-ttu-id="75952-213">グローバルカタログのレプリケーション用にマークされています。</span><span class="sxs-lookup"><span data-stu-id="75952-213">It is marked for global catalog replication.</span></span></p>
<p><span data-ttu-id="75952-214">この属性の範囲は、1人のユーザーまたは連絡先によって異なります。</span><span class="sxs-lookup"><span data-stu-id="75952-214">The scope of this attribute is specific to a single user or contact.</span></span> <span data-ttu-id="75952-215">Lync Server の有効な値 (および関連するビット位置) は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="75952-215">The valid values (and associated bit positions) in Lync Server are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="75952-216">0: アーカイブしない (ビットセットなし)</span><span class="sxs-lookup"><span data-stu-id="75952-216">0: Do not archive (no bit set)</span></span></p></li>
<li><p><span data-ttu-id="75952-217">1: 廃止 (ビット位置 0)</span><span class="sxs-lookup"><span data-stu-id="75952-217">1: Retired (bit position 0)</span></span></p></li>
<li><p><span data-ttu-id="75952-218">2: 廃止 (ビット位置 1)</span><span class="sxs-lookup"><span data-stu-id="75952-218">2: Retired (bit position 1)</span></span></p></li>
<li><p><span data-ttu-id="75952-219">4: 内部通信をアーカイブする (ビット位置 2)</span><span class="sxs-lookup"><span data-stu-id="75952-219">4: Archive internal communications (bit position 2)</span></span></p></li>
<li><p><span data-ttu-id="75952-220">8: フェデレーション通信をアーカイブする (ビット位置 3)</span><span class="sxs-lookup"><span data-stu-id="75952-220">8: Archive federated communications (bit position 3)</span></span></p></li>
</ul>
<p><span data-ttu-id="75952-221">Live Communications Server 2005 で以前に有効になっていた値は、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="75952-221">Previously valid values in Live Communications Server 2005 are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="75952-222">0: Msrtcsip-userenabled true によって定義された既定値を使用します。これは、次の優先順位で、<strong>アーカイブの既定</strong>と<strong>msrtcsip-userenabled true フェデレーション</strong>によって定義されます。</span><span class="sxs-lookup"><span data-stu-id="75952-222">0:Use the default value defined by <strong>msRTCSIP-ArchiveDefault</strong> and <strong>msRTCSIP-ArchiveFederation</strong> in this order of precedence:</span></span></p>
<ul>
<li><p><span data-ttu-id="75952-223">1: アーカイブ</span><span class="sxs-lookup"><span data-stu-id="75952-223">1: Archive</span></span></p></li>
<li><p><span data-ttu-id="75952-224">2: アーカイブしない</span><span class="sxs-lookup"><span data-stu-id="75952-224">2: Do not archive</span></span></p></li>
<li><p><span data-ttu-id="75952-225">3: メッセージ本文を含まないアーカイブ</span><span class="sxs-lookup"><span data-stu-id="75952-225">3: Archive without the message body</span></span></p></li>
</ul></li>
</ul></td>
<td><p><span data-ttu-id="75952-226">Live Communications Server 2005 の新サービスです。</span><span class="sxs-lookup"><span data-stu-id="75952-226">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="75952-227">Msrtcsip-userenabled true-ArchivingServerData (廃止)</span><span class="sxs-lookup"><span data-stu-id="75952-227">msRTCSIP-ArchivingServerData (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="75952-228">この属性は将来使用するために予約されています。</span><span class="sxs-lookup"><span data-stu-id="75952-228">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="75952-229">Lync Server 2010 では廃止されています。</span><span class="sxs-lookup"><span data-stu-id="75952-229">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="75952-230">Msrtcsip-userenabled true-ArchivingServerVersion (廃止)</span><span class="sxs-lookup"><span data-stu-id="75952-230">msRTCSIP-ArchivingServerVersion (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="75952-231">この属性は、アーカイブサービスのバージョンを定義します。</span><span class="sxs-lookup"><span data-stu-id="75952-231">This attribute defines the version of the Archiving service.</span></span> <span data-ttu-id="75952-232">この属性は、各公式の製品リリースによってインクリメントされる monotonously の増加整数型です。</span><span class="sxs-lookup"><span data-stu-id="75952-232">This attribute is a monotonously increasing integer type that increments with each official product release.</span></span> <span data-ttu-id="75952-233">有効な値は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="75952-233">The possible valid values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="75952-234">未定義: Live Communications Server 2003</span><span class="sxs-lookup"><span data-stu-id="75952-234">Undefined: Live Communications Server 2003</span></span></p>
<p><span data-ttu-id="75952-235">                 Live Communications Server 2005</span><span class="sxs-lookup"><span data-stu-id="75952-235">                 Live Communications Server 2005</span></span></p>
<p><span data-ttu-id="75952-236">                 Live Communications Server 2005 SP1</span><span class="sxs-lookup"><span data-stu-id="75952-236">                 Live Communications Server 2005 with SP1</span></span></p></li>
<li><p><span data-ttu-id="75952-237">3: Office Communications Server 2007</span><span class="sxs-lookup"><span data-stu-id="75952-237">3: Office Communications Server 2007</span></span></p></li>
<li><p><span data-ttu-id="75952-238">4: Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="75952-238">4: Office Communications Server 2007 R2</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="75952-239">Office Communications Server 2007 の新製品。</span><span class="sxs-lookup"><span data-stu-id="75952-239">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="75952-240">Lync Server 2010 では廃止されています。</span><span class="sxs-lookup"><span data-stu-id="75952-240">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="75952-241">Msrtcsip-userenabled true-BackEndServer</span><span class="sxs-lookup"><span data-stu-id="75952-241">msRTCSIP-BackEndServer</span></span></p></td>
<td><p><span data-ttu-id="75952-242">この属性は、プールのバックエンドサーバーの FQDN を指定します。</span><span class="sxs-lookup"><span data-stu-id="75952-242">This attribute specifies the FQDN of the Back End Server of the pool.</span></span> <span data-ttu-id="75952-243">バックエンドサーバーは1つのプールにつき1つしか存在できないため、これは単一値の属性です。</span><span class="sxs-lookup"><span data-stu-id="75952-243">Because there can only be a single Back End Server per pool, this is a single-valued attribute.</span></span></p>
<p><span data-ttu-id="75952-244">各セグメントの有効な値は、63文字です。FQDN 全体の有効な値は、255文字です。</span><span class="sxs-lookup"><span data-stu-id="75952-244">The valid value for each segment is 63 characters; the valid value for the entire FQDN is 255 characters.</span></span></p></td>
<td><p><span data-ttu-id="75952-245">Live Communications Server 2005 の新サービスです。</span><span class="sxs-lookup"><span data-stu-id="75952-245">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="75952-246">Msrtcsip-userenabled true-ConferenceDirectoryHomePool</span><span class="sxs-lookup"><span data-stu-id="75952-246">msRTCSIP-ConferenceDirectoryHomePool</span></span></p></td>
<td><p><span data-ttu-id="75952-247">この属性には、会議ディレクトリをホストするプールの識別子が含まれます。</span><span class="sxs-lookup"><span data-stu-id="75952-247">This attribute contains the identifier of the pool that hosts the conference directory.</span></span></p></td>
<td><p><span data-ttu-id="75952-248">Office Communications Server 2007 R2 の新製品。</span><span class="sxs-lookup"><span data-stu-id="75952-248">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="75952-249">Msrtcsip-userenabled true-ConferenceDirectoryId</span><span class="sxs-lookup"><span data-stu-id="75952-249">msRTCSIP-ConferenceDirectoryId</span></span></p></td>
<td><p><span data-ttu-id="75952-250">この属性には、会議ディレクトリの識別子が含まれます。</span><span class="sxs-lookup"><span data-stu-id="75952-250">This attribute contains the identifier of a conference directory.</span></span></p></td>
<td><p><span data-ttu-id="75952-251">Office Communications Server 2007 R2 の新製品。</span><span class="sxs-lookup"><span data-stu-id="75952-251">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="75952-252">Msrtcsip-userenabled true-ConferenceDirectoryTargetPool</span><span class="sxs-lookup"><span data-stu-id="75952-252">msRTCSIP-ConferenceDirectoryTargetPool</span></span></p></td>
<td><p><span data-ttu-id="75952-253">この属性には、会議ディレクトリの移動先のプールの識別子が含まれています。</span><span class="sxs-lookup"><span data-stu-id="75952-253">This attribute contains the identifier of the pool to which the conference directory is being moved.</span></span></p></td>
<td><p><span data-ttu-id="75952-254">Office Communications Server 2007 R2 の新製品。</span><span class="sxs-lookup"><span data-stu-id="75952-254">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="75952-255">Msrtcsip-userenabled true-既定値</span><span class="sxs-lookup"><span data-stu-id="75952-255">msRTCSIP-Default</span></span></p></td>
<td><p><span data-ttu-id="75952-256">このブール値の属性は、電話の使用状況が既定で使用されているかどうかを定義します。</span><span class="sxs-lookup"><span data-stu-id="75952-256">This Boolean attribute defines whether the phone usage is a default usage.</span></span> <span data-ttu-id="75952-257">この属性が<strong>TRUE</strong>に設定されている場合、電話の使用状況は既定で使用されているため、管理者は削除できません。</span><span class="sxs-lookup"><span data-stu-id="75952-257">If this attribute is set to <strong>TRUE</strong>, the phone usage is a default usage and cannot be deleted by the administrator.</span></span> <span data-ttu-id="75952-258">この属性が<strong>FALSE</strong>に設定されている場合、使用法は削除できます。</span><span class="sxs-lookup"><span data-stu-id="75952-258">If this attribute is set to <strong>FALSE</strong>, the usage can be deleted.</span></span></p></td>
<td><p><span data-ttu-id="75952-259">Office Communications Server 2007 の新製品。</span><span class="sxs-lookup"><span data-stu-id="75952-259">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="75952-260">Msrtcsip-userenabled true-DefaultCWAExternalURL</span><span class="sxs-lookup"><span data-stu-id="75952-260">msRTCSIP-DefaultCWAExternalURL</span></span></p></td>
<td><p><span data-ttu-id="75952-261">この属性は、組織外のユーザーの Communicator Web Access URL を識別します。</span><span class="sxs-lookup"><span data-stu-id="75952-261">This attribute identifies the Communicator Web Access URL for users who are outside the organization.</span></span></p></td>
<td><p><span data-ttu-id="75952-262">Office Communications Server 2007 R2 の新製品。</span><span class="sxs-lookup"><span data-stu-id="75952-262">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="75952-263">Msrtcsip-userenabled true-DefaultCWAInternalURL</span><span class="sxs-lookup"><span data-stu-id="75952-263">msRTCSIP-DefaultCWAInternalURL</span></span></p></td>
<td><p><span data-ttu-id="75952-264">この属性は、組織内のユーザーの Communicator Web Access URL を識別します。</span><span class="sxs-lookup"><span data-stu-id="75952-264">This attribute identifies the Communicator Web Access URL for users who are inside the organization.</span></span></p></td>
<td><p><span data-ttu-id="75952-265">Office Communications Server 2007 R2 の新製品。</span><span class="sxs-lookup"><span data-stu-id="75952-265">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="75952-266">Msrtcsip-userenabled true-DefaultLocationProfileLink (廃止)</span><span class="sxs-lookup"><span data-stu-id="75952-266">msRTCSIP-DefaultLocationProfileLink (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="75952-267">この単一値の属性には、割り当てられた位置情報プロファイルクラスオブジェクトの識別名 (DN) が含まれます。</span><span class="sxs-lookup"><span data-stu-id="75952-267">This single-valued attribute contains the distinguished name (DN) of a location profile class object assigned to it.</span></span></p>
<p><span data-ttu-id="75952-268">転送リンク:<strong>リンク ID 11036</strong></span><span class="sxs-lookup"><span data-stu-id="75952-268">Forward link: <strong>Link ID 11036</strong></span></span></p>
<p><span data-ttu-id="75952-269">対応する後方リンクは、 <strong>msrtcsip-userenabled true-ServerReferenceBL</strong>です。</span><span class="sxs-lookup"><span data-stu-id="75952-269">The corresponding backward link is <strong>msRTCSIP-ServerReferenceBL</strong>.</span></span></p></td>
<td><p><span data-ttu-id="75952-270">Lync Server 2010 では廃止されています。</span><span class="sxs-lookup"><span data-stu-id="75952-270">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="75952-271">Msrtcsip-userenabled true-DefaultPolicy (廃止)</span><span class="sxs-lookup"><span data-stu-id="75952-271">msRTCSIP-DefaultPolicy (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="75952-272">このブール属性は、ポリシーが既定のポリシーであるかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="75952-272">This Boolean attribute specifies whether the policy is a default policy.</span></span> <span data-ttu-id="75952-273">ポリシーは、 <strong>TRUE</strong>に設定されている場合の既定のポリシーです。</span><span class="sxs-lookup"><span data-stu-id="75952-273">The policy is a default policy when set to <strong>TRUE</strong>.</span></span></p></td>
<td><p><span data-ttu-id="75952-274">Office Communications Server 2007 の新製品</span><span class="sxs-lookup"><span data-stu-id="75952-274">New in Office Communications Server 2007</span></span></p>
<p><span data-ttu-id="75952-275">Lync Server 2010 では廃止されています。</span><span class="sxs-lookup"><span data-stu-id="75952-275">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="75952-276">Msrtcsip-userenabled true-DefaultRouteToEdgeProxy (廃止)</span><span class="sxs-lookup"><span data-stu-id="75952-276">msRTCSIP-DefaultRouteToEdgeProxy (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="75952-277">この属性は、アクセスエッジサービスを実行しているエッジサーバーの FQDN (access edge サービスを実行しているサーバーのプールに直接アクセスできるか、またはハードウェアロードバランサー) を指定します。</span><span class="sxs-lookup"><span data-stu-id="75952-277">This attribute specifies the FQDN of either the Edge Server running the Access Edge service, if it can be accessed directly, or of the hardware load balancer for a pool of servers running Access Edge service.</span></span> <span data-ttu-id="75952-278">アクセスエッジサービスを実行しているサーバーが1つ以上のディレクターを介してのみアクセスできる場合、この属性は、ディレクタープールを提供するディレクターまたはハードウェアロードバランサーのポート番号を指定します。</span><span class="sxs-lookup"><span data-stu-id="75952-278">If the servers running Access Edge service can be accessed only through one or more Directors, this attribute specifies the FQDN and, optionally, the port number of the Director or of the hardware load balancer serving a Director pool.</span></span></p>
<p><span data-ttu-id="75952-279">各セグメントの有効な値は、63文字です。FQDN 全体の有効な値は、255文字です。</span><span class="sxs-lookup"><span data-stu-id="75952-279">The valid value for each segment is 63 characters; the valid value for the entire FQDN is 255 characters.</span></span></p></td>
<td><p><span data-ttu-id="75952-280">Live Communications Server 2005 の新サービスです。</span><span class="sxs-lookup"><span data-stu-id="75952-280">New in Live Communications Server 2005.</span></span></p>
<p><span data-ttu-id="75952-281">Lync Server 2010 では廃止されています。</span><span class="sxs-lookup"><span data-stu-id="75952-281">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="75952-282">Msrtcsip-userenabled true-DefaultRouteToEdgeProxyPort (廃止)</span><span class="sxs-lookup"><span data-stu-id="75952-282">msRTCSIP-DefaultRouteToEdgeProxyPort (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="75952-283">この属性は、アクセスエッジサービスを実行しているサーバーへの接続に使用するポート番号を表します。</span><span class="sxs-lookup"><span data-stu-id="75952-283">This attribute represents the port number that should be used to connect to the server running Access Edge service.</span></span></p>
<p><span data-ttu-id="75952-284">有効な値は、使用するポートを指定する整数値です。</span><span class="sxs-lookup"><span data-stu-id="75952-284">The valid value is an integer value specifying the port to be used.</span></span> <span data-ttu-id="75952-285">既定値は5061です。</span><span class="sxs-lookup"><span data-stu-id="75952-285">The default value is 5061.</span></span></p></td>
<td><p><span data-ttu-id="75952-286">Live Communications Server 2005 の新サービスです。</span><span class="sxs-lookup"><span data-stu-id="75952-286">New in Live Communications Server 2005.</span></span></p>
<p><span data-ttu-id="75952-287">Lync Server 2010 では廃止されています。</span><span class="sxs-lookup"><span data-stu-id="75952-287">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="75952-288">Msrtcsip-userenabled true-DefPresenceSubscriptionTimeout (廃止)</span><span class="sxs-lookup"><span data-stu-id="75952-288">msRTCSIP-DefPresenceSubscriptionTimeout (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="75952-289">この属性は、既定のプレゼンスサブスクリプションのタイムアウト期間を表します。</span><span class="sxs-lookup"><span data-stu-id="75952-289">This attribute represents the default presence subscription time-out period.</span></span></p></td>
<td><p><span data-ttu-id="75952-290">Lync Server 2010 では廃止されています。</span><span class="sxs-lookup"><span data-stu-id="75952-290">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="75952-291">Msrtcsip-userenabled true-DefRegistrationTimeout (廃止)</span><span class="sxs-lookup"><span data-stu-id="75952-291">msRTCSIP-DefRegistrationTimeout (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="75952-292">この属性は、既定の登録タイムアウトウィンドウを表します。</span><span class="sxs-lookup"><span data-stu-id="75952-292">This attribute represents the default registration time-out window.</span></span></p></td>
<td><p><span data-ttu-id="75952-293">Lync Server 2010 では廃止されています。</span><span class="sxs-lookup"><span data-stu-id="75952-293">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="75952-294">Msrtcsip-userenabled true-DefRoamingDataSubscriptionTimeout (廃止)</span><span class="sxs-lookup"><span data-stu-id="75952-294">msRTCSIP-DefRoamingDataSubscriptionTimeout (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="75952-295">この属性は、既定のローミングデータサブスクリプションのタイムアウトウィンドウを表します。</span><span class="sxs-lookup"><span data-stu-id="75952-295">This attribute represents the default roaming data subscription time-out window.</span></span></p></td>
<td><p><span data-ttu-id="75952-296">Lync Server 2010 では廃止されています。</span><span class="sxs-lookup"><span data-stu-id="75952-296">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="75952-297">msRTCSIP-DeploymentLocator</span><span class="sxs-lookup"><span data-stu-id="75952-297">msRTCSIP-DeploymentLocator</span></span></p></td>
<td><p><span data-ttu-id="75952-298">この属性は、分割ドメイントポロジで使用され、完全修飾ドメイン名 (FQDN) が含まれます。</span><span class="sxs-lookup"><span data-stu-id="75952-298">This attribute is used in a split domain topology and contains a fully qualified domain name (FQDN).</span></span></p></td>
<td><p><span data-ttu-id="75952-299">Lync Server 2010 の新サービスです。</span><span class="sxs-lookup"><span data-stu-id="75952-299">New in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="75952-300">Msrtcsip-userenabled true-Description (廃止)</span><span class="sxs-lookup"><span data-stu-id="75952-300">msRTCSIP-Description (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="75952-301">この単一値の UNICODE 文字列属性には、この電話ルートまたは正規化ルールのわかりやすい説明が含まれています。</span><span class="sxs-lookup"><span data-stu-id="75952-301">This single-valued UNICODE string attribute contains a friendly description of this phone route or normalization rule.</span></span></p></td>
<td><p><span data-ttu-id="75952-302">Office Communications Server 2007 の新製品。</span><span class="sxs-lookup"><span data-stu-id="75952-302">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="75952-303">Lync Server 2010 では廃止されています。</span><span class="sxs-lookup"><span data-stu-id="75952-303">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="75952-304">Msrtcsip-userenabled true-DomainData</span><span class="sxs-lookup"><span data-stu-id="75952-304">msRTCSIP-DomainData</span></span></p></td>
<td><p><span data-ttu-id="75952-305">この属性は将来使用するために予約されています。</span><span class="sxs-lookup"><span data-stu-id="75952-305">This attribute is reserved for future use.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="75952-306">Msrtcsip-userenabled true-ドメイン名</span><span class="sxs-lookup"><span data-stu-id="75952-306">msRTCSIP-DomainName</span></span></p></td>
<td><p><span data-ttu-id="75952-307">この属性は、レジストラー用に構成されているドメインを表します。</span><span class="sxs-lookup"><span data-stu-id="75952-307">This attribute represents a domain configured for the Registrar.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="75952-308">Msrtcsip-userenabled true-EdgeProxyData</span><span class="sxs-lookup"><span data-stu-id="75952-308">msRTCSIP-EdgeProxyData</span></span></p></td>
<td><p><span data-ttu-id="75952-309">この属性は将来使用するために予約されています。</span><span class="sxs-lookup"><span data-stu-id="75952-309">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="75952-310">Live Communications Server 2005 の新サービスです。</span><span class="sxs-lookup"><span data-stu-id="75952-310">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="75952-311">Msrtcsip-userenabled true-EdgeProxyFQDN</span><span class="sxs-lookup"><span data-stu-id="75952-311">msRTCSIP-EdgeProxyFQDN</span></span></p></td>
<td><p><span data-ttu-id="75952-312">この属性は、Access Edge サービスを実行しているサーバーの FQDN を指定します。</span><span class="sxs-lookup"><span data-stu-id="75952-312">This attribute specifies the FQDN of the server running Access Edge service.</span></span></p>
<p><span data-ttu-id="75952-313">各セグメントの有効な値は、63文字です。FQDN 全体の有効な値は、255文字です。</span><span class="sxs-lookup"><span data-stu-id="75952-313">The valid value for each segment is 63 characters; the valid value for the entire FQDN is 255 characters.</span></span></p></td>
<td><p><span data-ttu-id="75952-314">Live Communications Server 2005 の新サービスです。</span><span class="sxs-lookup"><span data-stu-id="75952-314">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="75952-315">Msrtcsip-userenabled true-EnableBestEffortNotify (廃止)</span><span class="sxs-lookup"><span data-stu-id="75952-315">msRTCSIP-EnableBestEffortNotify (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="75952-316">この属性は、クライアントからの SUBSCRIBE 要求に応じて、サーバーが NOTIFY 要求ではなく、ベストエフォート通知 (BENOTIFY) 要求を生成するかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="75952-316">This attribute controls whether a server generates a Best Effort NOTIFY (BENOTIFY) request, instead of a NOTIFY request, in response to a SUBSCRIBE request from a client.</span></span> <span data-ttu-id="75952-317">BENOTIFY は、通常の通知要求の代わりにサーバーが BENOTIFY 要求を生成する、サブスクライブ通知ハンドシェイクのパフォーマンス強化された拡張機能です。</span><span class="sxs-lookup"><span data-stu-id="75952-317">BENOTIFY is a performance-enhancing extension to the subscribe notification handshake where the server generates BENOTIFY requests, instead of regular NOTIFY requests.</span></span> <span data-ttu-id="75952-318">パフォーマンスの利点は、通知要求によって、BENOTIFY 要求でクライアントから 200 OK 応答が要求されないことです。</span><span class="sxs-lookup"><span data-stu-id="75952-318">The performance benefit is that a BENOTIFY request does not require a 200 OK response from the client as the NOTIFY request does.</span></span></p>
<p><span data-ttu-id="75952-319">有効な値は、 <strong>TRUE</strong>または<strong>FALSE</strong>です。</span><span class="sxs-lookup"><span data-stu-id="75952-319">The valid values are <strong>TRUE</strong> or <strong>FALSE</strong>.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="75952-320">Live Communications Server 2003 は BENOTIFY 要求をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="75952-320">Live Communications Server 2003 does not support BENOTIFY requests.</span></span> <span data-ttu-id="75952-321">Live communications server の2005とサードパーティのサーバーで実行されている Live Communications Server 2003 server API で記述されたサーバーアプリケーションと相互運用するには、BENOTIFY 要求の値を<STRONG>FALSE</STRONG>に設定して無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="75952-321">To interoperate with server applications written with the Live Communications Server 2003 server API running on Live Communications Server 2005 and third-party servers, BENOTIFY requests can be disabled by setting its value to <STRONG>FALSE</STRONG>.</span></span> <span data-ttu-id="75952-322">現在、BENOTIFY は IETF (インターネットエンジニアリングタスクフォース) SIP 標準化プロセスの一部ではありません。</span><span class="sxs-lookup"><span data-stu-id="75952-322">BENOTIFY is not currently part of the IETF (Internet Engineering Task Force) SIP standardization process.</span></span>


</div></td>
<td><p><span data-ttu-id="75952-323">Live Communications Server 2005 の新サービスです。</span><span class="sxs-lookup"><span data-stu-id="75952-323">New in Live Communications Server 2005.</span></span></p>
<p><span data-ttu-id="75952-324">Lync Server 2010 では廃止されています。</span><span class="sxs-lookup"><span data-stu-id="75952-324">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="75952-325">Msrtcsip-userenabled true-EnableFederation (廃止)</span><span class="sxs-lookup"><span data-stu-id="75952-325">msRTCSIP-EnableFederation (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="75952-326">この属性は、IT 管理者が他の組織のユーザーとの通信を許可するかどうかを構成するために使用するグローバルスイッチです。</span><span class="sxs-lookup"><span data-stu-id="75952-326">This attribute is a global switch that IT administrators use to configure whether users are allowed to communicate with users from other organizations.</span></span> <span data-ttu-id="75952-327">管理者が個々のユーザーの<strong>FederationEnabled</strong>属性を上書きできるようにします。</span><span class="sxs-lookup"><span data-stu-id="75952-327">It enables an administrator to overwrite an individual user’s <strong>FederationEnabled</strong> attribute.</span></span> <span data-ttu-id="75952-328">この属性は、ワーム、ウイルス、または企業の標的となる攻撃によって発生する可能性があるインターネット攻撃から内部ネットワークを保護するために役立ちます。</span><span class="sxs-lookup"><span data-stu-id="75952-328">This attribute can be useful to help protect the internal network from Internet attacks that may be caused by worms, viruses, or targeted attacks on the company.</span></span></p>
<p><span data-ttu-id="75952-329">有効な値 (および関連するビット位置) は、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="75952-329">The valid values (and associated bit positions) are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="75952-330">1: パブリック IM 接続を有効にする (ビット位置 0)</span><span class="sxs-lookup"><span data-stu-id="75952-330">1: Enabled for public IM connectivity (bit position 0)</span></span></p></li>
<li><p><span data-ttu-id="75952-331">2: 予約済み (ビット位置 1)</span><span class="sxs-lookup"><span data-stu-id="75952-331">2: Reserved (bit position 1)</span></span></p></li>
<li><p><span data-ttu-id="75952-332">4: 予約済み (ビット位置 2)</span><span class="sxs-lookup"><span data-stu-id="75952-332">4: Reserved (bit position 2)</span></span></p></li>
<li><p><span data-ttu-id="75952-333">8: 予約済み (ビット位置 3)</span><span class="sxs-lookup"><span data-stu-id="75952-333">8: Reserved (bit position 3)</span></span></p></li>
<li><p><span data-ttu-id="75952-334">16: リモート通話コントロールが有効になっている [Telephony] (ビット位置 4)</span><span class="sxs-lookup"><span data-stu-id="75952-334">16: Remote call control Enabled [Telephony] (bit position 4)</span></span></p></li>
<li><p><span data-ttu-id="75952-335">64: AllowOrganizeMeetingWithAnonymousParticipants (ユーザーが会議に匿名ユーザーを招待することを許可する (ビット位置 6)</span><span class="sxs-lookup"><span data-stu-id="75952-335">64: AllowOrganizeMeetingWithAnonymousParticipants (allow users to invite anonymous users to meetings (bit position 6)</span></span></p></li>
<li><p><span data-ttu-id="75952-336">128: UCEnabled (ユニファイドコミュニケーションのためのユーザーの有効化) (ビット位置 7)</span><span class="sxs-lookup"><span data-stu-id="75952-336">128: UCEnabled (enable users for unified communications) (bit position 7)</span></span></p></li>
<li><p><span data-ttu-id="75952-337">256: EnabledForEnhancedPresence (ユーザーにパブリック IM 接続を有効にする) (ビット位置 8)</span><span class="sxs-lookup"><span data-stu-id="75952-337">256: EnabledForEnhancedPresence (enable user for public IM connectivity) (bit position 8)</span></span></p></li>
<li><p><span data-ttu-id="75952-338">512: RemoteCallControlDualMode (ビット位置 9)</span><span class="sxs-lookup"><span data-stu-id="75952-338">512: RemoteCallControlDualMode (bit position 9)</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="75952-339">Live Communications Server 2005 の新サービスです。</span><span class="sxs-lookup"><span data-stu-id="75952-339">New in Live Communications Server 2005.</span></span></p>
<p><span data-ttu-id="75952-340">Lync Server 2010 では廃止されています。</span><span class="sxs-lookup"><span data-stu-id="75952-340">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="75952-341">Msrtcsip-userenabled true-EnterpriseServices</span><span class="sxs-lookup"><span data-stu-id="75952-341">msRTCSIP-EnterpriseServices</span></span></p></td>
<td><p><span data-ttu-id="75952-342">この属性は、エンタープライズサービスが指定されたサーバーに読み込まれているかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="75952-342">This attribute indicates whether the Enterprise Services are loaded on the given server.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="75952-343">Msrtcsip-userenabled true-ExtensionData</span><span class="sxs-lookup"><span data-stu-id="75952-343">msRTCSIP-ExtensionData</span></span></p></td>
<td><p><span data-ttu-id="75952-344">この属性は将来使用するために予約されています。</span><span class="sxs-lookup"><span data-stu-id="75952-344">This attribute is reserved for future use.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="75952-345">Msrtcsip-userenabled true-ExternalAccessCode</span><span class="sxs-lookup"><span data-stu-id="75952-345">msRTCSIP-ExternalAccessCode</span></span></p></td>
<td><p><span data-ttu-id="75952-346">この属性には、外部アクセスのダイヤルコードが含まれています。</span><span class="sxs-lookup"><span data-stu-id="75952-346">This attribute contains the dial code for external access.</span></span></p></td>
<td><p><span data-ttu-id="75952-347">Office Communications Server 2007 R2 の新製品。</span><span class="sxs-lookup"><span data-stu-id="75952-347">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="75952-348">Msrtcsip-userenabled true-FederationEnabled</span><span class="sxs-lookup"><span data-stu-id="75952-348">msRTCSIP-FederationEnabled</span></span></p></td>
<td><p><span data-ttu-id="75952-349">この属性は、1人のユーザーがフェデレーションを有効にしているかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="75952-349">This attribute controls whether a single user is enabled for federation.</span></span> <span data-ttu-id="75952-350">エンタープライズサービスレイヤーによって適用されます。</span><span class="sxs-lookup"><span data-stu-id="75952-350">It is enforced by the Enterprise Services layer.</span></span> <span data-ttu-id="75952-351">グローバルカタログのレプリケーション用にマークされています。</span><span class="sxs-lookup"><span data-stu-id="75952-351">It is marked for global catalog replication.</span></span></p>
<p><span data-ttu-id="75952-352">有効な値は、 <strong>TRUE</strong>または<strong>FALSE</strong>です。</span><span class="sxs-lookup"><span data-stu-id="75952-352">The valid values are <strong>TRUE</strong> or <strong>FALSE</strong>.</span></span></p></td>
<td><p><span data-ttu-id="75952-353">Live Communications Server 2005 の新サービスです。</span><span class="sxs-lookup"><span data-stu-id="75952-353">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="75952-354">Msrtcsip-userenabled true-FrontEndServers</span><span class="sxs-lookup"><span data-stu-id="75952-354">msRTCSIP-FrontEndServers</span></span></p></td>
<td><p><span data-ttu-id="75952-355">この属性は、プールに関連付けられたすべての Enterprise Edition サーバーのドメイン名の複数値を持つ一覧です。</span><span class="sxs-lookup"><span data-stu-id="75952-355">This attribute is a multi-valued list of the domain names of all Enterprise Edition servers associated with a pool.</span></span></p>
<p><span data-ttu-id="75952-356">戻るリンク:<strong>リンク ID 11023</strong></span><span class="sxs-lookup"><span data-stu-id="75952-356">Back link: <strong>Link ID 11023</strong></span></span></p>
<p><span data-ttu-id="75952-357">この戻るリンクへの対応する前方リンクは<strong>msrtcsip-userenabled true の住所</strong>です。</span><span class="sxs-lookup"><span data-stu-id="75952-357">The corresponding forward link to this back link is <strong>msRTCSIP-PoolAddress</strong>.</span></span></p></td>
<td><p><span data-ttu-id="75952-358">Live Communications Server 2005 の新サービスです。</span><span class="sxs-lookup"><span data-stu-id="75952-358">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="75952-359">Msrtcsip-userenabled true-ゲートウェイ (廃止)</span><span class="sxs-lookup"><span data-stu-id="75952-359">msRTCSIP-Gateways (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="75952-360">この複数値文字列属性には、ゲートウェイとポート (ゲートウェイごと) の一覧が含まれています。</span><span class="sxs-lookup"><span data-stu-id="75952-360">This multi-valued string attribute contains a list of gateways and ports (per gateway).</span></span></p></td>
<td><p><span data-ttu-id="75952-361">Lync Server 2010 では廃止されています。</span><span class="sxs-lookup"><span data-stu-id="75952-361">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="75952-362">Msrtcsip-userenabled true-GlobalSettingsData (廃止)</span><span class="sxs-lookup"><span data-stu-id="75952-362">msRTCSIP-GlobalSettingsData (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="75952-363">この属性には、名前と値のペアが格納されます。</span><span class="sxs-lookup"><span data-stu-id="75952-363">This attribute stores name:value pairs.</span></span> <span data-ttu-id="75952-364">既に定義された名前: 値のペアは、プレゼンス設定の [<strong>ポーリングを許可</strong>する] に対応しています。</span><span class="sxs-lookup"><span data-stu-id="75952-364">The already-defined name:value pair is for the <strong>allow polling for presence</strong> setting.</span></span></p></td>
<td><p><span data-ttu-id="75952-365">Lync Server 2010 では廃止されています。</span><span class="sxs-lookup"><span data-stu-id="75952-365">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="75952-366">Msrtcsip-userenabled true-GroupingID</span><span class="sxs-lookup"><span data-stu-id="75952-366">msRTCSIP-GroupingID</span></span></p></td>
<td><p><span data-ttu-id="75952-367">この属性は、アドレス帳のエントリをグループ化するために使用されるグループの一意の識別子です。</span><span class="sxs-lookup"><span data-stu-id="75952-367">This attribute is a unique identifier of a group that is used to group address book entries.</span></span></p></td>
<td><p><span data-ttu-id="75952-368">Lync Server 2010 の新サービスです。</span><span class="sxs-lookup"><span data-stu-id="75952-368">New in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="75952-369">Msrtcsip-userenabled true-HomeServer (廃止)</span><span class="sxs-lookup"><span data-stu-id="75952-369">msRTCSIP-HomeServer (obsolete)</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="75952-370">最新のライブ通信サーバー 2003 (使用されていません)。</span><span class="sxs-lookup"><span data-stu-id="75952-370">New in Live Communications Server 2003 (not used).</span></span></p>
<p><span data-ttu-id="75952-371">現在、ライブ通信サーバー2005で廃止されています。</span><span class="sxs-lookup"><span data-stu-id="75952-371">Obsolete in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="75952-372">Msrtcsip-userenabled true-HomeServerString (廃止)</span><span class="sxs-lookup"><span data-stu-id="75952-372">msRTCSIP-HomeServerString (obsolete)</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="75952-373">Live Communications Server 2003 の新サービスです。</span><span class="sxs-lookup"><span data-stu-id="75952-373">New in Live Communications Server 2003.</span></span></p>
<p><span data-ttu-id="75952-374">現在、ライブ通信サーバー2005で廃止されています。</span><span class="sxs-lookup"><span data-stu-id="75952-374">Obsolete in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="75952-375">Msrtcsip-userenabled true-ホームユーザー (廃止)</span><span class="sxs-lookup"><span data-stu-id="75952-375">msRTCSIP-HomeUsers (obsolete)</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="75952-376">最新のライブ通信サーバー 2003 (使用されていません)。</span><span class="sxs-lookup"><span data-stu-id="75952-376">New in Live Communications Server 2003 (not used).</span></span></p>
<p><span data-ttu-id="75952-377">現在、ライブ通信サーバー2005で廃止されています。</span><span class="sxs-lookup"><span data-stu-id="75952-377">Obsolete in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="75952-378">Msrtcsip-userenabled true-InternetAccessEnabled</span><span class="sxs-lookup"><span data-stu-id="75952-378">msRTCSIP-InternetAccessEnabled</span></span></p></td>
<td><p><span data-ttu-id="75952-379">この属性は、1人のユーザーが外部ユーザーアクセスを有効にしているかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="75952-379">This attribute controls whether a single user is enabled for outside user access.</span></span> <span data-ttu-id="75952-380">エンタープライズサービスレイヤーによって適用されます。</span><span class="sxs-lookup"><span data-stu-id="75952-380">It is enforced by the Enterprise Services layer.</span></span> <span data-ttu-id="75952-381">グローバルカタログのレプリケーション用にマークされています。</span><span class="sxs-lookup"><span data-stu-id="75952-381">It is marked for global catalog replication.</span></span></p>
<p><span data-ttu-id="75952-382">有効な値は、 <strong>TRUE</strong>または<strong>FALSE</strong>です。</span><span class="sxs-lookup"><span data-stu-id="75952-382">The valid values are <strong>TRUE</strong> or <strong>FALSE</strong>.</span></span></p></td>
<td><p><span data-ttu-id="75952-383">Live Communications Server 2005 の新サービスです。</span><span class="sxs-lookup"><span data-stu-id="75952-383">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="75952-384">Msrtcsip-userenabled true-IsMaster (廃止)</span><span class="sxs-lookup"><span data-stu-id="75952-384">msRTCSIP-IsMaster (obsolete)</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="75952-385">最新のライブコミュニケーションサーバー2003</span><span class="sxs-lookup"><span data-stu-id="75952-385">New in Live Communications Server 2003</span></span></p>
<p><span data-ttu-id="75952-386">現在、ライブ通信サーバー2005で廃止されています。</span><span class="sxs-lookup"><span data-stu-id="75952-386">Obsolete in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="75952-387">Msrtcsip-userenabled true ライン</span><span class="sxs-lookup"><span data-stu-id="75952-387">msRTCSIP-Line</span></span></p></td>
<td><p><span data-ttu-id="75952-388">この単一値の属性には、Lync for telephony によって使用されるデバイス ID (SIP URI またはユーザーが制御する電話の TEL URI のいずれか) が含まれます。</span><span class="sxs-lookup"><span data-stu-id="75952-388">This single-valued attribute contains the device ID (either the SIP URI or the TEL URI of the phone the user controls) used by Lync for telephony.</span></span> <span data-ttu-id="75952-389">この属性はグローバルカタログのレプリケーション用にマークされ、インデックスが作成されます。</span><span class="sxs-lookup"><span data-stu-id="75952-389">This attribute is marked for Global Catalog replication and is indexed.</span></span> <span data-ttu-id="75952-390">ユーザーがエンタープライズ Voip を有効にしている場合、この属性には、ユーザーの電話番号の E.i 正規化されたバージョンが格納されます。</span><span class="sxs-lookup"><span data-stu-id="75952-390">If a user is enabled for Enterprise Voice, this attribute stores the E.164 normalized version of the user’s phone number.</span></span></p></td>
<td><p><span data-ttu-id="75952-391">Microsoft Office Live Communications Server 2005 SP1 の新製品</span><span class="sxs-lookup"><span data-stu-id="75952-391">New in Microsoft Office Live Communications Server 2005 with SP1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="75952-392">Msrtcsip-userenabled true</span><span class="sxs-lookup"><span data-stu-id="75952-392">msRTCSIP-LineServer</span></span></p></td>
<td><p><span data-ttu-id="75952-393">この単一値属性には、CSTA-SIP ゲートウェイサーバーの SIP URI が含まれています。</span><span class="sxs-lookup"><span data-stu-id="75952-393">This single-valued attribute contains the SIP URI of the CSTA-SIP gateway server.</span></span> <span data-ttu-id="75952-394">この属性はグローバルカタログのレプリケーション用にマークされていますが、インデックスは作成されません。</span><span class="sxs-lookup"><span data-stu-id="75952-394">This attribute is marked for Global Catalog replication but is not indexed.</span></span></p></td>
<td><p><span data-ttu-id="75952-395">Microsoft Office Live Communications Server 2005 SP1 の新製品</span><span class="sxs-lookup"><span data-stu-id="75952-395">New in Microsoft Office Live Communications Server 2005 with SP1</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="75952-396">Msrtcsip-userenabled true-LocalNormalizationData (廃止)</span><span class="sxs-lookup"><span data-stu-id="75952-396">msRTCSIP-LocalNormalizationData (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="75952-397">この属性は将来使用するために予約されています。</span><span class="sxs-lookup"><span data-stu-id="75952-397">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="75952-398">Office Communications Server 2007 の新製品。</span><span class="sxs-lookup"><span data-stu-id="75952-398">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="75952-399">Lync Server 2010 では廃止されています。</span><span class="sxs-lookup"><span data-stu-id="75952-399">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="75952-400">Msrtcsip-userenabled true-Localnormallinks (廃止)</span><span class="sxs-lookup"><span data-stu-id="75952-400">msRTCSIP-LocalNormalizationLinks (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="75952-401">この複数値属性には、この場所プロファイルに関連付けられたローカル正規化識別名 (DN) の一覧が含まれています。</span><span class="sxs-lookup"><span data-stu-id="75952-401">This multi-valued attribute contains a list of local normalization distinguished names (DN) associated with this location profile.</span></span> <span data-ttu-id="75952-402">この属性の型は、DN バイナリです。</span><span class="sxs-lookup"><span data-stu-id="75952-402">The type of this attribute is a DN binary.</span></span> <span data-ttu-id="75952-403">位置情報プロファイルとローカル正規化ルールの間には一対多のリレーションシップがあります。</span><span class="sxs-lookup"><span data-stu-id="75952-403">There is a one-to-many relationship between location profile and local normalization rules.</span></span> <span data-ttu-id="75952-404">ローカル正規化 DNs の一覧の順序は、管理者が指定した順序で維持する必要があります。</span><span class="sxs-lookup"><span data-stu-id="75952-404">The ordering of the list of local normalization DNs must be maintained in the order specified by the administrator.</span></span> <span data-ttu-id="75952-405">順序の保持は、DN バイナリのバイナリ部分によって管理されます。これにより、注文インデックスが指定されます。</span><span class="sxs-lookup"><span data-stu-id="75952-405">The preservation of order is maintained by the binary portion of the DN binary, which specifies the order index.</span></span></p>
<p><span data-ttu-id="75952-406">転送リンク:<strong>リンク ID 11034</strong></span><span class="sxs-lookup"><span data-stu-id="75952-406">Forward link: <strong>Link ID 11034</strong></span></span></p>
<p><span data-ttu-id="75952-407">この転送リンク属性への対応する "戻る" リンクは、 <strong>msrtcsip-userenabled true (プロファイル Ebl)</strong>です。</span><span class="sxs-lookup"><span data-stu-id="75952-407">The corresponding back link to this forward link attribute is <strong>msRTCSIP-LocationProfileBL</strong>.</span></span></p></td>
<td><p><span data-ttu-id="75952-408">Office Communications Server 2007 の新製品。</span><span class="sxs-lookup"><span data-stu-id="75952-408">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="75952-409">Lync Server 2010 では廃止されています。</span><span class="sxs-lookup"><span data-stu-id="75952-409">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="75952-410">Msrtcsip-userenabled true-LocalNormalizationOptions</span><span class="sxs-lookup"><span data-stu-id="75952-410">msRTCSIP-LocalNormalizationOptions</span></span></p></td>
<td><p><span data-ttu-id="75952-411">この属性には、正規化ルールのオプションの一覧が含まれています。</span><span class="sxs-lookup"><span data-stu-id="75952-411">This attribute contains a list of options for the normalization rule.</span></span></p></td>
<td><p><span data-ttu-id="75952-412">Office Communications Server 2007 R2 の新製品。</span><span class="sxs-lookup"><span data-stu-id="75952-412">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="75952-413">Msrtcsip-userenabled true-LocationName (廃止)</span><span class="sxs-lookup"><span data-stu-id="75952-413">msRTCSIP-LocationName (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="75952-414">この単一値の属性には、このプロファイルが表す場所を示す場所プロファイルのフレンドリ名が含まれています。</span><span class="sxs-lookup"><span data-stu-id="75952-414">This single-valued attribute contains a friendly name for the location profile that indicates which location this profile represents.</span></span> <span data-ttu-id="75952-415">複数の場所プロファイルが存在する可能性があるため、管理者はさまざまなプロファイルを区別するための方法が必要です。</span><span class="sxs-lookup"><span data-stu-id="75952-415">Because there can be multiple location profiles, the administrator needs a way to distinguish between different profiles.</span></span></p></td>
<td><p><span data-ttu-id="75952-416">Office Communications Server 2007 の新製品。</span><span class="sxs-lookup"><span data-stu-id="75952-416">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="75952-417">Lync Server 2010 では廃止されています。</span><span class="sxs-lookup"><span data-stu-id="75952-417">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="75952-418">Msrtcsip-userenabled true-locationProfileBL (廃止)</span><span class="sxs-lookup"><span data-stu-id="75952-418">msRTCSIP-locationProfileBL (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="75952-419">この複数値属性には、場所プロファイルの識別名の一覧が含まれています。</span><span class="sxs-lookup"><span data-stu-id="75952-419">This multi-valued attribute contains a list of location profile distinguished names.</span></span> <span data-ttu-id="75952-420">この属性は、1つ以上の位置情報プロファイルへの戻るリンクを指定します。</span><span class="sxs-lookup"><span data-stu-id="75952-420">This attribute specifies the back link to one or more location profiles.</span></span></p>
<p><span data-ttu-id="75952-421">戻るリンク:<strong>リンク ID 11035</strong></span><span class="sxs-lookup"><span data-stu-id="75952-421">Back link: <strong>Link ID 11035</strong></span></span></p>
<p><span data-ttu-id="75952-422">この属性は、forward link <strong>msrtcsip-userenabled true-Localnormalのリンク</strong>に対応します。</span><span class="sxs-lookup"><span data-stu-id="75952-422">This attribute corresponds to the forward link <strong>msRTCSIP-LocalNormalizationLinks</strong>.</span></span></p></td>
<td><p><span data-ttu-id="75952-423">Office Communications Server 2007 の新製品。</span><span class="sxs-lookup"><span data-stu-id="75952-423">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="75952-424">Lync Server 2010 では廃止されています。</span><span class="sxs-lookup"><span data-stu-id="75952-424">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="75952-425">Msrtcsip-userenabled true-LocationProfileData (廃止)</span><span class="sxs-lookup"><span data-stu-id="75952-425">msRTCSIP-LocationProfileData (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="75952-426">この属性は将来使用するために予約されています。</span><span class="sxs-lookup"><span data-stu-id="75952-426">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="75952-427">Office Communications Server 2007 の新製品。</span><span class="sxs-lookup"><span data-stu-id="75952-427">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="75952-428">Lync Server 2010 では廃止されています。</span><span class="sxs-lookup"><span data-stu-id="75952-428">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="75952-429">Msrtcsip-userenabled true-LocationProfileOptions</span><span class="sxs-lookup"><span data-stu-id="75952-429">msRTCSIP-LocationProfileOptions</span></span></p></td>
<td><p><span data-ttu-id="75952-430">この属性には、位置情報プロファイルのオプションが含まれています。</span><span class="sxs-lookup"><span data-stu-id="75952-430">This attribute contains the options for the location profile.</span></span></p></td>
<td><p><span data-ttu-id="75952-431">Office Communications Server 2007 R2 の新製品。</span><span class="sxs-lookup"><span data-stu-id="75952-431">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="75952-432">Msrtcsip-userenabled true-MappingContact</span><span class="sxs-lookup"><span data-stu-id="75952-432">msRTCSIP-MappingContact</span></span></p></td>
<td><p><span data-ttu-id="75952-433">この複数値属性は、アプリケーションの連絡先の一覧を保持します。</span><span class="sxs-lookup"><span data-stu-id="75952-433">This multiple-value attribute holds a list of application contacts.</span></span></p></td>
<td><p><span data-ttu-id="75952-434">Office Communications Server 2007 R2 の新製品。</span><span class="sxs-lookup"><span data-stu-id="75952-434">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="75952-435">Msrtcsip-userenabled true-MappingLocation</span><span class="sxs-lookup"><span data-stu-id="75952-435">msRTCSIP-MappingLocation</span></span></p></td>
<td><p><span data-ttu-id="75952-436">この複数値属性は、位置情報プロファイルの一覧を保持します。</span><span class="sxs-lookup"><span data-stu-id="75952-436">This multiple-value attribute holds a list of location profiles.</span></span></p></td>
<td><p><span data-ttu-id="75952-437">Office Communications Server 2007 R2 の新製品。</span><span class="sxs-lookup"><span data-stu-id="75952-437">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="75952-438">Msrtcsip-userenabled true-Maxnumoutスタンド Ingsearchperserver (廃止)</span><span class="sxs-lookup"><span data-stu-id="75952-438">msRTCSIP-MaxNumOutstandingSearchPerServer (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="75952-439">この属性は、サーバーあたりの未処理の検索要求の最大数を表します。</span><span class="sxs-lookup"><span data-stu-id="75952-439">This attribute represents the maximum number of outstanding search requests per server.</span></span></p></td>
<td><p><span data-ttu-id="75952-440">Lync Server 2010 では廃止されています。</span><span class="sxs-lookup"><span data-stu-id="75952-440">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="75952-441">Msrtcsip-userenabled true-MaxNumSubscriptionsPerUser (廃止)</span><span class="sxs-lookup"><span data-stu-id="75952-441">msRTCSIP-MaxNumSubscriptionsPerUser (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="75952-442">この属性は、ユーザーごとのサブスクリプションの最大数を表します。</span><span class="sxs-lookup"><span data-stu-id="75952-442">The attribute represents the maximum number of subscriptions per user.</span></span></p></td>
<td><p><span data-ttu-id="75952-443">Lync Server 2010 では廃止されています。</span><span class="sxs-lookup"><span data-stu-id="75952-443">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="75952-444">Msrtcsip-userenabled true-MaxPresenceSubscriptionTimeout (廃止)</span><span class="sxs-lookup"><span data-stu-id="75952-444">msRTCSIP-MaxPresenceSubscriptionTimeout (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="75952-445">この属性は、サブスクリプションの最大タイムアウトウィンドウを表します。</span><span class="sxs-lookup"><span data-stu-id="75952-445">This attribute represents the maximum subscription time-out window.</span></span></p></td>
<td><p><span data-ttu-id="75952-446">Lync Server 2010 では廃止されています。</span><span class="sxs-lookup"><span data-stu-id="75952-446">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="75952-447">Msrtcsip-userenabled true-MaxRegistrationsTimeout (廃止)</span><span class="sxs-lookup"><span data-stu-id="75952-447">msRTCSIP-MaxRegistrationsTimeout (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="75952-448">この属性は、登録の最大タイムアウトウィンドウを表します。</span><span class="sxs-lookup"><span data-stu-id="75952-448">This attribute represents the maximum registrations time-out window.</span></span></p></td>
<td><p><span data-ttu-id="75952-449">Lync Server 2010 では廃止されています。</span><span class="sxs-lookup"><span data-stu-id="75952-449">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="75952-450">Msrtcsip-userenabled true-MaxRoamingDataSubscriptionTimeout (廃止)</span><span class="sxs-lookup"><span data-stu-id="75952-450">msRTCSIP-MaxRoamingDataSubscriptionTimeout (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="75952-451">この属性は、最大ローミングデータサブスクリプションのタイムアウトウィンドウを表します。</span><span class="sxs-lookup"><span data-stu-id="75952-451">This attribute represents the maximum roaming data subscriptions time-out window.</span></span></p></td>
<td><p><span data-ttu-id="75952-452">Lync Server 2010 では廃止されています。</span><span class="sxs-lookup"><span data-stu-id="75952-452">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="75952-453">Msrtcsip-userenabled true-MCUData</span><span class="sxs-lookup"><span data-stu-id="75952-453">msRTCSIP-MCUData</span></span></p></td>
<td><p><span data-ttu-id="75952-454">この属性は将来使用するために予約されています。</span><span class="sxs-lookup"><span data-stu-id="75952-454">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="75952-455">Office Communications Server 2007 の新製品。</span><span class="sxs-lookup"><span data-stu-id="75952-455">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="75952-456">Msrtcsip-userenabled true-MCUFactoryAddress</span><span class="sxs-lookup"><span data-stu-id="75952-456">msRTCSIP-MCUFactoryAddress</span></span></p></td>
<td><p><span data-ttu-id="75952-457">この属性は、属している multipoint control unit (MCU) ファクトリへのリンクを指定するコンピュータークラスの下のサービス制御ポイント属性です。</span><span class="sxs-lookup"><span data-stu-id="75952-457">This attribute is a service control point attribute under the computer class that specifies a link back to the multipoint control unit (MCU) Factory to which it belongs.</span></span> <span data-ttu-id="75952-458">このサービス制御ポイントと属性は、Microsoft MCU ごとに作成されます。</span><span class="sxs-lookup"><span data-stu-id="75952-458">This service control point and attribute is created for every Microsoft MCU.</span></span> <span data-ttu-id="75952-459">各 Microsoft MCU は、プールレベルの設定を取得するために、所属するプールのバックエンドサーバーを見つける必要があります。</span><span class="sxs-lookup"><span data-stu-id="75952-459">Each Microsoft MCU must find the Back End Server of the pool to which it belongs, in order to retrieve pool-level settings from it.</span></span></p>
<p><span data-ttu-id="75952-460">この属性の値は、MCU ファクトリの識別名 (DN) です。</span><span class="sxs-lookup"><span data-stu-id="75952-460">The value of this attribute is the distinguished name (DN) of the MCU Factory.</span></span> <span data-ttu-id="75952-461">これは単一値の属性であり、グローバルカタログのレプリケーション用にマークされています。</span><span class="sxs-lookup"><span data-stu-id="75952-461">This is a single-valued attribute and marked for global catalog replication.</span></span></p>
<p><span data-ttu-id="75952-462">転送リンク:<strong>リンク ID 11026</strong></span><span class="sxs-lookup"><span data-stu-id="75952-462">Forward link: <strong>Link ID 11026</strong></span></span></p>
<p><span data-ttu-id="75952-463">この転送リンク属性への対応する "戻る" リンクは、 <strong>Msrtcsip-userenabled true MCUServers</strong>です。</span><span class="sxs-lookup"><span data-stu-id="75952-463">The corresponding back link to this forward link attribute is <strong>msRTCSIP-MCUServers</strong>.</span></span></p></td>
<td><p><span data-ttu-id="75952-464">Office Communications Server 2007 の新製品。</span><span class="sxs-lookup"><span data-stu-id="75952-464">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="75952-465">Msrtcsip-userenabled true-MCUFactoryData</span><span class="sxs-lookup"><span data-stu-id="75952-465">msRTCSIP-MCUFactoryData</span></span></p></td>
<td><p><span data-ttu-id="75952-466">これは、複数の文字列で予約された属性です。</span><span class="sxs-lookup"><span data-stu-id="75952-466">This is a multi-string reserved attribute.</span></span> <span data-ttu-id="75952-467">この属性に格納される設定は、name = value のペアとして表されます。</span><span class="sxs-lookup"><span data-stu-id="75952-467">Settings stored in this attribute are represented as name=value pairs.</span></span> <span data-ttu-id="75952-468">現在定義されている name = value のペア:</span><span class="sxs-lookup"><span data-stu-id="75952-468">Currently defined name=value pairs are:</span></span></p>
<ul>
<li><p><span data-ttu-id="75952-469">FactoryURL = &lt;URL&gt;</span><span class="sxs-lookup"><span data-stu-id="75952-469">FactoryURL = &lt;URL&gt;</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="75952-470">Office Communications Server 2007 の新製品。</span><span class="sxs-lookup"><span data-stu-id="75952-470">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="75952-471">Msrtcsip-userenabled true-MCUFactoryPath</span><span class="sxs-lookup"><span data-stu-id="75952-471">msRTCSIP-MCUFactoryPath</span></span></p></td>
<td><p><span data-ttu-id="75952-472">これは、プールに関連付けられた単一の MCU ファクトリの識別名 (DN) を含む単一値の属性です。</span><span class="sxs-lookup"><span data-stu-id="75952-472">This is a single-valued attribute that contains the distinguished name (DN) of a single MCU factory associated with a pool.</span></span></p>
<p><span data-ttu-id="75952-473">転送リンク:<strong>リンク ID 11024</strong></span><span class="sxs-lookup"><span data-stu-id="75952-473">Forward link: <strong>Link ID 11024</strong></span></span></p>
<p><span data-ttu-id="75952-474">この転送リンク属性への対応する "戻る" リンクは<strong>msrtcsip-userenabled true の住所</strong>です。</span><span class="sxs-lookup"><span data-stu-id="75952-474">The corresponding back link to this forward link attribute is <strong>msRTCSIP-PoolAddresses</strong>.</span></span></p></td>
<td><p><span data-ttu-id="75952-475">Office Communications Server 2007 の新製品。</span><span class="sxs-lookup"><span data-stu-id="75952-475">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="75952-476">Msrtcsip-userenabled true-MCUFactoryProviderID</span><span class="sxs-lookup"><span data-stu-id="75952-476">msRTCSIP-MCUFactoryProviderID</span></span></p></td>
<td><p><span data-ttu-id="75952-477">この属性は、MCU ファクトリプロバイダーの GUID を指定する単一値の文字列です。</span><span class="sxs-lookup"><span data-stu-id="75952-477">This attribute is a single-valued string that specifies the GUID of the MCU factory provider.</span></span> <span data-ttu-id="75952-478">MCU ファクトリプロセスは、GUID 値に基づいて、この MCU 型をサービスするかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="75952-478">Based on the GUID value, the MCU factory process determines whether to service this MCU type.</span></span> <span data-ttu-id="75952-479">GUID 値が<strong>{F0810510-424F-46ef-84FE-6CC720DF1791}</strong>の場合は、MCU ファクトリプロセス (既定では Lync Server で利用可能) によって処理されます。</span><span class="sxs-lookup"><span data-stu-id="75952-479">If the GUID value is <strong>{F0810510-424F-46ef-84FE-6CC720DF1791}</strong>, then the MCU factory process (available by default in Lync Server) will process it.</span></span> <span data-ttu-id="75952-480">他の GUID 値の場合、MCU ファクトリプロセスは MCU の種類を処理しません。</span><span class="sxs-lookup"><span data-stu-id="75952-480">For any other GUID value, the MCU factory process will not service the MCU type.</span></span></p></td>
<td><p><span data-ttu-id="75952-481">Office Communications Server 2007 の新製品。</span><span class="sxs-lookup"><span data-stu-id="75952-481">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="75952-482">msrtcsip-userenabled true-mcuser</span><span class="sxs-lookup"><span data-stu-id="75952-482">msRTCSIP-MCUServers</span></span></p></td>
<td><p><span data-ttu-id="75952-483">この属性は、複数値を持つ識別名 (DN) の一覧です。</span><span class="sxs-lookup"><span data-stu-id="75952-483">This attribute is a multi-valued list of distinguished names (DN).</span></span> <span data-ttu-id="75952-484">この属性には、この MCU ファクトリに関連付けられている同じ種類とベンダーのすべての MCU サーバーの一覧が含まれます。</span><span class="sxs-lookup"><span data-stu-id="75952-484">This attribute contains a list of all MCU servers of the same type and vendor associated with this MCU factory.</span></span> <span data-ttu-id="75952-485">各セグメントの有効な値は、63文字です。FQDN 全体の有効な値は、255文字です。</span><span class="sxs-lookup"><span data-stu-id="75952-485">The valid value for each segment is 63 characters; the valid value for the entire FQDN is 255 characters.</span></span></p>
<p><span data-ttu-id="75952-486">戻るリンク: リンク ID 11027</span><span class="sxs-lookup"><span data-stu-id="75952-486">Back link: Link ID 11027</span></span></p>
<p><span data-ttu-id="75952-487">この戻るリンクへの対応する前方リンクは<strong>Msrtcsip-userenabled true MCUFactoryAddress</strong>です。</span><span class="sxs-lookup"><span data-stu-id="75952-487">The corresponding forward link to this back link is <strong>msRTCSIP-MCUFactoryAddress</strong>.</span></span></p></td>
<td><p><span data-ttu-id="75952-488">Office Communications Server 2007 の新製品。</span><span class="sxs-lookup"><span data-stu-id="75952-488">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="75952-489">Msrtcsip-userenabled true-MCUType</span><span class="sxs-lookup"><span data-stu-id="75952-489">msRTCSIP-MCUType</span></span></p></td>
<td><p><span data-ttu-id="75952-490">この属性は、MCU が処理できる媒体を指定する単一値の文字列です。</span><span class="sxs-lookup"><span data-stu-id="75952-490">This attribute is a single-valued string that specifies the medium the MCU can handle.</span></span></p>
<p><span data-ttu-id="75952-491">サポートされている有効な形式は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="75952-491">Supported valid types are:</span></span></p>
<ul>
<li><p><span data-ttu-id="75952-492">会議</span><span class="sxs-lookup"><span data-stu-id="75952-492">meeting</span></span></p></li>
<li><p><span data-ttu-id="75952-493">オーディオ-ビデオ</span><span class="sxs-lookup"><span data-stu-id="75952-493">audio-video</span></span></p></li>
<li><p><span data-ttu-id="75952-494">チャット</span><span class="sxs-lookup"><span data-stu-id="75952-494">chat</span></span></p></li>
<li><p><span data-ttu-id="75952-495">電話-conf</span><span class="sxs-lookup"><span data-stu-id="75952-495">phone-conf</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="75952-496">Office Communications Server 2007 の新製品。</span><span class="sxs-lookup"><span data-stu-id="75952-496">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="75952-497">Msrtcsip-userenabled true-MCUVendor</span><span class="sxs-lookup"><span data-stu-id="75952-497">msRTCSIP-MCUVendor</span></span></p></td>
<td><p><span data-ttu-id="75952-498">この属性は、MCU ベンダーの名前を指定する単一値の文字列です。</span><span class="sxs-lookup"><span data-stu-id="75952-498">This attribute is a single-valued string that specifies an MCU vendor’s name.</span></span> <span data-ttu-id="75952-499">Microsoft のすべての Mcu は、この属性を<strong>Microsoft Corporation</strong>に指定します。</span><span class="sxs-lookup"><span data-stu-id="75952-499">All Microsoft MCUs will specify this attribute to be <strong>Microsoft Corporation</strong>.</span></span></p></td>
<td><p><span data-ttu-id="75952-500">Office Communications Server 2007 の新製品。</span><span class="sxs-lookup"><span data-stu-id="75952-500">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="75952-501">Msrtcsip-userenabled true-会議フラグ (廃止)</span><span class="sxs-lookup"><span data-stu-id="75952-501">msRTCSIP-MeetingFlags (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="75952-502">この属性は、すべてのユーザーまたは連絡先オブジェクトでグローバルに有効になるさまざまな会議オプションを定義します。</span><span class="sxs-lookup"><span data-stu-id="75952-502">This attribute defines different meeting options that are enabled globally for all users or contact objects.</span></span> <span data-ttu-id="75952-503">この属性は、整数型のビットマスク値です。</span><span class="sxs-lookup"><span data-stu-id="75952-503">This attribute is a bit-mask value of integer type.</span></span></p>
<p><span data-ttu-id="75952-504">有効な値 (および関連するビット位置) は、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="75952-504">The valid values (and associated bit positions) are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="75952-505">0: AllowOrganizeMeetingWithAnonymousParticipants が None (ユーザーが会議に匿名ユーザーを招待することを許可しない) (bits は設定されません)</span><span class="sxs-lookup"><span data-stu-id="75952-505">0: AllowOrganizeMeetingWithAnonymousParticipants is None (do not allow users to invite anonymous users to meetings) (no bits set)</span></span></p></li>
<li><p><span data-ttu-id="75952-506">4: AllowOrganizeMeetingWithAnonymousParticipants はすべてのユーザー (すべてのユーザーが会議に匿名ユーザーを招待することを許可します) (ビット位置 2)</span><span class="sxs-lookup"><span data-stu-id="75952-506">4: AllowOrganizeMeetingWithAnonymousParticipants is Everyone (allow all users to invite anonymous users to meetings) (bit position 2)</span></span></p></li>
<li><p><span data-ttu-id="75952-507">8: AllowOrganizeMeetingWithAnonymousParticipants は UsePerUserSetting (ユーザーごとの設定に基づいてユーザーが会議に匿名ユーザーを招待できるようにします) (ビット位置 3)</span><span class="sxs-lookup"><span data-stu-id="75952-507">8: AllowOrganizeMeetingWithAnonymousParticipants is UsePerUserSetting (allow users to invite anonymous users to meetings based on per user setting) (bit position 3)</span></span></p></li>
<li><p><span data-ttu-id="75952-508">16: Userperuser会議ポリシー (会議ポリシーはユーザーごとに定義されます) (ビット位置 4)</span><span class="sxs-lookup"><span data-stu-id="75952-508">16: UserPerUserMeetingPolicy (meeting policy is defined per user) (bit position 4)</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="75952-509">Office Communications Server 2007 の新製品。</span><span class="sxs-lookup"><span data-stu-id="75952-509">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="75952-510">Lync Server 2010 では廃止されています。</span><span class="sxs-lookup"><span data-stu-id="75952-510">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="75952-511">Msrtcsip-userenabled true-会議ポリシー (廃止)</span><span class="sxs-lookup"><span data-stu-id="75952-511">msRTCSIP-MeetingPolicy (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="75952-512">この属性は、管理者がこのユーザーに割り当てたポリシーの識別名 (DN) を単一値の属性として指定します。</span><span class="sxs-lookup"><span data-stu-id="75952-512">This attribute specifies the distinguished name (DN) of the policy the administrator has assigned for this user as a single-valued attribute.</span></span></p></td>
<td><p><span data-ttu-id="75952-513">Office Communications Server 2007 の新製品。</span><span class="sxs-lookup"><span data-stu-id="75952-513">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="75952-514">Lync Server 2010 では廃止されています。</span><span class="sxs-lookup"><span data-stu-id="75952-514">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="75952-515">Msrtcsip-userenabled true-MinPresenceSubscriptionTimeout (廃止)</span><span class="sxs-lookup"><span data-stu-id="75952-515">msRTCSIP-MinPresenceSubscriptionTimeout (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="75952-516">この属性は、最小プレゼンスサブスクリプションのタイムアウトウィンドウを表します。</span><span class="sxs-lookup"><span data-stu-id="75952-516">This attribute represents the minimum presence subscription time-out window.</span></span></p></td>
<td><p><span data-ttu-id="75952-517">Lync Server 2010 では廃止されています。</span><span class="sxs-lookup"><span data-stu-id="75952-517">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="75952-518">Msrtcsip-userenabled true-MinRegistrationTimeout (廃止)</span><span class="sxs-lookup"><span data-stu-id="75952-518">msRTCSIP-MinRegistrationTimeout (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="75952-519">この属性は、最小登録タイムアウトウィンドウを表します。</span><span class="sxs-lookup"><span data-stu-id="75952-519">This attribute represents the minimum registration time-out window.</span></span></p></td>
<td><p><span data-ttu-id="75952-520">Office Communications Server 2007 の新製品。</span><span class="sxs-lookup"><span data-stu-id="75952-520">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="75952-521">Lync Server 2010 では廃止されています。</span><span class="sxs-lookup"><span data-stu-id="75952-521">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="75952-522">Msrtcsip-userenabled true-MinRoamingDataSubscriptionTimeout (廃止)</span><span class="sxs-lookup"><span data-stu-id="75952-522">msRTCSIP-MinRoamingDataSubscriptionTimeout (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="75952-523">この属性は、最小のローミングデータサブスクリプションのタイムアウトウィンドウを表します。</span><span class="sxs-lookup"><span data-stu-id="75952-523">This attribute represents the minimum roaming data subscription time-out window.</span></span></p></td>
<td><p><span data-ttu-id="75952-524">Office Communications Server 2007 の新製品。</span><span class="sxs-lookup"><span data-stu-id="75952-524">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="75952-525">Lync Server 2010 では廃止されています。</span><span class="sxs-lookup"><span data-stu-id="75952-525">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="75952-526">Msrtcsip-userenabled true-MirrorBackEndServer</span><span class="sxs-lookup"><span data-stu-id="75952-526">msRTCSIP-MirrorBackEndServer</span></span></p></td>
<td><p><span data-ttu-id="75952-527">この属性は、フロントエンドプールによって使用されるミラー化された SQL Server バックエンドを格納するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="75952-527">This attribute is used to store the mirrored SQL Server backend used by the Front End pool.</span></span></p></td>
<td><p><span data-ttu-id="75952-528">Lync Server 2013 の新サービスです。</span><span class="sxs-lookup"><span data-stu-id="75952-528">New in Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="75952-529">Msrtcsip-userenabled true-MobilityFlags</span><span class="sxs-lookup"><span data-stu-id="75952-529">msRTCSIP-MobilityFlags</span></span></p></td>
<td><p><span data-ttu-id="75952-530">この属性には、モビリティー設定を定義するオプションとフラグが含まれています。</span><span class="sxs-lookup"><span data-stu-id="75952-530">This attribute contains options and flags that define mobility settings.</span></span></p></td>
<td><p><span data-ttu-id="75952-531">Office Communications Server 2007 R2 の新製品。</span><span class="sxs-lookup"><span data-stu-id="75952-531">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="75952-532">Msrtcsip-userenabled true-MobilityPolicy</span><span class="sxs-lookup"><span data-stu-id="75952-532">msRTCSIP-MobilityPolicy</span></span></p></td>
<td><p><span data-ttu-id="75952-533">この属性には、モビリティーポリシーオブジェクトの DN が含まれます。</span><span class="sxs-lookup"><span data-stu-id="75952-533">This attribute contains the DN for a mobility policy object.</span></span></p></td>
<td><p><span data-ttu-id="75952-534">Office Communications Server 2007 R2 の新製品。</span><span class="sxs-lookup"><span data-stu-id="75952-534">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="75952-535">Msrtcsip-userenabled true-NumDevicesPerUser (廃止)</span><span class="sxs-lookup"><span data-stu-id="75952-535">msRTCSIP-NumDevicesPerUser (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="75952-536">この属性は、ユーザーが SIP コミュニケーションに登録してプレゼンスをサブスクライブできるデバイスの許可された数を表します。</span><span class="sxs-lookup"><span data-stu-id="75952-536">This attribute represents the allowed number of devices on which a user can register for SIP communications and subscribe to presence.</span></span></p></td>
<td><p><span data-ttu-id="75952-537">Office Communications Server 2007 の新製品。</span><span class="sxs-lookup"><span data-stu-id="75952-537">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="75952-538">Lync Server 2010 では廃止されています。</span><span class="sxs-lookup"><span data-stu-id="75952-538">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="75952-539">Msrtcsip-userenabled true-OptionFlags</span><span class="sxs-lookup"><span data-stu-id="75952-539">msRTCSIP-OptionFlags</span></span></p></td>
<td><p><span data-ttu-id="75952-540">この属性は、ユーザーまたは連絡先オブジェクトに対して有効になるオプションを指定します。</span><span class="sxs-lookup"><span data-stu-id="75952-540">This attribute specifies the options that are enabled for the user or contact object.</span></span> <span data-ttu-id="75952-541">この属性は、integer 型のビットマスク値です。</span><span class="sxs-lookup"><span data-stu-id="75952-541">This attribute is a bit-mask value of type integer.</span></span> <span data-ttu-id="75952-542">各オプションは1ビットで表されます。</span><span class="sxs-lookup"><span data-stu-id="75952-542">Each option is represented by a bit.</span></span> <span data-ttu-id="75952-543">この属性は、グローバルカタログのレプリケーション用にマークされます。</span><span class="sxs-lookup"><span data-stu-id="75952-543">This attribute is marked for global catalog replication.</span></span></p>
<p><span data-ttu-id="75952-544">有効な値 (および関連するビット位置) は、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="75952-544">The valid values (and associated bit positions) are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="75952-545">1: パブリックインスタントメッセージング (IM) 接続を有効にします (ビット位置 0)。</span><span class="sxs-lookup"><span data-stu-id="75952-545">1: Enabled for public instant messaging (IM) connectivity (bit position 0)</span></span></p></li>
<li><p><span data-ttu-id="75952-546">2: 予約済み (ビット位置 1)</span><span class="sxs-lookup"><span data-stu-id="75952-546">2: Reserved (bit position 1)</span></span></p></li>
<li><p><span data-ttu-id="75952-547">4: 予約済み (ビット位置 2)</span><span class="sxs-lookup"><span data-stu-id="75952-547">4: Reserved (bit position 2)</span></span></p></li>
<li><p><span data-ttu-id="75952-548">8: 予約済み (ビット位置 3)</span><span class="sxs-lookup"><span data-stu-id="75952-548">8: Reserved (bit position 3)</span></span></p></li>
<li><p><span data-ttu-id="75952-549">16: リモート通話コントロールが有効になっている [Telephony] (ビット位置 4)</span><span class="sxs-lookup"><span data-stu-id="75952-549">16: Remote call control Enabled [Telephony] (bit position 4)</span></span></p></li>
<li><p><span data-ttu-id="75952-550">64: AllowOrganizeMeetingWithAnonymousParticipants (ユーザーが会議に匿名ユーザーを招待することを許可する (ビット位置 6)</span><span class="sxs-lookup"><span data-stu-id="75952-550">64: AllowOrganizeMeetingWithAnonymousParticipants (allow users to invite anonymous users to meetings (bit position 6)</span></span></p></li>
<li><p><span data-ttu-id="75952-551">128: UCEnabled (UC でのユーザーの有効化) (ビット位置 7)</span><span class="sxs-lookup"><span data-stu-id="75952-551">128: UCEnabled (enable users for UC) (bit position 7)</span></span></p></li>
<li><p><span data-ttu-id="75952-552">256: EnabledForEnhancedPresence (ユーザーにパブリック IM 接続を有効にする) (ビット位置 8)</span><span class="sxs-lookup"><span data-stu-id="75952-552">256: EnabledForEnhancedPresence (enable user for public IM connectivity) (bit position 8)</span></span></p></li>
<li><p><span data-ttu-id="75952-553">512: RemoteCallControlDualMode (ビット位置 9)</span><span class="sxs-lookup"><span data-stu-id="75952-553">512: RemoteCallControlDualMode (bit position 9)</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="75952-554">SP1 での最新のライブ通信サーバー2005。</span><span class="sxs-lookup"><span data-stu-id="75952-554">New in Live Communications Server 2005 with SP1.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="75952-555">msRTCSIP-OriginatorSID</span><span class="sxs-lookup"><span data-stu-id="75952-555">msRTCSIP-OriginatorSID</span></span></p></td>
<td><p><span data-ttu-id="75952-556">この属性は、リソースおよび中央フォレストトポロジで使用され、Windows NT Server プリンシパルアカウントからのユーザーの ObjectSID が、リソースまたは中央フォレストの対応するユーザーまたは連絡先オブジェクトのこの属性にコピーされた場合に、シングルサインオンを有効にします。</span><span class="sxs-lookup"><span data-stu-id="75952-556">This attribute is used in resource and central forest topologies to enable single sign-on when a user’s ObjectSID from the Windows NT Server principal account is copied into this attribute of the corresponding user or contact object in the resource or central forest.</span></span> <span data-ttu-id="75952-557">Communicator Web Access は、この属性またはユーザーの ObjectSID を使用して、AD DS 内のユーザーを検索します。</span><span class="sxs-lookup"><span data-stu-id="75952-557">Communicator Web Access searches for a user in AD DS using this attribute or the user’s ObjectSID.</span></span> <span data-ttu-id="75952-558">この属性は、グローバルカタログのレプリケーション用にマークされます。</span><span class="sxs-lookup"><span data-stu-id="75952-558">This attribute is marked for global catalog replication.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="75952-559">Msrtcsip-userenabled true-OwnerUrn</span><span class="sxs-lookup"><span data-stu-id="75952-559">msRTCSIP-OwnerUrn</span></span></p></td>
<td><p><span data-ttu-id="75952-560">この属性は、アプリケーションの連絡先の所有者の Uniform Resource Name (URN) です。</span><span class="sxs-lookup"><span data-stu-id="75952-560">This attribute is the Uniform Resource Name (URN) of the owner for an application contact.</span></span></p></td>
<td><p><span data-ttu-id="75952-561">Lync Server 2010 の新サービスです。</span><span class="sxs-lookup"><span data-stu-id="75952-561">New in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="75952-562">Msrtcsip-userenabled true-Pattern (廃止)</span><span class="sxs-lookup"><span data-stu-id="75952-562">msRTCSIP-Pattern (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="75952-563">この単一値文字列属性には、ダイヤル番号を E.i 形式に一致させるために使われるパターンが含まれています。</span><span class="sxs-lookup"><span data-stu-id="75952-563">This single-valued string attribute contains a pattern used for matching dial numbers into E.164 format.</span></span> <span data-ttu-id="75952-564">ダイヤル番号がこのパターンと一致する場合、翻訳はダイヤルされた番号に適用されます。</span><span class="sxs-lookup"><span data-stu-id="75952-564">If the dial number matches this pattern, the translation is applied to the dialed number.</span></span></p></td>
<td><p><span data-ttu-id="75952-565">Office Communications Server 2007 の新製品。</span><span class="sxs-lookup"><span data-stu-id="75952-565">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="75952-566">Lync Server 2010 では廃止されています。</span><span class="sxs-lookup"><span data-stu-id="75952-566">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="75952-567">Msrtcsip-userenabled true-PhoneRouteBL (廃止)</span><span class="sxs-lookup"><span data-stu-id="75952-567">msRTCSIP-PhoneRouteBL (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="75952-568">この複数値属性には、電話ルートの識別名 (DN) の一覧が含まれます。</span><span class="sxs-lookup"><span data-stu-id="75952-568">This multi-valued attribute contains a list of phone route distinguished names (DN).</span></span> <span data-ttu-id="75952-569">この属性は、1つ以上の電話ルートへの戻るリンクを指定します。</span><span class="sxs-lookup"><span data-stu-id="75952-569">This attribute specifies the back link to one or more phone routes.</span></span></p>
<p><span data-ttu-id="75952-570">戻るリンク:<strong>リンク ID 11033</strong></span><span class="sxs-lookup"><span data-stu-id="75952-570">Back link: <strong>Link ID 11033</strong></span></span></p>
<p><span data-ttu-id="75952-571">この属性は、 <strong>msrtcsip-userenabled true-RouteUsageLinks</strong>の前方リンクに対応しています。</span><span class="sxs-lookup"><span data-stu-id="75952-571">This attribute corresponds to the forward link <strong>msRTCSIP-RouteUsageLinks</strong>.</span></span></p></td>
<td><p><span data-ttu-id="75952-572">Office Communications Server 2007 の新製品。</span><span class="sxs-lookup"><span data-stu-id="75952-572">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="75952-573">Lync Server 2010 では廃止されています。</span><span class="sxs-lookup"><span data-stu-id="75952-573">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="75952-574">Msrtcsip-userenabled true-PhoneRouteData (廃止)</span><span class="sxs-lookup"><span data-stu-id="75952-574">msRTCSIP-PhoneRouteData (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="75952-575">この属性は将来使用するために予約されています。</span><span class="sxs-lookup"><span data-stu-id="75952-575">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="75952-576">Lync Server 2010 では廃止されています。</span><span class="sxs-lookup"><span data-stu-id="75952-576">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="75952-577">Msrtcsip-userenabled true-PhoneRouteName (廃止)</span><span class="sxs-lookup"><span data-stu-id="75952-577">msRTCSIP-PhoneRouteName (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="75952-578">この単一の値の UNICODE 文字列属性は、電話ルートのフレンドリ名を指定するため、管理者が簡単に参照できます。</span><span class="sxs-lookup"><span data-stu-id="75952-578">This single valued UNICODE string attribute specifies the friendly name of the phone route, so it can easily be referenced by the administrator.</span></span></p></td>
<td><p><span data-ttu-id="75952-579">Lync Server 2010 では廃止されています。</span><span class="sxs-lookup"><span data-stu-id="75952-579">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="75952-580">Msrtcsip-userenabled true-電話の使用データ (廃止)</span><span class="sxs-lookup"><span data-stu-id="75952-580">msRTCSIP-PhoneUsageData (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="75952-581">この属性は将来使用するために予約されています。</span><span class="sxs-lookup"><span data-stu-id="75952-581">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="75952-582">Office Communications Server 2007 の新製品。</span><span class="sxs-lookup"><span data-stu-id="75952-582">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="75952-583">Lync Server 2010 では廃止されています。</span><span class="sxs-lookup"><span data-stu-id="75952-583">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="75952-584">Msrtcsip-userenabled true-ポリシーのコンテンツ (廃止)</span><span class="sxs-lookup"><span data-stu-id="75952-584">msRTCSIP-PolicyContent (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="75952-585">この属性は、単一の値を持つ Unicode 文字列です。</span><span class="sxs-lookup"><span data-stu-id="75952-585">This attribute is a single-valued Unicode string.</span></span> <span data-ttu-id="75952-586">この文字列属性には、XML 形式のポリシー定義が含まれています。</span><span class="sxs-lookup"><span data-stu-id="75952-586">This string attribute contains the policy definition in XML format.</span></span> <span data-ttu-id="75952-587">XML スキーマ定義は、ポリシーの種類によって共通していますが、ポリシーの種類によって設定は異なります。</span><span class="sxs-lookup"><span data-stu-id="75952-587">The XML schema definition is common across different policy types, only the settings are different for each policy type.</span></span></p>
<p><span data-ttu-id="75952-588">XML スキーマ定義 (XSD) は、次のように定義されます。</span><span class="sxs-lookup"><span data-stu-id="75952-588">The XML schema definition (XSD) is defined as follows:</span></span></p>
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
<td><p><span data-ttu-id="75952-589">Office Communications Server 2007 の新製品。</span><span class="sxs-lookup"><span data-stu-id="75952-589">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="75952-590">Lync Server 2010 では廃止されています。</span><span class="sxs-lookup"><span data-stu-id="75952-590">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="75952-591">Msrtcsip-userenabled true-ポリシーデータ (廃止)</span><span class="sxs-lookup"><span data-stu-id="75952-591">msRTCSIP-PolicyData (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="75952-592">この属性は将来使用するために予約されています。</span><span class="sxs-lookup"><span data-stu-id="75952-592">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="75952-593">Office Communications Server 2007 の新製品。</span><span class="sxs-lookup"><span data-stu-id="75952-593">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="75952-594">Lync Server 2010 では廃止されています。</span><span class="sxs-lookup"><span data-stu-id="75952-594">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="75952-595">Msrtcsip-userenabled true-PolicyType (廃止)</span><span class="sxs-lookup"><span data-stu-id="75952-595">msRTCSIP-PolicyType (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="75952-596">この単一値の Unicode 文字列属性には、ポリシー型が含まれています。</span><span class="sxs-lookup"><span data-stu-id="75952-596">This single-valued Unicode string attribute contains the policy type.</span></span> <span data-ttu-id="75952-597">有効なポリシーの種類は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="75952-597">Valid policy types are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="75952-598">会議</span><span class="sxs-lookup"><span data-stu-id="75952-598">meeting</span></span></p></li>
<li><p><span data-ttu-id="75952-599">電話</span><span class="sxs-lookup"><span data-stu-id="75952-599">telephony</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="75952-600">Office Communications Server 2007 の新製品。</span><span class="sxs-lookup"><span data-stu-id="75952-600">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="75952-601">Lync Server 2010 では廃止されています。</span><span class="sxs-lookup"><span data-stu-id="75952-601">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="75952-602">Msrtcsip-userenabled true-PoolAddress</span><span class="sxs-lookup"><span data-stu-id="75952-602">msRTCSIP-PoolAddress</span></span></p></td>
<td><p><span data-ttu-id="75952-603">この属性は、コンピューターが属しているプールへのリンクを指定します。</span><span class="sxs-lookup"><span data-stu-id="75952-603">This attribute specifies a link back to the pool to which a computer belongs.</span></span> <span data-ttu-id="75952-604">この属性は、コンピューターで実行されているのが標準エディションであるか、エンタープライズ版の Lync Server であるかに関係なく設定されます。</span><span class="sxs-lookup"><span data-stu-id="75952-604">This attribute is set regardless of whether the computer is running the Standard Edition or the Enterprise Edition of Lync Server.</span></span> <span data-ttu-id="75952-605">この属性は、グローバルカタログのレプリケーション用にマークされます。</span><span class="sxs-lookup"><span data-stu-id="75952-605">This attribute is marked for global catalog replication.</span></span></p>
<p><span data-ttu-id="75952-606">有効な値は、プールのドメイン名です。</span><span class="sxs-lookup"><span data-stu-id="75952-606">The valid value is the domain name of the pool.</span></span></p>
<p><span data-ttu-id="75952-607">転送リンク:<strong>リンク ID 11022</strong></span><span class="sxs-lookup"><span data-stu-id="75952-607">Forward link: <strong>Link ID 11022</strong></span></span></p>
<p><span data-ttu-id="75952-608">この転送リンク属性への対応する "戻る" リンクは、 <strong>msrtcsip-userenabled true-FrontEndServers</strong>です。</span><span class="sxs-lookup"><span data-stu-id="75952-608">The corresponding back link to this forward link attribute is <strong>msRTCSIP-FrontEndServers</strong>.</span></span></p></td>
<td><p><span data-ttu-id="75952-609">Live Communications Server 2005 の新サービスです。</span><span class="sxs-lookup"><span data-stu-id="75952-609">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="75952-610">Msrtcsip-userenabled true-PoolAddresses</span><span class="sxs-lookup"><span data-stu-id="75952-610">msRTCSIP-PoolAddresses</span></span></p></td>
<td><p><span data-ttu-id="75952-611">これは、MCU ファクトリが関連付けられているプールの識別名 (DN) の一覧を含む複数値の属性です。</span><span class="sxs-lookup"><span data-stu-id="75952-611">This is a multi-valued attribute that contains a list of the distinguished names (DN) of pools with which the MCU factory is associated.</span></span></p>
<p><span data-ttu-id="75952-612">戻るリンク:<strong>リンク ID 11025</strong></span><span class="sxs-lookup"><span data-stu-id="75952-612">Back link: <strong>Link ID 11025</strong></span></span></p>
<p><span data-ttu-id="75952-613">この戻るリンクへの対応する前方リンクは<strong>Msrtcsip-userenabled true MCUFactoryPath</strong>です。</span><span class="sxs-lookup"><span data-stu-id="75952-613">The corresponding forward link to this back link is <strong>msRTCSIP-MCUFactoryPath</strong>.</span></span></p></td>
<td><p><span data-ttu-id="75952-614">Office Communications Server 2007 の新製品。</span><span class="sxs-lookup"><span data-stu-id="75952-614">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="75952-615">Msrtcsip-userenabled true-PoolData</span><span class="sxs-lookup"><span data-stu-id="75952-615">msRTCSIP-PoolData</span></span></p></td>
<td><p><span data-ttu-id="75952-616">この属性は将来使用するために予約されています。</span><span class="sxs-lookup"><span data-stu-id="75952-616">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="75952-617">SP1 での最新のライブ通信サーバー2005。</span><span class="sxs-lookup"><span data-stu-id="75952-617">New in Live Communications Server 2005 with SP1.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="75952-618">Msrtcsip-userenabled true-PoolDisplayName</span><span class="sxs-lookup"><span data-stu-id="75952-618">msRTCSIP-PoolDisplayName</span></span></p></td>
<td><p><span data-ttu-id="75952-619">この属性は、管理コンソールによって表示されるプールの任意の名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="75952-619">This attribute specifies an arbitrary name for a pool that is displayed by the management console.</span></span> <span data-ttu-id="75952-620">この名前は管理者が変更できます。</span><span class="sxs-lookup"><span data-stu-id="75952-620">This name can be changed by the administrator.</span></span></p>
<p><span data-ttu-id="75952-621">有効な値は、プールの名前を表す文字列です。</span><span class="sxs-lookup"><span data-stu-id="75952-621">The valid value is a string representing the name of a pool.</span></span></p></td>
<td><p><span data-ttu-id="75952-622">Live Communications Server 2005 の新サービスです。</span><span class="sxs-lookup"><span data-stu-id="75952-622">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="75952-623">Msrtcsip-userenabled true-Pooldomaqdn</span><span class="sxs-lookup"><span data-stu-id="75952-623">msRTCSIP-PoolDomainFQDN</span></span></p></td>
<td><p><span data-ttu-id="75952-624">この属性は単一値文字列値です。</span><span class="sxs-lookup"><span data-stu-id="75952-624">This attribute is a single-valued string value.</span></span> <span data-ttu-id="75952-625">この属性の値が指定されている場合、管理者がフロントエンドプールを作成する Active Directory ドメイン構造に準拠していない FQDN (たとえば、SIP) を使っている場合、プールのドメイン FQDN が示されます。ドメインネームシステム (DNS) 名前空間からの名前空間の分離。</span><span class="sxs-lookup"><span data-stu-id="75952-625">The value of this attribute, when present, represents the pool’s domain FQDN if the administrator wants to create a Front End pool with an FQDN that does not conform to the Active Directory domain structure in which the Front End pool is created (for example, a SIP namespace disjoined from Domain Name System (DNS) namespace).</span></span></p>
<p><span data-ttu-id="75952-626">プールが存在する Active Directory ドメインとして、フロントエンドプールドメイン FQDN をドメイン名部分にマッピングすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="75952-626">We recommend that you map the Front End pool domain FQDN to the domain name portion as the Active Directory domain in which the pool resides.</span></span> <span data-ttu-id="75952-627">そのため、この属性に値が含まれていない場合、フロントエンドプールの FQDN は、 <strong>dnsHostName</strong>属性で示される Active Directory ドメイン名の構造体に既定値として設定されます。</span><span class="sxs-lookup"><span data-stu-id="75952-627">Therefore, when no value is present in this attribute, the Front End pool FQDN will default to the Active Directory domain name structure, as denoted by the <strong>dnsHostName</strong> attribute.</span></span></p></td>
<td><p><span data-ttu-id="75952-628">Office Communications Server 2007 の新製品。</span><span class="sxs-lookup"><span data-stu-id="75952-628">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="75952-629">Msrtcsip-userenabled true-PoolFunctionality</span><span class="sxs-lookup"><span data-stu-id="75952-629">msRTCSIP-PoolFunctionality</span></span></p></td>
<td><p><span data-ttu-id="75952-630">プールに関連付けられたすべての Lync Server Enterprise Edition サーバーのドメイン名の複数値を持つリスト。</span><span class="sxs-lookup"><span data-stu-id="75952-630">A multi-valued list of the domain names of all Lync Server, Enterprise Edition servers associated with a pool.</span></span> <span data-ttu-id="75952-631">Integer 型の属性は、プールがインスタントメッセージング (IM) とプレゼンス、会議に対応しているかどうかを定義します。</span><span class="sxs-lookup"><span data-stu-id="75952-631">This attribute of type integer defines whether the pool is capable of instant messaging (IM) and presence, and meetings.</span></span></p>
<p><span data-ttu-id="75952-632">有効な値の型は、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="75952-632">The possible valid value types are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="75952-633">未定義: IM とプレゼンスサービス (Live Communications Server 2005 および 2003)</span><span class="sxs-lookup"><span data-stu-id="75952-633">Undefined: IM and Presence Service (Live Communications Server 2005 and 2003)</span></span></p></li>
<li><p><span data-ttu-id="75952-634">1: IM とプレゼンスサービス (Lync Server)</span><span class="sxs-lookup"><span data-stu-id="75952-634">1: IM and Presence Service (Lync Server)</span></span></p></li>
<li><p><span data-ttu-id="75952-635">2: IM、プレゼンス、会議サービス (Lync Server)</span><span class="sxs-lookup"><span data-stu-id="75952-635">2: IM and Presence and Meeting Service (Lync Server)</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="75952-636">Office Communications Server 2007 の新製品。</span><span class="sxs-lookup"><span data-stu-id="75952-636">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="75952-637">Msrtcsip-userenabled true-PoolType</span><span class="sxs-lookup"><span data-stu-id="75952-637">msRTCSIP-PoolType</span></span></p></td>
<td><p><span data-ttu-id="75952-638">この属性は、サーバープールで Standard Edition server または Enterprise Edition server が実行されているかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="75952-638">This attribute specifies whether a server pool is running Standard Edition server or Enterprise Edition server.</span></span> <span data-ttu-id="75952-639">この属性は、integer 型のビットマスク値です。</span><span class="sxs-lookup"><span data-stu-id="75952-639">This attribute is a bit-mask value of type integer.</span></span> <span data-ttu-id="75952-640">各オプションは1ビットで表されます。</span><span class="sxs-lookup"><span data-stu-id="75952-640">Each option is represented by a bit.</span></span></p>
<p><span data-ttu-id="75952-641">有効な値 (および関連するビット位置) は、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="75952-641">The valid values (and associated bit positions) are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="75952-642">1: Standard Edition server、ホストユーザー (ビット位置 0)</span><span class="sxs-lookup"><span data-stu-id="75952-642">1: Standard Edition server, hosts users (bit position 0)</span></span></p></li>
<li><p><span data-ttu-id="75952-643">2: Enterprise Edition server、hosts ユーザー (ビット位置 1)</span><span class="sxs-lookup"><span data-stu-id="75952-643">2: Enterprise Edition server, hosts users (bit position 1)</span></span></p></li>
<li><p><span data-ttu-id="75952-644">4: 標準エディションサーバー、ホストアプリケーション (ビット位置 2)</span><span class="sxs-lookup"><span data-stu-id="75952-644">4: Standard Edition server, hosts applications (bit position 2)</span></span></p></li>
<li><p><span data-ttu-id="75952-645">8: Enterprise Edition server、ホストアプリケーション (ビット位置 3)</span><span class="sxs-lookup"><span data-stu-id="75952-645">8: Enterprise Edition server, hosts applications (bit position 3)</span></span></p></li>
</ul>
<p><span data-ttu-id="75952-646">Lync Server はアプリケーションのみをホストするプールをサポートしていないため、有効な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="75952-646">Because Lync Server does not support pools that host only applications, the only valid values are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="75952-647">5: 標準エディションサーバー、ホストユーザーとアプリケーション (ビット位置0、2)</span><span class="sxs-lookup"><span data-stu-id="75952-647">5: Standard Edition server, hosts users and applications (bit positions 0 and 2)</span></span></p></li>
<li><p><span data-ttu-id="75952-648">10: Enterprise Edition server、ホストユーザーとアプリケーション (ビット位置1と 3)</span><span class="sxs-lookup"><span data-stu-id="75952-648">10: Enterprise Edition server, hosts users and applications (bit positions 1 and 3)</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="75952-649">Live Communications Server 2005 の新サービスです。</span><span class="sxs-lookup"><span data-stu-id="75952-649">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="75952-650">Msrtcsip-userenabled true-PoolVersion</span><span class="sxs-lookup"><span data-stu-id="75952-650">msRTCSIP-PoolVersion</span></span></p></td>
<td><p><span data-ttu-id="75952-651">この属性はプールのバージョンを定義します。</span><span class="sxs-lookup"><span data-stu-id="75952-651">This attribute defines the pool version.</span></span> <span data-ttu-id="75952-652">これは、主要製品のリリースごとにインクリメントされる整数型です。</span><span class="sxs-lookup"><span data-stu-id="75952-652">It is an integer type that is incremented with each major product release.</span></span></p>
<p><span data-ttu-id="75952-653">有効な値の型は、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="75952-653">The possible valid value types are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="75952-654">0: Live Communications Server 2003</span><span class="sxs-lookup"><span data-stu-id="75952-654">0: Live Communications Server 2003</span></span></p></li>
<li><p><span data-ttu-id="75952-655">1: Live Communications Server 2005</span><span class="sxs-lookup"><span data-stu-id="75952-655">1: Live Communications Server 2005</span></span></p></li>
<li><p><span data-ttu-id="75952-656">2: SP1 での Live Communications Server 2005</span><span class="sxs-lookup"><span data-stu-id="75952-656">2: Live Communications Server 2005 with SP1</span></span></p></li>
<li><p><span data-ttu-id="75952-657">3: Office Communications Server 2007</span><span class="sxs-lookup"><span data-stu-id="75952-657">3: Office Communications Server 2007</span></span></p></li>
<li><p><span data-ttu-id="75952-658">4: Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="75952-658">4: Office Communications Server 2007 R2</span></span></p></li>
<li><p><span data-ttu-id="75952-659">5: Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="75952-659">5: Lync Server 2010</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="75952-660">Live Communications Server 2005 SP1</span><span class="sxs-lookup"><span data-stu-id="75952-660">Live Communications Server 2005 with SP1.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="75952-661">Msrtcsip-userenabled true-PresenceFlags</span><span class="sxs-lookup"><span data-stu-id="75952-661">msRTCSIP-PresenceFlags</span></span></p></td>
<td><p><span data-ttu-id="75952-662">この属性には、プレゼンス設定を定義するオプションとフラグが含まれます。</span><span class="sxs-lookup"><span data-stu-id="75952-662">This attribute contains options and flags that define presence settings.</span></span></p></td>
<td><p><span data-ttu-id="75952-663">Office Communications Server 2007 R2 の新製品。</span><span class="sxs-lookup"><span data-stu-id="75952-663">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="75952-664">Msrtcsip-userenabled true-PresencePolicy</span><span class="sxs-lookup"><span data-stu-id="75952-664">msRTCSIP-PresencePolicy</span></span></p></td>
<td><p><span data-ttu-id="75952-665">この属性には、プレゼンスポリシーオブジェクトの DN が含まれます。</span><span class="sxs-lookup"><span data-stu-id="75952-665">This attribute contains the DN for a presence policy object.</span></span></p></td>
<td><p><span data-ttu-id="75952-666">Office Communications Server 2007 R2 の新製品。</span><span class="sxs-lookup"><span data-stu-id="75952-666">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="75952-667">Msrtcsip-userenabled true-PrimaryHomeServer</span><span class="sxs-lookup"><span data-stu-id="75952-667">msRTCSIP-PrimaryHomeServer</span></span></p></td>
<td><p><span data-ttu-id="75952-668">この属性によって、SIP メッセージングのユーザーまたは連絡先が有効になります。</span><span class="sxs-lookup"><span data-stu-id="75952-668">This attribute enables a user or contact for SIP messaging.</span></span> <span data-ttu-id="75952-669">この機能は、中央フォレストのトポロジでは、ユーザーオブジェクトではなく SIP 対応の連絡先オブジェクトであるため、連絡先クラスに追加されます。</span><span class="sxs-lookup"><span data-stu-id="75952-669">It is added to the contact class because in the central forest topology, contact objects, not user objects, are SIP enabled.</span></span></p>
<p><span data-ttu-id="75952-670">有効な値は、ユーザーが所属する Standard Edition server または Enterprise Edition のフロントエンドプールの DN です。</span><span class="sxs-lookup"><span data-stu-id="75952-670">The valid value is the DN of the Standard Edition server or Enterprise Edition Front End pool where a user is homed.</span></span></p></td>
<td><p><span data-ttu-id="75952-671">Live Communications Server 2005 の新サービスです。</span><span class="sxs-lookup"><span data-stu-id="75952-671">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="75952-672">msRTCSIP-PrimaryUserAddress</span><span class="sxs-lookup"><span data-stu-id="75952-672">msRTCSIP-PrimaryUserAddress</span></span></p></td>
<td><p><span data-ttu-id="75952-673">この属性には、特定のユーザーの SIP アドレスが含まれます。</span><span class="sxs-lookup"><span data-stu-id="75952-673">This attribute contains the SIP address of a given user.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="75952-674">Msrtcsip-userenabled true-PrivateLine</span><span class="sxs-lookup"><span data-stu-id="75952-674">msRTCSIP-PrivateLine</span></span></p></td>
<td><p><span data-ttu-id="75952-675">この属性には、プライベート回線デバイスのデバイス ID が含まれます。</span><span class="sxs-lookup"><span data-stu-id="75952-675">This attribute contains the device ID of the private line device.</span></span></p></td>
<td><p><span data-ttu-id="75952-676">Lync Server 2010 の新サービスです。</span><span class="sxs-lookup"><span data-stu-id="75952-676">New in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="75952-677">Msrtcsip-userenabled true-ルーティング可能</span><span class="sxs-lookup"><span data-stu-id="75952-677">msRTCSIP-Routable</span></span></p></td>
<td><p><span data-ttu-id="75952-678">この属性は、Lync Server がその GRUU アドレスを使ってこのサービスにルーティングすることを許可するかどうかを決定するために使用されるブール型の属性です。</span><span class="sxs-lookup"><span data-stu-id="75952-678">This attribute is a Boolean attribute used to determine whether Lync Server is authorized to route to this service using its GRUU address.</span></span> <span data-ttu-id="75952-679">この値が<strong>TRUE</strong>に設定されている場合、Lync Server はこのサービスにルーティングすることを許可されています。</span><span class="sxs-lookup"><span data-stu-id="75952-679">If this value is set to <strong>TRUE</strong>, Lync Server is authorized to route to this service.</span></span> <span data-ttu-id="75952-680">この値が<strong>FALSE</strong>に設定されている場合、Lync Server はこのサービスにルーティングする権限がありません。</span><span class="sxs-lookup"><span data-stu-id="75952-680">If this value is set to <strong>FALSE</strong>, Lync Server is not authorized to route to this service.</span></span></p></td>
<td><p><span data-ttu-id="75952-681">Office Communications Server 2007 の新製品。</span><span class="sxs-lookup"><span data-stu-id="75952-681">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="75952-682">Msrtcsip-userenabled true-RouteUsageAttribute (廃止)</span><span class="sxs-lookup"><span data-stu-id="75952-682">msRTCSIP-RouteUsageAttribute (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="75952-683">この単一値の UNICODE 文字列属性は、電話ルートの使用を限定する属性を定義します。</span><span class="sxs-lookup"><span data-stu-id="75952-683">This single-valued UNICODE string attribute defines an attribute that qualifies the usage for a phone route.</span></span> <span data-ttu-id="75952-684">電話ルートの選択は、電話ルートに割り当てられる利用属性と、発信者に許可されているポリシー使用属性の2つの要素に基づいて決定されます。</span><span class="sxs-lookup"><span data-stu-id="75952-684">Selection of a phone route is determined based on two elements: the usage attribute assigned to the phone route and the caller’s allowed policy usage attributes.</span></span> <span data-ttu-id="75952-685">呼び出し元の使用が許可されている使用法属性を持つ最初の電話ルートが選択されています。</span><span class="sxs-lookup"><span data-stu-id="75952-685">The first phone route with a usage attribute that matches the caller’s allowed usage is selected.</span></span></p></td>
<td><p><span data-ttu-id="75952-686">Office Communications Server 2007 の新製品。</span><span class="sxs-lookup"><span data-stu-id="75952-686">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="75952-687">Lync Server 2010 では廃止されています。</span><span class="sxs-lookup"><span data-stu-id="75952-687">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="75952-688">Msrtcsip-userenabled true-RouteUsageLinks (廃止)</span><span class="sxs-lookup"><span data-stu-id="75952-688">msRTCSIP-RouteUsageLinks (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="75952-689">この複数値識別名 (DN) 属性には、ルートの使用の識別名の一覧が含まれています。</span><span class="sxs-lookup"><span data-stu-id="75952-689">This multi-valued distinguished name (DN) attribute contains a list of route usage distinguished names.</span></span></p>
<p><span data-ttu-id="75952-690">転送リンク:<strong>リンク ID 11032</strong></span><span class="sxs-lookup"><span data-stu-id="75952-690">Forward link: <strong>Link ID 11032</strong></span></span></p>
<p><span data-ttu-id="75952-691">この属性は、対応する back link <strong>msrtcsip-userenabled true-PhoneRouteBL</strong>への転送リンクです。</span><span class="sxs-lookup"><span data-stu-id="75952-691">This attribute is a forward link to the corresponding back link <strong>msRTCSIP-PhoneRouteBL</strong>.</span></span></p></td>
<td><p><span data-ttu-id="75952-692">Lync Server 2010 では廃止されています。</span><span class="sxs-lookup"><span data-stu-id="75952-692">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="75952-693">Msrtcsip-userenabled true-RoutingPoolDN</span><span class="sxs-lookup"><span data-stu-id="75952-693">msRTCSIP-RoutingPoolDN</span></span></p></td>
<td><p><span data-ttu-id="75952-694">この属性には、この MCU または信頼されたサービスに宛てたすべての SIP トラフィックが通過する必要があるプールを指す DN が含まれています。</span><span class="sxs-lookup"><span data-stu-id="75952-694">This attribute contains the DN that points to the pool that all SIP traffic addressed to this MCU or Trusted Service must go through.</span></span></p></td>
<td><p><span data-ttu-id="75952-695">Office Communications Server 2007 R2 の新製品。</span><span class="sxs-lookup"><span data-stu-id="75952-695">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="75952-696">Msrtcsip-userenabled true-RuleName (廃止)</span><span class="sxs-lookup"><span data-stu-id="75952-696">msRTCSIP-RuleName (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="75952-697">この単一値の UNICODE 文字列属性は、正規化ルールのフレンドリ名を指定するため、管理者が簡単に参照できます。</span><span class="sxs-lookup"><span data-stu-id="75952-697">This single-valued UNICODE string attribute specifies the friendly name of the normalization rule, so it can easily be referenced by an administrator.</span></span></p></td>
<td><p><span data-ttu-id="75952-698">Office Communications Server 2007 の新製品。</span><span class="sxs-lookup"><span data-stu-id="75952-698">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="75952-699">Lync Server 2010 では廃止されています。</span><span class="sxs-lookup"><span data-stu-id="75952-699">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="75952-700">Msrtcsip-userenabled true-SchemaVersion</span><span class="sxs-lookup"><span data-stu-id="75952-700">msRTCSIP-SchemaVersion</span></span></p></td>
<td><p><span data-ttu-id="75952-701">この属性は、組織に現在展開されているスキーマバージョンを表します。</span><span class="sxs-lookup"><span data-stu-id="75952-701">This attribute represents the schema version currently deployed in the organization.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="75952-702">Msrtcsip-userenabled true-SearchMaxRequests (廃止)</span><span class="sxs-lookup"><span data-stu-id="75952-702">msRTCSIP-SearchMaxRequests (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="75952-703">この属性は、ユーザーが Communicator を使って連絡先を検索するときに、ディレクトリ検索から返される検索結果の数を制限します。</span><span class="sxs-lookup"><span data-stu-id="75952-703">This attribute limits the number of search results to be returned from a directory search when a user searches for a contact using Communicator.</span></span> <span data-ttu-id="75952-704">この属性は、クライアントによって指定された値を上書きします。</span><span class="sxs-lookup"><span data-stu-id="75952-704">This attribute will override the value provided by the client.</span></span></p></td>
<td><p><span data-ttu-id="75952-705">Lync Server 2010 では廃止されています。</span><span class="sxs-lookup"><span data-stu-id="75952-705">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="75952-706">Msrtcsip-userenabled true-SearchMaxResults (廃止)</span><span class="sxs-lookup"><span data-stu-id="75952-706">msRTCSIP-SearchMaxResults (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="75952-707">この属性は、返される検索要求の数を制限します。</span><span class="sxs-lookup"><span data-stu-id="75952-707">This attribute limits the number of search requests returned.</span></span></p></td>
<td><p><span data-ttu-id="75952-708">Lync Server 2010 では廃止されています。</span><span class="sxs-lookup"><span data-stu-id="75952-708">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="75952-709">Msrtcsip-userenabled true-ServerBL</span><span class="sxs-lookup"><span data-stu-id="75952-709">msRTCSIP-ServerBL</span></span></p></td>
<td><p><span data-ttu-id="75952-710">この複数値属性は、識別名 (DN) の一覧を含む戻るリンクです。</span><span class="sxs-lookup"><span data-stu-id="75952-710">This multi-valued attribute is a back link that contains a list of distinguished names (DN).</span></span> <span data-ttu-id="75952-711">これらの DNs はプールまたは<strong>Trustedservice</strong>オブジェクトを参照します。</span><span class="sxs-lookup"><span data-stu-id="75952-711">These DNs point to a pool or <strong>TrustedService</strong> object.</span></span></p>
<p><span data-ttu-id="75952-712">この属性は、 <strong>msrtcsip-userenabled true-TrustedServiceLinks</strong>の前方リンクに対応しています。</span><span class="sxs-lookup"><span data-stu-id="75952-712">This attribute corresponds to the forward link <strong>msRTCSIP-TrustedServiceLinks</strong>.</span></span></p></td>
<td><p><span data-ttu-id="75952-713">Office Communications Server 2007 の新製品。</span><span class="sxs-lookup"><span data-stu-id="75952-713">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="75952-714">Msrtcsip-userenabled true-ServerData</span><span class="sxs-lookup"><span data-stu-id="75952-714">msRTCSIP-ServerData</span></span></p></td>
<td><p><span data-ttu-id="75952-715">この属性は将来使用するために予約されています。</span><span class="sxs-lookup"><span data-stu-id="75952-715">This attribute is reserved for future use.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="75952-716">Msrtcsip-userenabled true-ServerReferenceBL (廃止)</span><span class="sxs-lookup"><span data-stu-id="75952-716">msRTCSIP-ServerReferenceBL (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="75952-717">この複数値属性には、識別名のリストが含まれています。</span><span class="sxs-lookup"><span data-stu-id="75952-717">This multi-valued attribute contains a list of distinguished names.</span></span> <span data-ttu-id="75952-718">これらの識別名は、既定の場所プロファイルを割り当てることができる他のサーバーオブジェクトを参照する戻るリンクです。</span><span class="sxs-lookup"><span data-stu-id="75952-718">These distinguished names are back links that reference other server objects that can be assigned a default location profile.</span></span></p>
<p><span data-ttu-id="75952-719">戻るリンク:<strong>リンク ID 11037</strong></span><span class="sxs-lookup"><span data-stu-id="75952-719">Back link: <strong>Link ID 11037</strong></span></span></p>
<p><span data-ttu-id="75952-720">この戻るリンクへの対応する前方リンクは<strong>msrtcsip-userenabled true-DefaultLocationProfileLink</strong>です。</span><span class="sxs-lookup"><span data-stu-id="75952-720">The corresponding forward link to this back link is <strong>msRTCSIP-DefaultLocationProfileLink</strong>.</span></span></p>
<p><span data-ttu-id="75952-721">この back link 属性は、プールおよび仲介サーバーのみを参照します。</span><span class="sxs-lookup"><span data-stu-id="75952-721">This back link attribute references pools and Mediation Servers only.</span></span></p></td>
<td><p><span data-ttu-id="75952-722">Office Communications Server 2007 の新製品。</span><span class="sxs-lookup"><span data-stu-id="75952-722">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="75952-723">Lync Server 2010 では廃止されています。</span><span class="sxs-lookup"><span data-stu-id="75952-723">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="75952-724">Msrtcsip-userenabled true-ServerVersion</span><span class="sxs-lookup"><span data-stu-id="75952-724">msRTCSIP-ServerVersion</span></span></p></td>
<td><p><span data-ttu-id="75952-725">この属性は、サーバーのバージョン情報を定義します。</span><span class="sxs-lookup"><span data-stu-id="75952-725">This attribute defines the version information of the server.</span></span> <span data-ttu-id="75952-726">このバージョン番号は、すべてのサーバーの役割に適用されます。</span><span class="sxs-lookup"><span data-stu-id="75952-726">This version number applies to all server roles.</span></span> <span data-ttu-id="75952-727">これは、各公式の製品リリースによって増加する monotonously 整数です。</span><span class="sxs-lookup"><span data-stu-id="75952-727">It is a monotonously increasing integer that increments with each official product release.</span></span></p>
<p><span data-ttu-id="75952-728">有効な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="75952-728">The possible valid values are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="75952-729">未定義: Live Communications Server 2003</span><span class="sxs-lookup"><span data-stu-id="75952-729">Undefined: Live Communications Server 2003</span></span></p>
<p><span data-ttu-id="75952-730">                 Live Communications Server 2005</span><span class="sxs-lookup"><span data-stu-id="75952-730">                 Live Communications Server 2005</span></span></p>
<p><span data-ttu-id="75952-731">                 Live Communications Server 2005 SP1</span><span class="sxs-lookup"><span data-stu-id="75952-731">                 Live Communications Server 2005 with SP1</span></span></p></li>
<li><p><span data-ttu-id="75952-732">3: Office Communications Server 2007</span><span class="sxs-lookup"><span data-stu-id="75952-732">3: Office Communications Server 2007</span></span></p></li>
<li><p><span data-ttu-id="75952-733">4: Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="75952-733">4: Office Communications Server 2007 R2</span></span></p></li>
<li><p><span data-ttu-id="75952-734">5: Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="75952-734">5: Lync Server 2010</span></span></p></li>
<li><p><span data-ttu-id="75952-735">6: Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="75952-735">6: Lync Server 2013</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="75952-736">Office Communications Server 2007 の新製品。</span><span class="sxs-lookup"><span data-stu-id="75952-736">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="75952-737">Msrtcsip-userenabled true-SourceObjectType</span><span class="sxs-lookup"><span data-stu-id="75952-737">msRTCSIP-SourceObjectType</span></span></p></td>
<td><p><span data-ttu-id="75952-738">Integer 型の単一値属性は、次のように、 <strong>SourceObjectDN</strong>が指すオブジェクトの型を指定します。</span><span class="sxs-lookup"><span data-stu-id="75952-738">This single-valued attribute of integer type specifies the type of object the <strong>msDS-SourceObjectDN</strong> points to, as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="75952-739">null |0x00000001: 別のフォレストから Windows NT Server プリンシパルユーザーオブジェクトを表します。</span><span class="sxs-lookup"><span data-stu-id="75952-739">null | 0x00000001: Represents a Windows NT Server principal user object from a different forest</span></span></p></li>
<li><p><span data-ttu-id="75952-740">次の属性は、配布グループの展開用に別のフォレストからのグループの種類を表します。</span><span class="sxs-lookup"><span data-stu-id="75952-740">The following attributes represent a group type from a different forest for distribution group expansion:</span></span></p>
<ul>
<li><p><span data-ttu-id="75952-741">0x00000002: ADS_GROUP_TYPE_GLOBAL_GROUP</span><span class="sxs-lookup"><span data-stu-id="75952-741">0x00000002: ADS_GROUP_TYPE_GLOBAL_GROUP</span></span></p></li>
<li><p><span data-ttu-id="75952-742">0x00000004: ADS_GROUP_TYPE_DOMAIN_LOCAL_GROUP</span><span class="sxs-lookup"><span data-stu-id="75952-742">0x00000004: ADS_GROUP_TYPE_DOMAIN_LOCAL_GROUP</span></span></p></li>
<li><p><span data-ttu-id="75952-743">0x00000004: ADS_GROUP_TYPE_LOCAL_GROUP</span><span class="sxs-lookup"><span data-stu-id="75952-743">0x00000004: ADS_GROUP_TYPE_LOCAL_GROUP</span></span></p></li>
<li><p><span data-ttu-id="75952-744">0x00000008: ADS_GROUP_TYPE_UNIVERSAL_GROUP</span><span class="sxs-lookup"><span data-stu-id="75952-744">0x00000008: ADS_GROUP_TYPE_UNIVERSAL_GROUP</span></span></p></li>
<li><p><span data-ttu-id="75952-745">0x80000000: ADS_GROUP_TYPE_SECURITY_ENABLED</span><span class="sxs-lookup"><span data-stu-id="75952-745">0x80000000: ADS_GROUP_TYPE_SECURITY_ENABLED</span></span></p></li>
<li><p><span data-ttu-id="75952-746">0x90000000: 同じフォレストまたは別のフォレストからの自動応答またはサブスクライバーのアクセスオブジェクトを表します。</span><span class="sxs-lookup"><span data-stu-id="75952-746">0x90000000: Represents an Auto-Attendant or subscriber access object from the same forest or a different forest</span></span></p></li>
</ul></li>
</ul></td>
<td><p><span data-ttu-id="75952-747">Office Communications Server 2007 の新製品。</span><span class="sxs-lookup"><span data-stu-id="75952-747">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="75952-748">Msrtcsip-userenabled true-SubscriptionAuthRequired (廃止)</span><span class="sxs-lookup"><span data-stu-id="75952-748">msRTCSIP-SubscriptionAuthRequired (obsolete)</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="75952-749">Live Communications Server 2003 の新サービスです。</span><span class="sxs-lookup"><span data-stu-id="75952-749">New in Live Communications Server 2003.</span></span></p>
<p><span data-ttu-id="75952-750">現在、ライブ通信サーバー2005で廃止されています。</span><span class="sxs-lookup"><span data-stu-id="75952-750">Obsolete in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="75952-751">Msrtcsip-userenabled true-Targethoのメッセージ</span><span class="sxs-lookup"><span data-stu-id="75952-751">msRTCSIP-TargetHomeServer</span></span></p></td>
<td><p><span data-ttu-id="75952-752">この属性によって、ユーザーまたは連絡先オブジェクトを、Lync Server プール間で移動することができます。</span><span class="sxs-lookup"><span data-stu-id="75952-752">This attribute enables you to move a user or contact object from one Lync Server pool to another.</span></span> <span data-ttu-id="75952-753">この属性は、中央フォレストのトポロジでは、ユーザーオブジェクトではなく、SIP が有効になるため、contact クラスに追加されます。</span><span class="sxs-lookup"><span data-stu-id="75952-753">This attribute is added to the contact class, because in the central forest topology, contact objects, not user objects, are SIP enabled.</span></span></p>
<p><span data-ttu-id="75952-754">有効な値は、ユーザーが移動するターゲットの Standard Edition サーバーまたはフロントエンドプールの DN です。</span><span class="sxs-lookup"><span data-stu-id="75952-754">The valid value is the DN of the destination Standard Edition server or Front End pool to which a user is to be moved.</span></span></p></td>
<td><p><span data-ttu-id="75952-755">Live Communications Server 2005 の新サービスです。</span><span class="sxs-lookup"><span data-stu-id="75952-755">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="75952-756">Msrtcsip-userenabled true-TargetPhoneNumber (廃止)</span><span class="sxs-lookup"><span data-stu-id="75952-756">msRTCSIP-TargetPhoneNumber (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="75952-757">この単一値文字列属性には、 <strong>msrtcsip-userenabled true</strong>で定義されたゲートウェイにルーティングするための電話番号のパターンまたは範囲が含まれます。</span><span class="sxs-lookup"><span data-stu-id="75952-757">This single-valued string attribute contains a phone number pattern or range to route to the specified gateways defined in <strong>msRTCSIP-Gateways</strong>.</span></span></p></td>
<td><p><span data-ttu-id="75952-758">Lync Server 2010 では廃止されています。</span><span class="sxs-lookup"><span data-stu-id="75952-758">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="75952-759">Msrtcsip-userenabled true-TargetUserPolicies</span><span class="sxs-lookup"><span data-stu-id="75952-759">msRTCSIP-TargetUserPolicies</span></span></p></td>
<td><p><span data-ttu-id="75952-760">この属性は、Lync Server ユーザーのターゲットポリシーの名前と値のペアを格納します。</span><span class="sxs-lookup"><span data-stu-id="75952-760">This attribute stores name-value pairs for target policies for Lync Server users.</span></span></p></td>
<td><p><span data-ttu-id="75952-761">Lync Server 2010 の新サービスです。</span><span class="sxs-lookup"><span data-stu-id="75952-761">New in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="75952-762">Msrtcsip-userenabled true-TenantId</span><span class="sxs-lookup"><span data-stu-id="75952-762">msRTCSIP-TenantId</span></span></p></td>
<td><p><span data-ttu-id="75952-763">この属性には、テナントの一意の識別子が格納されます。</span><span class="sxs-lookup"><span data-stu-id="75952-763">This attribute stores the unique identifier for a tenant.</span></span></p></td>
<td><p><span data-ttu-id="75952-764">Lync Server 2010 の新サービスです。</span><span class="sxs-lookup"><span data-stu-id="75952-764">New in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="75952-765">Msrtcsip-userenabled true-翻訳 (廃止)</span><span class="sxs-lookup"><span data-stu-id="75952-765">msRTCSIP-Translation (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="75952-766">この属性は、Lync Server の音声機能によって使用され、一致が見つかった場合は、ダイヤルした番号に適用する翻訳文字列が含まれます。</span><span class="sxs-lookup"><span data-stu-id="75952-766">This attribute is used by the voice feature of Lync Server and contains the translation string to apply on the dialed number, if a match is found.</span></span></p></td>
<td><p><span data-ttu-id="75952-767">Office Communications Server 2007 の新製品。</span><span class="sxs-lookup"><span data-stu-id="75952-767">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="75952-768">Lync Server 2010 では廃止されています。</span><span class="sxs-lookup"><span data-stu-id="75952-768">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="75952-769">Msrtcsip-userenabled true-TrustedMCUData</span><span class="sxs-lookup"><span data-stu-id="75952-769">msRTCSIP-TrustedMCUData</span></span></p></td>
<td><p><span data-ttu-id="75952-770">この属性は将来使用するために予約されています。</span><span class="sxs-lookup"><span data-stu-id="75952-770">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="75952-771">Office Communications Server 2007 の新製品。</span><span class="sxs-lookup"><span data-stu-id="75952-771">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="75952-772">Msrtcsip-userenabled true-TrustedMCUFQDN</span><span class="sxs-lookup"><span data-stu-id="75952-772">msRTCSIP-TrustedMCUFQDN</span></span></p></td>
<td><p><span data-ttu-id="75952-773">この属性は、MCU の FQDN を含む文字列値です。</span><span class="sxs-lookup"><span data-stu-id="75952-773">This attribute is a string value that contains the FQDN of the MCU.</span></span> <span data-ttu-id="75952-774">これは単一値の属性です。</span><span class="sxs-lookup"><span data-stu-id="75952-774">This is a single-valued attribute.</span></span> <span data-ttu-id="75952-775">各セグメントの有効な値は、63文字です。FQDN 全体の有効な値は、255文字です。</span><span class="sxs-lookup"><span data-stu-id="75952-775">The valid value for each segment is 63 characters; the valid value for the entire FQDN is 255 characters.</span></span></p></td>
<td><p><span data-ttu-id="75952-776">Office Communications Server 2007 の新製品。</span><span class="sxs-lookup"><span data-stu-id="75952-776">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="75952-777">Msrtcsip-userenabled true-TrustedProxyData</span><span class="sxs-lookup"><span data-stu-id="75952-777">msRTCSIP-TrustedProxyData</span></span></p></td>
<td><p><span data-ttu-id="75952-778">この属性は将来使用するために予約されています。</span><span class="sxs-lookup"><span data-stu-id="75952-778">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="75952-779">Office Communications Server 2007 の新製品。</span><span class="sxs-lookup"><span data-stu-id="75952-779">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="75952-780">Msrtcsip-userenabled true-TrustedProxyFQDN</span><span class="sxs-lookup"><span data-stu-id="75952-780">msRTCSIP-TrustedProxyFQDN</span></span></p></td>
<td><p><span data-ttu-id="75952-781">この属性は、プロキシサーバーを実行しているサーバーの FQDN を含む文字列値です。</span><span class="sxs-lookup"><span data-stu-id="75952-781">This attribute is a string value that contains the FQDN of the server running Proxy Server.</span></span> <span data-ttu-id="75952-782">この属性は単一値になります。</span><span class="sxs-lookup"><span data-stu-id="75952-782">This attribute is single-valued.</span></span> <span data-ttu-id="75952-783">各セグメントの有効な値は、63文字です。FQDN 全体の有効な値は、255文字です。</span><span class="sxs-lookup"><span data-stu-id="75952-783">The valid value for each segment is 63 characters; the valid value for the entire FQDN is 255 characters.</span></span></p></td>
<td><p><span data-ttu-id="75952-784">Office Communications Server 2007 の新製品。</span><span class="sxs-lookup"><span data-stu-id="75952-784">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="75952-785">Msrtcsip-userenabled true-TrustedServerData</span><span class="sxs-lookup"><span data-stu-id="75952-785">msRTCSIP-TrustedServerData</span></span></p></td>
<td><p><span data-ttu-id="75952-786">この属性は将来使用するために予約されています。</span><span class="sxs-lookup"><span data-stu-id="75952-786">This attribute is reserved for future use.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="75952-787">Msrtcsip-userenabled true-TrustedServerFQDN</span><span class="sxs-lookup"><span data-stu-id="75952-787">msRTCSIP-TrustedServerFQDN</span></span></p></td>
<td><p><span data-ttu-id="75952-788">この属性は、信頼されたサーバーの FQDN を表す単一値属性です。</span><span class="sxs-lookup"><span data-stu-id="75952-788">This attribute is a single-valued attribute that represents the FQDN of a trusted server.</span></span></p></td>
<td><p><span data-ttu-id="75952-789">Live Communications Server 2005 の新サービスです。</span><span class="sxs-lookup"><span data-stu-id="75952-789">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="75952-790">Msrtcsip-userenabled true-TrustedServerVersion</span><span class="sxs-lookup"><span data-stu-id="75952-790">msRTCSIP-TrustedServerVersion</span></span></p></td>
<td><p><span data-ttu-id="75952-791">この属性は、信頼されたサーバーの一覧にあるサーバーのバージョン番号を指定します。</span><span class="sxs-lookup"><span data-stu-id="75952-791">This attribute specifies the version number of a server in the trusted server list.</span></span></p>
<p><span data-ttu-id="75952-792">有効な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="75952-792">The possible valid values are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="75952-793">NULL: Live Communications Server 2003</span><span class="sxs-lookup"><span data-stu-id="75952-793">NULL: Live Communications Server 2003</span></span></p></li>
<li><p><span data-ttu-id="75952-794">2: Live Communications Server 2005</span><span class="sxs-lookup"><span data-stu-id="75952-794">2: Live Communications Server 2005</span></span></p></li>
<li><p><span data-ttu-id="75952-795">3: Office Communications Server 2007</span><span class="sxs-lookup"><span data-stu-id="75952-795">3: Office Communications Server 2007</span></span></p></li>
<li><p><span data-ttu-id="75952-796">4: Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="75952-796">4: Office Communications Server 2007 R2</span></span></p></li>
<li><p><span data-ttu-id="75952-797">5: Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="75952-797">5: Lync Server 2010</span></span></p></li>
<li><p><span data-ttu-id="75952-798">6: Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="75952-798">6: Lync Server 2013</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="75952-799">Live Communications Server 2005 の新サービスです。</span><span class="sxs-lookup"><span data-stu-id="75952-799">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="75952-800">Msrtcsip-userenabled true-TrustedServiceFlags</span><span class="sxs-lookup"><span data-stu-id="75952-800">msRTCSIP-TrustedServiceFlags</span></span></p></td>
<td><p><span data-ttu-id="75952-801">この属性は、信頼されたサービスに対して有効になるオプションを定義します。</span><span class="sxs-lookup"><span data-stu-id="75952-801">This attribute defines the options that are enabled for the trusted service.</span></span></p></td>
<td><p><span data-ttu-id="75952-802">Office Communications Server 2007 R2 の新製品。</span><span class="sxs-lookup"><span data-stu-id="75952-802">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="75952-803">Msrtcsip-userenabled true-TrustedServiceLinks</span><span class="sxs-lookup"><span data-stu-id="75952-803">msRTCSIP-TrustedServiceLinks</span></span></p></td>
<td><p><span data-ttu-id="75952-804">この複数値属性には、メディアリレー認証サービスなどの信頼されたサービスオブジェクトを参照する識別名 (DN) の一覧が含まれています。</span><span class="sxs-lookup"><span data-stu-id="75952-804">This multi-valued attribute contains a list of distinguished names (DN) that reference a trusted service object, such as a Media Relay Authentication Service.</span></span> <span data-ttu-id="75952-805">リモートユーザー向けのオーディオシナリオをサポートするには、メディアリレー認証サービス (A/V 会議サービスを実行しているエッジサーバーに物理的に併置されているサービス) がプールに関連付けられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="75952-805">A Media Relay Authentication Service (physically collocated on the Edge Server running the A/V Conferencing service) must be associated with a pool to support audio scenarios for remote users.</span></span></p>
<p><span data-ttu-id="75952-806">この転送リンク属性への対応する [戻る] リンクは、 <strong>msrtcsip-userenabled true-ServerBL</strong>です。</span><span class="sxs-lookup"><span data-stu-id="75952-806">The corresponding back link to this forward link attribute is <strong>msRTCSIP-ServerBL</strong>.</span></span></p></td>
<td><p><span data-ttu-id="75952-807">コミュニケーション</span><span class="sxs-lookup"><span data-stu-id="75952-807">UC</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="75952-808">Msrtcsip-userenabled true-TrustedServicePort</span><span class="sxs-lookup"><span data-stu-id="75952-808">msRTCSIP-TrustedServicePort</span></span></p></td>
<td><p><span data-ttu-id="75952-809">この属性は、この GRUU サービスへの接続に使用するポート番号を定義する整数です。</span><span class="sxs-lookup"><span data-stu-id="75952-809">This attribute is an integer that defines the port number used to connect to this GRUU service.</span></span></p></td>
<td><p><span data-ttu-id="75952-810">Office Communications Server 2007 の新製品。</span><span class="sxs-lookup"><span data-stu-id="75952-810">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="75952-811">Msrtcsip-userenabled true-TrustedServiceType</span><span class="sxs-lookup"><span data-stu-id="75952-811">msRTCSIP-TrustedServiceType</span></span></p></td>
<td><p><span data-ttu-id="75952-812">この属性は、GRUU サービスの型を定義する文字列値です。</span><span class="sxs-lookup"><span data-stu-id="75952-812">This attribute is a string value that defines the type of GRUU service it represents.</span></span></p>
<p><span data-ttu-id="75952-813">有効な GRUU サービスの種類は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="75952-813">The valid GRUU service types are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="75952-814">MediationServer</span><span class="sxs-lookup"><span data-stu-id="75952-814">MediationServer</span></span></p></li>
<li><p><span data-ttu-id="75952-815">ゲートウェイ</span><span class="sxs-lookup"><span data-stu-id="75952-815">Gateway</span></span></p></li>
<li><p><span data-ttu-id="75952-816">メディアリレー認証サービス (MRAS)</span><span class="sxs-lookup"><span data-stu-id="75952-816">Media Relay Authentication Service (MRAS)</span></span></p></li>
<li><p><span data-ttu-id="75952-817">QoSM</span><span class="sxs-lookup"><span data-stu-id="75952-817">QoSM</span></span></p></li>
<li><p><span data-ttu-id="75952-818">Msrtcsip-userenabled true-UserExtension CWA</span><span class="sxs-lookup"><span data-stu-id="75952-818">msRTCSIP-UserExtension CWA</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="75952-819">Office Communications Server 2007 の新製品。</span><span class="sxs-lookup"><span data-stu-id="75952-819">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="75952-820">Msrtcsip-userenabled true-TrustedWebComponentsServerData</span><span class="sxs-lookup"><span data-stu-id="75952-820">msRTCSIP-TrustedWebComponentsServerData</span></span></p></td>
<td><p><span data-ttu-id="75952-821">この属性は将来使用するために予約されています。</span><span class="sxs-lookup"><span data-stu-id="75952-821">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="75952-822">Office Communications Server 2007 の新製品。</span><span class="sxs-lookup"><span data-stu-id="75952-822">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="75952-823">Msrtcsip-userenabled true-TrustedWebComponentsServerFQDN</span><span class="sxs-lookup"><span data-stu-id="75952-823">msRTCSIP-TrustedWebComponentsServerFQDN</span></span></p></td>
<td><p><span data-ttu-id="75952-824">この属性は、Lync Server Web サービスが実行されている IIS の FQDN を含む文字列値です。</span><span class="sxs-lookup"><span data-stu-id="75952-824">This attribute is a string value that contains the FQDN of the IIS running Lync Server Web Services.</span></span> <span data-ttu-id="75952-825">これは単一値の属性です。</span><span class="sxs-lookup"><span data-stu-id="75952-825">This is a single-valued attribute.</span></span> <span data-ttu-id="75952-826">各セグメントの有効な値は、63文字です。FQDN 全体の有効な値は、255文字です。</span><span class="sxs-lookup"><span data-stu-id="75952-826">The valid value for each segment is 63 characters; the valid value for the entire FQDN is 255 characters.</span></span></p></td>
<td><p><span data-ttu-id="75952-827">Office Communications Server 2007 の新製品。</span><span class="sxs-lookup"><span data-stu-id="75952-827">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="75952-828">Msrtcsip-userenabled true-UCFlags (廃止)</span><span class="sxs-lookup"><span data-stu-id="75952-828">msRTCSIP-UCFlags (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="75952-829">この属性は、すべてのユーザーオブジェクトまたは連絡先オブジェクトでグローバルに有効になるさまざまな UC オプションを定義します。</span><span class="sxs-lookup"><span data-stu-id="75952-829">This attribute defines different UC options that are enabled globally to all user or contact objects.</span></span> <span data-ttu-id="75952-830">この属性は、整数型のビットマスク値です。</span><span class="sxs-lookup"><span data-stu-id="75952-830">This attribute is a bit-mask value of integer type.</span></span> <span data-ttu-id="75952-831">各オプションはビットが存在することで表されます。</span><span class="sxs-lookup"><span data-stu-id="75952-831">Each option is represented by the presence of a bit.</span></span></p>
<p><span data-ttu-id="75952-832">有効な値 (および関連するビット位置) は、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="75952-832">The possible valid value (and associated bit position) are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="75952-833">4: Peruserucpolicy (ビット位置 2)</span><span class="sxs-lookup"><span data-stu-id="75952-833">4: UsePerUserUCPolicy (bit position 2)</span></span></p></li>
</ul>
<p><span data-ttu-id="75952-834">このビットが設定されると、ユーザーごとに UC ポリシーが定義されます。</span><span class="sxs-lookup"><span data-stu-id="75952-834">When this bit is set, the UC policy is defined per user.</span></span></p></td>
<td><p><span data-ttu-id="75952-835">Lync Server 2010 では廃止されています。</span><span class="sxs-lookup"><span data-stu-id="75952-835">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="75952-836">Msrtcsip-userenabled true-UCPolicy (廃止)</span><span class="sxs-lookup"><span data-stu-id="75952-836">msRTCSIP-UCPolicy (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="75952-837">この単一値属性には、管理者がこのユーザーに割り当てた UC ポリシーの識別名 (DN) が含まれます。</span><span class="sxs-lookup"><span data-stu-id="75952-837">This single-valued attribute contains the distinguished name (DN) of the UC policy that the administrator has assigned for this user.</span></span></p></td>
<td><p><span data-ttu-id="75952-838">Lync Server 2010 では廃止されています。</span><span class="sxs-lookup"><span data-stu-id="75952-838">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="75952-839">Msrtcsip-userenabled true-UserDomainList (廃止)</span><span class="sxs-lookup"><span data-stu-id="75952-839">msRTCSIP-UserDomainList (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="75952-840">この属性は、SIP 対応ユーザーをホストしているフォレスト内のすべてのドメインの一覧を提供します。</span><span class="sxs-lookup"><span data-stu-id="75952-840">This attribute provides a list of all the domains in a forest that host SIP-enabled users.</span></span> <span data-ttu-id="75952-841">既定値は空の一覧で、フォレスト内のすべてのドメインが SIP 対応であることを示します。</span><span class="sxs-lookup"><span data-stu-id="75952-841">The default is an empty list, indicating that all domains in the forest are SIP-enabled.</span></span></p>
<p><span data-ttu-id="75952-842">有効な値は、個々のドメインのドメイン名を表す複数の文字列です。</span><span class="sxs-lookup"><span data-stu-id="75952-842">Valid values are multiple strings representing the domain names of individual domains.</span></span></p></td>
<td><p><span data-ttu-id="75952-843">Live Communications Server 2005 の新サービスです。</span><span class="sxs-lookup"><span data-stu-id="75952-843">New in Live Communications Server 2005.</span></span></p>
<p><span data-ttu-id="75952-844">Lync Server 2010 では廃止されています。</span><span class="sxs-lookup"><span data-stu-id="75952-844">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="75952-845">Msrtcsip-userenabled true-UserEnabled</span><span class="sxs-lookup"><span data-stu-id="75952-845">msRTCSIP-UserEnabled</span></span></p></td>
<td><p><span data-ttu-id="75952-846">この属性は、ユーザーが Lync Server で現在有効になっているかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="75952-846">This attribute determines whether the user is currently enabled for Lync Server.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="75952-847">Msrtcsip-userenabled true-UserExtension</span><span class="sxs-lookup"><span data-stu-id="75952-847">msRTCSIP-UserExtension</span></span></p></td>
<td><p><span data-ttu-id="75952-848">この複数値を持つ属性には、name = value の&quot;形式の名前と値のペアの一覧が含まれています。&quot;この属性は、グローバルカタログのレプリケーション用にマークされます。</span><span class="sxs-lookup"><span data-stu-id="75952-848">This multi-valued attribute contains a list of name-value pairs in the format of &quot;name=value.&quot; This attribute is marked for global catalog replication.</span></span></p></td>
<td><p><span data-ttu-id="75952-849">SP1 での最新のライブ通信サーバー2005。</span><span class="sxs-lookup"><span data-stu-id="75952-849">New in Live Communications Server 2005 with SP1.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="75952-850">Msrtcsip-userenabled true-UserLocationProfile</span><span class="sxs-lookup"><span data-stu-id="75952-850">msRTCSIP-UserLocationProfile</span></span></p></td>
<td><p><span data-ttu-id="75952-851">この属性には、場所プロファイルオブジェクトを参照する識別名 (DN) が含まれます。</span><span class="sxs-lookup"><span data-stu-id="75952-851">This attribute contains the distinguished name (DN) that points to a location profile object.</span></span></p></td>
<td><p><span data-ttu-id="75952-852">Office Communications Server 2007 R2 の新製品。</span><span class="sxs-lookup"><span data-stu-id="75952-852">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="75952-853">Msrtcsip-userenabled true-UserPolicies</span><span class="sxs-lookup"><span data-stu-id="75952-853">msRTCSIP-UserPolicies</span></span></p></td>
<td><p><span data-ttu-id="75952-854">この属性は、ユーザーポリシーの名前と値のペアを格納します。</span><span class="sxs-lookup"><span data-stu-id="75952-854">This attribute stores name-value pairs for user policies.</span></span></p></td>
<td><p><span data-ttu-id="75952-855">Lync Server 2010 の新サービスです。</span><span class="sxs-lookup"><span data-stu-id="75952-855">New in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="75952-856">Msrtcsip-userenabled true-UserPolicy</span><span class="sxs-lookup"><span data-stu-id="75952-856">msRTCSIP-UserPolicy</span></span></p></td>
<td><p><span data-ttu-id="75952-857">これは、さまざまな種類のグローバルユーザーポリシーを指定するバイナリ (DN_WITH_BINARY) の識別名のリストを含む複数値の属性です。</span><span class="sxs-lookup"><span data-stu-id="75952-857">This is a multi-valued attribute containing a list of distinguished names with binary (DN_WITH_BINARY) pointing to global user policies of different types.</span></span> <span data-ttu-id="75952-858">バイナリ部分は、DN の部分が指しているポリシーの種類を示します。</span><span class="sxs-lookup"><span data-stu-id="75952-858">The binary part indicates the type of policy to which the DN portion points.</span></span></p>
<p><span data-ttu-id="75952-859">有効なバイナリ値は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="75952-859">The valid binary values are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="75952-860">0x00000001: 会議のポリシー</span><span class="sxs-lookup"><span data-stu-id="75952-860">0x00000001: Meeting policy</span></span></p></li>
<li><p><span data-ttu-id="75952-861">0x00000002: UC ポリシー</span><span class="sxs-lookup"><span data-stu-id="75952-861">0x00000002: UC policy</span></span></p></li>
<li><p><span data-ttu-id="75952-862">0x00000005: プレゼンスポリシー</span><span class="sxs-lookup"><span data-stu-id="75952-862">0x00000005: Presence policy</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="75952-863">Office Communications Server 2007 の新製品。</span><span class="sxs-lookup"><span data-stu-id="75952-863">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="75952-864">Msrtcsip-userenabled true-UserRoutingGroupId</span><span class="sxs-lookup"><span data-stu-id="75952-864">msRTCSIP-UserRoutingGroupId</span></span></p></td>
<td><p><span data-ttu-id="75952-865">これは、SIP ルーティンググループの ID です。</span><span class="sxs-lookup"><span data-stu-id="75952-865">This is the SIP routing group ID.</span></span> <span data-ttu-id="75952-866">同じグループ内のユーザーは、同じフロントエンドサーバーに登録されます。</span><span class="sxs-lookup"><span data-stu-id="75952-866">Users in the same group will register to the same Front End Server.</span></span></p></td>
<td><p><span data-ttu-id="75952-867">Lync Server 2013 の新サービスです。</span><span class="sxs-lookup"><span data-stu-id="75952-867">New in Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="75952-868">Msrtcsip-userenabled true-Webcontacts データ</span><span class="sxs-lookup"><span data-stu-id="75952-868">msRTCSIP-WebComponentsData</span></span></p></td>
<td><p><span data-ttu-id="75952-869">これは複数値の属性です。</span><span class="sxs-lookup"><span data-stu-id="75952-869">This is a multi-valued attribute.</span></span> <span data-ttu-id="75952-870">この属性は将来使用するために予約されています。</span><span class="sxs-lookup"><span data-stu-id="75952-870">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="75952-871">Office Communications Server 2007 の新製品。</span><span class="sxs-lookup"><span data-stu-id="75952-871">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="75952-872">Msrtcsip-userenabled true-WebComponentsPoolAddress</span><span class="sxs-lookup"><span data-stu-id="75952-872">msRTCSIP-WebComponentsPoolAddress</span></span></p></td>
<td><p><span data-ttu-id="75952-873">この単一値の属性は、web コンポーネントが属しているプールまたは Standard Edition サーバーを指します。</span><span class="sxs-lookup"><span data-stu-id="75952-873">This single-valued attribute points to the pool or Standard Edition server to which the web components belong.</span></span></p>
<p><span data-ttu-id="75952-874">転送リンク:<strong>リンク ID 11028</strong></span><span class="sxs-lookup"><span data-stu-id="75952-874">Forward link: <strong>Link ID 11028</strong></span></span></p>
<p><span data-ttu-id="75952-875">この転送リンク属性への対応する "戻る" リンクは、 <strong>Msrtcsip-userenabled true Webservers サーバー</strong>です。</span><span class="sxs-lookup"><span data-stu-id="75952-875">The corresponding back link to this forward link attribute is <strong>msRTCSIP-WebComponentsServers</strong>.</span></span></p></td>
<td><p><span data-ttu-id="75952-876">Office Communications Server 2007 の新製品。</span><span class="sxs-lookup"><span data-stu-id="75952-876">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="75952-877">Msrtcsip-userenabled true-Webservers サーバー</span><span class="sxs-lookup"><span data-stu-id="75952-877">msRTCSIP-WebComponentsServers</span></span></p></td>
<td><p><span data-ttu-id="75952-878">この属性は、複数値を持つ識別名の一覧です。</span><span class="sxs-lookup"><span data-stu-id="75952-878">This attribute is a multi-valued list of distinguished names.</span></span> <span data-ttu-id="75952-879">この属性には、このプールに関連付けられているすべての Web サーバーの一覧が含まれます。</span><span class="sxs-lookup"><span data-stu-id="75952-879">This attribute contains a list of all Web servers associated with this pool.</span></span></p>
<p><span data-ttu-id="75952-880">戻るリンク:<strong>リンク ID 11029</strong></span><span class="sxs-lookup"><span data-stu-id="75952-880">Back link: <strong>Link ID 11029</strong></span></span></p>
<p><span data-ttu-id="75952-881">この戻るリンクへの対応する前方リンクは<strong>Msrtcsip-userenabled true WebComponentsPoolAddress</strong>です。</span><span class="sxs-lookup"><span data-stu-id="75952-881">The corresponding forward link to this back link is <strong>msRTCSIP-WebComponentsPoolAddress</strong>.</span></span></p></td>
<td><p><span data-ttu-id="75952-882">Office Communications Server 2007 の新製品。</span><span class="sxs-lookup"><span data-stu-id="75952-882">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="75952-883">Msrtcsip-userenabled true の形式の Instanceid (廃止)</span><span class="sxs-lookup"><span data-stu-id="75952-883">msRTCSIP-WMIInstanceId (obsolete)</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="75952-884">Live Communications Server 2003 の新サービスです。</span><span class="sxs-lookup"><span data-stu-id="75952-884">New in Live Communications Server 2003.</span></span></p>
<p><span data-ttu-id="75952-885">現在、ライブ通信サーバー2005で廃止されています。</span><span class="sxs-lookup"><span data-stu-id="75952-885">Obsolete in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="75952-886">他の Ip電話</span><span class="sxs-lookup"><span data-stu-id="75952-886">OtherIPPhone</span></span></p></td>
<td><p><span data-ttu-id="75952-887">この既存の Active Directory 属性は、電話の代替 TCP/IP アドレスの一覧を指定するためにテレフォニーで使用されます。</span><span class="sxs-lookup"><span data-stu-id="75952-887">This existing Active Directory attribute is used by telephony to specify the list of alternate TCP/IP addresses for a phone.</span></span></p></td>
<td><p><span data-ttu-id="75952-888">Windows Server 2008 オペレーティングシステムの新機能。</span><span class="sxs-lookup"><span data-stu-id="75952-888">New in Windows Server 2008 operating system.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="75952-889">他の電話帳</span><span class="sxs-lookup"><span data-stu-id="75952-889">PhoneOfficeOther</span></span></p></td>
<td><p><span data-ttu-id="75952-890">この既存の Active Directory 属性は、ユニファイドメッセージングの自動応答とサブスクライバーアクセス番号の呼び出しをルーティングすることを目的として、Lync Server のボイスコンポーネントに対してのみ使用されます。</span><span class="sxs-lookup"><span data-stu-id="75952-890">This existing Active Directory attribute is used by the voice components in Lync Server, for contact objects only, for the purpose of routing calls to the unified messaging auto-attendant and subscriber access numbers.</span></span> <span data-ttu-id="75952-891">無条件着信転送アドレスがこの複数値属性に保存されています。</span><span class="sxs-lookup"><span data-stu-id="75952-891">The unconditional call forwarding address is stored in this multi-valued attribute.</span></span> <span data-ttu-id="75952-892">このアカウントは、自動応答とサブスクライバーアクセスの特定の目的で作成されます。</span><span class="sxs-lookup"><span data-stu-id="75952-892">This account is created for the specific purpose of auto-attendant and subscriber access.</span></span> <span data-ttu-id="75952-893">このアカウントの属性は、管理者が変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="75952-893">This account’s attributes should not be modified by administrators.</span></span></p></td>
<td><p><span data-ttu-id="75952-894">Windows 2000 オペレーティングシステムの新機能。</span><span class="sxs-lookup"><span data-stu-id="75952-894">New in Windows 2000 operating system.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="75952-895">ProxyAddresses</span><span class="sxs-lookup"><span data-stu-id="75952-895">ProxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="75952-896">この既存の Active Directory マルチバリュー属性は、Windows 2000 で導入されたベース Active Directory スキーマの一部です。</span><span class="sxs-lookup"><span data-stu-id="75952-896">This existing Active Directory multi-valued attribute is part of the base Active Directory schema introduced in Windows 2000.</span></span> <span data-ttu-id="75952-897">この属性には、ユーザーのメールのさまざまな X400、X500、および SMTP アドレスが含まれています。</span><span class="sxs-lookup"><span data-stu-id="75952-897">This attribute contains the various X400, X500, and SMTP addresses of the user’s email.</span></span> <span data-ttu-id="75952-898">Live Communications Server 2003 以降では、 &quot;sip:&quot;タグを使用して、ユーザーの sip URI がこのリストに追加されます。</span><span class="sxs-lookup"><span data-stu-id="75952-898">In Live Communications Server 2003 and later, the user’s SIP URI is added to this list, using the &quot;sip:&quot; tag.</span></span></p>
<p><span data-ttu-id="75952-899">次のアプリケーションは、この属性によってユーザーの SIP URI を検索します。</span><span class="sxs-lookup"><span data-stu-id="75952-899">The following applications search the user’s SIP URI from this attribute:</span></span></p>
<ul>
<li><p><span data-ttu-id="75952-900">Microsoft Office Outlook 2003 メッセージングおよびコラボレーションクライアント</span><span class="sxs-lookup"><span data-stu-id="75952-900">Microsoft Office Outlook 2003 messaging and collaboration client</span></span></p></li>
<li><p><span data-ttu-id="75952-901">Microsoft Office SharePoint Server 2007</span><span class="sxs-lookup"><span data-stu-id="75952-901">Microsoft Office SharePoint Server 2007</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="75952-902">Windows 2000 オペレーティングシステムの新機能。</span><span class="sxs-lookup"><span data-stu-id="75952-902">New in Windows 2000 operating system.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="75952-903">TelephoneNumber</span><span class="sxs-lookup"><span data-stu-id="75952-903">TelephoneNumber</span></span></p></td>
<td><p><span data-ttu-id="75952-904">この既存の Active Directory の属性には、ユーザーの電話番号が含まれています。</span><span class="sxs-lookup"><span data-stu-id="75952-904">This existing Active Directory attribute contains the telephone number for the user.</span></span></p></td>
<td><p><span data-ttu-id="75952-905">Windows 2000 オペレーティングシステムの新機能。</span><span class="sxs-lookup"><span data-stu-id="75952-905">New in Windows 2000 operating system.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

