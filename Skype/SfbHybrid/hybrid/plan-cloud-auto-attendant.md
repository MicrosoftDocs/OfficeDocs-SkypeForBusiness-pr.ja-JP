---
title: クラウド自動応答を計画する
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: wasseemh
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: Skype for Business Server 2019 でのクラウド自動応答の使用の概要
ms.openlocfilehash: 50cd9bb8b20e44d750dab68ec6fecb30bd02e203
ms.sourcegitcommit: 212b2985591ca1109eb3643fbb49d8b18ab07a70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/21/2021
ms.locfileid: "49918693"
---
# <a name="plan-cloud-auto-attendants"></a><span data-ttu-id="37813-103">クラウド自動応答の計画</span><span class="sxs-lookup"><span data-stu-id="37813-103">Plan Cloud auto attendants</span></span>

<span data-ttu-id="37813-104">Exchange ユニファイド メッセージング (Exchange Server 2013 または Exchange Server 2016) で使用される自動応答は、Exchange Server 2019 または Exchange Online では使用できなくなりました。</span><span class="sxs-lookup"><span data-stu-id="37813-104">The auto attendant used with Exchange Unified Messaging (Exchange Server 2013 or Exchange Server 2016) is no longer available in Exchange Server 2019 or Exchange Online.</span></span> <span data-ttu-id="37813-105">Skype for Business Server 2019 の実装がこれらの Exchange バージョンのいずれかと統合されている場合は、電話システムに関連付けられているオンラインクラウド音声機能を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="37813-105">If your implementation of Skype for Business Server 2019 integrates with either of these Exchange versions, you'll need to use the online Cloud Voice features associated with Phone System.</span></span> <span data-ttu-id="37813-106">Exchange Server 2013 および 2016 にホームに Exchange UM サービスを移行する方法については [、「Plan for Skype for Business Server and Exchange Server](plan-um-migration.md) migration」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="37813-106">See [Plan for Skype for Business Server and Exchange Server migration](plan-um-migration.md) for information about moving Exchange UM services homed on Exchange server 2013 and 2016 to the cloud.</span></span>

<span data-ttu-id="37813-107">つまり、自動応答のようなユニファイド メッセージング機能を使用する場合は、Skype for Business Server 2019 のハイブリッド実装が必要になります。</span><span class="sxs-lookup"><span data-stu-id="37813-107">This inherently means that you will have a hybrid implementation of Skype for Business Server 2019 if you wish to use Unified Messaging features like auto attendants.</span></span> <span data-ttu-id="37813-108">詳細 [については、「Skype for Business Server と Microsoft 365 または Office 365](configure-hybrid-connectivity.md) の間のハイブリッド接続を構成する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="37813-108">See [Configure hybrid connectivity between Skype for Business Server and Microsoft 365 or Office 365](configure-hybrid-connectivity.md) for details.</span></span>

<span data-ttu-id="37813-109">自動応答は、顧客の呼び出しを受け付けて案内応答を再生し、メニュー オプションを提供し、音声またはダイヤル パッドを使用して発信者と対話して、通話を適切な宛先にルーティングするクラウド サービスです。</span><span class="sxs-lookup"><span data-stu-id="37813-109">An auto attendant is a cloud service that accepts customer calls and plays greetings, provides them with menu options, and interacts with callers using speech or the dial pad to route their calls to the right destination.</span></span> <span data-ttu-id="37813-110">各自動応答には、Microsoft Teams 管理センターの自動応答に直接リンクされるリソース アカウント *(「* リソース アカウントの構成」を [参照)](configure-onprem-ra.md)が Skype for Business Server 2019 システムに割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="37813-110">Each auto attendant is assigned a *resource account* (see [Configure resource accounts](configure-onprem-ra.md)) on your Skype for Business Server 2019 system that will be linked directly to an auto attendant in the Microsoft Teams admin center.</span></span> <span data-ttu-id="37813-111">自動 [応答とは何か](/SkypeForBusiness/what-is-phone-system-in-office-365/what-are-phone-system-auto-attendants.md) 、自動応答に関するオプションと機能の詳細については、「クラウド自動応答とは」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="37813-111">See [What are Cloud auto attendants?](/SkypeForBusiness/what-is-phone-system-in-office-365/what-are-phone-system-auto-attendants.md) for more detail on what auto attendants are and what options and features exist for auto attendants.</span></span>

