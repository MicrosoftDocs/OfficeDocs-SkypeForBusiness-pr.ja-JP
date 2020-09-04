---
title: オンプレミスユーザー用にクラウドボイスメールサービスを計画する |PBX Skype for Business Server 2019
ms.reviewer: ''
ms.author: dstrome
author: dstrome
manager: serdars
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: この記事では、Microsoft クラウドボイスメールサービスを実装するための利点、計画に関する考慮事項、および要件について説明します。 クラウドボイスメールの構成の詳細については、「Cloud 留守番電話を構成する」を参照してください。
ms.openlocfilehash: d95d3674eb9119be07e8b588ec3fe0e619fb5f1c
ms.sourcegitcommit: b424ab14683ab5080ebfd085adff7c0dbe1be84c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/03/2020
ms.locfileid: "47359133"
---
# <a name="plan-cloud-voicemail-service-for-on-premises-users"></a><span data-ttu-id="225c1-104">オンプレミスユーザー用にクラウドボイスメールサービスを計画する</span><span class="sxs-lookup"><span data-stu-id="225c1-104">Plan Cloud Voicemail service for on-premises users</span></span>

## <a name="overview"></a><span data-ttu-id="225c1-105">概要</span><span class="sxs-lookup"><span data-stu-id="225c1-105">Overview</span></span>

