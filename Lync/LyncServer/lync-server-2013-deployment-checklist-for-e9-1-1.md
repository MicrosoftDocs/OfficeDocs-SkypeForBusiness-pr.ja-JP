---
title: 'Lync Server 2013: E9-1-1 の展開チェックリスト'
description: 'Lync Server 2013: E9-1-1 の展開チェックリスト。'
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
ms.openlocfilehash: 0c93762e2acef5e065249ced17bfa0eab2f159e4
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48568359"
---
# <a name="deployment-checklist-for-e9-1-1-in-lync-server-2013"></a><span data-ttu-id="ea27f-103">Lync Server 2013 の E9-1-1 の展開チェックリスト</span><span class="sxs-lookup"><span data-stu-id="ea27f-103">Deployment checklist for E9-1-1 in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ea27f-104">_**トピックの最終更新日:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="ea27f-104">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="ea27f-105">Enhanced 9-1-1 (E9-1-1) について効果的な計画を行うには、以下の展開要件を含めるようにしてください。</span><span class="sxs-lookup"><span data-stu-id="ea27f-105">To plan effectively for Enhanced 9-1-1 (E9-1-1), be sure to include the following deployment requirements:</span></span>

  - <span data-ttu-id="ea27f-106">E9-1-1 を展開する場合の前提条件。</span><span class="sxs-lookup"><span data-stu-id="ea27f-106">Prerequisites for deploying E9-1-1.</span></span>

  - <span data-ttu-id="ea27f-107">E9-1-1 を展開するために必要なステップ。</span><span class="sxs-lookup"><span data-stu-id="ea27f-107">Steps that are required to deploy E9-1-1.</span></span>

<div>

## <a name="deployment-prerequisites-for-e9-1-1"></a><span data-ttu-id="ea27f-108">E9-1-1 の展開前提条件</span><span class="sxs-lookup"><span data-stu-id="ea27f-108">Deployment Prerequisites for E9-1-1</span></span>

<span data-ttu-id="ea27f-109">E9-1-1 を展開する前に、中央管理ストア、フロントエンドプールまたは Standard Edition サーバー、1つ以上の仲介サーバーまたは仲介サーバープール、および Lync Server クライアントを含む、Lync Server の内部サーバーを展開しておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="ea27f-109">Before you deploy E9-1-1, you must already have deployed your Lync Server internal servers, including a Central Management store, a Front End pool or a Standard Edition server, one or more Mediation Servers or Mediation Server pools, and Lync Server clients.</span></span> <span data-ttu-id="ea27f-110">E9-1-1 の展開はさらに、認定された緊急サービス サービス プロバイダーへの SIP トランク、または公衆交換電話網 (PSTN) への緊急位置識別番号 (ELIN) ゲートウェイも必要とします。</span><span class="sxs-lookup"><span data-stu-id="ea27f-110">In addition, an E9-1-1 deployment requires a SIP trunk to a qualified E9-1-1 service provider or an Emergency Location Identification Number (ELIN) gateway to your public switched telephone network (PSTN).</span></span> <span data-ttu-id="ea27f-111">Lync Server は、E9-1-1 サービスプロバイダーを米国内でのみ使用することをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="ea27f-111">Lync Server supports using E9-1-1 service providers only inside the United States.</span></span>

</div>

<div>

## <a name="deployment-process"></a><span data-ttu-id="ea27f-112">展開プロセス</span><span class="sxs-lookup"><span data-stu-id="ea27f-112">Deployment Process</span></span>

