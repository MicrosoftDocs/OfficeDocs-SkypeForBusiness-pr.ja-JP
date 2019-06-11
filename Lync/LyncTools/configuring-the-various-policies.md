---
title: 各種ポリシーの構成
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Configuring the Various Policies
ms:assetid: e3b3cbda-7c17-470b-acb0-82fdcc473184
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945610(v=OCS.15)
ms:contentKeyID: 51541436
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a105ea62b82d904007a2faa0493fd17092b84462
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34841051"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-the-various-policies"></a><span data-ttu-id="c6d62-102">各種ポリシーの構成</span><span class="sxs-lookup"><span data-stu-id="c6d62-102">Configuring the Various Policies</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c6d62-103">_**最終更新日:** 2013-02-24_</span><span class="sxs-lookup"><span data-stu-id="c6d62-103">_**Topic Last Modified:** 2013-02-24_</span></span>

<div>

## <a name="configuring-the-various-policies"></a><span data-ttu-id="c6d62-104">各種ポリシーの構成</span><span class="sxs-lookup"><span data-stu-id="c6d62-104">Configuring the Various Policies</span></span>

<span data-ttu-id="c6d62-105">Lync Server 2013 のストレスとパフォーマンスツールを実行する前に、Lync Server 2013 トポロジで構成できる各種のポリシーを次に示します。</span><span class="sxs-lookup"><span data-stu-id="c6d62-105">Here are the various policies that you can configure in your Lync Server 2013 topology, prior to running the Lync Server 2013 Stress and Performance Tool.</span></span>

<div>

## <a name="configuring-the-archiving-policy"></a><span data-ttu-id="c6d62-106">アーカイブポリシーを構成する</span><span class="sxs-lookup"><span data-stu-id="c6d62-106">Configuring the Archiving Policy</span></span>

