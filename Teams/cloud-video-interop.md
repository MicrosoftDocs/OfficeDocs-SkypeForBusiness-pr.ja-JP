---
title: Microsoft Teams のクラウド ビデオ相互運用性
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
ms.reviewer: srividhc
description: クラウドビデオ相互運用機能を利用すると、サードパーティの会議室デバイスが Microsoft Teams 会議に参加できるようになります。
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9a3da2281ffcc444478a32e3a4980f707acfd25f
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32198531"
---
# <a name="cloud-video-interop-for-microsoft-teams"></a><span data-ttu-id="88e8e-103">Microsoft Teams のクラウド ビデオ相互運用性</span><span class="sxs-lookup"><span data-stu-id="88e8e-103">Cloud Video Interop for Microsoft Teams</span></span>

<span data-ttu-id="88e8e-104">クラウドビデオ相互運用機能 (CVI) は、microsoft Teams 会議に参加するためのサードパーティの会議室 (テレプレゼンス) と個人用ビデオデバイス (VTCs) を可能にする、Microsoft 認定のサードパーティソリューションです。</span><span class="sxs-lookup"><span data-stu-id="88e8e-104">Cloud Video Interop (CVI) is a Microsoft Qualified third-party solution that enables third-party meeting rooms (telepresence) and personal video devices (VTCs) to join Microsoft Teams meetings.</span></span>
 
<span data-ttu-id="88e8e-105">Microsoft Teams を使用すると、オーディオ、ビデオ、コンテンツの共有を含む、豊富なオンラインコンテンツコラボレーションを会議で利用できます。</span><span class="sxs-lookup"><span data-stu-id="88e8e-105">With Microsoft Teams, you get rich online content collaboration in meetings that include audio, video, and content sharing.</span></span> <span data-ttu-id="88e8e-106">これは、デスクトップと web クライアント、および Microsoft Teams とネイティブに統合されている多くのパートナーデバイスを通じて利用することができます。</span><span class="sxs-lookup"><span data-stu-id="88e8e-106">This can be enjoyed through the desktop and web client, as well as through many partner devices that integrate natively with Microsoft Teams.</span></span> <span data-ttu-id="88e8e-107">ただし、多くのお客様は、すでにビデオ会議や個人のビデオ通信デバイスに投資していますが、アップグレードにはコストがかかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="88e8e-107">However, many customers have already invested in video teleconferencing and personal video communication devices, which can be expensive to upgrade.</span></span> <span data-ttu-id="88e8e-108">クラウドビデオの相互運用機能により、簡単な解決方法が提供されるため、アップグレードの準備ができたら、既存のソリューションを引き続き使用できます。</span><span class="sxs-lookup"><span data-stu-id="88e8e-108">Cloud Video Interop provides an easy solution, allowing you to keep using your existing solutions until you are ready to upgrade.</span></span>

<span data-ttu-id="88e8e-109">クラウドビデオの相互運用機能を使用すると、Microsoft Teams がすべての参加者に対してネイティブな会議エクスペリエンスを提供します。会議室または Teams クライアントの内部で行います。</span><span class="sxs-lookup"><span data-stu-id="88e8e-109">With Cloud Video Interop, Microsoft Teams delivers a native meeting experience for all participants – in meeting rooms or inside of Teams clients.</span></span>

### <a name="is-cloud-video-interop-for-me"></a><span data-ttu-id="88e8e-110">クラウドビデオの相互運用機能</span><span class="sxs-lookup"><span data-stu-id="88e8e-110">Is Cloud Video Interop for me?</span></span>

<span data-ttu-id="88e8e-111">クラウドビデオ相互運用機能は、チームのエンドポイントを使用して、完全なネイティブの Microsoft Teams ソリューションに移行しながら、中間的なサービスを提供します。</span><span class="sxs-lookup"><span data-stu-id="88e8e-111">Cloud Video Interop provides an intermediate service while you transition to a full native Microsoft Teams Solution, using Teams endpoints.</span></span> <span data-ttu-id="88e8e-112">提供されるサービスは、移行パスの一部である必要があります。</span><span class="sxs-lookup"><span data-stu-id="88e8e-112">The service provided should be part of your migration path.</span></span>

