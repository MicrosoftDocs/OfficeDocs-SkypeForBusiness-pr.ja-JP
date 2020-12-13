---
title: オンプレミス ユーザー向けクラウド ボイスメール サービスを計画する|PBX Skype for Business Server 2019
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
description: この記事では、Microsoft クラウド ボイスメール サービスを実装するための利点、計画に関する考慮事項、および要件について説明します。 クラウド ボイスメールの構成の詳細については、「クラウド ボイスメールの構成」を参照してください。
ms.openlocfilehash: 8a75c670448cf69cf6d9d772c670c9451fd94f80
ms.sourcegitcommit: 975f81d9e595dfb339550625d7cef8ad84449e20
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/12/2020
ms.locfileid: "49662092"
---
# <a name="plan-cloud-voicemail-service-for-on-premises-users"></a><span data-ttu-id="f58ef-104">オンプレミス ユーザー向けクラウド ボイスメール サービスを計画する</span><span class="sxs-lookup"><span data-stu-id="f58ef-104">Plan Cloud Voicemail service for on-premises users</span></span>

## <a name="overview"></a><span data-ttu-id="f58ef-105">概要</span><span class="sxs-lookup"><span data-stu-id="f58ef-105">Overview</span></span>

<span data-ttu-id="f58ef-106">この記事では、オンプレミス ユーザー向け Microsoft クラウド ボイスメール サービスを実装するための利点、計画に関する考慮事項、および要件について説明します。</span><span class="sxs-lookup"><span data-stu-id="f58ef-106">This article describes benefits, planning considerations, and requirements for implementing the Microsoft Cloud Voicemail service for your on-premises users.</span></span> <span data-ttu-id="f58ef-107">クラウド ボイスメールの構成の詳細については、「クラウド ボイスメール サービス [の構成」を参照してください](configure-cloud-voicemail.md)。</span><span class="sxs-lookup"><span data-stu-id="f58ef-107">For information on configuring Cloud Voicemail, see [Configure Cloud Voicemail service](configure-cloud-voicemail.md).</span></span>

<span data-ttu-id="f58ef-108">クラウド ボイスメールは、Exchange Server 2019 または Exchange Online 上にメールボックスを持つ Skype for Business 2019 音声ユーザー向け音声メッセージング機能を提供する際に、Exchange ユニファイド メッセージング (UM) の代用です。</span><span class="sxs-lookup"><span data-stu-id="f58ef-108">Cloud Voicemail takes the place of Exchange Unified Messaging (UM) in providing voice messaging functionality for Skype for Business 2019 voice users who have mailboxes on Exchange Server 2019 or Exchange Online.</span></span> <span data-ttu-id="f58ef-109">クラウド ボイスメールは、オンプレミスユーザーとオンライン ユーザーの両方に次の利点があります。</span><span class="sxs-lookup"><span data-stu-id="f58ef-109">Cloud Voicemail provides the following benefits for both your on-premises and online users:</span></span>

- <span data-ttu-id="f58ef-110">拡張音声トランスクリプションを使用したボイスメールの応答および入金機能</span><span class="sxs-lookup"><span data-stu-id="f58ef-110">Voicemail answering and deposit functionality with enhanced speech transcription</span></span>

- <span data-ttu-id="f58ef-111">Skype for Business Online または Outlook クライアントを使用してユーザーの Exchange メールボックスのボイスメールにアクセスする</span><span class="sxs-lookup"><span data-stu-id="f58ef-111">Access to voicemail in the user's Exchange mailbox by using the Skype for Business Online or Outlook clients</span></span>

- <span data-ttu-id="f58ef-112">Microsoft 365 管理センターを使用してボイスメール オプションを管理する機能</span><span class="sxs-lookup"><span data-stu-id="f58ef-112">The ability to use the Microsoft 365 admin center to manage voicemail options</span></span>

- <span data-ttu-id="f58ef-113">オンプレミスまたはクラウドでの Exchange メールボックスのサポート</span><span class="sxs-lookup"><span data-stu-id="f58ef-113">Support for Exchange mailboxes on premises or in the cloud</span></span>

