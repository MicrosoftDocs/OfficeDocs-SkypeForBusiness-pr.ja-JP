---
title: Teams for Virtual の訪問
author: cichur
ms.author: v-cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Healthcare
- microsoftcloud-healthcare
appliesto:
- Microsoft Teams
ms.reviewer: ''
description: Microsoft Teams を使用して仮想訪問システムをセットアップする
ms.openlocfilehash: 4c8511939532a448d5229865618aa308494c7a42
ms.sourcegitcommit: 4bf85d91befb56566130731198518c103a53ebc4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2021
ms.locfileid: "50101335"
---
# <a name="virtual-visits-with-teams---integration-into-ehr"></a><span data-ttu-id="20979-103">Teams を使用した仮想アクセス - EHR への統合</span><span class="sxs-lookup"><span data-stu-id="20979-103">Virtual visits with Teams - Integration into EHR</span></span>

<span data-ttu-id="20979-104">Microsoft Teams 電子健康記録 (EHR) コネクタを使用すると、診療所は、EHR システムから直接 Teams の別のプロバイダーへの仮想患者訪問または相談を簡単に開始できます。</span><span class="sxs-lookup"><span data-stu-id="20979-104">Microsoft Teams Electronic Health Record (EHR) Connector makes it easy for clinicians to launch a virtual patient visit or consultation with another provider in Teams directly from the EHR system.</span></span> <span data-ttu-id="20979-105">Microsoft Teams は、Microsoft 365 クラウド上に構築され、HIPAA、HITECH 認定、その他のコンプライアンスをサポートする単一のハブで、チャット、ビデオ、音声、医療ツールを使用した簡単で安全な共同作業とコミュニケーションを可能にしています。</span><span class="sxs-lookup"><span data-stu-id="20979-105">Built on the Microsoft 365 cloud, Microsoft Teams enables simple, secure collaboration and communication with chat, video, voice, and healthcare tools in a single hub that supports compliance with HIPAA, HITECH certification, and more.</span></span>
<span data-ttu-id="20979-106">Teams のコミュニケーションプラットフォームとコラボレーション プラットフォームを使用すると、診療所は断片化したシステムを簡単に切り取り、可能な限り最適なケアを提供するために時間を費やします。</span><span class="sxs-lookup"><span data-stu-id="20979-106">The communication and collaboration platform of Teams makes it easy for clinicians to cut through the clutter of fragmented systems so they can spend time providing the best possible care.</span></span> <span data-ttu-id="20979-107">Microsoft Teams 電子健康記録 (EHR) コネクタでは、次の機能を使用できます。</span><span class="sxs-lookup"><span data-stu-id="20979-107">Microsoft Teams Electronic Health Record (EHR) Connector can:</span></span>
- <span data-ttu-id="20979-108">Teams の仮想アクセスをプロバイダーと患者の両方のポータルから起動します。</span><span class="sxs-lookup"><span data-stu-id="20979-108">Launch Teams virtual visits from both provider and patient portals.</span></span>
- <span data-ttu-id="20979-109">接続イベントと切断イベントの EHR メタデータに書き戻して、自動監査と記録を有効にする。</span><span class="sxs-lookup"><span data-stu-id="20979-109">Write back into EHR metadata on connect and disconnect events to enable automatic auditing and record keeping.</span></span>
- <span data-ttu-id="20979-110">Microsoft Teams を使用しながら、既存の診療所や患者のワークフローに統合します。</span><span class="sxs-lookup"><span data-stu-id="20979-110">Integrate into existing clinician and patient workflows while allowing them to use Microsoft Teams.</span></span>

  <span data-ttu-id="20979-111">EHR ポータルから仮想アクセスを管理する方法のビデオをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="20979-111">Watch the video of How to manage virtual visits from the EHR portal.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4HAtn]

## <a name="before-you-begin"></a><span data-ttu-id="20979-112">開始する前に</span><span class="sxs-lookup"><span data-stu-id="20979-112">Before you begin</span></span>

<span data-ttu-id="20979-113">EHR コネクタを統合する前に、次の前提条件を満たしていることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="20979-113">You’ll need to make sure you have the following prerequisites before you can integrate the EHR connector:</span></span>