> [!NOTE]
> <span data-ttu-id="37813-112">複数の Microsoft サービス番号、ダイレクト ルーティング番号、またはハイブリッド番号を自動応答に割り当てできます。</span><span class="sxs-lookup"><span data-stu-id="37813-112">You can assign multiple Microsoft service numbers, Direct Routing numbers, or hybrid numbers to an auto attendant.</span></span>

<span data-ttu-id="37813-113">クラウド自動応答への着信呼び出しは、次に示すように、いくつかのパスのいずれかを受け取る場合があります。</span><span class="sxs-lookup"><span data-stu-id="37813-113">An incoming call to a Cloud auto attendant can take one of several paths, as shown here:</span></span>

![自動応答の図](../../SfBServer2019/media/AA-plan-concept.png)

1. <span data-ttu-id="37813-115">Skype for Business Server 2019 経由</span><span class="sxs-lookup"><span data-stu-id="37813-115">Via Skype for Business Server 2019</span></span>
2. <span data-ttu-id="37813-116">セッション ボーダー[コントローラーとダイレクト](/MicrosoftTeams/direct-routing-border-controllers.md)[ルーティングを使用する](/MicrosoftTeams/direct-routing-plan.md)</span><span class="sxs-lookup"><span data-stu-id="37813-116">Via a [Session Border Controller](/MicrosoftTeams/direct-routing-border-controllers.md) and [Direct Routing](/MicrosoftTeams/direct-routing-plan.md)</span></span>
3. <span data-ttu-id="37813-117">Microsoft 365 または Microsoft 365 にOffice。</span><span class="sxs-lookup"><span data-stu-id="37813-117">Via a number homed online in Microsoft 365 or Office 365.</span></span>

<span data-ttu-id="37813-118">以下も参照してください。</span><span class="sxs-lookup"><span data-stu-id="37813-118">Also see:</span></span>