- <span data-ttu-id="f58ef-114">Exchange Online ユニファイド メッセージングからの既存のユーザー案内応答の活用</span><span class="sxs-lookup"><span data-stu-id="f58ef-114">Leveraging of existing user greetings from Exchange Online Unified Messaging</span></span>

> [!Important]
> <span data-ttu-id="f58ef-115">Skype for Business Online は 2021 年 7 月 31 日に廃止され、その後、ユーザーは Skype for Business Online クライアントを介して Exchange メールボックスのボイスメールにアクセスできなくなりました。</span><span class="sxs-lookup"><span data-stu-id="f58ef-115">Skype for Business Online will be retired on July 31, 2021 after which users will no longer be able to access voicemail in their Exchange mailbox through the Skype for Business Online client.</span></span>

<span data-ttu-id="f58ef-116">機能の比較の詳細については [、「Plan for Skype for Business Server and Exchange Server migration](plan-um-migration.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f58ef-116">For more information about feature comparison, see [Plan for Skype for Business Server and Exchange Server migration](plan-um-migration.md).</span></span>

<span data-ttu-id="f58ef-117">Skype for Business Server 2019 は、メールボックスが以前のバージョンの Exchange Server (2013、2016) にあるユーザーに対して引き続き Exchange UM を使用します。</span><span class="sxs-lookup"><span data-stu-id="f58ef-117">Skype for Business Server 2019 continues to use Exchange UM for users whose mailboxes are on previous versions of Exchange Server (2013, 2016).</span></span>  <span data-ttu-id="f58ef-118">skype for Business Server 2019 または Exchange Server 2019 への移行を計画する上で、Exchange Server および Skype for Business Server のバージョンに基づいて使用されるボイスメール ソリューションを理解することが重要です。</span><span class="sxs-lookup"><span data-stu-id="f58ef-118">Understanding which voicemail solution will be used based on the Exchange Server and Skype for Business Server version is an important part of planning for migration to either Skype for Business Server 2019 or Exchange Server 2019.</span></span> <span data-ttu-id="f58ef-119">移行と相互運用性の詳細については [、「Plan for Skype for Business Server and Exchange Server migration](plan-um-migration.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f58ef-119">For more information about migration and interoperability, see [Plan for Skype for Business Server and Exchange Server migration](plan-um-migration.md).</span></span>

<span data-ttu-id="f58ef-120">クラウド ボイスメールを使用すると、次の理由から管理タスクが大幅に簡素化されます。</span><span class="sxs-lookup"><span data-stu-id="f58ef-120">With Cloud Voicemail, your administration tasks are greatly simplified because:</span></span>

- <span data-ttu-id="f58ef-121">Exchange UM の役割を構成する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="f58ef-121">There is no need to configure the Exchange UM role.</span></span>
- <span data-ttu-id="f58ef-122">クラウド ボイスメールのセットアップ タスクは簡単です。</span><span class="sxs-lookup"><span data-stu-id="f58ef-122">The setup tasks for Cloud Voicemail are simpler.</span></span>
- <span data-ttu-id="f58ef-123">ボイスメール機能の更新プログラムはクラウドに直接配信されます。そのため、ユーザーは常に、累積的な更新プログラム (CUs) への依存が少ない最新の機能と更新プログラムにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="f58ef-123">Updates to voicemail functionality are delivered directly in the cloud, so your users always have access to the latest features and updates with less dependency on Cumulative Updates (CUs).</span></span>
- <span data-ttu-id="f58ef-124">オンプレミスの Exchange メールボックスとオンライン Exchange メールボックスの両方に対して同じ一連のコントロールを使用できます。</span><span class="sxs-lookup"><span data-stu-id="f58ef-124">You have the same set of controls for both on-premises and online Exchange mailboxes.</span></span> <span data-ttu-id="f58ef-125">これらのコントロールの詳細については、「電話システム ボイスメールのセットアップ [」を参照してください](https://support.office.com/article/Set-up-Phone-System-voicemail-Admin-help-9c590873-b014-4df3-9e27-1bb97322a79d)。</span><span class="sxs-lookup"><span data-stu-id="f58ef-125">For more information on these controls, see [Set up Phone System voicemail](https://support.office.com/article/Set-up-Phone-System-voicemail-Admin-help-9c590873-b014-4df3-9e27-1bb97322a79d).</span></span>

<span data-ttu-id="f58ef-126">次の図は、ハイブリッド展開でのクラウド ボイスメールを示しています。</span><span class="sxs-lookup"><span data-stu-id="f58ef-126">The following diagram shows Cloud Voicemail in a hybrid deployment:</span></span>

![SfB クラウド ボイスメール](../../sfbserver2019/media/plan-cloud-voice-mail-server1.png)

<span data-ttu-id="f58ef-128">応答のない呼び出しは、次のように処理されます。</span><span class="sxs-lookup"><span data-stu-id="f58ef-128">Unanswered calls are handled as follows:</span></span>  

1. <span data-ttu-id="f58ef-129">オンプレミスの Skype for Business 2019 にホームしているユーザーの場合、応答のない通話はオンプレミスの Skype for Business Server からオンライン クラウド ボイスメール サービスに送信されます。</span><span class="sxs-lookup"><span data-stu-id="f58ef-129">For users homed in Skype for Business 2019 on premises, unanswered calls are sent by the on-premises Skype for Business Server to the online Cloud Voicemail service.</span></span>
2. <span data-ttu-id="f58ef-130">サービスは、トランスクリプションを含むボイスメールを処理します。</span><span class="sxs-lookup"><span data-stu-id="f58ef-130">The service processes the voicemail, including transcription.</span></span>
3. <span data-ttu-id="f58ef-131">次に、このサービスは、メールボックスがオンプレミスかオンラインかに関わりますが、ユーザーの Exchange メールボックスにボイスメールを保存します。</span><span class="sxs-lookup"><span data-stu-id="f58ef-131">The service then deposits the voicemail in the Exchange mailbox of the user, whether the mailbox is on-premises or online.</span></span>  
4. <span data-ttu-id="f58ef-132">ユーザーは、Skype for Business または Outlook クライアントからボイスメールにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="f58ef-132">Users can access their voicemail from either their Skype for Business or Outlook client.</span></span>

## <a name="requirements"></a><span data-ttu-id="f58ef-133">Requirements</span><span class="sxs-lookup"><span data-stu-id="f58ef-133">Requirements</span></span>

<span data-ttu-id="f58ef-134">次の要件は、サポートされているトポロジに Skype for Business Server が既に展開済みである必要があります。</span><span class="sxs-lookup"><span data-stu-id="f58ef-134">The following requirements assume that you already have Skype for Business Server deployed in a supported topology.</span></span>  <span data-ttu-id="f58ef-135">要件はシナリオによって異なります。</span><span class="sxs-lookup"><span data-stu-id="f58ef-135">Your requirements depend on your scenario:</span></span>

- <span data-ttu-id="f58ef-136">既に Exchange UM をオンラインで使用している場合に Skype for Business 2019 にアップグレードする場合は、ホスト型ボイスメール ポリシーを変更し、ホスティング プロバイダーが正しく設定されていることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f58ef-136">If you are already using Exchange UM online and you upgrade to Skype for Business 2019, you will need to modify your hosted voicemail policy and verify that your hosting providers are set correctly.</span></span> <span data-ttu-id="f58ef-137">詳細については、「クラウド ボイスメール サービス [の構成」を参照してください](configure-cloud-voicemail.md)。</span><span class="sxs-lookup"><span data-stu-id="f58ef-137">For more information, see [Configure Cloud Voicemail service](configure-cloud-voicemail.md).</span></span>

- <span data-ttu-id="f58ef-138">Exchange UM をオンプレミスで使用している場合、または Exchange UM をオンラインとオンプレミスで使用しているユーザーが混在している場合は、ホストボイスメール ポリシーとホスティング プロバイダーの両方を変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f58ef-138">If you are using Exchange UM on premises, or you have a mix of users using Exchange UM online and on premises, you will need modify both your hosted voicemail policy and hosting provider.</span></span>  <span data-ttu-id="f58ef-139">詳細については、「クラウド ボイスメール サービス [の構成」を参照してください](configure-cloud-voicemail.md)。</span><span class="sxs-lookup"><span data-stu-id="f58ef-139">For more information, see [Configure Cloud Voicemail service](configure-cloud-voicemail.md).</span></span>

- <span data-ttu-id="f58ef-140">クラウド ボイスメールの新しい構成については、「クラウド ボイスメール サービスの構成」で説明 [されている手順に従います](configure-cloud-voicemail.md)。</span><span class="sxs-lookup"><span data-stu-id="f58ef-140">For a new configuration of Cloud Voicemail, follow the steps outlined in [Configure Cloud Voicemail service](configure-cloud-voicemail.md).</span></span>

<span data-ttu-id="f58ef-141">上記の要件に加えて、Microsoft クラウド ボイスメール サービスに接続するように以下の要件を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f58ef-141">In addition to the requirements above, the below requirements must be configured to connect to the Microsoft Cloud Voicemail service:</span></span>

- <span data-ttu-id="f58ef-142">ハイブリッド接続。</span><span class="sxs-lookup"><span data-stu-id="f58ef-142">Hybrid connectivity.</span></span> <span data-ttu-id="f58ef-143">Skype for Business Server を既に展開済みで、オンプレミス ユーザーに対してクラウド ボイスメールを有効にする場合は、オンプレミス環境とオンライン環境の間にハイブリッド接続が設定されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="f58ef-143">If you already have Skype for Business Server deployed, and you want to enable Cloud Voicemail for your on-premises users, you must ensure that you have hybrid connectivity set up between your on-premises and online environments.</span></span> <span data-ttu-id="f58ef-144">これは、分割ドメイン構成とも呼ばれる場合があります。</span><span class="sxs-lookup"><span data-stu-id="f58ef-144">This is sometimes called a split domain configuration.</span></span>

   <span data-ttu-id="f58ef-145">詳細については [、「Plan hybrid connectivity between Skype for Business Server and Microsoft 365 or Office 365](plan-hybrid-connectivity.md) and [Configure hybrid connectivity between Skype for Business Server and Office 365](configure-hybrid-connectivity.md).</span><span class="sxs-lookup"><span data-stu-id="f58ef-145">For more information, see [Plan hybrid connectivity between Skype for Business Server and Microsoft 365 or Office 365](plan-hybrid-connectivity.md) and [Configure hybrid connectivity between Skype for Business Server and Office 365](configure-hybrid-connectivity.md).</span></span>

- <span data-ttu-id="f58ef-146">オンプレミス のユーザーは、Skype for Business Server でエンタープライズ VoIPボイスメールに対して有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="f58ef-146">On-premises users must be enabled for Enterprise Voice and Hosted Voicemail in Skype for Business Server.</span></span>

- <span data-ttu-id="f58ef-147">外部 Exchange Web サービス (EWS) の URL と自動検出を設定する必要があります。設定するか、クラウド ボイスメール機能の一部が制限されます。</span><span class="sxs-lookup"><span data-stu-id="f58ef-147">An External Exchange Web Services (EWS) URL and Autodiscover must be set up or some Cloud Voicemail features will be limited.</span></span>

- <span data-ttu-id="f58ef-148">オンプレミスの Exchange サーバーがある場合は、「メールボックス ユーザー用にクラウド ボイスメールをセットアップする」の手順に従ってクラウド ボイス [メールExchange Server設定します](https://docs.microsoft.com/microsoftteams/set-up-phone-system-voicemail#set-up-cloud-voicemail-for-exchange-server-mailbox-users)。</span><span class="sxs-lookup"><span data-stu-id="f58ef-148">If you have an on-premises Exchange server, set up Cloud Voicemail using the steps in [Set up Cloud Voicemail for Exchange Server Mailbox Users](https://docs.microsoft.com/microsoftteams/set-up-phone-system-voicemail#set-up-cloud-voicemail-for-exchange-server-mailbox-users).</span></span>

## <a name="migration-and-interoperability"></a><span data-ttu-id="f58ef-149">移行と相互運用性</span><span class="sxs-lookup"><span data-stu-id="f58ef-149">Migration and interoperability</span></span>

<span data-ttu-id="f58ef-150">Skype for Business Server 2019 または Exchange Server 2019 の展開を計画している場合は、ボイス メッセージングの継続的なサービスを確保するために、移行を慎重に計画する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f58ef-150">If you are planning to deploy Skype for Business Server 2019 and/or Exchange Server 2019, you must plan your migration carefully to ensure continued service for voice messaging.</span></span> <span data-ttu-id="f58ef-151">以下の点にご注意ください:</span><span class="sxs-lookup"><span data-stu-id="f58ef-151">Keep the following in mind:</span></span>

- <span data-ttu-id="f58ef-152">Exchange Server 2019 では Exchange UM 機能が提供されなくなりました</span><span class="sxs-lookup"><span data-stu-id="f58ef-152">Exchange Server 2019 no longer provides Exchange UM functionality</span></span>
- <span data-ttu-id="f58ef-153">Skype for Business Server 2019 は Exchange Online UM と統合されなくなりました</span><span class="sxs-lookup"><span data-stu-id="f58ef-153">Skype for Business Server 2019 no longer integrates with Exchange Online UM</span></span>

<span data-ttu-id="f58ef-154">次の表に、クラウド ボイスメールのバージョンの相互運用性とサポートされるトポロジを示します。この表は、ユーザーがホームにしている可能性がある Skype for Business Server のバージョンと、Exchange メールボックスを提供する可能なバージョンを比較しています。</span><span class="sxs-lookup"><span data-stu-id="f58ef-154">Version interoperability and supported topologies for Cloud Voicemail are listed in the following table, which compares the Skype for Business Server versions the user might be homed on with the possible version providing their Exchange Mailbox.</span></span> <span data-ttu-id="f58ef-155">Exchange Online または Exchange Server 2019 で Skype for Business 2019 を使用する場合は、クラウド ボイスメールを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f58ef-155">You need to use Cloud Voicemail if you want to use Skype for Business 2019 with Exchange Online or Exchange Server 2019.</span></span>

| | <span data-ttu-id="f58ef-156">Exchange Server 2013</span><span class="sxs-lookup"><span data-stu-id="f58ef-156">Exchange Server 2013</span></span> | <span data-ttu-id="f58ef-157">Exchange Server 2016</span><span class="sxs-lookup"><span data-stu-id="f58ef-157">Exchange Server 2016</span></span> | <span data-ttu-id="f58ef-158">Exchange Server 2019</span><span class="sxs-lookup"><span data-stu-id="f58ef-158">Exchange Server 2019</span></span> | <span data-ttu-id="f58ef-159">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="f58ef-159">Exchange Online</span></span>   |
|:---    |:--- |:--- |:--- |:---  |
| <span data-ttu-id="f58ef-160">Skype for Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="f58ef-160">Skype for Business Server 2019</span></span> | <span data-ttu-id="f58ef-161">Exchange Server UM</span><span class="sxs-lookup"><span data-stu-id="f58ef-161">Exchange Server UM</span></span> | <span data-ttu-id="f58ef-162">Exchange Server UM</span><span class="sxs-lookup"><span data-stu-id="f58ef-162">Exchange Server UM</span></span> | <span data-ttu-id="f58ef-163">クラウド ボイスメール</span><span class="sxs-lookup"><span data-stu-id="f58ef-163">Cloud Voicemail</span></span> | <span data-ttu-id="f58ef-164">クラウド ボイスメール</span><span class="sxs-lookup"><span data-stu-id="f58ef-164">Cloud Voicemail</span></span> |
| <span data-ttu-id="f58ef-165">Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="f58ef-165">Skype for Business Server 2015</span></span> | <span data-ttu-id="f58ef-166">Exchange Server UM</span><span class="sxs-lookup"><span data-stu-id="f58ef-166">Exchange Server UM</span></span> | <span data-ttu-id="f58ef-167">Exchange Server UM</span><span class="sxs-lookup"><span data-stu-id="f58ef-167">Exchange Server UM</span></span> | <span data-ttu-id="f58ef-168">サポートされていません</span><span class="sxs-lookup"><span data-stu-id="f58ef-168">Not supported</span></span> | <span data-ttu-id="f58ef-169">クラウド ボイスメール</span><span class="sxs-lookup"><span data-stu-id="f58ef-169">Cloud Voicemail</span></span> |
| <span data-ttu-id="f58ef-170">Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f58ef-170">Lync Server 2013</span></span> <br>  | <span data-ttu-id="f58ef-171">Exchange Server UM</span><span class="sxs-lookup"><span data-stu-id="f58ef-171">Exchange Server UM</span></span> | <span data-ttu-id="f58ef-172">Exchange Server UM</span><span class="sxs-lookup"><span data-stu-id="f58ef-172">Exchange Server UM</span></span> | <span data-ttu-id="f58ef-173">サポート対象外</span><span class="sxs-lookup"><span data-stu-id="f58ef-173">Not Supported</span></span> | <span data-ttu-id="f58ef-174">クラウド ボイスメール</span><span class="sxs-lookup"><span data-stu-id="f58ef-174">Cloud Voicemail</span></span> |

<span data-ttu-id="f58ef-175">Microsoft では、次の移行パスをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="f58ef-175">Microsoft recommends the following migration paths:</span></span>

- <span data-ttu-id="f58ef-176">Skype for Business Server 2019 にアップグレードする場合は、Exchange Server 2013 または 2016 の Exchange UM を使用できますが、Exchange Server 2019 を使用している場合はクラウド ボイスメールにアップグレードする必要があります。</span><span class="sxs-lookup"><span data-stu-id="f58ef-176">If you are upgrading to Skype for Business Server 2019, you can use Exchange UM in Exchange Server 2013 or 2016, but you must upgrade to Cloud Voicemail if you are using Exchange Server 2019.</span></span>
- <span data-ttu-id="f58ef-177">Exchange Server 2019 にアップグレードする場合に、以前のバージョンの Exchange Server UM for Skype for Business Server ボイス メッセージングを使用している場合は、メールボックスのアップグレードの前に Skype for Business Server 2019 にアップグレードしてください。</span><span class="sxs-lookup"><span data-stu-id="f58ef-177">If you are upgrading to Exchange Server 2019, and you are using previous versions of Exchange Server UM for Skype for Business Server voice messaging, Microsoft recommends that you upgrade to Skype for Business Server 2019 before the mailbox upgrade.</span></span>  <span data-ttu-id="f58ef-178">そうしないと、音声メッセージング機能が失われます。</span><span class="sxs-lookup"><span data-stu-id="f58ef-178">Otherwise, voice messaging capabilities will be lost.</span></span>
- <span data-ttu-id="f58ef-179">Skype for Business Server 2019 にアップグレードし、Skype for Business Server 2015 が Exchange Online UM のボイスメール用に構成されている場合、ユーザーのアカウントが Skype for Business Server 2019 に移動すると、ユーザーのボイスメールは Exchange Online UM からクラウド ボイスメールに自動的に移行されます。</span><span class="sxs-lookup"><span data-stu-id="f58ef-179">If you are upgrading to Skype for Business Server 2019, and have Skype for Business Server 2015 configured for voicemail with Exchange Online UM, users' voicemail will automatically migrate from Exchange Online UM to Cloud Voicemail when their account is moved to Skype for Business Server 2019.</span></span> 

<span data-ttu-id="f58ef-180">移行の計画の詳細については [、「Plan for Skype for Business Server and Exchange Server migration](plan-um-migration.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f58ef-180">For more information about planning your migration, see [Plan for Skype for Business Server and Exchange Server migration](plan-um-migration.md).</span></span>