<span data-ttu-id="88e8e-113">クラウドビデオの相互運用機能は、次の条件を満たしているお客様を対象としています。</span><span class="sxs-lookup"><span data-stu-id="88e8e-113">Cloud Video Interop is intended for customers who meet the following criteria:</span></span>

- <span data-ttu-id="88e8e-114">Microsoft Teams との直接統合が認められていない、会議室デバイスと個人用ビデオデバイスの展開 (50 以上のデバイス) の大規模な展開を行う</span><span class="sxs-lookup"><span data-stu-id="88e8e-114">Have a large deployment of meeting room devices and personal video devices deployment (50+ devices) that are not qualified for direct integration with Microsoft Teams</span></span>
- <span data-ttu-id="88e8e-115">は、クラウドビデオの相互運用パートナーのいずれかでサポートされています。</span><span class="sxs-lookup"><span data-stu-id="88e8e-115">Are supported by one of our Cloud Video Interop partners</span></span>
- <span data-ttu-id="88e8e-116">Microsoft Teams のネイティブソリューションへの移行中に、現在の会議室のデバイスと個人用のビデオデバイスで投資の金額の値を保持する</span><span class="sxs-lookup"><span data-stu-id="88e8e-116">Want to retain the value of their investment in their current meeting room devices and personal video devices during the migration to a native Microsoft Teams solution</span></span>

<span data-ttu-id="88e8e-117">クラウドビデオ相互運用機能は、優れた中級ソリューションを提供していますが、お客様は長期のチームルームシステムなどのネイティブのチーム会議ソリューションを参照することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="88e8e-117">While Cloud Video Interop provides a great intermediate solution, we encourage our customers to look into our native Teams Meeting solutions, such as Teams Room Systems, for the long term.</span></span> 

### <a name="partners-certified-for-microsoft-teams"></a><span data-ttu-id="88e8e-118">Microsoft Teams の認定パートナー</span><span class="sxs-lookup"><span data-stu-id="88e8e-118">Partners Certified for Microsoft Teams</span></span>

<span data-ttu-id="88e8e-119">次のパートナーには、Microsoft Teams のビデオ相互運用ソリューションが用意されています。</span><span class="sxs-lookup"><span data-stu-id="88e8e-119">The following partners have video interop solutions for Microsoft Teams.</span></span> <span data-ttu-id="88e8e-120">会社では、企業内でこれらのパートナーの任意の組み合わせを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="88e8e-120">Your company may choose to work with any combination of these partners within your enterprise.</span></span> 

|<span data-ttu-id="88e8e-121">パートナー</span><span class="sxs-lookup"><span data-stu-id="88e8e-121">Partner</span></span>|<span data-ttu-id="88e8e-122">パートナーソリューション</span><span class="sxs-lookup"><span data-stu-id="88e8e-122">Partner solution</span></span>|
|----|---|
|![Polycom RealConnect](media/polycom.png) | <span data-ttu-id="88e8e-124"><a href="https://aka.ms/PolycomRealConnect" target="_blank">Polycom RealConnect サービス</a></span><span class="sxs-lookup"><span data-stu-id="88e8e-124"><a href="https://aka.ms/PolycomRealConnect" target="_blank">Polycom RealConnect Service</a></span></span> |
|![Pexip 無限大](media/pexip.png)| <span data-ttu-id="88e8e-126"><a href="https://aka.ms/PexipInfinity" target="_blank">Microsoft Teams の Pexip 無限大</a></span><span class="sxs-lookup"><span data-stu-id="88e8e-126"><a href="https://aka.ms/PexipInfinity" target="_blank">Pexip Infinity for Microsoft Teams</a></span></span> | 
|![BlueJeans Gateway](media/bluejeans.png)| <span data-ttu-id="88e8e-128"><a href="https://aka.ms/BluejeansGateway" target="_blank">Microsoft Teams の BlueJeans ゲートウェイ</a></span><span class="sxs-lookup"><span data-stu-id="88e8e-128"><a href="https://aka.ms/BluejeansGateway" target="_blank">BlueJeans Gateway for Microsoft Teams</a></span></span> |

