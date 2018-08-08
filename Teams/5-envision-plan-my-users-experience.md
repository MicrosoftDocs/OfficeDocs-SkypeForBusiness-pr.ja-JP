---
title: マイクロソフトのチームのユーザーの経験を計画します。
author: rmw2890
ms.author: MyAdvisor
manager: serdars
ms.date: 03/13/2018
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
description: チームのクライアント アプリケーション、エンドポイントの品質管理の計画は、Wi-fi の端点を配置して、オーディオ デバイスを選択するための推奨事項を取得」を選択します。
localization_priority: Priority
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4e328f591ac97ace73b2cd2bb45aab61db75f064
ms.sourcegitcommit: d979aecf73da0ba493a0b3be1db4d8b997c6ce2d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/07/2018
ms.locfileid: "19695351"
---
# <a name="plan-my-users-experience"></a><span data-ttu-id="077bc-103">自分のユーザー エクスペリエンスを計画します。</span><span class="sxs-lookup"><span data-stu-id="077bc-103">Plan my users’ experience</span></span>

<span data-ttu-id="077bc-104">この資料では、正しく、ユーザーのエクスペリエンスに直接影響するクラウドの音声サービスの展開の要素を識別するための要件の概要を示します。</span><span class="sxs-lookup"><span data-stu-id="077bc-104">This article gives an overview of the requirements for properly identifying the elements of your cloud voice services deployment that directly affect your users’ experience.</span></span> <span data-ttu-id="077bc-105">展開する前にこれらのアイテムの準備ができたら、正常に高品質で信頼性の高いユーザー エクスペリエンスを提供する可能性が増加します。</span><span class="sxs-lookup"><span data-stu-id="077bc-105">By preparing for these items before deployment, you’ll increase your chances of successfully delivering a high-quality, reliable experience for users.</span></span> 

## <a name="client-deployment"></a><span data-ttu-id="077bc-106">クライアントの展開</span><span class="sxs-lookup"><span data-stu-id="077bc-106">Client deployment</span></span>

