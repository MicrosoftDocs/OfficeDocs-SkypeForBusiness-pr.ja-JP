---
title: 'Lync Server 2013: スキーマのクラスと説明'
description: 'Lync Server 2013: スキーマのクラスと説明。'
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
ms.openlocfilehash: ec27c2e00a7f969dbc13c91b06313c8045894a9e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48557103"
---
# <a name="schema-classes-and-descriptions-in-lync-server-2013"></a><span data-ttu-id="95e40-103">Lync Server 2013 のスキーマクラスと説明</span><span class="sxs-lookup"><span data-stu-id="95e40-103">Schema classes and descriptions in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="95e40-104">_**トピックの最終更新日:** 2012-10-30_</span><span class="sxs-lookup"><span data-stu-id="95e40-104">_**Topic Last Modified:** 2012-10-30_</span></span>

<span data-ttu-id="95e40-105">このセクションでは、Lync Server 2013 で使用されるすべてのスキーマクラスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="95e40-105">This section describes all the schema classes used by Lync Server 2013.</span></span>

<div>

## <a name="schema-classes-and-descriptions"></a><span data-ttu-id="95e40-106">スキーマのクラスと説明</span><span class="sxs-lookup"><span data-stu-id="95e40-106">Schema Classes and Descriptions</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="95e40-107">クラス</span><span class="sxs-lookup"><span data-stu-id="95e40-107">Class</span></span></th>
<th><span data-ttu-id="95e40-108">説明</span><span class="sxs-lookup"><span data-stu-id="95e40-108">Description</span></span></th>
<th><span data-ttu-id="95e40-109">Comments</span><span class="sxs-lookup"><span data-stu-id="95e40-109">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="95e40-110">Mail-Recipient</span><span class="sxs-lookup"><span data-stu-id="95e40-110">Mail-Recipient</span></span></p></td>
<td><p><span data-ttu-id="95e40-111">Exchange ユニファイドメッセージング (UM) 電子メール受信者。</span><span class="sxs-lookup"><span data-stu-id="95e40-111">Exchange Unified Messaging (UM) email recipient.</span></span></p></td>
<td><p><span data-ttu-id="95e40-112">この補助クラスは、Exchange UM と共有されています。</span><span class="sxs-lookup"><span data-stu-id="95e40-112">This auxiliary class is shared with Exchange UM.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95e40-113">msRTCSIP-ApplicationContacts</span><span class="sxs-lookup"><span data-stu-id="95e40-113">msRTCSIP-ApplicationContacts</span></span></p></td>
<td><p><span data-ttu-id="95e40-114">複数のアプリケーションの連絡先のコンテナーです。属性そのものは含まれません。</span><span class="sxs-lookup"><span data-stu-id="95e40-114">This class is a container for multiple application contacts and does not contain any attributes itself.</span></span></p></td>
<td><p><span data-ttu-id="95e40-115">Microsoft Office Communications Server 2007 R2 の新製品。</span><span class="sxs-lookup"><span data-stu-id="95e40-115">New in Microsoft Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="95e40-116">msRTCSIP-ApplicationServer</span><span class="sxs-lookup"><span data-stu-id="95e40-116">msRTCSIP-ApplicationServer</span></span></p></td>
<td><p><span data-ttu-id="95e40-117">統合コミュニケーション アプリケーション サービス (UCAS) のインスタンスのサービス制御ポイントのエントリを保持するクラスです。</span><span class="sxs-lookup"><span data-stu-id="95e40-117">This class holds the entry for the service control point for an instance of Unified Communications Application Services (UCAS).</span></span></p></td>
<td><p><span data-ttu-id="95e40-118">Office Communications Server 2007 R2 の新製品。</span><span class="sxs-lookup"><span data-stu-id="95e40-118">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95e40-119">msRTCSIP-ApplicationServerService</span><span class="sxs-lookup"><span data-stu-id="95e40-119">msRTCSIP-ApplicationServerService</span></span></p></td>
<td><p><span data-ttu-id="95e40-120">このクラスは、特定のプールからそのアプリケーションサービスへの関連付けを提供します。</span><span class="sxs-lookup"><span data-stu-id="95e40-120">This class provides an association from a specific pool to its Application service.</span></span></p></td>
<td><p><span data-ttu-id="95e40-121">Communications Server 2007 R2 の新サービス。</span><span class="sxs-lookup"><span data-stu-id="95e40-121">New in Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="95e40-122">msRTCSIP-ApplicationServerSettings</span><span class="sxs-lookup"><span data-stu-id="95e40-122">msRTCSIP-ApplicationServerSettings</span></span></p></td>
<td><p><span data-ttu-id="95e40-123">この補助クラスから msRTCSIP への ApplicationServer は、アプリケーションサービスのインスタンスの設定を表す属性を保持します。</span><span class="sxs-lookup"><span data-stu-id="95e40-123">This auxiliary class to msRTCSIP-ApplicationServer holds attributes representing settings for instances of the Application service.</span></span></p></td>
<td><p><span data-ttu-id="95e40-124">Communications Server 2007 R2 の新サービス。</span><span class="sxs-lookup"><span data-stu-id="95e40-124">New in Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95e40-125">msRTCSIP-Archive (廃止)</span><span class="sxs-lookup"><span data-stu-id="95e40-125">msRTCSIP-Archive (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="95e40-126">アーカイブに関連するすべての設定を保持する msRTCSIP-GlobalContainer の補助型クラスです。</span><span class="sxs-lookup"><span data-stu-id="95e40-126">This auxiliary class to msRTCSIP-GlobalContainer holds all settings related to archiving.</span></span></p></td>
<td><p><span data-ttu-id="95e40-127">Lync Server 2010 では廃止されました。</span><span class="sxs-lookup"><span data-stu-id="95e40-127">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="95e40-128">msRTCSIP-ArchivingServer (廃止)</span><span class="sxs-lookup"><span data-stu-id="95e40-128">msRTCSIP-ArchivingServer (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="95e40-p101">1 つのインスタント メッセージング アーカイブ サーバーを表すクラスです。 このクラスのインスタンスは、コンピューター (インスタント メッセージング アーカイブ サービスがインストールされたコンピューターなど) がインスタント メッセージング アーカイブ サーバーとしてアクティブ化されると作成されます。</span><span class="sxs-lookup"><span data-stu-id="95e40-p101">This class represents a single instant messaging Archiving Server. An instance of this class is created when a computer is activated as an instant messaging Archiving Server, such as a computer with the Instant Messaging Archiving service installed.</span></span></p></td>
<td><p><span data-ttu-id="95e40-131">Lync Server 2010 では廃止されました。</span><span class="sxs-lookup"><span data-stu-id="95e40-131">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95e40-132">msRTCSIP-Microsoft.rtc.management.writableconfig.settings.pstnconf.conferencedirectories</span><span class="sxs-lookup"><span data-stu-id="95e40-132">msRTCSIP-ConferenceDirectories</span></span></p></td>
<td><p><span data-ttu-id="95e40-133">会議ディレクトリの複数のインスタンスを格納するコンテナーです。属性そのものは含まれません。</span><span class="sxs-lookup"><span data-stu-id="95e40-133">This class is a container for multiple instances of conference directories and does not contain any attributes itself.</span></span></p></td>
<td><p><span data-ttu-id="95e40-134">Communications Server 2007 R2 の新サービス。</span><span class="sxs-lookup"><span data-stu-id="95e40-134">New in Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="95e40-135">msRTCSIP-ConferenceDirectory</span><span class="sxs-lookup"><span data-stu-id="95e40-135">msRTCSIP-ConferenceDirectory</span></span></p></td>
<td><p><span data-ttu-id="95e40-136">特定の会議ディレクトリの設定を表す属性を保持します。</span><span class="sxs-lookup"><span data-stu-id="95e40-136">This class holds attributes representing settings for a specific conference directory.</span></span></p></td>
<td><p><span data-ttu-id="95e40-137">Communications Server 2007 R2 の新サービス。</span><span class="sxs-lookup"><span data-stu-id="95e40-137">New in Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95e40-138">msRTCSIP-Msrtcsip-connectionpoint</span><span class="sxs-lookup"><span data-stu-id="95e40-138">msRTCSIP-ConnectionPoint</span></span></p></td>
<td><p><span data-ttu-id="95e40-139">Lync Server を実行しているサーバーとしてコンピューターを指定する汎用サービス制御ポイント (SCP)。</span><span class="sxs-lookup"><span data-stu-id="95e40-139">Generic service control point (SCP) to specify the computer as a server running Lync Server.</span></span></p></td>
<td><p><span data-ttu-id="95e40-140">Lync 2010 の新。</span><span class="sxs-lookup"><span data-stu-id="95e40-140">New in Lync 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="95e40-141">msRTCSIP-DefaultCWABank</span><span class="sxs-lookup"><span data-stu-id="95e40-141">msRTCSIP-DefaultCWABank</span></span></p></td>
<td><p><span data-ttu-id="95e40-142">この補助クラスは、Microsoft Lync Web App bank の設定を保持します。</span><span class="sxs-lookup"><span data-stu-id="95e40-142">This auxiliary class holds the settings for a Microsoft Lync Web App bank.</span></span></p></td>
<td><p><span data-ttu-id="95e40-143">Communications Server 2007 R2 の新サービス。</span><span class="sxs-lookup"><span data-stu-id="95e40-143">New in Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95e40-144">msRTCSIP-ドメイン</span><span class="sxs-lookup"><span data-stu-id="95e40-144">msRTCSIP-Domain</span></span></p></td>
<td><p><span data-ttu-id="95e40-145">SIP レジストラーの構成済みドメインを定義する属性を保持するクラスです。</span><span class="sxs-lookup"><span data-stu-id="95e40-145">This class holds attributes that define the configured domains of the SIP Registrar.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="95e40-146">msRTCSIP-EdgeProxy</span><span class="sxs-lookup"><span data-stu-id="95e40-146">msRTCSIP-EdgeProxy</span></span></p></td>
<td><p><span data-ttu-id="95e40-147">このクラスコンテナーは、1つのアクセスエッジサービスを表します。</span><span class="sxs-lookup"><span data-stu-id="95e40-147">This class container represents a single Access Edge service.</span></span> <span data-ttu-id="95e40-148">アクセスエッジサービスは境界ネットワークに展開され、ユーザーは通常、境界ネットワークからの Active Directory ドメインサービスのアクセスを許可していないため、アクセスエッジサービスのインスタンスはイントラネットの Active Directory ネットワークには参加しません。</span><span class="sxs-lookup"><span data-stu-id="95e40-148">Because an Access Edge service is deployed in the perimeter network and customers usually do not allow Active Directory Domain Services access from the perimeter network, instances of Access Edge service are not joined to the intranet’s Active Directory network.</span></span> <span data-ttu-id="95e40-149">したがって、アクセス プロキシは、自動的には AD DS に登録されません。</span><span class="sxs-lookup"><span data-stu-id="95e40-149">Therefore, Access Proxies are not automatically registered in AD DS.</span></span> <span data-ttu-id="95e40-150">管理者は、AD DS のアクセスエッジサービスの各インスタンスの存在を手動で構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="95e40-150">The administrator must manually configure the existence of each instance of Access Edge service in AD DS.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95e40-151">msRTCSIP-EnterpriseMCUSettings</span><span class="sxs-lookup"><span data-stu-id="95e40-151">msRTCSIP-EnterpriseMCUSettings</span></span></p></td>
<td><p><span data-ttu-id="95e40-152">電話会議サーバーの設定を表す属性を保持する msRTCSIP-MCU の補助型クラスです。</span><span class="sxs-lookup"><span data-stu-id="95e40-152">This auxiliary class to msRTCSIP-MCU holds attributes representing settings for Conferencing servers.</span></span></p></td>
<td><p><span data-ttu-id="95e40-153">Microsoft Office Communications Server 2007 の新製品。</span><span class="sxs-lookup"><span data-stu-id="95e40-153">New in Microsoft Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="95e40-154">msRTCSIP-EnterpriseMediationServerSettings</span><span class="sxs-lookup"><span data-stu-id="95e40-154">msRTCSIP-EnterpriseMediationServerSettings</span></span></p></td>
<td><p><span data-ttu-id="95e40-155">仲介サーバーの設定を表す属性を保持する msRTCSIP-MediationServer の補助型クラスです。</span><span class="sxs-lookup"><span data-stu-id="95e40-155">This auxiliary class to msRTCSIP-MediationServer holds attributes representing settings for Mediation Servers.</span></span></p></td>
<td><p><span data-ttu-id="95e40-156">Office Communications Server 2007 の新製品。</span><span class="sxs-lookup"><span data-stu-id="95e40-156">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95e40-157">msRTCSIP-EnterpriseServerSettings</span><span class="sxs-lookup"><span data-stu-id="95e40-157">msRTCSIP-EnterpriseServerSettings</span></span></p></td>
<td><p><span data-ttu-id="95e40-158">SIP サーバーの設定を表す属性を保持する msRTCSIP-Server の補助型クラスです。</span><span class="sxs-lookup"><span data-stu-id="95e40-158">This auxiliary class to msRTCSIP-Server holds attributes representing settings for SIP servers.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="95e40-159">msRTCSIP</span><span class="sxs-lookup"><span data-stu-id="95e40-159">msRTCSIP-Federation</span></span></p></td>
<td><p><span data-ttu-id="95e40-160">フェデレーションに関連するすべての設定を保持する msRTCSIP-GlobalContainer の補助型クラスです。</span><span class="sxs-lookup"><span data-stu-id="95e40-160">This auxiliary class to msRTCSIP-GlobalContainer holds all settings related to federation.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95e40-161">msRTCSIP-GlobalContainer</span><span class="sxs-lookup"><span data-stu-id="95e40-161">msRTCSIP-GlobalContainer</span></span></p></td>
<td><p><span data-ttu-id="95e40-162">このクラスは、Lync Server 展開全体で適用されるすべての設定を保持します。</span><span class="sxs-lookup"><span data-stu-id="95e40-162">This class holds all settings that apply throughout a Lync Server deployment.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="95e40-163">msRTCSIP-GlobalUserPolicy (廃止)</span><span class="sxs-lookup"><span data-stu-id="95e40-163">msRTCSIP-GlobalUserPolicy (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="95e40-164">このクラスは、1つの Office Communications Server 会議ポリシーを表します。</span><span class="sxs-lookup"><span data-stu-id="95e40-164">This class represents a single Office Communications Server meeting policy.</span></span></p></td>
<td><p><span data-ttu-id="95e40-165">Lync Server 2010 では廃止されました。</span><span class="sxs-lookup"><span data-stu-id="95e40-165">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95e40-166">msRTCSIP-GlobalTopologySetting</span><span class="sxs-lookup"><span data-stu-id="95e40-166">msRTCSIP-GlobalTopologySetting</span></span></p></td>
<td><p><span data-ttu-id="95e40-167">ローカルのグローバル トポロジ設定オブジェクトです。</span><span class="sxs-lookup"><span data-stu-id="95e40-167">The local global topology setting object.</span></span></p></td>
<td><p><span data-ttu-id="95e40-168">Lync Server 2010 の新。</span><span class="sxs-lookup"><span data-stu-id="95e40-168">New in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="95e40-169">msRTCSIP-GlobalTopologySettings</span><span class="sxs-lookup"><span data-stu-id="95e40-169">msRTCSIP-GlobalTopologySettings</span></span></p></td>
<td><p><span data-ttu-id="95e40-170">グローバル トポロジ設定オブジェクトを保持するコンテナーです。</span><span class="sxs-lookup"><span data-stu-id="95e40-170">Container to hold global topology setting objects.</span></span></p></td>
<td><p><span data-ttu-id="95e40-171">Lync Server 2010 の新。</span><span class="sxs-lookup"><span data-stu-id="95e40-171">New in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95e40-172">msRTCSIP-LocalNormalization</span><span class="sxs-lookup"><span data-stu-id="95e40-172">msRTCSIP-LocalNormalization</span></span></p></td>
<td><p><span data-ttu-id="95e40-173">ローカル正規化ルールのインスタンスを表すコンテナーです。</span><span class="sxs-lookup"><span data-stu-id="95e40-173">This class is a container that represents an instance of a location normalization rule.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="95e40-174">msRTCSIP-LocationContactMapping</span><span class="sxs-lookup"><span data-stu-id="95e40-174">msRTCSIP-LocationContactMapping</span></span></p></td>
<td><p><span data-ttu-id="95e40-175">このクラスは、会議アテンダントアプリケーションによって作成され、電話会議の電話番号を地域別に分類するために使用される属性を保持します。</span><span class="sxs-lookup"><span data-stu-id="95e40-175">This class is created by the Conferencing Attendant application and holds attributes used to categorize conference telephone numbers by region.</span></span></p></td>
<td><p><span data-ttu-id="95e40-176">Communications Server 2007 R2 の新サービス。</span><span class="sxs-lookup"><span data-stu-id="95e40-176">New in Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95e40-177">msRTCSIP-LocationContactMappings</span><span class="sxs-lookup"><span data-stu-id="95e40-177">msRTCSIP-LocationContactMappings</span></span></p></td>
<td><p><span data-ttu-id="95e40-178">場所と連絡先のマッピングの複数のインスタンスを保持するコンテナーです。属性そのものは含まれません。</span><span class="sxs-lookup"><span data-stu-id="95e40-178">This class is a container for multiple instances of location contact mappings and does not contain any attributes itself.</span></span></p></td>
<td><p><span data-ttu-id="95e40-179">Communications Server 2007 R2 の新サービス。</span><span class="sxs-lookup"><span data-stu-id="95e40-179">New in Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="95e40-180">msRTCSIP-LocationProfile</span><span class="sxs-lookup"><span data-stu-id="95e40-180">msRTCSIP-LocationProfile</span></span></p></td>
<td><p><span data-ttu-id="95e40-181">特定の場所のプロファイルを表すコンテナーです。</span><span class="sxs-lookup"><span data-stu-id="95e40-181">This class is a container that represents a specific location profile.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95e40-182">msRTCSIP-LocationProfiles (廃止)</span><span class="sxs-lookup"><span data-stu-id="95e40-182">msRTCSIP-LocationProfiles (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="95e40-183">複数の場所のプロファイルのコンテナーです。属性そのものは含まれません。</span><span class="sxs-lookup"><span data-stu-id="95e40-183">This class is a container for multiple location profiles and does not contain any attributes itself.</span></span></p></td>
<td><p><span data-ttu-id="95e40-184">Lync Server 2010 では廃止されました。</span><span class="sxs-lookup"><span data-stu-id="95e40-184">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="95e40-185">msRTCSIP-LocalNormalizations (廃止)</span><span class="sxs-lookup"><span data-stu-id="95e40-185">msRTCSIP-LocalNormalizations (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="95e40-186">複数のローカル正規化ルールのコンテナーです。属性そのものは含まれません。</span><span class="sxs-lookup"><span data-stu-id="95e40-186">This class is a container for multiple local normalization rules and does not contain any attributes itself.</span></span></p></td>
<td><p><span data-ttu-id="95e40-187">Lync Server 2010 では廃止されました。</span><span class="sxs-lookup"><span data-stu-id="95e40-187">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95e40-188">msRTCSIP-MCU</span><span class="sxs-lookup"><span data-stu-id="95e40-188">msRTCSIP-MCU</span></span></p></td>
<td><p><span data-ttu-id="95e40-189">1 つの電話会議サーバーを表すクラスです。</span><span class="sxs-lookup"><span data-stu-id="95e40-189">This class represents a single Conferencing server.</span></span></p></td>
<td><p><span data-ttu-id="95e40-190">Communications Server 2007 の新情報。</span><span class="sxs-lookup"><span data-stu-id="95e40-190">New in Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="95e40-191">msRTCSIP-MCUFactories</span><span class="sxs-lookup"><span data-stu-id="95e40-191">msRTCSIP-MCUFactories</span></span></p></td>
<td><p><span data-ttu-id="95e40-192">複数の msRTCSIP-MCUFactory クラスを保持するクラスです。属性そのものは含まれません。</span><span class="sxs-lookup"><span data-stu-id="95e40-192">This class holds multiple msRTCSIP-MCUFactory classes and does not have attributes itself.</span></span></p></td>
<td><p><span data-ttu-id="95e40-193">Communications Server 2007 の新情報。</span><span class="sxs-lookup"><span data-stu-id="95e40-193">New in Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95e40-194">msRTCSIP-MCUFactory</span><span class="sxs-lookup"><span data-stu-id="95e40-194">msRTCSIP-MCUFactory</span></span></p></td>
<td><p><span data-ttu-id="95e40-p103">1 つのメディアの種類の会議サーバー ファクトリを表すコンテナーです。 このクラスのインスタンスは、この特定の種類およびベンダーの最初の電話会議サーバーがアクティブ化されると作成されます。</span><span class="sxs-lookup"><span data-stu-id="95e40-p103">This class is a container representing a Conferencing Server Factory for a single medium type. An instance of this class is created when the first Conferencing server for this particular type and vendor is activated.</span></span></p></td>
<td><p><span data-ttu-id="95e40-197">Communications Server 2007 の新情報。</span><span class="sxs-lookup"><span data-stu-id="95e40-197">New in Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="95e40-198">msRTCSIP-MCUFactoryService</span><span class="sxs-lookup"><span data-stu-id="95e40-198">msRTCSIP-MCUFactoryService</span></span></p></td>
<td><p><span data-ttu-id="95e40-199">特定のプールからその会議サーバー ファクトリへの関連付けを提供するクラスです。</span><span class="sxs-lookup"><span data-stu-id="95e40-199">This class provides an association from a specific pool to its Conferencing Server Factory.</span></span></p></td>
<td><p><span data-ttu-id="95e40-200">Communications Server 2007 の新情報。</span><span class="sxs-lookup"><span data-stu-id="95e40-200">New in Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95e40-201">msRTCSIP-MediationServer</span><span class="sxs-lookup"><span data-stu-id="95e40-201">msRTCSIP-MediationServer</span></span></p></td>
<td><p><span data-ttu-id="95e40-202">仲介サーバーのサービス制御ポイントのエントリを保持するクラスです。</span><span class="sxs-lookup"><span data-stu-id="95e40-202">This class holds the entry for the service control point for a Mediation Server.</span></span></p></td>
<td><p><span data-ttu-id="95e40-203">Communications Server 2007 の新情報。</span><span class="sxs-lookup"><span data-stu-id="95e40-203">New in Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="95e40-204">msRTCSIP-Meeting (廃止)</span><span class="sxs-lookup"><span data-stu-id="95e40-204">msRTCSIP-Meeting (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="95e40-205">構成可能な会議の設定を表す属性を保持する msRTCSIP-GlobalContainer の補助型クラスです。</span><span class="sxs-lookup"><span data-stu-id="95e40-205">This auxiliary class to msRTCSIP-GlobalContainer holds attributes representing configurable meeting settings.</span></span></p></td>
<td><p><span data-ttu-id="95e40-206">Lync Server 2010 では廃止されました。</span><span class="sxs-lookup"><span data-stu-id="95e40-206">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95e40-207">msRTCSIP</span><span class="sxs-lookup"><span data-stu-id="95e40-207">msRTCSIP-Mobility</span></span></p></td>
<td><p><span data-ttu-id="95e40-208">グローバル モビリティ設定を格納するコンテナーです。</span><span class="sxs-lookup"><span data-stu-id="95e40-208">Container that stores the global mobility settings.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="95e40-209">msRTCSIP-MonitoringServer</span><span class="sxs-lookup"><span data-stu-id="95e40-209">msRTCSIP-MonitoringServer</span></span></p></td>
<td><p><span data-ttu-id="95e40-210">このクラスは、単一の監視サーバーの設定を表す属性を保持します。</span><span class="sxs-lookup"><span data-stu-id="95e40-210">This class holds attributes that represent settings for a single Monitoring Server.</span></span></p></td>
<td><p><span data-ttu-id="95e40-211">Communications Server 2007 R2 の新サービス。</span><span class="sxs-lookup"><span data-stu-id="95e40-211">New in Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95e40-212">msRTCSIP-PhoneRoute (廃止)</span><span class="sxs-lookup"><span data-stu-id="95e40-212">msRTCSIP-PhoneRoute (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="95e40-p104">ゲートウェイまたはゲートウェイのセットへの最小コスト経路のインスタンスを表すコンテナーです。 この情報は、すべてのエンタープライズ プールや Standard Edition サーバーによって、最もコストの小さい方法で、発信通話を公衆交換電話網 (PSTN) にルーティングするために使用されます。</span><span class="sxs-lookup"><span data-stu-id="95e40-p104">This class is a container representing an instance of a least cost route to a gateway or set of gateways. This information is used by all Enterprise pools or servers running Standard Edition to route outgoing calls to the public switched telephone network (PSTN) in the most cost effective way.</span></span></p></td>
<td><p><span data-ttu-id="95e40-215">Lync Server 2010 では廃止されました。</span><span class="sxs-lookup"><span data-stu-id="95e40-215">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="95e40-216">msRTCSIP-PhoneRoutes (廃止)</span><span class="sxs-lookup"><span data-stu-id="95e40-216">msRTCSIP-PhoneRoutes (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="95e40-217">複数の最小コスト経路のコンテナーです。属性そのものは含まれません。</span><span class="sxs-lookup"><span data-stu-id="95e40-217">This class is a container for multiple, least cost routes and does not contain any attributes itself.</span></span></p></td>
<td><p><span data-ttu-id="95e40-218">Lync Server 2010 では廃止されました。</span><span class="sxs-lookup"><span data-stu-id="95e40-218">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95e40-219">msRTCSIP-Policies (廃止)</span><span class="sxs-lookup"><span data-stu-id="95e40-219">msRTCSIP-Policies (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="95e40-220">複数の Lync Server ポリシークラスを保持するクラスです。属性そのものは含まれません。</span><span class="sxs-lookup"><span data-stu-id="95e40-220">This class holds multiple Lync Server policy classes and does not have any attributes itself.</span></span></p></td>
<td><p><span data-ttu-id="95e40-221">Lync Server 2010 では廃止されました。</span><span class="sxs-lookup"><span data-stu-id="95e40-221">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="95e40-222">msRTCSIP</span><span class="sxs-lookup"><span data-stu-id="95e40-222">msRTCSIP-Pool</span></span></p></td>
<td><p><span data-ttu-id="95e40-223">このクラスは、1つの Lync Server プールを表します。</span><span class="sxs-lookup"><span data-stu-id="95e40-223">This class represents a single Lync Server pool.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95e40-224">msRTCSIP</span><span class="sxs-lookup"><span data-stu-id="95e40-224">msRTCSIP-Pools</span></span></p></td>
<td><p><span data-ttu-id="95e40-225">複数の Lync Server プールを保持するクラスです。属性そのものは含まれません。</span><span class="sxs-lookup"><span data-stu-id="95e40-225">This class holds multiple Lync Server pools and does not have any attributes itself.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="95e40-226">msRTCSIP-PoolService</span><span class="sxs-lookup"><span data-stu-id="95e40-226">msRTCSIP-PoolService</span></span></p></td>
<td><p><span data-ttu-id="95e40-p105">プールのサービス制御ポイントを表すクラスです。プールでホストされるユーザーは、msRTCSIP-PrimaryHomeServer 属性をこのクラスのインスタンスに設定します。</span><span class="sxs-lookup"><span data-stu-id="95e40-p105">This class represents the service control pointservice control point of a pool. Users hosted on a pool have their msRTCSIP-PrimaryHomeServer attribute point to an instance of this class.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95e40-229">msRTCSIP-プレゼンス</span><span class="sxs-lookup"><span data-stu-id="95e40-229">msRTCSIP-Presence</span></span></p></td>
<td><p><span data-ttu-id="95e40-230">グローバル プレゼンス設定を格納するコンテナーです。</span><span class="sxs-lookup"><span data-stu-id="95e40-230">Container that stores the global presence settings.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="95e40-231">msRTCSIP</span><span class="sxs-lookup"><span data-stu-id="95e40-231">msRTCSIP-Registrar</span></span></p></td>
<td><p><span data-ttu-id="95e40-232">SIP レジストラー サーバーによって管理されるユーザー設定を表す属性を保持する msRTCSIP-GlobalContainer の補助型クラスです。</span><span class="sxs-lookup"><span data-stu-id="95e40-232">This auxiliary class to msRTCSIP-GlobalContainer holds attributes representing user settings maintained by the SIP Registrar servers.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95e40-233">msRTCSIP-RouteUsage (廃止)</span><span class="sxs-lookup"><span data-stu-id="95e40-233">msRTCSIP-RouteUsage (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="95e40-p106">電話ルート使用法のインスタンスを表すコンテナーです。電話ルート使用法クラスは、属性フィールドと説明フィールドで構成されています。属性フィールドは使用法の種類を定義します。管理者は説明フィールドに、電話ルートでのその属性の使用法の説明を記入できます。</span><span class="sxs-lookup"><span data-stu-id="95e40-p106">This class is a container representing an instance of a phone route usage. A phone route usage class consists of an attribute field and a description field. The attribute field defines a usage type. The description field allows administrators to describe the usage for this attribute in the phone route.</span></span></p></td>
<td><p><span data-ttu-id="95e40-238">Lync Server 2010 では廃止されました。</span><span class="sxs-lookup"><span data-stu-id="95e40-238">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="95e40-239">msRTCSIP-RouteUsages (廃止)</span><span class="sxs-lookup"><span data-stu-id="95e40-239">msRTCSIP-RouteUsages (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="95e40-240">msRTCSIP-RouteUsage クラスの複数のインスタンスを保持するクラスです。属性そのものは含まれません。</span><span class="sxs-lookup"><span data-stu-id="95e40-240">This class holds multiple instances of the msRTCSIP-RouteUsage class and does not have any attributes itself.</span></span></p></td>
<td><p><span data-ttu-id="95e40-241">Lync Server 2010 では廃止されました。</span><span class="sxs-lookup"><span data-stu-id="95e40-241">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95e40-242">msRTCSIP-検索</span><span class="sxs-lookup"><span data-stu-id="95e40-242">msRTCSIP-Search</span></span></p></td>
<td><p><span data-ttu-id="95e40-243">検索結果の範囲を制限および制御する属性を保持する msRTCSIP-GlobalContainer の補助型クラスです。</span><span class="sxs-lookup"><span data-stu-id="95e40-243">This auxiliary class to msRTCSIP-GlobalContainer holds attributes that limit and control the scope of search results.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="95e40-244">msRTCSIP-サーバー</span><span class="sxs-lookup"><span data-stu-id="95e40-244">msRTCSIP-Server</span></span></p></td>
<td><p><span data-ttu-id="95e40-245">このクラスは、Lync Server を実行している1台のサーバーを表します。</span><span class="sxs-lookup"><span data-stu-id="95e40-245">This class represents a single server running Lync Server.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95e40-246">msRTCSIP</span><span class="sxs-lookup"><span data-stu-id="95e40-246">msRTCSIP-Service</span></span></p></td>
<td><p><span data-ttu-id="95e40-247">グローバル設定コンテナーと msRTCSIP-Domain オブジェクトを保持するクラスです。</span><span class="sxs-lookup"><span data-stu-id="95e40-247">This class holds the global settings container and msRTCSIP-Domain objects.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="95e40-248">msRTCSIP-TrustedMCU</span><span class="sxs-lookup"><span data-stu-id="95e40-248">msRTCSIP-TrustedMCU</span></span></p></td>
<td><p><span data-ttu-id="95e40-249">1 つの信頼済み電話会議サーバーの設定を表す属性を保持するクラスです。</span><span class="sxs-lookup"><span data-stu-id="95e40-249">This class holds attributes that represent settings for a trusted Conferencing server.</span></span></p></td>
<td><p><span data-ttu-id="95e40-250">Communications Server 2007 の新情報。</span><span class="sxs-lookup"><span data-stu-id="95e40-250">New in Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95e40-251">msRTCSIP-TrustedMCUs</span><span class="sxs-lookup"><span data-stu-id="95e40-251">msRTCSIP-TrustedMCUs</span></span></p></td>
<td><p><span data-ttu-id="95e40-252">msRTCSIP-TrustedMCU クラスの複数のインスタンスを保持するクラスです。属性そのものは含まれません。</span><span class="sxs-lookup"><span data-stu-id="95e40-252">This class holds multiple instances of the msRTCSIP-TrustedMCU class and does not have any attributes itself.</span></span></p></td>
<td><p><span data-ttu-id="95e40-253">Communications Server 2007 の新情報。</span><span class="sxs-lookup"><span data-stu-id="95e40-253">New in Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="95e40-254">msRTCSIP-TrustedProxies</span><span class="sxs-lookup"><span data-stu-id="95e40-254">msRTCSIP-TrustedProxies</span></span></p></td>
<td><p><span data-ttu-id="95e40-255">複数の msRTCSIP-TrustedProxy クラスを保持するクラスです。属性そのものは含まれません。</span><span class="sxs-lookup"><span data-stu-id="95e40-255">This class holds multiple msRTCSIP-TrustedProxy classes and does not contain any attributes itself.</span></span></p></td>
<td><p><span data-ttu-id="95e40-256">Communications Server 2007 の新情報。</span><span class="sxs-lookup"><span data-stu-id="95e40-256">New in Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95e40-257">msRTCSIP-TrustedProxy</span><span class="sxs-lookup"><span data-stu-id="95e40-257">msRTCSIP-TrustedProxy</span></span></p></td>
<td><p><span data-ttu-id="95e40-p107">プロキシ サーバーを実行しているサーバーを表すコンテナーです。 このクラスのインスタンスは、AD DS に参加しているコンピューターで新しいプロキシ サーバーがアクティブ化されると作成されます。</span><span class="sxs-lookup"><span data-stu-id="95e40-p107">This class is a container representing a server running Proxy Server. An instance of this class is created when activating a new Proxy Server on a computer joined to AD DS.</span></span></p></td>
<td><p><span data-ttu-id="95e40-260">Communications Server 2007 の新情報。</span><span class="sxs-lookup"><span data-stu-id="95e40-260">New in Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="95e40-261">msRTCSIP-TrustedServer</span><span class="sxs-lookup"><span data-stu-id="95e40-261">msRTCSIP-TrustedServer</span></span></p></td>
<td><p><span data-ttu-id="95e40-262">1 つの信頼済みサーバーの設定を表す属性を保持するクラスです。</span><span class="sxs-lookup"><span data-stu-id="95e40-262">This class holds attributes that represent settings for a trusted server.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95e40-263">msRTCSIP-TrustedService</span><span class="sxs-lookup"><span data-stu-id="95e40-263">msRTCSIP-TrustedService</span></span></p></td>
<td><p><span data-ttu-id="95e40-264">グローバルにルーティング可能なユーザー エージェント (GRUU) アドレスを使用してルーティングできる信頼済みサービスを表すコンテナーです。</span><span class="sxs-lookup"><span data-stu-id="95e40-264">This class is a container representing a trusted service that is routable using a Globally Routable User Agent URI (GRUU) address.</span></span> <span data-ttu-id="95e40-265">このクラスのインスタンスは、Lync Server によって信頼されている新しいサーバーがアクティブ化されたときに作成されます。</span><span class="sxs-lookup"><span data-stu-id="95e40-265">An instance of this class is created when a new server that is trusted by Lync Server is activated.</span></span> <span data-ttu-id="95e40-266">この信頼済みサーバーは Active Directory ドメインに参加している必要があります。</span><span class="sxs-lookup"><span data-stu-id="95e40-266">This trusted server must be joined to an Active Directory domain.</span></span></p></td>
<td><p><span data-ttu-id="95e40-267">Communications Server 2007 の新情報。</span><span class="sxs-lookup"><span data-stu-id="95e40-267">New in Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="95e40-268">msRTCSIP-TrustedServices</span><span class="sxs-lookup"><span data-stu-id="95e40-268">msRTCSIP-TrustedServices</span></span></p></td>
<td><p><span data-ttu-id="95e40-269">複数の GRUU サーバーのコンテナーです。属性そのものは含まれません。</span><span class="sxs-lookup"><span data-stu-id="95e40-269">This class is a container for multiple GRUU servers and does not contain any attributes itself.</span></span></p></td>
<td><p><span data-ttu-id="95e40-270">Communications Server 2007 の新情報。</span><span class="sxs-lookup"><span data-stu-id="95e40-270">New in Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95e40-271">msRTCSIP-Trustedwebコンポーネントサーバー</span><span class="sxs-lookup"><span data-stu-id="95e40-271">msRTCSIP-TrustedWebComponentsServer</span></span></p></td>
<td><p><span data-ttu-id="95e40-272">1 つの信頼済み Web コンポーネントの設定を表す属性を保持するクラスです。</span><span class="sxs-lookup"><span data-stu-id="95e40-272">This class holds attributes that represent the settings for a trusted web component.</span></span></p></td>
<td><p><span data-ttu-id="95e40-273">Communications Server 2007 の新情報。</span><span class="sxs-lookup"><span data-stu-id="95e40-273">New in Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="95e40-274">msRTCSIP-Trustedwebコンポーネントサーバー</span><span class="sxs-lookup"><span data-stu-id="95e40-274">msRTCSIP-TrustedWebComponentsServers</span></span></p></td>
<td><p><span data-ttu-id="95e40-275">msRTCSIP-TrustedWebComponentServer クラスの複数のインスタンスを保持するクラスです。属性そのものは含まれません。</span><span class="sxs-lookup"><span data-stu-id="95e40-275">This class holds multiple instances of the msRTCSIP-TrustedWebComponentServer class and does not have any attributes itself.</span></span></p></td>
<td><p><span data-ttu-id="95e40-276">Communications Server 2007 の新情報。</span><span class="sxs-lookup"><span data-stu-id="95e40-276">New in Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95e40-277">msRTCSIP-UnifiedCommunications (廃止)</span><span class="sxs-lookup"><span data-stu-id="95e40-277">msRTCSIP-UnifiedCommunications (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="95e40-278">統合コミュニケーションに関連する属性を保持する msRTCSIP-GlobalContainer の補助型クラスです。</span><span class="sxs-lookup"><span data-stu-id="95e40-278">This auxiliary class to msRTCSIP-GlobalContainer holds attributes related to unified communications.</span></span></p></td>
<td><p><span data-ttu-id="95e40-279">Lync Server 2010 では廃止されました。</span><span class="sxs-lookup"><span data-stu-id="95e40-279">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="95e40-280">msRTCSIP-WebComponents</span><span class="sxs-lookup"><span data-stu-id="95e40-280">msRTCSIP-WebComponents</span></span></p></td>
<td><p><span data-ttu-id="95e40-p109">インターネット インフォメーション サーバー (IIS) のサービス制御ポイントを保持するクラスです。サーバーを Web コンポーネント サーバーとして識別します。</span><span class="sxs-lookup"><span data-stu-id="95e40-p109">This class holds the service control pointservice control point for Internet Information Server (IIS). It identifies a server as a web components server.</span></span></p></td>
<td><p><span data-ttu-id="95e40-283">Communications Server 2007 の新情報。</span><span class="sxs-lookup"><span data-stu-id="95e40-283">New in Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95e40-284">msRTCSIP-Webコンポーネントサービス</span><span class="sxs-lookup"><span data-stu-id="95e40-284">msRTCSIP-WebComponentsService</span></span></p></td>
<td><p><span data-ttu-id="95e40-285">特定のプールからそのプールが使用する Web コンポーネントへの関連付けを提供するクラスです。</span><span class="sxs-lookup"><span data-stu-id="95e40-285">This class provides an association from a specific pool to the web components that the pool will use.</span></span></p></td>
<td><p><span data-ttu-id="95e40-286">Communications Server 2007 の新情報。</span><span class="sxs-lookup"><span data-stu-id="95e40-286">New in Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="95e40-287">msRTCSIP-WebComponentSettings</span><span class="sxs-lookup"><span data-stu-id="95e40-287">msRTCSIP-WebComponentSettings</span></span></p></td>
<td><p><span data-ttu-id="95e40-288">Web コンポーネントの設定を表す属性を保持する msRTCSIP-WebComponents の補助型クラスです。</span><span class="sxs-lookup"><span data-stu-id="95e40-288">This auxiliary class to msRTCSIP-WebComponents holds attributes representing settings for web components.</span></span></p></td>
<td><p><span data-ttu-id="95e40-289">Communications Server 2007 の新情報。</span><span class="sxs-lookup"><span data-stu-id="95e40-289">New in Communications Server 2007.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