### <a name="cloud-video-interop-overview"></a><span data-ttu-id="88e8e-129">クラウドビデオの相互運用の概要</span><span class="sxs-lookup"><span data-stu-id="88e8e-129">Cloud Video Interop overview</span></span>

<span data-ttu-id="88e8e-130">クラウドビデオ相互運用機能は、社内のビデオ会議と、オンプレミスのビデオデバイスソリューション、および Microsoft Teams との相互運用性を実現するために、パートナーが提供するサードパーティサービスです。</span><span class="sxs-lookup"><span data-stu-id="88e8e-130">Cloud Video Interop is a third-party service that is offered by our partners to provide interoperability between existing video conferencing and personal video device solutions on premises, and Microsoft Teams.</span></span>

<span data-ttu-id="88e8e-131">パートナーが提供するソリューションは、完全なクラウドベースまたは一部/すべてのオンプレミスのいずれかに展開できるコンポーネントで構成されます。</span><span class="sxs-lookup"><span data-stu-id="88e8e-131">The solutions offered by our partners consist of components that can be deployed either fully cloud based or partially/fully on premises.</span></span> 
     
<span data-ttu-id="88e8e-132">次の図は、パートナーソリューションの上位レベルのアーキテクチャを示しています。</span><span class="sxs-lookup"><span data-stu-id="88e8e-132">The following diagram shows the high-level architecture of our partner solutions.</span></span>

![Teams Cloud ビデオの相互運用性パートナーソリューション](media/teams-cloud-video-interop-partner-solution.png)


## <a name="deploy-cloud-video-interop"></a><span data-ttu-id="88e8e-134">クラウドビデオの相互運用機能を導入する</span><span class="sxs-lookup"><span data-stu-id="88e8e-134">Deploy Cloud Video Interop</span></span>

<span data-ttu-id="88e8e-135">クラウドビデオ相互運用ソリューションを展開するときは、パートナーソリューションを展開することを理解しておくことが重要です。</span><span class="sxs-lookup"><span data-stu-id="88e8e-135">When deploying a Cloud Video Interop solution, it’s important to understand that you are deploying a partner solution.</span></span> <span data-ttu-id="88e8e-136">クラウドビデオの相互運用機能を展開するための一般的な手順を次の図に示します。</span><span class="sxs-lookup"><span data-stu-id="88e8e-136">The general steps you should take to deploy Cloud Video Interop are listed in the following diagram.</span></span>

![組織での CVI の展開](media/deploying-cvi.png)

### <a name="plan"></a><span data-ttu-id="88e8e-138">プラン</span><span class="sxs-lookup"><span data-stu-id="88e8e-138">Plan</span></span>

<span data-ttu-id="88e8e-139">計画フェーズでは、ネイティブの Teams デバイスと置き換えることができないデバイスを特定し、これらのデバイスをサポートできるクラウドビデオの相互運用パートナーを見つけます。</span><span class="sxs-lookup"><span data-stu-id="88e8e-139">During the plan phase, you should identify the devices that you will not replace with a native Teams device, and find a Cloud Video Interop partner that can support these devices.</span></span>  

<span data-ttu-id="88e8e-140">また、クラウドビデオ相互運用対応デバイスを参加させる会議をスケジュールするユーザーごとに、ライセンスが必要であることを理解しておくことも重要です。</span><span class="sxs-lookup"><span data-stu-id="88e8e-140">It’s also important to understand that you will need a license for each user who will schedule meetings in which you want a Cloud Video Interop-enabled device to join.</span></span> <span data-ttu-id="88e8e-141">正確なライセンス要件は、クラウドビデオの相互運用パートナーから入手できることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="88e8e-141">Note that exact licensing requirements can be obtained from the Cloud Video Interop partner.</span></span> <span data-ttu-id="88e8e-142">展開を開始する前に、これが明確であることを確認します。</span><span class="sxs-lookup"><span data-stu-id="88e8e-142">Ensure that this is clear before you start your deployment.</span></span>

### <a name="configure"></a><span data-ttu-id="88e8e-143">構成</span><span class="sxs-lookup"><span data-stu-id="88e8e-143">Configure</span></span>