<span data-ttu-id="225c1-106">この記事では、オンプレミスのユーザー用に Microsoft クラウドボイスメールサービスを実装するための利点、計画に関する考慮事項、および要件について説明します。</span><span class="sxs-lookup"><span data-stu-id="225c1-106">This article describes benefits, planning considerations, and requirements for implementing the Microsoft Cloud Voicemail service for your on-premises users.</span></span> <span data-ttu-id="225c1-107">クラウドボイスメールの構成の詳細については、「 [クラウドボイスメールサービスを構成する](configure-cloud-voicemail.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="225c1-107">For information on configuring Cloud Voicemail, see [Configure Cloud Voicemail service](configure-cloud-voicemail.md).</span></span>

<span data-ttu-id="225c1-108">クラウドボイスメールは、exchange ユニファイドメッセージング (UM) の代わりに、Exchange Server 2019 または Exchange Online にメールボックスを持つ Skype for Business 2019 音声ユーザーの音声メッセージング機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="225c1-108">Cloud Voicemail takes the place of Exchange Unified Messaging (UM) in providing voice messaging functionality for Skype for Business 2019 voice users who have mailboxes on Exchange Server 2019 or Exchange Online.</span></span> <span data-ttu-id="225c1-109">クラウドボイスメールには、オンプレミスのユーザーとオンラインユーザーの両方に対して次のような利点があります。</span><span class="sxs-lookup"><span data-stu-id="225c1-109">Cloud Voicemail provides the following benefits for both your on-premises and online users:</span></span>

- <span data-ttu-id="225c1-110">音声による留守番電話の応答と取り込み機能の強化</span><span class="sxs-lookup"><span data-stu-id="225c1-110">Voicemail answering and deposit functionality with enhanced speech transcription</span></span>

- <span data-ttu-id="225c1-111">Skype for Business Online または Outlook クライアントを使用して、ユーザーの Exchange メールボックス内のボイスメールにアクセスする</span><span class="sxs-lookup"><span data-stu-id="225c1-111">Access to voicemail in the user's Exchange mailbox by using the Skype for Business Online or Outlook clients</span></span>

- <span data-ttu-id="225c1-112">Microsoft 365 管理センターを使用してボイスメールオプションを管理する機能</span><span class="sxs-lookup"><span data-stu-id="225c1-112">The ability to use the Microsoft 365 admin center to manage voicemail options</span></span>

- <span data-ttu-id="225c1-113">社内またはクラウドでの Exchange メールボックスのサポート</span><span class="sxs-lookup"><span data-stu-id="225c1-113">Support for Exchange mailboxes on premises or in the cloud</span></span>

- <span data-ttu-id="225c1-114">Exchange Online ユニファイドメッセージングからの既存のユーザー案内応答の活用</span><span class="sxs-lookup"><span data-stu-id="225c1-114">Leveraging of existing user greetings from Exchange Online Unified Messaging</span></span>

> [!Important]
> <span data-ttu-id="225c1-115">Skype for Business Online は2021年7月31日に廃止されます。これは、ユーザーが Skype for Business Online クライアントを介して Exchange メールボックス内のボイスメールにアクセスできなくなります。</span><span class="sxs-lookup"><span data-stu-id="225c1-115">Skype for Business Online will be retired on July 31, 2021 after which users will no longer be able to access voicemail in their Exchange mailbox through the Skype for Business Online client.</span></span>

<span data-ttu-id="225c1-116">機能の比較の詳細については、「 [Plan For Skype for Business server And Exchange server migration](plan-um-migration.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="225c1-116">For more information about feature comparison, see [Plan for Skype for Business Server and Exchange Server migration](plan-um-migration.md).</span></span>

<span data-ttu-id="225c1-117">Skype for Business Server 2019 は、メールボックスが以前のバージョンの Exchange Server (2013, 2016) にあるユーザーに対して Exchange UM を引き続き使用します。</span><span class="sxs-lookup"><span data-stu-id="225c1-117">Skype for Business Server 2019 continues to use Exchange UM for users whose mailboxes are on previous versions of Exchange Server (2013, 2016).</span></span>  <span data-ttu-id="225c1-118">Exchange Server および Skype for Business Server のバージョンに基づいてどのボイスメールソリューションを使用するかを理解することは、Skype for Business Server 2019 または Exchange Server 2019 に移行するための計画において重要な部分です。</span><span class="sxs-lookup"><span data-stu-id="225c1-118">Understanding which voicemail solution will be used based on the Exchange Server and Skype for Business Server version is an important part of planning for migration to either Skype for Business Server 2019 or Exchange Server 2019.</span></span> <span data-ttu-id="225c1-119">移行と相互運用性の詳細については、「 [Plan For Skype for Business server And Exchange server migration](plan-um-migration.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="225c1-119">For more information about migration and interoperability, see [Plan for Skype for Business Server and Exchange Server migration](plan-um-migration.md).</span></span>

<span data-ttu-id="225c1-120">クラウドボイスメールを使用すると、管理タスクは以下の理由で大幅に簡素化されます。</span><span class="sxs-lookup"><span data-stu-id="225c1-120">With Cloud Voicemail, your administration tasks are greatly simplified because:</span></span>

- <span data-ttu-id="225c1-121">Exchange UM の役割を構成する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="225c1-121">There is no need to configure the Exchange UM role.</span></span>
- <span data-ttu-id="225c1-122">クラウドボイスメールのセットアップタスクの方が簡単です。</span><span class="sxs-lookup"><span data-stu-id="225c1-122">The setup tasks for Cloud Voicemail are simpler.</span></span>
- <span data-ttu-id="225c1-123">ボイスメール機能への更新はクラウドに直接配信されるため、ユーザーは常に最新の機能と更新プログラムにアクセスでき、累積的な更新プログラム (Cu) への依存度は低くなります。</span><span class="sxs-lookup"><span data-stu-id="225c1-123">Updates to voicemail functionality are delivered directly in the cloud, so your users always have access to the latest features and updates with less dependency on Cumulative Updates (CUs).</span></span>
- <span data-ttu-id="225c1-124">オンプレミスとオンラインの両方の Exchange メールボックスに対して同じコントロールセットがあります。</span><span class="sxs-lookup"><span data-stu-id="225c1-124">You have the same set of controls for both on-premises and online Exchange mailboxes.</span></span> <span data-ttu-id="225c1-125">これらのコントロールの詳細については、「 [電話システムボイスメールをセットアップ](https://support.office.com/article/Set-up-Phone-System-voicemail-Admin-help-9c590873-b014-4df3-9e27-1bb97322a79d)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="225c1-125">For more information on these controls, see [Set up Phone System voicemail](https://support.office.com/article/Set-up-Phone-System-voicemail-Admin-help-9c590873-b014-4df3-9e27-1bb97322a79d).</span></span>

<span data-ttu-id="225c1-126">次の図は、ハイブリッド展開でのクラウドボイスメールを示しています。</span><span class="sxs-lookup"><span data-stu-id="225c1-126">The following diagram shows Cloud Voicemail in a hybrid deployment:</span></span>

![SfB クラウドボイスメール](../../sfbserver2019/media/plan-cloud-voice-mail-server1.png)

<span data-ttu-id="225c1-128">応答のない通話は次のように処理されます。</span><span class="sxs-lookup"><span data-stu-id="225c1-128">Unanswered calls are handled as follows:</span></span>  

1. <span data-ttu-id="225c1-129">オンプレミスの Skype for Business 2019 に所属するユーザーは、オンプレミスの Skype for Business Server によってオンラインクラウドボイスメールサービスに送信されます。</span><span class="sxs-lookup"><span data-stu-id="225c1-129">For users homed in Skype for Business 2019 on premises, unanswered calls are sent by the on-premises Skype for Business Server to the online Cloud Voicemail service.</span></span>
2. <span data-ttu-id="225c1-130">サービスは、議事録を含めて、ボイスメールを処理します。</span><span class="sxs-lookup"><span data-stu-id="225c1-130">The service processes the voicemail, including transcription.</span></span>
3. <span data-ttu-id="225c1-131">その後、メールボックスがオンプレミスかオンラインかにかかわらず、ユーザーの Exchange メールボックスにボイスメールがデポジットされます。</span><span class="sxs-lookup"><span data-stu-id="225c1-131">The service then deposits the voicemail in the Exchange mailbox of the user, whether the mailbox is on-premises or online.</span></span>  
4. <span data-ttu-id="225c1-132">ユーザーは、Skype for Business または Outlook クライアントから、ボイスメールにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="225c1-132">Users can access their voicemail from either their Skype for Business or Outlook client.</span></span>

## <a name="requirements"></a><span data-ttu-id="225c1-133">要件</span><span class="sxs-lookup"><span data-stu-id="225c1-133">Requirements</span></span>

<span data-ttu-id="225c1-134">次の要件は、サポートされているトポロジで Skype for Business Server を既に展開していることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="225c1-134">The following requirements assume that you already have Skype for Business Server deployed in a supported topology.</span></span>  <span data-ttu-id="225c1-135">要件は、シナリオによって異なります。</span><span class="sxs-lookup"><span data-stu-id="225c1-135">Your requirements depend on your scenario:</span></span>

- <span data-ttu-id="225c1-136">既に Exchange UM online を使用していて、Skype for Business 2019 にアップグレードする場合は、ホスト型ボイスメールポリシーを変更し、ホスティングプロバイダーが正しく設定されていることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="225c1-136">If you are already using Exchange UM online and you upgrade to Skype for Business 2019, you will need to modify your hosted voicemail policy and verify that your hosting providers are set correctly.</span></span> <span data-ttu-id="225c1-137">詳細については、「 [クラウドボイスメールサービスを構成する](configure-cloud-voicemail.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="225c1-137">For more information, see [Configure Cloud Voicemail service](configure-cloud-voicemail.md).</span></span>

- <span data-ttu-id="225c1-138">Exchange UM を社内で使用している場合、または Exchange UM online とオンプレミスを使用しているユーザーが混在している場合は、ホスト型ボイスメールポリシーとホスティングプロバイダーの両方を変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="225c1-138">If you are using Exchange UM on premises, or you have a mix of users using Exchange UM online and on premises, you will need modify both your hosted voicemail policy and hosting provider.</span></span>  <span data-ttu-id="225c1-139">詳細については、「 [クラウドボイスメールサービスを構成する](configure-cloud-voicemail.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="225c1-139">For more information, see [Configure Cloud Voicemail service](configure-cloud-voicemail.md).</span></span>

- <span data-ttu-id="225c1-140">クラウドボイスメールの新しい構成を行うには、「 [Configure Cloud ボイスメールサービス](configure-cloud-voicemail.md)」に記載されている手順に従ってください。</span><span class="sxs-lookup"><span data-stu-id="225c1-140">For a new configuration of Cloud Voicemail, follow the steps outlined in [Configure Cloud Voicemail service](configure-cloud-voicemail.md).</span></span>

<span data-ttu-id="225c1-141">上記の要件に加えて、次の要件を構成して、Microsoft クラウドボイスメールサービスに接続する必要があります。</span><span class="sxs-lookup"><span data-stu-id="225c1-141">In addition to the requirements above, the below requirements must be configured to connect to the Microsoft Cloud Voicemail service:</span></span>

- <span data-ttu-id="225c1-142">ハイブリッド接続。</span><span class="sxs-lookup"><span data-stu-id="225c1-142">Hybrid connectivity.</span></span> <span data-ttu-id="225c1-143">Skype for Business Server を既に展開しており、オンプレミスのユーザーに対してクラウドボイスメールを有効にする場合は、オンプレミスの環境とオンライン環境の間でハイブリッド接続が設定されていることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="225c1-143">If you already have Skype for Business Server deployed, and you want to enable Cloud Voicemail for your on-premises users, you must ensure that you have hybrid connectivity set up between your on-premises and online environments.</span></span> <span data-ttu-id="225c1-144">これは、分割ドメイン構成と呼ばれることがあります。</span><span class="sxs-lookup"><span data-stu-id="225c1-144">This is sometimes called a split domain configuration.</span></span>

   <span data-ttu-id="225c1-145">詳細については、「Skype for business [server と Microsoft 365 または office 365 の間のハイブリッド接続を計画](plan-hybrid-connectivity.md) する」および「 [Skype for Business server と office 365 の間のハイブリッド接続を構成する](configure-hybrid-connectivity.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="225c1-145">For more information, see [Plan hybrid connectivity between Skype for Business Server and Microsoft 365 or Office 365](plan-hybrid-connectivity.md) and [Configure hybrid connectivity between Skype for Business Server and Office 365](configure-hybrid-connectivity.md).</span></span>

- <span data-ttu-id="225c1-146">オンプレミスのユーザーは、Skype for Business Server のエンタープライズ Voip およびホストボイスメールに対して有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="225c1-146">On-premises users must be enabled for Enterprise Voice and Hosted Voicemail in Skype for Business Server.</span></span>

- <span data-ttu-id="225c1-147">外部 Exchange Web サービス (EWS) の URL と自動検出を設定する必要があります。また、一部のクラウドボイスメール機能は制限されます。</span><span class="sxs-lookup"><span data-stu-id="225c1-147">An External Exchange Web Services (EWS) URL and Autodiscover must be set up or some Cloud Voicemail features will be limited.</span></span>

- <span data-ttu-id="225c1-148">オンプレミスの Exchange サーバーがある場合は、「 [set Up Cloud ボイスメール For Exchange Server Mailbox Users](https://docs.microsoft.com/microsoftteams/set-up-phone-system-voicemail#set-up-cloud-voicemail-for-exchange-server-mailbox-users)」の手順を使用してクラウドボイスメールをセットアップします。</span><span class="sxs-lookup"><span data-stu-id="225c1-148">If you have an on-premises Exchange server, set up Cloud Voicemail using the steps in [Set up Cloud Voicemail for Exchange Server Mailbox Users](https://docs.microsoft.com/microsoftteams/set-up-phone-system-voicemail#set-up-cloud-voicemail-for-exchange-server-mailbox-users).</span></span>

## <a name="migration-and-interoperability"></a><span data-ttu-id="225c1-149">移行と相互運用性</span><span class="sxs-lookup"><span data-stu-id="225c1-149">Migration and interoperability</span></span>

<span data-ttu-id="225c1-150">Skype for Business Server 2019 または Exchange Server 2019 の展開を計画している場合は、ボイスメッセージングのサービスを継続するために、慎重に移行を計画する必要があります。</span><span class="sxs-lookup"><span data-stu-id="225c1-150">If you are planning to deploy Skype for Business Server 2019 and/or Exchange Server 2019, you must plan your migration carefully to ensure continued service for voice messaging.</span></span> <span data-ttu-id="225c1-151">以下の点に注意します。</span><span class="sxs-lookup"><span data-stu-id="225c1-151">Keep the following in mind:</span></span>

- <span data-ttu-id="225c1-152">Exchange Server 2019 が Exchange UM 機能を提供しなくなった</span><span class="sxs-lookup"><span data-stu-id="225c1-152">Exchange Server 2019 no longer provides Exchange UM functionality</span></span>
- <span data-ttu-id="225c1-153">Skype for Business Server 2019 が Exchange Online UM と統合されなくなりました</span><span class="sxs-lookup"><span data-stu-id="225c1-153">Skype for Business Server 2019 no longer integrates with Exchange Online UM</span></span>

<span data-ttu-id="225c1-154">次の表は、クラウドボイスメールのバージョン相互運用性とサポートトポロジを示しています。これは、ユーザーが Exchange メールボックスを提供している可能性のあるバージョンで、ユーザーが所属している可能性のある Skype for Business Server バージョンを比較したものです。</span><span class="sxs-lookup"><span data-stu-id="225c1-154">Version interoperability and supported topologies for Cloud Voicemail are listed in the following table, which compares the Skype for Business Server versions the user might be homed on with the possible version providing their Exchange Mailbox.</span></span> <span data-ttu-id="225c1-155">Skype for Business 2019 を Exchange Online または Exchange Server 2019 で使用する場合は、クラウドボイスメールを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="225c1-155">You need to use Cloud Voicemail if you want to use Skype for Business 2019 with Exchange Online or Exchange Server 2019.</span></span>

| | <span data-ttu-id="225c1-156">Exchange Server 2013</span><span class="sxs-lookup"><span data-stu-id="225c1-156">Exchange Server 2013</span></span> | <span data-ttu-id="225c1-157">Exchange Server 2016</span><span class="sxs-lookup"><span data-stu-id="225c1-157">Exchange Server 2016</span></span> | <span data-ttu-id="225c1-158">Exchange Server 2019</span><span class="sxs-lookup"><span data-stu-id="225c1-158">Exchange Server 2019</span></span> | <span data-ttu-id="225c1-159">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="225c1-159">Exchange Online</span></span>   |
|:---    |:--- |:--- |:--- |:---  |
| <span data-ttu-id="225c1-160">Skype for Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="225c1-160">Skype for Business Server 2019</span></span> | <span data-ttu-id="225c1-161">Exchange Server UM</span><span class="sxs-lookup"><span data-stu-id="225c1-161">Exchange Server UM</span></span> | <span data-ttu-id="225c1-162">Exchange Server UM</span><span class="sxs-lookup"><span data-stu-id="225c1-162">Exchange Server UM</span></span> | <span data-ttu-id="225c1-163">クラウド ボイスメール</span><span class="sxs-lookup"><span data-stu-id="225c1-163">Cloud Voicemail</span></span> | <span data-ttu-id="225c1-164">クラウド ボイスメール</span><span class="sxs-lookup"><span data-stu-id="225c1-164">Cloud Voicemail</span></span> |
| <span data-ttu-id="225c1-165">Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="225c1-165">Skype for Business Server 2015</span></span> | <span data-ttu-id="225c1-166">Exchange Server UM</span><span class="sxs-lookup"><span data-stu-id="225c1-166">Exchange Server UM</span></span> | <span data-ttu-id="225c1-167">Exchange Server UM</span><span class="sxs-lookup"><span data-stu-id="225c1-167">Exchange Server UM</span></span> | <span data-ttu-id="225c1-168">クラウド ボイスメール</span><span class="sxs-lookup"><span data-stu-id="225c1-168">Cloud Voicemail</span></span> | <span data-ttu-id="225c1-169">クラウド ボイスメール</span><span class="sxs-lookup"><span data-stu-id="225c1-169">Cloud Voicemail</span></span> |
| <span data-ttu-id="225c1-170">Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="225c1-170">Lync Server 2013</span></span> <br>  | <span data-ttu-id="225c1-171">Exchange Server UM</span><span class="sxs-lookup"><span data-stu-id="225c1-171">Exchange Server UM</span></span> | <span data-ttu-id="225c1-172">Exchange Server UM</span><span class="sxs-lookup"><span data-stu-id="225c1-172">Exchange Server UM</span></span> | <span data-ttu-id="225c1-173">サポート対象外</span><span class="sxs-lookup"><span data-stu-id="225c1-173">Not Supported</span></span> | <span data-ttu-id="225c1-174">クラウド ボイスメール</span><span class="sxs-lookup"><span data-stu-id="225c1-174">Cloud Voicemail</span></span> |

<span data-ttu-id="225c1-175">Microsoft では、次の移行パスをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="225c1-175">Microsoft recommends the following migration paths:</span></span>

- <span data-ttu-id="225c1-176">Skype for Business Server 2019 にアップグレードする場合は、exchange Server 2013 または2016で Exchange UM を使用できますが、Exchange Server 2019 を使用している場合は、クラウドボイスメールにアップグレードする必要があります。</span><span class="sxs-lookup"><span data-stu-id="225c1-176">If you are upgrading to Skype for Business Server 2019, you can use Exchange UM in Exchange Server 2013 or 2016, but you must upgrade to Cloud Voicemail if you are using Exchange Server 2019.</span></span>
- <span data-ttu-id="225c1-177">Exchange Server 2019 にアップグレードしていて、以前のバージョンの Exchange Server UM を Skype for Business Server voice messaging に対して使用している場合は、メールボックスをアップグレードする前に、Skype for Business Server 2019 にアップグレードすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="225c1-177">If you are upgrading to Exchange Server 2019, and you are using previous versions of Exchange Server UM for Skype for Business Server voice messaging, Microsoft recommends that you upgrade to Skype for Business Server 2019 before the mailbox upgrade.</span></span>  <span data-ttu-id="225c1-178">それ以外の場合、音声メッセージング機能は失われます。</span><span class="sxs-lookup"><span data-stu-id="225c1-178">Otherwise, voice messaging capabilities will be lost.</span></span>
- <span data-ttu-id="225c1-179">Skype for Business Server 2019 にアップグレードするときに、Skype for Business Server 2015 が Exchange Online UM を使用してボイスメール用に構成されている場合、ユーザーのボイスメールは、アカウントが Skype for Business Server の2019に移動されるときに、Exchange Online UM からクラウドボイスメールに自動的に移行されます。</span><span class="sxs-lookup"><span data-stu-id="225c1-179">If you are upgrading to Skype for Business Server 2019, and have Skype for Business Server 2015 configured for voicemail with Exchange Online UM, users' voicemail will automatically migrate from Exchange Online UM to Cloud Voicemail when their account is moved to Skype for Business Server 2019.</span></span> 

<span data-ttu-id="225c1-180">移行の計画の詳細については、「 [Plan For Skype for Business server And Exchange server migration](plan-um-migration.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="225c1-180">For more information about planning your migration, see [Plan for Skype for Business Server and Exchange Server migration](plan-um-migration.md).</span></span>
