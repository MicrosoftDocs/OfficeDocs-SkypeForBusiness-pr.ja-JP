---
title: 'Lync Server 2013: E9 の展開チェックリスト-1-1'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment checklist for E9-1-1
ms:assetid: cc6a656a-6043-4b9b-85c2-5708b9bb1c06
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398864(v=OCS.15)
ms:contentKeyID: 48185655
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5efe5c55386eb431c91e798ad960cc510ce33ce1
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763451"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-checklist-for-e9-1-1-in-lync-server-2013"></a><span data-ttu-id="b52d7-102">Lync Server 2013 の E9-1 の展開チェックリスト</span><span class="sxs-lookup"><span data-stu-id="b52d7-102">Deployment checklist for E9-1-1 in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b52d7-103">_**最終更新日:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="b52d7-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="b52d7-104">強化された 9-1-1 (E9) を効率的に計画するには、次の展開要件を必ず含めてください。</span><span class="sxs-lookup"><span data-stu-id="b52d7-104">To plan effectively for Enhanced 9-1-1 (E9-1-1), be sure to include the following deployment requirements:</span></span>

  - <span data-ttu-id="b52d7-105">E9 を展開するための前提条件-1-1。</span><span class="sxs-lookup"><span data-stu-id="b52d7-105">Prerequisites for deploying E9-1-1.</span></span>

  - <span data-ttu-id="b52d7-106">E9 の展開に必要な手順。-1-1。</span><span class="sxs-lookup"><span data-stu-id="b52d7-106">Steps that are required to deploy E9-1-1.</span></span>

<div>

## <a name="deployment-prerequisites-for-e9-1-1"></a><span data-ttu-id="b52d7-107">E9-1-1 の展開前提条件</span><span class="sxs-lookup"><span data-stu-id="b52d7-107">Deployment Prerequisites for E9-1-1</span></span>

<span data-ttu-id="b52d7-108">E9-1 を展開する前に、一元管理ストア、フロントエンドプール、Standard Edition サーバー、1つ以上の仲介サーバーまたは仲介サーバー、Lync Server クライアントなど、Lync Server の内部サーバーを既に展開している必要があります。</span><span class="sxs-lookup"><span data-stu-id="b52d7-108">Before you deploy E9-1-1, you must already have deployed your Lync Server internal servers, including a Central Management store, a Front End pool or a Standard Edition server, one or more Mediation Servers or Mediation Server pools, and Lync Server clients.</span></span> <span data-ttu-id="b52d7-109">さらに、E9-1-1 の展開では、認定された E9-1-1 サービス プロバイダーへの SIP トランク、または公衆交換電話網 (PSTN) への緊急位置識別番号 (ELIN) ゲートウェイも必要とします。</span><span class="sxs-lookup"><span data-stu-id="b52d7-109">In addition, an E9-1-1 deployment requires a SIP trunk to a qualified E9-1-1 service provider or an Emergency Location Identification Number (ELIN) gateway to your public switched telephone network (PSTN).</span></span> <span data-ttu-id="b52d7-110">Lync Server は、米国内でのみ E9 サービスプロバイダーを使用することをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="b52d7-110">Lync Server supports using E9-1-1 service providers only inside the United States.</span></span>

</div>

<div>

## <a name="deployment-process"></a><span data-ttu-id="b52d7-111">展開プロセス</span><span class="sxs-lookup"><span data-stu-id="b52d7-111">Deployment Process</span></span>

