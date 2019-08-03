---
title: クラウド自動応答を計画する
ms.author: jambirk
author: jambirk
manager: serdars
ms.reviewer: wasseemh
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: Skype for Business Server 2019 でのクラウド自動応答の使用の概要
ms.openlocfilehash: 1a5f1aad4cd983f1f3839f47c54404d168ecf7f0
ms.sourcegitcommit: 016beacc8b64eaeeaefb641360dd9bb8d2191c4a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/29/2019
ms.locfileid: "36160663"
---
# <a name="plan-cloud-auto-attendants"></a><span data-ttu-id="af53d-103">クラウド自動応答を計画する</span><span class="sxs-lookup"><span data-stu-id="af53d-103">Plan Cloud auto attendants</span></span>

<span data-ttu-id="af53d-104">Exchange ユニファイドメッセージング (Exchange Server 2013 または Exchange Server 2016) で使用される自動応答は、Exchange Server 2019 または Exchange Online では使用できなくなりました。</span><span class="sxs-lookup"><span data-stu-id="af53d-104">The auto attendant used with Exchange Unified Messaging (Exchange Server 2013 or Exchange Server 2016) is no longer available in Exchange Server 2019 or Exchange Online.</span></span> <span data-ttu-id="af53d-105">Skype for Business Server 2019 の実装が、これらのいずれかの Exchange バージョンと統合されている場合は、電話システムに関連付けられているオンラインクラウド音声機能を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="af53d-105">If your implementation of Skype for Business Server 2019 integrates with either of these Exchange versions, you'll need to use the online Cloud Voice features associated with Phone System.</span></span> <span data-ttu-id="af53d-106">Exchange server 2013 および2016に所属する Exchange UM サービスをクラウドに移行する方法については、「 [Plan For Skype For Business server And Exchange server migration](plan-um-migration.md) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="af53d-106">See [Plan for Skype for Business Server and Exchange Server migration](plan-um-migration.md) for information about moving Exchange UM services homed on Exchange server 2013 and 2016 to the cloud.</span></span>

