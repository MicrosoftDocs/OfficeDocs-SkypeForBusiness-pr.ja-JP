---
title: ビジネス サーバー 2015 のストレスおよびパフォーマンス ツールは、Skype のポリシーを構成します。
ms.reviewer: ''
ms.author: heidip
author: microsoftheidi
ms.date: 11/11/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 7e1435e2-d073-4265-8067-ebcb5bf28835
description: ポリシーの構成の Skype ビジネス サーバー 2015 のストレスおよびパフォーマンス ツールです。
ms.openlocfilehash: c5dd20df0cac3121169f6eb5659eb6339d7875e2
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30881208"
---
# <a name="configuring-policies-for-the-skype-for-business-server-2015-stress-and-performance-tool"></a><span data-ttu-id="f9674-103">ビジネス サーバー 2015 のストレスおよびパフォーマンス ツールは、Skype のポリシーを構成します。</span><span class="sxs-lookup"><span data-stu-id="f9674-103">Configuring policies for the Skype for Business Server 2015 Stress and Performance Tool</span></span>
 
<span data-ttu-id="f9674-104">ポリシーの構成の Skype ビジネス サーバー 2015 のストレスおよびパフォーマンス ツールです。</span><span class="sxs-lookup"><span data-stu-id="f9674-104">Policy configuration for Skype for Business Server 2015 Stress and Performance Tool.</span></span>
  
<span data-ttu-id="f9674-105">ビジネス サーバー 2015、ストレスおよびパフォーマンス ツールを実行する前に Skype で構成できるようにしていくつかのポリシーがあります。</span><span class="sxs-lookup"><span data-stu-id="f9674-105">There are several policies and other areas that you can configure in Skype for Business Server 2015, prior to running the Stress and Performance Tool:</span></span>
  
