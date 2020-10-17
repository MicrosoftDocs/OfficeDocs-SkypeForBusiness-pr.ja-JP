---
title: さまざまなポリシーの構成
description: さまざまなポリシーを構成します。
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Configuring the Various Policies
ms:assetid: e3b3cbda-7c17-470b-acb0-82fdcc473184
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945610(v=OCS.15)
ms:contentKeyID: 51541436
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 746d299ac605c7dfe89a957246d47309dfbc0a5d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48548843"
---
# <a name="configuring-the-various-policies"></a><span data-ttu-id="850ff-103">さまざまなポリシーの構成</span><span class="sxs-lookup"><span data-stu-id="850ff-103">Configuring the Various Policies</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="850ff-104">_**トピックの最終更新日:** 2013-02-24_</span><span class="sxs-lookup"><span data-stu-id="850ff-104">_**Topic Last Modified:** 2013-02-24_</span></span>

<div>

<span data-ttu-id="850ff-105">ここでは、lync Server 2013 ストレスおよびパフォーマンスツールを実行する前に、Lync Server 2013 トポロジで構成できるさまざまなポリシーについて説明します。</span><span class="sxs-lookup"><span data-stu-id="850ff-105">Here are the various policies that you can configure in your Lync Server 2013 topology, prior to running the Lync Server 2013 Stress and Performance Tool.</span></span>

<div>

## <a name="configuring-the-archiving-policy"></a><span data-ttu-id="850ff-106">アーカイブポリシーの構成</span><span class="sxs-lookup"><span data-stu-id="850ff-106">Configuring the Archiving Policy</span></span>