<span data-ttu-id="c6d62-107">「スクリプト ArchivingPolicy の例を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c6d62-107">See the example script ArchivingPolicy.ps1.</span></span> <span data-ttu-id="c6d62-108">このスクリプトは、アーカイブサーバーがトポロジに展開されている場合にのみ使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c6d62-108">You need to use this script only if an Archiving Server is deployed in your topology.</span></span> <span data-ttu-id="c6d62-109">詳細については、「lync Server 2013 のドキュメントとコマンドレットのヘルプ」を参照してください。 [lync server 2013 のコマンドレットのアーカイブと監視](https://technet.microsoft.com/en-us/library/gg415629\(v=ocs.15\))を行います。</span><span class="sxs-lookup"><span data-stu-id="c6d62-109">For details, see the Lync Server 2013 documentation and cmdlet Help for [Archiving and Monitoring cmdlets in Lync Server 2013](https://technet.microsoft.com/en-us/library/gg415629\(v=ocs.15\)).</span></span>

</div>

<div>

## <a name="configuring-the-conferencing-policy"></a><span data-ttu-id="c6d62-110">会議ポリシーを構成する</span><span class="sxs-lookup"><span data-stu-id="c6d62-110">Configuring the Conferencing Policy</span></span>

<span data-ttu-id="c6d62-111">「スクリプト会議ポリシー ps1」の例を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c6d62-111">See the example script MeetingPolicy.ps1.</span></span> <span data-ttu-id="c6d62-112">詳細については、「lync Server 2013 ドキュメント」および「 [Lync server 2013 の Web 会議コマンド](https://technet.microsoft.com/en-us/library/gg415675\(v=ocs.15\))レットのヘルプ」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c6d62-112">For details, see the Lync Server 2013 documentation and the cmdlet Help for [Web conferencing cmdlets in Lync Server 2013](https://technet.microsoft.com/en-us/library/gg415675\(v=ocs.15\)).</span></span>

</div>

<div>

## <a name="configuring-the-contacts-policy"></a><span data-ttu-id="c6d62-113">連絡先ポリシーを構成する</span><span class="sxs-lookup"><span data-stu-id="c6d62-113">Configuring the Contacts Policy</span></span>

<span data-ttu-id="c6d62-114">例 ContactsPolicy を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c6d62-114">See the example ContactsPolicy.ps1.</span></span> <span data-ttu-id="c6d62-115">詳細については、「lync Server 2013 ドキュメント」および「 [Lync server 2013 の IM とプレゼンスのコマンド](https://technet.microsoft.com/en-us/library/gg398611\(v=ocs.15\))レットのヘルプ」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c6d62-115">For details, see the Lync Server 2013 documentation and the cmdlet Help for [IM and presence cmdlets in Lync Server 2013](https://technet.microsoft.com/en-us/library/gg398611\(v=ocs.15\)).</span></span>

</div>

<div>

## <a name="configuring-the-federation-policy"></a><span data-ttu-id="c6d62-116">フェデレーションポリシーを構成する</span><span class="sxs-lookup"><span data-stu-id="c6d62-116">Configuring the Federation Policy</span></span>

<span data-ttu-id="c6d62-117">例 FederationPolicy を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c6d62-117">See the example FederationPolicy.ps1.</span></span> <span data-ttu-id="c6d62-118">詳細については、「lync server 2013 ドキュメント」および「lync server 2013 での microsoft Lync Server 2013 および[フェデレーションと外部アクセスコマンド](https://technet.microsoft.com/en-us/library/gg415651\(v=ocs.15\))レットの[Edge server コマンド](https://technet.microsoft.com/en-us/library/gg415635\(v=ocs.15\))レットのヘルプ」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c6d62-118">For details, see the Lync Server 2013 documentation and the cmdlet Help for [Edge Server cmdlets in Lync Server 2013](https://technet.microsoft.com/en-us/library/gg415635\(v=ocs.15\)) and [Federation and external access cmdlets in Lync Server 2013](https://technet.microsoft.com/en-us/library/gg415651\(v=ocs.15\)).</span></span>

</div>

<div>

## <a name="configuring-the-call-admission-control-policy"></a><span data-ttu-id="c6d62-119">通話受付制御ポリシーを構成する</span><span class="sxs-lookup"><span data-stu-id="c6d62-119">Configuring the Call Admission Control Policy</span></span>

<span data-ttu-id="c6d62-120">例 BandwidthPolicy を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c6d62-120">See the example BandwidthPolicy.ps1.</span></span> <span data-ttu-id="c6d62-121">詳細については、lync server 2013 の「[通話受付制御](https://technet.microsoft.com/en-us/library/gg398529\(v=ocs.15\))」と「lync server [2013 での通話受付制御コマンド](https://technet.microsoft.com/en-us/library/gg415676\(v=ocs.15\))レットのヘルプ」を参照し2013てください。</span><span class="sxs-lookup"><span data-stu-id="c6d62-121">For details, see the Lync Server 2013 documentation [Overview of call admission control in Lync Server 2013](https://technet.microsoft.com/en-us/library/gg398529\(v=ocs.15\)) and the cmdlet Help for [Call admission control cmdlets in Lync Server 2013](https://technet.microsoft.com/en-us/library/gg415676\(v=ocs.15\)).</span></span>

</div>

<div>

## <a name="configuring-the-voice-routing-rules"></a><span data-ttu-id="c6d62-122">ボイスルーティングルールを構成する</span><span class="sxs-lookup"><span data-stu-id="c6d62-122">Configuring the Voice Routing Rules</span></span>

<span data-ttu-id="c6d62-123">例 RoutingRules を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c6d62-123">See the example RoutingRules.ps1.</span></span> <span data-ttu-id="c6d62-124">ボイスルーティングルールを構成するときは、電話のコンテキスト (¥ Location Profile または/simplename) と内部/外部の市外局番をメモして、ユーザーの作成時と LyncPerfTool の構成時に指定できるようにします (特にPSTN-UC および UC-PSTN)。</span><span class="sxs-lookup"><span data-stu-id="c6d62-124">When you configure the voice routing rules, take note of the Phone Context (that is, /Location Profile or /SimpleName) and Internal/External Area Codes so that you can specify them when creating users and during LyncPerfTool configuration (specifically for PSTN-UC and UC-PSTN).</span></span> <span data-ttu-id="c6d62-125">たとえば、RoutingRules の例の**CsDialPlan**コマンドレットの呼び出しの simplename パラメーターは、UserProfileGenerator の次の図の locationprofile 値に使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c6d62-125">For example, the SimpleName parameter in the call to the **New-CsDialPlan** cmdlet in the RoutingRules.ps1 example should be used for the LocationProfile value in the following figure of UserProfileGenerator.exe.</span></span>

<span data-ttu-id="c6d62-126">![ボイスルーティングルールの例。](images/JJ945610.9f34d971-4ed0-4a4c-b101-086a91c4578c(OCS.15).jpg "ボイスルーティングルールの例。")</span><span class="sxs-lookup"><span data-stu-id="c6d62-126">![Sample voice routing rule.](images/JJ945610.9f34d971-4ed0-4a4c-b101-086a91c4578c(OCS.15).jpg "Sample voice routing rule.")</span></span>

<span data-ttu-id="c6d62-127">詳細については、「lync Server 2013 ドキュメント」および「 [Lync server 2013 のエンタープライズボイスコマンド](https://technet.microsoft.com/en-us/library/gg415658\(v=ocs.15\))レットのヘルプ」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c6d62-127">For details, see the Lync Server 2013 documentation and the cmdlet Help for [Enterprise Voice cmdlets in Lync Server 2013](https://technet.microsoft.com/en-us/library/gg415658\(v=ocs.15\)).</span></span>

</div>

<div>

## <a name="configuring-conferencing-attendant-application"></a><span data-ttu-id="c6d62-128">会議アテンダントアプリケーションの構成</span><span class="sxs-lookup"><span data-stu-id="c6d62-128">Configuring Conferencing Attendant application</span></span>

<span data-ttu-id="c6d62-129">例 ConferenceAutoAttendantConfiguration を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c6d62-129">See the example ConferenceAutoAttendantConfiguration.ps1.</span></span> <span data-ttu-id="c6d62-130">ConferencingAutoAttendant 電話番号 (既定では 1121111111) をメモし、それを構成の生成用の LyncPerf ツール構成ツールに入力できるようにします。</span><span class="sxs-lookup"><span data-stu-id="c6d62-130">Take note of the ConferencingAutoAttendant phone number (1121111111, by default), so that you can type it into the LyncPerf Tool Configuration tool for configuration generation.</span></span>

<span data-ttu-id="c6d62-131">![会議アテンダントアプリケーションの構成](images/JJ945610.0618a22f-27a9-423a-9085-d2bf71e82db6(OCS.15).jpg "会議アテンダントアプリケーションの構成")</span><span class="sxs-lookup"><span data-stu-id="c6d62-131">![Configuring the Conferencing Attendant application](images/JJ945610.0618a22f-27a9-423a-9085-d2bf71e82db6(OCS.15).jpg "Configuring the Conferencing Attendant application")</span></span>

<span data-ttu-id="c6d62-132">詳細については、「lync server 2013 ドキュメント」および「lync server 2013 での[Web 会議コマンド](https://technet.microsoft.com/en-us/library/gg415675\(v=ocs.15\))レットのヘルプ (lync server 2013 および[ダイヤルイン会議コマンド](https://technet.microsoft.com/en-us/library/gg415630\(v=ocs.15\))レットのヘルプ)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c6d62-132">For details, see the Lync Server 2013 documentation and the cmdlet Help for [Web conferencing cmdlets in Lync Server 2013](https://technet.microsoft.com/en-us/library/gg415675\(v=ocs.15\)) and [Dial-in conferencing cmdlets in Lync Server 2013](https://technet.microsoft.com/en-us/library/gg415630\(v=ocs.15\)).</span></span>

</div>

<div>

## <a name="configuring-lync-server-call-park-service"></a><span data-ttu-id="c6d62-133">Lync Server コールパークサービスの構成</span><span class="sxs-lookup"><span data-stu-id="c6d62-133">Configuring Lync Server Call Park Service</span></span>

<span data-ttu-id="c6d62-134">コールパークは既定では無効になっています。</span><span class="sxs-lookup"><span data-stu-id="c6d62-134">Call Park is disabled by default.</span></span> <span data-ttu-id="c6d62-135">「CallParkConfiguration」の例を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c6d62-135">See the example CallParkConfiguration.ps1.</span></span> <span data-ttu-id="c6d62-136">詳細については、「lync Server 2013 ドキュメント」および「 [Lync server 2013 のコールパークアプリケーションコマンドレット](https://technet.microsoft.com/en-us/library/gg415639\(v=ocs.15\))のヘルプ」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c6d62-136">For details, see the Lync Server 2013 documentation and the cmdlet Help for [Call Park application cmdlets in Lync Server 2013](https://technet.microsoft.com/en-us/library/gg415639\(v=ocs.15\)).</span></span>

</div>

<div>

## <a name="configuring-emergency-calls"></a><span data-ttu-id="c6d62-137">緊急通話の設定</span><span class="sxs-lookup"><span data-stu-id="c6d62-137">Configuring Emergency Calls</span></span>

<span data-ttu-id="c6d62-138">緊急通話のストレスとパフォーマンスのテストを構成するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="c6d62-138">Perform the following steps to configure stress and performance testing for emergency calls.</span></span>

1.  <span data-ttu-id="c6d62-139">緊急通話のためのボイスルートを設定します。</span><span class="sxs-lookup"><span data-stu-id="c6d62-139">Set up a voice route for emergency calls.</span></span> <span data-ttu-id="c6d62-140">このボイスルートを設定する例については、「コメント "E911 にルーティングする RoutingRules」の説明を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c6d62-140">See the RoutingRules.ps1 script under the comment "Route E911 to PSTN" for an example of setting up this voice route.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="c6d62-141">RoutingRules の例のコマンドには、911ではなく数値119を含む数値パターンが含まれています。</span><span class="sxs-lookup"><span data-stu-id="c6d62-141">The example command in RoutingRules.ps1 has a number pattern that includes the number 119 rather than 911.</span></span> <span data-ttu-id="c6d62-142">ロードテスト中に、ローカルの緊急電話会社に誤って通話を発信しないようにするには、911 (または実際のローカル緊急電話番号) の使用を避ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="c6d62-142">You should avoid using 911 (or your actual local emergency number) to prevent accidental calls to your local emergency operators during load testing.</span></span> <span data-ttu-id="c6d62-143">この構成は、シミュレーション目的でのみ使用されます。</span><span class="sxs-lookup"><span data-stu-id="c6d62-143">This configuration is for simulation purposes only.</span></span>

    
    </div>

2.  <span data-ttu-id="c6d62-144">次の図に示すように、Userプロビジョニングツールの [ **LIS** ] タブの値を入力して、アドレスを構成します。</span><span class="sxs-lookup"><span data-stu-id="c6d62-144">Configure addresses by filling in the values on the **LIS** tab in the UserProvisioningTool, as shown in the following figure.</span></span>
    
    <span data-ttu-id="c6d62-145">![位置情報サービスを構成します。](images/JJ945610.8ac1faa1-e9f9-40d0-b8b7-b159f4f459f7(OCS.15).jpg "位置情報サービスを構成します。")</span><span class="sxs-lookup"><span data-stu-id="c6d62-145">![Configuring the Location Information Service.](images/JJ945610.8ac1faa1-e9f9-40d0-b8b7-b159f4f459f7(OCS.15).jpg "Configuring the Location Information Service.")</span></span>  

3.  <span data-ttu-id="c6d62-146">[ **LIS 構成ファイルの生成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c6d62-146">Click **Generate LIS Config Files**.</span></span>

4.  <span data-ttu-id="c6d62-147">ポート、サブネット、スイッチ、ワイヤレスアクセスポイント (Wap) の CSV ファイル、および Lync Server 2013 ストレスおよびパフォーマンスツール用の XML ファイルが生成されます。</span><span class="sxs-lookup"><span data-stu-id="c6d62-147">CSV files for ports, subnets, switches, and wireless access points (WAPs), and an XML file for the Lync Server 2013 Stress and Performance Tool, are generated.</span></span> <span data-ttu-id="c6d62-148">CSV ファイルは、LisConfiguration スクリプトを使用して位置情報サービス (LIS) を構成するときに、同じフォルダー内で入力として使用されます。</span><span class="sxs-lookup"><span data-stu-id="c6d62-148">The CSV files are to be used as inputs (in the same folder) when configuring Location Information service (LIS) with the LisConfiguration.ps1 script.</span></span> <span data-ttu-id="c6d62-149">生成された Locations0 ファイルを、Lync Server 2013 のストレスとパフォーマンスツールの実行可能ファイル (LyncPerfTool) と同じフォルダーに移動します。これにより、位置情報プロファイル (ダイヤルプラン) のシナリオが実行されます。</span><span class="sxs-lookup"><span data-stu-id="c6d62-149">Move the generated Locations0.xml file to the same folder as the Lync Server 2013 Stress and Performance Tool executable (LyncPerfTool.exe), which will run location profile (dial plan) scenarios.</span></span>

</div>

<div>

## <a name="creating-enabling-configuring-and-disabling-users"></a><span data-ttu-id="c6d62-150">ユーザーの作成、有効化、構成、無効化</span><span class="sxs-lookup"><span data-stu-id="c6d62-150">Creating, Enabling, Configuring and Disabling Users</span></span>

<span data-ttu-id="c6d62-151">次のスクリプトを実行する前に、すべてのユーザーを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c6d62-151">You should create all your users before running the following scripts.</span></span> <span data-ttu-id="c6d62-152">「ユーザー[と連絡先を作成して](create-users-and-contacts.md)ユーザーを作成する」の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="c6d62-152">Follow the instructions in [Create Users and Contacts](create-users-and-contacts.md) to create users.</span></span> <span data-ttu-id="c6d62-153">詳細については、「[ユーザー](https://technet.microsoft.com/en-us/library/gg398125\(v=ocs.15\))用の Lync Server 2013 コマンドレット」を参照してください。また[](https://technet.microsoft.com/en-us/library/gg398747\(v=ocs.15\)) 、「ユーザーの[設定](https://technet.microsoft.com/en-us/library/gg398510\(v=ocs.15\))」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c6d62-153">For details, see the Lync Server 2013 cmdlet documentation for the [Get-CsUser](https://technet.microsoft.com/en-us/library/gg398125\(v=ocs.15\)), [Set-CsUser](https://technet.microsoft.com/en-us/library/gg398510\(v=ocs.15\)), and [Disable-CsUser](https://technet.microsoft.com/en-us/library/gg398747\(v=ocs.15\)) cmdlets.</span></span>

</div>

<div>

## <a name="configuring-response-group-application"></a><span data-ttu-id="c6d62-154">応答グループアプリケーションを構成する</span><span class="sxs-lookup"><span data-stu-id="c6d62-154">Configuring Response Group application</span></span>

<span data-ttu-id="c6d62-155">ResponseGroupConfiguration ps1 の例を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c6d62-155">See the example ResponseGroupConfiguration.ps1.</span></span> <span data-ttu-id="c6d62-156">詳細については、「Lync Server 2013 ドキュメント」および「 [lync server 2013 のグループアプリケーションコマンドレットに応答](https://technet.microsoft.com/en-us/library/gg415654\(v=ocs.15\))するためのコマンドレットのヘルプ」を参照してください。応答グループのアプリケーション構成を確認するに`https://<poolfqdn>/RgsConfig/`は、次の図のように「」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c6d62-156">For details, see the Lync Server 2013 documentation and the cmdlet Help for [Response Group application cmdlets in Lync Server 2013](https://technet.microsoft.com/en-us/library/gg415654\(v=ocs.15\)).To review the Response Group application configuration, see `https://<poolfqdn>/RgsConfig/`, as shown in the following figure.</span></span>

<span data-ttu-id="c6d62-157">![応答グループ構成ツール。](images/JJ945610.480a9440-2283-4533-98f8-86daaab4781c(OCS.15).jpg "応答グループ構成ツール。")</span><span class="sxs-lookup"><span data-stu-id="c6d62-157">![The Response Group Configuration Tool.](images/JJ945610.480a9440-2283-4533-98f8-86daaab4781c(OCS.15).jpg "The Response Group Configuration Tool.")</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

