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
ms.openlocfilehash: 72da4adb0f660604dba7f20c9ddc333425086df2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41732637"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="schema-attributes-and-descriptions-in-lync-server-2013"></a><span data-ttu-id="6b2e2-102">Lync Server 2013 でのスキーマの属性と説明</span><span class="sxs-lookup"><span data-stu-id="6b2e2-102">Schema attributes and descriptions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6b2e2-103">_**最終更新日:** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="6b2e2-103">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="6b2e2-104">このセクションでは、Lync Server 2013 で使用されるすべてのスキーマ属性について説明します。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-104">This section describes all the schema attributes used by Lync Server 2013.</span></span> <span data-ttu-id="6b2e2-105">属性に関連付けられているクラスについては、「 [Lync Server 2013 のクラス別のスキーマ属性](lync-server-2013-schema-attributes-by-class.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-105">For the classes associated with attributes, see [Schema attributes by class in Lync Server 2013](lync-server-2013-schema-attributes-by-class.md).</span></span> <span data-ttu-id="6b2e2-106">Lync Server 2013 で新しく追加されたクラスと属性の一覧については、「 [Lync server 2013 でのスキーマの変更](lync-server-2013-schema-changes-in-lync-server-2013.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-106">For a list of classes and attributes that are new in Lync Server 2013, see [Schema changes in Lync Server 2013](lync-server-2013-schema-changes-in-lync-server-2013.md).</span></span>

<span data-ttu-id="6b2e2-107">リンクペアの属性は、転送リンクまたは戻るリンクとして指定します。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-107">Attributes that are linked pairs are specified as forward links or back links.</span></span> <span data-ttu-id="6b2e2-108">別のオブジェクトを参照する属性は、転送リンクです。最初のオブジェクトを参照する他のオブジェクトの属性は、[戻る] リンクです。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-108">An attribute that refers to another object is a forward link; the attribute of the other object that refers back to the first object is a back link.</span></span> <span data-ttu-id="6b2e2-109">前方リンクは更新可能で、戻るリンクは読み取り専用です。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-109">Forward links are updatable, while back links are read-only.</span></span>

<span data-ttu-id="6b2e2-110">一部の属性にはビットマスク値があります。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-110">Some attributes have a bit-mask value.</span></span> <span data-ttu-id="6b2e2-111">これらの属性の場合、各設定は1ビットで表され、表示される10進値はビット位置を表します。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-111">For these attributes, each setting is represented by a bit, and the displayed decimal value represents the bit position.</span></span> <span data-ttu-id="6b2e2-112">ビット位置はビット0から始まります。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-112">Bit positions start with bit 0.</span></span> <span data-ttu-id="6b2e2-113">たとえば、1 (binary) はビット0に設定され、1万 (binary) はビット4で設定されています。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-113">For example, 1 (binary) is bit 0 set and 10000 (binary) is bit 4 set.</span></span> <span data-ttu-id="6b2e2-114">各ビットはプロパティを表します。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-114">Each bit represents a property.</span></span> <span data-ttu-id="6b2e2-115">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-115">The following are some examples:</span></span>

  - <span data-ttu-id="6b2e2-116">1万 (binary) の10進数は16です (つまり、ビット4が設定されています)。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-116">10000 (binary) has a decimal value of 16 (that is, bit 4 is set).</span></span>

  - <span data-ttu-id="6b2e2-117">1億 (binary) の小数点以下の値は 256 (ビット8が設定されている) です。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-117">100000000 (binary) has a decimal value of 256 (that is, bit 8 is set).</span></span>

  - <span data-ttu-id="6b2e2-118">1100 (binary) の10進数の値は12です (つまり、ビット2と3は設定され、両方のビットで表されるプロパティは有効です)。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-118">1100 (binary) has a decimal value of 12 (that is, bits 2 and 3 are set; properties represented by both bits are enabled).</span></span>

  - <span data-ttu-id="6b2e2-119">1111000001 (binary) には、10進数の 961 (ビット0、6、7、8、および9の値が設定されています。これらの各ビットのプロパティは有効です)。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-119">1111000001 (binary) has a decimal value of 961 (that is, bits 0, 6, 7, 8, and 9 are set; properties for each of these bits are enabled).</span></span>

<div id="sectionSection0" class="section">

### <a name="schema-attributes-for-lync-server-2013"></a><span data-ttu-id="6b2e2-120">Lync Server 2013 のスキーマ属性</span><span class="sxs-lookup"><span data-stu-id="6b2e2-120">Schema Attributes for Lync Server 2013</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6b2e2-121">属性</span><span class="sxs-lookup"><span data-stu-id="6b2e2-121">Attribute</span></span></th>
<th><span data-ttu-id="6b2e2-122">説明</span><span class="sxs-lookup"><span data-stu-id="6b2e2-122">Description</span></span></th>
<th><span data-ttu-id="6b2e2-123">コメント</span><span class="sxs-lookup"><span data-stu-id="6b2e2-123">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6b2e2-124">dnsHostName</span><span class="sxs-lookup"><span data-stu-id="6b2e2-124">dnsHostName</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-125"><strong>Msrtcsip-userenabled true</strong>と<strong>msrtcsip-userenabled true の</strong>両方のサーバークラスに関連付けられている、Active Directory ドメインサービス内の既存の属性。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-125">An existing attribute in Active Directory Domain Services that is now associated with the <strong>msRTCSIP-Pool</strong> and <strong>msRTCSIP-MonitoringServer</strong> classes.</span></span> <span data-ttu-id="6b2e2-126">この属性は、プールまたは監視サーバーの完全修飾ドメイン名 (FQDN) を指定します。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-126">This attribute specifies the fully qualified domain name (FQDN) of a pool or Monitoring Server.</span></span></p>
<p><span data-ttu-id="6b2e2-127">各セグメントの有効な値は、63文字です。FQDN 全体の有効な値は、255文字です。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-127">A valid value for each segment is 63 characters; a valid value for the entire FQDN is 255 characters.</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-128">Microsoft Office Live Communications Server 2005 の新製品。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-128">New in Microsoft Office Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6b2e2-129">SourceObjectDN</span><span class="sxs-lookup"><span data-stu-id="6b2e2-129">msDS-SourceObjectDN</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-130">この属性には、このオブジェクトに対応する別のフォレストのオブジェクトの識別名 (DN) の文字列表現が含まれます。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-130">This attribute contains the string representation of the distinguished name (DN) of the object in another forest that corresponds to this object.</span></span> <span data-ttu-id="6b2e2-131">この属性は、配布グループの展開と自動参加に使用されます。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-131">This attribute is used for distribution group expansion and auto attendance.</span></span> <span data-ttu-id="6b2e2-132">この属性は、Windows Server 2003 R2 の既定の Active Directory スキーマで定義されています。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-132">This attribute is defined in the default Active Directory schema for Windows Server 2003 R2.</span></span></p>
<p><span data-ttu-id="6b2e2-133">AD DS から Windows Server 2003 R2 へのアップグレードを必要としないように、Active Directory スキーマの準備では、Windows Server 2003 スキーマがこの属性定義で拡張されます。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-133">To avoid requiring an upgrade of AD DS to Windows Server 2003 R2, Active Directory schema preparation extends the Windows Server 2003 schema with this attribute definition.</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-134">Microsoft Office Communications Server 2007 の新製品。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-134">New in Microsoft Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6b2e2-135">msExchUCVoiceMailSettings</span><span class="sxs-lookup"><span data-stu-id="6b2e2-135">msExchUCVoiceMailSettings</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-136">この複数値属性はボイスメールの設定を保持します。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-136">This multi-valued attribute holds voice mail settings.</span></span> <span data-ttu-id="6b2e2-137">この属性は、Exchange ユニファイドメッセージング (UM) と共有されます。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-137">This attribute is shared with Exchange Unified Messaging (UM).</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-138">Microsoft Lync Server 2010 の新製品です。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-138">New in Microsoft Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6b2e2-139">msExchUserHoldPolicies</span><span class="sxs-lookup"><span data-stu-id="6b2e2-139">msExchUserHoldPolicies</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-140">このマルチバリュー属性は、ユーザーに適用される保留ポリシーの識別子を保持します。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-140">This multi-value attribute holds identifiers for hold policies that apply to the user.</span></span> <span data-ttu-id="6b2e2-141">保留ポリシーは、保留中のユーザーのメールボックスアイテムを保持します。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-141">Hold policies preserve mailbox items for the user for the duration of the hold.</span></span> <span data-ttu-id="6b2e2-142">この属性は Exchange 2013 と共有されます。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-142">This attribute is shared with Exchange 2013.</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-143">Lync Server 2013 の新サービスです。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-143">New in Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6b2e2-144">Msrtcsip-userenabled true-AcpInfo</span><span class="sxs-lookup"><span data-stu-id="6b2e2-144">msRTCSIP-AcpInfo</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-145">この属性は、ユーザーに対して電話会議プロバイダーの情報を格納します。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-145">This attribute stores audio conferencing provider information for a user.</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-146">Lync Server 2010 の新サービスです。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-146">New in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6b2e2-147">Msrtcsip-userenabled true-ApplicationDestination</span><span class="sxs-lookup"><span data-stu-id="6b2e2-147">msRTCSIP-ApplicationDestination</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-148">この属性は、アプリケーションの連絡先に対して信頼されているサービスエントリを指します。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-148">This attribute points to the trusted service entry for the application contact.</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-149">Microsoft Office Communications Server 2007 R2 の新製品。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-149">New in Microsoft Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6b2e2-150">Msrtcsip-userenabled true-ApplicationList</span><span class="sxs-lookup"><span data-stu-id="6b2e2-150">msRTCSIP-ApplicationList</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-151">この属性には、アプリケーションサーバー上でホストされているアプリケーションの一覧が含まれます。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-151">This attribute contains a list of hosted applications on the application server.</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-152">Office Communications Server 2007 R2 の新製品。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-152">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6b2e2-153">Msrtcsip-userenabled true-ApplicationOptions</span><span class="sxs-lookup"><span data-stu-id="6b2e2-153">msRTCSIP-ApplicationOptions</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-154">この属性は、アプリケーションの連絡先のオプションを指定します。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-154">This attribute specifies the options for the application contact.</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-155">Office Communications Server 2007 R2 の新製品。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-155">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6b2e2-156">Msrtcsip-userenabled true-ApplicationPrimaryLanguage</span><span class="sxs-lookup"><span data-stu-id="6b2e2-156">msRTCSIP-ApplicationPrimaryLanguage</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-157">この属性には、アプリケーションの連絡先の第一言語が含まれます。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-157">This attribute contains the primary language for the application contact.</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-158">Office Communications Server 2007 R2 の新製品。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-158">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6b2e2-159">Msrtcsip-userenabled true-ApplicationSecondaryLanguages</span><span class="sxs-lookup"><span data-stu-id="6b2e2-159">msRTCSIP-ApplicationSecondaryLanguages</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-160">この複数の値の属性には、アプリケーションの連絡先のセカンダリ言語が含まれています。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-160">This multiple value attribute contains the secondary languages for the application contact.</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-161">Office Communications Server 2007 R2 の新製品。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-161">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6b2e2-162">Msrtcsip-userenabled true-ApplicationServerBL</span><span class="sxs-lookup"><span data-stu-id="6b2e2-162">msRTCSIP-ApplicationServerBL</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-163">この属性には、このプールに属しているアプリケーションサーバーの一覧が含まれます。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-163">This attribute contains a list of application servers that belong to this pool.</span></span> <span data-ttu-id="6b2e2-164">このバックリンク属性への対応する前方リンクは<strong>Msrtcsip-userenabled true Serverpoollink</strong>です。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-164">The corresponding forward link to this back link attribute is <strong>msRTCSIP-ApplicationServerPoolLink</strong>.</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-165">Office Communications Server 2007 R2 の新製品。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-165">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6b2e2-166">Msrtcsip-userenabled true-ApplicationServerPoolLink</span><span class="sxs-lookup"><span data-stu-id="6b2e2-166">msRTCSIP-ApplicationServerPoolLink</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-167">この属性は、このアプリケーションサーバーが属しているプールを指します。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-167">This attribute points to the pool to which this application server belongs.</span></span> <span data-ttu-id="6b2e2-168">これは、転送リンクです。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-168">This is the forward link.</span></span> <span data-ttu-id="6b2e2-169">対応する後方リンクは、 <strong>Msrtcsip-userenabled true Serverbl</strong>です。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-169">The corresponding backward link is <strong>msRTCSIP-ApplicationServerBL</strong>.</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-170">Office Communications Server 2007 R2 の新製品。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-170">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6b2e2-171">Msrtcsip-userenabled true-アーカイブの既定値 (廃止)</span><span class="sxs-lookup"><span data-stu-id="6b2e2-171">msRTCSIP-ArchiveDefault (obsolete)</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="6b2e2-172">Live Communications Server 2005 の新サービスです。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-172">New in Live Communications Server 2005.</span></span></p>
<p><span data-ttu-id="6b2e2-173">Office Communications Server 2007 で廃止されます。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-173">Obsolete in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6b2e2-174">Msrtcsip-userenabled true-アーカイブ Defaultflags (廃止)</span><span class="sxs-lookup"><span data-stu-id="6b2e2-174">msRTCSIP-ArchiveDefaultFlags (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-175">この属性は、すべてのユーザーの通信をアーカイブするために、フォレストの境界内でグローバルな既定値を指定します。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-175">This attribute specifies the global default within the forest boundary for archiving all user communications.</span></span> <span data-ttu-id="6b2e2-176">これは、アーカイブエージェントレイヤーによって適用されます。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-176">This is enforced by the archiving agent layer.</span></span> <span data-ttu-id="6b2e2-177">この属性の値の範囲は、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-177">The range of values for this attribute is as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="6b2e2-178"><strong>TRUE</strong>: すべてのユーザーをアーカイブする</span><span class="sxs-lookup"><span data-stu-id="6b2e2-178"><strong>TRUE</strong>: Archive all users</span></span></p></li>
<li><p><span data-ttu-id="6b2e2-179"><strong>FALSE</strong>: すべてのユーザーをアーカイブしない</span><span class="sxs-lookup"><span data-stu-id="6b2e2-179"><strong>FALSE</strong>: Do not archive all users</span></span></p></li>
</ul>
<p><span data-ttu-id="6b2e2-180">この属性は、フォレストの境界内でのグローバルコントロールであり、内部ネットワーク内でのユーザーの通信はどのようにアーカイブされますか。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-180">This attribute globally controls, within the forest boundary, how user communications within an internal network are archived.</span></span></p>
<p><span data-ttu-id="6b2e2-181"><strong>Live Communications Server 2005 の動作 (現在は廃止)</strong></span><span class="sxs-lookup"><span data-stu-id="6b2e2-181"><strong>Live Communications Server 2005 behavior (now retired)</strong></span></span></p>
<p><span data-ttu-id="6b2e2-182">この属性の値の範囲は、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-182">The range of values for this attribute is as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="6b2e2-183">0: メッセージ本文をアーカイブする [ビット 0]</span><span class="sxs-lookup"><span data-stu-id="6b2e2-183">0: Archive the message body [bit 0]</span></span></p></li>
<li><p><span data-ttu-id="6b2e2-184">1: メッセージ本文をアーカイブしない [ビット 0]</span><span class="sxs-lookup"><span data-stu-id="6b2e2-184">1: Do not archive the message body [bit 0]</span></span></p></li>
</ul>
<p><span data-ttu-id="6b2e2-185"><strong>Office Communications Server 2007 の動作</strong></span><span class="sxs-lookup"><span data-stu-id="6b2e2-185"><strong>Office Communications Server 2007 behavior</strong></span></span></p>
<p><span data-ttu-id="6b2e2-186">この属性の値の範囲は、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-186">The range of values for this attribute is as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="6b2e2-187">0: ArchiveFederationDefaultWithoutBody (廃止)</span><span class="sxs-lookup"><span data-stu-id="6b2e2-187">0: ArchiveFederationDefaultWithoutBody (retired)</span></span></p></li>
<li><p><span data-ttu-id="6b2e2-188">1-2: アーカイブ内部通信</span><span class="sxs-lookup"><span data-stu-id="6b2e2-188">1-2: ArchiveInternalCommunications</span></span></p></li>
<li><p><span data-ttu-id="6b2e2-189">3-4: ArchiveFederatedCommunications</span><span class="sxs-lookup"><span data-stu-id="6b2e2-189">3-4: ArchiveFederatedCommunications</span></span></p></li>
<li><p><span data-ttu-id="6b2e2-190">5: RecordPresenceRegistrations</span><span class="sxs-lookup"><span data-stu-id="6b2e2-190">5: RecordPresenceRegistrations</span></span></p></li>
<li><p><span data-ttu-id="6b2e2-191">6: RecordIMCallDetails</span><span class="sxs-lookup"><span data-stu-id="6b2e2-191">6: RecordIMCallDetails</span></span></p></li>
<li><p><span data-ttu-id="6b2e2-192">7: RecordGroupIMCallDetails</span><span class="sxs-lookup"><span data-stu-id="6b2e2-192">7: RecordGroupIMCallDetails</span></span></p></li>
<li><p><span data-ttu-id="6b2e2-193">8: RecordFileTransferInstances</span><span class="sxs-lookup"><span data-stu-id="6b2e2-193">8: RecordFileTransferInstances</span></span></p></li>
<li><p><span data-ttu-id="6b2e2-194">9: RecordAudioCallDetails</span><span class="sxs-lookup"><span data-stu-id="6b2e2-194">9: RecordAudioCallDetails</span></span></p></li>
<li><p><span data-ttu-id="6b2e2-195">10: RecordVideoCallDetails</span><span class="sxs-lookup"><span data-stu-id="6b2e2-195">10: RecordVideoCallDetails</span></span></p></li>
<li><p><span data-ttu-id="6b2e2-196">11: RecordRemoteAssistanceCallDetails</span><span class="sxs-lookup"><span data-stu-id="6b2e2-196">11: RecordRemoteAssistanceCallDetails</span></span></p></li>
<li><p><span data-ttu-id="6b2e2-197">12: RecordApplicationSharingDetails</span><span class="sxs-lookup"><span data-stu-id="6b2e2-197">12: RecordApplicationSharingDetails</span></span></p></li>
<li><p><span data-ttu-id="6b2e2-198">13: Record会議のインスタンス化</span><span class="sxs-lookup"><span data-stu-id="6b2e2-198">13: RecordMeetingInstantiations</span></span></p></li>
<li><p><span data-ttu-id="6b2e2-199">14: Record会議の結合</span><span class="sxs-lookup"><span data-stu-id="6b2e2-199">14: RecordMeetingJoins</span></span></p></li>
<li><p><span data-ttu-id="6b2e2-200">15: RecordDataJoins</span><span class="sxs-lookup"><span data-stu-id="6b2e2-200">15: RecordDataJoins</span></span></p></li>
<li><p><span data-ttu-id="6b2e2-201">16: RecordAVJoins</span><span class="sxs-lookup"><span data-stu-id="6b2e2-201">16: RecordAVJoins</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="6b2e2-202">Live Communications Server 2005 の新サービスです。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-202">New in Live Communications Server 2005.</span></span></p>
<p><span data-ttu-id="6b2e2-203">Lync Server 2010 では廃止されています。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-203">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6b2e2-204">Msrtcsip-userenabled true-ArchiveFederationDefault (廃止)</span><span class="sxs-lookup"><span data-stu-id="6b2e2-204">msRTCSIP-ArchiveFederationDefault (obsolete)</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="6b2e2-205">Live Communications Server 2005 の新サービスです。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-205">New in Live Communications Server 2005.</span></span></p>
<p><span data-ttu-id="6b2e2-206">Office Communications Server 2007 で廃止されます。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-206">Obsolete in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6b2e2-207">Msrtcsip-userenabled true-ArchiveFederationDefaultFlags (廃止)</span><span class="sxs-lookup"><span data-stu-id="6b2e2-207">msRTCSIP-ArchiveFederationDefaultFlags (obsolete)</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="6b2e2-208">Live Communications Server 2005 の新サービスです。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-208">New in Live Communications Server 2005.</span></span></p>
<p><span data-ttu-id="6b2e2-209">Office Communications Server 2007 で廃止されます。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-209">Obsolete in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6b2e2-210">Msrtcsip-userenabled true-ArchivingEnabled</span><span class="sxs-lookup"><span data-stu-id="6b2e2-210">msRTCSIP-ArchivingEnabled</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-211">この属性は、1人のユーザーの通信がアーカイブされるかどうかを制御するためのビットフィールドとして使用される整数です。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-211">This attribute is an integer used as a bit field to control whether a single user’s communications are to be archived.</span></span> <span data-ttu-id="6b2e2-212">このコントロールは、アーカイブエージェントレイヤーによって適用されます。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-212">This control is enforced by the archiving agent layer.</span></span> <span data-ttu-id="6b2e2-213">グローバルカタログのレプリケーション用にマークされています。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-213">It is marked for global catalog replication.</span></span></p>
<p><span data-ttu-id="6b2e2-214">この属性の範囲は、1人のユーザーまたは連絡先によって異なります。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-214">The scope of this attribute is specific to a single user or contact.</span></span> <span data-ttu-id="6b2e2-215">Lync Server の有効な値 (および関連するビット位置) は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-215">The valid values (and associated bit positions) in Lync Server are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="6b2e2-216">0: アーカイブしない (ビットセットなし)</span><span class="sxs-lookup"><span data-stu-id="6b2e2-216">0: Do not archive (no bit set)</span></span></p></li>
<li><p><span data-ttu-id="6b2e2-217">1: 廃止 (ビット位置 0)</span><span class="sxs-lookup"><span data-stu-id="6b2e2-217">1: Retired (bit position 0)</span></span></p></li>
<li><p><span data-ttu-id="6b2e2-218">2: 廃止 (ビット位置 1)</span><span class="sxs-lookup"><span data-stu-id="6b2e2-218">2: Retired (bit position 1)</span></span></p></li>
<li><p><span data-ttu-id="6b2e2-219">4: 内部通信をアーカイブする (ビット位置 2)</span><span class="sxs-lookup"><span data-stu-id="6b2e2-219">4: Archive internal communications (bit position 2)</span></span></p></li>
<li><p><span data-ttu-id="6b2e2-220">8: フェデレーション通信をアーカイブする (ビット位置 3)</span><span class="sxs-lookup"><span data-stu-id="6b2e2-220">8: Archive federated communications (bit position 3)</span></span></p></li>
</ul>
<p><span data-ttu-id="6b2e2-221">Live Communications Server 2005 で以前に有効になっていた値は、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-221">Previously valid values in Live Communications Server 2005 are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="6b2e2-222">0: Msrtcsip-userenabled true によって定義された既定値を使用します。これは、次の優先順位で、<strong>アーカイブの既定</strong>と<strong>msrtcsip-userenabled true フェデレーション</strong>によって定義されます。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-222">0:Use the default value defined by <strong>msRTCSIP-ArchiveDefault</strong> and <strong>msRTCSIP-ArchiveFederation</strong> in this order of precedence:</span></span></p>
<ul>
<li><p><span data-ttu-id="6b2e2-223">1: アーカイブ</span><span class="sxs-lookup"><span data-stu-id="6b2e2-223">1: Archive</span></span></p></li>
<li><p><span data-ttu-id="6b2e2-224">2: アーカイブしない</span><span class="sxs-lookup"><span data-stu-id="6b2e2-224">2: Do not archive</span></span></p></li>
<li><p><span data-ttu-id="6b2e2-225">3: メッセージ本文を含まないアーカイブ</span><span class="sxs-lookup"><span data-stu-id="6b2e2-225">3: Archive without the message body</span></span></p></li>
</ul></li>
</ul></td>
<td><p><span data-ttu-id="6b2e2-226">Live Communications Server 2005 の新サービスです。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-226">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6b2e2-227">Msrtcsip-userenabled true-ArchivingServerData (廃止)</span><span class="sxs-lookup"><span data-stu-id="6b2e2-227">msRTCSIP-ArchivingServerData (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-228">この属性は将来使用するために予約されています。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-228">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-229">Lync Server 2010 では廃止されています。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-229">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6b2e2-230">Msrtcsip-userenabled true-ArchivingServerVersion (廃止)</span><span class="sxs-lookup"><span data-stu-id="6b2e2-230">msRTCSIP-ArchivingServerVersion (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-231">この属性は、アーカイブサービスのバージョンを定義します。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-231">This attribute defines the version of the Archiving service.</span></span> <span data-ttu-id="6b2e2-232">この属性は、各公式の製品リリースによってインクリメントされる monotonously の増加整数型です。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-232">This attribute is a monotonously increasing integer type that increments with each official product release.</span></span> <span data-ttu-id="6b2e2-233">有効な値は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-233">The possible valid values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="6b2e2-234">未定義: Live Communications Server 2003</span><span class="sxs-lookup"><span data-stu-id="6b2e2-234">Undefined: Live Communications Server 2003</span></span></p>
<p><span data-ttu-id="6b2e2-235">                 Live Communications Server 2005</span><span class="sxs-lookup"><span data-stu-id="6b2e2-235">                 Live Communications Server 2005</span></span></p>
<p><span data-ttu-id="6b2e2-236">                 Live Communications Server 2005 SP1</span><span class="sxs-lookup"><span data-stu-id="6b2e2-236">                 Live Communications Server 2005 with SP1</span></span></p></li>
<li><p><span data-ttu-id="6b2e2-237">3: Office Communications Server 2007</span><span class="sxs-lookup"><span data-stu-id="6b2e2-237">3: Office Communications Server 2007</span></span></p></li>
<li><p><span data-ttu-id="6b2e2-238">4: Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="6b2e2-238">4: Office Communications Server 2007 R2</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="6b2e2-239">Office Communications Server 2007 の新製品。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-239">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="6b2e2-240">Lync Server 2010 では廃止されています。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-240">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6b2e2-241">Msrtcsip-userenabled true-BackEndServer</span><span class="sxs-lookup"><span data-stu-id="6b2e2-241">msRTCSIP-BackEndServer</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-242">この属性は、プールのバックエンドサーバーの FQDN を指定します。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-242">This attribute specifies the FQDN of the Back End Server of the pool.</span></span> <span data-ttu-id="6b2e2-243">バックエンドサーバーは1つのプールにつき1つしか存在できないため、これは単一値の属性です。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-243">Because there can only be a single Back End Server per pool, this is a single-valued attribute.</span></span></p>
<p><span data-ttu-id="6b2e2-244">各セグメントの有効な値は、63文字です。FQDN 全体の有効な値は、255文字です。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-244">The valid value for each segment is 63 characters; the valid value for the entire FQDN is 255 characters.</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-245">Live Communications Server 2005 の新サービスです。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-245">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6b2e2-246">Msrtcsip-userenabled true-ConferenceDirectoryHomePool</span><span class="sxs-lookup"><span data-stu-id="6b2e2-246">msRTCSIP-ConferenceDirectoryHomePool</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-247">この属性には、会議ディレクトリをホストするプールの識別子が含まれます。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-247">This attribute contains the identifier of the pool that hosts the conference directory.</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-248">Office Communications Server 2007 R2 の新製品。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-248">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6b2e2-249">Msrtcsip-userenabled true-ConferenceDirectoryId</span><span class="sxs-lookup"><span data-stu-id="6b2e2-249">msRTCSIP-ConferenceDirectoryId</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-250">この属性には、会議ディレクトリの識別子が含まれます。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-250">This attribute contains the identifier of a conference directory.</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-251">Office Communications Server 2007 R2 の新製品。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-251">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6b2e2-252">Msrtcsip-userenabled true-ConferenceDirectoryTargetPool</span><span class="sxs-lookup"><span data-stu-id="6b2e2-252">msRTCSIP-ConferenceDirectoryTargetPool</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-253">この属性には、会議ディレクトリの移動先のプールの識別子が含まれています。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-253">This attribute contains the identifier of the pool to which the conference directory is being moved.</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-254">Office Communications Server 2007 R2 の新製品。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-254">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6b2e2-255">Msrtcsip-userenabled true-既定値</span><span class="sxs-lookup"><span data-stu-id="6b2e2-255">msRTCSIP-Default</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-256">このブール値の属性は、電話の使用状況が既定で使用されているかどうかを定義します。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-256">This Boolean attribute defines whether the phone usage is a default usage.</span></span> <span data-ttu-id="6b2e2-257">この属性が<strong>TRUE</strong>に設定されている場合、電話の使用状況は既定で使用されているため、管理者は削除できません。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-257">If this attribute is set to <strong>TRUE</strong>, the phone usage is a default usage and cannot be deleted by the administrator.</span></span> <span data-ttu-id="6b2e2-258">この属性が<strong>FALSE</strong>に設定されている場合、使用法は削除できます。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-258">If this attribute is set to <strong>FALSE</strong>, the usage can be deleted.</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-259">Office Communications Server 2007 の新製品。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-259">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6b2e2-260">Msrtcsip-userenabled true-DefaultCWAExternalURL</span><span class="sxs-lookup"><span data-stu-id="6b2e2-260">msRTCSIP-DefaultCWAExternalURL</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-261">この属性は、組織外のユーザーの Communicator Web Access URL を識別します。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-261">This attribute identifies the Communicator Web Access URL for users who are outside the organization.</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-262">Office Communications Server 2007 R2 の新製品。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-262">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6b2e2-263">Msrtcsip-userenabled true-DefaultCWAInternalURL</span><span class="sxs-lookup"><span data-stu-id="6b2e2-263">msRTCSIP-DefaultCWAInternalURL</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-264">この属性は、組織内のユーザーの Communicator Web Access URL を識別します。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-264">This attribute identifies the Communicator Web Access URL for users who are inside the organization.</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-265">Office Communications Server 2007 R2 の新製品。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-265">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6b2e2-266">Msrtcsip-userenabled true-DefaultLocationProfileLink (廃止)</span><span class="sxs-lookup"><span data-stu-id="6b2e2-266">msRTCSIP-DefaultLocationProfileLink (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-267">この単一値の属性には、割り当てられた位置情報プロファイルクラスオブジェクトの識別名 (DN) が含まれます。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-267">This single-valued attribute contains the distinguished name (DN) of a location profile class object assigned to it.</span></span></p>
<p><span data-ttu-id="6b2e2-268">転送リンク:<strong>リンク ID 11036</strong></span><span class="sxs-lookup"><span data-stu-id="6b2e2-268">Forward link: <strong>Link ID 11036</strong></span></span></p>
<p><span data-ttu-id="6b2e2-269">対応する後方リンクは、 <strong>msrtcsip-userenabled true-ServerReferenceBL</strong>です。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-269">The corresponding backward link is <strong>msRTCSIP-ServerReferenceBL</strong>.</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-270">Lync Server 2010 では廃止されています。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-270">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6b2e2-271">Msrtcsip-userenabled true-DefaultPolicy (廃止)</span><span class="sxs-lookup"><span data-stu-id="6b2e2-271">msRTCSIP-DefaultPolicy (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-272">このブール属性は、ポリシーが既定のポリシーであるかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-272">This Boolean attribute specifies whether the policy is a default policy.</span></span> <span data-ttu-id="6b2e2-273">ポリシーは、 <strong>TRUE</strong>に設定されている場合の既定のポリシーです。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-273">The policy is a default policy when set to <strong>TRUE</strong>.</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-274">Office Communications Server 2007 の新製品</span><span class="sxs-lookup"><span data-stu-id="6b2e2-274">New in Office Communications Server 2007</span></span></p>
<p><span data-ttu-id="6b2e2-275">Lync Server 2010 では廃止されています。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-275">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6b2e2-276">Msrtcsip-userenabled true-DefaultRouteToEdgeProxy (廃止)</span><span class="sxs-lookup"><span data-stu-id="6b2e2-276">msRTCSIP-DefaultRouteToEdgeProxy (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-277">この属性は、アクセスエッジサービスを実行しているエッジサーバーの FQDN (access edge サービスを実行しているサーバーのプールに直接アクセスできるか、またはハードウェアロードバランサー) を指定します。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-277">This attribute specifies the FQDN of either the Edge Server running the Access Edge service, if it can be accessed directly, or of the hardware load balancer for a pool of servers running Access Edge service.</span></span> <span data-ttu-id="6b2e2-278">アクセスエッジサービスを実行しているサーバーが1つ以上のディレクターを介してのみアクセスできる場合、この属性は、ディレクタープールを提供するディレクターまたはハードウェアロードバランサーのポート番号を指定します。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-278">If the servers running Access Edge service can be accessed only through one or more Directors, this attribute specifies the FQDN and, optionally, the port number of the Director or of the hardware load balancer serving a Director pool.</span></span></p>
<p><span data-ttu-id="6b2e2-279">各セグメントの有効な値は、63文字です。FQDN 全体の有効な値は、255文字です。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-279">The valid value for each segment is 63 characters; the valid value for the entire FQDN is 255 characters.</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-280">Live Communications Server 2005 の新サービスです。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-280">New in Live Communications Server 2005.</span></span></p>
<p><span data-ttu-id="6b2e2-281">Lync Server 2010 では廃止されています。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-281">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6b2e2-282">Msrtcsip-userenabled true-DefaultRouteToEdgeProxyPort (廃止)</span><span class="sxs-lookup"><span data-stu-id="6b2e2-282">msRTCSIP-DefaultRouteToEdgeProxyPort (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-283">この属性は、アクセスエッジサービスを実行しているサーバーへの接続に使用するポート番号を表します。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-283">This attribute represents the port number that should be used to connect to the server running Access Edge service.</span></span></p>
<p><span data-ttu-id="6b2e2-284">有効な値は、使用するポートを指定する整数値です。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-284">The valid value is an integer value specifying the port to be used.</span></span> <span data-ttu-id="6b2e2-285">既定値は5061です。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-285">The default value is 5061.</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-286">Live Communications Server 2005 の新サービスです。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-286">New in Live Communications Server 2005.</span></span></p>
<p><span data-ttu-id="6b2e2-287">Lync Server 2010 では廃止されています。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-287">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6b2e2-288">Msrtcsip-userenabled true-DefPresenceSubscriptionTimeout (廃止)</span><span class="sxs-lookup"><span data-stu-id="6b2e2-288">msRTCSIP-DefPresenceSubscriptionTimeout (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-289">この属性は、既定のプレゼンスサブスクリプションのタイムアウト期間を表します。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-289">This attribute represents the default presence subscription time-out period.</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-290">Lync Server 2010 では廃止されています。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-290">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6b2e2-291">Msrtcsip-userenabled true-DefRegistrationTimeout (廃止)</span><span class="sxs-lookup"><span data-stu-id="6b2e2-291">msRTCSIP-DefRegistrationTimeout (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-292">この属性は、既定の登録タイムアウトウィンドウを表します。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-292">This attribute represents the default registration time-out window.</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-293">Lync Server 2010 では廃止されています。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-293">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6b2e2-294">Msrtcsip-userenabled true-DefRoamingDataSubscriptionTimeout (廃止)</span><span class="sxs-lookup"><span data-stu-id="6b2e2-294">msRTCSIP-DefRoamingDataSubscriptionTimeout (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-295">この属性は、既定のローミングデータサブスクリプションのタイムアウトウィンドウを表します。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-295">This attribute represents the default roaming data subscription time-out window.</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-296">Lync Server 2010 では廃止されています。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-296">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6b2e2-297">msRTCSIP-DeploymentLocator</span><span class="sxs-lookup"><span data-stu-id="6b2e2-297">msRTCSIP-DeploymentLocator</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-298">この属性は、分割ドメイントポロジで使用され、完全修飾ドメイン名 (FQDN) が含まれます。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-298">This attribute is used in a split domain topology and contains a fully qualified domain name (FQDN).</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-299">Lync Server 2010 の新サービスです。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-299">New in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6b2e2-300">Msrtcsip-userenabled true-Description (廃止)</span><span class="sxs-lookup"><span data-stu-id="6b2e2-300">msRTCSIP-Description (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-301">この単一値の UNICODE 文字列属性には、この電話ルートまたは正規化ルールのわかりやすい説明が含まれています。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-301">This single-valued UNICODE string attribute contains a friendly description of this phone route or normalization rule.</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-302">Office Communications Server 2007 の新製品。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-302">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="6b2e2-303">Lync Server 2010 では廃止されています。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-303">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6b2e2-304">Msrtcsip-userenabled true-DomainData</span><span class="sxs-lookup"><span data-stu-id="6b2e2-304">msRTCSIP-DomainData</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-305">この属性は将来使用するために予約されています。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-305">This attribute is reserved for future use.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6b2e2-306">Msrtcsip-userenabled true-ドメイン名</span><span class="sxs-lookup"><span data-stu-id="6b2e2-306">msRTCSIP-DomainName</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-307">この属性は、レジストラー用に構成されているドメインを表します。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-307">This attribute represents a domain configured for the Registrar.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6b2e2-308">Msrtcsip-userenabled true-EdgeProxyData</span><span class="sxs-lookup"><span data-stu-id="6b2e2-308">msRTCSIP-EdgeProxyData</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-309">この属性は将来使用するために予約されています。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-309">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-310">Live Communications Server 2005 の新サービスです。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-310">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6b2e2-311">Msrtcsip-userenabled true-EdgeProxyFQDN</span><span class="sxs-lookup"><span data-stu-id="6b2e2-311">msRTCSIP-EdgeProxyFQDN</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-312">この属性は、Access Edge サービスを実行しているサーバーの FQDN を指定します。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-312">This attribute specifies the FQDN of the server running Access Edge service.</span></span></p>
<p><span data-ttu-id="6b2e2-313">各セグメントの有効な値は、63文字です。FQDN 全体の有効な値は、255文字です。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-313">The valid value for each segment is 63 characters; the valid value for the entire FQDN is 255 characters.</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-314">Live Communications Server 2005 の新サービスです。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-314">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6b2e2-315">Msrtcsip-userenabled true-EnableBestEffortNotify (廃止)</span><span class="sxs-lookup"><span data-stu-id="6b2e2-315">msRTCSIP-EnableBestEffortNotify (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-316">この属性は、クライアントからの SUBSCRIBE 要求に応じて、サーバーが NOTIFY 要求ではなく、ベストエフォート通知 (BENOTIFY) 要求を生成するかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-316">This attribute controls whether a server generates a Best Effort NOTIFY (BENOTIFY) request, instead of a NOTIFY request, in response to a SUBSCRIBE request from a client.</span></span> <span data-ttu-id="6b2e2-317">BENOTIFY は、通常の通知要求の代わりにサーバーが BENOTIFY 要求を生成する、サブスクライブ通知ハンドシェイクのパフォーマンス強化された拡張機能です。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-317">BENOTIFY is a performance-enhancing extension to the subscribe notification handshake where the server generates BENOTIFY requests, instead of regular NOTIFY requests.</span></span> <span data-ttu-id="6b2e2-318">パフォーマンスの利点は、通知要求によって、BENOTIFY 要求でクライアントから 200 OK 応答が要求されないことです。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-318">The performance benefit is that a BENOTIFY request does not require a 200 OK response from the client as the NOTIFY request does.</span></span></p>
<p><span data-ttu-id="6b2e2-319">有効な値は、 <strong>TRUE</strong>または<strong>FALSE</strong>です。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-319">The valid values are <strong>TRUE</strong> or <strong>FALSE</strong>.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="6b2e2-320">Live Communications Server 2003 は BENOTIFY 要求をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-320">Live Communications Server 2003 does not support BENOTIFY requests.</span></span> <span data-ttu-id="6b2e2-321">Live communications server の2005とサードパーティのサーバーで実行されている Live Communications Server 2003 server API で記述されたサーバーアプリケーションと相互運用するには、BENOTIFY 要求の値を<STRONG>FALSE</STRONG>に設定して無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-321">To interoperate with server applications written with the Live Communications Server 2003 server API running on Live Communications Server 2005 and third-party servers, BENOTIFY requests can be disabled by setting its value to <STRONG>FALSE</STRONG>.</span></span> <span data-ttu-id="6b2e2-322">現在、BENOTIFY は IETF (インターネットエンジニアリングタスクフォース) SIP 標準化プロセスの一部ではありません。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-322">BENOTIFY is not currently part of the IETF (Internet Engineering Task Force) SIP standardization process.</span></span>


</div></td>
<td><p><span data-ttu-id="6b2e2-323">Live Communications Server 2005 の新サービスです。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-323">New in Live Communications Server 2005.</span></span></p>
<p><span data-ttu-id="6b2e2-324">Lync Server 2010 では廃止されています。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-324">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6b2e2-325">Msrtcsip-userenabled true-EnableFederation (廃止)</span><span class="sxs-lookup"><span data-stu-id="6b2e2-325">msRTCSIP-EnableFederation (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-326">この属性は、IT 管理者が他の組織のユーザーとの通信を許可するかどうかを構成するために使用するグローバルスイッチです。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-326">This attribute is a global switch that IT administrators use to configure whether users are allowed to communicate with users from other organizations.</span></span> <span data-ttu-id="6b2e2-327">管理者が個々のユーザーの<strong>FederationEnabled</strong>属性を上書きできるようにします。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-327">It enables an administrator to overwrite an individual user’s <strong>FederationEnabled</strong> attribute.</span></span> <span data-ttu-id="6b2e2-328">この属性は、ワーム、ウイルス、または企業の標的となる攻撃によって発生する可能性があるインターネット攻撃から内部ネットワークを保護するために役立ちます。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-328">This attribute can be useful to help protect the internal network from Internet attacks that may be caused by worms, viruses, or targeted attacks on the company.</span></span></p>
<p><span data-ttu-id="6b2e2-329">有効な値 (および関連するビット位置) は、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-329">The valid values (and associated bit positions) are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="6b2e2-330">1: パブリック IM 接続を有効にする (ビット位置 0)</span><span class="sxs-lookup"><span data-stu-id="6b2e2-330">1: Enabled for public IM connectivity (bit position 0)</span></span></p></li>
<li><p><span data-ttu-id="6b2e2-331">2: 予約済み (ビット位置 1)</span><span class="sxs-lookup"><span data-stu-id="6b2e2-331">2: Reserved (bit position 1)</span></span></p></li>
<li><p><span data-ttu-id="6b2e2-332">4: 予約済み (ビット位置 2)</span><span class="sxs-lookup"><span data-stu-id="6b2e2-332">4: Reserved (bit position 2)</span></span></p></li>
<li><p><span data-ttu-id="6b2e2-333">8: 予約済み (ビット位置 3)</span><span class="sxs-lookup"><span data-stu-id="6b2e2-333">8: Reserved (bit position 3)</span></span></p></li>
<li><p><span data-ttu-id="6b2e2-334">16: リモート通話コントロールが有効になっている [Telephony] (ビット位置 4)</span><span class="sxs-lookup"><span data-stu-id="6b2e2-334">16: Remote call control Enabled [Telephony] (bit position 4)</span></span></p></li>
<li><p><span data-ttu-id="6b2e2-335">64: AllowOrganizeMeetingWithAnonymousParticipants (ユーザーが会議に匿名ユーザーを招待することを許可する (ビット位置 6)</span><span class="sxs-lookup"><span data-stu-id="6b2e2-335">64: AllowOrganizeMeetingWithAnonymousParticipants (allow users to invite anonymous users to meetings (bit position 6)</span></span></p></li>
<li><p><span data-ttu-id="6b2e2-336">128: UCEnabled (ユニファイドコミュニケーションのためのユーザーの有効化) (ビット位置 7)</span><span class="sxs-lookup"><span data-stu-id="6b2e2-336">128: UCEnabled (enable users for unified communications) (bit position 7)</span></span></p></li>
<li><p><span data-ttu-id="6b2e2-337">256: EnabledForEnhancedPresence (ユーザーにパブリック IM 接続を有効にする) (ビット位置 8)</span><span class="sxs-lookup"><span data-stu-id="6b2e2-337">256: EnabledForEnhancedPresence (enable user for public IM connectivity) (bit position 8)</span></span></p></li>
<li><p><span data-ttu-id="6b2e2-338">512: RemoteCallControlDualMode (ビット位置 9)</span><span class="sxs-lookup"><span data-stu-id="6b2e2-338">512: RemoteCallControlDualMode (bit position 9)</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="6b2e2-339">Live Communications Server 2005 の新サービスです。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-339">New in Live Communications Server 2005.</span></span></p>
<p><span data-ttu-id="6b2e2-340">Lync Server 2010 では廃止されています。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-340">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6b2e2-341">Msrtcsip-userenabled true-EnterpriseServices</span><span class="sxs-lookup"><span data-stu-id="6b2e2-341">msRTCSIP-EnterpriseServices</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-342">この属性は、エンタープライズサービスが指定されたサーバーに読み込まれているかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-342">This attribute indicates whether the Enterprise Services are loaded on the given server.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6b2e2-343">Msrtcsip-userenabled true-ExtensionData</span><span class="sxs-lookup"><span data-stu-id="6b2e2-343">msRTCSIP-ExtensionData</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-344">この属性は将来使用するために予約されています。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-344">This attribute is reserved for future use.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6b2e2-345">Msrtcsip-userenabled true-ExternalAccessCode</span><span class="sxs-lookup"><span data-stu-id="6b2e2-345">msRTCSIP-ExternalAccessCode</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-346">この属性には、外部アクセスのダイヤルコードが含まれています。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-346">This attribute contains the dial code for external access.</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-347">Office Communications Server 2007 R2 の新製品。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-347">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6b2e2-348">Msrtcsip-userenabled true-FederationEnabled</span><span class="sxs-lookup"><span data-stu-id="6b2e2-348">msRTCSIP-FederationEnabled</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-349">この属性は、1人のユーザーがフェデレーションを有効にしているかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-349">This attribute controls whether a single user is enabled for federation.</span></span> <span data-ttu-id="6b2e2-350">エンタープライズサービスレイヤーによって適用されます。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-350">It is enforced by the Enterprise Services layer.</span></span> <span data-ttu-id="6b2e2-351">グローバルカタログのレプリケーション用にマークされています。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-351">It is marked for global catalog replication.</span></span></p>
<p><span data-ttu-id="6b2e2-352">有効な値は、 <strong>TRUE</strong>または<strong>FALSE</strong>です。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-352">The valid values are <strong>TRUE</strong> or <strong>FALSE</strong>.</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-353">Live Communications Server 2005 の新サービスです。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-353">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6b2e2-354">Msrtcsip-userenabled true-FrontEndServers</span><span class="sxs-lookup"><span data-stu-id="6b2e2-354">msRTCSIP-FrontEndServers</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-355">この属性は、プールに関連付けられたすべての Enterprise Edition サーバーのドメイン名の複数値を持つ一覧です。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-355">This attribute is a multi-valued list of the domain names of all Enterprise Edition servers associated with a pool.</span></span></p>
<p><span data-ttu-id="6b2e2-356">戻るリンク:<strong>リンク ID 11023</strong></span><span class="sxs-lookup"><span data-stu-id="6b2e2-356">Back link: <strong>Link ID 11023</strong></span></span></p>
<p><span data-ttu-id="6b2e2-357">この戻るリンクへの対応する前方リンクは<strong>msrtcsip-userenabled true の住所</strong>です。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-357">The corresponding forward link to this back link is <strong>msRTCSIP-PoolAddress</strong>.</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-358">Live Communications Server 2005 の新サービスです。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-358">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6b2e2-359">Msrtcsip-userenabled true-ゲートウェイ (廃止)</span><span class="sxs-lookup"><span data-stu-id="6b2e2-359">msRTCSIP-Gateways (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-360">この複数値文字列属性には、ゲートウェイとポート (ゲートウェイごと) の一覧が含まれています。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-360">This multi-valued string attribute contains a list of gateways and ports (per gateway).</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-361">Lync Server 2010 では廃止されています。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-361">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6b2e2-362">Msrtcsip-userenabled true-GlobalSettingsData (廃止)</span><span class="sxs-lookup"><span data-stu-id="6b2e2-362">msRTCSIP-GlobalSettingsData (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-363">この属性には、名前と値のペアが格納されます。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-363">This attribute stores name:value pairs.</span></span> <span data-ttu-id="6b2e2-364">既に定義された名前: 値のペアは、プレゼンス設定の [<strong>ポーリングを許可</strong>する] に対応しています。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-364">The already-defined name:value pair is for the <strong>allow polling for presence</strong> setting.</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-365">Lync Server 2010 では廃止されています。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-365">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6b2e2-366">Msrtcsip-userenabled true-GroupingID</span><span class="sxs-lookup"><span data-stu-id="6b2e2-366">msRTCSIP-GroupingID</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-367">この属性は、アドレス帳のエントリをグループ化するために使用されるグループの一意の識別子です。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-367">This attribute is a unique identifier of a group that is used to group address book entries.</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-368">Lync Server 2010 の新サービスです。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-368">New in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6b2e2-369">Msrtcsip-userenabled true-HomeServer (廃止)</span><span class="sxs-lookup"><span data-stu-id="6b2e2-369">msRTCSIP-HomeServer (obsolete)</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="6b2e2-370">最新のライブ通信サーバー 2003 (使用されていません)。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-370">New in Live Communications Server 2003 (not used).</span></span></p>
<p><span data-ttu-id="6b2e2-371">現在、ライブ通信サーバー2005で廃止されています。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-371">Obsolete in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6b2e2-372">Msrtcsip-userenabled true-HomeServerString (廃止)</span><span class="sxs-lookup"><span data-stu-id="6b2e2-372">msRTCSIP-HomeServerString (obsolete)</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="6b2e2-373">Live Communications Server 2003 の新サービスです。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-373">New in Live Communications Server 2003.</span></span></p>
<p><span data-ttu-id="6b2e2-374">現在、ライブ通信サーバー2005で廃止されています。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-374">Obsolete in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6b2e2-375">Msrtcsip-userenabled true-ホームユーザー (廃止)</span><span class="sxs-lookup"><span data-stu-id="6b2e2-375">msRTCSIP-HomeUsers (obsolete)</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="6b2e2-376">最新のライブ通信サーバー 2003 (使用されていません)。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-376">New in Live Communications Server 2003 (not used).</span></span></p>
<p><span data-ttu-id="6b2e2-377">現在、ライブ通信サーバー2005で廃止されています。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-377">Obsolete in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6b2e2-378">Msrtcsip-userenabled true-InternetAccessEnabled</span><span class="sxs-lookup"><span data-stu-id="6b2e2-378">msRTCSIP-InternetAccessEnabled</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-379">この属性は、1人のユーザーが外部ユーザーアクセスを有効にしているかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-379">This attribute controls whether a single user is enabled for outside user access.</span></span> <span data-ttu-id="6b2e2-380">エンタープライズサービスレイヤーによって適用されます。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-380">It is enforced by the Enterprise Services layer.</span></span> <span data-ttu-id="6b2e2-381">グローバルカタログのレプリケーション用にマークされています。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-381">It is marked for global catalog replication.</span></span></p>
<p><span data-ttu-id="6b2e2-382">有効な値は、 <strong>TRUE</strong>または<strong>FALSE</strong>です。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-382">The valid values are <strong>TRUE</strong> or <strong>FALSE</strong>.</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-383">Live Communications Server 2005 の新サービスです。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-383">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6b2e2-384">Msrtcsip-userenabled true-IsMaster (廃止)</span><span class="sxs-lookup"><span data-stu-id="6b2e2-384">msRTCSIP-IsMaster (obsolete)</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="6b2e2-385">最新のライブコミュニケーションサーバー2003</span><span class="sxs-lookup"><span data-stu-id="6b2e2-385">New in Live Communications Server 2003</span></span></p>
<p><span data-ttu-id="6b2e2-386">現在、ライブ通信サーバー2005で廃止されています。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-386">Obsolete in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6b2e2-387">Msrtcsip-userenabled true ライン</span><span class="sxs-lookup"><span data-stu-id="6b2e2-387">msRTCSIP-Line</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-388">この単一値の属性には、Lync for telephony によって使用されるデバイス ID (SIP URI またはユーザーが制御する電話の TEL URI のいずれか) が含まれます。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-388">This single-valued attribute contains the device ID (either the SIP URI or the TEL URI of the phone the user controls) used by Lync for telephony.</span></span> <span data-ttu-id="6b2e2-389">この属性はグローバルカタログのレプリケーション用にマークされ、インデックスが作成されます。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-389">This attribute is marked for Global Catalog replication and is indexed.</span></span> <span data-ttu-id="6b2e2-390">ユーザーがエンタープライズ Voip を有効にしている場合、この属性には、ユーザーの電話番号の E.i 正規化されたバージョンが格納されます。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-390">If a user is enabled for Enterprise Voice, this attribute stores the E.164 normalized version of the user’s phone number.</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-391">Microsoft Office Live Communications Server 2005 SP1 の新製品</span><span class="sxs-lookup"><span data-stu-id="6b2e2-391">New in Microsoft Office Live Communications Server 2005 with SP1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6b2e2-392">Msrtcsip-userenabled true</span><span class="sxs-lookup"><span data-stu-id="6b2e2-392">msRTCSIP-LineServer</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-393">この単一値属性には、CSTA-SIP ゲートウェイサーバーの SIP URI が含まれています。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-393">This single-valued attribute contains the SIP URI of the CSTA-SIP gateway server.</span></span> <span data-ttu-id="6b2e2-394">この属性はグローバルカタログのレプリケーション用にマークされていますが、インデックスは作成されません。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-394">This attribute is marked for Global Catalog replication but is not indexed.</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-395">Microsoft Office Live Communications Server 2005 SP1 の新製品</span><span class="sxs-lookup"><span data-stu-id="6b2e2-395">New in Microsoft Office Live Communications Server 2005 with SP1</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6b2e2-396">Msrtcsip-userenabled true-LocalNormalizationData (廃止)</span><span class="sxs-lookup"><span data-stu-id="6b2e2-396">msRTCSIP-LocalNormalizationData (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-397">この属性は将来使用するために予約されています。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-397">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-398">Office Communications Server 2007 の新製品。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-398">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="6b2e2-399">Lync Server 2010 では廃止されています。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-399">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6b2e2-400">Msrtcsip-userenabled true-Localnormallinks (廃止)</span><span class="sxs-lookup"><span data-stu-id="6b2e2-400">msRTCSIP-LocalNormalizationLinks (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-401">この複数値属性には、この場所プロファイルに関連付けられたローカル正規化識別名 (DN) の一覧が含まれています。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-401">This multi-valued attribute contains a list of local normalization distinguished names (DN) associated with this location profile.</span></span> <span data-ttu-id="6b2e2-402">この属性の型は、DN バイナリです。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-402">The type of this attribute is a DN binary.</span></span> <span data-ttu-id="6b2e2-403">位置情報プロファイルとローカル正規化ルールの間には一対多のリレーションシップがあります。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-403">There is a one-to-many relationship between location profile and local normalization rules.</span></span> <span data-ttu-id="6b2e2-404">ローカル正規化 DNs の一覧の順序は、管理者が指定した順序で維持する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-404">The ordering of the list of local normalization DNs must be maintained in the order specified by the administrator.</span></span> <span data-ttu-id="6b2e2-405">順序の保持は、DN バイナリのバイナリ部分によって管理されます。これにより、注文インデックスが指定されます。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-405">The preservation of order is maintained by the binary portion of the DN binary, which specifies the order index.</span></span></p>
<p><span data-ttu-id="6b2e2-406">転送リンク:<strong>リンク ID 11034</strong></span><span class="sxs-lookup"><span data-stu-id="6b2e2-406">Forward link: <strong>Link ID 11034</strong></span></span></p>
<p><span data-ttu-id="6b2e2-407">この転送リンク属性への対応する "戻る" リンクは、 <strong>msrtcsip-userenabled true (プロファイル Ebl)</strong>です。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-407">The corresponding back link to this forward link attribute is <strong>msRTCSIP-LocationProfileBL</strong>.</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-408">Office Communications Server 2007 の新製品。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-408">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="6b2e2-409">Lync Server 2010 では廃止されています。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-409">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6b2e2-410">Msrtcsip-userenabled true-LocalNormalizationOptions</span><span class="sxs-lookup"><span data-stu-id="6b2e2-410">msRTCSIP-LocalNormalizationOptions</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-411">この属性には、正規化ルールのオプションの一覧が含まれています。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-411">This attribute contains a list of options for the normalization rule.</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-412">Office Communications Server 2007 R2 の新製品。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-412">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6b2e2-413">Msrtcsip-userenabled true-LocationName (廃止)</span><span class="sxs-lookup"><span data-stu-id="6b2e2-413">msRTCSIP-LocationName (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-414">この単一値の属性には、このプロファイルが表す場所を示す場所プロファイルのフレンドリ名が含まれています。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-414">This single-valued attribute contains a friendly name for the location profile that indicates which location this profile represents.</span></span> <span data-ttu-id="6b2e2-415">複数の場所プロファイルが存在する可能性があるため、管理者はさまざまなプロファイルを区別するための方法が必要です。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-415">Because there can be multiple location profiles, the administrator needs a way to distinguish between different profiles.</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-416">Office Communications Server 2007 の新製品。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-416">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="6b2e2-417">Lync Server 2010 では廃止されています。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-417">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6b2e2-418">Msrtcsip-userenabled true-locationProfileBL (廃止)</span><span class="sxs-lookup"><span data-stu-id="6b2e2-418">msRTCSIP-locationProfileBL (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-419">この複数値属性には、場所プロファイルの識別名の一覧が含まれています。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-419">This multi-valued attribute contains a list of location profile distinguished names.</span></span> <span data-ttu-id="6b2e2-420">この属性は、1つ以上の位置情報プロファイルへの戻るリンクを指定します。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-420">This attribute specifies the back link to one or more location profiles.</span></span></p>
<p><span data-ttu-id="6b2e2-421">戻るリンク:<strong>リンク ID 11035</strong></span><span class="sxs-lookup"><span data-stu-id="6b2e2-421">Back link: <strong>Link ID 11035</strong></span></span></p>
<p><span data-ttu-id="6b2e2-422">この属性は、forward link <strong>msrtcsip-userenabled true-Localnormalのリンク</strong>に対応します。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-422">This attribute corresponds to the forward link <strong>msRTCSIP-LocalNormalizationLinks</strong>.</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-423">Office Communications Server 2007 の新製品。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-423">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="6b2e2-424">Lync Server 2010 では廃止されています。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-424">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6b2e2-425">Msrtcsip-userenabled true-LocationProfileData (廃止)</span><span class="sxs-lookup"><span data-stu-id="6b2e2-425">msRTCSIP-LocationProfileData (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-426">この属性は将来使用するために予約されています。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-426">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-427">Office Communications Server 2007 の新製品。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-427">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="6b2e2-428">Lync Server 2010 では廃止されています。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-428">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6b2e2-429">Msrtcsip-userenabled true-LocationProfileOptions</span><span class="sxs-lookup"><span data-stu-id="6b2e2-429">msRTCSIP-LocationProfileOptions</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-430">この属性には、位置情報プロファイルのオプションが含まれています。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-430">This attribute contains the options for the location profile.</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-431">Office Communications Server 2007 R2 の新製品。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-431">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6b2e2-432">Msrtcsip-userenabled true-MappingContact</span><span class="sxs-lookup"><span data-stu-id="6b2e2-432">msRTCSIP-MappingContact</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-433">この複数値属性は、アプリケーションの連絡先の一覧を保持します。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-433">This multiple-value attribute holds a list of application contacts.</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-434">Office Communications Server 2007 R2 の新製品。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-434">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6b2e2-435">Msrtcsip-userenabled true-MappingLocation</span><span class="sxs-lookup"><span data-stu-id="6b2e2-435">msRTCSIP-MappingLocation</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-436">この複数値属性は、位置情報プロファイルの一覧を保持します。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-436">This multiple-value attribute holds a list of location profiles.</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-437">Office Communications Server 2007 R2 の新製品。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-437">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6b2e2-438">Msrtcsip-userenabled true-Maxnumoutスタンド Ingsearchperserver (廃止)</span><span class="sxs-lookup"><span data-stu-id="6b2e2-438">msRTCSIP-MaxNumOutstandingSearchPerServer (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-439">この属性は、サーバーあたりの未処理の検索要求の最大数を表します。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-439">This attribute represents the maximum number of outstanding search requests per server.</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-440">Lync Server 2010 では廃止されています。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-440">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6b2e2-441">Msrtcsip-userenabled true-MaxNumSubscriptionsPerUser (廃止)</span><span class="sxs-lookup"><span data-stu-id="6b2e2-441">msRTCSIP-MaxNumSubscriptionsPerUser (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-442">この属性は、ユーザーごとのサブスクリプションの最大数を表します。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-442">The attribute represents the maximum number of subscriptions per user.</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-443">Lync Server 2010 では廃止されています。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-443">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6b2e2-444">Msrtcsip-userenabled true-MaxPresenceSubscriptionTimeout (廃止)</span><span class="sxs-lookup"><span data-stu-id="6b2e2-444">msRTCSIP-MaxPresenceSubscriptionTimeout (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-445">この属性は、サブスクリプションの最大タイムアウトウィンドウを表します。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-445">This attribute represents the maximum subscription time-out window.</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-446">Lync Server 2010 では廃止されています。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-446">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6b2e2-447">Msrtcsip-userenabled true-MaxRegistrationsTimeout (廃止)</span><span class="sxs-lookup"><span data-stu-id="6b2e2-447">msRTCSIP-MaxRegistrationsTimeout (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-448">この属性は、登録の最大タイムアウトウィンドウを表します。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-448">This attribute represents the maximum registrations time-out window.</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-449">Lync Server 2010 では廃止されています。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-449">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6b2e2-450">Msrtcsip-userenabled true-MaxRoamingDataSubscriptionTimeout (廃止)</span><span class="sxs-lookup"><span data-stu-id="6b2e2-450">msRTCSIP-MaxRoamingDataSubscriptionTimeout (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-451">この属性は、最大ローミングデータサブスクリプションのタイムアウトウィンドウを表します。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-451">This attribute represents the maximum roaming data subscriptions time-out window.</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-452">Lync Server 2010 では廃止されています。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-452">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6b2e2-453">Msrtcsip-userenabled true-MCUData</span><span class="sxs-lookup"><span data-stu-id="6b2e2-453">msRTCSIP-MCUData</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-454">この属性は将来使用するために予約されています。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-454">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-455">Office Communications Server 2007 の新製品。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-455">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6b2e2-456">Msrtcsip-userenabled true-MCUFactoryAddress</span><span class="sxs-lookup"><span data-stu-id="6b2e2-456">msRTCSIP-MCUFactoryAddress</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-457">この属性は、属している multipoint control unit (MCU) ファクトリへのリンクを指定するコンピュータークラスの下のサービス制御ポイント属性です。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-457">This attribute is a service control point attribute under the computer class that specifies a link back to the multipoint control unit (MCU) Factory to which it belongs.</span></span> <span data-ttu-id="6b2e2-458">このサービス制御ポイントと属性は、Microsoft MCU ごとに作成されます。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-458">This service control point and attribute is created for every Microsoft MCU.</span></span> <span data-ttu-id="6b2e2-459">各 Microsoft MCU は、プールレベルの設定を取得するために、所属するプールのバックエンドサーバーを見つける必要があります。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-459">Each Microsoft MCU must find the Back End Server of the pool to which it belongs, in order to retrieve pool-level settings from it.</span></span></p>
<p><span data-ttu-id="6b2e2-460">この属性の値は、MCU ファクトリの識別名 (DN) です。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-460">The value of this attribute is the distinguished name (DN) of the MCU Factory.</span></span> <span data-ttu-id="6b2e2-461">これは単一値の属性であり、グローバルカタログのレプリケーション用にマークされています。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-461">This is a single-valued attribute and marked for global catalog replication.</span></span></p>
<p><span data-ttu-id="6b2e2-462">転送リンク:<strong>リンク ID 11026</strong></span><span class="sxs-lookup"><span data-stu-id="6b2e2-462">Forward link: <strong>Link ID 11026</strong></span></span></p>
<p><span data-ttu-id="6b2e2-463">この転送リンク属性への対応する "戻る" リンクは、 <strong>Msrtcsip-userenabled true MCUServers</strong>です。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-463">The corresponding back link to this forward link attribute is <strong>msRTCSIP-MCUServers</strong>.</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-464">Office Communications Server 2007 の新製品。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-464">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6b2e2-465">Msrtcsip-userenabled true-MCUFactoryData</span><span class="sxs-lookup"><span data-stu-id="6b2e2-465">msRTCSIP-MCUFactoryData</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-466">これは、複数の文字列で予約された属性です。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-466">This is a multi-string reserved attribute.</span></span> <span data-ttu-id="6b2e2-467">この属性に格納される設定は、name = value のペアとして表されます。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-467">Settings stored in this attribute are represented as name=value pairs.</span></span> <span data-ttu-id="6b2e2-468">現在定義されている name = value のペア:</span><span class="sxs-lookup"><span data-stu-id="6b2e2-468">Currently defined name=value pairs are:</span></span></p>
<ul>
<li><p><span data-ttu-id="6b2e2-469">FactoryURL = &lt;URL&gt;</span><span class="sxs-lookup"><span data-stu-id="6b2e2-469">FactoryURL = &lt;URL&gt;</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="6b2e2-470">Office Communications Server 2007 の新製品。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-470">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6b2e2-471">Msrtcsip-userenabled true-MCUFactoryPath</span><span class="sxs-lookup"><span data-stu-id="6b2e2-471">msRTCSIP-MCUFactoryPath</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-472">これは、プールに関連付けられた単一の MCU ファクトリの識別名 (DN) を含む単一値の属性です。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-472">This is a single-valued attribute that contains the distinguished name (DN) of a single MCU factory associated with a pool.</span></span></p>
<p><span data-ttu-id="6b2e2-473">転送リンク:<strong>リンク ID 11024</strong></span><span class="sxs-lookup"><span data-stu-id="6b2e2-473">Forward link: <strong>Link ID 11024</strong></span></span></p>
<p><span data-ttu-id="6b2e2-474">この転送リンク属性への対応する "戻る" リンクは<strong>msrtcsip-userenabled true の住所</strong>です。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-474">The corresponding back link to this forward link attribute is <strong>msRTCSIP-PoolAddresses</strong>.</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-475">Office Communications Server 2007 の新製品。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-475">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6b2e2-476">Msrtcsip-userenabled true-MCUFactoryProviderID</span><span class="sxs-lookup"><span data-stu-id="6b2e2-476">msRTCSIP-MCUFactoryProviderID</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-477">この属性は、MCU ファクトリプロバイダーの GUID を指定する単一値の文字列です。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-477">This attribute is a single-valued string that specifies the GUID of the MCU factory provider.</span></span> <span data-ttu-id="6b2e2-478">MCU ファクトリプロセスは、GUID 値に基づいて、この MCU 型をサービスするかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-478">Based on the GUID value, the MCU factory process determines whether to service this MCU type.</span></span> <span data-ttu-id="6b2e2-479">GUID 値が<strong>{F0810510-424F-46ef-84FE-6CC720DF1791}</strong>の場合は、MCU ファクトリプロセス (既定では Lync Server で利用可能) によって処理されます。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-479">If the GUID value is <strong>{F0810510-424F-46ef-84FE-6CC720DF1791}</strong>, then the MCU factory process (available by default in Lync Server) will process it.</span></span> <span data-ttu-id="6b2e2-480">他の GUID 値の場合、MCU ファクトリプロセスは MCU の種類を処理しません。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-480">For any other GUID value, the MCU factory process will not service the MCU type.</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-481">Office Communications Server 2007 の新製品。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-481">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6b2e2-482">msrtcsip-userenabled true-mcuser</span><span class="sxs-lookup"><span data-stu-id="6b2e2-482">msRTCSIP-MCUServers</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-483">この属性は、複数値を持つ識別名 (DN) の一覧です。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-483">This attribute is a multi-valued list of distinguished names (DN).</span></span> <span data-ttu-id="6b2e2-484">この属性には、この MCU ファクトリに関連付けられている同じ種類とベンダーのすべての MCU サーバーの一覧が含まれます。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-484">This attribute contains a list of all MCU servers of the same type and vendor associated with this MCU factory.</span></span> <span data-ttu-id="6b2e2-485">各セグメントの有効な値は、63文字です。FQDN 全体の有効な値は、255文字です。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-485">The valid value for each segment is 63 characters; the valid value for the entire FQDN is 255 characters.</span></span></p>
<p><span data-ttu-id="6b2e2-486">戻るリンク: リンク ID 11027</span><span class="sxs-lookup"><span data-stu-id="6b2e2-486">Back link: Link ID 11027</span></span></p>
<p><span data-ttu-id="6b2e2-487">この戻るリンクへの対応する前方リンクは<strong>Msrtcsip-userenabled true MCUFactoryAddress</strong>です。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-487">The corresponding forward link to this back link is <strong>msRTCSIP-MCUFactoryAddress</strong>.</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-488">Office Communications Server 2007 の新製品。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-488">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6b2e2-489">Msrtcsip-userenabled true-MCUType</span><span class="sxs-lookup"><span data-stu-id="6b2e2-489">msRTCSIP-MCUType</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-490">この属性は、MCU が処理できる媒体を指定する単一値の文字列です。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-490">This attribute is a single-valued string that specifies the medium the MCU can handle.</span></span></p>
<p><span data-ttu-id="6b2e2-491">サポートされている有効な形式は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-491">Supported valid types are:</span></span></p>
<ul>
<li><p><span data-ttu-id="6b2e2-492">会議</span><span class="sxs-lookup"><span data-stu-id="6b2e2-492">meeting</span></span></p></li>
<li><p><span data-ttu-id="6b2e2-493">オーディオ-ビデオ</span><span class="sxs-lookup"><span data-stu-id="6b2e2-493">audio-video</span></span></p></li>
<li><p><span data-ttu-id="6b2e2-494">チャット</span><span class="sxs-lookup"><span data-stu-id="6b2e2-494">chat</span></span></p></li>
<li><p><span data-ttu-id="6b2e2-495">電話-conf</span><span class="sxs-lookup"><span data-stu-id="6b2e2-495">phone-conf</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="6b2e2-496">Office Communications Server 2007 の新製品。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-496">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6b2e2-497">Msrtcsip-userenabled true-MCUVendor</span><span class="sxs-lookup"><span data-stu-id="6b2e2-497">msRTCSIP-MCUVendor</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-498">この属性は、MCU ベンダーの名前を指定する単一値の文字列です。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-498">This attribute is a single-valued string that specifies an MCU vendor’s name.</span></span> <span data-ttu-id="6b2e2-499">Microsoft のすべての Mcu は、この属性を<strong>Microsoft Corporation</strong>に指定します。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-499">All Microsoft MCUs will specify this attribute to be <strong>Microsoft Corporation</strong>.</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-500">Office Communications Server 2007 の新製品。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-500">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6b2e2-501">Msrtcsip-userenabled true-会議フラグ (廃止)</span><span class="sxs-lookup"><span data-stu-id="6b2e2-501">msRTCSIP-MeetingFlags (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-502">この属性は、すべてのユーザーまたは連絡先オブジェクトでグローバルに有効になるさまざまな会議オプションを定義します。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-502">This attribute defines different meeting options that are enabled globally for all users or contact objects.</span></span> <span data-ttu-id="6b2e2-503">この属性は、整数型のビットマスク値です。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-503">This attribute is a bit-mask value of integer type.</span></span></p>
<p><span data-ttu-id="6b2e2-504">有効な値 (および関連するビット位置) は、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-504">The valid values (and associated bit positions) are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="6b2e2-505">0: AllowOrganizeMeetingWithAnonymousParticipants が None (ユーザーが会議に匿名ユーザーを招待することを許可しない) (bits は設定されません)</span><span class="sxs-lookup"><span data-stu-id="6b2e2-505">0: AllowOrganizeMeetingWithAnonymousParticipants is None (do not allow users to invite anonymous users to meetings) (no bits set)</span></span></p></li>
<li><p><span data-ttu-id="6b2e2-506">4: AllowOrganizeMeetingWithAnonymousParticipants はすべてのユーザー (すべてのユーザーが会議に匿名ユーザーを招待することを許可します) (ビット位置 2)</span><span class="sxs-lookup"><span data-stu-id="6b2e2-506">4: AllowOrganizeMeetingWithAnonymousParticipants is Everyone (allow all users to invite anonymous users to meetings) (bit position 2)</span></span></p></li>
<li><p><span data-ttu-id="6b2e2-507">8: AllowOrganizeMeetingWithAnonymousParticipants は UsePerUserSetting (ユーザーごとの設定に基づいてユーザーが会議に匿名ユーザーを招待できるようにします) (ビット位置 3)</span><span class="sxs-lookup"><span data-stu-id="6b2e2-507">8: AllowOrganizeMeetingWithAnonymousParticipants is UsePerUserSetting (allow users to invite anonymous users to meetings based on per user setting) (bit position 3)</span></span></p></li>
<li><p><span data-ttu-id="6b2e2-508">16: Userperuser会議ポリシー (会議ポリシーはユーザーごとに定義されます) (ビット位置 4)</span><span class="sxs-lookup"><span data-stu-id="6b2e2-508">16: UserPerUserMeetingPolicy (meeting policy is defined per user) (bit position 4)</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="6b2e2-509">Office Communications Server 2007 の新製品。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-509">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="6b2e2-510">Lync Server 2010 では廃止されています。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-510">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6b2e2-511">Msrtcsip-userenabled true-会議ポリシー (廃止)</span><span class="sxs-lookup"><span data-stu-id="6b2e2-511">msRTCSIP-MeetingPolicy (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-512">この属性は、管理者がこのユーザーに割り当てたポリシーの識別名 (DN) を単一値の属性として指定します。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-512">This attribute specifies the distinguished name (DN) of the policy the administrator has assigned for this user as a single-valued attribute.</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-513">Office Communications Server 2007 の新製品。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-513">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="6b2e2-514">Lync Server 2010 では廃止されています。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-514">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6b2e2-515">Msrtcsip-userenabled true-MinPresenceSubscriptionTimeout (廃止)</span><span class="sxs-lookup"><span data-stu-id="6b2e2-515">msRTCSIP-MinPresenceSubscriptionTimeout (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-516">この属性は、最小プレゼンスサブスクリプションのタイムアウトウィンドウを表します。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-516">This attribute represents the minimum presence subscription time-out window.</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-517">Lync Server 2010 では廃止されています。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-517">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6b2e2-518">Msrtcsip-userenabled true-MinRegistrationTimeout (廃止)</span><span class="sxs-lookup"><span data-stu-id="6b2e2-518">msRTCSIP-MinRegistrationTimeout (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-519">この属性は、最小登録タイムアウトウィンドウを表します。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-519">This attribute represents the minimum registration time-out window.</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-520">Office Communications Server 2007 の新製品。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-520">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="6b2e2-521">Lync Server 2010 では廃止されています。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-521">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6b2e2-522">Msrtcsip-userenabled true-MinRoamingDataSubscriptionTimeout (廃止)</span><span class="sxs-lookup"><span data-stu-id="6b2e2-522">msRTCSIP-MinRoamingDataSubscriptionTimeout (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-523">この属性は、最小のローミングデータサブスクリプションのタイムアウトウィンドウを表します。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-523">This attribute represents the minimum roaming data subscription time-out window.</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-524">Office Communications Server 2007 の新製品。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-524">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="6b2e2-525">Lync Server 2010 では廃止されています。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-525">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6b2e2-526">Msrtcsip-userenabled true-MirrorBackEndServer</span><span class="sxs-lookup"><span data-stu-id="6b2e2-526">msRTCSIP-MirrorBackEndServer</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-527">この属性は、フロントエンドプールによって使用されるミラー化された SQL Server バックエンドを格納するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-527">This attribute is used to store the mirrored SQL Server backend used by the Front End pool.</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-528">Lync Server 2013 の新サービスです。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-528">New in Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6b2e2-529">Msrtcsip-userenabled true-MobilityFlags</span><span class="sxs-lookup"><span data-stu-id="6b2e2-529">msRTCSIP-MobilityFlags</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-530">この属性には、モビリティー設定を定義するオプションとフラグが含まれています。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-530">This attribute contains options and flags that define mobility settings.</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-531">Office Communications Server 2007 R2 の新製品。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-531">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6b2e2-532">Msrtcsip-userenabled true-MobilityPolicy</span><span class="sxs-lookup"><span data-stu-id="6b2e2-532">msRTCSIP-MobilityPolicy</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-533">この属性には、モビリティーポリシーオブジェクトの DN が含まれます。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-533">This attribute contains the DN for a mobility policy object.</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-534">Office Communications Server 2007 R2 の新製品。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-534">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6b2e2-535">Msrtcsip-userenabled true-NumDevicesPerUser (廃止)</span><span class="sxs-lookup"><span data-stu-id="6b2e2-535">msRTCSIP-NumDevicesPerUser (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-536">この属性は、ユーザーが SIP コミュニケーションに登録してプレゼンスをサブスクライブできるデバイスの許可された数を表します。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-536">This attribute represents the allowed number of devices on which a user can register for SIP communications and subscribe to presence.</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-537">Office Communications Server 2007 の新製品。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-537">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="6b2e2-538">Lync Server 2010 では廃止されています。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-538">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6b2e2-539">Msrtcsip-userenabled true-OptionFlags</span><span class="sxs-lookup"><span data-stu-id="6b2e2-539">msRTCSIP-OptionFlags</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-540">この属性は、ユーザーまたは連絡先オブジェクトに対して有効になるオプションを指定します。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-540">This attribute specifies the options that are enabled for the user or contact object.</span></span> <span data-ttu-id="6b2e2-541">この属性は、integer 型のビットマスク値です。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-541">This attribute is a bit-mask value of type integer.</span></span> <span data-ttu-id="6b2e2-542">各オプションは1ビットで表されます。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-542">Each option is represented by a bit.</span></span> <span data-ttu-id="6b2e2-543">この属性は、グローバルカタログのレプリケーション用にマークされます。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-543">This attribute is marked for global catalog replication.</span></span></p>
<p><span data-ttu-id="6b2e2-544">有効な値 (および関連するビット位置) は、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-544">The valid values (and associated bit positions) are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="6b2e2-545">1: パブリックインスタントメッセージング (IM) 接続を有効にします (ビット位置 0)。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-545">1: Enabled for public instant messaging (IM) connectivity (bit position 0)</span></span></p></li>
<li><p><span data-ttu-id="6b2e2-546">2: 予約済み (ビット位置 1)</span><span class="sxs-lookup"><span data-stu-id="6b2e2-546">2: Reserved (bit position 1)</span></span></p></li>
<li><p><span data-ttu-id="6b2e2-547">4: 予約済み (ビット位置 2)</span><span class="sxs-lookup"><span data-stu-id="6b2e2-547">4: Reserved (bit position 2)</span></span></p></li>
<li><p><span data-ttu-id="6b2e2-548">8: 予約済み (ビット位置 3)</span><span class="sxs-lookup"><span data-stu-id="6b2e2-548">8: Reserved (bit position 3)</span></span></p></li>
<li><p><span data-ttu-id="6b2e2-549">16: リモート通話コントロールが有効になっている [Telephony] (ビット位置 4)</span><span class="sxs-lookup"><span data-stu-id="6b2e2-549">16: Remote call control Enabled [Telephony] (bit position 4)</span></span></p></li>
<li><p><span data-ttu-id="6b2e2-550">64: AllowOrganizeMeetingWithAnonymousParticipants (ユーザーが会議に匿名ユーザーを招待することを許可する (ビット位置 6)</span><span class="sxs-lookup"><span data-stu-id="6b2e2-550">64: AllowOrganizeMeetingWithAnonymousParticipants (allow users to invite anonymous users to meetings (bit position 6)</span></span></p></li>
<li><p><span data-ttu-id="6b2e2-551">128: UCEnabled (UC でのユーザーの有効化) (ビット位置 7)</span><span class="sxs-lookup"><span data-stu-id="6b2e2-551">128: UCEnabled (enable users for UC) (bit position 7)</span></span></p></li>
<li><p><span data-ttu-id="6b2e2-552">256: EnabledForEnhancedPresence (ユーザーにパブリック IM 接続を有効にする) (ビット位置 8)</span><span class="sxs-lookup"><span data-stu-id="6b2e2-552">256: EnabledForEnhancedPresence (enable user for public IM connectivity) (bit position 8)</span></span></p></li>
<li><p><span data-ttu-id="6b2e2-553">512: RemoteCallControlDualMode (ビット位置 9)</span><span class="sxs-lookup"><span data-stu-id="6b2e2-553">512: RemoteCallControlDualMode (bit position 9)</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="6b2e2-554">SP1 での最新のライブ通信サーバー2005。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-554">New in Live Communications Server 2005 with SP1.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6b2e2-555">msRTCSIP-OriginatorSID</span><span class="sxs-lookup"><span data-stu-id="6b2e2-555">msRTCSIP-OriginatorSID</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-556">この属性は、リソースおよび中央フォレストトポロジで使用され、Windows NT Server プリンシパルアカウントからのユーザーの ObjectSID が、リソースまたは中央フォレストの対応するユーザーまたは連絡先オブジェクトのこの属性にコピーされた場合に、シングルサインオンを有効にします。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-556">This attribute is used in resource and central forest topologies to enable single sign-on when a user’s ObjectSID from the Windows NT Server principal account is copied into this attribute of the corresponding user or contact object in the resource or central forest.</span></span> <span data-ttu-id="6b2e2-557">Communicator Web Access は、この属性またはユーザーの ObjectSID を使用して、AD DS 内のユーザーを検索します。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-557">Communicator Web Access searches for a user in AD DS using this attribute or the user’s ObjectSID.</span></span> <span data-ttu-id="6b2e2-558">この属性は、グローバルカタログのレプリケーション用にマークされます。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-558">This attribute is marked for global catalog replication.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6b2e2-559">Msrtcsip-userenabled true-OwnerUrn</span><span class="sxs-lookup"><span data-stu-id="6b2e2-559">msRTCSIP-OwnerUrn</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-560">この属性は、アプリケーションの連絡先の所有者の Uniform Resource Name (URN) です。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-560">This attribute is the Uniform Resource Name (URN) of the owner for an application contact.</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-561">Lync Server 2010 の新サービスです。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-561">New in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6b2e2-562">Msrtcsip-userenabled true-Pattern (廃止)</span><span class="sxs-lookup"><span data-stu-id="6b2e2-562">msRTCSIP-Pattern (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-563">この単一値文字列属性には、ダイヤル番号を E.i 形式に一致させるために使われるパターンが含まれています。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-563">This single-valued string attribute contains a pattern used for matching dial numbers into E.164 format.</span></span> <span data-ttu-id="6b2e2-564">ダイヤル番号がこのパターンと一致する場合、翻訳はダイヤルされた番号に適用されます。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-564">If the dial number matches this pattern, the translation is applied to the dialed number.</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-565">Office Communications Server 2007 の新製品。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-565">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="6b2e2-566">Lync Server 2010 では廃止されています。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-566">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6b2e2-567">Msrtcsip-userenabled true-PhoneRouteBL (廃止)</span><span class="sxs-lookup"><span data-stu-id="6b2e2-567">msRTCSIP-PhoneRouteBL (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-568">この複数値属性には、電話ルートの識別名 (DN) の一覧が含まれます。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-568">This multi-valued attribute contains a list of phone route distinguished names (DN).</span></span> <span data-ttu-id="6b2e2-569">この属性は、1つ以上の電話ルートへの戻るリンクを指定します。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-569">This attribute specifies the back link to one or more phone routes.</span></span></p>
<p><span data-ttu-id="6b2e2-570">戻るリンク:<strong>リンク ID 11033</strong></span><span class="sxs-lookup"><span data-stu-id="6b2e2-570">Back link: <strong>Link ID 11033</strong></span></span></p>
<p><span data-ttu-id="6b2e2-571">この属性は、 <strong>msrtcsip-userenabled true-RouteUsageLinks</strong>の前方リンクに対応しています。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-571">This attribute corresponds to the forward link <strong>msRTCSIP-RouteUsageLinks</strong>.</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-572">Office Communications Server 2007 の新製品。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-572">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="6b2e2-573">Lync Server 2010 では廃止されています。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-573">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6b2e2-574">Msrtcsip-userenabled true-PhoneRouteData (廃止)</span><span class="sxs-lookup"><span data-stu-id="6b2e2-574">msRTCSIP-PhoneRouteData (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-575">この属性は将来使用するために予約されています。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-575">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-576">Lync Server 2010 では廃止されています。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-576">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6b2e2-577">Msrtcsip-userenabled true-PhoneRouteName (廃止)</span><span class="sxs-lookup"><span data-stu-id="6b2e2-577">msRTCSIP-PhoneRouteName (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-578">この単一の値の UNICODE 文字列属性は、電話ルートのフレンドリ名を指定するため、管理者が簡単に参照できます。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-578">This single valued UNICODE string attribute specifies the friendly name of the phone route, so it can easily be referenced by the administrator.</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-579">Lync Server 2010 では廃止されています。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-579">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6b2e2-580">Msrtcsip-userenabled true-電話の使用データ (廃止)</span><span class="sxs-lookup"><span data-stu-id="6b2e2-580">msRTCSIP-PhoneUsageData (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-581">この属性は将来使用するために予約されています。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-581">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-582">Office Communications Server 2007 の新製品。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-582">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="6b2e2-583">Lync Server 2010 では廃止されています。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-583">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6b2e2-584">Msrtcsip-userenabled true-ポリシーのコンテンツ (廃止)</span><span class="sxs-lookup"><span data-stu-id="6b2e2-584">msRTCSIP-PolicyContent (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-585">この属性は、単一の値を持つ Unicode 文字列です。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-585">This attribute is a single-valued Unicode string.</span></span> <span data-ttu-id="6b2e2-586">この文字列属性には、XML 形式のポリシー定義が含まれています。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-586">This string attribute contains the policy definition in XML format.</span></span> <span data-ttu-id="6b2e2-587">XML スキーマ定義は、ポリシーの種類によって共通していますが、ポリシーの種類によって設定は異なります。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-587">The XML schema definition is common across different policy types, only the settings are different for each policy type.</span></span></p>
<p><span data-ttu-id="6b2e2-588">XML スキーマ定義 (XSD) は、次のように定義されます。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-588">The XML schema definition (XSD) is defined as follows:</span></span></p>
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
<td><p><span data-ttu-id="6b2e2-589">Office Communications Server 2007 の新製品。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-589">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="6b2e2-590">Lync Server 2010 では廃止されています。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-590">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6b2e2-591">Msrtcsip-userenabled true-ポリシーデータ (廃止)</span><span class="sxs-lookup"><span data-stu-id="6b2e2-591">msRTCSIP-PolicyData (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-592">この属性は将来使用するために予約されています。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-592">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-593">Office Communications Server 2007 の新製品。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-593">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="6b2e2-594">Lync Server 2010 では廃止されています。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-594">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6b2e2-595">Msrtcsip-userenabled true-PolicyType (廃止)</span><span class="sxs-lookup"><span data-stu-id="6b2e2-595">msRTCSIP-PolicyType (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-596">この単一値の Unicode 文字列属性には、ポリシー型が含まれています。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-596">This single-valued Unicode string attribute contains the policy type.</span></span> <span data-ttu-id="6b2e2-597">有効なポリシーの種類は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-597">Valid policy types are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="6b2e2-598">会議</span><span class="sxs-lookup"><span data-stu-id="6b2e2-598">meeting</span></span></p></li>
<li><p><span data-ttu-id="6b2e2-599">電話</span><span class="sxs-lookup"><span data-stu-id="6b2e2-599">telephony</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="6b2e2-600">Office Communications Server 2007 の新製品。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-600">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="6b2e2-601">Lync Server 2010 では廃止されています。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-601">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6b2e2-602">Msrtcsip-userenabled true-PoolAddress</span><span class="sxs-lookup"><span data-stu-id="6b2e2-602">msRTCSIP-PoolAddress</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-603">この属性は、コンピューターが属しているプールへのリンクを指定します。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-603">This attribute specifies a link back to the pool to which a computer belongs.</span></span> <span data-ttu-id="6b2e2-604">この属性は、コンピューターで実行されているのが標準エディションであるか、エンタープライズ版の Lync Server であるかに関係なく設定されます。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-604">This attribute is set regardless of whether the computer is running the Standard Edition or the Enterprise Edition of Lync Server.</span></span> <span data-ttu-id="6b2e2-605">この属性は、グローバルカタログのレプリケーション用にマークされます。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-605">This attribute is marked for global catalog replication.</span></span></p>
<p><span data-ttu-id="6b2e2-606">有効な値は、プールのドメイン名です。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-606">The valid value is the domain name of the pool.</span></span></p>
<p><span data-ttu-id="6b2e2-607">転送リンク:<strong>リンク ID 11022</strong></span><span class="sxs-lookup"><span data-stu-id="6b2e2-607">Forward link: <strong>Link ID 11022</strong></span></span></p>
<p><span data-ttu-id="6b2e2-608">この転送リンク属性への対応する "戻る" リンクは、 <strong>msrtcsip-userenabled true-FrontEndServers</strong>です。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-608">The corresponding back link to this forward link attribute is <strong>msRTCSIP-FrontEndServers</strong>.</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-609">Live Communications Server 2005 の新サービスです。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-609">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6b2e2-610">Msrtcsip-userenabled true-PoolAddresses</span><span class="sxs-lookup"><span data-stu-id="6b2e2-610">msRTCSIP-PoolAddresses</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-611">これは、MCU ファクトリが関連付けられているプールの識別名 (DN) の一覧を含む複数値の属性です。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-611">This is a multi-valued attribute that contains a list of the distinguished names (DN) of pools with which the MCU factory is associated.</span></span></p>
<p><span data-ttu-id="6b2e2-612">戻るリンク:<strong>リンク ID 11025</strong></span><span class="sxs-lookup"><span data-stu-id="6b2e2-612">Back link: <strong>Link ID 11025</strong></span></span></p>
<p><span data-ttu-id="6b2e2-613">この戻るリンクへの対応する前方リンクは<strong>Msrtcsip-userenabled true MCUFactoryPath</strong>です。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-613">The corresponding forward link to this back link is <strong>msRTCSIP-MCUFactoryPath</strong>.</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-614">Office Communications Server 2007 の新製品。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-614">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6b2e2-615">Msrtcsip-userenabled true-PoolData</span><span class="sxs-lookup"><span data-stu-id="6b2e2-615">msRTCSIP-PoolData</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-616">この属性は将来使用するために予約されています。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-616">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-617">SP1 での最新のライブ通信サーバー2005。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-617">New in Live Communications Server 2005 with SP1.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6b2e2-618">Msrtcsip-userenabled true-PoolDisplayName</span><span class="sxs-lookup"><span data-stu-id="6b2e2-618">msRTCSIP-PoolDisplayName</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-619">この属性は、管理コンソールによって表示されるプールの任意の名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-619">This attribute specifies an arbitrary name for a pool that is displayed by the management console.</span></span> <span data-ttu-id="6b2e2-620">この名前は管理者が変更できます。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-620">This name can be changed by the administrator.</span></span></p>
<p><span data-ttu-id="6b2e2-621">有効な値は、プールの名前を表す文字列です。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-621">The valid value is a string representing the name of a pool.</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-622">Live Communications Server 2005 の新サービスです。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-622">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6b2e2-623">Msrtcsip-userenabled true-Pooldomaqdn</span><span class="sxs-lookup"><span data-stu-id="6b2e2-623">msRTCSIP-PoolDomainFQDN</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-624">この属性は単一値文字列値です。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-624">This attribute is a single-valued string value.</span></span> <span data-ttu-id="6b2e2-625">この属性の値が指定されている場合、管理者がフロントエンドプールを作成する Active Directory ドメイン構造に準拠していない FQDN (たとえば、SIP) を使っている場合、プールのドメイン FQDN が示されます。ドメインネームシステム (DNS) 名前空間からの名前空間の分離。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-625">The value of this attribute, when present, represents the pool’s domain FQDN if the administrator wants to create a Front End pool with an FQDN that does not conform to the Active Directory domain structure in which the Front End pool is created (for example, a SIP namespace disjoined from Domain Name System (DNS) namespace).</span></span></p>
<p><span data-ttu-id="6b2e2-626">プールが存在する Active Directory ドメインとして、フロントエンドプールドメイン FQDN をドメイン名部分にマッピングすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-626">We recommend that you map the Front End pool domain FQDN to the domain name portion as the Active Directory domain in which the pool resides.</span></span> <span data-ttu-id="6b2e2-627">そのため、この属性に値が含まれていない場合、フロントエンドプールの FQDN は、 <strong>dnsHostName</strong>属性で示される Active Directory ドメイン名の構造体に既定値として設定されます。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-627">Therefore, when no value is present in this attribute, the Front End pool FQDN will default to the Active Directory domain name structure, as denoted by the <strong>dnsHostName</strong> attribute.</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-628">Office Communications Server 2007 の新製品。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-628">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6b2e2-629">Msrtcsip-userenabled true-PoolFunctionality</span><span class="sxs-lookup"><span data-stu-id="6b2e2-629">msRTCSIP-PoolFunctionality</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-630">プールに関連付けられたすべての Lync Server Enterprise Edition サーバーのドメイン名の複数値を持つリスト。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-630">A multi-valued list of the domain names of all Lync Server, Enterprise Edition servers associated with a pool.</span></span> <span data-ttu-id="6b2e2-631">Integer 型の属性は、プールがインスタントメッセージング (IM) とプレゼンス、会議に対応しているかどうかを定義します。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-631">This attribute of type integer defines whether the pool is capable of instant messaging (IM) and presence, and meetings.</span></span></p>
<p><span data-ttu-id="6b2e2-632">有効な値の型は、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-632">The possible valid value types are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="6b2e2-633">未定義: IM とプレゼンスサービス (Live Communications Server 2005 および 2003)</span><span class="sxs-lookup"><span data-stu-id="6b2e2-633">Undefined: IM and Presence Service (Live Communications Server 2005 and 2003)</span></span></p></li>
<li><p><span data-ttu-id="6b2e2-634">1: IM とプレゼンスサービス (Lync Server)</span><span class="sxs-lookup"><span data-stu-id="6b2e2-634">1: IM and Presence Service (Lync Server)</span></span></p></li>
<li><p><span data-ttu-id="6b2e2-635">2: IM、プレゼンス、会議サービス (Lync Server)</span><span class="sxs-lookup"><span data-stu-id="6b2e2-635">2: IM and Presence and Meeting Service (Lync Server)</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="6b2e2-636">Office Communications Server 2007 の新製品。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-636">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6b2e2-637">Msrtcsip-userenabled true-PoolType</span><span class="sxs-lookup"><span data-stu-id="6b2e2-637">msRTCSIP-PoolType</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-638">この属性は、サーバープールで Standard Edition server または Enterprise Edition server が実行されているかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-638">This attribute specifies whether a server pool is running Standard Edition server or Enterprise Edition server.</span></span> <span data-ttu-id="6b2e2-639">この属性は、integer 型のビットマスク値です。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-639">This attribute is a bit-mask value of type integer.</span></span> <span data-ttu-id="6b2e2-640">各オプションは1ビットで表されます。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-640">Each option is represented by a bit.</span></span></p>
<p><span data-ttu-id="6b2e2-641">有効な値 (および関連するビット位置) は、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-641">The valid values (and associated bit positions) are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="6b2e2-642">1: Standard Edition server、ホストユーザー (ビット位置 0)</span><span class="sxs-lookup"><span data-stu-id="6b2e2-642">1: Standard Edition server, hosts users (bit position 0)</span></span></p></li>
<li><p><span data-ttu-id="6b2e2-643">2: Enterprise Edition server、hosts ユーザー (ビット位置 1)</span><span class="sxs-lookup"><span data-stu-id="6b2e2-643">2: Enterprise Edition server, hosts users (bit position 1)</span></span></p></li>
<li><p><span data-ttu-id="6b2e2-644">4: 標準エディションサーバー、ホストアプリケーション (ビット位置 2)</span><span class="sxs-lookup"><span data-stu-id="6b2e2-644">4: Standard Edition server, hosts applications (bit position 2)</span></span></p></li>
<li><p><span data-ttu-id="6b2e2-645">8: Enterprise Edition server、ホストアプリケーション (ビット位置 3)</span><span class="sxs-lookup"><span data-stu-id="6b2e2-645">8: Enterprise Edition server, hosts applications (bit position 3)</span></span></p></li>
</ul>
<p><span data-ttu-id="6b2e2-646">Lync Server はアプリケーションのみをホストするプールをサポートしていないため、有効な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-646">Because Lync Server does not support pools that host only applications, the only valid values are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="6b2e2-647">5: 標準エディションサーバー、ホストユーザーとアプリケーション (ビット位置0、2)</span><span class="sxs-lookup"><span data-stu-id="6b2e2-647">5: Standard Edition server, hosts users and applications (bit positions 0 and 2)</span></span></p></li>
<li><p><span data-ttu-id="6b2e2-648">10: Enterprise Edition server、ホストユーザーとアプリケーション (ビット位置1と 3)</span><span class="sxs-lookup"><span data-stu-id="6b2e2-648">10: Enterprise Edition server, hosts users and applications (bit positions 1 and 3)</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="6b2e2-649">Live Communications Server 2005 の新サービスです。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-649">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6b2e2-650">Msrtcsip-userenabled true-PoolVersion</span><span class="sxs-lookup"><span data-stu-id="6b2e2-650">msRTCSIP-PoolVersion</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-651">この属性はプールのバージョンを定義します。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-651">This attribute defines the pool version.</span></span> <span data-ttu-id="6b2e2-652">これは、主要製品のリリースごとにインクリメントされる整数型です。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-652">It is an integer type that is incremented with each major product release.</span></span></p>
<p><span data-ttu-id="6b2e2-653">有効な値の型は、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-653">The possible valid value types are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="6b2e2-654">0: Live Communications Server 2003</span><span class="sxs-lookup"><span data-stu-id="6b2e2-654">0: Live Communications Server 2003</span></span></p></li>
<li><p><span data-ttu-id="6b2e2-655">1: Live Communications Server 2005</span><span class="sxs-lookup"><span data-stu-id="6b2e2-655">1: Live Communications Server 2005</span></span></p></li>
<li><p><span data-ttu-id="6b2e2-656">2: SP1 での Live Communications Server 2005</span><span class="sxs-lookup"><span data-stu-id="6b2e2-656">2: Live Communications Server 2005 with SP1</span></span></p></li>
<li><p><span data-ttu-id="6b2e2-657">3: Office Communications Server 2007</span><span class="sxs-lookup"><span data-stu-id="6b2e2-657">3: Office Communications Server 2007</span></span></p></li>
<li><p><span data-ttu-id="6b2e2-658">4: Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="6b2e2-658">4: Office Communications Server 2007 R2</span></span></p></li>
<li><p><span data-ttu-id="6b2e2-659">5: Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="6b2e2-659">5: Lync Server 2010</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="6b2e2-660">Live Communications Server 2005 SP1</span><span class="sxs-lookup"><span data-stu-id="6b2e2-660">Live Communications Server 2005 with SP1.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6b2e2-661">Msrtcsip-userenabled true-PresenceFlags</span><span class="sxs-lookup"><span data-stu-id="6b2e2-661">msRTCSIP-PresenceFlags</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-662">この属性には、プレゼンス設定を定義するオプションとフラグが含まれます。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-662">This attribute contains options and flags that define presence settings.</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-663">Office Communications Server 2007 R2 の新製品。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-663">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6b2e2-664">Msrtcsip-userenabled true-PresencePolicy</span><span class="sxs-lookup"><span data-stu-id="6b2e2-664">msRTCSIP-PresencePolicy</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-665">この属性には、プレゼンスポリシーオブジェクトの DN が含まれます。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-665">This attribute contains the DN for a presence policy object.</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-666">Office Communications Server 2007 R2 の新製品。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-666">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6b2e2-667">Msrtcsip-userenabled true-PrimaryHomeServer</span><span class="sxs-lookup"><span data-stu-id="6b2e2-667">msRTCSIP-PrimaryHomeServer</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-668">この属性によって、SIP メッセージングのユーザーまたは連絡先が有効になります。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-668">This attribute enables a user or contact for SIP messaging.</span></span> <span data-ttu-id="6b2e2-669">この機能は、中央フォレストのトポロジでは、ユーザーオブジェクトではなく SIP 対応の連絡先オブジェクトであるため、連絡先クラスに追加されます。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-669">It is added to the contact class because in the central forest topology, contact objects, not user objects, are SIP enabled.</span></span></p>
<p><span data-ttu-id="6b2e2-670">有効な値は、ユーザーが所属する Standard Edition server または Enterprise Edition のフロントエンドプールの DN です。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-670">The valid value is the DN of the Standard Edition server or Enterprise Edition Front End pool where a user is homed.</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-671">Live Communications Server 2005 の新サービスです。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-671">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6b2e2-672">msRTCSIP-PrimaryUserAddress</span><span class="sxs-lookup"><span data-stu-id="6b2e2-672">msRTCSIP-PrimaryUserAddress</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-673">この属性には、特定のユーザーの SIP アドレスが含まれます。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-673">This attribute contains the SIP address of a given user.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6b2e2-674">Msrtcsip-userenabled true-PrivateLine</span><span class="sxs-lookup"><span data-stu-id="6b2e2-674">msRTCSIP-PrivateLine</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-675">この属性には、プライベート回線デバイスのデバイス ID が含まれます。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-675">This attribute contains the device ID of the private line device.</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-676">Lync Server 2010 の新サービスです。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-676">New in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6b2e2-677">Msrtcsip-userenabled true-ルーティング可能</span><span class="sxs-lookup"><span data-stu-id="6b2e2-677">msRTCSIP-Routable</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-678">この属性は、Lync Server がその GRUU アドレスを使ってこのサービスにルーティングすることを許可するかどうかを決定するために使用されるブール型の属性です。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-678">This attribute is a Boolean attribute used to determine whether Lync Server is authorized to route to this service using its GRUU address.</span></span> <span data-ttu-id="6b2e2-679">この値が<strong>TRUE</strong>に設定されている場合、Lync Server はこのサービスにルーティングすることを許可されています。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-679">If this value is set to <strong>TRUE</strong>, Lync Server is authorized to route to this service.</span></span> <span data-ttu-id="6b2e2-680">この値が<strong>FALSE</strong>に設定されている場合、Lync Server はこのサービスにルーティングする権限がありません。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-680">If this value is set to <strong>FALSE</strong>, Lync Server is not authorized to route to this service.</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-681">Office Communications Server 2007 の新製品。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-681">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6b2e2-682">Msrtcsip-userenabled true-RouteUsageAttribute (廃止)</span><span class="sxs-lookup"><span data-stu-id="6b2e2-682">msRTCSIP-RouteUsageAttribute (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-683">この単一値の UNICODE 文字列属性は、電話ルートの使用を限定する属性を定義します。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-683">This single-valued UNICODE string attribute defines an attribute that qualifies the usage for a phone route.</span></span> <span data-ttu-id="6b2e2-684">電話ルートの選択は、電話ルートに割り当てられる利用属性と、発信者に許可されているポリシー使用属性の2つの要素に基づいて決定されます。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-684">Selection of a phone route is determined based on two elements: the usage attribute assigned to the phone route and the caller’s allowed policy usage attributes.</span></span> <span data-ttu-id="6b2e2-685">呼び出し元の使用が許可されている使用法属性を持つ最初の電話ルートが選択されています。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-685">The first phone route with a usage attribute that matches the caller’s allowed usage is selected.</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-686">Office Communications Server 2007 の新製品。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-686">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="6b2e2-687">Lync Server 2010 では廃止されています。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-687">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6b2e2-688">Msrtcsip-userenabled true-RouteUsageLinks (廃止)</span><span class="sxs-lookup"><span data-stu-id="6b2e2-688">msRTCSIP-RouteUsageLinks (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-689">この複数値識別名 (DN) 属性には、ルートの使用の識別名の一覧が含まれています。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-689">This multi-valued distinguished name (DN) attribute contains a list of route usage distinguished names.</span></span></p>
<p><span data-ttu-id="6b2e2-690">転送リンク:<strong>リンク ID 11032</strong></span><span class="sxs-lookup"><span data-stu-id="6b2e2-690">Forward link: <strong>Link ID 11032</strong></span></span></p>
<p><span data-ttu-id="6b2e2-691">この属性は、対応する back link <strong>msrtcsip-userenabled true-PhoneRouteBL</strong>への転送リンクです。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-691">This attribute is a forward link to the corresponding back link <strong>msRTCSIP-PhoneRouteBL</strong>.</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-692">Lync Server 2010 では廃止されています。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-692">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6b2e2-693">Msrtcsip-userenabled true-RoutingPoolDN</span><span class="sxs-lookup"><span data-stu-id="6b2e2-693">msRTCSIP-RoutingPoolDN</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-694">この属性には、この MCU または信頼されたサービスに宛てたすべての SIP トラフィックが通過する必要があるプールを指す DN が含まれています。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-694">This attribute contains the DN that points to the pool that all SIP traffic addressed to this MCU or Trusted Service must go through.</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-695">Office Communications Server 2007 R2 の新製品。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-695">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6b2e2-696">Msrtcsip-userenabled true-RuleName (廃止)</span><span class="sxs-lookup"><span data-stu-id="6b2e2-696">msRTCSIP-RuleName (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-697">この単一値の UNICODE 文字列属性は、正規化ルールのフレンドリ名を指定するため、管理者が簡単に参照できます。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-697">This single-valued UNICODE string attribute specifies the friendly name of the normalization rule, so it can easily be referenced by an administrator.</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-698">Office Communications Server 2007 の新製品。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-698">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="6b2e2-699">Lync Server 2010 では廃止されています。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-699">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6b2e2-700">Msrtcsip-userenabled true-SchemaVersion</span><span class="sxs-lookup"><span data-stu-id="6b2e2-700">msRTCSIP-SchemaVersion</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-701">この属性は、組織に現在展開されているスキーマバージョンを表します。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-701">This attribute represents the schema version currently deployed in the organization.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6b2e2-702">Msrtcsip-userenabled true-SearchMaxRequests (廃止)</span><span class="sxs-lookup"><span data-stu-id="6b2e2-702">msRTCSIP-SearchMaxRequests (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-703">この属性は、ユーザーが Communicator を使って連絡先を検索するときに、ディレクトリ検索から返される検索結果の数を制限します。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-703">This attribute limits the number of search results to be returned from a directory search when a user searches for a contact using Communicator.</span></span> <span data-ttu-id="6b2e2-704">この属性は、クライアントによって指定された値を上書きします。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-704">This attribute will override the value provided by the client.</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-705">Lync Server 2010 では廃止されています。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-705">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6b2e2-706">Msrtcsip-userenabled true-SearchMaxResults (廃止)</span><span class="sxs-lookup"><span data-stu-id="6b2e2-706">msRTCSIP-SearchMaxResults (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-707">この属性は、返される検索要求の数を制限します。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-707">This attribute limits the number of search requests returned.</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-708">Lync Server 2010 では廃止されています。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-708">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6b2e2-709">Msrtcsip-userenabled true-ServerBL</span><span class="sxs-lookup"><span data-stu-id="6b2e2-709">msRTCSIP-ServerBL</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-710">この複数値属性は、識別名 (DN) の一覧を含む戻るリンクです。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-710">This multi-valued attribute is a back link that contains a list of distinguished names (DN).</span></span> <span data-ttu-id="6b2e2-711">これらの DNs はプールまたは<strong>Trustedservice</strong>オブジェクトを参照します。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-711">These DNs point to a pool or <strong>TrustedService</strong> object.</span></span></p>
<p><span data-ttu-id="6b2e2-712">この属性は、 <strong>msrtcsip-userenabled true-TrustedServiceLinks</strong>の前方リンクに対応しています。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-712">This attribute corresponds to the forward link <strong>msRTCSIP-TrustedServiceLinks</strong>.</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-713">Office Communications Server 2007 の新製品。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-713">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6b2e2-714">Msrtcsip-userenabled true-ServerData</span><span class="sxs-lookup"><span data-stu-id="6b2e2-714">msRTCSIP-ServerData</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-715">この属性は将来使用するために予約されています。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-715">This attribute is reserved for future use.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6b2e2-716">Msrtcsip-userenabled true-ServerReferenceBL (廃止)</span><span class="sxs-lookup"><span data-stu-id="6b2e2-716">msRTCSIP-ServerReferenceBL (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-717">この複数値属性には、識別名のリストが含まれています。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-717">This multi-valued attribute contains a list of distinguished names.</span></span> <span data-ttu-id="6b2e2-718">これらの識別名は、既定の場所プロファイルを割り当てることができる他のサーバーオブジェクトを参照する戻るリンクです。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-718">These distinguished names are back links that reference other server objects that can be assigned a default location profile.</span></span></p>
<p><span data-ttu-id="6b2e2-719">戻るリンク:<strong>リンク ID 11037</strong></span><span class="sxs-lookup"><span data-stu-id="6b2e2-719">Back link: <strong>Link ID 11037</strong></span></span></p>
<p><span data-ttu-id="6b2e2-720">この戻るリンクへの対応する前方リンクは<strong>msrtcsip-userenabled true-DefaultLocationProfileLink</strong>です。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-720">The corresponding forward link to this back link is <strong>msRTCSIP-DefaultLocationProfileLink</strong>.</span></span></p>
<p><span data-ttu-id="6b2e2-721">この back link 属性は、プールおよび仲介サーバーのみを参照します。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-721">This back link attribute references pools and Mediation Servers only.</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-722">Office Communications Server 2007 の新製品。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-722">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="6b2e2-723">Lync Server 2010 では廃止されています。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-723">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6b2e2-724">Msrtcsip-userenabled true-ServerVersion</span><span class="sxs-lookup"><span data-stu-id="6b2e2-724">msRTCSIP-ServerVersion</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-725">この属性は、サーバーのバージョン情報を定義します。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-725">This attribute defines the version information of the server.</span></span> <span data-ttu-id="6b2e2-726">このバージョン番号は、すべてのサーバーの役割に適用されます。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-726">This version number applies to all server roles.</span></span> <span data-ttu-id="6b2e2-727">これは、各公式の製品リリースによって増加する monotonously 整数です。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-727">It is a monotonously increasing integer that increments with each official product release.</span></span></p>
<p><span data-ttu-id="6b2e2-728">有効な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-728">The possible valid values are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="6b2e2-729">未定義: Live Communications Server 2003</span><span class="sxs-lookup"><span data-stu-id="6b2e2-729">Undefined: Live Communications Server 2003</span></span></p>
<p><span data-ttu-id="6b2e2-730">                 Live Communications Server 2005</span><span class="sxs-lookup"><span data-stu-id="6b2e2-730">                 Live Communications Server 2005</span></span></p>
<p><span data-ttu-id="6b2e2-731">                 Live Communications Server 2005 SP1</span><span class="sxs-lookup"><span data-stu-id="6b2e2-731">                 Live Communications Server 2005 with SP1</span></span></p></li>
<li><p><span data-ttu-id="6b2e2-732">3: Office Communications Server 2007</span><span class="sxs-lookup"><span data-stu-id="6b2e2-732">3: Office Communications Server 2007</span></span></p></li>
<li><p><span data-ttu-id="6b2e2-733">4: Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="6b2e2-733">4: Office Communications Server 2007 R2</span></span></p></li>
<li><p><span data-ttu-id="6b2e2-734">5: Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="6b2e2-734">5: Lync Server 2010</span></span></p></li>
<li><p><span data-ttu-id="6b2e2-735">6: Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6b2e2-735">6: Lync Server 2013</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="6b2e2-736">Office Communications Server 2007 の新製品。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-736">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6b2e2-737">Msrtcsip-userenabled true-SourceObjectType</span><span class="sxs-lookup"><span data-stu-id="6b2e2-737">msRTCSIP-SourceObjectType</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-738">Integer 型の単一値属性は、次のように、 <strong>SourceObjectDN</strong>が指すオブジェクトの型を指定します。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-738">This single-valued attribute of integer type specifies the type of object the <strong>msDS-SourceObjectDN</strong> points to, as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="6b2e2-739">null |0x00000001: 別のフォレストから Windows NT Server プリンシパルユーザーオブジェクトを表します。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-739">null | 0x00000001: Represents a Windows NT Server principal user object from a different forest</span></span></p></li>
<li><p><span data-ttu-id="6b2e2-740">次の属性は、配布グループの展開用に別のフォレストからのグループの種類を表します。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-740">The following attributes represent a group type from a different forest for distribution group expansion:</span></span></p>
<ul>
<li><p><span data-ttu-id="6b2e2-741">0x00000002: ADS_GROUP_TYPE_GLOBAL_GROUP</span><span class="sxs-lookup"><span data-stu-id="6b2e2-741">0x00000002: ADS_GROUP_TYPE_GLOBAL_GROUP</span></span></p></li>
<li><p><span data-ttu-id="6b2e2-742">0x00000004: ADS_GROUP_TYPE_DOMAIN_LOCAL_GROUP</span><span class="sxs-lookup"><span data-stu-id="6b2e2-742">0x00000004: ADS_GROUP_TYPE_DOMAIN_LOCAL_GROUP</span></span></p></li>
<li><p><span data-ttu-id="6b2e2-743">0x00000004: ADS_GROUP_TYPE_LOCAL_GROUP</span><span class="sxs-lookup"><span data-stu-id="6b2e2-743">0x00000004: ADS_GROUP_TYPE_LOCAL_GROUP</span></span></p></li>
<li><p><span data-ttu-id="6b2e2-744">0x00000008: ADS_GROUP_TYPE_UNIVERSAL_GROUP</span><span class="sxs-lookup"><span data-stu-id="6b2e2-744">0x00000008: ADS_GROUP_TYPE_UNIVERSAL_GROUP</span></span></p></li>
<li><p><span data-ttu-id="6b2e2-745">0x80000000: ADS_GROUP_TYPE_SECURITY_ENABLED</span><span class="sxs-lookup"><span data-stu-id="6b2e2-745">0x80000000: ADS_GROUP_TYPE_SECURITY_ENABLED</span></span></p></li>
<li><p><span data-ttu-id="6b2e2-746">0x90000000: 同じフォレストまたは別のフォレストからの自動応答またはサブスクライバーのアクセスオブジェクトを表します。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-746">0x90000000: Represents an Auto-Attendant or subscriber access object from the same forest or a different forest</span></span></p></li>
</ul></li>
</ul></td>
<td><p><span data-ttu-id="6b2e2-747">Office Communications Server 2007 の新製品。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-747">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6b2e2-748">Msrtcsip-userenabled true-SubscriptionAuthRequired (廃止)</span><span class="sxs-lookup"><span data-stu-id="6b2e2-748">msRTCSIP-SubscriptionAuthRequired (obsolete)</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="6b2e2-749">Live Communications Server 2003 の新サービスです。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-749">New in Live Communications Server 2003.</span></span></p>
<p><span data-ttu-id="6b2e2-750">現在、ライブ通信サーバー2005で廃止されています。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-750">Obsolete in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6b2e2-751">Msrtcsip-userenabled true-Targethoのメッセージ</span><span class="sxs-lookup"><span data-stu-id="6b2e2-751">msRTCSIP-TargetHomeServer</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-752">この属性によって、ユーザーまたは連絡先オブジェクトを、Lync Server プール間で移動することができます。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-752">This attribute enables you to move a user or contact object from one Lync Server pool to another.</span></span> <span data-ttu-id="6b2e2-753">この属性は、中央フォレストのトポロジでは、ユーザーオブジェクトではなく、SIP が有効になるため、contact クラスに追加されます。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-753">This attribute is added to the contact class, because in the central forest topology, contact objects, not user objects, are SIP enabled.</span></span></p>
<p><span data-ttu-id="6b2e2-754">有効な値は、ユーザーが移動するターゲットの Standard Edition サーバーまたはフロントエンドプールの DN です。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-754">The valid value is the DN of the destination Standard Edition server or Front End pool to which a user is to be moved.</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-755">Live Communications Server 2005 の新サービスです。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-755">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6b2e2-756">Msrtcsip-userenabled true-TargetPhoneNumber (廃止)</span><span class="sxs-lookup"><span data-stu-id="6b2e2-756">msRTCSIP-TargetPhoneNumber (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-757">この単一値文字列属性には、 <strong>msrtcsip-userenabled true</strong>で定義されたゲートウェイにルーティングするための電話番号のパターンまたは範囲が含まれます。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-757">This single-valued string attribute contains a phone number pattern or range to route to the specified gateways defined in <strong>msRTCSIP-Gateways</strong>.</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-758">Lync Server 2010 では廃止されています。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-758">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6b2e2-759">Msrtcsip-userenabled true-TargetUserPolicies</span><span class="sxs-lookup"><span data-stu-id="6b2e2-759">msRTCSIP-TargetUserPolicies</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-760">この属性は、Lync Server ユーザーのターゲットポリシーの名前と値のペアを格納します。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-760">This attribute stores name-value pairs for target policies for Lync Server users.</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-761">Lync Server 2010 の新サービスです。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-761">New in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6b2e2-762">Msrtcsip-userenabled true-TenantId</span><span class="sxs-lookup"><span data-stu-id="6b2e2-762">msRTCSIP-TenantId</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-763">この属性には、テナントの一意の識別子が格納されます。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-763">This attribute stores the unique identifier for a tenant.</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-764">Lync Server 2010 の新サービスです。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-764">New in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6b2e2-765">Msrtcsip-userenabled true-翻訳 (廃止)</span><span class="sxs-lookup"><span data-stu-id="6b2e2-765">msRTCSIP-Translation (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-766">この属性は、Lync Server の音声機能によって使用され、一致が見つかった場合は、ダイヤルした番号に適用する翻訳文字列が含まれます。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-766">This attribute is used by the voice feature of Lync Server and contains the translation string to apply on the dialed number, if a match is found.</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-767">Office Communications Server 2007 の新製品。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-767">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="6b2e2-768">Lync Server 2010 では廃止されています。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-768">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6b2e2-769">Msrtcsip-userenabled true-TrustedMCUData</span><span class="sxs-lookup"><span data-stu-id="6b2e2-769">msRTCSIP-TrustedMCUData</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-770">この属性は将来使用するために予約されています。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-770">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-771">Office Communications Server 2007 の新製品。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-771">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6b2e2-772">Msrtcsip-userenabled true-TrustedMCUFQDN</span><span class="sxs-lookup"><span data-stu-id="6b2e2-772">msRTCSIP-TrustedMCUFQDN</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-773">この属性は、MCU の FQDN を含む文字列値です。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-773">This attribute is a string value that contains the FQDN of the MCU.</span></span> <span data-ttu-id="6b2e2-774">これは単一値の属性です。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-774">This is a single-valued attribute.</span></span> <span data-ttu-id="6b2e2-775">各セグメントの有効な値は、63文字です。FQDN 全体の有効な値は、255文字です。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-775">The valid value for each segment is 63 characters; the valid value for the entire FQDN is 255 characters.</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-776">Office Communications Server 2007 の新製品。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-776">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6b2e2-777">Msrtcsip-userenabled true-TrustedProxyData</span><span class="sxs-lookup"><span data-stu-id="6b2e2-777">msRTCSIP-TrustedProxyData</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-778">この属性は将来使用するために予約されています。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-778">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-779">Office Communications Server 2007 の新製品。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-779">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6b2e2-780">Msrtcsip-userenabled true-TrustedProxyFQDN</span><span class="sxs-lookup"><span data-stu-id="6b2e2-780">msRTCSIP-TrustedProxyFQDN</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-781">この属性は、プロキシサーバーを実行しているサーバーの FQDN を含む文字列値です。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-781">This attribute is a string value that contains the FQDN of the server running Proxy Server.</span></span> <span data-ttu-id="6b2e2-782">この属性は単一値になります。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-782">This attribute is single-valued.</span></span> <span data-ttu-id="6b2e2-783">各セグメントの有効な値は、63文字です。FQDN 全体の有効な値は、255文字です。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-783">The valid value for each segment is 63 characters; the valid value for the entire FQDN is 255 characters.</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-784">Office Communications Server 2007 の新製品。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-784">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6b2e2-785">Msrtcsip-userenabled true-TrustedServerData</span><span class="sxs-lookup"><span data-stu-id="6b2e2-785">msRTCSIP-TrustedServerData</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-786">この属性は将来使用するために予約されています。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-786">This attribute is reserved for future use.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6b2e2-787">Msrtcsip-userenabled true-TrustedServerFQDN</span><span class="sxs-lookup"><span data-stu-id="6b2e2-787">msRTCSIP-TrustedServerFQDN</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-788">この属性は、信頼されたサーバーの FQDN を表す単一値属性です。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-788">This attribute is a single-valued attribute that represents the FQDN of a trusted server.</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-789">Live Communications Server 2005 の新サービスです。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-789">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6b2e2-790">Msrtcsip-userenabled true-TrustedServerVersion</span><span class="sxs-lookup"><span data-stu-id="6b2e2-790">msRTCSIP-TrustedServerVersion</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-791">この属性は、信頼されたサーバーの一覧にあるサーバーのバージョン番号を指定します。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-791">This attribute specifies the version number of a server in the trusted server list.</span></span></p>
<p><span data-ttu-id="6b2e2-792">有効な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-792">The possible valid values are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="6b2e2-793">NULL: Live Communications Server 2003</span><span class="sxs-lookup"><span data-stu-id="6b2e2-793">NULL: Live Communications Server 2003</span></span></p></li>
<li><p><span data-ttu-id="6b2e2-794">2: Live Communications Server 2005</span><span class="sxs-lookup"><span data-stu-id="6b2e2-794">2: Live Communications Server 2005</span></span></p></li>
<li><p><span data-ttu-id="6b2e2-795">3: Office Communications Server 2007</span><span class="sxs-lookup"><span data-stu-id="6b2e2-795">3: Office Communications Server 2007</span></span></p></li>
<li><p><span data-ttu-id="6b2e2-796">4: Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="6b2e2-796">4: Office Communications Server 2007 R2</span></span></p></li>
<li><p><span data-ttu-id="6b2e2-797">5: Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="6b2e2-797">5: Lync Server 2010</span></span></p></li>
<li><p><span data-ttu-id="6b2e2-798">6: Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6b2e2-798">6: Lync Server 2013</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="6b2e2-799">Live Communications Server 2005 の新サービスです。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-799">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6b2e2-800">Msrtcsip-userenabled true-TrustedServiceFlags</span><span class="sxs-lookup"><span data-stu-id="6b2e2-800">msRTCSIP-TrustedServiceFlags</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-801">この属性は、信頼されたサービスに対して有効になるオプションを定義します。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-801">This attribute defines the options that are enabled for the trusted service.</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-802">Office Communications Server 2007 R2 の新製品。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-802">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6b2e2-803">Msrtcsip-userenabled true-TrustedServiceLinks</span><span class="sxs-lookup"><span data-stu-id="6b2e2-803">msRTCSIP-TrustedServiceLinks</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-804">この複数値属性には、メディアリレー認証サービスなどの信頼されたサービスオブジェクトを参照する識別名 (DN) の一覧が含まれています。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-804">This multi-valued attribute contains a list of distinguished names (DN) that reference a trusted service object, such as a Media Relay Authentication Service.</span></span> <span data-ttu-id="6b2e2-805">リモートユーザー向けのオーディオシナリオをサポートするには、メディアリレー認証サービス (A/V 会議サービスを実行しているエッジサーバーに物理的に併置されているサービス) がプールに関連付けられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-805">A Media Relay Authentication Service (physically collocated on the Edge Server running the A/V Conferencing service) must be associated with a pool to support audio scenarios for remote users.</span></span></p>
<p><span data-ttu-id="6b2e2-806">この転送リンク属性への対応する [戻る] リンクは、 <strong>msrtcsip-userenabled true-ServerBL</strong>です。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-806">The corresponding back link to this forward link attribute is <strong>msRTCSIP-ServerBL</strong>.</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-807">コミュニケーション</span><span class="sxs-lookup"><span data-stu-id="6b2e2-807">UC</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6b2e2-808">Msrtcsip-userenabled true-TrustedServicePort</span><span class="sxs-lookup"><span data-stu-id="6b2e2-808">msRTCSIP-TrustedServicePort</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-809">この属性は、この GRUU サービスへの接続に使用するポート番号を定義する整数です。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-809">This attribute is an integer that defines the port number used to connect to this GRUU service.</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-810">Office Communications Server 2007 の新製品。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-810">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6b2e2-811">Msrtcsip-userenabled true-TrustedServiceType</span><span class="sxs-lookup"><span data-stu-id="6b2e2-811">msRTCSIP-TrustedServiceType</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-812">この属性は、GRUU サービスの型を定義する文字列値です。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-812">This attribute is a string value that defines the type of GRUU service it represents.</span></span></p>
<p><span data-ttu-id="6b2e2-813">有効な GRUU サービスの種類は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-813">The valid GRUU service types are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="6b2e2-814">MediationServer</span><span class="sxs-lookup"><span data-stu-id="6b2e2-814">MediationServer</span></span></p></li>
<li><p><span data-ttu-id="6b2e2-815">ゲートウェイ</span><span class="sxs-lookup"><span data-stu-id="6b2e2-815">Gateway</span></span></p></li>
<li><p><span data-ttu-id="6b2e2-816">メディアリレー認証サービス (MRAS)</span><span class="sxs-lookup"><span data-stu-id="6b2e2-816">Media Relay Authentication Service (MRAS)</span></span></p></li>
<li><p><span data-ttu-id="6b2e2-817">QoSM</span><span class="sxs-lookup"><span data-stu-id="6b2e2-817">QoSM</span></span></p></li>
<li><p><span data-ttu-id="6b2e2-818">Msrtcsip-userenabled true-UserExtension CWA</span><span class="sxs-lookup"><span data-stu-id="6b2e2-818">msRTCSIP-UserExtension CWA</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="6b2e2-819">Office Communications Server 2007 の新製品。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-819">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6b2e2-820">Msrtcsip-userenabled true-TrustedWebComponentsServerData</span><span class="sxs-lookup"><span data-stu-id="6b2e2-820">msRTCSIP-TrustedWebComponentsServerData</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-821">この属性は将来使用するために予約されています。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-821">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-822">Office Communications Server 2007 の新製品。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-822">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6b2e2-823">Msrtcsip-userenabled true-TrustedWebComponentsServerFQDN</span><span class="sxs-lookup"><span data-stu-id="6b2e2-823">msRTCSIP-TrustedWebComponentsServerFQDN</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-824">この属性は、Lync Server Web サービスが実行されている IIS の FQDN を含む文字列値です。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-824">This attribute is a string value that contains the FQDN of the IIS running Lync Server Web Services.</span></span> <span data-ttu-id="6b2e2-825">これは単一値の属性です。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-825">This is a single-valued attribute.</span></span> <span data-ttu-id="6b2e2-826">各セグメントの有効な値は、63文字です。FQDN 全体の有効な値は、255文字です。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-826">The valid value for each segment is 63 characters; the valid value for the entire FQDN is 255 characters.</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-827">Office Communications Server 2007 の新製品。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-827">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6b2e2-828">Msrtcsip-userenabled true-UCFlags (廃止)</span><span class="sxs-lookup"><span data-stu-id="6b2e2-828">msRTCSIP-UCFlags (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-829">この属性は、すべてのユーザーオブジェクトまたは連絡先オブジェクトでグローバルに有効になるさまざまな UC オプションを定義します。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-829">This attribute defines different UC options that are enabled globally to all user or contact objects.</span></span> <span data-ttu-id="6b2e2-830">この属性は、整数型のビットマスク値です。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-830">This attribute is a bit-mask value of integer type.</span></span> <span data-ttu-id="6b2e2-831">各オプションはビットが存在することで表されます。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-831">Each option is represented by the presence of a bit.</span></span></p>
<p><span data-ttu-id="6b2e2-832">有効な値 (および関連するビット位置) は、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-832">The possible valid value (and associated bit position) are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="6b2e2-833">4: Peruserucpolicy (ビット位置 2)</span><span class="sxs-lookup"><span data-stu-id="6b2e2-833">4: UsePerUserUCPolicy (bit position 2)</span></span></p></li>
</ul>
<p><span data-ttu-id="6b2e2-834">このビットが設定されると、ユーザーごとに UC ポリシーが定義されます。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-834">When this bit is set, the UC policy is defined per user.</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-835">Lync Server 2010 では廃止されています。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-835">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6b2e2-836">Msrtcsip-userenabled true-UCPolicy (廃止)</span><span class="sxs-lookup"><span data-stu-id="6b2e2-836">msRTCSIP-UCPolicy (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-837">この単一値属性には、管理者がこのユーザーに割り当てた UC ポリシーの識別名 (DN) が含まれます。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-837">This single-valued attribute contains the distinguished name (DN) of the UC policy that the administrator has assigned for this user.</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-838">Lync Server 2010 では廃止されています。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-838">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6b2e2-839">Msrtcsip-userenabled true-UserDomainList (廃止)</span><span class="sxs-lookup"><span data-stu-id="6b2e2-839">msRTCSIP-UserDomainList (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-840">この属性は、SIP 対応ユーザーをホストしているフォレスト内のすべてのドメインの一覧を提供します。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-840">This attribute provides a list of all the domains in a forest that host SIP-enabled users.</span></span> <span data-ttu-id="6b2e2-841">既定値は空の一覧で、フォレスト内のすべてのドメインが SIP 対応であることを示します。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-841">The default is an empty list, indicating that all domains in the forest are SIP-enabled.</span></span></p>
<p><span data-ttu-id="6b2e2-842">有効な値は、個々のドメインのドメイン名を表す複数の文字列です。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-842">Valid values are multiple strings representing the domain names of individual domains.</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-843">Live Communications Server 2005 の新サービスです。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-843">New in Live Communications Server 2005.</span></span></p>
<p><span data-ttu-id="6b2e2-844">Lync Server 2010 では廃止されています。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-844">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6b2e2-845">Msrtcsip-userenabled true-UserEnabled</span><span class="sxs-lookup"><span data-stu-id="6b2e2-845">msRTCSIP-UserEnabled</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-846">この属性は、ユーザーが Lync Server で現在有効になっているかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-846">This attribute determines whether the user is currently enabled for Lync Server.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6b2e2-847">Msrtcsip-userenabled true-UserExtension</span><span class="sxs-lookup"><span data-stu-id="6b2e2-847">msRTCSIP-UserExtension</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-848">この複数値を持つ属性には、name = value の&quot;形式の名前と値のペアの一覧が含まれています。&quot;この属性は、グローバルカタログのレプリケーション用にマークされます。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-848">This multi-valued attribute contains a list of name-value pairs in the format of &quot;name=value.&quot; This attribute is marked for global catalog replication.</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-849">SP1 での最新のライブ通信サーバー2005。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-849">New in Live Communications Server 2005 with SP1.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6b2e2-850">Msrtcsip-userenabled true-UserLocationProfile</span><span class="sxs-lookup"><span data-stu-id="6b2e2-850">msRTCSIP-UserLocationProfile</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-851">この属性には、場所プロファイルオブジェクトを参照する識別名 (DN) が含まれます。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-851">This attribute contains the distinguished name (DN) that points to a location profile object.</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-852">Office Communications Server 2007 R2 の新製品。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-852">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6b2e2-853">Msrtcsip-userenabled true-UserPolicies</span><span class="sxs-lookup"><span data-stu-id="6b2e2-853">msRTCSIP-UserPolicies</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-854">この属性は、ユーザーポリシーの名前と値のペアを格納します。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-854">This attribute stores name-value pairs for user policies.</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-855">Lync Server 2010 の新サービスです。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-855">New in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6b2e2-856">Msrtcsip-userenabled true-UserPolicy</span><span class="sxs-lookup"><span data-stu-id="6b2e2-856">msRTCSIP-UserPolicy</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-857">これは、さまざまな種類のグローバルユーザーポリシーを指定するバイナリ (DN_WITH_BINARY) の識別名の一覧を含む複数値の属性です。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-857">This is a multi-valued attribute containing a list of distinguished names with binary (DN_WITH_BINARY) pointing to global user policies of different types.</span></span> <span data-ttu-id="6b2e2-858">バイナリ部分は、DN の部分が指しているポリシーの種類を示します。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-858">The binary part indicates the type of policy to which the DN portion points.</span></span></p>
<p><span data-ttu-id="6b2e2-859">有効なバイナリ値は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-859">The valid binary values are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="6b2e2-860">0x00000001: 会議のポリシー</span><span class="sxs-lookup"><span data-stu-id="6b2e2-860">0x00000001: Meeting policy</span></span></p></li>
<li><p><span data-ttu-id="6b2e2-861">0x00000002: UC ポリシー</span><span class="sxs-lookup"><span data-stu-id="6b2e2-861">0x00000002: UC policy</span></span></p></li>
<li><p><span data-ttu-id="6b2e2-862">0x00000005: プレゼンスポリシー</span><span class="sxs-lookup"><span data-stu-id="6b2e2-862">0x00000005: Presence policy</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="6b2e2-863">Office Communications Server 2007 の新製品。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-863">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6b2e2-864">Msrtcsip-userenabled true-UserRoutingGroupId</span><span class="sxs-lookup"><span data-stu-id="6b2e2-864">msRTCSIP-UserRoutingGroupId</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-865">これは、SIP ルーティンググループの ID です。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-865">This is the SIP routing group ID.</span></span> <span data-ttu-id="6b2e2-866">同じグループ内のユーザーは、同じフロントエンドサーバーに登録されます。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-866">Users in the same group will register to the same Front End Server.</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-867">Lync Server 2013 の新サービスです。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-867">New in Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6b2e2-868">Msrtcsip-userenabled true-Webcontacts データ</span><span class="sxs-lookup"><span data-stu-id="6b2e2-868">msRTCSIP-WebComponentsData</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-869">これは複数値の属性です。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-869">This is a multi-valued attribute.</span></span> <span data-ttu-id="6b2e2-870">この属性は将来使用するために予約されています。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-870">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-871">Office Communications Server 2007 の新製品。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-871">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6b2e2-872">Msrtcsip-userenabled true-WebComponentsPoolAddress</span><span class="sxs-lookup"><span data-stu-id="6b2e2-872">msRTCSIP-WebComponentsPoolAddress</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-873">この単一値の属性は、web コンポーネントが属しているプールまたは Standard Edition サーバーを指します。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-873">This single-valued attribute points to the pool or Standard Edition server to which the web components belong.</span></span></p>
<p><span data-ttu-id="6b2e2-874">転送リンク:<strong>リンク ID 11028</strong></span><span class="sxs-lookup"><span data-stu-id="6b2e2-874">Forward link: <strong>Link ID 11028</strong></span></span></p>
<p><span data-ttu-id="6b2e2-875">この転送リンク属性への対応する "戻る" リンクは、 <strong>Msrtcsip-userenabled true Webservers サーバー</strong>です。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-875">The corresponding back link to this forward link attribute is <strong>msRTCSIP-WebComponentsServers</strong>.</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-876">Office Communications Server 2007 の新製品。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-876">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6b2e2-877">Msrtcsip-userenabled true-Webservers サーバー</span><span class="sxs-lookup"><span data-stu-id="6b2e2-877">msRTCSIP-WebComponentsServers</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-878">この属性は、複数値を持つ識別名の一覧です。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-878">This attribute is a multi-valued list of distinguished names.</span></span> <span data-ttu-id="6b2e2-879">この属性には、このプールに関連付けられているすべての Web サーバーの一覧が含まれます。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-879">This attribute contains a list of all Web servers associated with this pool.</span></span></p>
<p><span data-ttu-id="6b2e2-880">戻るリンク:<strong>リンク ID 11029</strong></span><span class="sxs-lookup"><span data-stu-id="6b2e2-880">Back link: <strong>Link ID 11029</strong></span></span></p>
<p><span data-ttu-id="6b2e2-881">この戻るリンクへの対応する前方リンクは<strong>Msrtcsip-userenabled true WebComponentsPoolAddress</strong>です。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-881">The corresponding forward link to this back link is <strong>msRTCSIP-WebComponentsPoolAddress</strong>.</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-882">Office Communications Server 2007 の新製品。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-882">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6b2e2-883">Msrtcsip-userenabled true の形式の Instanceid (廃止)</span><span class="sxs-lookup"><span data-stu-id="6b2e2-883">msRTCSIP-WMIInstanceId (obsolete)</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="6b2e2-884">Live Communications Server 2003 の新サービスです。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-884">New in Live Communications Server 2003.</span></span></p>
<p><span data-ttu-id="6b2e2-885">現在、ライブ通信サーバー2005で廃止されています。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-885">Obsolete in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6b2e2-886">他の Ip電話</span><span class="sxs-lookup"><span data-stu-id="6b2e2-886">OtherIPPhone</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-887">この既存の Active Directory 属性は、電話の代替 TCP/IP アドレスの一覧を指定するためにテレフォニーで使用されます。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-887">This existing Active Directory attribute is used by telephony to specify the list of alternate TCP/IP addresses for a phone.</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-888">Windows Server 2008 オペレーティングシステムの新機能。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-888">New in Windows Server 2008 operating system.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6b2e2-889">他の電話帳</span><span class="sxs-lookup"><span data-stu-id="6b2e2-889">PhoneOfficeOther</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-890">この既存の Active Directory 属性は、ユニファイドメッセージングの自動応答とサブスクライバーアクセス番号の呼び出しをルーティングすることを目的として、Lync Server のボイスコンポーネントに対してのみ使用されます。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-890">This existing Active Directory attribute is used by the voice components in Lync Server, for contact objects only, for the purpose of routing calls to the unified messaging auto-attendant and subscriber access numbers.</span></span> <span data-ttu-id="6b2e2-891">無条件着信転送アドレスがこの複数値属性に保存されています。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-891">The unconditional call forwarding address is stored in this multi-valued attribute.</span></span> <span data-ttu-id="6b2e2-892">このアカウントは、自動応答とサブスクライバーアクセスの特定の目的で作成されます。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-892">This account is created for the specific purpose of auto-attendant and subscriber access.</span></span> <span data-ttu-id="6b2e2-893">このアカウントの属性は、管理者が変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-893">This account’s attributes should not be modified by administrators.</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-894">Windows 2000 オペレーティングシステムの新機能。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-894">New in Windows 2000 operating system.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6b2e2-895">ProxyAddresses</span><span class="sxs-lookup"><span data-stu-id="6b2e2-895">ProxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-896">この既存の Active Directory マルチバリュー属性は、Windows 2000 で導入されたベース Active Directory スキーマの一部です。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-896">This existing Active Directory multi-valued attribute is part of the base Active Directory schema introduced in Windows 2000.</span></span> <span data-ttu-id="6b2e2-897">この属性には、ユーザーのメールのさまざまな X400、X500、および SMTP アドレスが含まれています。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-897">This attribute contains the various X400, X500, and SMTP addresses of the user’s email.</span></span> <span data-ttu-id="6b2e2-898">Live Communications Server 2003 以降では、 &quot;sip:&quot;タグを使用して、ユーザーの sip URI がこのリストに追加されます。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-898">In Live Communications Server 2003 and later, the user’s SIP URI is added to this list, using the &quot;sip:&quot; tag.</span></span></p>
<p><span data-ttu-id="6b2e2-899">次のアプリケーションは、この属性によってユーザーの SIP URI を検索します。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-899">The following applications search the user’s SIP URI from this attribute:</span></span></p>
<ul>
<li><p><span data-ttu-id="6b2e2-900">Microsoft Office Outlook 2003 メッセージングおよびコラボレーションクライアント</span><span class="sxs-lookup"><span data-stu-id="6b2e2-900">Microsoft Office Outlook 2003 messaging and collaboration client</span></span></p></li>
<li><p><span data-ttu-id="6b2e2-901">Microsoft Office SharePoint Server 2007</span><span class="sxs-lookup"><span data-stu-id="6b2e2-901">Microsoft Office SharePoint Server 2007</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="6b2e2-902">Windows 2000 オペレーティングシステムの新機能。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-902">New in Windows 2000 operating system.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6b2e2-903">TelephoneNumber</span><span class="sxs-lookup"><span data-stu-id="6b2e2-903">TelephoneNumber</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-904">この既存の Active Directory の属性には、ユーザーの電話番号が含まれています。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-904">This existing Active Directory attribute contains the telephone number for the user.</span></span></p></td>
<td><p><span data-ttu-id="6b2e2-905">Windows 2000 オペレーティングシステムの新機能。</span><span class="sxs-lookup"><span data-stu-id="6b2e2-905">New in Windows 2000 operating system.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

