---
title: Microsoft Teams のユーザー エクスペリエンスを計画する
author: rmw2890
ms.author: Rowille
manager: serdars
ms.date: 03/13/2018
ms.topic: conceptual
audience: admin
ms.service: msteams
search.appverid: MET150
ms.reviewer: rowille
description: クライアント Teamsを選択し、エンドポイントの品質を計画し、エンドポイントをデプロイし、オーディオ デバイスWi-Fi推奨事項を取得します。
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5d20d914ab6ceca1d264a23662c9c8a067798a82
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51094735"
---
# <a name="plan-my-users-experience"></a><span data-ttu-id="42fd6-103">ユーザーエクスペリエンスを計画する</span><span class="sxs-lookup"><span data-stu-id="42fd6-103">Plan my users’ experience</span></span>

<span data-ttu-id="42fd6-104">この記事では、ユーザーのエクスペリエンスに直接影響するクラウド 音声サービス デプロイの要素を適切に識別するための要件の概要を説明します。</span><span class="sxs-lookup"><span data-stu-id="42fd6-104">This article gives an overview of the requirements for properly identifying the elements of your cloud voice services deployment that directly affect your users’ experience.</span></span> <span data-ttu-id="42fd6-105">デプロイ前にこれらの項目を準備することで、ユーザーに高品質で信頼性の高いエクスペリエンスを正常に提供する可能性を高めるでしょう。</span><span class="sxs-lookup"><span data-stu-id="42fd6-105">By preparing for these items before deployment, you’ll increase your chances of successfully delivering a high-quality, reliable experience for users.</span></span> 

## <a name="client-deployment"></a><span data-ttu-id="42fd6-106">クライアントのデプロイ</span><span class="sxs-lookup"><span data-stu-id="42fd6-106">Client deployment</span></span>

<span data-ttu-id="42fd6-107">Microsoft Teams、Web、デスクトップ (Windows Mac)、モバイル (Android および iOS) で使用できるクライアントがあります。</span><span class="sxs-lookup"><span data-stu-id="42fd6-107">Microsoft Teams has clients available for web, desktop (Windows and Mac), and mobile (Android and iOS).</span></span> <span data-ttu-id="42fd6-108">デスクトップ (Windows および Mac) とモバイル クライアントのインストール方法の詳細については、「Get clients for Microsoft Teams 」[を参照してください](./get-clients.md)。</span><span class="sxs-lookup"><span data-stu-id="42fd6-108">For additional details about how the desktop (Windows and Mac) and mobile clients are installed, see [Get clients for Microsoft Teams](./get-clients.md).</span></span>

## <a name="client-updates"></a><span data-ttu-id="42fd6-109">クライアントの更新</span><span class="sxs-lookup"><span data-stu-id="42fd6-109">Client updates</span></span>

<span data-ttu-id="42fd6-110">この機能の主な利点Teams、クライアントは自動的に最新の状態に維持されます。</span><span class="sxs-lookup"><span data-stu-id="42fd6-110">One of the key benefits of Teams is that the client is kept up to date automatically.</span></span> <span data-ttu-id="42fd6-111">PC と Mac 上のクライアントは、アプリがアイドル状態のときに新しいビルドがあるかを確認したり、新しいクライアントをダウンロードしたりする、バックグラウンド プロセスを使用して更新されます。</span><span class="sxs-lookup"><span data-stu-id="42fd6-111">The clients on the PC and Mac are updated by using a background process that checks for new builds and downloads the new client when the app is idle.</span></span>

<!--ENDOFSECTION-->

## <a name="plan-for-endpoint-quality"></a><span data-ttu-id="42fd6-112">エンドポイント品質の計画</span><span class="sxs-lookup"><span data-stu-id="42fd6-112">Plan for endpoint quality</span></span>

<span data-ttu-id="42fd6-113">次の図に示す通り、エンドポイントは、ユーザーに高品質のエクスペリエンスを提供する上で重要なブロックです。</span><span class="sxs-lookup"><span data-stu-id="42fd6-113">As you can see from the diagram below, endpoints are an important building block in providing a quality experience for users.</span></span>