<span data-ttu-id="ea27f-113">次の表に、E9-1-1 展開プロセスの概要を示します。</span><span class="sxs-lookup"><span data-stu-id="ea27f-113">The following table provides an overview of the E9-1-1 deployment process.</span></span> <span data-ttu-id="ea27f-114">展開手順の詳細については、「展開」のドキュメントの「 [Configure Enhanced 9-1-1 In Lync Server 2013](lync-server-2013-configure-enhanced-9-1-1.md) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ea27f-114">For details about deployment steps, see [Configure Enhanced 9-1-1 in Lync Server 2013](lync-server-2013-configure-enhanced-9-1-1.md) in the Deployment documentation.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ea27f-115">フェーズ</span><span class="sxs-lookup"><span data-stu-id="ea27f-115">Phase</span></span></th>
<th><span data-ttu-id="ea27f-116">手順</span><span class="sxs-lookup"><span data-stu-id="ea27f-116">Steps</span></span></th>
<th><span data-ttu-id="ea27f-117">ロール</span><span class="sxs-lookup"><span data-stu-id="ea27f-117">Roles</span></span></th>
<th><span data-ttu-id="ea27f-118">展開のドキュメント</span><span class="sxs-lookup"><span data-stu-id="ea27f-118">Deployment documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ea27f-119">音声使用、ルート、およびトランクを構成する</span><span class="sxs-lookup"><span data-stu-id="ea27f-119">Configure voice usages, routes, and trunk configurations</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="ea27f-p103">新しい PSTN 使用法レコードを作成します。これは、場所のポリシーの [<strong>PSTN の使用法</strong>] 設定で使用する名前と同じです。</span><span class="sxs-lookup"><span data-stu-id="ea27f-p103">Create a new PSTN usage record. This is the same name that is used for the <strong>PSTN Usage</strong> setting in the location policy.</span></span></p></li>
<li><p><span data-ttu-id="ea27f-122">前のステップで作成した PSTN 使用法レコードに対するボイス ルートを作成するか割り当て、ゲートウェイ属性が E9-1-1 SIP トランクまたは ELIN ゲートウェイを指すようにします。</span><span class="sxs-lookup"><span data-stu-id="ea27f-122">Create or assign a voice route to the PSTN usage record created in the previous step and then point the gateway attribute to the E9-1-1 SIP trunk or ELIN gateway.</span></span></p></li>
<li><p><span data-ttu-id="ea27f-123">SIP トランク E9-1-1 サービス プロバイダーの場合は、<strong>Set-CsTrunkConfiguration –EnablePIDFLOSupport</strong> コマンドレットを使用して、SIP 経由の E9-1-1 呼び出しを処理するトランクが PIDF-LO データを渡すように設定します。</span><span class="sxs-lookup"><span data-stu-id="ea27f-123">For a SIP trunk E9-1-1 service provider, set the trunk that will be handling E9-1-1 calls over the SIP to pass PIDF-LO data by using the <strong>Set-CsTrunkConfiguration –EnablePIDFLOSupport</strong> cmdlet.</span></span></p></li>
<li><p><span data-ttu-id="ea27f-p104">必要に応じて、SIP トランク E9-1-1 サービス プロバイダーの場合は、E9-1-1 サービス プロバイダーの SIP トランクによって処理されない呼び出しに対するローカル PSTN ルートを作成するか、割り当てます。このルートは、E9-1-1 サービス プロバイダーへの接続が利用できない場合に使用されます。E9-1-1 サービス プロバイダーがサポートしている場合は、911 ダイヤル文字列を国または地域の Emergency Call Response Center (ECRC) の Direct Inward Dialing (DID) 番号に変換するトランク構成ルールをゲートウェイに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="ea27f-p104">Optionally, for a SIP trunk E9-1-1 service provider, create or assign a local PSTN route for calls that are not handled by the E9-1-1 service provider’s SIP trunk. This route will be used if the connection to the E9-1-1 service provider is not available. If supported by your E9-1-1 service provider, assign a trunk configuration rule to the gateway that translates the 911 dial string into the direct inward dialing (DID) number of the national/regional Emergency Call Response Center (ECRC).</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="ea27f-127">CSVoiceAdmin</span><span class="sxs-lookup"><span data-stu-id="ea27f-127">CSVoiceAdmin</span></span></p></td>
<td><p><span data-ttu-id="ea27f-128"><a href="lync-server-2013-configure-an-e9-1-1-voice-route.md">Lync Server 2013 での E9-1-1 ボイスルートの構成</a></span><span class="sxs-lookup"><span data-stu-id="ea27f-128"><a href="lync-server-2013-configure-an-e9-1-1-voice-route.md">Configure an E9-1-1 voice route in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ea27f-129">場所のポリシーを作成し、ユーザーおよびサブネットに割り当てる</span><span class="sxs-lookup"><span data-stu-id="ea27f-129">Create location policies and assign them to users and subnets</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="ea27f-130">グローバルの場所のポリシーを確認します。</span><span class="sxs-lookup"><span data-stu-id="ea27f-130">Review the global location policy.</span></span></p></li>
<li><p><span data-ttu-id="ea27f-131">ユーザーレベル スコープで場所のポリシーを作成します。または、組織に緊急使用法が異なる複数のサイトがある場合は、ネットワークレベル スコープで場所のポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="ea27f-131">Create a location policy with a user-level scope; or, if the organization has more than one site with different emergency usages, create a location policy with a network-level scope.</span></span></p></li>
<li><p><span data-ttu-id="ea27f-132">場所のポリシーをネットワーク サイトに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="ea27f-132">Assign the location policy to network sites.</span></span></p></li>
<li><p><span data-ttu-id="ea27f-133">適切なサブネットをネットワーク サイトに追加します。</span><span class="sxs-lookup"><span data-stu-id="ea27f-133">Add the appropriate subnets to the network site.</span></span></p></li>
<li><p><span data-ttu-id="ea27f-134">(必要に応じて) 場所のポリシーをユーザー ポリシーに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="ea27f-134">(Optional) Assign the location policy to user policies.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="ea27f-135">CSVoiceAdmin</span><span class="sxs-lookup"><span data-stu-id="ea27f-135">CSVoiceAdmin</span></span></p>
<p><span data-ttu-id="ea27f-136">CSLocationAdmin (場所のポリシーの作成を除く)</span><span class="sxs-lookup"><span data-stu-id="ea27f-136">CSLocationAdmin (except for creating Location Policies)</span></span></p></td>
<td><p><span data-ttu-id="ea27f-137"><a href="lync-server-2013-create-location-policies.md">Lync Server 2013 での場所のポリシーの作成</a></span><span class="sxs-lookup"><span data-stu-id="ea27f-137"><a href="lync-server-2013-create-location-policies.md">Create location policies in Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="ea27f-138"><a href="lync-server-2013-add-a-location-policy-to-a-network-site.md">Lync Server 2013 でのネットワークサイトへの場所ポリシーの追加</a></span><span class="sxs-lookup"><span data-stu-id="ea27f-138"><a href="lync-server-2013-add-a-location-policy-to-a-network-site.md">Add a location policy to a network site in Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="ea27f-139"><a href="lync-server-2013-associate-subnets-with-network-sites-for-e9-1-1.md">Lync Server 2013 での E9-1-1 のネットワークサイトへのサブネットの関連付け</a></span><span class="sxs-lookup"><span data-stu-id="ea27f-139"><a href="lync-server-2013-associate-subnets-with-network-sites-for-e9-1-1.md">Associate subnets with network sites for E9-1-1 in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ea27f-140">場所データベースを構成する</span><span class="sxs-lookup"><span data-stu-id="ea27f-140">Configure the location database</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="ea27f-141">ネットワーク要素と場所のマッピングをデータベースに設定します。</span><span class="sxs-lookup"><span data-stu-id="ea27f-141">Populate the database with a mapping of network elements to locations.</span></span></p></li>
<li><p><span data-ttu-id="ea27f-142">ELIN ゲートウェイの場合は、[CompanyName] 列に ELINs を追加し &lt; &gt; ます。</span><span class="sxs-lookup"><span data-stu-id="ea27f-142">For ELIN gateways, add the ELINs to the &lt;CompanyName&gt; column.</span></span></p></li>
<li><p><span data-ttu-id="ea27f-143">アドレスを確認するために、E9-1-1 サービス プロバイダーへの接続を構成します。</span><span class="sxs-lookup"><span data-stu-id="ea27f-143">Configure the connection to the E9-1-1 service provider for validating addresses.</span></span></p></li>
<li><p><span data-ttu-id="ea27f-144">E9-1-1  サービス プロバイダーでアドレスを確認します。</span><span class="sxs-lookup"><span data-stu-id="ea27f-144">Validate the addresses with the E9-1-1 service provider.</span></span></p></li>
<li><p><span data-ttu-id="ea27f-145">更新したデータベースを公開します。</span><span class="sxs-lookup"><span data-stu-id="ea27f-145">Publish the updated database.</span></span></p></li>
<li><p><span data-ttu-id="ea27f-146">ELIN ゲートウェイの場合は、ELIN を PSTN 通信業者の自動ロケーション識別 (ALI) データベースにアップロードします。</span><span class="sxs-lookup"><span data-stu-id="ea27f-146">For ELIN gateways, upload the ELINs to your PSTN carrier's Automatic Location Identification (ALI) database.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="ea27f-147">CSVoiceAdmin</span><span class="sxs-lookup"><span data-stu-id="ea27f-147">CSVoiceAdmin</span></span></p>
<p><span data-ttu-id="ea27f-148">CSLocationAdmin</span><span class="sxs-lookup"><span data-stu-id="ea27f-148">CSLocationAdmin</span></span></p></td>
<td><p><span data-ttu-id="ea27f-149"><a href="lync-server-2013-configure-the-location-database.md">Lync Server 2013 で場所データベースを構成する</a></span><span class="sxs-lookup"><span data-stu-id="ea27f-149"><a href="lync-server-2013-configure-the-location-database.md">Configure the location database in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ea27f-150">高度な機能を構成する (オプション)</span><span class="sxs-lookup"><span data-stu-id="ea27f-150">Configure Advanced Features (optional)</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="ea27f-151">SNMP アプリケーションの URL を構成します。</span><span class="sxs-lookup"><span data-stu-id="ea27f-151">Configure the URL for the SNMP application.</span></span></p></li>
<li><p><span data-ttu-id="ea27f-152">セカンダリ場所情報サービスの場所の URL を構成します。</span><span class="sxs-lookup"><span data-stu-id="ea27f-152">Configure the URL for the location of the Secondary Location Information service.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="ea27f-153">CSVoiceAdmin</span><span class="sxs-lookup"><span data-stu-id="ea27f-153">CSVoiceAdmin</span></span></p></td>
<td><p><span data-ttu-id="ea27f-154"><a href="lync-server-2013-configure-an-snmp-application.md">Lync Server 2013 で SNMP アプリケーションを構成する</a></span><span class="sxs-lookup"><span data-stu-id="ea27f-154"><a href="lync-server-2013-configure-an-snmp-application.md">Configure an SNMP application in Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="ea27f-155"><a href="lync-server-2013-configure-a-secondary-location-information-service.md">Lync Server 2013 のセカンダリ場所情報サービスを構成する</a></span><span class="sxs-lookup"><span data-stu-id="ea27f-155"><a href="lync-server-2013-configure-a-secondary-location-information-service.md">Configure a secondary Location Information service in Lync Server 2013</a></span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

