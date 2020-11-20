---
title: 仮想アクセスのチーム
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
description: Microsoft Teams を使用して仮想ビジットシステムをセットアップする
ms.openlocfilehash: 808d957cd86273852e7c2c98ec223b1988e5bd0d
ms.sourcegitcommit: cbf87fc914a19088af8ec08fb0976db9f838a45d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/19/2020
ms.locfileid: "49355967"
---
# <a name="virtual-visits-with-teams---integration-into-ehr"></a><span data-ttu-id="ca1fb-103">チームでの仮想アクセス-EHR との統合</span><span class="sxs-lookup"><span data-stu-id="ca1fb-103">Virtual visits with Teams - Integration into EHR</span></span>

<span data-ttu-id="ca1fb-104">Microsoft Teams の電子医療記録 (EHR) コネクタを使用すると、clinicians は、EHR システムから直接、Teams の他のプロバイダーとの間で仮想患者のアクセスや相談を簡単に開始できます。</span><span class="sxs-lookup"><span data-stu-id="ca1fb-104">Microsoft Teams Electronic Health Record (EHR) Connector makes it easy for clinicians to launch a virtual patient visit or consultation with another provider in Teams directly from the EHR system.</span></span> <span data-ttu-id="ca1fb-105">Microsoft Teams では、microsoft 365 クラウドを基盤として、Microsoft Teams を使用することで、HIPAA、ビデオ、音声、および医療ツールとのシンプルで安全な共同作業とコミュニケーションが実現されます。これは、HIPAA への準拠をサポートしている単一のハブです。</span><span class="sxs-lookup"><span data-stu-id="ca1fb-105">Built on the Microsoft 365 cloud, Microsoft Teams enables simple, secure collaboration and communication with chat, video, voice, and healthcare tools in a single hub that supports compliance with HIPAA, HITECH certification, and more.</span></span>

<span data-ttu-id="ca1fb-106">チームのコミュニケーションとコラボレーションのプラットフォームにより、clinicians は、断片化されたシステムの低優先メールを簡単にカットできるため、時間を節約できます。</span><span class="sxs-lookup"><span data-stu-id="ca1fb-106">The communication and collaboration platform of Teams makes it easy for clinicians to cut through the clutter of fragmented systems so they can spend time providing the best possible care.</span></span> <span data-ttu-id="ca1fb-107">Microsoft Teams の電子医療記録 (EHR) コネクタは、次のことができます。</span><span class="sxs-lookup"><span data-stu-id="ca1fb-107">Microsoft Teams Electronic Health Record (EHR) Connector can:</span></span>

- <span data-ttu-id="ca1fb-108">プロバイダーと患者の両方のポータルから、Teams の仮想アクセスを起動します。</span><span class="sxs-lookup"><span data-stu-id="ca1fb-108">Launch Teams virtual visits from both provider and patient portals.</span></span>

- <span data-ttu-id="ca1fb-109">自動監査とレコード保持を有効にするには、接続イベントと切断イベントに関する EHR メタデータに書き戻します。</span><span class="sxs-lookup"><span data-stu-id="ca1fb-109">Write back into EHR metadata on connect and disconnect events to enable automatic auditing and record keeping.</span></span>

- <span data-ttu-id="ca1fb-110">既存の clinician と患者のワークフローに統合しながら、Microsoft Teams を使用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="ca1fb-110">Integrate into existing clinician and patient workflows while allowing them to use Microsoft Teams.</span></span>

  <span data-ttu-id="ca1fb-111">EHR ポータルから仮想アクセスを管理する方法のビデオをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="ca1fb-111">Watch the video of How to manage virtual visits from the EHR portal.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4HAtn]

## <a name="before-you-begin"></a><span data-ttu-id="ca1fb-112">始める前に</span><span class="sxs-lookup"><span data-stu-id="ca1fb-112">Before you begin</span></span>

<span data-ttu-id="ca1fb-113">EHR コネクタを統合するには、次の前提条件が満たされていることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ca1fb-113">You’ll need to make sure you have the following prerequisites before you can integrate the EHR connector:</span></span>