<span data-ttu-id="88e8e-144">CVI 展開用に選択したパートナーには、組織内で正常に展開するために必要なすべての手順で構成される完全な展開ドキュメントが提供されます。</span><span class="sxs-lookup"><span data-stu-id="88e8e-144">The partner that you have chosen for your CVI deployment will provide you with a full deployment document that consists of all the steps needed to deploy successfully within your organization.</span></span> <span data-ttu-id="88e8e-145">これには、ファイアウォールポートと IP 範囲、デバイスの構成の変更、変更が必要なその他の設定が含まれます。</span><span class="sxs-lookup"><span data-stu-id="88e8e-145">This will include firewall ports and IP ranges, configuration changes for your devices, and other settings that need to change.</span></span>

### <a name="provision"></a><span data-ttu-id="88e8e-146">規定</span><span class="sxs-lookup"><span data-stu-id="88e8e-146">Provision</span></span>  

<span data-ttu-id="88e8e-147">プロビジョニングフェーズでは、パートナー構成ガイドに従ってライセンスを適切なユーザーに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="88e8e-147">During the provision phase, you will assign licenses to the appropriate users according to the partner configuration guide.</span></span> <span data-ttu-id="88e8e-148">また、Azure の同意プロセスに従って、パートナーのアクセスをチーム環境に提供する必要があります。</span><span class="sxs-lookup"><span data-stu-id="88e8e-148">You will also need to go through the Azure Consent process to provide the partner access to your Teams environment.</span></span> <span data-ttu-id="88e8e-149">Azure 同意プロセスの詳細については、次のページを参照してください。https://docs.microsoft.com/en-us/azure/active-directory/develop/v2-permissions-and-consent</span><span class="sxs-lookup"><span data-stu-id="88e8e-149">More information on the Azure Consent process can be found here: https://docs.microsoft.com/en-us/azure/active-directory/develop/v2-permissions-and-consent</span></span> 

### <a name="schedule"></a><span data-ttu-id="88e8e-150">基点</span><span class="sxs-lookup"><span data-stu-id="88e8e-150">Schedule</span></span>

<span data-ttu-id="88e8e-151">クラウドビデオ相互運用機能が有効になった後、[Teams 会議] アドインを使用して予定されている Outlook または Teams クライアントでは、適切な追加情報が Teams 会議に自動的に追加されるため、クラウドビデオを利用することができるようになります。相互運用対応デバイスは、これらの会議に参加できます。</span><span class="sxs-lookup"><span data-stu-id="88e8e-151">After a user is enabled for Cloud Video Interop, any meeting scheduled using either the Teams Meeting Add-in for Outlook or the Teams Client will have the appropriate additional information automatically added into the Teams meeting so that Cloud Video Interop-compatible devices can join these meetings.</span></span>

### <a name="join"></a><span data-ttu-id="88e8e-152">Join</span><span class="sxs-lookup"><span data-stu-id="88e8e-152">Join</span></span>

<span data-ttu-id="88e8e-153">パートナーソリューションによっては、クラウドビデオ相互運用対応の会議に参加するには、いくつかの方法があります。</span><span class="sxs-lookup"><span data-stu-id="88e8e-153">Depending on the partner solution, there are several ways to join a Cloud Video Interop-enabled meeting.</span></span> <span data-ttu-id="88e8e-154">会議の正確な参加シナリオは、クラウドビデオの相互運用パートナーによって提供されます。</span><span class="sxs-lookup"><span data-stu-id="88e8e-154">Exact meeting join scenarios will be provided by your Cloud Video Interop partner.</span></span> <span data-ttu-id="88e8e-155">以下に例をいくつか示しました。</span><span class="sxs-lookup"><span data-stu-id="88e8e-155">We’ve listed some examples below:</span></span>