- <span data-ttu-id="20979-114">エピスの App Marketplace マーケットプレースで Microsoft Teams [アプリに使用するアクセス](https://apporchard.epic.com/Gallery?id=6153)。</span><span class="sxs-lookup"><span data-stu-id="20979-114">Access to use to the Microsoft Teams app in [Epic’s App Orchard marketplace](https://apporchard.epic.com/Gallery?id=6153).</span></span>

- <span data-ttu-id="20979-115">医療向け Microsoft Cloud のアクティブなサブスクリプション、または Microsoft Teams EHR Connector 単体プランのサブスクリプション (実稼働テスト中にのみ適用されます)。</span><span class="sxs-lookup"><span data-stu-id="20979-115">Active subscription to Microsoft Cloud for Healthcare or subscription to Microsoft Teams EHR Connector standalone offer (only enforced during production testing).</span></span>

- <span data-ttu-id="20979-116">ユーザーは、Microsoft Teams 会議を含む適切な Microsoft 365 Office 365 ライセンスを持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="20979-116">Users must have an appropriate Microsoft 365 or Office 365 license that includes Microsoft Teams meetings.</span></span>

- <span data-ttu-id="20979-117">Microsoft Teams は、組織内で採用および使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="20979-117">Microsoft Teams should be adopted and used inside the organization.</span></span>

- <span data-ttu-id="20979-118">組織は、2018 年 11 月以降のバージョンのエピスを使用している必要があります。</span><span class="sxs-lookup"><span data-stu-id="20979-118">Organizations must have with Epic version November 2018 or later.</span></span>

- <span data-ttu-id="20979-119">システムは、すべてのソフトウェアと [ブラウザーの前提条件を満たす必要があります](https://docs.microsoft.com/microsoftteams/hardware-requirements-for-the-teams-app)。</span><span class="sxs-lookup"><span data-stu-id="20979-119">Your systems must meet all [software and browser prerequisites](https://docs.microsoft.com/microsoftteams/hardware-requirements-for-the-teams-app).</span></span>

<span data-ttu-id="20979-120">組織内の次のユーザーからの情報も必要です。</span><span class="sxs-lookup"><span data-stu-id="20979-120">You’ll also need information from the following people in your organization:</span></span>

- <span data-ttu-id="20979-121">Microsoft 365 管理者</span><span class="sxs-lookup"><span data-stu-id="20979-121">Microsoft 365 administrator</span></span>

- <span data-ttu-id="20979-122">壮大な顧客アナリスト</span><span class="sxs-lookup"><span data-stu-id="20979-122">Epic customer analyst</span></span>

> [!Note]
> <span data-ttu-id="20979-123">壮大なテクニカル スペシャリストに依頼して、エEpic-Microsoftマーケットプレースで利用可能な Teams Telehealth Integration Guide の機能を提供してください。</span><span class="sxs-lookup"><span data-stu-id="20979-123">Request your Epic technical specialist to provide the Epic-Microsoft Teams Telehealth Integration Guide available in the Epic marketplace.</span></span>

## <a name="connector-setup"></a><span data-ttu-id="20979-124">コネクタのセットアップ</span><span class="sxs-lookup"><span data-stu-id="20979-124">Connector setup</span></span>

<span data-ttu-id="20979-125">コネクタのセットアップでは、次の操作が必要です。</span><span class="sxs-lookup"><span data-stu-id="20979-125">The connector setup requires that you:</span></span>

- [<span data-ttu-id="20979-126">EHR コネクタ構成ポータルを起動する</span><span class="sxs-lookup"><span data-stu-id="20979-126">Launch the EHR Connector configuration portal</span></span>](ehr-admin.md#launch-the-ehr-connector-configuration-portal)
- [<span data-ttu-id="20979-127">構成情報</span><span class="sxs-lookup"><span data-stu-id="20979-127">Configuration information</span></span>](ehr-admin.md#configuration-information)
- [<span data-ttu-id="20979-128">構成を承認または表示する</span><span class="sxs-lookup"><span data-stu-id="20979-128">Approve or view configuration</span></span>](ehr-admin.md#approve-or-view-configuration)
- [<span data-ttu-id="20979-129">構成を確認して完了する</span><span class="sxs-lookup"><span data-stu-id="20979-129">Review and finish the configuration</span></span>](ehr-admin.md#review-and-finish-the-configuration)

### <a name="launch-the-ehr-connector-configuration-portal"></a>[<span data-ttu-id="20979-130">EHR コネクタ構成ポータルを起動する</span><span class="sxs-lookup"><span data-stu-id="20979-130">Launch the EHR Connector configuration portal</span></span>](#launch-the-ehr-connector-configuration-portal)

<span data-ttu-id="20979-131">Microsoft Teams で仮想訪問を開始するための医療組織の構成は、EHR Connector 構成ポータルを起動して開始します。</span><span class="sxs-lookup"><span data-stu-id="20979-131">Configuring your healthcare organization to launch virtual visits with Microsoft Teams starts by launching the EHR Connector configuration portal.</span></span> <span data-ttu-id="20979-132">統合をテストするために、1 つ以上の組織を構成します。</span><span class="sxs-lookup"><span data-stu-id="20979-132">You configure a single or multiple organizations to test the integration.</span></span> <span data-ttu-id="20979-133">構成ポータルでテストと実稼働の URL を構成します。</span><span class="sxs-lookup"><span data-stu-id="20979-133">Configure the test and production URL in the configuration portal.</span></span> <span data-ttu-id="20979-134">実稼働環境に移行する前に、エピスのテスト環境から統合をテストします。</span><span class="sxs-lookup"><span data-stu-id="20979-134">Test the integration from Epic’s test environment before moving to production.</span></span>
  
- <span data-ttu-id="20979-135">EHR コネクタ構成 URL: [https://ehrconnector.teams.microsoft.com](https://ehrconnector.teams.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="20979-135">EHR connector configuration URL: [https://ehrconnector.teams.microsoft.com](https://ehrconnector.teams.microsoft.com)</span></span>

<span data-ttu-id="20979-136">組織の Microsoft 365 管理者および壮大な顧客アナリストは、構成ポータルの情報と統合の手順を完了する必要があります。</span><span class="sxs-lookup"><span data-stu-id="20979-136">The Microsoft 365 admin and Epic customer analyst from your organization must complete the information and integration steps in the configuration portal.</span></span> <span data-ttu-id="20979-137">壮大な構成手順については、組織に割り当てられているエピスの技術専門リソースにお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="20979-137">For Epic configuration steps, contact the Epic technical specialist resource assigned to your organization.</span></span>

### <a name="configuration-information"></a>[<span data-ttu-id="20979-138">構成情報</span><span class="sxs-lookup"><span data-stu-id="20979-138">Configuration information</span></span>](#configuration-information)

<span data-ttu-id="20979-139">この手順は **、Microsoft 365 管理者が行います**。</span><span class="sxs-lookup"><span data-stu-id="20979-139">This step is to be completed by the **Microsoft 365 administrator**.</span></span> <span data-ttu-id="20979-140">Microsoft 365 管理者は、コネクタ構成ポータルを起動し、Microsoft 資格情報でサインインして構成プロセスを開始する必要があります。</span><span class="sxs-lookup"><span data-stu-id="20979-140">The Microsoft 365 administrator must launch the connector configuration portal and sign in with Microsoft credentials to start the configuration process.</span></span>

<span data-ttu-id="20979-141">この手順を完了するには、Microsoft 365 管理者が、有効なファースト Health 相互運用性リソース (FHIR) ベース URL を、エピスの技術専門家と、構成を承認するエピスの顧客アナリストのユーザー名を受け取る必要があります。</span><span class="sxs-lookup"><span data-stu-id="20979-141">To complete this step, the Microsoft 365 administrator must receive a valid Fast Health Interoperability Resources (FHIR) base URL from your Epic technical specialist and the username of the Epic customer analyst who will be approving the configuration.</span></span> <span data-ttu-id="20979-142">Microsoft 365 管理者は、コネクタ構成ページを起動し、Microsoft 資格情報でサインインして構成プロセスを開始する必要があります。</span><span class="sxs-lookup"><span data-stu-id="20979-142">The Microsoft 365 administrator must launch the connector configuration page and sign in with Microsoft credentials to start the configuration process.</span></span>

- <span data-ttu-id="20979-143">FHIR ベース URL は、サーバー FHIR API エンドポイントに対応する静的アドレスです。</span><span class="sxs-lookup"><span data-stu-id="20979-143">The FHIR base URL is a static address corresponding to your server FHIR API endpoint.</span></span> <span data-ttu-id="20979-144">URL の例 `https://lamnahealthcare.org/fihr/auth/connect-ocurprd-oauth/api/FHDST` は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="20979-144">An example URL is `https://lamnahealthcare.org/fihr/auth/connect-ocurprd-oauth/api/FHDST`.</span></span>

- <span data-ttu-id="20979-145">構成承認者の名前は、次の手順で構成の承認を担当する、壮大な顧客アナリストの名前です。</span><span class="sxs-lookup"><span data-stu-id="20979-145">Configuration approver name is the name of the Epic customer analyst who will be responsible for approving the configuration in the next step.</span></span> <span data-ttu-id="20979-146">エピスの顧客アナリストは、エピスへのサインイン アクセス権を持つ組織内のユーザーです。</span><span class="sxs-lookup"><span data-stu-id="20979-146">The Epic customer analyst is a person in your organization with signin access to Epic.</span></span>

  ![構成承認者の名前は、EHR コネクタの一覧から選択されます。](../../media/teams-ehr-connector.png)

### <a name="approve-or-view-configuration"></a>[<span data-ttu-id="20979-148">構成を承認または表示する</span><span class="sxs-lookup"><span data-stu-id="20979-148">Approve or view configuration</span></span>](#approve-or-view-configuration)

<span data-ttu-id="20979-149">承認者として追加された医療組織の壮大な顧客アナリストは、Microsoft 365 の資格情報を使用してサインインするために、前の手順と同じ EHR Connector URL を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="20979-149">The Epic customer analyst for your healthcare organization who was added as an approver must now use the same EHR Connector URL from the previous step to sign in using their Microsoft 365 credentials.</span></span> <span data-ttu-id="20979-150">検証が成功すると、承認者は、エピカル組織を検証するために、エピカルの資格情報を使用してサインインを求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="20979-150">After successful validation, the approver is going to be asked to sign in using their Epic credentials to validate the Epic organization.</span></span>

> [!Note]
> <span data-ttu-id="20979-151">組織内の Microsoft 365 管理者と壮大な顧客アナリストは、同じ人物である可能性があります。</span><span class="sxs-lookup"><span data-stu-id="20979-151">The Microsoft 365 admin and Epic customer analyst in your organization can be the same person.</span></span> <span data-ttu-id="20979-152">その場合は、独自のユーザー名を承認者として追加します。</span><span class="sxs-lookup"><span data-stu-id="20979-152">In that case, add your own username as approver.</span></span> <span data-ttu-id="20979-153">アクセスを検証するには、引き続きエピスにサインインする必要があります。</span><span class="sxs-lookup"><span data-stu-id="20979-153">You'll still need to sign in to Epic to validate your access.</span></span> <span data-ttu-id="20979-154">エピカル サインインは、FHIR ベース URL の検証にのみ使用されます。</span><span class="sxs-lookup"><span data-stu-id="20979-154">The Epic sign in is only used to validate your FHIR base URL.</span></span> <span data-ttu-id="20979-155">Microsoft は、このサインインで資格情報を保存したり、EHR データにアクセスしたりは行ないます。</span><span class="sxs-lookup"><span data-stu-id="20979-155">Microsoft won't store credentials or access EHR data with this sign in.</span></span>

  ![資格情報の構成を確認して承認します。](../../media/approve-view-configuration.png)

<span data-ttu-id="20979-157">壮大なサインインが成功した後、壮大な顧客アナリストが **構成を** 承認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="20979-157">After a successful Epic sign in, the Epic customer analyst **must** approve the configuration.</span></span> <span data-ttu-id="20979-158">構成が正しく設定されていない場合、Microsoft 365 管理者は、Microsoft EHR コネクタ ポータルにもう一度サインインして、元の構成を変更できます。</span><span class="sxs-lookup"><span data-stu-id="20979-158">If the configuration isn't correct, the Microsoft 365 admin will have the ability to modify the original configurations by signing in to the Microsoft EHR connector portal again.</span></span> 

![EHR コネクタが構成されていることを確認し、構成を変更するオプションを選択します。](../../media/ehc-approve-3.png)

### <a name="review-and-finish-the-configuration"></a>[<span data-ttu-id="20979-160">構成を確認して完了する</span><span class="sxs-lookup"><span data-stu-id="20979-160">Review and finish the configuration</span></span>](#review-and-finish-the-configuration)

<span data-ttu-id="20979-161">構成情報が壮大な管理者によって承認されると、患者とプロバイダーの立ち上げに関する統合レコードが表示されます。</span><span class="sxs-lookup"><span data-stu-id="20979-161">When the configuration information is approved by the Epic administrator, you'll be presented with integration records for patient and provider launch.</span></span> <span data-ttu-id="20979-162">これらのレコードは、壮大な仮想訪問構成を完了するために必要です。</span><span class="sxs-lookup"><span data-stu-id="20979-162">These records are necessary to complete the virtual visit configuration in Epic.</span></span> <span data-ttu-id="20979-163">詳細については、Epic-Microsoft Teams Telehealth Integration ガイドを参照してください。</span><span class="sxs-lookup"><span data-stu-id="20979-163">Refer to the Epic-Microsoft Teams Telehealth Integration guide for more details.</span></span>

> [!Note]  
> <span data-ttu-id="20979-164">Microsoft 365 または壮大な顧客アナリストは、いつでも構成ポータルにサインインして統合レコードを表示し、必要に応じて組織の構成を変更できます。</span><span class="sxs-lookup"><span data-stu-id="20979-164">At any time the Microsoft 365 or Epic customer analyst can sign in to the configuration portal to view integration records and modify organization configuration, if needed.</span></span>

![統合情報が表示されます。](../../media/finish-configuration.png)

> [!Note]
> <span data-ttu-id="20979-166">承認プロセスは、以前に Microsoft 管理者によって構成された FHIR URL ごとに、壮大な顧客アナリストによって完了する必要があります。</span><span class="sxs-lookup"><span data-stu-id="20979-166">The approval process must be completed by the Epic customer analyst for every FHIR URL configured by the Microsoft admin before.</span></span>

![構成情報が承認されます。](../../media/approve-configuration-2.png)

## <a name="launch-teams-virtual-visits"></a><span data-ttu-id="20979-168">Teams の仮想アクセスを開始する</span><span class="sxs-lookup"><span data-stu-id="20979-168">Launch Teams virtual visits</span></span>

<span data-ttu-id="20979-169">EHR Connector の手順と壮大な構成が完了すると、組織は Microsoft Teams でのビデオアクセスをサポートする準備が整います。</span><span class="sxs-lookup"><span data-stu-id="20979-169">After completing the EHR Connector steps and Epic configuration, your organization is ready to support video visits with Microsoft Teams.</span></span>

### <a name="virtual-visit-prerequisites"></a><span data-ttu-id="20979-170">仮想アクセスの前提条件</span><span class="sxs-lookup"><span data-stu-id="20979-170">Virtual visit prerequisites</span></span>

- <span data-ttu-id="20979-171">システムは、すべてのソフトウェアと [ブラウザーの前提条件を満たす必要があります](https://docs.microsoft.com/microsoftteams/hardware-requirements-for-the-teams-app)。</span><span class="sxs-lookup"><span data-stu-id="20979-171">Your systems must meet all [software and browser prerequisites](https://docs.microsoft.com/microsoftteams/hardware-requirements-for-the-teams-app).</span></span>

- <span data-ttu-id="20979-172">医療組織は、エピスの組織と Microsoft 365 組織の間のセットアップを完了している必要があります。</span><span class="sxs-lookup"><span data-stu-id="20979-172">Healthcare organization must have completed the setup between the Epic organization and Microsoft 365 organization.</span></span>

### <a name="provider-experience"></a><span data-ttu-id="20979-173">プロバイダーエクスペリエンス</span><span class="sxs-lookup"><span data-stu-id="20979-173">Provider experience</span></span>

<span data-ttu-id="20979-174">組織の医療プロバイダーは、エピクト プロバイダー アプリケーション (Hyperspace、Haグループ、Canto) から Microsoft Teams を使用して仮想訪問に参加することもできます。</span><span class="sxs-lookup"><span data-stu-id="20979-174">Healthcare providers from your organization can also join virtual visits with Microsoft Teams from their Epic provider applications (Hyperspace, Haiku, Canto).</span></span> <span data-ttu-id="20979-175">[ **仮想アクセスの開始]** ボタンがプロバイダー フローに埋め込まれている。</span><span class="sxs-lookup"><span data-stu-id="20979-175">The **Begin virtual visit** button is embedded in the provider flow.</span></span>

<span data-ttu-id="20979-176">プロバイダーエクスペリエンスの主な機能:</span><span class="sxs-lookup"><span data-stu-id="20979-176">Key features of the provider experience:</span></span>

- <span data-ttu-id="20979-177">プロバイダーは、サポートされているブラウザーまたは Microsoft Teams アプリケーションを使用して仮想アクセスに参加できます。</span><span class="sxs-lookup"><span data-stu-id="20979-177">Providers can join virtual visits using supported browsers or the Microsoft Teams application.</span></span>

- <span data-ttu-id="20979-178">プロバイダーは、仮想アクセスに初めて参加する際に、Microsoft 365 アカウントで 1 回のサインインを行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="20979-178">Providers must do a one-time sign-in with their Microsoft 365 account when joining a virtual visit for the first time.</span></span>

- <span data-ttu-id="20979-179">1 回のサインイン後、プロバイダーは Microsoft Teams の仮想予定に直接アクセスします。</span><span class="sxs-lookup"><span data-stu-id="20979-179">After the one-time sign-in, the provider will be taken straight to the virtual appointment in Microsoft Teams.</span></span> <span data-ttu-id="20979-180">(プロバイダーは Microsoft Teams にサインインしている必要があります)。</span><span class="sxs-lookup"><span data-stu-id="20979-180">(Provider must be signed-in to Microsoft Teams).</span></span>

- <span data-ttu-id="20979-181">プロバイダーは、特定の予定の接続と切断の参加者の更新をリアルタイムで確認できます。</span><span class="sxs-lookup"><span data-stu-id="20979-181">Provider can see real-time updates of participants connect and disconnect for a given appointment.</span></span> <span data-ttu-id="20979-182">プロバイダーは、患者がいつ仮想訪問に接続されたのか確認できます。</span><span class="sxs-lookup"><span data-stu-id="20979-182">The provider can see when the patient is connected to a virtual visit.</span></span>

  ![患者との仮想訪問のプロバイダーエクスペリエンス](../../media/ehc-provider-experience-6.png)

### <a name="patient-experience"></a><span data-ttu-id="20979-184">患者の経験</span><span class="sxs-lookup"><span data-stu-id="20979-184">Patient experience</span></span>

<span data-ttu-id="20979-185">このコネクタは、MyChart Web とモバイルを介して仮想訪問に参加する患者をサポートします。</span><span class="sxs-lookup"><span data-stu-id="20979-185">The connector supports patients joining virtual visits through MyChart web and mobile.</span></span> <span data-ttu-id="20979-186">予約の時点で、患者は [仮想訪問の開始] ボタンを使用して、MyChart から **仮想訪問を開始** できます。</span><span class="sxs-lookup"><span data-stu-id="20979-186">At the time of the appointment, patients can start a virtual visit from MyChart using the **Begin virtual visit** button.</span></span>

<span data-ttu-id="20979-187">患者の経験の主な機能:</span><span class="sxs-lookup"><span data-stu-id="20979-187">Key features of the patient experience:</span></span>

- <span data-ttu-id="20979-188">患者は、アプリをインストールすることなく、デスクトップとモバイルの最新の Web ブラウザーから仮想アクセスに参加できます。</span><span class="sxs-lookup"><span data-stu-id="20979-188">Patients can join virtual visits from modern web browsers on desktop and mobile without app installation.</span></span>

- <span data-ttu-id="20979-189">患者は 1 回のクリックで仮想訪問に参加できます。他のアカウントやサインインは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="20979-189">Patients can join virtual visits with a single click and there is no other account or sign-in required.</span></span>

- <span data-ttu-id="20979-190">患者は、Microsoft アカウントを作成したり、仮想アクセスを開始するためにサインインしたりする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="20979-190">Patients aren't required to create a Microsoft account or sign in to launch a virtual visit.</span></span>

- <span data-ttu-id="20979-191">患者は、医療プロバイダーが予定に参加し、仮想訪問を認めるまでロビーに置かれる予定です。</span><span class="sxs-lookup"><span data-stu-id="20979-191">Patients will be placed in a lobby until the healthcare provider joins the appointment and admits them to the virtual visit.</span></span>

- <span data-ttu-id="20979-192">仮想訪問に参加する前に、ロビーでビデオとマイクのテストを利用できます。</span><span class="sxs-lookup"><span data-stu-id="20979-192">Testing of the video and microphone is available in the lobby before joining the virtual visit.</span></span>

  ![仮想訪問の患者体験](../../media/ehc-virtual-visit-5.png)

> [!Note]
> <span data-ttu-id="20979-194">エピクト、MyChart、Ha、Canto は、エピクト システム社の商標です。</span><span class="sxs-lookup"><span data-stu-id="20979-194">Epic, MyChart, Haiku, and Canto are trademarks of Epic Systems Corporation.</span></span>

### <a name="privacy-and-location-of-data"></a><span data-ttu-id="20979-195">データのプライバシーと場所</span><span class="sxs-lookup"><span data-stu-id="20979-195">Privacy and location of data</span></span>

<span data-ttu-id="20979-196">Teams を EHR システムに統合すると、統合中に使用および保存されるデータの量と仮想訪問フローが最適化されます。</span><span class="sxs-lookup"><span data-stu-id="20979-196">Teams integration into EHR systems optimizes the amount of data being used and stored during integration and virtual visit flows.</span></span> <span data-ttu-id="20979-197">このソリューションは、Teams のプライバシーとデータ管理に関する全体的な原則と、Teams のプライバシーに関するガイドラインに従います。</span><span class="sxs-lookup"><span data-stu-id="20979-197">The solution follows the overall Teams privacy and data management principles and guidelines outlined in Teams Privacy.</span></span>

<span data-ttu-id="20979-198">Microsoft Teams EHR コネクタは、識別可能な個人データや、患者や医療プロバイダーの医療記録を EHR システムから保存または転送したりできません。</span><span class="sxs-lookup"><span data-stu-id="20979-198">The Microsoft Teams EHR connector doesn't store nor transfer any identifiable personal data or any health records of patients or healthcare providers from the EHR system.</span></span> <span data-ttu-id="20979-199">EHR コネクタによって保存される唯一のデータは、Teams 会議のセットアップ中に使用される EHR ユーザーの一意の ID です。</span><span class="sxs-lookup"><span data-stu-id="20979-199">The only data that is stored by the EHR connector is the EHR user’s unique ID, which is used during Teams meeting setup.</span></span> <span data-ttu-id="20979-200">EHR ユーザーの一意の ID は [、Microsoft 365](https://docs.microsoft.com/microsoft-365/enterprise/o365-data-locations?view=o365-worldwide#data-center-geographies)の顧客データが保存される場所で説明されている 3 つの地理的領域の 1 つに格納されます。</span><span class="sxs-lookup"><span data-stu-id="20979-200">The EHR user’s unique ID is stored in one of the three geographic regions described in [Where your Microsoft 365 customer data is stored](https://docs.microsoft.com/microsoft-365/enterprise/o365-data-locations?view=o365-worldwide#data-center-geographies).</span></span> <span data-ttu-id="20979-201">会議の参加者によって Teams に入力されたチャット、レコーディング、その他のデータはすべて、既存のストレージ ポリシーに従って保存されます。</span><span class="sxs-lookup"><span data-stu-id="20979-201">All chat, recordings, and other data entered into Teams by the meeting participants are stored according to existing storage policies.</span></span> <span data-ttu-id="20979-202">Microsoft Teams のデータの場所に関する詳細については、Teams のデータの場所 [にアクセスしてください](https://docs.microsoft.com/microsoftteams/location-of-data-in-teams)。</span><span class="sxs-lookup"><span data-stu-id="20979-202">If you want to learn more information on the location of data in Microsoft Teams, visit [Locations of data in Teams](https://docs.microsoft.com/microsoftteams/location-of-data-in-teams).</span></span>