<span data-ttu-id="42fd6-114">![品質にかかわる 3 つの構成要素を取り上げた図](media/plan-my-users-experience-image1.png "品質の 3 つのコンポーネントと、サービス管理が 3 つのコンポーネントすべてとどのように重なるかについて説明する図。エンドポイントに重点を置く。")</span><span class="sxs-lookup"><span data-stu-id="42fd6-114">![Diagram describing the three components of quality](media/plan-my-users-experience-image1.png "Diagram describing the three components of quality, and how service management overlaps all three components. With a focus on endpoints.")</span></span>

<span data-ttu-id="42fd6-115">Teamsエンドポイントは、PC、Mac、タブレット、モバイル デバイスなど、多くのデバイスで実行できます。</span><span class="sxs-lookup"><span data-stu-id="42fd6-115">Teams endpoints can run on many devices, including PCs, Macs, tablets, and mobile devices.</span></span> <span data-ttu-id="42fd6-116">エクスペリエンスの一部には、デバイスだけでなく、ユーザーがデバイスに接続する方法 (たとえば、デバイスの組み込みのマイク/スピーカー、イヤーパッド、最適化されたヘッドセットを使用する方法) が含されます。</span><span class="sxs-lookup"><span data-stu-id="42fd6-116">Part of the experience not only encompasses the device, but how a user connects to the device—for example, using the device’s built-in mic/speaker, earbuds, or an optimized headset.</span></span> <span data-ttu-id="42fd6-117">最適化されたヘッドセットを使用すると、全体的なユーザー エクスペリエンスが向上します。</span><span class="sxs-lookup"><span data-stu-id="42fd6-117">Using an optimized headset can enrich the overall user experience.</span></span>

<span data-ttu-id="42fd6-118">エンドポイントの計画についての次のガイダンスは、自分の組織が正常に Teams を使い始められるようになるために役立つ情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="42fd6-118">The following guidance on endpoint planning will help you ensure your organization has a successful onboarding experience with Teams.</span></span>

## <a name="endpoint-capability"></a><span data-ttu-id="42fd6-119">エンドポイントの機能</span><span class="sxs-lookup"><span data-stu-id="42fd6-119">Endpoint capability</span></span>

<span data-ttu-id="42fd6-120">計画の最初の部分は、組織内のすべての PC と他のデバイスが、すべてのデバイスで実行Teams。</span><span class="sxs-lookup"><span data-stu-id="42fd6-120">The first part of planning is to ensure all the PCs and other devices in your organization can run Teams.</span></span> <span data-ttu-id="42fd6-121">これには、単にハードウェア要件を確認するだけではなく、PC がバックグラウンドで他に何を実行しているかを理解することも含まれます。</span><span class="sxs-lookup"><span data-stu-id="42fd6-121">This involves not just looking at the hardware requirements, but also understanding what else the PC is doing in the background.</span></span> <span data-ttu-id="42fd6-122">多くの組織は、侵入検出システムやマルウェア対策ソフトウェアなどの、デバイスの基本パフォーマンスに影響する可能性がある、他のソフトウェアを実行しています。</span><span class="sxs-lookup"><span data-stu-id="42fd6-122">Many organizations run other software, including intrusion detection systems and antimalware software, which can affect the base performance of a device.</span></span>