<span data-ttu-id="850ff-107">スクリプト ArchivingPolicy.ps1 の例を参照してください。</span><span class="sxs-lookup"><span data-stu-id="850ff-107">See the example script ArchivingPolicy.ps1.</span></span> <span data-ttu-id="850ff-108">このスクリプトは、アーカイブサーバーがトポロジに展開されている場合にのみ使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="850ff-108">You need to use this script only if an Archiving Server is deployed in your topology.</span></span> <span data-ttu-id="850ff-109">詳細については、「lync server 2013 のドキュメントとコマンドレットのヘルプ」を参照してください。 [Lync server 2013 でのコマンドレットのアーカイブおよび監視](https://technet.microsoft.com/library/gg415629\(v=ocs.15\))について説明します。</span><span class="sxs-lookup"><span data-stu-id="850ff-109">For details, see the Lync Server 2013 documentation and cmdlet Help for [Archiving and Monitoring cmdlets in Lync Server 2013](https://technet.microsoft.com/library/gg415629\(v=ocs.15\)).</span></span>

</div>

<div>

## <a name="configuring-the-conferencing-policy"></a><span data-ttu-id="850ff-110">会議ポリシーの構成</span><span class="sxs-lookup"><span data-stu-id="850ff-110">Configuring the Conferencing Policy</span></span>

<span data-ttu-id="850ff-111">スクリプト MeetingPolicy.ps1 の例を参照してください。</span><span class="sxs-lookup"><span data-stu-id="850ff-111">See the example script MeetingPolicy.ps1.</span></span> <span data-ttu-id="850ff-112">詳細については、「lync server 2013 のドキュメント」および「 [Lync server 2013 での Web 会議のコマンド](https://technet.microsoft.com/library/gg415675\(v=ocs.15\))レットに関するヘルプ」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="850ff-112">For details, see the Lync Server 2013 documentation and the cmdlet Help for [Web conferencing cmdlets in Lync Server 2013](https://technet.microsoft.com/library/gg415675\(v=ocs.15\)).</span></span>

</div>

<div>

## <a name="configuring-the-contacts-policy"></a><span data-ttu-id="850ff-113">連絡先ポリシーを構成する</span><span class="sxs-lookup"><span data-stu-id="850ff-113">Configuring the Contacts Policy</span></span>

<span data-ttu-id="850ff-114">ContactsPolicy.ps1 の例を参照してください。</span><span class="sxs-lookup"><span data-stu-id="850ff-114">See the example ContactsPolicy.ps1.</span></span> <span data-ttu-id="850ff-115">詳細については、「lync server 2013 のドキュメントと、 [Lync server 2013 の IM およびプレゼンスのコマンド](https://technet.microsoft.com/library/gg398611\(v=ocs.15\))レットのヘルプ」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="850ff-115">For details, see the Lync Server 2013 documentation and the cmdlet Help for [IM and presence cmdlets in Lync Server 2013](https://technet.microsoft.com/library/gg398611\(v=ocs.15\)).</span></span>

</div>

<div>

## <a name="configuring-the-federation-policy"></a><span data-ttu-id="850ff-116">フェデレーションポリシーを構成する</span><span class="sxs-lookup"><span data-stu-id="850ff-116">Configuring the Federation Policy</span></span>

<span data-ttu-id="850ff-117">FederationPolicy.ps1 の例を参照してください。</span><span class="sxs-lookup"><span data-stu-id="850ff-117">See the example FederationPolicy.ps1.</span></span> <span data-ttu-id="850ff-118">詳細については、「lync server 2013 での [エッジサーバーのコマンドレット](https://technet.microsoft.com/library/gg415635\(v=ocs.15\)) 」および「lync server [2013 でのフェデレーションと外部アクセスのコマンド](https://technet.microsoft.com/library/gg415651\(v=ocs.15\))レットのための lync server 2013 ドキュメントとコマンドレットのヘルプ」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="850ff-118">For details, see the Lync Server 2013 documentation and the cmdlet Help for [Edge Server cmdlets in Lync Server 2013](https://technet.microsoft.com/library/gg415635\(v=ocs.15\)) and [Federation and external access cmdlets in Lync Server 2013](https://technet.microsoft.com/library/gg415651\(v=ocs.15\)).</span></span>

</div>

<div>

## <a name="configuring-the-call-admission-control-policy"></a><span data-ttu-id="850ff-119">通話受付管理ポリシーの構成</span><span class="sxs-lookup"><span data-stu-id="850ff-119">Configuring the Call Admission Control Policy</span></span>

<span data-ttu-id="850ff-120">BandwidthPolicy.ps1 の例を参照してください。</span><span class="sxs-lookup"><span data-stu-id="850ff-120">See the example BandwidthPolicy.ps1.</span></span> <span data-ttu-id="850ff-121">詳細については、lync server [2013 の通話受付管理の](https://technet.microsoft.com/library/gg398529\(v=ocs.15\)) lync server 2013 ドキュメントの概要と、 [lync server 2013 での通話受付管理のコマンド](https://technet.microsoft.com/library/gg415676\(v=ocs.15\))レットのヘルプを参照してください。</span><span class="sxs-lookup"><span data-stu-id="850ff-121">For details, see the Lync Server 2013 documentation [Overview of call admission control in Lync Server 2013](https://technet.microsoft.com/library/gg398529\(v=ocs.15\)) and the cmdlet Help for [Call admission control cmdlets in Lync Server 2013](https://technet.microsoft.com/library/gg415676\(v=ocs.15\)).</span></span>

</div>

<div>

## <a name="configuring-the-voice-routing-rules"></a><span data-ttu-id="850ff-122">音声ルーティングルールの構成</span><span class="sxs-lookup"><span data-stu-id="850ff-122">Configuring the Voice Routing Rules</span></span>

<span data-ttu-id="850ff-123">RoutingRules.ps1 の例を参照してください。</span><span class="sxs-lookup"><span data-stu-id="850ff-123">See the example RoutingRules.ps1.</span></span> <span data-ttu-id="850ff-124">音声ルーティングルールを構成するときは、電話のコンテキスト (つまり、[場所のプロファイル] または [simplename]) と [内部/外部] エリアコードをメモしてください。これにより、ユーザーの作成時および LyncPerfTool の構成 (特に PSTN と UC) の間にそれらを指定できるようになります。</span><span class="sxs-lookup"><span data-stu-id="850ff-124">When you configure the voice routing rules, take note of the Phone Context (that is, /Location Profile or /SimpleName) and Internal/External Area Codes so that you can specify them when creating users and during LyncPerfTool configuration (specifically for PSTN-UC and UC-PSTN).</span></span> <span data-ttu-id="850ff-125">たとえば、RoutingRules.ps1 の例の **get-csdialplan** コマンドレットの simplename パラメーターは、UserProfileGenerator.exe の次の図の locationprofile 値に使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="850ff-125">For example, the SimpleName parameter in the call to the **New-CsDialPlan** cmdlet in the RoutingRules.ps1 example should be used for the LocationProfile value in the following figure of UserProfileGenerator.exe.</span></span>

<span data-ttu-id="850ff-126">![音声ルーティングルールの例。](images/JJ945610.9f34d971-4ed0-4a4c-b101-086a91c4578c(OCS.15).jpg "音声ルーティングルールの例。")</span><span class="sxs-lookup"><span data-stu-id="850ff-126">![Sample voice routing rule.](images/JJ945610.9f34d971-4ed0-4a4c-b101-086a91c4578c(OCS.15).jpg "Sample voice routing rule.")</span></span>

<span data-ttu-id="850ff-127">詳細については、「lync server 2013 のドキュメント」および「 [Lync server 2013 でのエンタープライズ voip のコマンド](https://technet.microsoft.com/library/gg415658\(v=ocs.15\))レットのヘルプ」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="850ff-127">For details, see the Lync Server 2013 documentation and the cmdlet Help for [Enterprise Voice cmdlets in Lync Server 2013](https://technet.microsoft.com/library/gg415658\(v=ocs.15\)).</span></span>

</div>

<div>

## <a name="configuring-conferencing-attendant-application"></a><span data-ttu-id="850ff-128">会議アテンダントアプリケーションを構成する</span><span class="sxs-lookup"><span data-stu-id="850ff-128">Configuring Conferencing Attendant application</span></span>

<span data-ttu-id="850ff-129">ConferenceAutoAttendantConfiguration.ps1 の例を参照してください。</span><span class="sxs-lookup"><span data-stu-id="850ff-129">See the example ConferenceAutoAttendantConfiguration.ps1.</span></span> <span data-ttu-id="850ff-130">ConferencingAutoAttendant 電話番号 (既定では 1121111111) をメモして、構成を生成するために LyncPerf ツール構成ツールに入力できるようにします。</span><span class="sxs-lookup"><span data-stu-id="850ff-130">Take note of the ConferencingAutoAttendant phone number (1121111111, by default), so that you can type it into the LyncPerf Tool Configuration tool for configuration generation.</span></span>

<span data-ttu-id="850ff-131">![会議アテンダントアプリケーションを構成する](images/JJ945610.0618a22f-27a9-423a-9085-d2bf71e82db6(OCS.15).jpg "会議アテンダントアプリケーションを構成する")</span><span class="sxs-lookup"><span data-stu-id="850ff-131">![Configuring the Conferencing Attendant application](images/JJ945610.0618a22f-27a9-423a-9085-d2bf71e82db6(OCS.15).jpg "Configuring the Conferencing Attendant application")</span></span>

<span data-ttu-id="850ff-132">詳細については、lync server [2013 の Web 会議](https://technet.microsoft.com/library/gg415675\(v=ocs.15\)) のコマンドレットおよび lync [Server 2013 のダイヤルイン会議](https://technet.microsoft.com/library/gg415630\(v=ocs.15\))のコマンドレットについて、lync server 2013 のドキュメントとコマンドレットのヘルプを参照してください。</span><span class="sxs-lookup"><span data-stu-id="850ff-132">For details, see the Lync Server 2013 documentation and the cmdlet Help for [Web conferencing cmdlets in Lync Server 2013](https://technet.microsoft.com/library/gg415675\(v=ocs.15\)) and [Dial-in conferencing cmdlets in Lync Server 2013](https://technet.microsoft.com/library/gg415630\(v=ocs.15\)).</span></span>

</div>

<div>

## <a name="configuring-lync-server-call-park-service"></a><span data-ttu-id="850ff-133">Lync Server コールパークサービスの構成</span><span class="sxs-lookup"><span data-stu-id="850ff-133">Configuring Lync Server Call Park Service</span></span>

<span data-ttu-id="850ff-134">コールパークは既定で無効になっています。</span><span class="sxs-lookup"><span data-stu-id="850ff-134">Call Park is disabled by default.</span></span> <span data-ttu-id="850ff-135">CallParkConfiguration.ps1 の例を参照してください。</span><span class="sxs-lookup"><span data-stu-id="850ff-135">See the example CallParkConfiguration.ps1.</span></span> <span data-ttu-id="850ff-136">詳細については、「lync server 2013 のドキュメント」および「 [Lync server 2013 のコールパークアプリケーションのコマンド](https://technet.microsoft.com/library/gg415639\(v=ocs.15\))レットに関するヘルプ」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="850ff-136">For details, see the Lync Server 2013 documentation and the cmdlet Help for [Call Park application cmdlets in Lync Server 2013](https://technet.microsoft.com/library/gg415639\(v=ocs.15\)).</span></span>

</div>

<div>

## <a name="configuring-emergency-calls"></a><span data-ttu-id="850ff-137">緊急電話の構成</span><span class="sxs-lookup"><span data-stu-id="850ff-137">Configuring Emergency Calls</span></span>

<span data-ttu-id="850ff-138">次の手順を実行して、緊急電話のストレスとパフォーマンスのテストを構成します。</span><span class="sxs-lookup"><span data-stu-id="850ff-138">Perform the following steps to configure stress and performance testing for emergency calls.</span></span>

1.  <span data-ttu-id="850ff-139">緊急電話の音声ルートを設定します。</span><span class="sxs-lookup"><span data-stu-id="850ff-139">Set up a voice route for emergency calls.</span></span> <span data-ttu-id="850ff-140">この音声ルートを設定する例については、「E911 から PSTN へのルーティング」のコメントの下にある RoutingRules.ps1 スクリプトを参照してください。</span><span class="sxs-lookup"><span data-stu-id="850ff-140">See the RoutingRules.ps1 script under the comment "Route E911 to PSTN" for an example of setting up this voice route.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="850ff-141">RoutingRules.ps1 のコマンドの例では、911ではなく、119の数値パターンが指定されています。</span><span class="sxs-lookup"><span data-stu-id="850ff-141">The example command in RoutingRules.ps1 has a number pattern that includes the number 119 rather than 911.</span></span> <span data-ttu-id="850ff-142">ロードテスト時にローカルの緊急対応オペレーターを誤って呼び出すことを防ぐには、911 (または実際のローカル緊急電話番号) を使用しないようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="850ff-142">You should avoid using 911 (or your actual local emergency number) to prevent accidental calls to your local emergency operators during load testing.</span></span> <span data-ttu-id="850ff-143">この構成はシミュレーションのみを目的としています。</span><span class="sxs-lookup"><span data-stu-id="850ff-143">This configuration is for simulation purposes only.</span></span>

    
    </div>

2.  <span data-ttu-id="850ff-144">次の図に示すように、Userプロビジョニングツールの [ **LIS** ] タブで値を入力して、アドレスを構成します。</span><span class="sxs-lookup"><span data-stu-id="850ff-144">Configure addresses by filling in the values on the **LIS** tab in the UserProvisioningTool, as shown in the following figure.</span></span>
    
    <span data-ttu-id="850ff-145">![場所情報サービスを構成します。](images/JJ945610.8ac1faa1-e9f9-40d0-b8b7-b159f4f459f7(OCS.15).jpg "場所情報サービスを構成します。")</span><span class="sxs-lookup"><span data-stu-id="850ff-145">![Configuring the Location Information Service.](images/JJ945610.8ac1faa1-e9f9-40d0-b8b7-b159f4f459f7(OCS.15).jpg "Configuring the Location Information Service.")</span></span>  

3.  <span data-ttu-id="850ff-146">[ **LIS Config ファイルの生成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="850ff-146">Click **Generate LIS Config Files**.</span></span>

4.  <span data-ttu-id="850ff-147">ポート、サブネット、スイッチ、ワイヤレスアクセスポイント (Wap) の CSV ファイル、および Lync Server 2013 ストレスおよびパフォーマンスツール用の XML ファイルが生成されます。</span><span class="sxs-lookup"><span data-stu-id="850ff-147">CSV files for ports, subnets, switches, and wireless access points (WAPs), and an XML file for the Lync Server 2013 Stress and Performance Tool, are generated.</span></span> <span data-ttu-id="850ff-148">CSV ファイルは、LisConfiguration.ps1 スクリプトを使用して場所情報サービス (LIS) を構成するときに、同じフォルダー内の入力として使用されます。</span><span class="sxs-lookup"><span data-stu-id="850ff-148">The CSV files are to be used as inputs (in the same folder) when configuring Location Information service (LIS) with the LisConfiguration.ps1 script.</span></span> <span data-ttu-id="850ff-149">生成された Locations0.xml ファイルを、Lync Server 2013 ストレスおよびパフォーマンスツールの実行可能ファイル (LyncPerfTool.exe) と同じフォルダーに移動します。これにより、場所プロファイル (ダイヤルプラン) のシナリオが実行されます。</span><span class="sxs-lookup"><span data-stu-id="850ff-149">Move the generated Locations0.xml file to the same folder as the Lync Server 2013 Stress and Performance Tool executable (LyncPerfTool.exe), which will run location profile (dial plan) scenarios.</span></span>

</div>

<div>

## <a name="creating-enabling-configuring-and-disabling-users"></a><span data-ttu-id="850ff-150">ユーザーの作成、有効化、構成、無効化</span><span class="sxs-lookup"><span data-stu-id="850ff-150">Creating, Enabling, Configuring and Disabling Users</span></span>

<span data-ttu-id="850ff-151">次のスクリプトを実行する前に、すべてのユーザーを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="850ff-151">You should create all your users before running the following scripts.</span></span> <span data-ttu-id="850ff-152">[ [ユーザーと連絡先を作成](create-users-and-contacts.md) する] の指示に従って、ユーザーを作成します。</span><span class="sxs-lookup"><span data-stu-id="850ff-152">Follow the instructions in [Create Users and Contacts](create-users-and-contacts.md) to create users.</span></span> <span data-ttu-id="850ff-153">詳細については、「 [get-help](https://technet.microsoft.com/library/gg398125\(v=ocs.15\))user」、「 [Set-csuser](https://technet.microsoft.com/library/gg398510\(v=ocs.15\))」、および「 [Disable-Csuser](https://technet.microsoft.com/library/gg398747\(v=ocs.15\)) コマンドレット」の Lync Server 2013 コマンドレットのドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="850ff-153">For details, see the Lync Server 2013 cmdlet documentation for the [Get-CsUser](https://technet.microsoft.com/library/gg398125\(v=ocs.15\)), [Set-CsUser](https://technet.microsoft.com/library/gg398510\(v=ocs.15\)), and [Disable-CsUser](https://technet.microsoft.com/library/gg398747\(v=ocs.15\)) cmdlets.</span></span>

</div>

<div>

## <a name="configuring-response-group-application"></a><span data-ttu-id="850ff-154">応答グループアプリケーションの構成</span><span class="sxs-lookup"><span data-stu-id="850ff-154">Configuring Response Group application</span></span>

<span data-ttu-id="850ff-155">ResponseGroupConfiguration.ps1 の例を参照してください。</span><span class="sxs-lookup"><span data-stu-id="850ff-155">See the example ResponseGroupConfiguration.ps1.</span></span> <span data-ttu-id="850ff-156">詳細については、lync server 2013 のドキュメントとコマンドレットのヘルプを参照してください。 [Lync server 2013 の応答グループアプリケーションのコマンドレット](https://technet.microsoft.com/library/gg415654\(v=ocs.15\))を参照してください。応答グループアプリケーションの構成を確認するには、 `https://<poolfqdn>/RgsConfig/` 次の図に示すように「」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="850ff-156">For details, see the Lync Server 2013 documentation and the cmdlet Help for [Response Group application cmdlets in Lync Server 2013](https://technet.microsoft.com/library/gg415654\(v=ocs.15\)).To review the Response Group application configuration, see `https://<poolfqdn>/RgsConfig/`, as shown in the following figure.</span></span>

<span data-ttu-id="850ff-157">![応答グループ構成ツール。](images/JJ945610.480a9440-2283-4533-98f8-86daaab4781c(OCS.15).jpg "応答グループ構成ツール。")</span><span class="sxs-lookup"><span data-stu-id="850ff-157">![The Response Group Configuration Tool.](images/JJ945610.480a9440-2283-4533-98f8-86daaab4781c(OCS.15).jpg "The Response Group Configuration Tool.")</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