- [<span data-ttu-id="37813-119">クラウドの自動応答をセットアップする</span><span class="sxs-lookup"><span data-stu-id="37813-119">Set up a Cloud auto attendant</span></span>](/microsoftteams/create-a-phone-system-auto-attendant)
- [<span data-ttu-id="37813-120">着信呼び出しへの自動応答とルーティング</span><span class="sxs-lookup"><span data-stu-id="37813-120">Automatically answer and route incoming calls</span></span>](https://docs.microsoft.com/exchange/voice-mail-unified-messaging/automatically-answer-and-route-calls/automatically-answer-and-route-calls)

## <a name="requirements"></a><span data-ttu-id="37813-121">要件</span><span class="sxs-lookup"><span data-stu-id="37813-121">Requirements</span></span>

<span data-ttu-id="37813-122">次の要件は、サポートされているトポロジに Skype for Business Server 2019 が既に展開済みである必要があります。</span><span class="sxs-lookup"><span data-stu-id="37813-122">The following requirements assume that you already have Skype for Business Server 2019 deployed in a supported topology.</span></span>  <span data-ttu-id="37813-123">要件はシナリオによって異なります。</span><span class="sxs-lookup"><span data-stu-id="37813-123">Your requirements depend on your scenario:</span></span>

- <span data-ttu-id="37813-124">Exchange UM をオンラインまたはオンプレミスで既に使用している場合に、Skype for Business 2019 にアップグレードする場合は、自動応答の構造をキャプチャし、クラウドの自動応答を使用してクラウドに再作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="37813-124">If you are already using Exchange UM online or on-premises and you upgrade to Skype for Business 2019, you will need to capture the structure of your Auto attendants and re-create them in the cloud using Cloud auto attendants.</span></span> <span data-ttu-id="37813-125">詳細については、「Exchange UM 自動応答または呼び出しキューを電話システムに移動 [する」を参照してください](configure-onprem-ra.md#moving-an-exchange-um-auto-attendant-or-call-queue-to-phone-system)。</span><span class="sxs-lookup"><span data-stu-id="37813-125">For more information, see [Moving an Exchange UM auto attendant or call queue to Phone System](configure-onprem-ra.md#moving-an-exchange-um-auto-attendant-or-call-queue-to-phone-system).</span></span>

- <span data-ttu-id="37813-126">クラウド自動応答の新しい構成については、「リソース アカウントの構成」で説明されている  [手順に従います](configure-onprem-ra.md)。</span><span class="sxs-lookup"><span data-stu-id="37813-126">For a new configuration of Cloud auto attendants, follow the steps outlined in  [Configure resource accounts](configure-onprem-ra.md).</span></span>

<span data-ttu-id="37813-127">上記の要件に加えて、Microsoft Cloud 自動応答サービスに接続するには、次の要件を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="37813-127">In addition to the requirements above, the below requirements must be configured to connect to the Microsoft Cloud auto attendant service:</span></span>

- <span data-ttu-id="37813-128">ハイブリッド接続。</span><span class="sxs-lookup"><span data-stu-id="37813-128">Hybrid connectivity.</span></span> <span data-ttu-id="37813-129">Skype for Business Server を既に展開済みで、オンプレミス ユーザーに対してクラウド自動応答を有効にする場合は、オンプレミス環境とオンライン環境の間にハイブリッド接続が設定されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="37813-129">If you already have Skype for Business Server deployed, and you want to enable Cloud auto attendant for your on-premises users, you must ensure that you have hybrid connectivity set up between your on-premises and online environments.</span></span> <span data-ttu-id="37813-130">これは、分割ドメイン構成とも呼ばれる場合があります。</span><span class="sxs-lookup"><span data-stu-id="37813-130">This is sometimes called a split domain configuration.</span></span>

   <span data-ttu-id="37813-131">詳細については [、「Plan hybrid connectivity between Skype for Business Server and Microsoft 365 or Office 365](plan-hybrid-connectivity.md) and [Configure hybrid connectivity between Skype for Business Server and Microsoft 365 or Office 365](configure-hybrid-connectivity.md).</span><span class="sxs-lookup"><span data-stu-id="37813-131">For more information, see [Plan hybrid connectivity between Skype for Business Server and Microsoft 365 or Office 365](plan-hybrid-connectivity.md) and [Configure hybrid connectivity between Skype for Business Server and Microsoft 365 or Office 365](configure-hybrid-connectivity.md).</span></span>

- <span data-ttu-id="37813-132">自動応答に電話番号を割り当てる場合は、Office [365 Enterprise E5 ライセンスが必要](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/license-options-based-on-your-plan/office-365-enterprise-e5-with-audio-conferencing) です。</span><span class="sxs-lookup"><span data-stu-id="37813-132">If you're assigning a phone number to to your auto attendant, you will need an [Office 365 Enterprise E5](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/license-options-based-on-your-plan/office-365-enterprise-e5-with-audio-conferencing) license.</span></span>
- <span data-ttu-id="37813-133">自動応答ごとにオンライン[リソース アカウント](/MicrosoftTeams/manage-resource-accounts.md)または[](configure-onprem-ra.md)オンプレミス リソース アカウントを作成し、電話番号とライセンスを割り当てる。</span><span class="sxs-lookup"><span data-stu-id="37813-133">Create an online [resource account](/MicrosoftTeams/manage-resource-accounts.md) or on-premises [resource account](configure-onprem-ra.md) for each auto attendant, and assign phone numbers and licenses.</span></span> 

## <a name="migration-and-interoperability"></a><span data-ttu-id="37813-134">移行と相互運用性</span><span class="sxs-lookup"><span data-stu-id="37813-134">Migration and interoperability</span></span>

<span data-ttu-id="37813-135">Skype for Business Server 2019 または Exchange Server 2019 の展開を計画している場合は、自動応答の継続的なサポートを確保するために、移行を慎重に計画する必要があります。</span><span class="sxs-lookup"><span data-stu-id="37813-135">If you are planning to deploy Skype for Business Server 2019 and/or Exchange Server 2019, you must plan your migration carefully to ensure continued support for auto attendants.</span></span> <span data-ttu-id="37813-136">以下の点にご注意ください:</span><span class="sxs-lookup"><span data-stu-id="37813-136">Keep the following in mind:</span></span>

- <span data-ttu-id="37813-137">Exchange Server 2019 では Exchange UM 機能が提供されなくなりました</span><span class="sxs-lookup"><span data-stu-id="37813-137">Exchange Server 2019 no longer provides Exchange UM functionality</span></span>
- <span data-ttu-id="37813-138">Exchange ユニファイド メッセージングがサポート終了モード</span><span class="sxs-lookup"><span data-stu-id="37813-138">Exchange Unified Messaging is in retirement mode</span></span>
- <span data-ttu-id="37813-139">Skype for Business Server 2019 は Exchange Online UM と統合されなくなりました</span><span class="sxs-lookup"><span data-stu-id="37813-139">Skype for Business Server 2019 no longer integrates with Exchange Online UM</span></span>

<span data-ttu-id="37813-140">クラウド自動応答は、Skype for Business Server 2019、2015、および 2013 を使用して構成できます。</span><span class="sxs-lookup"><span data-stu-id="37813-140">Cloud auto attendants can be configured with Skype for Business Server 2019, 2015, and 2013.</span></span>

<span data-ttu-id="37813-141">Microsoft では、次の移行パスをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="37813-141">Microsoft recommends the following migration paths:</span></span>

- <span data-ttu-id="37813-142">Skype for Business Server 2019 にアップグレードする場合は、Exchange Server 2013 または 2016 の Exchange UM を使用できますが、Exchange Server 2019 を使用している場合はクラウド自動応答にアップグレードする必要があります。</span><span class="sxs-lookup"><span data-stu-id="37813-142">If you are upgrading to Skype for Business Server 2019, you can use Exchange UM in Exchange Server 2013 or 2016, but you must upgrade to Cloud auto attendant if you are using Exchange Server 2019.</span></span>

- <span data-ttu-id="37813-143">Exchange Server 2019 にアップグレードする場合に、以前のバージョンの Exchange Server UM for Skype for Business Server ボイス メッセージングを使用している場合は、メールボックスのアップグレードの前に Skype for Business Server 2019 にアップグレードしてください。</span><span class="sxs-lookup"><span data-stu-id="37813-143">If you are upgrading to Exchange Server 2019, and you are using previous versions of Exchange Server UM for Skype for Business Server voice messaging, Microsoft recommends that you upgrade to Skype for Business Server 2019 before the mailbox upgrade.</span></span>  <span data-ttu-id="37813-144">そうしないと、音声メッセージング機能が失われます。</span><span class="sxs-lookup"><span data-stu-id="37813-144">Otherwise, voice messaging capabilities will be lost.</span></span>

<span data-ttu-id="37813-145">移行の計画の詳細については [、「Plan for Skype for Business Server and Exchange Server migration](plan-um-migration.md).</span><span class="sxs-lookup"><span data-stu-id="37813-145">For more information about planning your migration, see [Plan for Skype for Business Server and Exchange Server migration](plan-um-migration.md).</span></span>

### <a name="migrating-a-previously-implemented-exchange-um-auto-attendant-system"></a><span data-ttu-id="37813-146">以前に実装した Exchange UM 自動応答システムの移行</span><span class="sxs-lookup"><span data-stu-id="37813-146">Migrating a previously implemented Exchange UM auto attendant system</span></span>

<span data-ttu-id="37813-147">現在、Exchange 2013 または 2016 で作成された UM 自動応答システムのクラウドへの自動移行はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="37813-147">Currently we don't support automated migration to the Cloud of a UM auto attendant system created in Exchange 2013 or 2016.</span></span> <span data-ttu-id="37813-148">自動応答システムを手動で再作成するには、次の操作を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="37813-148">To manually re-create an auto attendant system, you'll need to:</span></span>

1. <span data-ttu-id="37813-149">Exchange 管理 PowerShell コマンドを使用して、入れ子になった自動応答や通話キューなど、古い自動応答システムの構造を確認します。</span><span class="sxs-lookup"><span data-stu-id="37813-149">Use Exchange admin PowerShell commands to review the structure of the old auto attendant system, including any nested auto attendants and call queues.</span></span>  
2. <span data-ttu-id="37813-150">各 UM 自動応答ノードに関連付けられた音声合成スクリプトまたは録音されたメッセージのコピーを作成します。</span><span class="sxs-lookup"><span data-stu-id="37813-150">Create copies of text-to-speech scripts or recorded messages associated with each UM auto attendant node.</span></span>
3. <span data-ttu-id="37813-151">テスト用の電話番号とライセンスをオブジェクトに割り当てるなど、各自動応答ノードのオンプレミス エンドポイントを作成します。</span><span class="sxs-lookup"><span data-stu-id="37813-151">Create on premise endpoints for each auto attendant node, including assigning a test phone numbers and licenses to the objects.</span></span> <span data-ttu-id="37813-152">これで、電話システムのようなオンライン サービスで使用されるオンプレミスの電話番号ライセンスを割り当てる機能が追加されました。</span><span class="sxs-lookup"><span data-stu-id="37813-152">Note that you now have the ability to assign on-premise phone numbers licenses used by online services like Phone System.</span></span>
4. <span data-ttu-id="37813-153">Microsoft Teams と電話システムを使用して、新しいクラウド自動応答サービスを実装します。</span><span class="sxs-lookup"><span data-stu-id="37813-153">Implement a new Cloud auto attendant service with Microsoft Teams and Phone System.</span></span> <span data-ttu-id="37813-154">実装の [詳細については、「リソース アカウントを構成](configure-onprem-ra.md) する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="37813-154">See [Configure resource accounts](configure-onprem-ra.md) for implementation details.</span></span> <span data-ttu-id="37813-155">これを行う場合は、音声合成スクリプトまたは各 UM 自動応答ノードに関連付けられている録音されたメッセージをアップロードします。</span><span class="sxs-lookup"><span data-stu-id="37813-155">As you do this, upload the text-to-speech scripts or recorded messages associated with each UM auto attendant node.</span></span>
5. <span data-ttu-id="37813-156">クラウド自動応答の機能をテストします。</span><span class="sxs-lookup"><span data-stu-id="37813-156">Test the functionality of the Cloud auto attendant.</span></span>
6. <span data-ttu-id="37813-157">古い Exchange UM 自動応答に割り当てられている電話番号を、新しく作成したメインクラウド自動応答に再割り当てします。</span><span class="sxs-lookup"><span data-stu-id="37813-157">Reassign the phone number assigned to the old Exchange UM auto attendant to the newly created main Cloud auto attendant.</span></span>

<span data-ttu-id="37813-158">これらの [手順の詳細については、「Exchange UM 自動応答または通話キューを電話システム](configure-onprem-ra.md#moving-an-exchange-um-auto-attendant-or-call-queue-to-phone-system) に移動する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="37813-158">See [Moving an Exchange UM auto attendant or call queue to Phone System](configure-onprem-ra.md#moving-an-exchange-um-auto-attendant-or-call-queue-to-phone-system) for details on these steps.</span></span>

<span data-ttu-id="37813-159">ニーズを満たす構造と、顧客を効率的にガイドするスクリプトがある場合は、「リソース アカウントを構成する」に [進んでください](configure-onprem-ra.md)。</span><span class="sxs-lookup"><span data-stu-id="37813-159">When you have a solid structure that meets your needs and a script that guides customers efficiently, proceed to [Configure resource accounts](configure-onprem-ra.md).</span></span>

> [!CAUTION]
> <span data-ttu-id="37813-160">[KB4480742](https://support.microsoft.com/help/4480742/call-failures-and-500-server-internal-error-after-migration-to-2019)で説明したように、Server 2015 で作成された Exchange UM 自動応答を Server 2019 を実行しているサーバーに移動しないでください。</span><span class="sxs-lookup"><span data-stu-id="37813-160">As mentioned in [KB4480742](https://support.microsoft.com/help/4480742/call-failures-and-500-server-internal-error-after-migration-to-2019), moving Exchange UM auto attendants created in Server 2015 to servers running Server 2019 is discouraged.</span></span> <span data-ttu-id="37813-161">当分の間、共存モードで実行されている Skype for Business Server 2015 プールに保持する必要があります。</span><span class="sxs-lookup"><span data-stu-id="37813-161">For the time being, you'd have to keep them on a Skype for Business Server 2015 pool running in coexistance mode.</span></span>

## <a name="see-also"></a><span data-ttu-id="37813-162">関連項目</span><span class="sxs-lookup"><span data-stu-id="37813-162">See Also</span></span>

[<span data-ttu-id="37813-163">Skype for Business Server と Exchange Server の移行の計画</span><span class="sxs-lookup"><span data-stu-id="37813-163">Plan for Skype for Business Server and Exchange Server migration</span></span>](plan-um-migration.md)

[<span data-ttu-id="37813-164">リソース アカウントの構成</span><span class="sxs-lookup"><span data-stu-id="37813-164">Configure resource accounts</span></span>](configure-onprem-ra.md)

[<span data-ttu-id="37813-165">電話ユーザー インターフェイスでカスタム プロンプト録音を有効にする</span><span class="sxs-lookup"><span data-stu-id="37813-165">Enable custom prompt recording using the telephone user interface</span></span>](https://docs.microsoft.com/exchange/voice-mail-unified-messaging/greetings-announcements-menus-and-prompts/enable-custom-prompt-recording)

[<span data-ttu-id="37813-166">クラウドの自動応答とは</span><span class="sxs-lookup"><span data-stu-id="37813-166">What are Cloud auto attendants?</span></span>](/SkypeForBusiness/what-is-phone-system-in-office-365/what-are-phone-system-auto-attendants)

[<span data-ttu-id="37813-167">クラウドの自動応答をセットアップする</span><span class="sxs-lookup"><span data-stu-id="37813-167">Set up a Cloud auto attendant</span></span>](/microsoftteams/create-a-phone-system-auto-attendant)

<span data-ttu-id="37813-168">Exchange UM: [着信呼び出しに自動的に応答してルーティングする](https://docs.microsoft.com/exchange/voice-mail-unified-messaging/automatically-answer-and-route-calls/automatically-answer-and-route-calls)</span><span class="sxs-lookup"><span data-stu-id="37813-168">Exchange UM: [Automatically answer and route incoming calls](https://docs.microsoft.com/exchange/voice-mail-unified-messaging/automatically-answer-and-route-calls/automatically-answer-and-route-calls)</span></span>

[<span data-ttu-id="37813-169">Skype for Business Server と Microsoft 365 または Office 365 の間のハイブリッド接続を計画する</span><span class="sxs-lookup"><span data-stu-id="37813-169">Plan hybrid connectivity between Skype for Business Server and Microsoft 365 or Office 365</span></span>](plan-hybrid-connectivity.md)

[<span data-ttu-id="37813-170">Skype for Business Server と Microsoft 365 または Office 365 の間のハイブリッド接続を構成する</span><span class="sxs-lookup"><span data-stu-id="37813-170">Configure hybrid connectivity between Skype for Business Server and Microsoft 365 or Office 365</span></span>](configure-hybrid-connectivity.md)

[<span data-ttu-id="37813-171">KB4480742: 連絡先オブジェクトを Skype for Business Server 2019 に移動した後、サブスクライバー アクセスまたは自動応答への呼び出しが高速ビジーおよび "500 Server Internal" エラーで失敗する</span><span class="sxs-lookup"><span data-stu-id="37813-171">KB4480742: Calls to Subscriber Access or auto attendant fail with fast busy and “500 Server Internal" error after moving contact objects to Skype for Business Server 2019</span></span>](https://support.microsoft.com/help/4480742/call-failures-and-500-server-internal-error-after-migration-to-2019)