- <span data-ttu-id="ca1fb-114">医療機関向けの Microsoft Cloud、または Microsoft Teams の EHR コネクタスタンドアロンサービスのサブスクリプション。</span><span class="sxs-lookup"><span data-stu-id="ca1fb-114">Active subscription to Microsoft Cloud for Healthcare or subscription to Microsoft Teams EHR Connector standalone offer.</span></span>

- <span data-ttu-id="ca1fb-115">ユーザーには、Microsoft Teams の会議を含む適切な Microsoft 365 または Office 365 のライセンスが必要です。</span><span class="sxs-lookup"><span data-stu-id="ca1fb-115">Users must have an appropriate Microsoft 365 or Office 365 license that includes Microsoft Teams meetings.</span></span>

- <span data-ttu-id="ca1fb-116">Microsoft Teams は、組織内で採用して使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ca1fb-116">Microsoft Teams should be adopted and used inside the organization.</span></span>

- <span data-ttu-id="ca1fb-117">組織には、2018年11月以降のエピックバージョンが必要です。</span><span class="sxs-lookup"><span data-stu-id="ca1fb-117">Organizations must have with Epic version November 2018 or later.</span></span>

- <span data-ttu-id="ca1fb-118">システムは、 [ソフトウェアとブラウザーのすべての前提条件を](https://docs.microsoft.com/microsoftteams/hardware-requirements-for-the-teams-app)満たしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="ca1fb-118">Your systems must meet all [software and browser prerequisites](https://docs.microsoft.com/microsoftteams/hardware-requirements-for-the-teams-app).</span></span>

<span data-ttu-id="ca1fb-119">組織内の次のユーザーからの情報も必要になります。</span><span class="sxs-lookup"><span data-stu-id="ca1fb-119">You’ll also need information from the following people in your organization:</span></span>

- <span data-ttu-id="ca1fb-120">Microsoft 365 管理者</span><span class="sxs-lookup"><span data-stu-id="ca1fb-120">Microsoft 365 administrator</span></span>

- <span data-ttu-id="ca1fb-121">エピック管理者</span><span class="sxs-lookup"><span data-stu-id="ca1fb-121">Epic administrator</span></span>

> [!Note]
> <span data-ttu-id="ca1fb-122">エピック管理者に依頼して、エピック市場で利用可能な Epic-Microsoft Teams のテレライフの統合ガイドを提供してください。</span><span class="sxs-lookup"><span data-stu-id="ca1fb-122">Request your Epic admin to provide the Epic-Microsoft Teams Telehealth Integration Guide available in the Epic marketplace.</span></span>

## <a name="connector-setup"></a><span data-ttu-id="ca1fb-123">コネクタのセットアップ</span><span class="sxs-lookup"><span data-stu-id="ca1fb-123">Connector setup</span></span>

<span data-ttu-id="ca1fb-124">コネクタのセットアップでは、次のことを行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="ca1fb-124">The connector setup requires that you:</span></span>

- [<span data-ttu-id="ca1fb-125">EHR コネクタ構成ポータルを起動する</span><span class="sxs-lookup"><span data-stu-id="ca1fb-125">Launch the EHR Connector configuration portal</span></span>](ehr-admin.md#launch-the-ehr-connector-configuration-portal)
- [<span data-ttu-id="ca1fb-126">プロバイダー組織の情報を構成する</span><span class="sxs-lookup"><span data-stu-id="ca1fb-126">Configure provider organization information</span></span>](ehr-admin.md#configure-provider-organization-information)
- [<span data-ttu-id="ca1fb-127">構成を確認して承認する</span><span class="sxs-lookup"><span data-stu-id="ca1fb-127">Verify and approve the configuration</span></span>](ehr-admin.md#verify-and-approve-the-configuration)
- [<span data-ttu-id="ca1fb-128">構成を確認して完了する</span><span class="sxs-lookup"><span data-stu-id="ca1fb-128">Review and finish the configuration</span></span>](ehr-admin.md#review-and-finish-the-configuration)

### <a name="launch-the-ehr-connector-configuration-portal"></a>[<span data-ttu-id="ca1fb-129">EHR コネクタ構成ポータルを起動する</span><span class="sxs-lookup"><span data-stu-id="ca1fb-129">Launch the EHR Connector configuration portal</span></span>](#launch-the-ehr-connector-configuration-portal)

<span data-ttu-id="ca1fb-130">Microsoft Teams で仮想アクセスを起動するように医療組織を構成するには、EHR コネクタ構成ポータルを起動します。</span><span class="sxs-lookup"><span data-stu-id="ca1fb-130">Configuring your healthcare organization to launch virtual visits with Microsoft Teams starts by launching the EHR Connector configuration portal.</span></span> <span data-ttu-id="ca1fb-131">テスト URL を使って、エピックテスト環境のコネクタを構成します。</span><span class="sxs-lookup"><span data-stu-id="ca1fb-131">Use the test URL to configure the connector for your Epic test environment.</span></span> <span data-ttu-id="ca1fb-132">エピックの運用環境を有効にする準備ができたら、プロダクション URL を使います。</span><span class="sxs-lookup"><span data-stu-id="ca1fb-132">Use the production URL when you're ready to enable your Epic production environment.</span></span>
  
- <span data-ttu-id="ca1fb-133">テスト環境 [https://ehrconnector-ppe.teams.microsoft.com](https://ehrconnector-ppe.teams.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="ca1fb-133">Test environment [https://ehrconnector-ppe.teams.microsoft.com](https://ehrconnector-ppe.teams.microsoft.com)</span></span>
- <span data-ttu-id="ca1fb-134">運用環境 [https://ehrconnector.teams.microsoft.com](https://ehrconnector.teams.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="ca1fb-134">Production environment [https://ehrconnector.teams.microsoft.com](https://ehrconnector.teams.microsoft.com)</span></span>

<span data-ttu-id="ca1fb-135">組織の Microsoft 365 管理者とエピックの管理者は、構成ポータルで情報と統合の手順を完了する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ca1fb-135">The Microsoft 365 admin and Epic admin from your organization must complete the information and integration steps in the configuration portal.</span></span> <span data-ttu-id="ca1fb-136">エピック構成手順については、組織に割り当てられているエピックリソースに問い合わせてください。</span><span class="sxs-lookup"><span data-stu-id="ca1fb-136">For Epic configuration steps, contact the Epic resource assigned to your organization.</span></span>

### <a name="configure-provider-organization-information"></a>[<span data-ttu-id="ca1fb-137">プロバイダー組織の情報を構成する</span><span class="sxs-lookup"><span data-stu-id="ca1fb-137">Configure provider organization information</span></span>](#configure-provider-organization-information)

<span data-ttu-id="ca1fb-138">この手順は、Microsoft 365 管理者によって完了されます。</span><span class="sxs-lookup"><span data-stu-id="ca1fb-138">This step is to be completed by the Microsoft 365 administrator.</span></span> <span data-ttu-id="ca1fb-139">Microsoft 365 管理者は、コネクタ構成ポータルを起動し、Microsoft 資格情報でサインインして、構成プロセスを開始する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ca1fb-139">The Microsoft 365 administrator must launch the connector configuration portal and sign in with Microsoft credentials to start the configuration process.</span></span>

<span data-ttu-id="ca1fb-140">この手順を完了するために、Microsoft 365 管理者は、Microsoft 365 管理者から、構成を承認するエピック管理者のユーザー名から、有効な Fast Health の相互運用性リソース (FHIR) ベース URL を受け取る必要があります。</span><span class="sxs-lookup"><span data-stu-id="ca1fb-140">To complete this step, the Microsoft 365 administrator must receive a valid Fast Health Interoperability Resources (FHIR) base URL from your Microsoft 365 administrator and the username of the Epic administrator who will be approving the configuration.</span></span> <span data-ttu-id="ca1fb-141">Microsoft 365 管理者は、コネクタ構成ページを起動し、Microsoft 資格情報でサインインして、構成プロセスを開始する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ca1fb-141">The Microsoft 365 administrator must launch the connector configuration page and sign in with Microsoft credentials to start the configuration process.</span></span>

- <span data-ttu-id="ca1fb-142">FHIR ベース URL は、サーバー FHIR API エンドポイントに対応する静的アドレスです。</span><span class="sxs-lookup"><span data-stu-id="ca1fb-142">The FHIR base URL is a static address corresponding to your server FHIR API endpoint.</span></span> <span data-ttu-id="ca1fb-143">URL の例を次に示し `https://lamnahealthcare.org/fihr/auth/connect-ocurprd-oauth/api/FHDST` ます。</span><span class="sxs-lookup"><span data-stu-id="ca1fb-143">An example URL is `https://lamnahealthcare.org/fihr/auth/connect-ocurprd-oauth/api/FHDST`.</span></span>

- <span data-ttu-id="ca1fb-144">構成承認者名は、構成の承認を担当するエピックシステム管理者の名前です。</span><span class="sxs-lookup"><span data-stu-id="ca1fb-144">Configuration approver name is the name of the Epic system administrator who will be responsible for approving the configuration.</span></span>

  ![構成承認者名は、EHR コネクタのリストから選択されます。](../../media/ehc-provider-1.png)

### <a name="verify-and-approve-the-configuration"></a>[<span data-ttu-id="ca1fb-146">構成を確認して承認する</span><span class="sxs-lookup"><span data-stu-id="ca1fb-146">Verify and approve the configuration</span></span>](#verify-and-approve-the-configuration)

<span data-ttu-id="ca1fb-147">承認者として追加された医療機関向けのエピック管理者は、前の手順と同じ EHR コネクタ URL を使用して、Microsoft 365 の資格情報を使ってサインインする必要があります。</span><span class="sxs-lookup"><span data-stu-id="ca1fb-147">The Epic administrator for your healthcare organization who was added as an approver must now use the same EHR Connector URL from the previous step to sign in using their Microsoft 365 credentials.</span></span> <span data-ttu-id="ca1fb-148">検証に成功した後、承認者はエピックの資格情報を使用して、エピック組織を検証するように求められます。</span><span class="sxs-lookup"><span data-stu-id="ca1fb-148">After successful validation, the approver is going to be asked to sign in using their Epic credentials to validate the Epic organization.</span></span>

> [!Note]
> <span data-ttu-id="ca1fb-149">組織内の Microsoft 365 管理者とエピックの管理者は、同じユーザーになることができます。</span><span class="sxs-lookup"><span data-stu-id="ca1fb-149">The Microsoft 365 admin and Epic admin in your organizations can be the same person.</span></span> <span data-ttu-id="ca1fb-150">その場合は、最初の手順で承認者として独自のユーザー名を追加します。</span><span class="sxs-lookup"><span data-stu-id="ca1fb-150">In that case, add your own username as approver in the first step.</span></span> <span data-ttu-id="ca1fb-151">引き続き、エピックにサインインして、アクセスを検証する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ca1fb-151">You'll still need to sign in to Epic to validate your access.</span></span> <span data-ttu-id="ca1fb-152">エピックのサインインは、FHIR のベース URL を検証するためだけに使用されます。</span><span class="sxs-lookup"><span data-stu-id="ca1fb-152">The Epic sign in is only used to validate your FHIR base URL.</span></span> <span data-ttu-id="ca1fb-153">Microsoft は、このサインインを使用して、資格情報を保存したり、EHR データにアクセスしたりすることはありません。</span><span class="sxs-lookup"><span data-stu-id="ca1fb-153">Microsoft will not store credentials or access EHR data with this sign in.</span></span>

  ![資格情報の構成を確認し、承認します。](../../media/ehc-provider-2.png)

<span data-ttu-id="ca1fb-155">成功したエピックにサインインすると、エピック管理者が構成を承認 **する必要があり** ます。</span><span class="sxs-lookup"><span data-stu-id="ca1fb-155">After a successful Epic sign in, the Epic administrator **must** approve the configuration.</span></span> <span data-ttu-id="ca1fb-156">構成が正しくない場合、Microsoft 365 管理者は、Microsoft EHR コネクタポータルにもう一度サインインして、元の構成を変更することができます。</span><span class="sxs-lookup"><span data-stu-id="ca1fb-156">If the configuration isn't correct, the Microsoft 365 admin will have the ability to modify the original configurations by signing in to the Microsoft EHR Connector portal again.</span></span>

![EHR コネクタが構成されていることを確認し、構成を変更するオプションを選択します。](../../media/ehc-approve-3.png)

### <a name="review-and-finish-the-configuration"></a>[<span data-ttu-id="ca1fb-158">構成を確認して完了する</span><span class="sxs-lookup"><span data-stu-id="ca1fb-158">Review and finish the configuration</span></span>](#review-and-finish-the-configuration)

<span data-ttu-id="ca1fb-159">構成情報がエピック管理者によって承認されると、患者とプロバイダーの起動のための統合レコードが表示されます。</span><span class="sxs-lookup"><span data-stu-id="ca1fb-159">When the configuration information is approved by the Epic administrator, you'll be presented with integration records for patient and provider launch.</span></span> <span data-ttu-id="ca1fb-160">これらのレコードは、エピックで仮想アクセス構成を完了するために必要です。</span><span class="sxs-lookup"><span data-stu-id="ca1fb-160">These records are necessary to complete the virtual visit configuration in Epic.</span></span> <span data-ttu-id="ca1fb-161">詳細については、Epic-Microsoft Teams の「テレライフの統合」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ca1fb-161">Refer to the Epic-Microsoft Teams Telehealth Integration guide for more details.</span></span>

> [!Note]  
> <span data-ttu-id="ca1fb-162">いつでも、Microsoft 365 またはエピックの管理者は、構成ポータルにサインインして、統合レコードを表示し、必要に応じて組織の構成を変更することができます。</span><span class="sxs-lookup"><span data-stu-id="ca1fb-162">At any time the Microsoft 365 or Epic administrator can sign in to the configuration portal to view integration records and modify organization configuration, if needed.</span></span>

![統合情報が表示されます。](../../media/ehc-final-config-4.png)

## <a name="launch-teams-virtual-visits"></a><span data-ttu-id="ca1fb-164">チームの仮想訪問を開始する</span><span class="sxs-lookup"><span data-stu-id="ca1fb-164">Launch Teams virtual visits</span></span>

<span data-ttu-id="ca1fb-165">EHR コネクタの手順とエピックの構成を完了すると、組織で Microsoft Teams を使用してビデオ通話をサポートできるようになります。</span><span class="sxs-lookup"><span data-stu-id="ca1fb-165">After completing the EHR Connector steps and Epic configuration, your organization is ready to support video visits with Microsoft Teams.</span></span>

### <a name="virtual-visit-prerequisites"></a><span data-ttu-id="ca1fb-166">仮想アクセスの前提条件</span><span class="sxs-lookup"><span data-stu-id="ca1fb-166">Virtual visit prerequisites</span></span>

- <span data-ttu-id="ca1fb-167">システムは、 [ソフトウェアとブラウザーのすべての前提条件を](https://docs.microsoft.com/microsoftteams/hardware-requirements-for-the-teams-app)満たしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="ca1fb-167">Your systems must meet all [software and browser prerequisites](https://docs.microsoft.com/microsoftteams/hardware-requirements-for-the-teams-app).</span></span>

- <span data-ttu-id="ca1fb-168">医療機関は、エピック組織と Microsoft 365 組織間のセットアップを完了する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ca1fb-168">Healthcare organization must have completed the setup between the Epic organization and Microsoft 365 organization.</span></span>

### <a name="provider-experience"></a><span data-ttu-id="ca1fb-169">プロバイダーの操作</span><span class="sxs-lookup"><span data-stu-id="ca1fb-169">Provider experience</span></span>

<span data-ttu-id="ca1fb-170">組織の医療機関は、エピックプロバイダアプリケーション (ハイパースペース、Haiku、Canto) から Microsoft Teams を使用して仮想訪問に参加することもできます。</span><span class="sxs-lookup"><span data-stu-id="ca1fb-170">Healthcare providers from your organization can also join virtual visits with Microsoft Teams from their Epic provider applications (Hyperspace, Haiku, Canto).</span></span> <span data-ttu-id="ca1fb-171">[ **仮想アクセスの開始** ] ボタンがプロバイダーフローに埋め込まれます。</span><span class="sxs-lookup"><span data-stu-id="ca1fb-171">The **Begin virtual visit** button is embedded in the provider flow.</span></span>

<span data-ttu-id="ca1fb-172">プロバイダーエクスペリエンスの主な機能:</span><span class="sxs-lookup"><span data-stu-id="ca1fb-172">Key features of the provider experience:</span></span>

- <span data-ttu-id="ca1fb-173">プロバイダーは、サポートされているブラウザーまたは Microsoft Teams アプリケーションを使用して仮想ビジットに参加できます。</span><span class="sxs-lookup"><span data-stu-id="ca1fb-173">Providers can join virtual visits using supported browsers or the Microsoft Teams application.</span></span>

- <span data-ttu-id="ca1fb-174">プロバイダーは、仮想訪問を初めて参加するときに、Microsoft 365 アカウントで1回サインインする必要があります。</span><span class="sxs-lookup"><span data-stu-id="ca1fb-174">Providers must do a one time sign in with their Microsoft 365 account when joining a virtual visit for the first time.</span></span>

- <span data-ttu-id="ca1fb-175">一度サインインすると、プロバイダーは Microsoft Teams の仮想予定に直接取り込まれます。</span><span class="sxs-lookup"><span data-stu-id="ca1fb-175">After the one time sign in, the provider will be taken straight to the virtual appointment in Microsoft Teams.</span></span> <span data-ttu-id="ca1fb-176">(プロバイダーは Microsoft Teams にサインインしている必要があります)。</span><span class="sxs-lookup"><span data-stu-id="ca1fb-176">(Provider must be signed-in to Microsoft Teams).</span></span>

- <span data-ttu-id="ca1fb-177">プロバイダーは、特定の予定について、参加者の接続と切断をリアルタイムで行うことができます。</span><span class="sxs-lookup"><span data-stu-id="ca1fb-177">Provider can see real-time updates of participants connect and disconnect for a given appointment.</span></span> <span data-ttu-id="ca1fb-178">プロバイダーは、患者が仮想アクセスに接続されているかどうかを確認できます。</span><span class="sxs-lookup"><span data-stu-id="ca1fb-178">The provider can see when the patient is connected to a virtual visit.</span></span>

  ![患者との仮想アクセスのプロバイダーエクスペリエンス](../../media/ehc-provider-experience-6.png)

### <a name="patient-experience"></a><span data-ttu-id="ca1fb-180">患者の体験</span><span class="sxs-lookup"><span data-stu-id="ca1fb-180">Patient experience</span></span>

<span data-ttu-id="ca1fb-181">コネクタは、MyChart の web およびモバイルを通じて仮想訪問に参加する患者をサポートします。</span><span class="sxs-lookup"><span data-stu-id="ca1fb-181">The connector supports patients joining virtual visits through MyChart web and mobile.</span></span> <span data-ttu-id="ca1fb-182">予定の時点では、患者は [ **仮想アクセスの開始** ] ボタンを使って、MyChart から仮想アクセスを開始できます。</span><span class="sxs-lookup"><span data-stu-id="ca1fb-182">At the time of the appointment, patients can start a virtual visit from MyChart using the **Begin virtual visit** button.</span></span>

<span data-ttu-id="ca1fb-183">患者の体験の主要機能:</span><span class="sxs-lookup"><span data-stu-id="ca1fb-183">Key features of the patient experience:</span></span>

- <span data-ttu-id="ca1fb-184">患者は、アプリがインストールされていなくても、デスクトップおよびモバイルの最新の web ブラウザーから仮想アクセスに参加できます。</span><span class="sxs-lookup"><span data-stu-id="ca1fb-184">Patients can join virtual visits from modern web browsers on desktop and mobile without app installation.</span></span>

- <span data-ttu-id="ca1fb-185">患者は1回のクリックで仮想訪問に参加できます。追加のアカウントがないか、サインインする必要がありません。</span><span class="sxs-lookup"><span data-stu-id="ca1fb-185">Patients can join virtual visits with a single click and there is no additional account or sign in required.</span></span>

- <span data-ttu-id="ca1fb-186">患者は、Microsoft アカウントを作成したり、サインインして仮想アクセスを開始したりする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="ca1fb-186">Patients aren't required to create a Microsoft account or sign in to launch a virtual visit.</span></span>

- <span data-ttu-id="ca1fb-187">患者は、医療機関がその予定に参加して、仮想アクセスを許可するまで、ロビーに配置されます。</span><span class="sxs-lookup"><span data-stu-id="ca1fb-187">Patients will be placed in a lobby until the healthcare provider joins the appointment and admits them to the virtual visit.</span></span>

- <span data-ttu-id="ca1fb-188">ビデオとマイクのテストは、仮想アクセスの参加前にロビーで行うことができます。</span><span class="sxs-lookup"><span data-stu-id="ca1fb-188">Testing of the video and microphone is available in the lobby before joining the virtual visit.</span></span>

  ![仮想アクセスの患者の体験](../../media/ehc-virtual-visit-5.png)

> [!Note]
> <span data-ttu-id="ca1fb-190">エピック、MyChart、Haiku、および Canto、エピックシステム Corporation の商標です。</span><span class="sxs-lookup"><span data-stu-id="ca1fb-190">Epic, MyChart, Haiku, and Canto are trademarks of Epic Systems Corporation.</span></span>

### <a name="privacy-and-location-of-data"></a><span data-ttu-id="ca1fb-191">データのプライバシーと場所</span><span class="sxs-lookup"><span data-stu-id="ca1fb-191">Privacy and location of data</span></span>

<span data-ttu-id="ca1fb-192">チームと EHR システムの統合により、統合および仮想アクセスフローで使用されるデータ量が最適化されます。</span><span class="sxs-lookup"><span data-stu-id="ca1fb-192">Teams integration into EHR systems optimizes the amount of data being used and stored during integration and virtual visit flows.</span></span> <span data-ttu-id="ca1fb-193">このソリューションは、チームのプライバシーに関する全体的なチームのプライバシーとデータ管理の原則とガイドラインに従っています。</span><span class="sxs-lookup"><span data-stu-id="ca1fb-193">The solution follows the overall Teams privacy and data management principles and guidelines outlined in Teams Privacy.</span></span>

<span data-ttu-id="ca1fb-194">Microsoft Teams EHR コネクタは、EHR システムから特定の個人データ、または患者や医療機関の健康記録を保存することはできません。</span><span class="sxs-lookup"><span data-stu-id="ca1fb-194">The Microsoft Teams EHR connector doesn't store nor transfer any identifiable personal data or any health records of patients or healthcare providers from the EHR system.</span></span> <span data-ttu-id="ca1fb-195">EHR コネクタによって保存されるデータは、EHR ユーザーの固有の ID です。これは、Teams の会議のセットアップ時に使用されます。</span><span class="sxs-lookup"><span data-stu-id="ca1fb-195">The only data that is stored by the EHR connector is the EHR user’s unique ID, which is used during Teams meeting setup.</span></span> <span data-ttu-id="ca1fb-196">EHR ユーザーの固有の ID は、「 [Microsoft 365 顧客データの保存場所](https://docs.microsoft.com/microsoft-365/enterprise/o365-data-locations?view=o365-worldwide#data-center-geographies) 」で説明されている3つの地理的な地域のいずれかに保存されています。</span><span class="sxs-lookup"><span data-stu-id="ca1fb-196">The EHR user’s unique ID is stored in one of the three geographic regions described in the [Where your Microsoft 365 customer data is stored](https://docs.microsoft.com/microsoft-365/enterprise/o365-data-locations?view=o365-worldwide#data-center-geographies) article.</span></span> <span data-ttu-id="ca1fb-197">会議の参加者によってチームに入力されたすべてのチャット、レコーディング、その他のデータは、既存のストレージポリシーに従って保存されます。</span><span class="sxs-lookup"><span data-stu-id="ca1fb-197">All chat, recordings, and other data entered into Teams by the meeting participants are stored according to existing storage policies.</span></span> <span data-ttu-id="ca1fb-198">Microsoft Teams のデータの場所について詳しく知りたい場合は、Teams の [データの場所](https://docs.microsoft.com/microsoftteams/location-of-data-in-teams)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ca1fb-198">If you want to learn more information on the location of data in Microsoft Teams, visit [Locations of data in Teams](https://docs.microsoft.com/microsoftteams/location-of-data-in-teams).</span></span>