<span data-ttu-id="af53d-107">これは本質的に、自動応答などのユニファイドメッセージング機能を使用したい場合に、Skype for Business Server 2019 のハイブリッド実装を行うことを意味します。</span><span class="sxs-lookup"><span data-stu-id="af53d-107">This inherently means that you will have a hybrid implementation of Skype for Business Server 2019 if you wish to use Unified Messaging features like auto attendants.</span></span> <span data-ttu-id="af53d-108">詳細については[、「Skype For Business Server と Office 365 の間のハイブリッド接続の構成](configure-hybrid-connectivity.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="af53d-108">See [Configure hybrid connectivity between Skype for Business Server and Office 365](configure-hybrid-connectivity.md) for details.</span></span>

<span data-ttu-id="af53d-109">自動応答とは、お客様の電話を受け取って、案内応答を受け取り、メニューオプションを提供し、音声または dialpad を使用して発信者と対話し、正しい宛先に通話をルーティングするクラウドサービスです。</span><span class="sxs-lookup"><span data-stu-id="af53d-109">An Auto attendant is a cloud service that accept customer calls and play greetings, provide them with menu options, and interact with callers using speech or the dialpad to route their calls to the right destination.</span></span> <span data-ttu-id="af53d-110">各自動応答には、Microsoft Teams 管理センターの自動応答に直接リンクされる Skype for Business Server 2019 システムの**リソースアカウント**(「[リソースアカウントの構成](configure-onprem-ra.md)」を参照) が割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="af53d-110">Each auto attendant is assigned a **resource account** (see[Configure resource accounts](configure-onprem-ra.md)) on your Skype for Business Server 2019 system that will be linked directly to an auto attendant in the Microsoft Teams admin center.</span></span> <span data-ttu-id="af53d-111">自動応答に関する詳細については、「[クラウド自動応答とは](/SkypeForBusiness/what-is-phone-system-in-office-365/what-are-phone-system-auto-attendants.md)」を参照してください。自動応答にはどのようなオプションと機能がありますか。</span><span class="sxs-lookup"><span data-stu-id="af53d-111">See [What are Cloud auto attendants?](/SkypeForBusiness/what-is-phone-system-in-office-365/what-are-phone-system-auto-attendants.md) for more detail on what auto attendants are and what options and features exist for auto attendants.</span></span>

> [!NOTE]
> <span data-ttu-id="af53d-112">自動応答には、複数の Microsoft サービス番号またはハイブリッド番号を割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="af53d-112">You can assign multiple Microsoft service numbers or hybrid numbers to an auto attendant.</span></span>

<span data-ttu-id="af53d-113">クラウド自動応答への着信は、次に示すように、いくつかのパスのいずれかを受け取ることができます。</span><span class="sxs-lookup"><span data-stu-id="af53d-113">An incoming call to a Cloud auto attendant can take one of several paths, as shown here:</span></span>

![自動応答の図](../../SfBServer2019/media/AA-plan-concept.png)

1. <span data-ttu-id="af53d-115">Skype for Business Server 2019 経由</span><span class="sxs-lookup"><span data-stu-id="af53d-115">Via Skype for Business Server 2019</span></span>
2. <span data-ttu-id="af53d-116">[セッションボーダーコントローラー](/MicrosoftTeams/direct-routing-border-controllers.md)と[直接ルーティング](/MicrosoftTeams/direct-routing-plan.md)を介して</span><span class="sxs-lookup"><span data-stu-id="af53d-116">Via a [Session Border Controller](/MicrosoftTeams/direct-routing-border-controllers.md) and [Direct Routing](/MicrosoftTeams/direct-routing-plan.md)</span></span>
3. <span data-ttu-id="af53d-117">Office 365 でオンラインになっている番号を使用します。</span><span class="sxs-lookup"><span data-stu-id="af53d-117">Via a number homed online in Office 365.</span></span>

<span data-ttu-id="af53d-118">以下も参照してください。</span><span class="sxs-lookup"><span data-stu-id="af53d-118">Also see:</span></span>

- [<span data-ttu-id="af53d-119">クラウドの自動応答を設定する</span><span class="sxs-lookup"><span data-stu-id="af53d-119">Set up a Cloud auto attendant</span></span>](/microsoftteams/create-a-phone-system-auto-attendant)
- [<span data-ttu-id="af53d-120">着信呼び出しへの自動応答とルーティング</span><span class="sxs-lookup"><span data-stu-id="af53d-120">Automatically answer and route incoming calls</span></span>](https://docs.microsoft.com/exchange/voice-mail-unified-messaging/automatically-answer-and-route-calls/automatically-answer-and-route-calls)

## <a name="requirements"></a><span data-ttu-id="af53d-121">要件</span><span class="sxs-lookup"><span data-stu-id="af53d-121">Requirements</span></span>

<span data-ttu-id="af53d-122">次の要件は、サポートされているトポロジで Skype for Business Server 2019 が既に展開されていることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="af53d-122">The following requirements assume that you already have Skype for Business Server 2019 deployed in a supported topology.</span></span>  <span data-ttu-id="af53d-123">要件は、シナリオによって異なります。</span><span class="sxs-lookup"><span data-stu-id="af53d-123">Your requirements depend on your scenario:</span></span>

- <span data-ttu-id="af53d-124">既に Exchange UM online またはオンプレミスを使用している場合、Skype for Business 2019 にアップグレードするには、自動応答の構造をキャプチャし、クラウドの自動応答を使用してクラウドで再作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="af53d-124">If you are already using Exchange UM online or on premises and you upgrade to Skype for Business 2019, you will need to capture the structure of your Auto attendants and re-create them in the cloud using Cloud auto attendants.</span></span> <span data-ttu-id="af53d-125">詳細については、「 [EXCHANGE UM 自動応答またはコールキューを電話システムに移行する](configure-onprem-ra.md#moving-an-exchange-um-auto-attendant-or-call-queue-to-phone-system)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="af53d-125">For more information, see [Moving an Exchange UM auto attendant or call queue to Phone System](configure-onprem-ra.md#moving-an-exchange-um-auto-attendant-or-call-queue-to-phone-system).</span></span>

- <span data-ttu-id="af53d-126">クラウド自動応答の新しい構成については、「 [Configure resource accounts](configure-onprem-ra.md)」に記載されている手順に従ってください。</span><span class="sxs-lookup"><span data-stu-id="af53d-126">For a new configuration of Cloud auto attendants, follow the steps outlined in  [Configure resource accounts](configure-onprem-ra.md).</span></span>

<span data-ttu-id="af53d-127">上記の要件に加えて、次の要件を構成して、Microsoft クラウド自動応答サービスに接続する必要があります。</span><span class="sxs-lookup"><span data-stu-id="af53d-127">In addition to the requirements above, the below requirements must be configured to connect to the Microsoft Cloud auto attendant service:</span></span>

- <span data-ttu-id="af53d-128">ハイブリッド接続。</span><span class="sxs-lookup"><span data-stu-id="af53d-128">Hybrid connectivity.</span></span> <span data-ttu-id="af53d-129">Skype for Business Server を既に展開しており、オンプレミスのユーザーに対してクラウドの自動応答を有効にする場合は、オンプレミスの環境とオンライン環境の間でハイブリッド接続が設定されていることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="af53d-129">If you already have Skype for Business Server deployed, and you want to enable Cloud auto attendant for your on-premises users, you must ensure that you have hybrid connectivity set up between your on-premises and online environments.</span></span> <span data-ttu-id="af53d-130">これは、分割ドメイン構成と呼ばれることがあります。</span><span class="sxs-lookup"><span data-stu-id="af53d-130">This is sometimes called a split domain configuration.</span></span>

   <span data-ttu-id="af53d-131">詳細については、「skype for business [server と office 365 の間のハイブリッド接続を計画](plan-hybrid-connectivity.md)する」および「 [Skype for Business server と office 365 の間のハイブリッド接続を構成する](configure-hybrid-connectivity.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="af53d-131">For more information, see [Plan hybrid connectivity between Skype for Business Server and Office 365](plan-hybrid-connectivity.md) and [Configure hybrid connectivity between Skype for Business Server and Office 365](configure-hybrid-connectivity.md).</span></span>

- <span data-ttu-id="af53d-132">自動応答に電話番号を割り当てる場合は、 [Office 365 Enterprise E5](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/license-options-based-on-your-plan/office-365-enterprise-e5-with-audio-conferencing)ライセンスが必要です。</span><span class="sxs-lookup"><span data-stu-id="af53d-132">If you're assigning a phone number to to your auto attendant, you will need an [Office 365 Enterprise E5](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/license-options-based-on-your-plan/office-365-enterprise-e5-with-audio-conferencing) license.</span></span>
- <span data-ttu-id="af53d-133">各自動応答に対してオンプレミスの[リソースアカウント](/MicrosoftTeams/manage-resource-accounts.md)を作成し、電話番号とライセンスを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="af53d-133">Create an on-premises [resource account](/MicrosoftTeams/manage-resource-accounts.md) for each auto attendant, and assign phone numbers and licenses.</span></span> 

## <a name="migration-and-interoperability"></a><span data-ttu-id="af53d-134">移行と相互運用性</span><span class="sxs-lookup"><span data-stu-id="af53d-134">Migration and interoperability</span></span>

<span data-ttu-id="af53d-135">Skype for Business Server 2019 または Exchange Server 2019 の展開を計画している場合は、自動応答を引き続きサポートするように、移行を慎重に計画する必要があります。</span><span class="sxs-lookup"><span data-stu-id="af53d-135">If you are planning to deploy Skype for Business Server 2019 and/or Exchange Server 2019, you must plan your migration carefully to ensure continued support for auto attendants.</span></span> <span data-ttu-id="af53d-136">以下の点にご注意ください。</span><span class="sxs-lookup"><span data-stu-id="af53d-136">Keep the following in mind:</span></span>

- <span data-ttu-id="af53d-137">Exchange Server 2019 が Exchange UM 機能を提供しなくなった</span><span class="sxs-lookup"><span data-stu-id="af53d-137">Exchange Server 2019 no longer provides Exchange UM functionality</span></span>
- <span data-ttu-id="af53d-138">Exchange ユニファイドメッセージングオンラインが定年モードである</span><span class="sxs-lookup"><span data-stu-id="af53d-138">Exchange Unified Messaging Online is in retirement mode</span></span>
- <span data-ttu-id="af53d-139">Skype for Business Server 2019 が Exchange Online UM と統合されなくなりました</span><span class="sxs-lookup"><span data-stu-id="af53d-139">Skype for Business Server 2019 no longer integrates with Exchange Online UM</span></span>

<span data-ttu-id="af53d-140">クラウド自動応答は、Skype for Business Server 2019、2015、および2013を使用して構成できます。</span><span class="sxs-lookup"><span data-stu-id="af53d-140">Cloud auto attendants can be configured with Skype for Business Server 2019, 2015, and 2013.</span></span>

<span data-ttu-id="af53d-141">Microsoft では、次の移行パスをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="af53d-141">Microsoft recommends the following migration paths:</span></span>

- <span data-ttu-id="af53d-142">Skype for Business Server 2019 にアップグレードする場合は、exchange Server 2013 または2016で Exchange UM を使用できますが、Exchange Server 2019 を使用している場合は、クラウドの自動応答にアップグレードする必要があります。</span><span class="sxs-lookup"><span data-stu-id="af53d-142">If you are upgrading to Skype for Business Server 2019, you can use Exchange UM in Exchange Server 2013 or 2016, but you must upgrade to Cloud auto attendant if you are using Exchange Server 2019.</span></span>

- <span data-ttu-id="af53d-143">Exchange Server 2019 にアップグレードしていて、以前のバージョンの Exchange Server UM を Skype for Business Server voice messaging に対して使用している場合は、メールボックスをアップグレードする前に、Skype for Business Server 2019 にアップグレードすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="af53d-143">If you are upgrading to Exchange Server 2019, and you are using previous versions of Exchange Server UM for Skype for Business Server voice messaging, Microsoft recommends that you upgrade to Skype for Business Server 2019 before the mailbox upgrade.</span></span>  <span data-ttu-id="af53d-144">それ以外の場合、音声メッセージング機能は失われます。</span><span class="sxs-lookup"><span data-stu-id="af53d-144">Otherwise, voice messaging capabilities will be lost.</span></span>

<span data-ttu-id="af53d-145">移行の計画の詳細については、「 [Plan For Skype for Business server And Exchange server migration](plan-um-migration.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="af53d-145">For more information about planning your migration, see [Plan for Skype for Business Server and Exchange Server migration](plan-um-migration.md).</span></span>

### <a name="migrating-a-previously-implemented-exchange-um-auto-attendant-system"></a><span data-ttu-id="af53d-146">以前に実装された Exchange UM 自動応答システムを移行する</span><span class="sxs-lookup"><span data-stu-id="af53d-146">Migrating a previously implemented Exchange UM auto attendant system</span></span>

<span data-ttu-id="af53d-147">現時点では、Exchange 2013 または2016で作成された UM 自動応答システムのクラウドへの自動移行はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="af53d-147">Currently we don't support automated migration to the Cloud of a UM auto attendant system created in Exchange 2013 or 2016.</span></span> <span data-ttu-id="af53d-148">自動応答システムを手動で再作成するには、次の操作を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="af53d-148">To manually re-create an auto attendant system, you'll need to:</span></span>

1. <span data-ttu-id="af53d-149">Exchange 管理者の powershell コマンドを使用して、ネストされた自動応答と呼び出しキューを含む、古い自動応答システムの構造を確認します。</span><span class="sxs-lookup"><span data-stu-id="af53d-149">Use Exchange admin powershell commands to review the structure of the old auto attendant system, including any nested auto attendants and call queues.</span></span>  
2. <span data-ttu-id="af53d-150">各 UM 自動応答ノードに関連付けられている音声合成スクリプトまたは録音済みメッセージのコピーを作成します。</span><span class="sxs-lookup"><span data-stu-id="af53d-150">Create copies of text-to-speech scripts or recorded messages associated with each UM auto attendant node.</span></span>
3. <span data-ttu-id="af53d-151">テスト電話番号とライセンスをオブジェクトに割り当てることを含め、各自動応答ノードに対してオンプレミスエンドポイントを作成します。</span><span class="sxs-lookup"><span data-stu-id="af53d-151">Create on premise endpoints for each auto attendant node, including assigning a test phone numbers and licenses to the objects.</span></span> <span data-ttu-id="af53d-152">電話システムのようなオンラインサービスで使用される、オンプレミスの電話番号ライセンスを割り当てることができるようになりました。</span><span class="sxs-lookup"><span data-stu-id="af53d-152">Note that you now have the ability to assign on-premise phone numbers licenses used by online services like Phone System.</span></span>
4. <span data-ttu-id="af53d-153">Skype for Business Online と電話システムを使用して、新しいクラウド自動応答サービスを実装します。</span><span class="sxs-lookup"><span data-stu-id="af53d-153">Implement a new Cloud auto attendant service with Skype for Business Online and Phone System.</span></span> <span data-ttu-id="af53d-154">実装の詳細については、「 [Configure resource accounts](configure-onprem-ra.md) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="af53d-154">See [Configure resource accounts](configure-onprem-ra.md) for implementation details.</span></span> <span data-ttu-id="af53d-155">この場合は、各 UM 自動応答ノードに関連付けられている音声合成スクリプトまたは録音済みメッセージをアップロードします。</span><span class="sxs-lookup"><span data-stu-id="af53d-155">As you do this, upload the text-to-speech scripts or recorded messages associated with each UM auto attendant node.</span></span>
5. <span data-ttu-id="af53d-156">クラウド自動応答の機能をテストします。</span><span class="sxs-lookup"><span data-stu-id="af53d-156">Test the functionality of the Cloud auto attendant.</span></span>
6. <span data-ttu-id="af53d-157">古い Exchange UM 自動応答に割り当てられている電話番号を、新しく作成したメインクラウド自動応答に再割り当てします。</span><span class="sxs-lookup"><span data-stu-id="af53d-157">Reassign the phone number assigned to the old Exchange UM auto attendant to the newly created main Cloud auto attendant.</span></span>

<span data-ttu-id="af53d-158">これらの手順の詳細について[は、「EXCHANGE UM 自動応答またはコールキューを電話システムに移行する](configure-onprem-ra.md#moving-an-exchange-um-auto-attendant-or-call-queue-to-phone-system)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="af53d-158">See [Moving an Exchange UM auto attendant or call queue to Phone System](configure-onprem-ra.md#moving-an-exchange-um-auto-attendant-or-call-queue-to-phone-system) for details on these steps.</span></span>

## <a name="additional-planning-resources"></a><span data-ttu-id="af53d-159">その他の計画に関するリソース</span><span class="sxs-lookup"><span data-stu-id="af53d-159">Additional planning resources</span></span>

<span data-ttu-id="af53d-160">「[小規模企業の例-自動応答の設定](/microsoftteams/tutorial-org-aa)」というタイトルのチュートリアルでは、ユーザーのニーズに関する情報の収集、自動応答とユーザーの構成 (および場合によっては呼び出しキュー) の計画、およびメニュープロンプトの作成のプロセスについて説明します。オンライン管理センターでプランを実装します。</span><span class="sxs-lookup"><span data-stu-id="af53d-160">The tutorial titled [Small business example - Set up an auto attendant](/microsoftteams/tutorial-org-aa) goes through the process of gathering information about user needs, planning a structure of auto attendants and users (and possibly call queues), writing the menu prompts, and implementing the plan in the Online Admin center.</span></span> <span data-ttu-id="af53d-161">チュートリアルを確認し、そこにある演習を使用して計画を作成します。</span><span class="sxs-lookup"><span data-stu-id="af53d-161">review the tutorial and use the exercises there to create your plan.</span></span>

<span data-ttu-id="af53d-162">お客様のニーズを満たす堅固な構造を持っていて、顧客に効率的に対応するスクリプトを実行している場合は、「[リソースアカウントを構成](configure-onprem-ra.md)する」に進みます。</span><span class="sxs-lookup"><span data-stu-id="af53d-162">When you have a solid structure that meets your needs and a script that guides customers efficiently, proceed to [Configure resource accounts](configure-onprem-ra.md).</span></span>

> [!CAUTION]
> <span data-ttu-id="af53d-163">[KB4480742](https://support.microsoft.com/en-us/help/4480742/call-failures-and-500-server-internal-error-after-migration-to-2019)で説明したように、サーバー2015で作成された Exchange UM 自動応答をサーバー2019を実行しているサーバーに移動しないことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="af53d-163">As mentioned in [KB4480742](https://support.microsoft.com/en-us/help/4480742/call-failures-and-500-server-internal-error-after-migration-to-2019), moving Exchange UM auto attendants created in Server 2015 to servers running Server 2019 is discouraged.</span></span> <span data-ttu-id="af53d-164">そのため、その時間は共存モードで実行されている Skype for business Server 2015 プールに保持する必要があります。</span><span class="sxs-lookup"><span data-stu-id="af53d-164">For the time being, you'd have to keep them on a Skype for Business Server 2015 pool running in coexistance mode.</span></span>

## <a name="see-also"></a><span data-ttu-id="af53d-165">関連項目</span><span class="sxs-lookup"><span data-stu-id="af53d-165">See Also</span></span>

[<span data-ttu-id="af53d-166">Skype for Business Server および Exchange Server の移行を計画する</span><span class="sxs-lookup"><span data-stu-id="af53d-166">Plan for Skype for Business Server and Exchange Server migration</span></span>](plan-um-migration.md)

[<span data-ttu-id="af53d-167">リソースアカウントを構成する</span><span class="sxs-lookup"><span data-stu-id="af53d-167">Configure resource accounts</span></span>](configure-onprem-ra.md)

[<span data-ttu-id="af53d-168">電話ユーザー インターフェイスでカスタム プロンプト録音を有効にする</span><span class="sxs-lookup"><span data-stu-id="af53d-168">Enable custom prompt recording using the telephone user interface</span></span>](https://docs.microsoft.com/exchange/voice-mail-unified-messaging/greetings-announcements-menus-and-prompts/enable-custom-prompt-recording)

[<span data-ttu-id="af53d-169">クラウド自動応答とは</span><span class="sxs-lookup"><span data-stu-id="af53d-169">What are Cloud auto attendants?</span></span>](/SkypeForBusiness/what-is-phone-system-in-office-365/what-are-phone-system-auto-attendants)

[<span data-ttu-id="af53d-170">クラウドの自動応答を設定する</span><span class="sxs-lookup"><span data-stu-id="af53d-170">Set up a Cloud auto attendant</span></span>](/microsoftteams/create-a-phone-system-auto-attendant)

<span data-ttu-id="af53d-171">Exchange UM:[着信呼び出しへの自動応答とルーティング](https://docs.microsoft.com/exchange/voice-mail-unified-messaging/automatically-answer-and-route-calls/automatically-answer-and-route-calls)</span><span class="sxs-lookup"><span data-stu-id="af53d-171">Exchange UM: [Automatically answer and route incoming calls](https://docs.microsoft.com/exchange/voice-mail-unified-messaging/automatically-answer-and-route-calls/automatically-answer-and-route-calls)</span></span>

[<span data-ttu-id="af53d-172">Skype for Business Server と Office 365 の間のハイブリッド接続を計画する</span><span class="sxs-lookup"><span data-stu-id="af53d-172">Plan hybrid connectivity between Skype for Business Server and Office 365</span></span>](plan-hybrid-connectivity.md)

[<span data-ttu-id="af53d-173">Skype for Business Server と Office 365 の間のハイブリッド接続を構成する</span><span class="sxs-lookup"><span data-stu-id="af53d-173">Configure hybrid connectivity between Skype for Business Server and Office 365</span></span>](configure-hybrid-connectivity.md)

[<span data-ttu-id="af53d-174">KB4480742: contact オブジェクトを Skype for Business Server 2019 に移動した後、fast busy および "500 Server Internal" エラーが発生し、サブスクライバーアクセスまたは自動応答への呼び出しが失敗する</span><span class="sxs-lookup"><span data-stu-id="af53d-174">KB4480742: Calls to Subscriber Access or auto attendant fail with fast busy and “500 Server Internal" error after moving contact objects to Skype for Business Server 2019</span></span>](https://support.microsoft.com/help/4480742/call-failures-and-500-server-internal-error-after-migration-to-2019)
