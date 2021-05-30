---
title: 仮想アクセスのための Teams
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
- m365solution-healthcare
- m365solution-scenario
appliesto:
- Microsoft Teams
ms.reviewer: ansantam
description: Microsoft Teams を使用して仮想アクセス システムをセットアップする
ms.openlocfilehash: 9c002a90cd91014ca4887386ca5834a4b5b41266
ms.sourcegitcommit: d73dc8505a5cc5af29635a50cbbf0f25bbb17eac
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/29/2021
ms.locfileid: "52705251"
---
# <a name="virtual-visits-with-teams---integration-into-ehr"></a><span data-ttu-id="1624e-103">Teams での仮想アクセス - EHR への統合</span><span class="sxs-lookup"><span data-stu-id="1624e-103">Virtual visits with Teams - Integration into EHR</span></span>

<span data-ttu-id="1624e-104">Microsoft Teams電子健康記録 (EHR) コネクタを使用すると、医師は EHR システムから直接、Teams で仮想患者の訪問や別のプロバイダーとの相談を簡単に開始できます。</span><span class="sxs-lookup"><span data-stu-id="1624e-104">Microsoft Teams Electronic Health Record (EHR) connector makes it easy for clinicians to launch a virtual patient visit or consultation with another provider in Teams directly from the EHR system.</span></span> <span data-ttu-id="1624e-105">Microsoft 365 クラウド上に構築された Microsoft Teams は、HIPAA、HITECH 認定などへの準拠をサポートする単一のハブで、チャット、ビデオ、音声、およびヘルスケア ツールとのシンプルで安全なコラボレーションとコミュニケーションを可能にします。</span><span class="sxs-lookup"><span data-stu-id="1624e-105">Built on the Microsoft 365 cloud, Microsoft Teams enables simple, secure collaboration and communication with chat, video, voice, and healthcare tools in a single hub that supports compliance with HIPAA, HITECH certification, and more.</span></span>
<span data-ttu-id="1624e-106">Teams のコミュニケーションおよびコラボレーション プラットフォームにより、臨床医は断片化されたシステムの乱雑さを簡単に切り抜けることができるため、可能な限り最善のケアを提供するために時間を費やすことができます。</span><span class="sxs-lookup"><span data-stu-id="1624e-106">The communication and collaboration platform of Teams makes it easy for clinicians to cut through the clutter of fragmented systems so they can spend time providing the best possible care.</span></span> <span data-ttu-id="1624e-107">Microsoft Teams電子正常性レコード (EHR) コネクタでは、次の機能を使用できます。</span><span class="sxs-lookup"><span data-stu-id="1624e-107">Microsoft Teams Electronic Health Record (EHR) connector can:</span></span>

- <span data-ttu-id="1624e-108">統合Teamsワークフローを使用して、プロバイダー EHR システムから仮想アクセスを開始します。</span><span class="sxs-lookup"><span data-stu-id="1624e-108">Launch Teams virtual visits from the provider EHR system with an integrated clinical workflow.</span></span>
- <span data-ttu-id="1624e-109">患者が患者ポータル内Teams仮想訪問に参加できます。</span><span class="sxs-lookup"><span data-stu-id="1624e-109">Enable patients to join Teams virtual visits from within the patient portal.</span></span>
- <span data-ttu-id="1624e-110">出席者が接続と切断を行い、自動監査と記録Teamsを有効にした場合に記録する仮想アクセスに関するメタデータを EHR システムに書き戻します。</span><span class="sxs-lookup"><span data-stu-id="1624e-110">Write metadata back to the EHR system regarding Teams virtual visits to record when attendees connect and disconnect and enable automatic auditing and record keeping.</span></span>

  <span data-ttu-id="1624e-111">EHR ポータルから仮想アクセスを管理する方法のビデオをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="1624e-111">Watch the video of How to manage virtual visits from the EHR portal.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4HAtn]

## <a name="before-you-begin"></a><span data-ttu-id="1624e-112">はじめに</span><span class="sxs-lookup"><span data-stu-id="1624e-112">Before you begin</span></span>

<span data-ttu-id="1624e-113">EHR コネクタを統合する前に、次の前提条件があることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1624e-113">You’ll need to make sure you have the following prerequisites before you can integrate the EHR connector:</span></span>

