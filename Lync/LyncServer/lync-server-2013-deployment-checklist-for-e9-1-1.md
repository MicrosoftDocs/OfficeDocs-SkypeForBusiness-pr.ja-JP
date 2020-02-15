---
title: 'Lync Server 2013: E9-1-1 の展開チェックリスト'
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
ms.openlocfilehash: 330f1a31f9a91d69c9e2514d0744abc72806bf4f
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2020
ms.locfileid: "42007005"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-checklist-for-e9-1-1-in-lync-server-2013"></a><span data-ttu-id="dde5d-102">Lync Server 2013 の E9-1-1 の展開チェックリスト</span><span class="sxs-lookup"><span data-stu-id="dde5d-102">Deployment checklist for E9-1-1 in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dde5d-103">_**トピックの最終更新日:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="dde5d-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="dde5d-104">Enhanced 9-1-1 (E9-1-1) について効果的な計画を行うには、以下の展開要件を含めるようにしてください。</span><span class="sxs-lookup"><span data-stu-id="dde5d-104">To plan effectively for Enhanced 9-1-1 (E9-1-1), be sure to include the following deployment requirements:</span></span>

  - <span data-ttu-id="dde5d-105">E9-1-1 を展開する場合の前提条件。</span><span class="sxs-lookup"><span data-stu-id="dde5d-105">Prerequisites for deploying E9-1-1.</span></span>

  - <span data-ttu-id="dde5d-106">E9-1-1 を展開するために必要なステップ。</span><span class="sxs-lookup"><span data-stu-id="dde5d-106">Steps that are required to deploy E9-1-1.</span></span>

<div>

## <a name="deployment-prerequisites-for-e9-1-1"></a><span data-ttu-id="dde5d-107">E9-1-1 の展開前提条件</span><span class="sxs-lookup"><span data-stu-id="dde5d-107">Deployment Prerequisites for E9-1-1</span></span>

<span data-ttu-id="dde5d-108">E9-1-1 を展開する前に、中央管理ストア、フロントエンドプールまたは Standard Edition サーバー、1つ以上の仲介サーバーまたは仲介サーバープール、および Lync Server クライアントを含む、Lync Server の内部サーバーを展開しておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="dde5d-108">Before you deploy E9-1-1, you must already have deployed your Lync Server internal servers, including a Central Management store, a Front End pool or a Standard Edition server, one or more Mediation Servers or Mediation Server pools, and Lync Server clients.</span></span> <span data-ttu-id="dde5d-109">E9-1-1 の展開はさらに、認定された緊急サービス サービス プロバイダーへの SIP トランク、または公衆交換電話網 (PSTN) への緊急位置識別番号 (ELIN) ゲートウェイも必要とします。</span><span class="sxs-lookup"><span data-stu-id="dde5d-109">In addition, an E9-1-1 deployment requires a SIP trunk to a qualified E9-1-1 service provider or an Emergency Location Identification Number (ELIN) gateway to your public switched telephone network (PSTN).</span></span> <span data-ttu-id="dde5d-110">Lync Server は、E9-1-1 サービスプロバイダーを米国内でのみ使用することをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="dde5d-110">Lync Server supports using E9-1-1 service providers only inside the United States.</span></span>

</div>

<div>

## <a name="deployment-process"></a><span data-ttu-id="dde5d-111">展開プロセス</span><span class="sxs-lookup"><span data-stu-id="dde5d-111">Deployment Process</span></span>

