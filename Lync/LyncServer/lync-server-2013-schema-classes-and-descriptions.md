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
ms.openlocfilehash: 3063e0dd6288f4b9248c93de57a6182a7ab20a8f
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42049399"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="schema-classes-and-descriptions-in-lync-server-2013"></a><span data-ttu-id="c4024-102">Lync Server 2013 のスキーマクラスと説明</span><span class="sxs-lookup"><span data-stu-id="c4024-102">Schema classes and descriptions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c4024-103">_**トピックの最終更新日:** 2012-10-30_</span><span class="sxs-lookup"><span data-stu-id="c4024-103">_**Topic Last Modified:** 2012-10-30_</span></span>

<span data-ttu-id="c4024-104">このセクションでは、Lync Server 2013 で使用されるすべてのスキーマクラスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="c4024-104">This section describes all the schema classes used by Lync Server 2013.</span></span>

<div>

## <a name="schema-classes-and-descriptions"></a><span data-ttu-id="c4024-105">スキーマのクラスと説明</span><span class="sxs-lookup"><span data-stu-id="c4024-105">Schema Classes and Descriptions</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c4024-106">クラス</span><span class="sxs-lookup"><span data-stu-id="c4024-106">Class</span></span></th>
<th><span data-ttu-id="c4024-107">説明</span><span class="sxs-lookup"><span data-stu-id="c4024-107">Description</span></span></th>
<th><span data-ttu-id="c4024-108">コメント</span><span class="sxs-lookup"><span data-stu-id="c4024-108">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c4024-109">Mail-Recipient</span><span class="sxs-lookup"><span data-stu-id="c4024-109">Mail-Recipient</span></span></p></td>
<td><p><span data-ttu-id="c4024-110">Exchange ユニファイドメッセージング (UM) 電子メール受信者。</span><span class="sxs-lookup"><span data-stu-id="c4024-110">Exchange Unified Messaging (UM) email recipient.</span></span></p></td>
<td><p><span data-ttu-id="c4024-111">この補助クラスは、Exchange UM と共有されています。</span><span class="sxs-lookup"><span data-stu-id="c4024-111">This auxiliary class is shared with Exchange UM.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c4024-112">msRTCSIP-ApplicationContacts</span><span class="sxs-lookup"><span data-stu-id="c4024-112">msRTCSIP-ApplicationContacts</span></span></p></td>
<td><p><span data-ttu-id="c4024-113">複数のアプリケーションの連絡先のコンテナーです。属性そのものは含まれません。</span><span class="sxs-lookup"><span data-stu-id="c4024-113">This class is a container for multiple application contacts and does not contain any attributes itself.</span></span></p></td>
<td><p><span data-ttu-id="c4024-114">Microsoft Office Communications Server 2007 R2 の新製品。</span><span class="sxs-lookup"><span data-stu-id="c4024-114">New in Microsoft Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c4024-115">msRTCSIP-ApplicationServer</span><span class="sxs-lookup"><span data-stu-id="c4024-115">msRTCSIP-ApplicationServer</span></span></p></td>
<td><p><span data-ttu-id="c4024-116">統合コミュニケーション アプリケーション サービス (UCAS) のインスタンスのサービス制御ポイントのエントリを保持するクラスです。</span><span class="sxs-lookup"><span data-stu-id="c4024-116">This class holds the entry for the service control point for an instance of Unified Communications Application Services (UCAS).</span></span></p></td>
<td><p><span data-ttu-id="c4024-117">Office Communications Server 2007 R2 の新製品。</span><span class="sxs-lookup"><span data-stu-id="c4024-117">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c4024-118">msRTCSIP-ApplicationServerService</span><span class="sxs-lookup"><span data-stu-id="c4024-118">msRTCSIP-ApplicationServerService</span></span></p></td>
<td><p><span data-ttu-id="c4024-119">このクラスは、特定のプールからそのアプリケーションサービスへの関連付けを提供します。</span><span class="sxs-lookup"><span data-stu-id="c4024-119">This class provides an association from a specific pool to its Application service.</span></span></p></td>
<td><p><span data-ttu-id="c4024-120">Communications Server 2007 R2 の新サービス。</span><span class="sxs-lookup"><span data-stu-id="c4024-120">New in Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c4024-121">msRTCSIP-ApplicationServerSettings</span><span class="sxs-lookup"><span data-stu-id="c4024-121">msRTCSIP-ApplicationServerSettings</span></span></p></td>
<td><p><span data-ttu-id="c4024-122">この補助クラスから msRTCSIP への ApplicationServer は、アプリケーションサービスのインスタンスの設定を表す属性を保持します。</span><span class="sxs-lookup"><span data-stu-id="c4024-122">This auxiliary class to msRTCSIP-ApplicationServer holds attributes representing settings for instances of the Application service.</span></span></p></td>
<td><p><span data-ttu-id="c4024-123">Communications Server 2007 R2 の新サービス。</span><span class="sxs-lookup"><span data-stu-id="c4024-123">New in Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c4024-124">msRTCSIP-Archive (廃止)</span><span class="sxs-lookup"><span data-stu-id="c4024-124">msRTCSIP-Archive (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="c4024-125">アーカイブに関連するすべての設定を保持する msRTCSIP-GlobalContainer の補助型クラスです。</span><span class="sxs-lookup"><span data-stu-id="c4024-125">This auxiliary class to msRTCSIP-GlobalContainer holds all settings related to archiving.</span></span></p></td>
<td><p><span data-ttu-id="c4024-126">Lync Server 2010 では廃止されました。</span><span class="sxs-lookup"><span data-stu-id="c4024-126">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c4024-127">msRTCSIP-ArchivingServer (廃止)</span><span class="sxs-lookup"><span data-stu-id="c4024-127">msRTCSIP-ArchivingServer (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="c4024-p101">1 つのインスタント メッセージング アーカイブ サーバーを表すクラスです。 このクラスのインスタンスは、コンピューター (インスタント メッセージング アーカイブ サービスがインストールされたコンピューターなど) がインスタント メッセージング アーカイブ サーバーとしてアクティブ化されると作成されます。</span><span class="sxs-lookup"><span data-stu-id="c4024-p101">This class represents a single instant messaging Archiving Server. An instance of this class is created when a computer is activated as an instant messaging Archiving Server, such as a computer with the Instant Messaging Archiving service installed.</span></span></p></td>
<td><p><span data-ttu-id="c4024-130">Lync Server 2010 では廃止されました。</span><span class="sxs-lookup"><span data-stu-id="c4024-130">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c4024-131">msRTCSIP-Microsoft.rtc.management.writableconfig.settings.pstnconf.conferencedirectories</span><span class="sxs-lookup"><span data-stu-id="c4024-131">msRTCSIP-ConferenceDirectories</span></span></p></td>
<td><p><span data-ttu-id="c4024-132">会議ディレクトリの複数のインスタンスを格納するコンテナーです。属性そのものは含まれません。</span><span class="sxs-lookup"><span data-stu-id="c4024-132">This class is a container for multiple instances of conference directories and does not contain any attributes itself.</span></span></p></td>
<td><p><span data-ttu-id="c4024-133">Communications Server 2007 R2 の新サービス。</span><span class="sxs-lookup"><span data-stu-id="c4024-133">New in Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c4024-134">msRTCSIP-ConferenceDirectory</span><span class="sxs-lookup"><span data-stu-id="c4024-134">msRTCSIP-ConferenceDirectory</span></span></p></td>
<td><p><span data-ttu-id="c4024-135">特定の会議ディレクトリの設定を表す属性を保持します。</span><span class="sxs-lookup"><span data-stu-id="c4024-135">This class holds attributes representing settings for a specific conference directory.</span></span></p></td>
<td><p><span data-ttu-id="c4024-136">Communications Server 2007 R2 の新サービス。</span><span class="sxs-lookup"><span data-stu-id="c4024-136">New in Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c4024-137">msRTCSIP-Msrtcsip-connectionpoint</span><span class="sxs-lookup"><span data-stu-id="c4024-137">msRTCSIP-ConnectionPoint</span></span></p></td>
<td><p><span data-ttu-id="c4024-138">Lync Server を実行しているサーバーとしてコンピューターを指定する汎用サービス制御ポイント (SCP)。</span><span class="sxs-lookup"><span data-stu-id="c4024-138">Generic service control point (SCP) to specify the computer as a server running Lync Server.</span></span></p></td>
<td><p><span data-ttu-id="c4024-139">Lync 2010 の新。</span><span class="sxs-lookup"><span data-stu-id="c4024-139">New in Lync 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c4024-140">msRTCSIP-DefaultCWABank</span><span class="sxs-lookup"><span data-stu-id="c4024-140">msRTCSIP-DefaultCWABank</span></span></p></td>
<td><p><span data-ttu-id="c4024-141">この補助クラスは、Microsoft Lync Web App bank の設定を保持します。</span><span class="sxs-lookup"><span data-stu-id="c4024-141">This auxiliary class holds the settings for a Microsoft Lync Web App bank.</span></span></p></td>
<td><p><span data-ttu-id="c4024-142">Communications Server 2007 R2 の新サービス。</span><span class="sxs-lookup"><span data-stu-id="c4024-142">New in Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c4024-143">msRTCSIP-ドメイン</span><span class="sxs-lookup"><span data-stu-id="c4024-143">msRTCSIP-Domain</span></span></p></td>
<td><p><span data-ttu-id="c4024-144">SIP レジストラーの構成済みドメインを定義する属性を保持するクラスです。</span><span class="sxs-lookup"><span data-stu-id="c4024-144">This class holds attributes that define the configured domains of the SIP Registrar.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c4024-145">msRTCSIP-EdgeProxy</span><span class="sxs-lookup"><span data-stu-id="c4024-145">msRTCSIP-EdgeProxy</span></span></p></td>
<td><p><span data-ttu-id="c4024-146">このクラスコンテナーは、1つのアクセスエッジサービスを表します。</span><span class="sxs-lookup"><span data-stu-id="c4024-146">This class container represents a single Access Edge service.</span></span> <span data-ttu-id="c4024-147">アクセスエッジサービスは境界ネットワークに展開され、ユーザーは通常、境界ネットワークからの Active Directory ドメインサービスのアクセスを許可していないため、アクセスエッジサービスのインスタンスはイントラネットの Active Directory ネットワークには参加しません。</span><span class="sxs-lookup"><span data-stu-id="c4024-147">Because an Access Edge service is deployed in the perimeter network and customers usually do not allow Active Directory Domain Services access from the perimeter network, instances of Access Edge service are not joined to the intranet’s Active Directory network.</span></span> <span data-ttu-id="c4024-148">したがって、アクセス プロキシは、自動的には AD DS に登録されません。</span><span class="sxs-lookup"><span data-stu-id="c4024-148">Therefore, Access Proxies are not automatically registered in AD DS.</span></span> <span data-ttu-id="c4024-149">管理者は、AD DS のアクセスエッジサービスの各インスタンスの存在を手動で構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c4024-149">The administrator must manually configure the existence of each instance of Access Edge service in AD DS.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c4024-150">msRTCSIP-EnterpriseMCUSettings</span><span class="sxs-lookup"><span data-stu-id="c4024-150">msRTCSIP-EnterpriseMCUSettings</span></span></p></td>
<td><p><span data-ttu-id="c4024-151">電話会議サーバーの設定を表す属性を保持する msRTCSIP-MCU の補助型クラスです。</span><span class="sxs-lookup"><span data-stu-id="c4024-151">This auxiliary class to msRTCSIP-MCU holds attributes representing settings for Conferencing servers.</span></span></p></td>
<td><p><span data-ttu-id="c4024-152">Microsoft Office Communications Server 2007 の新製品。</span><span class="sxs-lookup"><span data-stu-id="c4024-152">New in Microsoft Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c4024-153">msRTCSIP-EnterpriseMediationServerSettings</span><span class="sxs-lookup"><span data-stu-id="c4024-153">msRTCSIP-EnterpriseMediationServerSettings</span></span></p></td>
<td><p><span data-ttu-id="c4024-154">仲介サーバーの設定を表す属性を保持する msRTCSIP-MediationServer の補助型クラスです。</span><span class="sxs-lookup"><span data-stu-id="c4024-154">This auxiliary class to msRTCSIP-MediationServer holds attributes representing settings for Mediation Servers.</span></span></p></td>
<td><p><span data-ttu-id="c4024-155">Office Communications Server 2007 の新製品。</span><span class="sxs-lookup"><span data-stu-id="c4024-155">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c4024-156">msRTCSIP-EnterpriseServerSettings</span><span class="sxs-lookup"><span data-stu-id="c4024-156">msRTCSIP-EnterpriseServerSettings</span></span></p></td>
<td><p><span data-ttu-id="c4024-157">SIP サーバーの設定を表す属性を保持する msRTCSIP-Server の補助型クラスです。</span><span class="sxs-lookup"><span data-stu-id="c4024-157">This auxiliary class to msRTCSIP-Server holds attributes representing settings for SIP servers.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c4024-158">msRTCSIP</span><span class="sxs-lookup"><span data-stu-id="c4024-158">msRTCSIP-Federation</span></span></p></td>
<td><p><span data-ttu-id="c4024-159">フェデレーションに関連するすべての設定を保持する msRTCSIP-GlobalContainer の補助型クラスです。</span><span class="sxs-lookup"><span data-stu-id="c4024-159">This auxiliary class to msRTCSIP-GlobalContainer holds all settings related to federation.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c4024-160">msRTCSIP-GlobalContainer</span><span class="sxs-lookup"><span data-stu-id="c4024-160">msRTCSIP-GlobalContainer</span></span></p></td>
<td><p><span data-ttu-id="c4024-161">このクラスは、Lync Server 展開全体で適用されるすべての設定を保持します。</span><span class="sxs-lookup"><span data-stu-id="c4024-161">This class holds all settings that apply throughout a Lync Server deployment.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c4024-162">msRTCSIP-GlobalUserPolicy (廃止)</span><span class="sxs-lookup"><span data-stu-id="c4024-162">msRTCSIP-GlobalUserPolicy (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="c4024-163">このクラスは、1つの Office Communications Server 会議ポリシーを表します。</span><span class="sxs-lookup"><span data-stu-id="c4024-163">This class represents a single Office Communications Server meeting policy.</span></span></p></td>
<td><p><span data-ttu-id="c4024-164">Lync Server 2010 では廃止されました。</span><span class="sxs-lookup"><span data-stu-id="c4024-164">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c4024-165">msRTCSIP-GlobalTopologySetting</span><span class="sxs-lookup"><span data-stu-id="c4024-165">msRTCSIP-GlobalTopologySetting</span></span></p></td>
<td><p><span data-ttu-id="c4024-166">ローカルのグローバル トポロジ設定オブジェクトです。</span><span class="sxs-lookup"><span data-stu-id="c4024-166">The local global topology setting object.</span></span></p></td>
<td><p><span data-ttu-id="c4024-167">Lync Server 2010 の新。</span><span class="sxs-lookup"><span data-stu-id="c4024-167">New in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c4024-168">msRTCSIP-GlobalTopologySettings</span><span class="sxs-lookup"><span data-stu-id="c4024-168">msRTCSIP-GlobalTopologySettings</span></span></p></td>
<td><p><span data-ttu-id="c4024-169">グローバル トポロジ設定オブジェクトを保持するコンテナーです。</span><span class="sxs-lookup"><span data-stu-id="c4024-169">Container to hold global topology setting objects.</span></span></p></td>
<td><p><span data-ttu-id="c4024-170">Lync Server 2010 の新。</span><span class="sxs-lookup"><span data-stu-id="c4024-170">New in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c4024-171">msRTCSIP-LocalNormalization</span><span class="sxs-lookup"><span data-stu-id="c4024-171">msRTCSIP-LocalNormalization</span></span></p></td>
<td><p><span data-ttu-id="c4024-172">ローカル正規化ルールのインスタンスを表すコンテナーです。</span><span class="sxs-lookup"><span data-stu-id="c4024-172">This class is a container that represents an instance of a location normalization rule.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c4024-173">msRTCSIP-LocationContactMapping</span><span class="sxs-lookup"><span data-stu-id="c4024-173">msRTCSIP-LocationContactMapping</span></span></p></td>
<td><p><span data-ttu-id="c4024-174">このクラスは、会議アテンダントアプリケーションによって作成され、電話会議の電話番号を地域別に分類するために使用される属性を保持します。</span><span class="sxs-lookup"><span data-stu-id="c4024-174">This class is created by the Conferencing Attendant application and holds attributes used to categorize conference telephone numbers by region.</span></span></p></td>
<td><p><span data-ttu-id="c4024-175">Communications Server 2007 R2 の新サービス。</span><span class="sxs-lookup"><span data-stu-id="c4024-175">New in Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c4024-176">msRTCSIP-LocationContactMappings</span><span class="sxs-lookup"><span data-stu-id="c4024-176">msRTCSIP-LocationContactMappings</span></span></p></td>
<td><p><span data-ttu-id="c4024-177">場所と連絡先のマッピングの複数のインスタンスを保持するコンテナーです。属性そのものは含まれません。</span><span class="sxs-lookup"><span data-stu-id="c4024-177">This class is a container for multiple instances of location contact mappings and does not contain any attributes itself.</span></span></p></td>
<td><p><span data-ttu-id="c4024-178">Communications Server 2007 R2 の新サービス。</span><span class="sxs-lookup"><span data-stu-id="c4024-178">New in Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c4024-179">msRTCSIP-LocationProfile</span><span class="sxs-lookup"><span data-stu-id="c4024-179">msRTCSIP-LocationProfile</span></span></p></td>
<td><p><span data-ttu-id="c4024-180">特定の場所のプロファイルを表すコンテナーです。</span><span class="sxs-lookup"><span data-stu-id="c4024-180">This class is a container that represents a specific location profile.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c4024-181">msRTCSIP-LocationProfiles (廃止)</span><span class="sxs-lookup"><span data-stu-id="c4024-181">msRTCSIP-LocationProfiles (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="c4024-182">複数の場所のプロファイルのコンテナーです。属性そのものは含まれません。</span><span class="sxs-lookup"><span data-stu-id="c4024-182">This class is a container for multiple location profiles and does not contain any attributes itself.</span></span></p></td>
<td><p><span data-ttu-id="c4024-183">Lync Server 2010 では廃止されました。</span><span class="sxs-lookup"><span data-stu-id="c4024-183">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c4024-184">msRTCSIP-LocalNormalizations (廃止)</span><span class="sxs-lookup"><span data-stu-id="c4024-184">msRTCSIP-LocalNormalizations (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="c4024-185">複数のローカル正規化ルールのコンテナーです。属性そのものは含まれません。</span><span class="sxs-lookup"><span data-stu-id="c4024-185">This class is a container for multiple local normalization rules and does not contain any attributes itself.</span></span></p></td>
<td><p><span data-ttu-id="c4024-186">Lync Server 2010 では廃止されました。</span><span class="sxs-lookup"><span data-stu-id="c4024-186">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c4024-187">msRTCSIP-MCU</span><span class="sxs-lookup"><span data-stu-id="c4024-187">msRTCSIP-MCU</span></span></p></td>
<td><p><span data-ttu-id="c4024-188">1 つの電話会議サーバーを表すクラスです。</span><span class="sxs-lookup"><span data-stu-id="c4024-188">This class represents a single Conferencing server.</span></span></p></td>
<td><p><span data-ttu-id="c4024-189">Communications Server 2007 の新情報。</span><span class="sxs-lookup"><span data-stu-id="c4024-189">New in Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c4024-190">msRTCSIP-MCUFactories</span><span class="sxs-lookup"><span data-stu-id="c4024-190">msRTCSIP-MCUFactories</span></span></p></td>
<td><p><span data-ttu-id="c4024-191">複数の msRTCSIP-MCUFactory クラスを保持するクラスです。属性そのものは含まれません。</span><span class="sxs-lookup"><span data-stu-id="c4024-191">This class holds multiple msRTCSIP-MCUFactory classes and does not have attributes itself.</span></span></p></td>
<td><p><span data-ttu-id="c4024-192">Communications Server 2007 の新情報。</span><span class="sxs-lookup"><span data-stu-id="c4024-192">New in Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c4024-193">msRTCSIP-MCUFactory</span><span class="sxs-lookup"><span data-stu-id="c4024-193">msRTCSIP-MCUFactory</span></span></p></td>
<td><p><span data-ttu-id="c4024-p103">1 つのメディアの種類の会議サーバー ファクトリを表すコンテナーです。 このクラスのインスタンスは、この特定の種類およびベンダーの最初の電話会議サーバーがアクティブ化されると作成されます。</span><span class="sxs-lookup"><span data-stu-id="c4024-p103">This class is a container representing a Conferencing Server Factory for a single medium type. An instance of this class is created when the first Conferencing server for this particular type and vendor is activated.</span></span></p></td>
<td><p><span data-ttu-id="c4024-196">Communications Server 2007 の新情報。</span><span class="sxs-lookup"><span data-stu-id="c4024-196">New in Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c4024-197">msRTCSIP-MCUFactoryService</span><span class="sxs-lookup"><span data-stu-id="c4024-197">msRTCSIP-MCUFactoryService</span></span></p></td>
<td><p><span data-ttu-id="c4024-198">特定のプールからその会議サーバー ファクトリへの関連付けを提供するクラスです。</span><span class="sxs-lookup"><span data-stu-id="c4024-198">This class provides an association from a specific pool to its Conferencing Server Factory.</span></span></p></td>
<td><p><span data-ttu-id="c4024-199">Communications Server 2007 の新情報。</span><span class="sxs-lookup"><span data-stu-id="c4024-199">New in Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c4024-200">msRTCSIP-MediationServer</span><span class="sxs-lookup"><span data-stu-id="c4024-200">msRTCSIP-MediationServer</span></span></p></td>
<td><p><span data-ttu-id="c4024-201">仲介サーバーのサービス制御ポイントのエントリを保持するクラスです。</span><span class="sxs-lookup"><span data-stu-id="c4024-201">This class holds the entry for the service control point for a Mediation Server.</span></span></p></td>
<td><p><span data-ttu-id="c4024-202">Communications Server 2007 の新情報。</span><span class="sxs-lookup"><span data-stu-id="c4024-202">New in Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c4024-203">msRTCSIP-Meeting (廃止)</span><span class="sxs-lookup"><span data-stu-id="c4024-203">msRTCSIP-Meeting (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="c4024-204">構成可能な会議の設定を表す属性を保持する msRTCSIP-GlobalContainer の補助型クラスです。</span><span class="sxs-lookup"><span data-stu-id="c4024-204">This auxiliary class to msRTCSIP-GlobalContainer holds attributes representing configurable meeting settings.</span></span></p></td>
<td><p><span data-ttu-id="c4024-205">Lync Server 2010 では廃止されました。</span><span class="sxs-lookup"><span data-stu-id="c4024-205">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c4024-206">msRTCSIP</span><span class="sxs-lookup"><span data-stu-id="c4024-206">msRTCSIP-Mobility</span></span></p></td>
<td><p><span data-ttu-id="c4024-207">グローバル モビリティ設定を格納するコンテナーです。</span><span class="sxs-lookup"><span data-stu-id="c4024-207">Container that stores the global mobility settings.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c4024-208">msRTCSIP-MonitoringServer</span><span class="sxs-lookup"><span data-stu-id="c4024-208">msRTCSIP-MonitoringServer</span></span></p></td>
<td><p><span data-ttu-id="c4024-209">このクラスは、単一の監視サーバーの設定を表す属性を保持します。</span><span class="sxs-lookup"><span data-stu-id="c4024-209">This class holds attributes that represent settings for a single Monitoring Server.</span></span></p></td>
<td><p><span data-ttu-id="c4024-210">Communications Server 2007 R2 の新サービス。</span><span class="sxs-lookup"><span data-stu-id="c4024-210">New in Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c4024-211">msRTCSIP-PhoneRoute (廃止)</span><span class="sxs-lookup"><span data-stu-id="c4024-211">msRTCSIP-PhoneRoute (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="c4024-p104">ゲートウェイまたはゲートウェイのセットへの最小コスト経路のインスタンスを表すコンテナーです。 この情報は、すべてのエンタープライズ プールや Standard Edition サーバーによって、最もコストの小さい方法で、発信通話を公衆交換電話網 (PSTN) にルーティングするために使用されます。</span><span class="sxs-lookup"><span data-stu-id="c4024-p104">This class is a container representing an instance of a least cost route to a gateway or set of gateways. This information is used by all Enterprise pools or servers running Standard Edition to route outgoing calls to the public switched telephone network (PSTN) in the most cost effective way.</span></span></p></td>
<td><p><span data-ttu-id="c4024-214">Lync Server 2010 では廃止されました。</span><span class="sxs-lookup"><span data-stu-id="c4024-214">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c4024-215">msRTCSIP-PhoneRoutes (廃止)</span><span class="sxs-lookup"><span data-stu-id="c4024-215">msRTCSIP-PhoneRoutes (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="c4024-216">複数の最小コスト経路のコンテナーです。属性そのものは含まれません。</span><span class="sxs-lookup"><span data-stu-id="c4024-216">This class is a container for multiple, least cost routes and does not contain any attributes itself.</span></span></p></td>
<td><p><span data-ttu-id="c4024-217">Lync Server 2010 では廃止されました。</span><span class="sxs-lookup"><span data-stu-id="c4024-217">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c4024-218">msRTCSIP-Policies (廃止)</span><span class="sxs-lookup"><span data-stu-id="c4024-218">msRTCSIP-Policies (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="c4024-219">複数の Lync Server ポリシークラスを保持するクラスです。属性そのものは含まれません。</span><span class="sxs-lookup"><span data-stu-id="c4024-219">This class holds multiple Lync Server policy classes and does not have any attributes itself.</span></span></p></td>
<td><p><span data-ttu-id="c4024-220">Lync Server 2010 では廃止されました。</span><span class="sxs-lookup"><span data-stu-id="c4024-220">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c4024-221">msRTCSIP</span><span class="sxs-lookup"><span data-stu-id="c4024-221">msRTCSIP-Pool</span></span></p></td>
<td><p><span data-ttu-id="c4024-222">このクラスは、1つの Lync Server プールを表します。</span><span class="sxs-lookup"><span data-stu-id="c4024-222">This class represents a single Lync Server pool.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c4024-223">msRTCSIP</span><span class="sxs-lookup"><span data-stu-id="c4024-223">msRTCSIP-Pools</span></span></p></td>
<td><p><span data-ttu-id="c4024-224">複数の Lync Server プールを保持するクラスです。属性そのものは含まれません。</span><span class="sxs-lookup"><span data-stu-id="c4024-224">This class holds multiple Lync Server pools and does not have any attributes itself.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c4024-225">msRTCSIP-PoolService</span><span class="sxs-lookup"><span data-stu-id="c4024-225">msRTCSIP-PoolService</span></span></p></td>
<td><p><span data-ttu-id="c4024-p105">プールのサービス制御ポイントを表すクラスです。プールでホストされるユーザーは、msRTCSIP-PrimaryHomeServer 属性をこのクラスのインスタンスに設定します。</span><span class="sxs-lookup"><span data-stu-id="c4024-p105">This class represents the service control pointservice control point of a pool. Users hosted on a pool have their msRTCSIP-PrimaryHomeServer attribute point to an instance of this class.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c4024-228">msRTCSIP-プレゼンス</span><span class="sxs-lookup"><span data-stu-id="c4024-228">msRTCSIP-Presence</span></span></p></td>
<td><p><span data-ttu-id="c4024-229">グローバル プレゼンス設定を格納するコンテナーです。</span><span class="sxs-lookup"><span data-stu-id="c4024-229">Container that stores the global presence settings.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c4024-230">msRTCSIP</span><span class="sxs-lookup"><span data-stu-id="c4024-230">msRTCSIP-Registrar</span></span></p></td>
<td><p><span data-ttu-id="c4024-231">SIP レジストラー サーバーによって管理されるユーザー設定を表す属性を保持する msRTCSIP-GlobalContainer の補助型クラスです。</span><span class="sxs-lookup"><span data-stu-id="c4024-231">This auxiliary class to msRTCSIP-GlobalContainer holds attributes representing user settings maintained by the SIP Registrar servers.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c4024-232">msRTCSIP-RouteUsage (廃止)</span><span class="sxs-lookup"><span data-stu-id="c4024-232">msRTCSIP-RouteUsage (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="c4024-p106">電話ルート使用法のインスタンスを表すコンテナーです。電話ルート使用法クラスは、属性フィールドと説明フィールドで構成されています。属性フィールドは使用法の種類を定義します。管理者は説明フィールドに、電話ルートでのその属性の使用法の説明を記入できます。</span><span class="sxs-lookup"><span data-stu-id="c4024-p106">This class is a container representing an instance of a phone route usage. A phone route usage class consists of an attribute field and a description field. The attribute field defines a usage type. The description field allows administrators to describe the usage for this attribute in the phone route.</span></span></p></td>
<td><p><span data-ttu-id="c4024-237">Lync Server 2010 では廃止されました。</span><span class="sxs-lookup"><span data-stu-id="c4024-237">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c4024-238">msRTCSIP-RouteUsages (廃止)</span><span class="sxs-lookup"><span data-stu-id="c4024-238">msRTCSIP-RouteUsages (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="c4024-239">msRTCSIP-RouteUsage クラスの複数のインスタンスを保持するクラスです。属性そのものは含まれません。</span><span class="sxs-lookup"><span data-stu-id="c4024-239">This class holds multiple instances of the msRTCSIP-RouteUsage class and does not have any attributes itself.</span></span></p></td>
<td><p><span data-ttu-id="c4024-240">Lync Server 2010 では廃止されました。</span><span class="sxs-lookup"><span data-stu-id="c4024-240">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c4024-241">msRTCSIP-検索</span><span class="sxs-lookup"><span data-stu-id="c4024-241">msRTCSIP-Search</span></span></p></td>
<td><p><span data-ttu-id="c4024-242">検索結果の範囲を制限および制御する属性を保持する msRTCSIP-GlobalContainer の補助型クラスです。</span><span class="sxs-lookup"><span data-stu-id="c4024-242">This auxiliary class to msRTCSIP-GlobalContainer holds attributes that limit and control the scope of search results.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c4024-243">msRTCSIP-サーバー</span><span class="sxs-lookup"><span data-stu-id="c4024-243">msRTCSIP-Server</span></span></p></td>
<td><p><span data-ttu-id="c4024-244">このクラスは、Lync Server を実行している1台のサーバーを表します。</span><span class="sxs-lookup"><span data-stu-id="c4024-244">This class represents a single server running Lync Server.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c4024-245">msRTCSIP</span><span class="sxs-lookup"><span data-stu-id="c4024-245">msRTCSIP-Service</span></span></p></td>
<td><p><span data-ttu-id="c4024-246">グローバル設定コンテナーと msRTCSIP-Domain オブジェクトを保持するクラスです。</span><span class="sxs-lookup"><span data-stu-id="c4024-246">This class holds the global settings container and msRTCSIP-Domain objects.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c4024-247">msRTCSIP-TrustedMCU</span><span class="sxs-lookup"><span data-stu-id="c4024-247">msRTCSIP-TrustedMCU</span></span></p></td>
<td><p><span data-ttu-id="c4024-248">1 つの信頼済み電話会議サーバーの設定を表す属性を保持するクラスです。</span><span class="sxs-lookup"><span data-stu-id="c4024-248">This class holds attributes that represent settings for a trusted Conferencing server.</span></span></p></td>
<td><p><span data-ttu-id="c4024-249">Communications Server 2007 の新情報。</span><span class="sxs-lookup"><span data-stu-id="c4024-249">New in Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c4024-250">msRTCSIP-TrustedMCUs</span><span class="sxs-lookup"><span data-stu-id="c4024-250">msRTCSIP-TrustedMCUs</span></span></p></td>
<td><p><span data-ttu-id="c4024-251">msRTCSIP-TrustedMCU クラスの複数のインスタンスを保持するクラスです。属性そのものは含まれません。</span><span class="sxs-lookup"><span data-stu-id="c4024-251">This class holds multiple instances of the msRTCSIP-TrustedMCU class and does not have any attributes itself.</span></span></p></td>
<td><p><span data-ttu-id="c4024-252">Communications Server 2007 の新情報。</span><span class="sxs-lookup"><span data-stu-id="c4024-252">New in Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c4024-253">msRTCSIP-TrustedProxies</span><span class="sxs-lookup"><span data-stu-id="c4024-253">msRTCSIP-TrustedProxies</span></span></p></td>
<td><p><span data-ttu-id="c4024-254">複数の msRTCSIP-TrustedProxy クラスを保持するクラスです。属性そのものは含まれません。</span><span class="sxs-lookup"><span data-stu-id="c4024-254">This class holds multiple msRTCSIP-TrustedProxy classes and does not contain any attributes itself.</span></span></p></td>
<td><p><span data-ttu-id="c4024-255">Communications Server 2007 の新情報。</span><span class="sxs-lookup"><span data-stu-id="c4024-255">New in Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c4024-256">msRTCSIP-TrustedProxy</span><span class="sxs-lookup"><span data-stu-id="c4024-256">msRTCSIP-TrustedProxy</span></span></p></td>
<td><p><span data-ttu-id="c4024-p107">プロキシ サーバーを実行しているサーバーを表すコンテナーです。 このクラスのインスタンスは、AD DS に参加しているコンピューターで新しいプロキシ サーバーがアクティブ化されると作成されます。</span><span class="sxs-lookup"><span data-stu-id="c4024-p107">This class is a container representing a server running Proxy Server. An instance of this class is created when activating a new Proxy Server on a computer joined to AD DS.</span></span></p></td>
<td><p><span data-ttu-id="c4024-259">Communications Server 2007 の新情報。</span><span class="sxs-lookup"><span data-stu-id="c4024-259">New in Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c4024-260">msRTCSIP-TrustedServer</span><span class="sxs-lookup"><span data-stu-id="c4024-260">msRTCSIP-TrustedServer</span></span></p></td>
<td><p><span data-ttu-id="c4024-261">1 つの信頼済みサーバーの設定を表す属性を保持するクラスです。</span><span class="sxs-lookup"><span data-stu-id="c4024-261">This class holds attributes that represent settings for a trusted server.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c4024-262">msRTCSIP-TrustedService</span><span class="sxs-lookup"><span data-stu-id="c4024-262">msRTCSIP-TrustedService</span></span></p></td>
<td><p><span data-ttu-id="c4024-263">グローバルにルーティング可能なユーザー エージェント (GRUU) アドレスを使用してルーティングできる信頼済みサービスを表すコンテナーです。</span><span class="sxs-lookup"><span data-stu-id="c4024-263">This class is a container representing a trusted service that is routable using a Globally Routable User Agent URI (GRUU) address.</span></span> <span data-ttu-id="c4024-264">このクラスのインスタンスは、Lync Server によって信頼されている新しいサーバーがアクティブ化されたときに作成されます。</span><span class="sxs-lookup"><span data-stu-id="c4024-264">An instance of this class is created when a new server that is trusted by Lync Server is activated.</span></span> <span data-ttu-id="c4024-265">この信頼済みサーバーは Active Directory ドメインに参加している必要があります。</span><span class="sxs-lookup"><span data-stu-id="c4024-265">This trusted server must be joined to an Active Directory domain.</span></span></p></td>
<td><p><span data-ttu-id="c4024-266">Communications Server 2007 の新情報。</span><span class="sxs-lookup"><span data-stu-id="c4024-266">New in Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c4024-267">msRTCSIP-TrustedServices</span><span class="sxs-lookup"><span data-stu-id="c4024-267">msRTCSIP-TrustedServices</span></span></p></td>
<td><p><span data-ttu-id="c4024-268">複数の GRUU サーバーのコンテナーです。属性そのものは含まれません。</span><span class="sxs-lookup"><span data-stu-id="c4024-268">This class is a container for multiple GRUU servers and does not contain any attributes itself.</span></span></p></td>
<td><p><span data-ttu-id="c4024-269">Communications Server 2007 の新情報。</span><span class="sxs-lookup"><span data-stu-id="c4024-269">New in Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c4024-270">msRTCSIP-Trustedwebコンポーネントサーバー</span><span class="sxs-lookup"><span data-stu-id="c4024-270">msRTCSIP-TrustedWebComponentsServer</span></span></p></td>
<td><p><span data-ttu-id="c4024-271">1 つの信頼済み Web コンポーネントの設定を表す属性を保持するクラスです。</span><span class="sxs-lookup"><span data-stu-id="c4024-271">This class holds attributes that represent the settings for a trusted web component.</span></span></p></td>
<td><p><span data-ttu-id="c4024-272">Communications Server 2007 の新情報。</span><span class="sxs-lookup"><span data-stu-id="c4024-272">New in Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c4024-273">msRTCSIP-Trustedwebコンポーネントサーバー</span><span class="sxs-lookup"><span data-stu-id="c4024-273">msRTCSIP-TrustedWebComponentsServers</span></span></p></td>
<td><p><span data-ttu-id="c4024-274">msRTCSIP-TrustedWebComponentServer クラスの複数のインスタンスを保持するクラスです。属性そのものは含まれません。</span><span class="sxs-lookup"><span data-stu-id="c4024-274">This class holds multiple instances of the msRTCSIP-TrustedWebComponentServer class and does not have any attributes itself.</span></span></p></td>
<td><p><span data-ttu-id="c4024-275">Communications Server 2007 の新情報。</span><span class="sxs-lookup"><span data-stu-id="c4024-275">New in Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c4024-276">msRTCSIP-UnifiedCommunications (廃止)</span><span class="sxs-lookup"><span data-stu-id="c4024-276">msRTCSIP-UnifiedCommunications (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="c4024-277">統合コミュニケーションに関連する属性を保持する msRTCSIP-GlobalContainer の補助型クラスです。</span><span class="sxs-lookup"><span data-stu-id="c4024-277">This auxiliary class to msRTCSIP-GlobalContainer holds attributes related to unified communications.</span></span></p></td>
<td><p><span data-ttu-id="c4024-278">Lync Server 2010 では廃止されました。</span><span class="sxs-lookup"><span data-stu-id="c4024-278">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c4024-279">msRTCSIP-WebComponents</span><span class="sxs-lookup"><span data-stu-id="c4024-279">msRTCSIP-WebComponents</span></span></p></td>
<td><p><span data-ttu-id="c4024-p109">インターネット インフォメーション サーバー (IIS) のサービス制御ポイントを保持するクラスです。サーバーを Web コンポーネント サーバーとして識別します。</span><span class="sxs-lookup"><span data-stu-id="c4024-p109">This class holds the service control pointservice control point for Internet Information Server (IIS). It identifies a server as a web components server.</span></span></p></td>
<td><p><span data-ttu-id="c4024-282">Communications Server 2007 の新情報。</span><span class="sxs-lookup"><span data-stu-id="c4024-282">New in Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c4024-283">msRTCSIP-Webコンポーネントサービス</span><span class="sxs-lookup"><span data-stu-id="c4024-283">msRTCSIP-WebComponentsService</span></span></p></td>
<td><p><span data-ttu-id="c4024-284">特定のプールからそのプールが使用する Web コンポーネントへの関連付けを提供するクラスです。</span><span class="sxs-lookup"><span data-stu-id="c4024-284">This class provides an association from a specific pool to the web components that the pool will use.</span></span></p></td>
<td><p><span data-ttu-id="c4024-285">Communications Server 2007 の新情報。</span><span class="sxs-lookup"><span data-stu-id="c4024-285">New in Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c4024-286">msRTCSIP-WebComponentSettings</span><span class="sxs-lookup"><span data-stu-id="c4024-286">msRTCSIP-WebComponentSettings</span></span></p></td>
<td><p><span data-ttu-id="c4024-287">Web コンポーネントの設定を表す属性を保持する msRTCSIP-WebComponents の補助型クラスです。</span><span class="sxs-lookup"><span data-stu-id="c4024-287">This auxiliary class to msRTCSIP-WebComponents holds attributes representing settings for web components.</span></span></p></td>
<td><p><span data-ttu-id="c4024-288">Communications Server 2007 の新情報。</span><span class="sxs-lookup"><span data-stu-id="c4024-288">New in Communications Server 2007.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