<span data-ttu-id="b52d7-112">次の表に、E9-1-1 展開プロセスの概要を示します。</span><span class="sxs-lookup"><span data-stu-id="b52d7-112">The following table provides an overview of the E9-1-1 deployment process.</span></span> <span data-ttu-id="b52d7-113">展開手順の詳細については、展開ドキュメントの「 [Lync Server 2013 で強化](lync-server-2013-configure-enhanced-9-1-1.md)された9-1-1 を構成する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b52d7-113">For details about deployment steps, see [Configure Enhanced 9-1-1 in Lync Server 2013](lync-server-2013-configure-enhanced-9-1-1.md) in the Deployment documentation.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b52d7-114">段階</span><span class="sxs-lookup"><span data-stu-id="b52d7-114">Phase</span></span></th>
<th><span data-ttu-id="b52d7-115">手順</span><span class="sxs-lookup"><span data-stu-id="b52d7-115">Steps</span></span></th>
<th><span data-ttu-id="b52d7-116">役割</span><span class="sxs-lookup"><span data-stu-id="b52d7-116">Roles</span></span></th>
<th><span data-ttu-id="b52d7-117">「展開」のドキュメント</span><span class="sxs-lookup"><span data-stu-id="b52d7-117">Deployment documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b52d7-118">音声使用、ルート、およびトランクを構成する</span><span class="sxs-lookup"><span data-stu-id="b52d7-118">Configure voice usages, routes, and trunk configurations</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="b52d7-p103">新しい PSTN 使用法レコードを作成します。これは、場所のポリシーの [<strong>PSTN の使用法</strong>] 設定で使用する名前と同じです。</span><span class="sxs-lookup"><span data-stu-id="b52d7-p103">Create a new PSTN usage record. This is the same name that is used for the <strong>PSTN Usage</strong> setting in the location policy.</span></span></p></li>
<li><p><span data-ttu-id="b52d7-121">前のステップで作成した PSTN 使用法レコードに対するボイス ルートを作成するか割り当て、ゲートウェイ属性が E9-1-1 SIP トランクまたは ELIN ゲートウェイを指すようにします。 </span><span class="sxs-lookup"><span data-stu-id="b52d7-121">Create or assign a voice route to the PSTN usage record created in the previous step and then point the gateway attribute to the E9-1-1 SIP trunk or ELIN gateway.</span></span></p></li>
<li><p><span data-ttu-id="b52d7-122">SIP トランク E9-1-1 サービス プロバイダーの場合は、<strong>Set-CsTrunkConfiguration –EnablePIDFLOSupport</strong> コマンドレットを使用して、SIP 経由の E9-1-1 呼び出しを処理するトランクが PIDF-LO データを渡すように設定します。</span><span class="sxs-lookup"><span data-stu-id="b52d7-122">For a SIP trunk E9-1-1 service provider, set the trunk that will be handling E9-1-1 calls over the SIP to pass PIDF-LO data by using the <strong>Set-CsTrunkConfiguration –EnablePIDFLOSupport</strong> cmdlet.</span></span></p></li>
<li><p><span data-ttu-id="b52d7-p104">必要に応じて、SIP トランク E9-1-1 サービス プロバイダーの場合は、E9-1-1 サービス プロバイダーの SIP トランクによって処理されない呼び出しに対するローカル PSTN ルートを作成するか、割り当てます。このルートは、E9-1-1 サービス プロバイダーへの接続が利用できない場合に使用されます。E9-1-1 サービス プロバイダーがサポートしている場合は、911 ダイヤル文字列を国または地域の Emergency Call Response Center (ECRC) の Direct Inward Dialing (DID) 番号に変換するトランク構成ルールをゲートウェイに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="b52d7-p104">Optionally, for a SIP trunk E9-1-1 service provider, create or assign a local PSTN route for calls that are not handled by the E9-1-1 service provider’s SIP trunk. This route will be used if the connection to the E9-1-1 service provider is not available. If supported by your E9-1-1 service provider, assign a trunk configuration rule to the gateway that translates the 911 dial string into the direct inward dialing (DID) number of the national/regional Emergency Call Response Center (ECRC).</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="b52d7-126">CSVoiceAdmin</span><span class="sxs-lookup"><span data-stu-id="b52d7-126">CSVoiceAdmin</span></span></p></td>
<td><p><span data-ttu-id="b52d7-127"><a href="lync-server-2013-configure-an-e9-1-1-voice-route.md">Lync Server 2013 での E9 音声ルートの構成</a></span><span class="sxs-lookup"><span data-stu-id="b52d7-127"><a href="lync-server-2013-configure-an-e9-1-1-voice-route.md">Configure an E9-1-1 voice route in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b52d7-128">場所のポリシーを作成し、ユーザーおよびサブネットに割り当てる</span><span class="sxs-lookup"><span data-stu-id="b52d7-128">Create location policies and assign them to users and subnets</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="b52d7-129">グローバルの場所のポリシーを確認します。</span><span class="sxs-lookup"><span data-stu-id="b52d7-129">Review the global location policy.</span></span></p></li>
<li><p><span data-ttu-id="b52d7-130">ユーザーレベル スコープで場所のポリシーを作成します。または、組織に緊急使用法が異なる複数のサイトがある場合は、ネットワークレベル スコープで場所のポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="b52d7-130">Create a location policy with a user-level scope; or, if the organization has more than one site with different emergency usages, create a location policy with a network-level scope.</span></span></p></li>
<li><p><span data-ttu-id="b52d7-131">場所のポリシーをネットワーク サイトに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="b52d7-131">Assign the location policy to network sites.</span></span></p></li>
<li><p><span data-ttu-id="b52d7-132">適切なサブネットをネットワーク サイトに追加します。</span><span class="sxs-lookup"><span data-stu-id="b52d7-132">Add the appropriate subnets to the network site.</span></span></p></li>
<li><p><span data-ttu-id="b52d7-133">(必要に応じて) 場所のポリシーをユーザー ポリシーに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="b52d7-133">(Optional) Assign the location policy to user policies.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="b52d7-134">CSVoiceAdmin</span><span class="sxs-lookup"><span data-stu-id="b52d7-134">CSVoiceAdmin</span></span></p>
<p><span data-ttu-id="b52d7-135">CSLocationAdmin (場所のポリシーの作成を除く)</span><span class="sxs-lookup"><span data-stu-id="b52d7-135">CSLocationAdmin (except for creating Location Policies)</span></span></p></td>
<td><p><span data-ttu-id="b52d7-136"><a href="lync-server-2013-create-location-policies.md">Lync Server 2013 で位置情報のポリシーを作成する</a></span><span class="sxs-lookup"><span data-stu-id="b52d7-136"><a href="lync-server-2013-create-location-policies.md">Create location policies in Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="b52d7-137"><a href="lync-server-2013-add-a-location-policy-to-a-network-site.md">Lync Server 2013 でネットワークサイトに位置情報ポリシーを追加する</a></span><span class="sxs-lookup"><span data-stu-id="b52d7-137"><a href="lync-server-2013-add-a-location-policy-to-a-network-site.md">Add a location policy to a network site in Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="b52d7-138"><a href="lync-server-2013-associate-subnets-with-network-sites-for-e9-1-1.md">Lync Server 2013 での E9-1 のネットワークサイトへのサブネットの関連付け</a></span><span class="sxs-lookup"><span data-stu-id="b52d7-138"><a href="lync-server-2013-associate-subnets-with-network-sites-for-e9-1-1.md">Associate subnets with network sites for E9-1-1 in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b52d7-139">場所データベースを構成する</span><span class="sxs-lookup"><span data-stu-id="b52d7-139">Configure the location database</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="b52d7-140">ネットワーク要素と場所のマッピングをデータベースに設定します。</span><span class="sxs-lookup"><span data-stu-id="b52d7-140">Populate the database with a mapping of network elements to locations.</span></span></p></li>
<li><p><span data-ttu-id="b52d7-141">ELIN ゲートウェイの場合は、[ &lt;CompanyName&gt; ] 列に elins を追加します。</span><span class="sxs-lookup"><span data-stu-id="b52d7-141">For ELIN gateways, add the ELINs to the &lt;CompanyName&gt; column.</span></span></p></li>
<li><p><span data-ttu-id="b52d7-142">アドレスを確認するために、E9-1-1 サービス プロバイダーへの接続を構成します。</span><span class="sxs-lookup"><span data-stu-id="b52d7-142">Configure the connection to the E9-1-1 service provider for validating addresses.</span></span></p></li>
<li><p><span data-ttu-id="b52d7-143">E9-1-1 サービス プロバイダーでアドレスを確認します。</span><span class="sxs-lookup"><span data-stu-id="b52d7-143">Validate the addresses with the E9-1-1 service provider.</span></span></p></li>
<li><p><span data-ttu-id="b52d7-144">更新したデータベースを公開します。</span><span class="sxs-lookup"><span data-stu-id="b52d7-144">Publish the updated database.</span></span></p></li>
<li><p><span data-ttu-id="b52d7-145">ELIN ゲートウェイの場合は、ELIN を PSTN 通信業者の自動ロケーション識別 (ALI) データベースにアップロードします。</span><span class="sxs-lookup"><span data-stu-id="b52d7-145">For ELIN gateways, upload the ELINs to your PSTN carrier's Automatic Location Identification (ALI) database.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="b52d7-146">CSVoiceAdmin</span><span class="sxs-lookup"><span data-stu-id="b52d7-146">CSVoiceAdmin</span></span></p>
<p><span data-ttu-id="b52d7-147">CSLocationAdmin</span><span class="sxs-lookup"><span data-stu-id="b52d7-147">CSLocationAdmin</span></span></p></td>
<td><p><span data-ttu-id="b52d7-148"><a href="lync-server-2013-configure-the-location-database.md">Configure the location database in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="b52d7-148"><a href="lync-server-2013-configure-the-location-database.md">Configure the location database in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b52d7-149">高度な機能を構成する (オプション)</span><span class="sxs-lookup"><span data-stu-id="b52d7-149">Configure Advanced Features (optional)</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="b52d7-150">SNMP アプリケーションの URL を構成します。</span><span class="sxs-lookup"><span data-stu-id="b52d7-150">Configure the URL for the SNMP application.</span></span></p></li>
<li><p><span data-ttu-id="b52d7-151">セカンダリの場所情報サービスの場所の URL を構成します。</span><span class="sxs-lookup"><span data-stu-id="b52d7-151">Configure the URL for the location of the Secondary Location Information service.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="b52d7-152">CSVoiceAdmin</span><span class="sxs-lookup"><span data-stu-id="b52d7-152">CSVoiceAdmin</span></span></p></td>
<td><p><span data-ttu-id="b52d7-153"><a href="lync-server-2013-configure-an-snmp-application.md">Lync Server 2013 での SNMP アプリケーションの構成</a></span><span class="sxs-lookup"><span data-stu-id="b52d7-153"><a href="lync-server-2013-configure-an-snmp-application.md">Configure an SNMP application in Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="b52d7-154"><a href="lync-server-2013-configure-a-secondary-location-information-service.md">Lync Server 2013 でセカンダリ場所情報サービスを構成する</a></span><span class="sxs-lookup"><span data-stu-id="b52d7-154"><a href="lync-server-2013-configure-a-secondary-location-information-service.md">Configure a secondary Location Information service in Lync Server 2013</a></span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