- [<span data-ttu-id="f9674-106">アーカイブ ・ ポリシー</span><span class="sxs-lookup"><span data-stu-id="f9674-106">Archiving policy</span></span>](configuring-policies.md#ArchivingPolicy)
    
- [<span data-ttu-id="f9674-107">会議ポリシー</span><span class="sxs-lookup"><span data-stu-id="f9674-107">Conferencing policy</span></span>](configuring-policies.md#ConferencingPolicy)
    
- [<span data-ttu-id="f9674-108">連絡先のポリシー</span><span class="sxs-lookup"><span data-stu-id="f9674-108">Contacts policy</span></span>](configuring-policies.md#ContactsPolicy)
    
- [<span data-ttu-id="f9674-109">フェデレーションのポリシー</span><span class="sxs-lookup"><span data-stu-id="f9674-109">Federation policy</span></span>](configuring-policies.md#FederationPolicy)
    
- [<span data-ttu-id="f9674-110">受付制御ポリシーします。</span><span class="sxs-lookup"><span data-stu-id="f9674-110">Call Admission Control policy</span></span>](configuring-policies.md#CACPolicy)
    
- [<span data-ttu-id="f9674-111">音声ルーティングのルール</span><span class="sxs-lookup"><span data-stu-id="f9674-111">Voice Routing rules</span></span>](configuring-policies.md#VoiceRoutingRules)
    
- [<span data-ttu-id="f9674-112">会議アテンダント アプリケーション</span><span class="sxs-lookup"><span data-stu-id="f9674-112">Conference Attendant application</span></span>](configuring-policies.md#ConfAttendantApp)
    
- [<span data-ttu-id="f9674-113">サーバー コール パーク サービス</span><span class="sxs-lookup"><span data-stu-id="f9674-113">Server Call Park service</span></span>](configuring-policies.md#ServerCallParkServ)
    
- [<span data-ttu-id="f9674-114">緊急電話番号</span><span class="sxs-lookup"><span data-stu-id="f9674-114">Emergency calls</span></span>](configuring-policies.md#EmergencyCalls)
    
- [<span data-ttu-id="f9674-115">応答グループの構成の適用</span><span class="sxs-lookup"><span data-stu-id="f9674-115">Configuring Response Group application</span></span>](configuring-policies.md#ConfigResponseGroupApp)
    
## <a name="archiving-policy"></a><span data-ttu-id="f9674-116">アーカイブ ・ ポリシー</span><span class="sxs-lookup"><span data-stu-id="f9674-116">Archiving policy</span></span>
<span data-ttu-id="f9674-117"><a name="ArchivingPolicy"> </a></span><span class="sxs-lookup"><span data-stu-id="f9674-117"></span></span>

<span data-ttu-id="f9674-118">ビジネス サーバー トポロジの場合、Skype で展開されたアーカイブ サーバーがあれば、ArchivingPolicy.ps1 スクリプトを検索できます。</span><span class="sxs-lookup"><span data-stu-id="f9674-118">If you have an Archiving server deployed in your Skype for Business Server topology, you can look at the ArchivingPolicy.ps1 script.</span></span> <span data-ttu-id="f9674-119">サポートが必要なさらに、アーカイブ、Web 会議のコマンドレットをチェック アウトします。</span><span class="sxs-lookup"><span data-stu-id="f9674-119">If you need further assistance, check out the Archiving and Web Conferencing cmdlets.</span></span>
  
## <a name="conferencing-policy"></a><span data-ttu-id="f9674-120">会議ポリシー</span><span class="sxs-lookup"><span data-stu-id="f9674-120">Conferencing policy</span></span>
<span data-ttu-id="f9674-121"><a name="ConferencingPolicy"> </a></span><span class="sxs-lookup"><span data-stu-id="f9674-121"></span></span>

<span data-ttu-id="f9674-122">会議で、MeetingPolicy.ps1 スクリプトがあります。</span><span class="sxs-lookup"><span data-stu-id="f9674-122">For conferencing, we have the MeetingPolicy.ps1 script.</span></span> <span data-ttu-id="f9674-123">サポートが必要なさらに、Web 会議のコマンドレットをチェック アウトします。</span><span class="sxs-lookup"><span data-stu-id="f9674-123">If you need further assistance, check out the Web Conferencing cmdlets.</span></span>
  
## <a name="contacts-policy"></a><span data-ttu-id="f9674-124">連絡先のポリシー</span><span class="sxs-lookup"><span data-stu-id="f9674-124">Contacts policy</span></span>
<span data-ttu-id="f9674-125"><a name="ContactsPolicy"> </a></span><span class="sxs-lookup"><span data-stu-id="f9674-125"></span></span>

<span data-ttu-id="f9674-126">ContactsPolicy.ps1 スクリプトを確認する必要がありますサンプルとなります。</span><span class="sxs-lookup"><span data-stu-id="f9674-126">ContactsPolicy.ps1 script will be the sample you'll need to review.</span></span> <span data-ttu-id="f9674-127">IM とプレゼンスのコマンドレットは、さらに参照が必要な場合に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="f9674-127">The IM and Presence cmdlets will help if you need further references.</span></span>
  
## <a name="federation-policy"></a><span data-ttu-id="f9674-128">フェデレーションのポリシー</span><span class="sxs-lookup"><span data-stu-id="f9674-128">Federation policy</span></span>
<span data-ttu-id="f9674-129"><a name="FederationPolicy"> </a></span><span class="sxs-lookup"><span data-stu-id="f9674-129"></span></span>

<span data-ttu-id="f9674-130">フェデレーションで使用するサンプル スクリプトは、FederationPolicy.ps1 です。</span><span class="sxs-lookup"><span data-stu-id="f9674-130">The sample script for federation is FederationPolicy.ps1.</span></span> <span data-ttu-id="f9674-131">コマンドレットを確認して、さらに深めが必要な場合は、エッジ サーバー、フェデレーション、および外部からのアクセスになります。</span><span class="sxs-lookup"><span data-stu-id="f9674-131">The cmdlets to review, if you need further insight, will be Edge Server, federation, and external access.</span></span>
  
## <a name="call-admission-control-policy"></a><span data-ttu-id="f9674-132">受付制御ポリシーします。</span><span class="sxs-lookup"><span data-stu-id="f9674-132">Call Admission Control policy</span></span>
<span data-ttu-id="f9674-133"><a name="CACPolicy"> </a></span><span class="sxs-lookup"><span data-stu-id="f9674-133"></span></span>

<span data-ttu-id="f9674-134">このポリシーの BandwidthPolicy.ps1 を参照することができます。</span><span class="sxs-lookup"><span data-stu-id="f9674-134">You can reference BandwidthPolicy.ps1 for this policy.</span></span> <span data-ttu-id="f9674-135">呼の受付制御コマンドレットは、さらに同様の情報を必要があります。</span><span class="sxs-lookup"><span data-stu-id="f9674-135">The Call Admission Control cmdlets will have further information as well.</span></span>
  
## <a name="voice-routing-rules"></a><span data-ttu-id="f9674-136">音声ルーティングのルール</span><span class="sxs-lookup"><span data-stu-id="f9674-136">Voice Routing rules</span></span>
<span data-ttu-id="f9674-137"><a name="VoiceRoutingRules"> </a></span><span class="sxs-lookup"><span data-stu-id="f9674-137"></span></span>

<span data-ttu-id="f9674-138">RoutingRules.ps1 のサンプル スクリプトは、音声ルーティングの必要があります。</span><span class="sxs-lookup"><span data-stu-id="f9674-138">You'll need the RoutingRules.ps1 sample script for Voice Routing.</span></span> <span data-ttu-id="f9674-139">これらの規則を構成しているときに注意の内部および外部の市外局番と電話のコンテキストは、/Location のプロファイル (/SimpleName) ユーザーを作成するときに指定することができます。</span><span class="sxs-lookup"><span data-stu-id="f9674-139">When you're configuring these rules, take note of the phone context (that is, /Location Profile or /SimpleName) and Internal/External Area Codes, so that you can specify them when creating users.</span></span> <span data-ttu-id="f9674-140">(具体的には、PSTN UC UC PSTN) の LyncPerfTool の構成時にも必要だぞ。</span><span class="sxs-lookup"><span data-stu-id="f9674-140">You'll also need them during LyncPerfTool configuration (specifically for PSTN-UC and UC-PSTN).</span></span>
  
<span data-ttu-id="f9674-141">たとえば、次の図の UserProfileGenerator.exe の LocationProfile 値の RoutingRules.ps1 の例では**新規 CsDialPlan**コマンドレットへの呼び出し内のパラメーターに SimpleName を使用してください。</span><span class="sxs-lookup"><span data-stu-id="f9674-141">For example, the SimpleName parameter in the call to the **New-CsDialPlan** cmdlet in the RoutingRules.ps1 example should be used for the LocationProfile value in the following figure of UserProfileGenerator.exe:</span></span>
  
![Skype for Business Load Configuration Tool、[Voice Scenarios] タブ、会話の詳細設定](../../media/59f42e4e-8f1e-4d43-9ae2-9e6026191951.png)
  
<span data-ttu-id="f9674-143">詳細については、エンタープライズ VoIP のコマンドレットを確認することができます。</span><span class="sxs-lookup"><span data-stu-id="f9674-143">For details, you can review the Enterprise Voice cmdlets.</span></span>
  
## <a name="conference-attendant-application"></a><span data-ttu-id="f9674-144">会議アテンダント アプリケーション</span><span class="sxs-lookup"><span data-stu-id="f9674-144">Conference Attendant application</span></span>
<span data-ttu-id="f9674-145"><a name="ConfAttendantApp"> </a></span><span class="sxs-lookup"><span data-stu-id="f9674-145"></span></span>

<span data-ttu-id="f9674-146">ConferenceAutoAttendantConfiguration.ps1 スクリプトを最初に確認します。</span><span class="sxs-lookup"><span data-stu-id="f9674-146">First review the ConferenceAutoAttendantConfiguration.ps1 script.</span></span> <span data-ttu-id="f9674-147">注意 ConferencingAutoAttendant の電話番号 (既定では、1121111111) を次に示すようなコンフィギュレーションの生成の LyncPerfTool の構成ツールに入力できるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="f9674-147">You'll want to take note of the ConferencingAutoAttendant phone number (1121111111 by default), so that you can enter it into the LyncPerfTool configuration tool for configuration generation, as below:</span></span>
  
![電話会議負荷レベルと電話番号を表示している [Voice Scenarios] タブ](../../media/a3ea5fc0-8b3d-4842-b809-f137f470dbdc.png)
  
<span data-ttu-id="f9674-149">会議とダイヤルイン会議の詳細がわかりますコマンドレットです。</span><span class="sxs-lookup"><span data-stu-id="f9674-149">You'll find more details in the Conferencing and Dial-in Conferencing cmdlets.</span></span>
  
## <a name="server-call-park-service"></a><span data-ttu-id="f9674-150">サーバー コール パーク サービス</span><span class="sxs-lookup"><span data-stu-id="f9674-150">Server Call Park service</span></span>
<span data-ttu-id="f9674-151"><a name="ServerCallParkServ"> </a></span><span class="sxs-lookup"><span data-stu-id="f9674-151"></span></span>

<span data-ttu-id="f9674-152">これは実際には既定で無効です。</span><span class="sxs-lookup"><span data-stu-id="f9674-152">This is actually disabled by default.</span></span> <span data-ttu-id="f9674-153">これをテストする必要がある場合は、CallParkConfiguration.ps1 のサンプル スクリプトを確認できます。</span><span class="sxs-lookup"><span data-stu-id="f9674-153">You can review the CallParkConfiguration.ps1 sample script if you need to test this.</span></span> <span data-ttu-id="f9674-154">必要に応じて、さらに、コール パーク アプリケーションのコマンドレットをチェックします。</span><span class="sxs-lookup"><span data-stu-id="f9674-154">Additionally, check out the Call Park Application cmdlets as needed.</span></span>
  
## <a name="emergency-calls"></a><span data-ttu-id="f9674-155">緊急電話番号</span><span class="sxs-lookup"><span data-stu-id="f9674-155">Emergency calls</span></span>
<span data-ttu-id="f9674-156"><a name="EmergencyCalls"> </a></span><span class="sxs-lookup"><span data-stu-id="f9674-156"></span></span>

<span data-ttu-id="f9674-157">ストレスおよびパフォーマンスの緊急電話のテストを構成するのには次の手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f9674-157">You'll need to perform the following steps to configure stress and performance testing for emergency calls:</span></span>
  
1. <span data-ttu-id="f9674-158">緊急通報用のボイス ルートを設定します。</span><span class="sxs-lookup"><span data-stu-id="f9674-158">Set up a voice route for emergency calls.</span></span> <span data-ttu-id="f9674-159">RoutingRules.ps1 のスクリプトを使用し、このボイス ルートを設定する方法の例については「 **PSTN にルーティング E911** 」というコメント下を確認できます。</span><span class="sxs-lookup"><span data-stu-id="f9674-159">You can use the RoutingRules.ps1 script, and check under the comment " **Route E911 to PSTN** " for an example of how to set up this voice route.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="f9674-160">RoutingRules.ps1 のコマンドの例には、911 ではなく、119 の番号を含む番号のパターンがあります。</span><span class="sxs-lookup"><span data-stu-id="f9674-160">The example command in RoutingRules.ps1 has a number pattern that includes the number 119 rather than 911.</span></span> <span data-ttu-id="f9674-161">ロード テスト中に、ローカルの緊急時のオペレーターへの偶発的な呼び出しを防ぐために 911 (または、実際のローカルの緊急電話番号) を使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="f9674-161">You should avoid using 911 (or your actual local emergency number) to prevent accidental calls to your local emergency operators during your load testing.</span></span> <span data-ttu-id="f9674-162">シミュレーションのためだけには、この構成に注意してください!</span><span class="sxs-lookup"><span data-stu-id="f9674-162">Remember, this configuration is for simulation purposes only!</span></span> 
  
2. <span data-ttu-id="f9674-163">次の図に示すように、**場所情報サービスの構成**] タブで、UserProvisioningTool の値を入力してアドレスを構成します。</span><span class="sxs-lookup"><span data-stu-id="f9674-163">Configure addresses by filling in the values on the **Location Info Service Config** tab in the UserProvisioningTool, as shown in the following figure:</span></span>
    
     ![アドレス、サブネット、スイッチ、ポートの数を表示している User Provisioning Tool](../../media/ebe85a0c-750f-4301-97d4-d158a40ea98a.png)
  
3. <span data-ttu-id="f9674-165">入力したすべてのもの、UserProvisioningTool、 **LIS 構成ファイルの生成**] ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="f9674-165">When you've entered everything into the UserProvisioningTool, click the **Generate LIS Config Files** button.</span></span>
    
4. <span data-ttu-id="f9674-166">今すぐストレスおよびパフォーマンス ツールの XML ファイルと同様のポート、サブネット、スイッチ、およびワイヤレス アクセス ポイント (Wap)、CSV ファイルが生成されます。</span><span class="sxs-lookup"><span data-stu-id="f9674-166">Now CSV files for ports, subnets, switches, and wireless access points (WAPs), as well as an XML file for the Stress and Performance tool will be generated.</span></span> <span data-ttu-id="f9674-167">LisConfiguration.ps1 スクリプトを使用して位置情報サービス (LIS) を構成する場合は、入力値の CSV ファイルを使用できます。</span><span class="sxs-lookup"><span data-stu-id="f9674-167">You can use the CSV files for inputs when configuring the Location Information service (LIS) with the LisConfiguration.ps1 script.</span></span> <span data-ttu-id="f9674-168">これを行うには、ストレスおよびパフォーマンス ツールの実行ファイル (LyncPerfTool.exe) と同じフォルダーに Locations0.xml ファイルを移動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f9674-168">To do this, you'll need to move the Locations0.xml file to the same folder as the Stress and Performance Tool executable (LyncPerfTool.exe).</span></span> <span data-ttu-id="f9674-169">これは、オプションを選択する場所のプロファイル (ダイヤル プラン) のシナリオを実行することができます。</span><span class="sxs-lookup"><span data-stu-id="f9674-169">This will let you run location profile (dial plan) scenarios.</span></span>
    
## <a name="configuring-response-group-application"></a><span data-ttu-id="f9674-170">応答グループの構成の適用</span><span class="sxs-lookup"><span data-stu-id="f9674-170">Configuring Response Group application</span></span>
<span data-ttu-id="f9674-171"><a name="ConfigResponseGroupApp"> </a></span><span class="sxs-lookup"><span data-stu-id="f9674-171"></span></span>

<span data-ttu-id="f9674-172">サンプル スクリプトは、ResponseGroupConfiguration.ps1 です。</span><span class="sxs-lookup"><span data-stu-id="f9674-172">The sample script is ResponseGroupConfiguration.ps1.</span></span> <span data-ttu-id="f9674-173">構成の詳細を確認するのには応答グループ アプリケーションのコマンドレットが用意されています。</span><span class="sxs-lookup"><span data-stu-id="f9674-173">There are also Response Group application cmdlets to review for further configuration details.</span></span> <span data-ttu-id="f9674-174">次の図は、いくつかの構成の詳細に表示されます。</span><span class="sxs-lookup"><span data-stu-id="f9674-174">The following diagram will show some of the configuration details:</span></span>
  
![既存のテスト用ワークフローを表示している Response Group Configuration Tool](../../media/e218a345-4813-4332-8cff-b48de05017ef.jpg)
  

