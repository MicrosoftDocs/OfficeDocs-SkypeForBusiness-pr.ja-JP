---
title: クラウドのボイスメール サービスを計画します。
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: この資料では、利点、計画に関する考慮事項、およびマイクロソフトのクラウドのボイスメール サービスを実装するための要件について説明します。 クラウドのボイス メールの構成方法の詳細については、クラウドのボイスメールを設定するを参照してください。
ms.openlocfilehash: e307ddcb5159e51ebe26e6a5bee10f9b2ee716e9
ms.sourcegitcommit: 247747ec19c0f5c1d45fea7e5ac5318e4d5127ea
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/02/2018
ms.locfileid: "25030624"
---
# <a name="plan-cloud-voicemail-service"></a><span data-ttu-id="e727e-104">クラウドのボイスメール サービスを計画します。</span><span class="sxs-lookup"><span data-stu-id="e727e-104">Plan Cloud Voicemail service</span></span>

[!INCLUDE [disclaimer](../disclaimer.md)]

## <a name="overview"></a><span data-ttu-id="e727e-105">概要</span><span class="sxs-lookup"><span data-stu-id="e727e-105">Overview</span></span> 

<span data-ttu-id="e727e-106">この資料では、利点、計画に関する考慮事項、およびマイクロソフトのクラウドのボイスメール サービスを実装するための要件について説明します。</span><span class="sxs-lookup"><span data-stu-id="e727e-106">This article describes benefits, planning considerations, and requirements for implementing the Microsoft Cloud Voicemail service.</span></span> <span data-ttu-id="e727e-107">クラウドのボイス メールの構成方法の詳細については、[クラウドのボイス メールを構成するサービス](configure-cloud-voicemail.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e727e-107">For information on configuring Cloud Voicemail, see [Configure Cloud Voicemail service](configure-cloud-voicemail.md).</span></span>

<span data-ttu-id="e727e-108">クラウドのボイスメールに代わる Exchange ユニファイド メッセージング (UM) のメッセージング機能をユーザーのためビジネス 2019年音声 2019 の Exchange Server または Exchange Online にメールボックスを持つ Skype の音声を提供することにします。</span><span class="sxs-lookup"><span data-stu-id="e727e-108">Cloud Voicemail takes the place of Exchange Unified Messaging (UM) in providing voice messaging functionality for Skype for Business 2019 voice users who have mailboxes on Exchange Server 2019 or Exchange Online.</span></span> <span data-ttu-id="e727e-109">ボイスメールのクラウドでは、オンプレミスとオンラインのユーザーの両方の次の利点があります。</span><span class="sxs-lookup"><span data-stu-id="e727e-109">Cloud Voicemail provides the following benefits for both your on-premises and online users:</span></span>

- <span data-ttu-id="e727e-110">ボイスメールへの応答と預金の機能と強化された音声認識議事録</span><span class="sxs-lookup"><span data-stu-id="e727e-110">Voicemail answering and deposit functionality with enhanced speech transcription</span></span>

- <span data-ttu-id="e727e-111">ビジネス オンラインまたは Outlook クライアントで、Skype を使用して、ユーザーの Exchange メールボックスにボイス メールへのアクセス</span><span class="sxs-lookup"><span data-stu-id="e727e-111">Access to voicemail in the user's Exchange mailbox by using the Skype for Business Online or Outlook clients</span></span> 

- <span data-ttu-id="e727e-112">ボイスメールのオプションを管理するために Office 365 の web ベースのポータルを使用する機能</span><span class="sxs-lookup"><span data-stu-id="e727e-112">The ability to use the Office 365 web-based portal to manage voicemail options</span></span>

- <span data-ttu-id="e727e-113">Exchange のメールボックスをオンプレミスとクラウドのためのサポート</span><span class="sxs-lookup"><span data-stu-id="e727e-113">Support for Exchange mailboxes on premises or in the cloud</span></span>

- <span data-ttu-id="e727e-114">オンライン ユニファイド メッセージングから既存のユーザーの応答メッセージの活用</span><span class="sxs-lookup"><span data-stu-id="e727e-114">Leveraging of existing user greetings from Exchange Online Unified Messaging</span></span>

<span data-ttu-id="e727e-115">機能比較の詳細については、 [Skype ビジネス サーバーと Exchange Server の移行のための計画](plan-um-migration.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e727e-115">For more information about feature comparison, see [Plan for Skype for Business Server and Exchange Server migration](plan-um-migration.md).</span></span> 

<span data-ttu-id="e727e-116">メールボックスが Exchange Server の以前のバージョンでは、ユーザーの Exchange UM を使用するビジネス サーバー 2019 の Skype を継続 (2013、2016)。</span><span class="sxs-lookup"><span data-stu-id="e727e-116">Skype for Business Server 2019 continues to use Exchange UM for users whose mailboxes are on previous versions of Exchange Server (2013, 2016).</span></span>  <span data-ttu-id="e727e-117">ビジネス サーバーの Exchange Server と Skype に基づいているのボイスメール ソリューションを使用するを理解するバージョンは、ビジネス サーバー 2019 2019 の Exchange Server のいずれかの Skype への移行の計画の重要な部分です。</span><span class="sxs-lookup"><span data-stu-id="e727e-117">Understanding which voicemail solution will be used based on the Exchange Server and Skype for Business Server version is an important part of planning for migration to either Skype for Business Server 2019 or Exchange Server 2019.</span></span> <span data-ttu-id="e727e-118">移行と相互運用性に関する詳細については、 [Skype ビジネス サーバーと Exchange Server の移行のための計画](plan-um-migration.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e727e-118">For more information about migration and interoperability, see [Plan for Skype for Business Server and Exchange Server migration](plan-um-migration.md).</span></span> 

<span data-ttu-id="e727e-119">クラウドのボイスメールを使用ため、管理作業を大幅に合理化します。</span><span class="sxs-lookup"><span data-stu-id="e727e-119">With Cloud Voicemail, your administration tasks are greatly simplified because:</span></span>

- <span data-ttu-id="e727e-120">Exchange UM の役割を構成する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="e727e-120">There is no need to configure the Exchange UM role.</span></span>
- <span data-ttu-id="e727e-121">クラウドのボイスメールの設定作業は簡単です。</span><span class="sxs-lookup"><span data-stu-id="e727e-121">The setup tasks for Cloud Voicemail are simpler.</span></span>
- <span data-ttu-id="e727e-122">ボイスメール機能への更新は、ユーザーでは、累積的な更新 (CUs) に以下の依存関係の更新プログラム、最新の機能へのアクセスを常があるので、クラウドに直接配信されます。</span><span class="sxs-lookup"><span data-stu-id="e727e-122">Updates to voicemail functionality are delivered directly in the cloud, so your users always have access to the latest features and updates with less dependency on Cumulative Updates (CUs).</span></span>
- <span data-ttu-id="e727e-123">設置とオンラインの Exchange メールボックスの両方のコントロールの同じセットがあります。</span><span class="sxs-lookup"><span data-stu-id="e727e-123">You have the same set of controls for both on-premises and online Exchange mailboxes.</span></span> <span data-ttu-id="e727e-124">これらのコントロールの詳細については、[電話システムのボイス メールの設定](https://support.office.com/en-us/article/Set-up-Phone-System-voicemail-Admin-help-9c590873-b014-4df3-9e27-1bb97322a79d?ui=en-US&rs=en-US&ad=US)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e727e-124">For more information on these controls, see [Set up Phone System voicemail](https://support.office.com/en-us/article/Set-up-Phone-System-voicemail-Admin-help-9c590873-b014-4df3-9e27-1bb97322a79d?ui=en-US&rs=en-US&ad=US).</span></span>

<span data-ttu-id="e727e-125">次の図は、ハイブリッド展開でのクラウドのボイスメールを示しています。</span><span class="sxs-lookup"><span data-stu-id="e727e-125">The following diagram shows Cloud Voicemail in a hybrid deployment:</span></span>


![デバイス クラウドのボイスメール](../../sfbserver2019/media/plan-cloud-voice-mail-server1.png)

<span data-ttu-id="e727e-127">不在時の着信は、次のように処理されます。</span><span class="sxs-lookup"><span data-stu-id="e727e-127">Unanswered calls are handled as follows:</span></span>  

1. <span data-ttu-id="e727e-128">社内のビジネス 2019年の Skype に所属していたユーザーの不在時の着信に送信されます設置 Skype でビジネス サーバーのオンラインのボイスメールのクラウド サービス。</span><span class="sxs-lookup"><span data-stu-id="e727e-128">For users homed in Skype for Business 2019 on premises, unanswered calls are sent by the on-premises Skype for Business Server to the online Cloud Voicemail service.</span></span> 
2. <span data-ttu-id="e727e-129">サービスでは、議事録を含め、ボイス メールを処理します。</span><span class="sxs-lookup"><span data-stu-id="e727e-129">The service processes the voicemail, including transcription.</span></span>
3. <span data-ttu-id="e727e-130">サービスにより、ボイスメール、ユーザーの Exchange メールボックスでメールボックスがオンプレミスであるかどうかまたはオンラインです。</span><span class="sxs-lookup"><span data-stu-id="e727e-130">The service then deposits the voicemail in the Exchange mailbox of the user, whether the mailbox is on-premises or online.</span></span>  
4. <span data-ttu-id="e727e-131">ユーザーからアクセスできる、ボイス メールいずれかのビジネスまたは Outlook クライアント用の Skype です。</span><span class="sxs-lookup"><span data-stu-id="e727e-131">Users can access their voicemail from either their Skype for Business or Outlook client.</span></span>

## <a name="requirements"></a><span data-ttu-id="e727e-132">要件</span><span class="sxs-lookup"><span data-stu-id="e727e-132">Requirements</span></span>

<span data-ttu-id="e727e-133">次の要件では、ビジネス サーバーのトポロジでサポートされている展開の Skype が既にあることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="e727e-133">The following requirements assume that you already have Skype for Business Server deployed in a supported topology.</span></span>  <span data-ttu-id="e727e-134">お客様の要件は、シナリオによって異なります。</span><span class="sxs-lookup"><span data-stu-id="e727e-134">Your requirements depend on your scenario:</span></span>

- <span data-ttu-id="e727e-135">既にを使用している Exchange UM オンライン ビジネス 2019年の Skype にアップグレードする場合は、ホスト ボイスメール ポリシーを変更し、ホスティング プロバイダーが正しく設定されていることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e727e-135">If you are already using Exchange UM online and you upgrade to Skype for Business 2019, you will need to modify your hosted voicemail policy and verify that your hosting providers are set correctly.</span></span> <span data-ttu-id="e727e-136">詳細については、[クラウドのボイス メールを構成するサービス](configure-cloud-voicemail.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e727e-136">For more information, see [Configure Cloud Voicemail service](configure-cloud-voicemail.md).</span></span>

- <span data-ttu-id="e727e-137">使用している Exchange UM の社内、または、オンライン、社内設置型の Exchange UM を使用するユーザーが混在している場合、必要がありますを変更して、ホスト ボイス メール ポリシーとホストのプロバイダー。</span><span class="sxs-lookup"><span data-stu-id="e727e-137">If you are using Exchange UM on premises, or you have a mix of users using Exchange UM online and on premises, you will need modify both your hosted voicemail policy and hosting provider.</span></span>  <span data-ttu-id="e727e-138">詳細については、[クラウドのボイス メールを構成するサービス](configure-cloud-voicemail.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e727e-138">For more information, see [Configure Cloud Voicemail service](configure-cloud-voicemail.md).</span></span>

- <span data-ttu-id="e727e-139">クラウドのボイスメールの新しい構成では、[クラウドのボイス メールを構成するサービス](configure-cloud-voicemail.md)に記載されている手順に従います。</span><span class="sxs-lookup"><span data-stu-id="e727e-139">For a new configuration of Cloud Voicemail, follow the steps outlined in [Configure Cloud Voicemail service](configure-cloud-voicemail.md).</span></span>

<span data-ttu-id="e727e-140">上記の要件に加えて、要件を満たしてマイクロソフト クラウド ボイスメール サービスへの接続を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e727e-140">In addition to the requirements above, the below requirements must be configured to connect to the Microsoft Cloud Voicemail service:</span></span>

- <span data-ttu-id="e727e-141">ハイブリッド接続です。</span><span class="sxs-lookup"><span data-stu-id="e727e-141">Hybrid connectivity.</span></span> <span data-ttu-id="e727e-142">ビジネス サーバーが展開されると、Skype が既にある、オンプレミス ユーザーのクラウドのボイスメールを有効にする場合は、ハイブリッド接続の設置とオンライン環境の設定があることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e727e-142">If you already have Skype for Business Server deployed, and you want to enable Cloud Voicemail for your on-premises users, you must ensure that you have hybrid connectivity set up between your on-premises and online environments.</span></span> <span data-ttu-id="e727e-143">分割ドメインの構成とも呼びます。</span><span class="sxs-lookup"><span data-stu-id="e727e-143">This is sometimes called a split domain configuration.</span></span> 

   <span data-ttu-id="e727e-144">詳細については、 [Skype ビジネス サーバーと Office 365 の間のハイブリッドの接続を計画](plan-hybrid-connectivity.md)し、 [Skype ビジネス サーバーと Office 365 の間のハイブリッド接続の構成](configure-hybrid-connectivity.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e727e-144">For more information, see [Plan hybrid connectivity between Skype for Business Server and Office 365](plan-hybrid-connectivity.md) and [Configure hybrid connectivity between Skype for Business Server and Office 365](configure-hybrid-connectivity.md).</span></span>

- <span data-ttu-id="e727e-145">オンプレミス ユーザーはエンタープライズ VoIP と Skype でボイスメールをホストのビジネス サーバーに対して有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="e727e-145">On-premises users must be enabled for Enterprise Voice and Hosted Voicemail in Skype for Business Server.</span></span>

- <span data-ttu-id="e727e-146">外部の Exchange Web サービス (EWS) URL と自動検出は、セットアップをする必要がありますまたはいくつかのクラウドのボイスメール機能が制限されます。</span><span class="sxs-lookup"><span data-stu-id="e727e-146">An External Exchange Web Services (EWS) URL and Autodiscover must be setup or some Cloud Voicemail features will be limited.</span></span>

-  <span data-ttu-id="e727e-147">されている、設置型のみ展開--は、Exchange およびビジネス用の Skype のみ設置型サーバー クラウドのボイスメールを活用するの PREM ライセンスが必要です。</span><span class="sxs-lookup"><span data-stu-id="e727e-147">If you have an on-premises only deployment--that is, only Exchange and Skype for Business on-premises servers--but you want to take advantage of Cloud Voicemail, you need the ON-PREM license.</span></span> 

##<a name="migration-and-interoperability"></a><span data-ttu-id="e727e-148">移行と相互運用性</span><span class="sxs-lookup"><span data-stu-id="e727e-148">Migration and interoperability</span></span>

<span data-ttu-id="e727e-149">Skype をビジネス サーバー 2019/2019 の Exchange Server の展開を計画している場合は、ボイス メッセージングの継続的なサービスを保証するには、慎重に、移行を計画する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e727e-149">If you are planning to deploy Skype for Business Server 2019 and/or Exchange Server 2019, you must plan your migration carefully to ensure continued service for voice messaging.</span></span> <span data-ttu-id="e727e-150">以下の点について留意してください。</span><span class="sxs-lookup"><span data-stu-id="e727e-150">Keep the following in mind:</span></span>

- <span data-ttu-id="e727e-151">Exchange Server 2019 Exchange UM の機能が提供されなくなります</span><span class="sxs-lookup"><span data-stu-id="e727e-151">Exchange Server 2019 no longer provides Exchange UM functionality</span></span>
- <span data-ttu-id="e727e-152">Skype ビジネス サーバー 2019 の不要になったとの統合オンライン UM</span><span class="sxs-lookup"><span data-stu-id="e727e-152">Skype for Business Server 2019 no longer integrates with Exchange Online UM</span></span>

<span data-ttu-id="e727e-153">バージョンの相互運用性およびボイスメールをクラウドでサポートされるトポロジは、次の表に表示されます。</span><span class="sxs-lookup"><span data-stu-id="e727e-153">Version interoperability and supported topologies for Cloud Voicemail are listed in the following table.</span></span> <span data-ttu-id="e727e-154">プレビュー リリースでは、クラウドのボイスメールだけが、Skype でビジネス サーバーと Exchange Server 2019、Exchange オンライン。</span><span class="sxs-lookup"><span data-stu-id="e727e-154">For the preview release, Cloud Voicemail only works with Skype for Business Server and Exchange Server 2019 or Exchange Online.</span></span>


|                               | <span data-ttu-id="e727e-155">Exchange Server 2013</span><span class="sxs-lookup"><span data-stu-id="e727e-155">Exchange Server 2013</span></span> | <span data-ttu-id="e727e-156">Exchange Server 2016</span><span class="sxs-lookup"><span data-stu-id="e727e-156">Exchange Server 2016</span></span> | <span data-ttu-id="e727e-157">Exchange Server 2019</span><span class="sxs-lookup"><span data-stu-id="e727e-157">Exchange Server 2019</span></span> | <span data-ttu-id="e727e-158">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="e727e-158">Exchange Online</span></span>   |
|:---------------------------    |:---------------------|:---------------------|:------------------|:---------------------- |
| <span data-ttu-id="e727e-159">Skype ビジネス サーバー 2019</span><span class="sxs-lookup"><span data-stu-id="e727e-159">Skype for Business Server 2019</span></span> | <span data-ttu-id="e727e-160">UM を Exchange Server</span><span class="sxs-lookup"><span data-stu-id="e727e-160">Exchange Server UM</span></span> | <span data-ttu-id="e727e-161">UM を Exchange Server</span><span class="sxs-lookup"><span data-stu-id="e727e-161">Exchange Server UM</span></span> | <span data-ttu-id="e727e-162">クラウドのボイスメール</span><span class="sxs-lookup"><span data-stu-id="e727e-162">Cloud Voicemail</span></span> | <span data-ttu-id="e727e-163">クラウドのボイスメール</span><span class="sxs-lookup"><span data-stu-id="e727e-163">Cloud Voicemail</span></span>
<span data-ttu-id="e727e-164">Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="e727e-164">Skype for Business Server 2015</span></span> | <span data-ttu-id="e727e-165">UM を Exchange Server</span><span class="sxs-lookup"><span data-stu-id="e727e-165">Exchange Server UM</span></span> | <span data-ttu-id="e727e-166">UM を Exchange Server</span><span class="sxs-lookup"><span data-stu-id="e727e-166">Exchange Server UM</span></span> |  | <span data-ttu-id="e727e-167">クラウドのボイスメール</span><span class="sxs-lookup"><span data-stu-id="e727e-167">Cloud Voicemail</span></span> <br> <span data-ttu-id="e727e-168">Exchange オンライン UM \*</span><span class="sxs-lookup"><span data-stu-id="e727e-168">Exchange Online UM\*</span></span> |
<span data-ttu-id="e727e-169">Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e727e-169">Lync Server 2013</span></span> <br>  | <span data-ttu-id="e727e-170">UM を Exchange Server</span><span class="sxs-lookup"><span data-stu-id="e727e-170">Exchange Server UM</span></span> | <span data-ttu-id="e727e-171">UM を Exchange Server</span><span class="sxs-lookup"><span data-stu-id="e727e-171">Exchange Server UM</span></span> | | <span data-ttu-id="e727e-172">クラウドのボイスメール</span><span class="sxs-lookup"><span data-stu-id="e727e-172">Cloud Voicemail</span></span> <br> <span data-ttu-id="e727e-173">Exchange オンライン UM \*</span><span class="sxs-lookup"><span data-stu-id="e727e-173">Exchange Online UM\*</span></span> |

<span data-ttu-id="e727e-174">\*まで、使用されなくなりました。</span><span class="sxs-lookup"><span data-stu-id="e727e-174">\* Until deprecated.</span></span>

<span data-ttu-id="e727e-175">マイクロソフトは、次の移行方法をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="e727e-175">Microsoft recommends the following migration paths:</span></span>

-  <span data-ttu-id="e727e-176">ビジネス サーバー 2019 の Skype にアップグレードする場合は、Exchange Server 2013 または 2016、Exchange UM を使用することができますが、2019 の Exchange Server を使用している場合、クラウドのボイスメールにアップグレードする必要があります。</span><span class="sxs-lookup"><span data-stu-id="e727e-176">If you are upgrading to Skype for Business Server 2019, you can use Exchange UM in Exchange Server 2013 or 2016, but you must upgrade to Cloud Voicemail if you are using Exchange Server 2019.</span></span>

- <span data-ttu-id="e727e-177">2019 の Exchange Server をアップグレードすると、Skype のビジネス サーバー ボイス メッセージングの UM の Exchange Server の以前のバージョンを使用して、アップグレードする Skype をビジネス サーバー 2019 メールボックス アップグレードする前にお勧めします。</span><span class="sxs-lookup"><span data-stu-id="e727e-177">If you are upgrading to Exchange Server 2019, and you are using previous versions of Exchange Server UM for Skype for Business Server voice messaging, Microsoft recommends that you upgrade to Skype for Business Server 2019 before the mailbox upgrade.</span></span>  <span data-ttu-id="e727e-178">それ以外の場合、ボイス メッセージ機能は失われます。</span><span class="sxs-lookup"><span data-stu-id="e727e-178">Otherwise, voice messaging capabilities will be lost.</span></span> 


<span data-ttu-id="e727e-179">移行を計画の詳細については、 [Skype ビジネス サーバーと Exchange Server の移行のための計画](plan-um-migration.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e727e-179">For more information about planning your migration, see [Plan for Skype for Business Server and Exchange Server migration](plan-um-migration.md).</span></span>