<span data-ttu-id="42fd6-123">各プラットフォーム (Web、デスクトップ、モバイル) 上の Teams クライアントのソフトウェア要件については、「Get [clients for Microsoft Teams](./get-clients.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="42fd6-123">For information about the software requirements for Teams clients on each platform (web, desktop, and mobile), see [Get clients for Microsoft Teams](./get-clients.md).</span></span>

## <a name="endpoint-firewalls"></a><span data-ttu-id="42fd6-124">エンドポイントのファイアウォール</span><span class="sxs-lookup"><span data-stu-id="42fd6-124">Endpoint firewalls</span></span>

<span data-ttu-id="42fd6-125">クライアント側のファイアウォールはユーザー エクスペリエンスに大きな影響をおよぼす可能性があります。</span><span class="sxs-lookup"><span data-stu-id="42fd6-125">Client-side firewalls can have a significant impact on the user experience.</span></span>
<span data-ttu-id="42fd6-126">クライアント側のファイアウォールは、通話が確立されないようにするだけではなく、通話品質に影響する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="42fd6-126">Client-side firewalls can affect call quality in addition to preventing a call from being established.</span></span> <span data-ttu-id="42fd6-127">クライアント ファイアウォールで適切な除外を構成します。クライアント ファイアウォールの URL と IP アドレスMicrosoft 365またはOffice 365[の情報に基づいて行います](/microsoft-365/enterprise/urls-and-ip-address-ranges)。</span><span class="sxs-lookup"><span data-stu-id="42fd6-127">Configure the appropriate exclusions on the client firewall based on the information in [Microsoft 365 or Office 365 URLs and IP address ranges](/microsoft-365/enterprise/urls-and-ip-address-ranges).</span></span> <span data-ttu-id="42fd6-128">ご利用のサードパーティ ベンダーには、例外の作成方法についての固有のガイダンスがあります。</span><span class="sxs-lookup"><span data-stu-id="42fd6-128">Your third-party vendor will have specific guidance on how to create the exclusions.</span></span>

>[!NOTE]
> <span data-ttu-id="42fd6-129">Microsoft Teams は、適切なファイアウォール構成で自動的に Windows ファイアウォールを更新します。</span><span class="sxs-lookup"><span data-stu-id="42fd6-129">Microsoft Teams will automatically update the Windows Firewall with an appropriate firewall configuration.</span></span>

## <a name="wi-fi-recommendations-for-endpoints"></a><span data-ttu-id="42fd6-130">エンドポイント向けの Wi-Fi の推奨事項</span><span class="sxs-lookup"><span data-stu-id="42fd6-130">Wi-Fi recommendations for endpoints</span></span>

<span data-ttu-id="42fd6-131">最適化されたネットワークをデプロイし、Wi-Fiのリアルタイム ワークロードをサポートするには、重要な計画がMicrosoft Teams。</span><span class="sxs-lookup"><span data-stu-id="42fd6-131">It takes significant planning to deploy an optimized Wi-Fi network to support real-time workloads in Microsoft Teams.</span></span> <span data-ttu-id="42fd6-132">次のセクションでは、エンドポイントを計画するときによくある落とし穴を回避するために役立つ一般的なガイダンスを示します。</span><span class="sxs-lookup"><span data-stu-id="42fd6-132">The following sections provide some general guidance that can help you avoid common pitfalls when planning for endpoints.</span></span>

### <a name="wi-fi-drivers"></a><span data-ttu-id="42fd6-133">Wi-Fi ドライバー</span><span class="sxs-lookup"><span data-stu-id="42fd6-133">Wi-Fi drivers</span></span>

<span data-ttu-id="42fd6-134">一部Wi-Fiドライバーが問題になる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="42fd6-134">Some Wi-Fi drivers can be problematic.</span></span> <span data-ttu-id="42fd6-135">たとえば、ドライバーによりアクセス ポイント間で非常に積極的なローミング動作が行われる場合があり、その結果として通話品質が下がります。</span><span class="sxs-lookup"><span data-stu-id="42fd6-135">As an example, a driver might have very aggressive roaming behaviors between access points, causing poor call quality.</span></span>
<span data-ttu-id="42fd6-136">これは一般的な問題ではありません。ただし、PC 上の Wi-Fi ドライバーが更新され、展開前にテスト済みである必要があります。</span><span class="sxs-lookup"><span data-stu-id="42fd6-136">This isn’t a common occurrence, but it’s important to ensure that Wi-Fi drivers on the PC have been updated and tested prior to deployment.</span></span>

### <a name="wi-fi-bands"></a><span data-ttu-id="42fd6-137">Wi-Fi バンド</span><span class="sxs-lookup"><span data-stu-id="42fd6-137">Wi-Fi bands</span></span>

<span data-ttu-id="42fd6-138">現在の Wi-Fi 機器では、2.4 GHz と 5.0 GHz という 2 つの主な種類のバンドが使用されています。</span><span class="sxs-lookup"><span data-stu-id="42fd6-138">There are primarily two types of bands used in Wi-Fi equipment today, 2.4 GHz and 5.0 GHz.</span></span> <span data-ttu-id="42fd6-139">自分の組織が両方のバンドを提供している場合、ドライバーの設定を、5.0 GHz バンドを優先するように構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="42fd6-139">If your organization provides both bands, you should configure your driver settings to prefer the 5.0 GHz band.</span></span> <span data-ttu-id="42fd6-140">このバンドでは、スループットの点で密度がより高く、2.4 GHz バンドで生じる干渉による影響がより少なくなります。</span><span class="sxs-lookup"><span data-stu-id="42fd6-140">This band is much denser in terms of throughput and is less affected by the interference seen in the 2.4 GHz band.</span></span>
<span data-ttu-id="42fd6-141">この推奨事項は、5.0 GHz のネットワーク バンドを正しく最適化したことを想定しています。</span><span class="sxs-lookup"><span data-stu-id="42fd6-141">This recommendation assumes that you’ve properly optimized the 5.0 GHz network band.</span></span>

### <a name="wi-fi-radio-type"></a><span data-ttu-id="42fd6-142">Wi-Fi 無線タイプ</span><span class="sxs-lookup"><span data-stu-id="42fd6-142">Wi-Fi radio type</span></span>

<span data-ttu-id="42fd6-143">新しい Wi-Fi 無線タイプをサポートするデバイス向けの計画です。</span><span class="sxs-lookup"><span data-stu-id="42fd6-143">Plan for devices that support the newer Wi-Fi radio types.</span></span> <span data-ttu-id="42fd6-144">プロビジョニングしたデバイス上で 802.11ac またはより新しいタイプを利用すると、優れた Wi-Fi パフォーマンスを得ることができます。</span><span class="sxs-lookup"><span data-stu-id="42fd6-144">You can get very good Wi-Fi performance if you leverage 802.11ac or newer on the devices you provision.</span></span>

### <a name="wireless-avoidance"></a><span data-ttu-id="42fd6-145">ワイヤレス回避</span><span class="sxs-lookup"><span data-stu-id="42fd6-145">Wireless avoidance</span></span>

<span data-ttu-id="42fd6-146">組織によっては、Wi-Fi を完全に回避することを希望します。</span><span class="sxs-lookup"><span data-stu-id="42fd6-146">Some organizations prefer to avoid Wi-Fi altogether.</span></span> <span data-ttu-id="42fd6-147">このガイダンスは、有線ネットワークに直接接続するユーザーに対する推奨事項として提供されることがあります。</span><span class="sxs-lookup"><span data-stu-id="42fd6-147">Sometimes this guidance is provided through a recommendation to users to connect directly to a wired network.</span></span> <span data-ttu-id="42fd6-148">場合によっては、PC が優先接続に接続されていても、ネットワークのバインド順でワイヤレス接続が優先されているため、その無線接続を継続して使用することがあります。</span><span class="sxs-lookup"><span data-stu-id="42fd6-148">In some cases, the network binding order might have the wireless connection preferred and continue to use that connection even though the PC is connected to the wired connection.</span></span> <span data-ttu-id="42fd6-149">このような意図しない動作を回避するには、このシナリオを回避するようにバインド順を構成します。</span><span class="sxs-lookup"><span data-stu-id="42fd6-149">To avoid this unintended behavior, configure the binding order to avoid this scenario.</span></span>

### <a name="80211-power-save-protocol"></a><span data-ttu-id="42fd6-150">802.11 Power Save プロトコル</span><span class="sxs-lookup"><span data-stu-id="42fd6-150">802.11 Power Save protocol</span></span>

<span data-ttu-id="42fd6-151">組織で 802.11 Power Save プロトコルをサポートしないワイヤレス アクセス ポイントまたはルーターを使用している場合は、Windows デバイスで実行されている Microsoft Teams で通話の低下や低品質が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="42fd6-151">If your organization uses wireless access points or routers that don’t support the 802.11 Power Save protocol, you might experience dropped calls or poor call quality in Microsoft Teams running on Windows devices.</span></span> <span data-ttu-id="42fd6-152">ワイヤレス アクセス ポイントまたはルーターをアップグレードすることができない場合は、バッテリで動作しているデバイスで Windows 電源プラン設定を更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="42fd6-152">If it’s not possible to upgrade your wireless access point or routers, you should update Windows Power Plan settings on devices that run on battery power.</span></span> <span data-ttu-id="42fd6-153">より詳細な情報と、構成についてのガイダンスは次の[サポート記事](https://support.microsoft.com/help/928152/you-may-experience-connectivity-issues-or-performance-issues-when-you)で提供されています。</span><span class="sxs-lookup"><span data-stu-id="42fd6-153">Further detail and configuration guidance is provided in the following [support article](https://support.microsoft.com/help/928152/you-may-experience-connectivity-issues-or-performance-issues-when-you).</span></span>

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/><span data-ttu-id="42fd6-154">判断ポイント</span><span class="sxs-lookup"><span data-stu-id="42fd6-154">Decision points</span></span></td><td><ul><li><span data-ttu-id="42fd6-155">組織Teamsどのクライアントをデプロイしますか。</span><span class="sxs-lookup"><span data-stu-id="42fd6-155">What Teams clients will be deployed in your organization?</span></span></li><li><span data-ttu-id="42fd6-156">ユーザーに対して最初にTeamsクライアントをデプロイする方法</span><span class="sxs-lookup"><span data-stu-id="42fd6-156">How will you initially deploy Teams clients to your users?</span></span></li><li><span data-ttu-id="42fd6-157">Whoエクスペリエンスの要件を満たしていることを検証するために、エンドポイントとデバイスTeams評価する責任がありますか。</span><span class="sxs-lookup"><span data-stu-id="42fd6-157">Who is responsible for evaluating endpoints and devices to validate they meet Teams requirements for a quality experience?</span></span></li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/><span data-ttu-id="42fd6-158">次の手順</span><span class="sxs-lookup"><span data-stu-id="42fd6-158">Next steps</span></span></td><td><ul><li><span data-ttu-id="42fd6-159">クライアントにデプロイするプロセスを文書化Teamsします。</span><span class="sxs-lookup"><span data-stu-id="42fd6-159">Document the process that will be followed to deploy Teams clients.</span></span></li><li><span data-ttu-id="42fd6-160">エンドポイントとデバイスを評価し、実行と修復が必要です。</span><span class="sxs-lookup"><span data-stu-id="42fd6-160">Evaluate endpoints and devices and perform and remediation required.</span></span></li></ul></td></tr>
</table>

<!--ENDOFSECTION-->

## <a name="devices-for-teams"></a><span data-ttu-id="42fd6-161">Teams 用のデバイス</span><span class="sxs-lookup"><span data-stu-id="42fd6-161">Devices for Teams</span></span>

<span data-ttu-id="42fd6-162">Microsoft Teams は会議のために、または電話システムとして使用することができます。</span><span class="sxs-lookup"><span data-stu-id="42fd6-162">Microsoft Teams can be used for meetings or as a phone system.</span></span> <span data-ttu-id="42fd6-163">これらの機能を使用するとき、Teams のために使用されるインターフェイス デバイスは、ユーザー エクスペリエンスにおいて重要な役割を果たします。</span><span class="sxs-lookup"><span data-stu-id="42fd6-163">When using these features, the interface device that is used for Teams plays an important role in the user experience.</span></span>

<span data-ttu-id="42fd6-164">内蔵の PC スピーカーとマイクを使用する構成で、ユーザーが許容できる音質が得られる場合があります。</span><span class="sxs-lookup"><span data-stu-id="42fd6-164">Using a built-in PC speaker and microphone might sound acceptable to the user who has that configuration.</span></span> <span data-ttu-id="42fd6-165">ただし、通常、これらのデバイスはノイズ 除去用に最適化されていないので、どの種類の環境ノイズでも、他のデバイスが呼び出しにダウンストリームに影響を与える可能性があります。</span><span class="sxs-lookup"><span data-stu-id="42fd6-165">But typically, those devices aren’t optimized for noise cancellation, and any type of ambient noise can have a downstream impact on others on the call.</span></span> <span data-ttu-id="42fd6-166">このようなシナリオに最適化されたデバイスを利用すると、高品質のエクスぺリエンスを確保することができるようになります。</span><span class="sxs-lookup"><span data-stu-id="42fd6-166">Leveraging devices optimized for these scenarios will help ensure a high-quality experience.</span></span>

<span data-ttu-id="42fd6-167">各デバイスが、自分のユーザーのニーズに合う必要があります。</span><span class="sxs-lookup"><span data-stu-id="42fd6-167">Each device needs to meet the needs of your users.</span></span> <span data-ttu-id="42fd6-168">ヘッドセットなどのデバイスを組織内のそれぞれの人やユース ケースに合わせて調整する必要があります。</span><span class="sxs-lookup"><span data-stu-id="42fd6-168">You’ll need to tailor devices such as headsets for the different personas and use cases in your organization.</span></span>
<span data-ttu-id="42fd6-169">人からデバイスへのマッピングの実施を、計画プロセスの一部として完了している必要があります。</span><span class="sxs-lookup"><span data-stu-id="42fd6-169">A persona-to-device mapping exercise should be completed as part of the planning process.</span></span>

<span data-ttu-id="42fd6-170">デバイスを選択したら、それらを最終検証のパイロット テスト計画に含めます。</span><span class="sxs-lookup"><span data-stu-id="42fd6-170">After you’ve selected the devices, include them in the pilot test plan for final validation.</span></span> <span data-ttu-id="42fd6-171">パイロット中にアンケートを活用して、デバイス戦略が適正であることを確認するために、フィードバックを収集します。</span><span class="sxs-lookup"><span data-stu-id="42fd6-171">Leverage surveys during the pilot to collect feedback to ensure your device strategy is optimal.</span></span>

> [!NOTE]
> <span data-ttu-id="42fd6-172">現時点では、Skype for Business の認証プログラムを通して認証されたオーディオ デバイスを使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="42fd6-172">At this time, we recommend using audio devices that were certified through the Skype for Business Certification program.</span></span> <span data-ttu-id="42fd6-173">このプログラムで認定されているデバイスを見つけるには、「Microsoft Teams [USB](https://products.office.com/microsoft-teams/across-devices/devices)オーディオ デバイスとビデオ デバイス」[を参照してください](/SkypeForBusiness/certification/devices-usb-devices)。</span><span class="sxs-lookup"><span data-stu-id="42fd6-173">To find devices certified under this program, see the [Microsoft Teams devices](https://products.office.com/microsoft-teams/across-devices/devices) and [USB audio and video devices](/SkypeForBusiness/certification/devices-usb-devices).</span></span>



<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/><span data-ttu-id="42fd6-174">判断ポイント</span><span class="sxs-lookup"><span data-stu-id="42fd6-174">Decision points</span></span></td><td><ul><li><span data-ttu-id="42fd6-175">ユーザーエクスペリエンスと会議室エクスペリエンスに関する組織の全体的なデバイス戦略を決定します。</span><span class="sxs-lookup"><span data-stu-id="42fd6-175">Decide on your organization’s overall device strategy for user and meeting room experiences.</span></span></li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/><span data-ttu-id="42fd6-176">次の手順</span><span class="sxs-lookup"><span data-stu-id="42fd6-176">Next steps</span></span></td><td><ul><li><span data-ttu-id="42fd6-177">組織のペルシャ対デバイス マッピングの演習を完了します。</span><span class="sxs-lookup"><span data-stu-id="42fd6-177">Complete a persona-to-device mapping exercise for your organization.</span></span></li><li><span data-ttu-id="42fd6-178">ユーザーと会議室のデバイスを取得するプロセスを文書化します。</span><span class="sxs-lookup"><span data-stu-id="42fd6-178">Document the process for obtaining devices for users and meeting rooms.</span></span></li><li><span data-ttu-id="42fd6-179">ユーザーと会議室のデバイスを展開および構成するプロセスを文書化します。</span><span class="sxs-lookup"><span data-stu-id="42fd6-179">Document the process for deploying and configuration devices for users and meeting rooms.</span></span></li><li><span data-ttu-id="42fd6-180">初期デバイスを調達してデプロイを開始します。</span><span class="sxs-lookup"><span data-stu-id="42fd6-180">Procure initial devices to begin your deployment.</span></span></li></ul></td></tr>
</table>

<!--ENDOFSECTION-->