<span data-ttu-id="dde5d-112">次の表に、E9-1-1 展開プロセスの概要を示します。</span><span class="sxs-lookup"><span data-stu-id="dde5d-112">The following table provides an overview of the E9-1-1 deployment process.</span></span> <span data-ttu-id="dde5d-113">展開手順の詳細については、「展開」のドキュメントの「 [Configure Enhanced 9-1-1 In Lync Server 2013](lync-server-2013-configure-enhanced-9-1-1.md) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dde5d-113">For details about deployment steps, see [Configure Enhanced 9-1-1 in Lync Server 2013](lync-server-2013-configure-enhanced-9-1-1.md) in the Deployment documentation.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="dde5d-114">フェーズ</span><span class="sxs-lookup"><span data-stu-id="dde5d-114">Phase</span></span></th>
<th><span data-ttu-id="dde5d-115">手順</span><span class="sxs-lookup"><span data-stu-id="dde5d-115">Steps</span></span></th>
<th><span data-ttu-id="dde5d-116">ロール</span><span class="sxs-lookup"><span data-stu-id="dde5d-116">Roles</span></span></th>
<th><span data-ttu-id="dde5d-117">展開のドキュメント</span><span class="sxs-lookup"><span data-stu-id="dde5d-117">Deployment documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="dde5d-118">音声使用、ルート、およびトランクを構成する</span><span class="sxs-lookup"><span data-stu-id="dde5d-118">Configure voice usages, routes, and trunk configurations</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="dde5d-p103">新しい PSTN 使用法レコードを作成します。これは、場所のポリシーの [<strong>PSTN の使用法</strong>] 設定で使用する名前と同じです。</span><span class="sxs-lookup"><span data-stu-id="dde5d-p103">Create a new PSTN usage record. This is the same name that is used for the <strong>PSTN Usage</strong> setting in the location policy.</span></span></p></li>
<li><p><span data-ttu-id="dde5d-121">前のステップで作成した PSTN 使用法レコードに対するボイス ルートを作成するか割り当て、ゲートウェイ属性が E9-1-1 SIP トランクまたは ELIN ゲートウェイを指すようにします。</span><span class="sxs-lookup"><span data-stu-id="dde5d-121">Create or assign a voice route to the PSTN usage record created in the previous step and then point the gateway attribute to the E9-1-1 SIP trunk or ELIN gateway.</span></span></p></li>
<li><p><span data-ttu-id="dde5d-122">SIP トランク E9-1-1 サービス プロバイダーの場合は、<strong>Set-CsTrunkConfiguration –EnablePIDFLOSupport</strong> コマンドレットを使用して、SIP 経由の E9-1-1 呼び出しを処理するトランクが PIDF-LO データを渡すように設定します。</span><span class="sxs-lookup"><span data-stu-id="dde5d-122">For a SIP trunk E9-1-1 service provider, set the trunk that will be handling E9-1-1 calls over the SIP to pass PIDF-LO data by using the <strong>Set-CsTrunkConfiguration –EnablePIDFLOSupport</strong> cmdlet.</span></span></p></li>
<li><p><span data-ttu-id="dde5d-p104">必要に応じて、SIP トランク E9-1-1 サービス プロバイダーの場合は、E9-1-1 サービス プロバイダーの SIP トランクによって処理されない呼び出しに対するローカル PSTN ルートを作成するか、割り当てます。このルートは、E9-1-1 サービス プロバイダーへの接続が利用できない場合に使用されます。E9-1-1 サービス プロバイダーがサポートしている場合は、911 ダイヤル文字列を国または地域の Emergency Call Response Center (ECRC) の Direct Inward Dialing (DID) 番号に変換するトランク構成ルールをゲートウェイに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="dde5d-p104">Optionally, for a SIP trunk E9-1-1 service provider, create or assign a local PSTN route for calls that are not handled by the E9-1-1 service provider’s SIP trunk. This route will be used if the connection to the E9-1-1 service provider is not available. If supported by your E9-1-1 service provider, assign a trunk configuration rule to the gateway that translates the 911 dial string into the direct inward dialing (DID) number of the national/regional Emergency Call Response Center (ECRC).</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="dde5d-126">CSVoiceAdmin</span><span class="sxs-lookup"><span data-stu-id="dde5d-126">CSVoiceAdmin</span></span></p></td>
<td><p><span data-ttu-id="dde5d-127"><a href="lync-server-2013-configure-an-e9-1-1-voice-route.md">Lync Server 2013 での E9-1-1 ボイスルートの構成</a></span><span class="sxs-lookup"><span data-stu-id="dde5d-127"><a href="lync-server-2013-configure-an-e9-1-1-voice-route.md">Configure an E9-1-1 voice route in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dde5d-128">場所のポリシーを作成し、ユーザーおよびサブネットに割り当てる</span><span class="sxs-lookup"><span data-stu-id="dde5d-128">Create location policies and assign them to users and subnets</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="dde5d-129">グローバルの場所のポリシーを確認します。</span><span class="sxs-lookup"><span data-stu-id="dde5d-129">Review the global location policy.</span></span></p></li>
<li><p><span data-ttu-id="dde5d-130">ユーザーレベル スコープで場所のポリシーを作成します。または、組織に緊急使用法が異なる複数のサイトがある場合は、ネットワークレベル スコープで場所のポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="dde5d-130">Create a location policy with a user-level scope; or, if the organization has more than one site with different emergency usages, create a location policy with a network-level scope.</span></span></p></li>
<li><p><span data-ttu-id="dde5d-131">場所のポリシーをネットワーク サイトに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="dde5d-131">Assign the location policy to network sites.</span></span></p></li>
<li><p><span data-ttu-id="dde5d-132">適切なサブネットをネットワーク サイトに追加します。</span><span class="sxs-lookup"><span data-stu-id="dde5d-132">Add the appropriate subnets to the network site.</span></span></p></li>
<li><p><span data-ttu-id="dde5d-133">(必要に応じて) 場所のポリシーをユーザー ポリシーに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="dde5d-133">(Optional) Assign the location policy to user policies.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="dde5d-134">CSVoiceAdmin</span><span class="sxs-lookup"><span data-stu-id="dde5d-134">CSVoiceAdmin</span></span></p>
<p><span data-ttu-id="dde5d-135">CSLocationAdmin (場所のポリシーの作成を除く)</span><span class="sxs-lookup"><span data-stu-id="dde5d-135">CSLocationAdmin (except for creating Location Policies)</span></span></p></td>
<td><p><span data-ttu-id="dde5d-136"><a href="lync-server-2013-create-location-policies.md">Lync Server 2013 での場所のポリシーの作成</a></span><span class="sxs-lookup"><span data-stu-id="dde5d-136"><a href="lync-server-2013-create-location-policies.md">Create location policies in Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="dde5d-137"><a href="lync-server-2013-add-a-location-policy-to-a-network-site.md">Lync Server 2013 でのネットワークサイトへの場所ポリシーの追加</a></span><span class="sxs-lookup"><span data-stu-id="dde5d-137"><a href="lync-server-2013-add-a-location-policy-to-a-network-site.md">Add a location policy to a network site in Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="dde5d-138"><a href="lync-server-2013-associate-subnets-with-network-sites-for-e9-1-1.md">Lync Server 2013 での E9-1-1 のネットワークサイトへのサブネットの関連付け</a></span><span class="sxs-lookup"><span data-stu-id="dde5d-138"><a href="lync-server-2013-associate-subnets-with-network-sites-for-e9-1-1.md">Associate subnets with network sites for E9-1-1 in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dde5d-139">場所データベースを構成する</span><span class="sxs-lookup"><span data-stu-id="dde5d-139">Configure the location database</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="dde5d-140">ネットワーク要素と場所のマッピングをデータベースに設定します。</span><span class="sxs-lookup"><span data-stu-id="dde5d-140">Populate the database with a mapping of network elements to locations.</span></span></p></li>
<li><p><span data-ttu-id="dde5d-141">ELIN ゲートウェイの場合は、[ &lt;CompanyName&gt; ] 列に elins を追加します。</span><span class="sxs-lookup"><span data-stu-id="dde5d-141">For ELIN gateways, add the ELINs to the &lt;CompanyName&gt; column.</span></span></p></li>
<li><p><span data-ttu-id="dde5d-142">アドレスを確認するために、E9-1-1 サービス プロバイダーへの接続を構成します。</span><span class="sxs-lookup"><span data-stu-id="dde5d-142">Configure the connection to the E9-1-1 service provider for validating addresses.</span></span></p></li>
<li><p><span data-ttu-id="dde5d-143">E9-1-1  サービス プロバイダーでアドレスを確認します。</span><span class="sxs-lookup"><span data-stu-id="dde5d-143">Validate the addresses with the E9-1-1 service provider.</span></span></p></li>
<li><p><span data-ttu-id="dde5d-144">更新したデータベースを公開します。</span><span class="sxs-lookup"><span data-stu-id="dde5d-144">Publish the updated database.</span></span></p></li>
<li><p><span data-ttu-id="dde5d-145">ELIN ゲートウェイの場合は、ELIN を PSTN 通信業者の自動ロケーション識別 (ALI) データベースにアップロードします。</span><span class="sxs-lookup"><span data-stu-id="dde5d-145">For ELIN gateways, upload the ELINs to your PSTN carrier's Automatic Location Identification (ALI) database.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="dde5d-146">CSVoiceAdmin</span><span class="sxs-lookup"><span data-stu-id="dde5d-146">CSVoiceAdmin</span></span></p>
<p><span data-ttu-id="dde5d-147">CSLocationAdmin</span><span class="sxs-lookup"><span data-stu-id="dde5d-147">CSLocationAdmin</span></span></p></td>
<td><p><span data-ttu-id="dde5d-148"><a href="lync-server-2013-configure-the-location-database.md">Lync Server 2013 で場所データベースを構成する</a></span><span class="sxs-lookup"><span data-stu-id="dde5d-148"><a href="lync-server-2013-configure-the-location-database.md">Configure the location database in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dde5d-149">高度な機能を構成する (オプション)</span><span class="sxs-lookup"><span data-stu-id="dde5d-149">Configure Advanced Features (optional)</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="dde5d-150">SNMP アプリケーションの URL を構成します。</span><span class="sxs-lookup"><span data-stu-id="dde5d-150">Configure the URL for the SNMP application.</span></span></p></li>
<li><p><span data-ttu-id="dde5d-151">セカンダリ場所情報サービスの場所の URL を構成します。</span><span class="sxs-lookup"><span data-stu-id="dde5d-151">Configure the URL for the location of the Secondary Location Information service.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="dde5d-152">CSVoiceAdmin</span><span class="sxs-lookup"><span data-stu-id="dde5d-152">CSVoiceAdmin</span></span></p></td>
<td><p><span data-ttu-id="dde5d-153"><a href="lync-server-2013-configure-an-snmp-application.md">Lync Server 2013 で SNMP アプリケーションを構成する</a></span><span class="sxs-lookup"><span data-stu-id="dde5d-153"><a href="lync-server-2013-configure-an-snmp-application.md">Configure an SNMP application in Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="dde5d-154"><a href="lync-server-2013-configure-a-secondary-location-information-service.md">Lync Server 2013 のセカンダリ場所情報サービスを構成する</a></span><span class="sxs-lookup"><span data-stu-id="dde5d-154"><a href="lync-server-2013-configure-a-secondary-location-information-service.md">Configure a secondary Location Information service in Lync Server 2013</a></span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