- <span data-ttu-id="1624e-114">[Epic の App Orchard マーケットプレイス](https://apporchard.epic.com/Gallery?id=6153)で Microsoft Teams アプリを使用するためのアクセス。</span><span class="sxs-lookup"><span data-stu-id="1624e-114">Access to use to the Microsoft Teams app in [Epic’s App Orchard marketplace](https://apporchard.epic.com/Gallery?id=6153).</span></span>

- <span data-ttu-id="1624e-115">Microsoft Cloud for Healthcare のアクティブなサブスクリプション、または EHR コネクタMicrosoft Teamsプランへのサブスクリプション (実稼働テスト中にのみ適用)。</span><span class="sxs-lookup"><span data-stu-id="1624e-115">Active subscription to Microsoft Cloud for Healthcare or subscription to Microsoft Teams EHR connector standalone offer (only enforced during production testing).</span></span>

- <span data-ttu-id="1624e-116">ユーザーは Microsoft Teams 会議が含まれている Microsoft 365 または Office 365 の適切なライセンスを所有している必要があります。</span><span class="sxs-lookup"><span data-stu-id="1624e-116">Users must have an appropriate Microsoft 365 or Office 365 license that includes Microsoft Teams meetings.</span></span>

- <span data-ttu-id="1624e-117">Microsoft Teams は、組織内で採用および使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1624e-117">Microsoft Teams should be adopted and used inside the organization.</span></span>

- <span data-ttu-id="1624e-118">組織は、 Epic の 2018 年 11 月以降のバージョンを持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="1624e-118">Organizations must have with Epic version November 2018 or later.</span></span>

- <span data-ttu-id="1624e-119">システムは、すべての[ソフトウェアとブラウザーの前提条件](../../hardware-requirements-for-the-teams-app.md)を満たす必要があります。</span><span class="sxs-lookup"><span data-stu-id="1624e-119">Your systems must meet all [software and browser prerequisites](../../hardware-requirements-for-the-teams-app.md).</span></span>

<span data-ttu-id="1624e-120">また、組織内の次のユーザーからの情報も必要になります。</span><span class="sxs-lookup"><span data-stu-id="1624e-120">You’ll also need information from the following people in your organization:</span></span>

- <span data-ttu-id="1624e-121">Microsoft 365 管理者</span><span class="sxs-lookup"><span data-stu-id="1624e-121">Microsoft 365 administrator</span></span>

- <span data-ttu-id="1624e-122">Epic 顧客アナリスト</span><span class="sxs-lookup"><span data-stu-id="1624e-122">Epic customer analyst</span></span>

> [!Note]
> <span data-ttu-id="1624e-123">「[Epic-Microsoft Teams Telehealth Integration ガイド](https://galaxy.epic.com/Search/GetFile?Url=1!68!100!100100357)」を Epic の技術専門家と一緒にご確認ください。</span><span class="sxs-lookup"><span data-stu-id="1624e-123">Review the [Epic-Microsoft Teams Telehealth Integration Guide](https://galaxy.epic.com/Search/GetFile?Url=1!68!100!100100357) with your Epic technical specialist.</span></span> <span data-ttu-id="1624e-124">前提条件がすべて完了している必要があります。</span><span class="sxs-lookup"><span data-stu-id="1624e-124">Make sure that all pre-requisites are completed.</span></span> 

## <a name="connector-setup"></a><span data-ttu-id="1624e-125">コネクタの設定</span><span class="sxs-lookup"><span data-stu-id="1624e-125">Connector setup</span></span>

<span data-ttu-id="1624e-126">コネクタの設定には、次のことが必要です。</span><span class="sxs-lookup"><span data-stu-id="1624e-126">The connector setup requires that you:</span></span>

- [<span data-ttu-id="1624e-127">EHR コネクタ構成ポータルを起動する</span><span class="sxs-lookup"><span data-stu-id="1624e-127">Launch the EHR connector configuration portal</span></span>](ehr-admin.md#launch-the-ehr-connector-configuration-portal)
- [<span data-ttu-id="1624e-128">構成情報</span><span class="sxs-lookup"><span data-stu-id="1624e-128">Configuration information</span></span>](ehr-admin.md#configuration-information)
- [<span data-ttu-id="1624e-129">構成を承認または表示する</span><span class="sxs-lookup"><span data-stu-id="1624e-129">Approve or view configuration</span></span>](ehr-admin.md#approve-or-view-configuration)
- [<span data-ttu-id="1624e-130">構成を確認して終了する</span><span class="sxs-lookup"><span data-stu-id="1624e-130">Review and finish the configuration</span></span>](ehr-admin.md#review-and-finish-the-configuration)

### <a name="launch-the-ehr-connector-configuration-portal"></a>[<span data-ttu-id="1624e-131">EHR コネクタ構成ポータルを起動する</span><span class="sxs-lookup"><span data-stu-id="1624e-131">Launch the EHR connector configuration portal</span></span>](#launch-the-ehr-connector-configuration-portal)

<span data-ttu-id="1624e-132">EHR コネクタ構成ポータルを起動して、Microsoft Teamsを起動する医療組織を構成します。</span><span class="sxs-lookup"><span data-stu-id="1624e-132">Configuring your healthcare organization to launch virtual visits with Microsoft Teams starts by launching the EHR connector configuration portal.</span></span> <span data-ttu-id="1624e-133">統合をテストするために、単一または複数の組織を構成します。</span><span class="sxs-lookup"><span data-stu-id="1624e-133">You configure a single or multiple organizations to test the integration.</span></span> <span data-ttu-id="1624e-134">構成ポータルでテスト URL と本番 URL を構成します。</span><span class="sxs-lookup"><span data-stu-id="1624e-134">Configure the test and production URL in the configuration portal.</span></span> <span data-ttu-id="1624e-135">本番環境に移行する前に、Epic のテスト環境から統合をテストします。</span><span class="sxs-lookup"><span data-stu-id="1624e-135">Test the integration from Epic’s test environment before moving to production.</span></span>
  
- <span data-ttu-id="1624e-136">EHR コネクタ構成 URL: [https://ehrconnector.teams.microsoft.com](https://ehrconnector.teams.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="1624e-136">EHR connector configuration URL: [https://ehrconnector.teams.microsoft.com](https://ehrconnector.teams.microsoft.com)</span></span>

<span data-ttu-id="1624e-137">組織の Microsoft 365 管理者と Epic 顧客アナリストは、構成ポータルで情報と統合の手順を完了する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1624e-137">The Microsoft 365 admin and Epic customer analyst from your organization must complete the information and integration steps in the configuration portal.</span></span> <span data-ttu-id="1624e-138">Epic の構成手順については、組織に割り当てられている Epic テクニカル スペシャリスト リソースにアクセスしてください。</span><span class="sxs-lookup"><span data-stu-id="1624e-138">For Epic configuration steps, contact the Epic technical specialist resource assigned to your organization.</span></span>

### <a name="configuration-information"></a>[<span data-ttu-id="1624e-139">構成情報</span><span class="sxs-lookup"><span data-stu-id="1624e-139">Configuration information</span></span>](#configuration-information)

<span data-ttu-id="1624e-140">この手順は、**Microsoft 365 管理者** が実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1624e-140">This step is to be completed by the **Microsoft 365 administrator**.</span></span> <span data-ttu-id="1624e-141">Microsoft 365 管理者は、コネクタ構成ポータルを起動し、Microsoft 資格情報を使用してサインインし、構成プロセスを開始する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1624e-141">The Microsoft 365 administrator must launch the connector configuration portal and sign in with Microsoft credentials to start the configuration process.</span></span>

<span data-ttu-id="1624e-142">この手順を完了するには、Microsoft 365 管理者は、Epic テクニカル スペシャリストから有効な Fast Health Interoperability Resources (FHIR) ベース URL と、構成を承認する Epic 顧客アナリストのユーザー名を受け取る必要があります。</span><span class="sxs-lookup"><span data-stu-id="1624e-142">To complete this step, the Microsoft 365 administrator must receive a valid Fast Health Interoperability Resources (FHIR) base URL from your Epic technical specialist and the username of the Epic customer analyst who will be approving the configuration.</span></span> <span data-ttu-id="1624e-143">Microsoft 365 管理者は、コネクタ構成ページを起動し、Microsoft 資格情報を使用してサインインし、構成プロセスを開始する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1624e-143">The Microsoft 365 administrator must launch the connector configuration page and sign in with Microsoft credentials to start the configuration process.</span></span>

- <span data-ttu-id="1624e-144">FHIR ベース URL は、サーバーの FHIR API エンドポイントに対応する静的アドレスです。</span><span class="sxs-lookup"><span data-stu-id="1624e-144">The FHIR base URL is a static address corresponding to your server FHIR API endpoint.</span></span> <span data-ttu-id="1624e-145">URL の例は、`https://lamnahealthcare.org/fihr/auth/connect-ocurprd-oauth/api/FHDST` です。</span><span class="sxs-lookup"><span data-stu-id="1624e-145">An example URL is `https://lamnahealthcare.org/fihr/auth/connect-ocurprd-oauth/api/FHDST`.</span></span>

- <span data-ttu-id="1624e-146">構成承認者名は、次の手順で構成を承認する責任を負う Epic 顧客アナリストの名前です。</span><span class="sxs-lookup"><span data-stu-id="1624e-146">Configuration approver name is the name of the Epic customer analyst who will be responsible for approving the configuration in the next step.</span></span> <span data-ttu-id="1624e-147">Epic 顧客アナリストは、Epic にサインイン アクセスできる組織内のユーザーです。</span><span class="sxs-lookup"><span data-stu-id="1624e-147">The Epic customer analyst is a person in your organization with sign-in access to Epic.</span></span>

  ![構成承認者の名前は、EHR コネクタのリストから選択されます。](../../media/teams-ehr-connector.png)

### <a name="approve-or-view-configuration"></a>[<span data-ttu-id="1624e-149">構成を承認または表示する</span><span class="sxs-lookup"><span data-stu-id="1624e-149">Approve or view configuration</span></span>](#approve-or-view-configuration)

<span data-ttu-id="1624e-150">承認者として追加された医療組織のエピックカスタマー アナリストは、前の手順と同じ EHR コネクタ URL を使用して、Microsoft 365 資格情報を使用してサインインする必要があります。</span><span class="sxs-lookup"><span data-stu-id="1624e-150">The Epic customer analyst for your healthcare organization who was added as an approver must now use the same EHR connector URL from the previous step to sign in using their Microsoft 365 credentials.</span></span> <span data-ttu-id="1624e-151">検証が成功すると、承認者は Epic 資格情報を使用してサインインし、Epic 組織を検証するように求められます。</span><span class="sxs-lookup"><span data-stu-id="1624e-151">After successful validation, the approver is going to be asked to sign in using their Epic credentials to validate the Epic organization.</span></span>

> [!Note]
> <span data-ttu-id="1624e-152">組織内の Microsoft 365 管理者と Epic 顧客アナリストは同じ人物であることが可能です。</span><span class="sxs-lookup"><span data-stu-id="1624e-152">The Microsoft 365 admin and Epic customer analyst in your organization can be the same person.</span></span> <span data-ttu-id="1624e-153">その場合は、自分のユーザー名を承認者として追加してください。</span><span class="sxs-lookup"><span data-stu-id="1624e-153">In that case, add your own username as approver.</span></span> <span data-ttu-id="1624e-154">アクセスを検証するには、Epic にサインインする必要があります。</span><span class="sxs-lookup"><span data-stu-id="1624e-154">You'll still need to sign in to Epic to validate your access.</span></span> <span data-ttu-id="1624e-155">Epic サインインは、FHIR ベース URL を検証するためにのみ使用されます。</span><span class="sxs-lookup"><span data-stu-id="1624e-155">The Epic sign in is only used to validate your FHIR base URL.</span></span> <span data-ttu-id="1624e-156">Microsoft は、このサインインで資格情報を保存したり、EHR データにアクセスしたりすることはありません。</span><span class="sxs-lookup"><span data-stu-id="1624e-156">Microsoft won't store credentials or access EHR data with this sign in.</span></span>

  ![資格情報の構成を確認して承認します。](../../media/approve-view-configuration.png)

<span data-ttu-id="1624e-158">Epic サインインが成功したら、Epic 顧客アナリストは構成を承認する **必要があります**。</span><span class="sxs-lookup"><span data-stu-id="1624e-158">After a successful Epic sign in, the Epic customer analyst **must** approve the configuration.</span></span> <span data-ttu-id="1624e-159">構成が正しくない場合、Microsoft 365 管理者は、Microsoft EHR コネクタ ポータルに再度サインインすることにより、元の構成を変更できます。</span><span class="sxs-lookup"><span data-stu-id="1624e-159">If the configuration isn't correct, the Microsoft 365 admin will have the ability to modify the original configurations by signing in to the Microsoft EHR connector portal again.</span></span> 

![EHR コネクタが構成されていること、および構成を変更するオプションがあることを確認します。](../../media/ehc-approve-3.png)

### <a name="review-and-finish-the-configuration"></a>[<span data-ttu-id="1624e-161">構成を確認して終了する</span><span class="sxs-lookup"><span data-stu-id="1624e-161">Review and finish the configuration</span></span>](#review-and-finish-the-configuration)

<span data-ttu-id="1624e-162">構成情報が Epic 管理者によって承認されると、患者とプロバイダーの立ち上げに関する統合レコードが表示されます。</span><span class="sxs-lookup"><span data-stu-id="1624e-162">When the configuration information is approved by the Epic administrator, you'll be presented with integration records for patient and provider launch.</span></span> <span data-ttu-id="1624e-163">これらのレコードは、Epic で仮想アクセスの構成を完了するために必要です。</span><span class="sxs-lookup"><span data-stu-id="1624e-163">These records are necessary to complete the virtual visit configuration in Epic.</span></span> <span data-ttu-id="1624e-164">詳細については、Epic-Microsoft Teams Telehealth Integration ガイドを参照してください。</span><span class="sxs-lookup"><span data-stu-id="1624e-164">Refer to the Epic-Microsoft Teams Telehealth Integration guide for more details.</span></span>

> [!Note]  
> <span data-ttu-id="1624e-165">Microsoft 365 または Epic 顧客アナリストは、いつでも構成ポータルにサインインして、統合レコードを表示し、必要に応じて組織の構成を変更できます。</span><span class="sxs-lookup"><span data-stu-id="1624e-165">At any time the Microsoft 365 or Epic customer analyst can sign in to the configuration portal to view integration records and modify organization configuration, if needed.</span></span>

![統合情報が表示されます。](../../media/finish-configuration.png)

> [!Note]
> <span data-ttu-id="1624e-167">承認プロセスは、Microsoft 管理者が以前に構成したすべての FHIR URL について、Epic 顧客アナリストにより完了される必要があります。</span><span class="sxs-lookup"><span data-stu-id="1624e-167">The approval process must be completed by the Epic customer analyst for every FHIR URL configured by the Microsoft admin before.</span></span>

![構成情報が承認されます。](../../media/approve-configuration-2.png)

## <a name="launch-teams-virtual-visits"></a><span data-ttu-id="1624e-169">Teams の仮想アクセスを開始する</span><span class="sxs-lookup"><span data-stu-id="1624e-169">Launch Teams virtual visits</span></span>

<span data-ttu-id="1624e-170">EHR コネクタの手順とエピックの構成を完了すると、組織はビデオアクセスをサポートする準備が整Microsoft Teams。</span><span class="sxs-lookup"><span data-stu-id="1624e-170">After completing the EHR connector steps and Epic configuration, your organization is ready to support video visits with Microsoft Teams.</span></span>

### <a name="virtual-visit-prerequisites"></a><span data-ttu-id="1624e-171">仮想アクセスの前提条件</span><span class="sxs-lookup"><span data-stu-id="1624e-171">Virtual visit prerequisites</span></span>

- <span data-ttu-id="1624e-172">システムは、すべての[ソフトウェアとブラウザーの前提条件](../../hardware-requirements-for-the-teams-app.md)を満たす必要があります。</span><span class="sxs-lookup"><span data-stu-id="1624e-172">Your systems must meet all [software and browser prerequisites](../../hardware-requirements-for-the-teams-app.md).</span></span>

- <span data-ttu-id="1624e-173">ヘルスケア組織は、Epic 組織と Microsoft 365 組織の間のセットアップを完了している必要があります。</span><span class="sxs-lookup"><span data-stu-id="1624e-173">Healthcare organization must have completed the setup between the Epic organization and Microsoft 365 organization.</span></span>

### <a name="provider-experience"></a><span data-ttu-id="1624e-174">プロバイダー エクスペリエンス</span><span class="sxs-lookup"><span data-stu-id="1624e-174">Provider experience</span></span>

<span data-ttu-id="1624e-175">組織の医療提供者は、Epic プロバイダー アプリケーション (Hyperspace、Haiku、Canto) から Microsoft Teams を使用した仮想アクセスに参加することもできます。</span><span class="sxs-lookup"><span data-stu-id="1624e-175">Healthcare providers from your organization can also join virtual visits with Microsoft Teams from their Epic provider applications (Hyperspace, Haiku, Canto).</span></span> <span data-ttu-id="1624e-176">**[仮想アクセスの開始]** ボタンは、プロバイダー フローに組み込まれています。</span><span class="sxs-lookup"><span data-stu-id="1624e-176">The **Begin virtual visit** button is embedded in the provider flow.</span></span>

<span data-ttu-id="1624e-177">プロバイダー エクスペリエンスの主な機能:</span><span class="sxs-lookup"><span data-stu-id="1624e-177">Key features of the provider experience:</span></span>

- <span data-ttu-id="1624e-178">プロバイダーは、サポートされているブラウザーまたは Microsoft Teams アプリケーションを使用して仮想アクセスに参加できます。</span><span class="sxs-lookup"><span data-stu-id="1624e-178">Providers can join virtual visits using supported browsers or the Microsoft Teams application.</span></span>

- <span data-ttu-id="1624e-179">プロバイダーは、仮想アクセスに初めて参加するときに、Microsoft 365 アカウントで 1 回サインインする必要があります。</span><span class="sxs-lookup"><span data-stu-id="1624e-179">Providers must do a one-time sign-in with their Microsoft 365 account when joining a virtual visit for the first time.</span></span>

- <span data-ttu-id="1624e-p114">1 回のサインイン後、プロバイダーは Microsoft Teams の仮想予定に直接移動します。(プロバイダーは Microsoft Teams にサインインする必要があります)。</span><span class="sxs-lookup"><span data-stu-id="1624e-p114">After the one-time sign-in, the provider will be taken straight to the virtual appointment in Microsoft Teams. (Provider must be signed-in to Microsoft Teams).</span></span>

- <span data-ttu-id="1624e-182">プロバイダーは、与えられた予定に対し、参加者の接続と切断のリアルタイム更新を確認できます。</span><span class="sxs-lookup"><span data-stu-id="1624e-182">Provider can see real-time updates of participants connect and disconnect for a given appointment.</span></span> <span data-ttu-id="1624e-183">プロバイダーは、患者が仮想アクセスに接続されていることを確認できます。</span><span class="sxs-lookup"><span data-stu-id="1624e-183">The provider can see when the patient is connected to a virtual visit.</span></span>

  ![患者の仮想アクセスのプロバイダー エクスペリエンス](../../media/ehc-provider-experience-6.png)

### <a name="patient-experience"></a><span data-ttu-id="1624e-185">患者エクスペリエンス</span><span class="sxs-lookup"><span data-stu-id="1624e-185">Patient experience</span></span>

<span data-ttu-id="1624e-186">コネクタは、MyChart の Web とモバイルを通じて仮想アクセスに参加する患者をサポートします。</span><span class="sxs-lookup"><span data-stu-id="1624e-186">The connector supports patients joining virtual visits through MyChart web and mobile.</span></span> <span data-ttu-id="1624e-187">予約時に、患者は **[仮想アクセスの開始]** ボタンを使用して MyChart から仮想アクセスを開始できます。</span><span class="sxs-lookup"><span data-stu-id="1624e-187">At the time of the appointment, patients can start a virtual visit from MyChart using the **Begin virtual visit** button.</span></span>

<span data-ttu-id="1624e-188">患者エクスペリエンスの主な機能:</span><span class="sxs-lookup"><span data-stu-id="1624e-188">Key features of the patient experience:</span></span>

- <span data-ttu-id="1624e-189">患者は、アプリをインストールしなくても、デスクトップとモバイルの最新の Web ブラウザーから仮想アクセスに参加できます。</span><span class="sxs-lookup"><span data-stu-id="1624e-189">Patients can join virtual visits from modern web browsers on desktop and mobile without app installation.</span></span>

- <span data-ttu-id="1624e-190">患者はワンクリックで仮想アクセスに参加でき、他のアカウントやサインインは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="1624e-190">Patients can join virtual visits with a single click and there is no other account or sign-in required.</span></span>

- <span data-ttu-id="1624e-191">患者は、仮想アクセスを開始するために Microsoft アカウントを作成したりサインインしたりする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="1624e-191">Patients aren't required to create a Microsoft account or sign in to launch a virtual visit.</span></span>

- <span data-ttu-id="1624e-192">患者は、医療提供者が予約に参加し、仮想アクセスを許可するまでロビーに配置されます。</span><span class="sxs-lookup"><span data-stu-id="1624e-192">Patients will be placed in a lobby until the healthcare provider joins the appointment and admits them to the virtual visit.</span></span>

- <span data-ttu-id="1624e-193">ビデオとマイクのテストは、仮想アクセスに参加する前にロビーで利用できます。</span><span class="sxs-lookup"><span data-stu-id="1624e-193">Testing of the video and microphone is available in the lobby before joining the virtual visit.</span></span>

  ![仮想アクセスの患者エクスペリエンス](../../media/ehc-virtual-visit-5.png)

> [!Note]
> <span data-ttu-id="1624e-195">Epic、MyChart、Haiku、および Canto は、Epic Systems Corporation の商標です。</span><span class="sxs-lookup"><span data-stu-id="1624e-195">Epic, MyChart, Haiku, and Canto are trademarks of Epic Systems Corporation.</span></span>

### <a name="privacy-and-location-of-data"></a><span data-ttu-id="1624e-196">データのプライバシーと場所</span><span class="sxs-lookup"><span data-stu-id="1624e-196">Privacy and location of data</span></span>

<span data-ttu-id="1624e-197">Teams の EHR システムへの統合により、統合および仮想アクセス フロー中に使用および保存されるデータの量が最適化されます。</span><span class="sxs-lookup"><span data-stu-id="1624e-197">Teams integration into EHR systems optimizes the amount of data being used and stored during integration and virtual visit flows.</span></span> <span data-ttu-id="1624e-198">このソリューションは、Teams のプライバシーとデータ管理の原則、および Teams のプライバシーで概説されているガイドラインに従います。</span><span class="sxs-lookup"><span data-stu-id="1624e-198">The solution follows the overall Teams privacy and data management principles and guidelines outlined in Teams Privacy.</span></span>

<span data-ttu-id="1624e-199">Microsoft Teams EHR コネクタは、EHR システムから、識別可能な個人データや患者または医療提供者の健康記録を保存または転送しません。</span><span class="sxs-lookup"><span data-stu-id="1624e-199">The Microsoft Teams EHR connector doesn't store nor transfer any identifiable personal data or any health records of patients or healthcare providers from the EHR system.</span></span> <span data-ttu-id="1624e-200">EHR コネクタによって保存される唯一のデータは、EHR ユーザーの一意の ID であり、Teams 会議のセットアップ中に使用されます。</span><span class="sxs-lookup"><span data-stu-id="1624e-200">The only data that is stored by the EHR connector is the EHR user’s unique ID, which is used during Teams meeting setup.</span></span> <span data-ttu-id="1624e-201">EHR ユーザーの一意の ID は、「[Microsoft 365 の顧客データの保存場所](/microsoft-365/enterprise/o365-data-locations)」で説明されている 3 つの地理的地域のいずれかに保存されます。</span><span class="sxs-lookup"><span data-stu-id="1624e-201">The EHR user’s unique ID is stored in one of the three geographic regions described in [Where your Microsoft 365 customer data is stored](/microsoft-365/enterprise/o365-data-locations).</span></span> <span data-ttu-id="1624e-202">会議の参加者が Teams に入力したすべてのチャット、録音、およびその他のデータは、既存の保存ポリシーに従って保存されます。</span><span class="sxs-lookup"><span data-stu-id="1624e-202">All chat, recordings, and other data entered into Teams by the meeting participants are stored according to existing storage policies.</span></span> <span data-ttu-id="1624e-203">Microsoft Teams のデータの場所の詳細については、「[Teams のデータの場所](../../location-of-data-in-teams.md)」にアクセスしてください。</span><span class="sxs-lookup"><span data-stu-id="1624e-203">If you want to learn more information on the location of data in Microsoft Teams, visit [Locations of data in Teams](../../location-of-data-in-teams.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="1624e-204">関連項目</span><span class="sxs-lookup"><span data-stu-id="1624e-204">Related topics</span></span>

[<span data-ttu-id="1624e-205">Teams仮想アクセス</span><span class="sxs-lookup"><span data-stu-id="1624e-205">Teams virtual visits</span></span>](ehr-admin-reports.md)