<span data-ttu-id="077bc-107">マイクロソフトのチームでは、使用可能なクライアントの web、デスクトップ (Windows および Mac) とモバイル (Android、iOS、および Windows Phone) があります。</span><span class="sxs-lookup"><span data-stu-id="077bc-107">Microsoft Teams has clients available for web, desktop (Windows and Mac), and mobile (Android, iOS, and Windows Phone).</span></span> <span data-ttu-id="077bc-108">(Windows および Mac) のデスクトップおよびモバイル クライアントをインストールする方法に関する詳細は、[マイクロソフトのチーム用のクライアントを取得する](https://docs.microsoft.com/microsoftteams/get-clients)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="077bc-108">For additional details about how the desktop (Windows and Mac) and mobile clients are installed, see [Get clients for Microsoft Teams](https://docs.microsoft.com/microsoftteams/get-clients).</span></span>

## <a name="client-updates"></a><span data-ttu-id="077bc-109">クライアント用更新プログラム</span><span class="sxs-lookup"><span data-stu-id="077bc-109">Client updates</span></span>

<span data-ttu-id="077bc-110">チームの主な利点の 1 つは、クライアントに格納されている最新の状態に自動的にします。</span><span class="sxs-lookup"><span data-stu-id="077bc-110">One of the key benefits of Teams is that the client is kept up to date automatically.</span></span> <span data-ttu-id="077bc-111">PC と Mac 上のクライアントは、新しいビルドをチェックし、アプリケーションがアイドル状態のときに、新しいクライアントをダウンロードするバック グラウンド プロセスを使用して更新されます。</span><span class="sxs-lookup"><span data-stu-id="077bc-111">The clients on the PC and Mac are updated by using a background process that checks for new builds and downloads the new client when the app is idle.</span></span>

<!--ENDOFSECTION-->

## <a name="plan-for-endpoint-quality"></a><span data-ttu-id="077bc-112">エンドポイントの品質管理の計画</span><span class="sxs-lookup"><span data-stu-id="077bc-112">Plan for endpoint quality</span></span>

<span data-ttu-id="077bc-113">次の図からわかるように、エンドポイントは、ユーザーに対して、高品質なエクスペリエンスを提供することの重要な基盤です。</span><span class="sxs-lookup"><span data-stu-id="077bc-113">As you can see from the diagram below, endpoints are an important building block in providing a quality experience for users.</span></span>

<span data-ttu-id="077bc-114">![の品質、およびサービスの管理がすべての 3 つのコンポーネントに重なっている 3 つのコンポーネントを説明する図。端点に重点を置いた]。(media/plan-my-users-experience-image1.png "の品質、およびサービスの管理がすべての 3 つのコンポーネントに重なっている 3 つのコンポーネントを説明する図。端点に重点を置いた")。</span><span class="sxs-lookup"><span data-stu-id="077bc-114">![Diagram describing the three components of quality, and how service management overlaps all three components. With a focus on endpoints.](media/plan-my-users-experience-image1.png "Diagram describing the three components of quality, and how service management overlaps all three components. With a focus on endpoints.")</span></span>

<span data-ttu-id="077bc-115">チームの端点は、Pc、Mac、タブレット、およびモバイル デバイスを含め、多くのデバイスで実行できます。</span><span class="sxs-lookup"><span data-stu-id="077bc-115">Teams endpoints can run on many devices, including PCs, Macs, tablets, and mobile devices.</span></span> <span data-ttu-id="077bc-116">経験の一部を含むだけでなく、そのデバイスは、ユーザーがデバイスに接続する方法-たとえば、デバイスの内蔵マイクとスピーカー、イヤホン、または、最適化されたヘッドセットを使用します。</span><span class="sxs-lookup"><span data-stu-id="077bc-116">Part of the experience not only encompasses the device, but how a user connects to the device—for example, using the device’s built-in mic/speaker, earbuds, or an optimized headset.</span></span> <span data-ttu-id="077bc-117">最適化されたヘッドセットを使用すると、全体的なユーザー エクスペリエンスを追加できます。</span><span class="sxs-lookup"><span data-stu-id="077bc-117">Using an optimized headset can enrich the overall user experience.</span></span>

<span data-ttu-id="077bc-118">エンドポイントの計画では、次のガイダンスを使用すると、組織の正常な契約時のチームが発生することを確認できます。</span><span class="sxs-lookup"><span data-stu-id="077bc-118">The following guidance on endpoint planning will help you ensure your organization has a successful onboarding experience with Teams.</span></span>

## <a name="endpoint-capability"></a><span data-ttu-id="077bc-119">エンドポイントの機能</span><span class="sxs-lookup"><span data-stu-id="077bc-119">Endpoint capability</span></span>

<span data-ttu-id="077bc-120">計画の最初の部分は、すべての Pc を確認して、組織内の他のデバイスは、チームを実行できます。</span><span class="sxs-lookup"><span data-stu-id="077bc-120">The first part of planning is to ensure all the PCs and other devices in your organization can run Teams.</span></span> <span data-ttu-id="077bc-121">これは、ハードウェアの要件を見るだけでなくが、他の PC が何をバック グラウンドでの理解も含まれます。</span><span class="sxs-lookup"><span data-stu-id="077bc-121">This involves not just looking at the hardware requirements, but also understanding what else the PC is doing in the background.</span></span> <span data-ttu-id="077bc-122">多くの組織では、侵入検知システムのウイルス対策ソフトウェアは、デバイスの基本のパフォーマンスに影響する場合など、その他のソフトウェアを実行します。</span><span class="sxs-lookup"><span data-stu-id="077bc-122">Many organizations run other software, including intrusion detection systems and antimalware software, which can affect the base performance of a device.</span></span>

<span data-ttu-id="077bc-123">チームのソフトウェア要件については、(web、デスクトップ、およびモバイル) は、各プラットフォーム上のクライアントは、[マイクロソフトのチーム用のクライアントを取得](https://docs.microsoft.com/microsoftteams/get-clients)参照してください。</span><span class="sxs-lookup"><span data-stu-id="077bc-123">For information about the software requirements for Teams clients on each platform (web, desktop, and mobile), see [Get clients for Microsoft Teams](https://docs.microsoft.com/microsoftteams/get-clients).</span></span>

## <a name="endpoint-firewalls"></a><span data-ttu-id="077bc-124">エンドポイントのファイアウォール</span><span class="sxs-lookup"><span data-stu-id="077bc-124">Endpoint firewalls</span></span>

<span data-ttu-id="077bc-125">クライアント側のファイアウォールでは、ユーザーの操作性に大きな影響を与えるをことができます。</span><span class="sxs-lookup"><span data-stu-id="077bc-125">Client-side firewalls can have a significant impact on the user experience.</span></span>
<span data-ttu-id="077bc-126">クライアント側のファイアウォールは、呼び出しを確立することを防ぐだけでなく、通話の音質に影響を与えます。</span><span class="sxs-lookup"><span data-stu-id="077bc-126">Client-side firewalls can affect call quality in addition to preventing a call from being established.</span></span> <span data-ttu-id="077bc-127">[Office 365 の Url と IP アドレスの範囲](https://aka.ms/o365ips)内の情報に基づいて、クライアント ファイアウォールで適切な除外を構成します。</span><span class="sxs-lookup"><span data-stu-id="077bc-127">Configure the appropriate exclusions on the client firewall based on the information in [Office 365 URLs and IP address ranges](https://aka.ms/o365ips).</span></span> <span data-ttu-id="077bc-128">サード パーティ ベンダーは、除外リストを作成する方法の具体的なガイダンスがあります。</span><span class="sxs-lookup"><span data-stu-id="077bc-128">Your third-party vendor will have specific guidance on how to create the exclusions.</span></span>

>[!NOTE]
> <span data-ttu-id="077bc-129">マイクロソフト チームは、適切なファイアウォール構成で Windows ファイアウォールを自動的に更新されます。</span><span class="sxs-lookup"><span data-stu-id="077bc-129">Microsoft Teams will automatically update the Windows Firewall with an appropriate firewall configuration.</span></span>

## <a name="wi-fi-recommendations-for-endpoints"></a><span data-ttu-id="077bc-130">エンドポイントの Wi-fi の推奨事項</span><span class="sxs-lookup"><span data-stu-id="077bc-130">Wi-Fi recommendations for endpoints</span></span>

<span data-ttu-id="077bc-131">マイクロソフトのチームでリアルタイムの作業負荷をサポートするために最適化された Wi-fi ネットワークを展開する計画がかなりかかります。</span><span class="sxs-lookup"><span data-stu-id="077bc-131">It takes significant planning to deploy an optimized Wi-Fi network to support real-time workloads in Microsoft Teams.</span></span> <span data-ttu-id="077bc-132">次のセクションでは、端点を計画するときは、一般的な落とし穴を回避するために役立ついくつかの一般的なガイダンスを提供します。</span><span class="sxs-lookup"><span data-stu-id="077bc-132">The following sections provide some general guidance that can help you avoid common pitfalls when planning for endpoints.</span></span>

### <a name="wi-fi-drivers"></a><span data-ttu-id="077bc-133">Wi-fi ドライバー</span><span class="sxs-lookup"><span data-stu-id="077bc-133">Wi-Fi drivers</span></span>

<span data-ttu-id="077bc-134">Wi-fi ドライバーによっては、問題が発生することができます。</span><span class="sxs-lookup"><span data-stu-id="077bc-134">Some Wi-Fi drivers can be problematic.</span></span> <span data-ttu-id="077bc-135">例として、ドライバーは、品質の低下の呼び出しの原因と、アクセス ポイント間で非常に積極的な移動の動作があります。</span><span class="sxs-lookup"><span data-stu-id="077bc-135">As an example, a driver might have very aggressive roaming behaviors between access points, causing poor call quality.</span></span>
<span data-ttu-id="077bc-136">よくある現象ではありませんが、PC の Wi-fi ドライバーが更新され、展開する前にテストすることを確認することが重要です。</span><span class="sxs-lookup"><span data-stu-id="077bc-136">This isn’t a common occurrence, but it’s important to ensure that Wi-Fi drivers on the PC have been updated and tested prior to deployment.</span></span>

### <a name="wi-fi-bands"></a><span data-ttu-id="077bc-137">Wi-fi バンド</span><span class="sxs-lookup"><span data-stu-id="077bc-137">Wi-Fi bands</span></span>

<span data-ttu-id="077bc-138">Wi-fi 機器は現在、2.4 GHz および 5.0 GHz で使用されているバンドの主に 2 種類あります。</span><span class="sxs-lookup"><span data-stu-id="077bc-138">There are primarily two types of bands used in Wi-Fi equipment today, 2.4 GHz and 5.0 GHz.</span></span> <span data-ttu-id="077bc-139">組織では、両方のバンドを提供する場合は、5.0 GHz バンドを使用するのには、ドライバーの設定を構成してください。</span><span class="sxs-lookup"><span data-stu-id="077bc-139">If your organization provides both bands, you should configure your driver settings to prefer the 5.0 GHz band.</span></span> <span data-ttu-id="077bc-140">このバンドはスループットの点ではるかに高密度と、2.4 GHz 帯域内で発生する障害で影響を受ける小さい。</span><span class="sxs-lookup"><span data-stu-id="077bc-140">This band is much denser in terms of throughput and is less affected by the interference seen in the 2.4 GHz band.</span></span>
<span data-ttu-id="077bc-141">この推奨事項では、5.0 GHz のネットワーク帯域を正しく最適化したことを前提としています。</span><span class="sxs-lookup"><span data-stu-id="077bc-141">This recommendation assumes that you’ve properly optimized the 5.0 GHz network band.</span></span>

### <a name="wi-fi-radio-type"></a><span data-ttu-id="077bc-142">Wi-fi 無線タイプ</span><span class="sxs-lookup"><span data-stu-id="077bc-142">Wi-Fi radio type</span></span>

<span data-ttu-id="077bc-143">新しい Wi-fi 無線の種類をサポートしているデバイスを計画します。</span><span class="sxs-lookup"><span data-stu-id="077bc-143">Plan for devices that support the newer Wi-Fi radio types.</span></span> <span data-ttu-id="077bc-144">802.11ac を活用する場合は、Wi-fi の非常に優れたパフォーマンスを取得できます以降にアップデートを提供するデバイスです。</span><span class="sxs-lookup"><span data-stu-id="077bc-144">You can get very good Wi-Fi performance if you leverage 802.11ac or newer on the devices you provision.</span></span>

### <a name="wireless-avoidance"></a><span data-ttu-id="077bc-145">ワイヤレスの回避</span><span class="sxs-lookup"><span data-stu-id="077bc-145">Wireless avoidance</span></span>

<span data-ttu-id="077bc-146">組織によっては、Wi-fi を完全に回避する場合します。</span><span class="sxs-lookup"><span data-stu-id="077bc-146">Some organizations prefer to avoid Wi-Fi altogether.</span></span> <span data-ttu-id="077bc-147">場合がありますこのガイドはユーザーがワイヤード (有線) ネットワークに直接接続するには推奨事項を用意されています。</span><span class="sxs-lookup"><span data-stu-id="077bc-147">Sometimes this guidance is provided through a recommendation to users to connect directly to a wired network.</span></span> <span data-ttu-id="077bc-148">場合によっては、ネットワークのバインド順序可能性があります優先ワイヤレス接続されているコンティニュ ワイヤード (有線) 接続する PC が接続されている場合でも、その接続を使用します。</span><span class="sxs-lookup"><span data-stu-id="077bc-148">In some cases, the network binding order might have the wireless connection preferred and continue to use that connection even though the PC is connected to the wired connection.</span></span> <span data-ttu-id="077bc-149">この予期しない動作を避けるためには、このシナリオを回避するのにはバインドの順序を構成します。</span><span class="sxs-lookup"><span data-stu-id="077bc-149">To avoid this unintended behavior, configure the binding order to avoid this scenario.</span></span>

### <a name="80211-power-save-protocol"></a><span data-ttu-id="077bc-150">802.11 省電力プロトコル</span><span class="sxs-lookup"><span data-stu-id="077bc-150">802.11 Power Save protocol</span></span>

<span data-ttu-id="077bc-151">組織では、ワイヤレス アクセス ポイントまたは 802.11 省電力プロトコルをサポートしないルーターを使用する場合、通話の中断や Windows のデバイスで実行されているマイクロソフトのチームでの不適切な呼び出し品質が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="077bc-151">If your organization uses wireless access points or routers that don’t support the 802.11 Power Save protocol, you might experience dropped calls or poor call quality in Microsoft Teams running on Windows devices.</span></span> <span data-ttu-id="077bc-152">ワイヤレス アクセス ポイントまたはルーターをアップグレードしない場合は、バッテリ電源で実行されているデバイス上の Windows の電源プランの設定を更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="077bc-152">If it’s not possible to upgrade your wireless access point or routers, you should update Windows Power Plan settings on devices that run on battery power.</span></span> <span data-ttu-id="077bc-153">次の[資料をサポート](https://support.microsoft.com/help/928152/you-may-experience-connectivity-issues-or-performance-issues-when-you)することでさらに詳細と構成のガイダンスが提供されます。</span><span class="sxs-lookup"><span data-stu-id="077bc-153">Further detail and configuration guidance is provided in the following [support article](https://support.microsoft.com/help/928152/you-may-experience-connectivity-issues-or-performance-issues-when-you).</span></span>

<table>
<tr><td>![](media/audio_conferencing_image7.png) <br/><span data-ttu-id="077bc-154">意思決定ポイント</span><span class="sxs-lookup"><span data-stu-id="077bc-154">Decision points</span></span></td><td><ul><li><span data-ttu-id="077bc-155">チーム クライアントは、組織内に展開されますか。</span><span class="sxs-lookup"><span data-stu-id="077bc-155">What Teams clients will be deployed in your organization?</span></span></li><li><span data-ttu-id="077bc-156">方法は最初にクライアントを展開するチーム、ユーザーにしますか。</span><span class="sxs-lookup"><span data-stu-id="077bc-156">How will you initially deploy Teams clients to your users?</span></span></li><li><span data-ttu-id="077bc-157">高品質のエクスペリエンスのチームの要件を満たすエンドポイント、および検証するためにデバイスの評価を担当しますか。</span><span class="sxs-lookup"><span data-stu-id="077bc-157">Who is responsible for evaluating endpoints and devices to validate they meet Teams requirements for a quality experience?</span></span></li></ul></td></tr>
<tr><td>![](media/audio_conferencing_image9.png)<br/><span data-ttu-id="077bc-158">次のステップ</span><span class="sxs-lookup"><span data-stu-id="077bc-158">Next steps</span></span></td><td><ul><li><span data-ttu-id="077bc-159">後に、チームのクライアントを展開するプロセスを文書化します。</span><span class="sxs-lookup"><span data-stu-id="077bc-159">Document the process that will be followed to deploy Teams clients.</span></span></li><li><span data-ttu-id="077bc-160">エンドポイント、およびデバイスを評価し、実行および必要な改善策です。</span><span class="sxs-lookup"><span data-stu-id="077bc-160">Evaluate endpoints and devices and perform and remediation required.</span></span></li></ul></td></tr>
</table>

<!--ENDOFSECTION-->

## <a name="devices-for-teams"></a><span data-ttu-id="077bc-161">チーム用のデバイス</span><span class="sxs-lookup"><span data-stu-id="077bc-161">Devices for Teams</span></span>

<span data-ttu-id="077bc-162">マイクロソフト チームは、会議や電話システムとして使用できます。</span><span class="sxs-lookup"><span data-stu-id="077bc-162">Microsoft Teams can be used for meetings or as a phone system.</span></span> <span data-ttu-id="077bc-163">これらの機能を使用して、チームのために使用されるインタ フェース デバイスは、ユーザー エクスペリエンスの重要な役割を果たします。</span><span class="sxs-lookup"><span data-stu-id="077bc-163">When using these features, the interface device that is used for Teams plays an important role in the user experience.</span></span>

<span data-ttu-id="077bc-164">組み込み PC スピーカーとマイクを使用しては、その構成を持っているユーザーに受け入れ可能な場合がありますサウンドです。</span><span class="sxs-lookup"><span data-stu-id="077bc-164">Using a built-in PC speaker and microphone might sound acceptable to the user who has that configuration.</span></span> <span data-ttu-id="077bc-165">ですが、通常、これらのデバイスは、ノイズ除去、用に最適化されていないし、周囲のノイズの任意の種類、ダウン ストリームに影響を与え他のユーザーの呼び出しに。</span><span class="sxs-lookup"><span data-stu-id="077bc-165">But typically, those devices aren’t optimized for noise cancellation, and any type of ambient noise can have a downstream impact on others on the call.</span></span> <span data-ttu-id="077bc-166">これらのシナリオ用に最適化されたデバイスを活用することと、質の高い環境を実現するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="077bc-166">Leveraging devices optimized for these scenarios will help ensure a high-quality experience.</span></span>

<span data-ttu-id="077bc-167">各デバイスは、ユーザーのニーズを満たす必要があります。</span><span class="sxs-lookup"><span data-stu-id="077bc-167">Each device needs to meet the needs of your users.</span></span> <span data-ttu-id="077bc-168">別のペルソナのヘッドセットなどのデバイスを調整し、組織内のユース ケースにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="077bc-168">You’ll need to tailor devices such as headsets for the different personas and use cases in your organization.</span></span>
<span data-ttu-id="077bc-169">ペルソナとデバイスのマッピングの手順は、計画プロセスの一部として完了する必要があります。</span><span class="sxs-lookup"><span data-stu-id="077bc-169">A persona-to-device mapping exercise should be completed as part of the planning process.</span></span>

<span data-ttu-id="077bc-170">デバイスを選択したら、それらを最終的な検証のためのパイロット テスト計画に含まれます。</span><span class="sxs-lookup"><span data-stu-id="077bc-170">After you’ve selected the devices, include them in the pilot test plan for final validation.</span></span> <span data-ttu-id="077bc-171">試験運用で、デバイスの戦略を確実にフィードバックを収集するアンケートを活用して、最適です。</span><span class="sxs-lookup"><span data-stu-id="077bc-171">Leverage surveys during the pilot to collect feedback to ensure your device strategy is optimal.</span></span>

> [!NOTE]
> <span data-ttu-id="077bc-172">この時点でビジネス認定プログラムは、Skype で認定されているオーディオ デバイスの使用をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="077bc-172">At this time, we recommend using audio devices that were certified through the Skype for Business Certification program.</span></span> <span data-ttu-id="077bc-173">このプログラムによって認定デバイスを検索するには、[ビジネスの Skype の USB デバイスの認定](http://partnersolutions.skypeforbusiness.com/solutionscatalog/personal-peripherals-pcs)ソリューション カタログを参照してください。</span><span class="sxs-lookup"><span data-stu-id="077bc-173">To find devices certified under this program, see the [USB Devices Certified for Skype for Business](http://partnersolutions.skypeforbusiness.com/solutionscatalog/personal-peripherals-pcs) solutions catalog.</span></span>

<table>
<tr><td>![](media/audio_conferencing_image7.png) <br/><span data-ttu-id="077bc-174">意思決定ポイント</span><span class="sxs-lookup"><span data-stu-id="077bc-174">Decision points</span></span></td><td><ul><li><span data-ttu-id="077bc-175">ユーザーと会議室の経験を組織の全体的なデバイスの戦略を決定します。</span><span class="sxs-lookup"><span data-stu-id="077bc-175">Decide on your organization’s overall device strategy for user and meeting room experiences.</span></span></li></ul></td></tr>
<tr><td>![](media/audio_conferencing_image9.png)<br/><span data-ttu-id="077bc-176">次のステップ</span><span class="sxs-lookup"><span data-stu-id="077bc-176">Next steps</span></span></td><td><ul><li><span data-ttu-id="077bc-177">組織のペルソナとデバイスのマッピングの手順を完了します。</span><span class="sxs-lookup"><span data-stu-id="077bc-177">Complete a persona-to-device mapping exercise for your organization.</span></span></li><li><span data-ttu-id="077bc-178">ユーザーのデバイスを取得して、会議室のプロセスを文書化します。</span><span class="sxs-lookup"><span data-stu-id="077bc-178">Document the process for obtaining devices for users and meeting rooms.</span></span></li><li><span data-ttu-id="077bc-179">ユーザーと会議室の配置と構成のデバイスのプロセスを文書化します。</span><span class="sxs-lookup"><span data-stu-id="077bc-179">Document the process for deploying and configuration devices for users and meeting rooms.</span></span></li><li><span data-ttu-id="077bc-180">展開作業を開始する最初のデバイスを購入します。</span><span class="sxs-lookup"><span data-stu-id="077bc-180">Procure initial devices to begin your deployment.</span></span></li></ul></td></tr>
</table>

<!--ENDOFSECTION-->