- <span data-ttu-id="88e8e-156">IVR (インタラクティブな音声応答)</span><span class="sxs-lookup"><span data-stu-id="88e8e-156">IVR (Interactive Voice Response)</span></span> 
  - <span data-ttu-id="88e8e-157">Tenantkey @ domain を使って、パートナーの IVR にダイヤルインすることができます。</span><span class="sxs-lookup"><span data-stu-id="88e8e-157">You can dial in to the partner's IVR using the tenantkey@domain.</span></span>
  - <span data-ttu-id="88e8e-158">パートナー IVR を使用している場合は、VTC conferenceId を入力するように求められます。これにより、Teams の会議に接続されます。</span><span class="sxs-lookup"><span data-stu-id="88e8e-158">When you are in the partner IVR, you will be prompted to enter the VTC conferenceId, which will then connect you to the Teams meeting.</span></span>
- <span data-ttu-id="88e8e-159">ダイレクトダイヤル</span><span class="sxs-lookup"><span data-stu-id="88e8e-159">Direct dial</span></span> 
  - <span data-ttu-id="88e8e-160">このダイレクトダイヤル機能を使用すると、パートナーの IVR とやり取りすることなく、直接、tenantkey の完全な文字列を使用して、Teams 会議に直接ダイヤルインすることができます。VTC ConferenceId @ domain</span><span class="sxs-lookup"><span data-stu-id="88e8e-160">You can directly dial in to the Teams meeting without interacting with the partner’s IVR by using the direct dial feature, using the full string of tenantkey.VTC ConferenceId@domain.</span></span>
- <span data-ttu-id="88e8e-161">ワンタッチダイヤル</span><span class="sxs-lookup"><span data-stu-id="88e8e-161">One-touch dial</span></span> 
  - <span data-ttu-id="88e8e-162">統合されたチームルームがある場合は、パートナーが提供するワンタッチダイヤル機能を使用できます (ダイヤル文字列を入力する必要はありません)。</span><span class="sxs-lookup"><span data-stu-id="88e8e-162">If you have an integrated Teams room, you can use the one-touch dial capabilities offered by your partner (without needing to type any dial string).</span></span>

## <a name="manage-cloud-video-interop"></a><span data-ttu-id="88e8e-163">クラウドビデオの相互運用機能を管理する</span><span class="sxs-lookup"><span data-stu-id="88e8e-163">Manage Cloud Video Interop</span></span>

<span data-ttu-id="88e8e-164">クラウドビデオ相互運用機能を展開した後は、パートナーが提供するソリューションを使用してデバイスを管理することができます。</span><span class="sxs-lookup"><span data-stu-id="88e8e-164">After Cloud Video Interop is deployed, you can manage the devices using the solutions provided by our partners.</span></span> <span data-ttu-id="88e8e-165">各パートナーには、ライセンスとデバイスの管理の両方を含む、管理インターフェイスが用意されています。</span><span class="sxs-lookup"><span data-stu-id="88e8e-165">Each partner will provide you with an administrative interface that will include both license and device management.</span></span> 

<span data-ttu-id="88e8e-166">レポートは、パートナー管理インターフェイスから直接利用することもできます。</span><span class="sxs-lookup"><span data-stu-id="88e8e-166">Reporting is also available directly from the partner administrative interface.</span></span> <span data-ttu-id="88e8e-167">レポート機能の詳細については、お好みのパートナーにお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="88e8e-167">For more information on reporting capabilities, contact the partner of your choice.</span></span> 

### <a name="troubleshooting-cloud-video-interop"></a><span data-ttu-id="88e8e-168">クラウドビデオの相互運用のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="88e8e-168">Troubleshooting Cloud Video Interop</span></span>

<span data-ttu-id="88e8e-169">クラウドビデオ相互運用機能はパートナーが提供するサービスです。</span><span class="sxs-lookup"><span data-stu-id="88e8e-169">Cloud Video Interop is a partner-provided service.</span></span> <span data-ttu-id="88e8e-170">問題が発生した場合は、最初の手順として、Teams クライアントがインストールされているデバイスを接続して、問題の原因となっているクラウドビデオ相互運用デバイスと同じセグメントに接続します。</span><span class="sxs-lookup"><span data-stu-id="88e8e-170">If you are experiencing issues, the first step is to connect a device that has the Teams Client installed and connect it to the same segment as the Cloud Video Interop device that is causing problems.</span></span> 

