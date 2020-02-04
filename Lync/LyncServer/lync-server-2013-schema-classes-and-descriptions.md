---
title: 'Lync Server 2013: スキーマのクラスと説明'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Schema classes and descriptions
ms:assetid: 7d43b920-ac37-40cc-adfe-be289bda6e9e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398625(v=OCS.15)
ms:contentKeyID: 48184612
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5080af0977457f5c4a75d2f121e75560b0f24524
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764935"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="schema-classes-and-descriptions-in-lync-server-2013"></a><span data-ttu-id="de882-102">Lync Server 2013 のスキーマクラスと説明</span><span class="sxs-lookup"><span data-stu-id="de882-102">Schema classes and descriptions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="de882-103">_**最終更新日:** 2012-10-30_</span><span class="sxs-lookup"><span data-stu-id="de882-103">_**Topic Last Modified:** 2012-10-30_</span></span>

<span data-ttu-id="de882-104">このセクションでは、Lync Server 2013 で使用されるすべてのスキーマクラスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="de882-104">This section describes all the schema classes used by Lync Server 2013.</span></span>

<div>

## <a name="schema-classes-and-descriptions"></a><span data-ttu-id="de882-105">スキーマのクラスと説明</span><span class="sxs-lookup"><span data-stu-id="de882-105">Schema Classes and Descriptions</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="de882-106">クラス</span><span class="sxs-lookup"><span data-stu-id="de882-106">Class</span></span></th>
<th><span data-ttu-id="de882-107">説明</span><span class="sxs-lookup"><span data-stu-id="de882-107">Description</span></span></th>
<th><span data-ttu-id="de882-108">コメント</span><span class="sxs-lookup"><span data-stu-id="de882-108">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="de882-109">メール受信者</span><span class="sxs-lookup"><span data-stu-id="de882-109">Mail-Recipient</span></span></p></td>
<td><p><span data-ttu-id="de882-110">Exchange ユニファイドメッセージング (UM) メール受信者。</span><span class="sxs-lookup"><span data-stu-id="de882-110">Exchange Unified Messaging (UM) email recipient.</span></span></p></td>
<td><p><span data-ttu-id="de882-111">この補助クラスは Exchange UM と共有されます。</span><span class="sxs-lookup"><span data-stu-id="de882-111">This auxiliary class is shared with Exchange UM.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="de882-112">Msrtcsip-userenabled true-ApplicationContacts</span><span class="sxs-lookup"><span data-stu-id="de882-112">msRTCSIP-ApplicationContacts</span></span></p></td>
<td><p><span data-ttu-id="de882-113">このクラスは、複数のアプリケーションの連絡先のコンテナーであり、属性自体は含まれません。</span><span class="sxs-lookup"><span data-stu-id="de882-113">This class is a container for multiple application contacts and does not contain any attributes itself.</span></span></p></td>
<td><p><span data-ttu-id="de882-114">Microsoft Office Communications Server 2007 R2 の新製品。</span><span class="sxs-lookup"><span data-stu-id="de882-114">New in Microsoft Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="de882-115">Msrtcsip-userenabled true-ApplicationServer</span><span class="sxs-lookup"><span data-stu-id="de882-115">msRTCSIP-ApplicationServer</span></span></p></td>
<td><p><span data-ttu-id="de882-116">このクラスは、ユニファイドコミュニケーションアプリケーションサービス (UCAS) のインスタンスのサービスコントロールポイントのエントリを保持します。</span><span class="sxs-lookup"><span data-stu-id="de882-116">This class holds the entry for the service control point for an instance of Unified Communications Application Services (UCAS).</span></span></p></td>
<td><p><span data-ttu-id="de882-117">Office Communications Server 2007 R2 の新製品。</span><span class="sxs-lookup"><span data-stu-id="de882-117">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="de882-118">Msrtcsip-userenabled true-ApplicationServerService</span><span class="sxs-lookup"><span data-stu-id="de882-118">msRTCSIP-ApplicationServerService</span></span></p></td>
<td><p><span data-ttu-id="de882-119">このクラスは、特定のプールからそのアプリケーションサービスへの関連付けを提供します。</span><span class="sxs-lookup"><span data-stu-id="de882-119">This class provides an association from a specific pool to its Application service.</span></span></p></td>
<td><p><span data-ttu-id="de882-120">Communications Server 2007 R2 の新サービスです。</span><span class="sxs-lookup"><span data-stu-id="de882-120">New in Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="de882-121">Msrtcsip-userenabled true-ApplicationServerSettings</span><span class="sxs-lookup"><span data-stu-id="de882-121">msRTCSIP-ApplicationServerSettings</span></span></p></td>
<td><p><span data-ttu-id="de882-122">この補助クラスと Msrtcsip-userenabled true-ApplicationServer は、アプリケーションサービスのインスタンスの設定を表す属性を保持します。</span><span class="sxs-lookup"><span data-stu-id="de882-122">This auxiliary class to msRTCSIP-ApplicationServer holds attributes representing settings for instances of the Application service.</span></span></p></td>
<td><p><span data-ttu-id="de882-123">Communications Server 2007 R2 の新サービスです。</span><span class="sxs-lookup"><span data-stu-id="de882-123">New in Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="de882-124">Msrtcsip-userenabled true-アーカイブ (廃止)</span><span class="sxs-lookup"><span data-stu-id="de882-124">msRTCSIP-Archive (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="de882-125">この補助クラス to Msrtcsip-userenabled true-GlobalContainer は、アーカイブに関連するすべての設定を保持します。</span><span class="sxs-lookup"><span data-stu-id="de882-125">This auxiliary class to msRTCSIP-GlobalContainer holds all settings related to archiving.</span></span></p></td>
<td><p><span data-ttu-id="de882-126">Lync Server 2010 では廃止されています。</span><span class="sxs-lookup"><span data-stu-id="de882-126">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="de882-127">Msrtcsip-userenabled true-ArchivingServer (廃止)</span><span class="sxs-lookup"><span data-stu-id="de882-127">msRTCSIP-ArchivingServer (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="de882-128">このクラスは、単一のインスタントメッセージングアーカイブサーバーを表します。</span><span class="sxs-lookup"><span data-stu-id="de882-128">This class represents a single instant messaging Archiving Server.</span></span> <span data-ttu-id="de882-129">このクラスのインスタンスは、インスタントメッセージアーカイブサービスがインストールされているコンピューターなど、コンピューターがインスタントメッセージングアーカイブサーバーとしてアクティブ化されたときに作成されます。</span><span class="sxs-lookup"><span data-stu-id="de882-129">An instance of this class is created when a computer is activated as an instant messaging Archiving Server, such as a computer with the Instant Messaging Archiving service installed.</span></span></p></td>
<td><p><span data-ttu-id="de882-130">Lync Server 2010 では廃止されています。</span><span class="sxs-lookup"><span data-stu-id="de882-130">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="de882-131">Msrtcsip-userenabled true-ConferenceDirectories</span><span class="sxs-lookup"><span data-stu-id="de882-131">msRTCSIP-ConferenceDirectories</span></span></p></td>
<td><p><span data-ttu-id="de882-132">このクラスは、会議ディレクトリの複数のインスタンスのコンテナーであり、属性自体は含まれません。</span><span class="sxs-lookup"><span data-stu-id="de882-132">This class is a container for multiple instances of conference directories and does not contain any attributes itself.</span></span></p></td>
<td><p><span data-ttu-id="de882-133">Communications Server 2007 R2 の新サービスです。</span><span class="sxs-lookup"><span data-stu-id="de882-133">New in Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="de882-134">Msrtcsip-userenabled true-ConferenceDirectory</span><span class="sxs-lookup"><span data-stu-id="de882-134">msRTCSIP-ConferenceDirectory</span></span></p></td>
<td><p><span data-ttu-id="de882-135">このクラスには、特定の会議ディレクトリの設定を表す属性が保持しています。</span><span class="sxs-lookup"><span data-stu-id="de882-135">This class holds attributes representing settings for a specific conference directory.</span></span></p></td>
<td><p><span data-ttu-id="de882-136">Communications Server 2007 R2 の新サービスです。</span><span class="sxs-lookup"><span data-stu-id="de882-136">New in Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="de882-137">Msrtcsip-userenabled true-ConnectionPoint</span><span class="sxs-lookup"><span data-stu-id="de882-137">msRTCSIP-ConnectionPoint</span></span></p></td>
<td><p><span data-ttu-id="de882-138">[汎用サービス制御ポイント (SCP)] は、Lync Server を実行しているサーバーとしてコンピューターを指定します。</span><span class="sxs-lookup"><span data-stu-id="de882-138">Generic service control point (SCP) to specify the computer as a server running Lync Server.</span></span></p></td>
<td><p><span data-ttu-id="de882-139">Lync 2010 の新方法。</span><span class="sxs-lookup"><span data-stu-id="de882-139">New in Lync 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="de882-140">Msrtcsip-userenabled true-DefaultCWABank</span><span class="sxs-lookup"><span data-stu-id="de882-140">msRTCSIP-DefaultCWABank</span></span></p></td>
<td><p><span data-ttu-id="de882-141">この補助クラスは、Microsoft Lync Web App bank の設定を保持します。</span><span class="sxs-lookup"><span data-stu-id="de882-141">This auxiliary class holds the settings for a Microsoft Lync Web App bank.</span></span></p></td>
<td><p><span data-ttu-id="de882-142">Communications Server 2007 R2 の新サービスです。</span><span class="sxs-lookup"><span data-stu-id="de882-142">New in Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="de882-143">Msrtcsip-userenabled true-ドメイン</span><span class="sxs-lookup"><span data-stu-id="de882-143">msRTCSIP-Domain</span></span></p></td>
<td><p><span data-ttu-id="de882-144">このクラスは、SIP レジストラーの構成済みドメインを定義する属性を保持します。</span><span class="sxs-lookup"><span data-stu-id="de882-144">This class holds attributes that define the configured domains of the SIP Registrar.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="de882-145">Msrtcsip-userenabled true-EdgeProxy</span><span class="sxs-lookup"><span data-stu-id="de882-145">msRTCSIP-EdgeProxy</span></span></p></td>
<td><p><span data-ttu-id="de882-146">このクラスコンテナーは、単一のアクセスエッジサービスを表します。</span><span class="sxs-lookup"><span data-stu-id="de882-146">This class container represents a single Access Edge service.</span></span> <span data-ttu-id="de882-147">アクセスエッジサービスは境界ネットワークに展開されているため、ユーザーは通常、境界ネットワークからの Active Directory ドメインサービスへのアクセスを許可しません。アクセスエッジサービスのインスタンスは、イントラネットの Active Directory ネットワークには参加していません。</span><span class="sxs-lookup"><span data-stu-id="de882-147">Because an Access Edge service is deployed in the perimeter network and customers usually do not allow Active Directory Domain Services access from the perimeter network, instances of Access Edge service are not joined to the intranet’s Active Directory network.</span></span> <span data-ttu-id="de882-148">そのため、アクセスプロキシは AD DS に自動的に登録されません。</span><span class="sxs-lookup"><span data-stu-id="de882-148">Therefore, Access Proxies are not automatically registered in AD DS.</span></span> <span data-ttu-id="de882-149">管理者は、AD DS のアクセスエッジサービスの各インスタンスの存在を手動で構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="de882-149">The administrator must manually configure the existence of each instance of Access Edge service in AD DS.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="de882-150">Msrtcsip-userenabled true-EnterpriseMCUSettings</span><span class="sxs-lookup"><span data-stu-id="de882-150">msRTCSIP-EnterpriseMCUSettings</span></span></p></td>
<td><p><span data-ttu-id="de882-151">この補助クラスから Msrtcsip-userenabled true への属性は、会議サーバーの設定を表す属性を保持します。</span><span class="sxs-lookup"><span data-stu-id="de882-151">This auxiliary class to msRTCSIP-MCU holds attributes representing settings for Conferencing servers.</span></span></p></td>
<td><p><span data-ttu-id="de882-152">Microsoft Office Communications Server 2007 の新製品。</span><span class="sxs-lookup"><span data-stu-id="de882-152">New in Microsoft Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="de882-153">Msrtcsip-userenabled true-EnterpriseMediationServerSettings</span><span class="sxs-lookup"><span data-stu-id="de882-153">msRTCSIP-EnterpriseMediationServerSettings</span></span></p></td>
<td><p><span data-ttu-id="de882-154">この補助クラスの Msrtcsip-userenabled true-MediationServer は、仲介サーバーの設定を表す属性を保持します。</span><span class="sxs-lookup"><span data-stu-id="de882-154">This auxiliary class to msRTCSIP-MediationServer holds attributes representing settings for Mediation Servers.</span></span></p></td>
<td><p><span data-ttu-id="de882-155">Office Communications Server 2007 の新製品。</span><span class="sxs-lookup"><span data-stu-id="de882-155">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="de882-156">Msrtcsip-userenabled true-EnterpriseServerSettings</span><span class="sxs-lookup"><span data-stu-id="de882-156">msRTCSIP-EnterpriseServerSettings</span></span></p></td>
<td><p><span data-ttu-id="de882-157">Msrtcsip-userenabled true への補助クラスは、SIP サーバーの設定を表す属性を保持します。</span><span class="sxs-lookup"><span data-stu-id="de882-157">This auxiliary class to msRTCSIP-Server holds attributes representing settings for SIP servers.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="de882-158">Msrtcsip-userenabled true-フェデレーション</span><span class="sxs-lookup"><span data-stu-id="de882-158">msRTCSIP-Federation</span></span></p></td>
<td><p><span data-ttu-id="de882-159">この補助クラス to Msrtcsip-userenabled true-GlobalContainer は、フェデレーションに関連するすべての設定を保持します。</span><span class="sxs-lookup"><span data-stu-id="de882-159">This auxiliary class to msRTCSIP-GlobalContainer holds all settings related to federation.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="de882-160">Msrtcsip-userenabled true-GlobalContainer</span><span class="sxs-lookup"><span data-stu-id="de882-160">msRTCSIP-GlobalContainer</span></span></p></td>
<td><p><span data-ttu-id="de882-161">このクラスは、Lync Server の展開全体で適用されるすべての設定を保持します。</span><span class="sxs-lookup"><span data-stu-id="de882-161">This class holds all settings that apply throughout a Lync Server deployment.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="de882-162">Msrtcsip-userenabled true-GlobalUserPolicy (廃止)</span><span class="sxs-lookup"><span data-stu-id="de882-162">msRTCSIP-GlobalUserPolicy (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="de882-163">このクラスは、1つの Office Communications Server 会議ポリシーを表します。</span><span class="sxs-lookup"><span data-stu-id="de882-163">This class represents a single Office Communications Server meeting policy.</span></span></p></td>
<td><p><span data-ttu-id="de882-164">Lync Server 2010 では廃止されています。</span><span class="sxs-lookup"><span data-stu-id="de882-164">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="de882-165">Msrtcsip-userenabled true-GlobalTopologySetting</span><span class="sxs-lookup"><span data-stu-id="de882-165">msRTCSIP-GlobalTopologySetting</span></span></p></td>
<td><p><span data-ttu-id="de882-166">ローカルグローバルトポロジ設定オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="de882-166">The local global topology setting object.</span></span></p></td>
<td><p><span data-ttu-id="de882-167">Lync Server 2010 の新サービスです。</span><span class="sxs-lookup"><span data-stu-id="de882-167">New in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="de882-168">Msrtcsip-userenabled true-GlobalTopologySettings</span><span class="sxs-lookup"><span data-stu-id="de882-168">msRTCSIP-GlobalTopologySettings</span></span></p></td>
<td><p><span data-ttu-id="de882-169">グローバルトポロジ設定オブジェクトを保持するコンテナー。</span><span class="sxs-lookup"><span data-stu-id="de882-169">Container to hold global topology setting objects.</span></span></p></td>
<td><p><span data-ttu-id="de882-170">Lync Server 2010 の新サービスです。</span><span class="sxs-lookup"><span data-stu-id="de882-170">New in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="de882-171">Msrtcsip-userenabled true-LocalNormalization</span><span class="sxs-lookup"><span data-stu-id="de882-171">msRTCSIP-LocalNormalization</span></span></p></td>
<td><p><span data-ttu-id="de882-172">このクラスは、位置正規化規則のインスタンスを表すコンテナーです。</span><span class="sxs-lookup"><span data-stu-id="de882-172">This class is a container that represents an instance of a location normalization rule.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="de882-173">Msrtcsip-userenabled true-LocationContactMapping</span><span class="sxs-lookup"><span data-stu-id="de882-173">msRTCSIP-LocationContactMapping</span></span></p></td>
<td><p><span data-ttu-id="de882-174">このクラスは、会議アテンダントアプリケーションによって作成され、地域ごとの会議電話番号の分類に使われる属性を保持します。</span><span class="sxs-lookup"><span data-stu-id="de882-174">This class is created by the Conferencing Attendant application and holds attributes used to categorize conference telephone numbers by region.</span></span></p></td>
<td><p><span data-ttu-id="de882-175">Communications Server 2007 R2 の新サービスです。</span><span class="sxs-lookup"><span data-stu-id="de882-175">New in Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="de882-176">Msrtcsip-userenabled true-LocationContactMappings マッピング</span><span class="sxs-lookup"><span data-stu-id="de882-176">msRTCSIP-LocationContactMappings</span></span></p></td>
<td><p><span data-ttu-id="de882-177">このクラスは、場所の連絡先マッピングの複数のインスタンスのコンテナーであり、属性自体は含まれません。</span><span class="sxs-lookup"><span data-stu-id="de882-177">This class is a container for multiple instances of location contact mappings and does not contain any attributes itself.</span></span></p></td>
<td><p><span data-ttu-id="de882-178">Communications Server 2007 R2 の新サービスです。</span><span class="sxs-lookup"><span data-stu-id="de882-178">New in Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="de882-179">Msrtcsip-userenabled true-LocationProfile</span><span class="sxs-lookup"><span data-stu-id="de882-179">msRTCSIP-LocationProfile</span></span></p></td>
<td><p><span data-ttu-id="de882-180">このクラスは、特定の位置情報プロファイルを表すコンテナーです。</span><span class="sxs-lookup"><span data-stu-id="de882-180">This class is a container that represents a specific location profile.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="de882-181">Msrtcsip-userenabled true-LocationProfiles (廃止)</span><span class="sxs-lookup"><span data-stu-id="de882-181">msRTCSIP-LocationProfiles (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="de882-182">このクラスは、複数の場所プロファイルのコンテナーであり、属性自体は含まれません。</span><span class="sxs-lookup"><span data-stu-id="de882-182">This class is a container for multiple location profiles and does not contain any attributes itself.</span></span></p></td>
<td><p><span data-ttu-id="de882-183">Lync Server 2010 では廃止されています。</span><span class="sxs-lookup"><span data-stu-id="de882-183">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="de882-184">Msrtcsip-userenabled true-LocalNormalizations 廃止)</span><span class="sxs-lookup"><span data-stu-id="de882-184">msRTCSIP-LocalNormalizations (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="de882-185">このクラスは、複数のローカル正規化規則のコンテナーであり、属性自体は含まれません。</span><span class="sxs-lookup"><span data-stu-id="de882-185">This class is a container for multiple local normalization rules and does not contain any attributes itself.</span></span></p></td>
<td><p><span data-ttu-id="de882-186">Lync Server 2010 では廃止されています。</span><span class="sxs-lookup"><span data-stu-id="de882-186">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="de882-187">Msrtcsip-userenabled true-MCU</span><span class="sxs-lookup"><span data-stu-id="de882-187">msRTCSIP-MCU</span></span></p></td>
<td><p><span data-ttu-id="de882-188">このクラスは、単一の会議サーバーを表します。</span><span class="sxs-lookup"><span data-stu-id="de882-188">This class represents a single Conferencing server.</span></span></p></td>
<td><p><span data-ttu-id="de882-189">Communications Server 2007 の新サービスです。</span><span class="sxs-lookup"><span data-stu-id="de882-189">New in Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="de882-190">Msrtcsip-userenabled true-MCUFactories</span><span class="sxs-lookup"><span data-stu-id="de882-190">msRTCSIP-MCUFactories</span></span></p></td>
<td><p><span data-ttu-id="de882-191">このクラスは、複数の Msrtcsip-userenabled true を保持し、属性自体は持ちません。</span><span class="sxs-lookup"><span data-stu-id="de882-191">This class holds multiple msRTCSIP-MCUFactory classes and does not have attributes itself.</span></span></p></td>
<td><p><span data-ttu-id="de882-192">Communications Server 2007 の新サービスです。</span><span class="sxs-lookup"><span data-stu-id="de882-192">New in Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="de882-193">Msrtcsip-userenabled true-MCUFactory</span><span class="sxs-lookup"><span data-stu-id="de882-193">msRTCSIP-MCUFactory</span></span></p></td>
<td><p><span data-ttu-id="de882-194">このクラスは、単一のメディアの種類の会議サーバーファクトリを表すコンテナーです。</span><span class="sxs-lookup"><span data-stu-id="de882-194">This class is a container representing a Conferencing Server Factory for a single medium type.</span></span> <span data-ttu-id="de882-195">このクラスのインスタンスは、この特定の種類とベンダーの最初の会議サーバーがアクティブ化されたときに作成されます。</span><span class="sxs-lookup"><span data-stu-id="de882-195">An instance of this class is created when the first Conferencing server for this particular type and vendor is activated.</span></span></p></td>
<td><p><span data-ttu-id="de882-196">Communications Server 2007 の新サービスです。</span><span class="sxs-lookup"><span data-stu-id="de882-196">New in Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="de882-197">Msrtcsip-userenabled true-MCUFactoryService</span><span class="sxs-lookup"><span data-stu-id="de882-197">msRTCSIP-MCUFactoryService</span></span></p></td>
<td><p><span data-ttu-id="de882-198">このクラスは、特定のプールから会議サーバーファクトリへの関連付けを提供します。</span><span class="sxs-lookup"><span data-stu-id="de882-198">This class provides an association from a specific pool to its Conferencing Server Factory.</span></span></p></td>
<td><p><span data-ttu-id="de882-199">Communications Server 2007 の新サービスです。</span><span class="sxs-lookup"><span data-stu-id="de882-199">New in Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="de882-200">Msrtcsip-userenabled true-MediationServer</span><span class="sxs-lookup"><span data-stu-id="de882-200">msRTCSIP-MediationServer</span></span></p></td>
<td><p><span data-ttu-id="de882-201">このクラスは、仲介サーバーのサービス制御ポイントのエントリを保持します。</span><span class="sxs-lookup"><span data-stu-id="de882-201">This class holds the entry for the service control point for a Mediation Server.</span></span></p></td>
<td><p><span data-ttu-id="de882-202">Communications Server 2007 の新サービスです。</span><span class="sxs-lookup"><span data-stu-id="de882-202">New in Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="de882-203">Msrtcsip-userenabled true-会議 (廃止)</span><span class="sxs-lookup"><span data-stu-id="de882-203">msRTCSIP-Meeting (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="de882-204">この補助クラスの Msrtcsip-userenabled true-GlobalContainer は、構成可能な会議の設定を示す属性を保持します。</span><span class="sxs-lookup"><span data-stu-id="de882-204">This auxiliary class to msRTCSIP-GlobalContainer holds attributes representing configurable meeting settings.</span></span></p></td>
<td><p><span data-ttu-id="de882-205">Lync Server 2010 では廃止されています。</span><span class="sxs-lookup"><span data-stu-id="de882-205">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="de882-206">Msrtcsip-userenabled true</span><span class="sxs-lookup"><span data-stu-id="de882-206">msRTCSIP-Mobility</span></span></p></td>
<td><p><span data-ttu-id="de882-207">グローバルモバイル設定を格納するコンテナー。</span><span class="sxs-lookup"><span data-stu-id="de882-207">Container that stores the global mobility settings.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="de882-208">Msrtcsip-userenabled true-MonitoringServer</span><span class="sxs-lookup"><span data-stu-id="de882-208">msRTCSIP-MonitoringServer</span></span></p></td>
<td><p><span data-ttu-id="de882-209">このクラスは、単一の監視サーバーの設定を表す属性を保持します。</span><span class="sxs-lookup"><span data-stu-id="de882-209">This class holds attributes that represent settings for a single Monitoring Server.</span></span></p></td>
<td><p><span data-ttu-id="de882-210">Communications Server 2007 R2 の新サービスです。</span><span class="sxs-lookup"><span data-stu-id="de882-210">New in Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="de882-211">Msrtcsip-userenabled true-PhoneRoute (廃止)</span><span class="sxs-lookup"><span data-stu-id="de882-211">msRTCSIP-PhoneRoute (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="de882-212">このクラスは、ゲートウェイまたはゲートウェイのセットへの最小料金のルートのインスタンスを示すコンテナーです。</span><span class="sxs-lookup"><span data-stu-id="de882-212">This class is a container representing an instance of a least cost route to a gateway or set of gateways.</span></span> <span data-ttu-id="de882-213">この情報は、標準エディションを実行しているすべてのエンタープライズプールまたはサーバーが、発信した通話を、最もお得な方法で公衆交換電話網 (PSTN) にルーティングするために使用されます。</span><span class="sxs-lookup"><span data-stu-id="de882-213">This information is used by all Enterprise pools or servers running Standard Edition to route outgoing calls to the public switched telephone network (PSTN) in the most cost effective way.</span></span></p></td>
<td><p><span data-ttu-id="de882-214">Lync Server 2010 では廃止されています。</span><span class="sxs-lookup"><span data-stu-id="de882-214">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="de882-215">Msrtcsip-userenabled true-PhoneRoutes (廃止)</span><span class="sxs-lookup"><span data-stu-id="de882-215">msRTCSIP-PhoneRoutes (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="de882-216">このクラスは、コストが最小の複数のルートのコンテナーであり、属性自体は含まれません。</span><span class="sxs-lookup"><span data-stu-id="de882-216">This class is a container for multiple, least cost routes and does not contain any attributes itself.</span></span></p></td>
<td><p><span data-ttu-id="de882-217">Lync Server 2010 では廃止されています。</span><span class="sxs-lookup"><span data-stu-id="de882-217">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="de882-218">Msrtcsip-userenabled true-ポリシー (廃止)</span><span class="sxs-lookup"><span data-stu-id="de882-218">msRTCSIP-Policies (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="de882-219">このクラスには、複数の Lync Server ポリシークラスが含まれており、属性自体は含まれていません。</span><span class="sxs-lookup"><span data-stu-id="de882-219">This class holds multiple Lync Server policy classes and does not have any attributes itself.</span></span></p></td>
<td><p><span data-ttu-id="de882-220">Lync Server 2010 では廃止されています。</span><span class="sxs-lookup"><span data-stu-id="de882-220">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="de882-221">Msrtcsip-userenabled true プール</span><span class="sxs-lookup"><span data-stu-id="de882-221">msRTCSIP-Pool</span></span></p></td>
<td><p><span data-ttu-id="de882-222">このクラスは、単一の Lync サーバープールを表します。</span><span class="sxs-lookup"><span data-stu-id="de882-222">This class represents a single Lync Server pool.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="de882-223">Msrtcsip-userenabled true-プール</span><span class="sxs-lookup"><span data-stu-id="de882-223">msRTCSIP-Pools</span></span></p></td>
<td><p><span data-ttu-id="de882-224">このクラスは、複数の Lync Server プールを保持しており、属性自体を持ちません。</span><span class="sxs-lookup"><span data-stu-id="de882-224">This class holds multiple Lync Server pools and does not have any attributes itself.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="de882-225">Msrtcsip-userenabled true-PoolService</span><span class="sxs-lookup"><span data-stu-id="de882-225">msRTCSIP-PoolService</span></span></p></td>
<td><p><span data-ttu-id="de882-226">このクラスは、プールのサービス制御ポイントサービス制御ポイントを表します。</span><span class="sxs-lookup"><span data-stu-id="de882-226">This class represents the service control pointservice control point of a pool.</span></span> <span data-ttu-id="de882-227">プールでホストされているユーザーの Msrtcsip-userenabled true 属性ポイントは、このクラスのインスタンスになります。</span><span class="sxs-lookup"><span data-stu-id="de882-227">Users hosted on a pool have their msRTCSIP-PrimaryHomeServer attribute point to an instance of this class.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="de882-228">Msrtcsip-userenabled true-プレゼンス</span><span class="sxs-lookup"><span data-stu-id="de882-228">msRTCSIP-Presence</span></span></p></td>
<td><p><span data-ttu-id="de882-229">グローバルプレゼンス設定を格納するコンテナー。</span><span class="sxs-lookup"><span data-stu-id="de882-229">Container that stores the global presence settings.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="de882-230">Msrtcsip-userenabled true-レジストラー</span><span class="sxs-lookup"><span data-stu-id="de882-230">msRTCSIP-Registrar</span></span></p></td>
<td><p><span data-ttu-id="de882-231">この補助クラス to Msrtcsip-userenabled true-GlobalContainer は、SIP レジストラーサーバーによって管理されるユーザー設定を表す属性を保持します。</span><span class="sxs-lookup"><span data-stu-id="de882-231">This auxiliary class to msRTCSIP-GlobalContainer holds attributes representing user settings maintained by the SIP Registrar servers.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="de882-232">Msrtcsip-userenabled true-RouteUsage (廃止)</span><span class="sxs-lookup"><span data-stu-id="de882-232">msRTCSIP-RouteUsage (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="de882-233">このクラスは、電話ルートの使用状況のインスタンスを表すコンテナーです。</span><span class="sxs-lookup"><span data-stu-id="de882-233">This class is a container representing an instance of a phone route usage.</span></span> <span data-ttu-id="de882-234">電話ルートの利用状況クラスは、属性フィールドと説明フィールドで構成されます。</span><span class="sxs-lookup"><span data-stu-id="de882-234">A phone route usage class consists of an attribute field and a description field.</span></span> <span data-ttu-id="de882-235">属性フィールドには、使用の種類が定義されています。</span><span class="sxs-lookup"><span data-stu-id="de882-235">The attribute field defines a usage type.</span></span> <span data-ttu-id="de882-236">[説明] フィールドでは、管理者が電話ルートでこの属性の使用を説明できます。</span><span class="sxs-lookup"><span data-stu-id="de882-236">The description field allows administrators to describe the usage for this attribute in the phone route.</span></span></p></td>
<td><p><span data-ttu-id="de882-237">Lync Server 2010 では廃止されています。</span><span class="sxs-lookup"><span data-stu-id="de882-237">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="de882-238">Msrtcsip-userenabled true-RouteUsages (廃止)</span><span class="sxs-lookup"><span data-stu-id="de882-238">msRTCSIP-RouteUsages (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="de882-239">このクラスは、Msrtcsip-userenabled true-RouteUsage クラスの複数のインスタンスを保持します。属性自体はありません。</span><span class="sxs-lookup"><span data-stu-id="de882-239">This class holds multiple instances of the msRTCSIP-RouteUsage class and does not have any attributes itself.</span></span></p></td>
<td><p><span data-ttu-id="de882-240">Lync Server 2010 では廃止されています。</span><span class="sxs-lookup"><span data-stu-id="de882-240">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="de882-241">Msrtcsip-userenabled true-検索</span><span class="sxs-lookup"><span data-stu-id="de882-241">msRTCSIP-Search</span></span></p></td>
<td><p><span data-ttu-id="de882-242">この補助クラス to Msrtcsip-userenabled true-GlobalContainer は、検索結果の範囲を制限および制御する属性を保持します。</span><span class="sxs-lookup"><span data-stu-id="de882-242">This auxiliary class to msRTCSIP-GlobalContainer holds attributes that limit and control the scope of search results.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="de882-243">Msrtcsip-userenabled true-サーバー</span><span class="sxs-lookup"><span data-stu-id="de882-243">msRTCSIP-Server</span></span></p></td>
<td><p><span data-ttu-id="de882-244">このクラスは、Lync Server を実行している1台のサーバーを表します。</span><span class="sxs-lookup"><span data-stu-id="de882-244">This class represents a single server running Lync Server.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="de882-245">Msrtcsip-userenabled true-サービス</span><span class="sxs-lookup"><span data-stu-id="de882-245">msRTCSIP-Service</span></span></p></td>
<td><p><span data-ttu-id="de882-246">このクラスは、グローバル設定コンテナーと Msrtcsip-userenabled true オブジェクトを保持します。</span><span class="sxs-lookup"><span data-stu-id="de882-246">This class holds the global settings container and msRTCSIP-Domain objects.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="de882-247">Msrtcsip-userenabled true-TrustedMCU</span><span class="sxs-lookup"><span data-stu-id="de882-247">msRTCSIP-TrustedMCU</span></span></p></td>
<td><p><span data-ttu-id="de882-248">このクラスは、信頼できる会議サーバーの設定を表す属性を保持します。</span><span class="sxs-lookup"><span data-stu-id="de882-248">This class holds attributes that represent settings for a trusted Conferencing server.</span></span></p></td>
<td><p><span data-ttu-id="de882-249">Communications Server 2007 の新サービスです。</span><span class="sxs-lookup"><span data-stu-id="de882-249">New in Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="de882-250">Msrtcsip-userenabled true-TrustedMCUs</span><span class="sxs-lookup"><span data-stu-id="de882-250">msRTCSIP-TrustedMCUs</span></span></p></td>
<td><p><span data-ttu-id="de882-251">このクラスには、Msrtcsip-userenabled true の複数のインスタンスが含まれており、属性自体はありません。</span><span class="sxs-lookup"><span data-stu-id="de882-251">This class holds multiple instances of the msRTCSIP-TrustedMCU class and does not have any attributes itself.</span></span></p></td>
<td><p><span data-ttu-id="de882-252">Communications Server 2007 の新サービスです。</span><span class="sxs-lookup"><span data-stu-id="de882-252">New in Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="de882-253">Msrtcsip-userenabled true-TrustedProxies</span><span class="sxs-lookup"><span data-stu-id="de882-253">msRTCSIP-TrustedProxies</span></span></p></td>
<td><p><span data-ttu-id="de882-254">このクラスは、複数の Msrtcsip-userenabled true プロキシクラスを保持し、属性自体は含まれません。</span><span class="sxs-lookup"><span data-stu-id="de882-254">This class holds multiple msRTCSIP-TrustedProxy classes and does not contain any attributes itself.</span></span></p></td>
<td><p><span data-ttu-id="de882-255">Communications Server 2007 の新サービスです。</span><span class="sxs-lookup"><span data-stu-id="de882-255">New in Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="de882-256">Msrtcsip-userenabled true-TrustedProxy</span><span class="sxs-lookup"><span data-stu-id="de882-256">msRTCSIP-TrustedProxy</span></span></p></td>
<td><p><span data-ttu-id="de882-257">このクラスは、プロキシサーバーを実行しているサーバーを表すコンテナーです。</span><span class="sxs-lookup"><span data-stu-id="de882-257">This class is a container representing a server running Proxy Server.</span></span> <span data-ttu-id="de882-258">このクラスのインスタンスは、AD DS に参加しているコンピューターで新しいプロキシサーバーをアクティブ化するときに作成されます。</span><span class="sxs-lookup"><span data-stu-id="de882-258">An instance of this class is created when activating a new Proxy Server on a computer joined to AD DS.</span></span></p></td>
<td><p><span data-ttu-id="de882-259">Communications Server 2007 の新サービスです。</span><span class="sxs-lookup"><span data-stu-id="de882-259">New in Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="de882-260">Msrtcsip-userenabled true-TrustedServer</span><span class="sxs-lookup"><span data-stu-id="de882-260">msRTCSIP-TrustedServer</span></span></p></td>
<td><p><span data-ttu-id="de882-261">このクラスは、信頼されたサーバーの設定を表す属性を保持します。</span><span class="sxs-lookup"><span data-stu-id="de882-261">This class holds attributes that represent settings for a trusted server.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="de882-262">Msrtcsip-userenabled true-TrustedService</span><span class="sxs-lookup"><span data-stu-id="de882-262">msRTCSIP-TrustedService</span></span></p></td>
<td><p><span data-ttu-id="de882-263">このクラスは、グローバルルーティング可能なユーザーエージェント URI (GRUU) アドレスを使ってルーティング可能な、信頼されたサービスを表すコンテナーです。</span><span class="sxs-lookup"><span data-stu-id="de882-263">This class is a container representing a trusted service that is routable using a Globally Routable User Agent URI (GRUU) address.</span></span> <span data-ttu-id="de882-264">このクラスのインスタンスは、Lync Server によって信頼されている新しいサーバーがアクティブ化されたときに作成されます。</span><span class="sxs-lookup"><span data-stu-id="de882-264">An instance of this class is created when a new server that is trusted by Lync Server is activated.</span></span> <span data-ttu-id="de882-265">この信頼できるサーバーは Active Directory ドメインに参加している必要があります。</span><span class="sxs-lookup"><span data-stu-id="de882-265">This trusted server must be joined to an Active Directory domain.</span></span></p></td>
<td><p><span data-ttu-id="de882-266">Communications Server 2007 の新サービスです。</span><span class="sxs-lookup"><span data-stu-id="de882-266">New in Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="de882-267">Msrtcsip-userenabled true-TrustedServices</span><span class="sxs-lookup"><span data-stu-id="de882-267">msRTCSIP-TrustedServices</span></span></p></td>
<td><p><span data-ttu-id="de882-268">このクラスは、複数の GRUU サーバーのコンテナーであり、属性自体は含まれていません。</span><span class="sxs-lookup"><span data-stu-id="de882-268">This class is a container for multiple GRUU servers and does not contain any attributes itself.</span></span></p></td>
<td><p><span data-ttu-id="de882-269">Communications Server 2007 の新サービスです。</span><span class="sxs-lookup"><span data-stu-id="de882-269">New in Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="de882-270">Msrtcsip-userenabled true-Trustedwebのサーバー</span><span class="sxs-lookup"><span data-stu-id="de882-270">msRTCSIP-TrustedWebComponentsServer</span></span></p></td>
<td><p><span data-ttu-id="de882-271">このクラスは、信頼された web コンポーネントの設定を表す属性を保持します。</span><span class="sxs-lookup"><span data-stu-id="de882-271">This class holds attributes that represent the settings for a trusted web component.</span></span></p></td>
<td><p><span data-ttu-id="de882-272">Communications Server 2007 の新サービスです。</span><span class="sxs-lookup"><span data-stu-id="de882-272">New in Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="de882-273">Msrtcsip-userenabled true-Trustedwebservers サーバー</span><span class="sxs-lookup"><span data-stu-id="de882-273">msRTCSIP-TrustedWebComponentsServers</span></span></p></td>
<td><p><span data-ttu-id="de882-274">このクラスは、Msrtcsip-userenabled true Webcomponentserver クラスの複数のインスタンスを保持します。属性自体はありません。</span><span class="sxs-lookup"><span data-stu-id="de882-274">This class holds multiple instances of the msRTCSIP-TrustedWebComponentServer class and does not have any attributes itself.</span></span></p></td>
<td><p><span data-ttu-id="de882-275">Communications Server 2007 の新サービスです。</span><span class="sxs-lookup"><span data-stu-id="de882-275">New in Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="de882-276">Msrtcsip-userenabled true-UnifiedCommunications (廃止)</span><span class="sxs-lookup"><span data-stu-id="de882-276">msRTCSIP-UnifiedCommunications (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="de882-277">この補助クラスの Msrtcsip-userenabled true-GlobalContainer は、統合された通信に関連する属性を保持します。</span><span class="sxs-lookup"><span data-stu-id="de882-277">This auxiliary class to msRTCSIP-GlobalContainer holds attributes related to unified communications.</span></span></p></td>
<td><p><span data-ttu-id="de882-278">Lync Server 2010 では廃止されています。</span><span class="sxs-lookup"><span data-stu-id="de882-278">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="de882-279">Msrtcsip-userenabled true-Web コンポーネント</span><span class="sxs-lookup"><span data-stu-id="de882-279">msRTCSIP-WebComponents</span></span></p></td>
<td><p><span data-ttu-id="de882-280">このクラスは、インターネットインフォメーションサーバー (IIS) のサービスコントロールポイントサービス制御ポイントを保持します。</span><span class="sxs-lookup"><span data-stu-id="de882-280">This class holds the service control pointservice control point for Internet Information Server (IIS).</span></span> <span data-ttu-id="de882-281">Web コンポーネントサーバーとしてサーバーを識別します。</span><span class="sxs-lookup"><span data-stu-id="de882-281">It identifies a server as a web components server.</span></span></p></td>
<td><p><span data-ttu-id="de882-282">Communications Server 2007 の新サービスです。</span><span class="sxs-lookup"><span data-stu-id="de882-282">New in Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="de882-283">Msrtcsip-userenabled true-Webmessages サービス</span><span class="sxs-lookup"><span data-stu-id="de882-283">msRTCSIP-WebComponentsService</span></span></p></td>
<td><p><span data-ttu-id="de882-284">このクラスは、プールで使用される web コンポーネントと特定のプールとの関連付けを提供します。</span><span class="sxs-lookup"><span data-stu-id="de882-284">This class provides an association from a specific pool to the web components that the pool will use.</span></span></p></td>
<td><p><span data-ttu-id="de882-285">Communications Server 2007 の新サービスです。</span><span class="sxs-lookup"><span data-stu-id="de882-285">New in Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="de882-286">Msrtcsip-userenabled true-WebComponentSettings</span><span class="sxs-lookup"><span data-stu-id="de882-286">msRTCSIP-WebComponentSettings</span></span></p></td>
<td><p><span data-ttu-id="de882-287">この補助クラスの Msrtcsip-userenabled true コンポーネントは、web コンポーネントの設定を表す属性を保持します。</span><span class="sxs-lookup"><span data-stu-id="de882-287">This auxiliary class to msRTCSIP-WebComponents holds attributes representing settings for web components.</span></span></p></td>
<td><p><span data-ttu-id="de882-288">Communications Server 2007 の新サービスです。</span><span class="sxs-lookup"><span data-stu-id="de882-288">New in Communications Server 2007.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