<span data-ttu-id="88e8e-171">Teams がこのセグメントで正しく機能し、パートナーが提供したすべてのネットワークと構成のガイドラインも順守されている場合は、さらにトラブルシューティングのためにパートナーに連絡する必要があります。</span><span class="sxs-lookup"><span data-stu-id="88e8e-171">If Teams functions correctly on this segment, and you have also followed all the networking and configuration guidelines the partner has provided, you will need to contact the partner for further troubleshooting.</span></span> 

## <a name="powershell-for-cloud-video-interop"></a><span data-ttu-id="88e8e-172">PowerShell for Cloud Video Interop</span><span class="sxs-lookup"><span data-stu-id="88e8e-172">PowerShell for Cloud Video Interop</span></span>

<span data-ttu-id="88e8e-173">次の PowerShell コマンドレットを使用して、クラウドビデオ相互運用機能の展開を自動化することができます (部分的な場合)。</span><span class="sxs-lookup"><span data-stu-id="88e8e-173">The following PowerShell cmdlets are available for you to (partially) automate the Cloud Video Interop deployment.</span></span>

- <span data-ttu-id="88e8e-174">**CsTeamsVideoInteropServicepolicy**: サポートされているパートナーのそれぞれに対して事前構築されたポリシーを提供します。これにより、クラウドビデオ相互運用に使用するパートナーを指定することができます。</span><span class="sxs-lookup"><span data-stu-id="88e8e-174">**Get-CsTeamsVideoInteropServicepolicy**: Microsoft provides pre-constructed policies for each of our supported partners that allow you to designate which partner(s) to use for Cloud Video Interop.</span></span><br><span data-ttu-id="88e8e-175">このコマンドレットでは、組織で使用できる事前構築済みのポリシーを識別できます。</span><span class="sxs-lookup"><span data-stu-id="88e8e-175">This cmdlet allows you to identify the pre-constructed policies that you can use in your organization.</span></span> <span data-ttu-id="88e8e-176">このポリシーは、Grant-CsTeamsVideoInteropServicePolicy コマンドレットを利用して、1人以上のユーザーに割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="88e8e-176">You can assign this policy to one or more of your users by leveraging the Grant-CsTeamsVideoInteropServicePolicy cmdlet.</span></span>
- <span data-ttu-id="88e8e-177">**Grant-CsTeamsVideoInteropServicePolicy**: このコマンドレットでは、組織で使用するために事前構築されたポリシーを割り当てることができます。または、特定のユーザーにポリシーを割り当てることもできます。</span><span class="sxs-lookup"><span data-stu-id="88e8e-177">**Grant-CsTeamsVideoInteropServicePolicy**: This cmdlet allows you to assign a pre-constructed policy for use in your organization or assign the policy to specific users.</span></span>
- <span data-ttu-id="88e8e-178">**新規-CsVideoInteropServiceProvider**: 組織で使用したいサポートされている cvi パートナーに関する情報を指定するには、このコマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="88e8e-178">**New-CsVideoInteropServiceProvider**: Use this cmdlet to specify information about a supported CVI partner that your organization would like to use.</span></span>
- <span data-ttu-id="88e8e-179">**Set-CsVideoInteropServiceProvider**: このコマンドレットを使用して、組織が使用しているサポートされている cvi パートナーに関する情報を更新します。</span><span class="sxs-lookup"><span data-stu-id="88e8e-179">**Set-CsVideoInteropServiceProvider**: Use this cmdlet to update information about a supported CVI partner that your organization uses.</span></span>
- <span data-ttu-id="88e8e-180">**Get-CsVideoInteropServiceProvider**: 組織内で使用するように構成されているすべてのプロバイダーを取得するには、このコマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="88e8e-180">**Get-CsVideoInteropServiceProvider**: Use this cmdlet to get all of the providers that have been configured for use within the organization.</span></span>
- <span data-ttu-id="88e8e-181">**Remove-CsVideoInteropServiceProvider**: このコマンドレットを使用して、組織で使用されなくなったプロバイダーに関するすべてのプロバイダー情報を削除します。</span><span class="sxs-lookup"><span data-stu-id="88e8e-181">**Remove-CsVideoInteropServiceProvider**: Use this cmdlet to remove all provider information about a provider that your organization no longer uses.</span></span>
