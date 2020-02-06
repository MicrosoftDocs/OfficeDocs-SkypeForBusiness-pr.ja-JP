---
title: Skype for Business Server 用のフロントエンドサーバー VoIP コンポーネント
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 310e81a7-da45-47d4-95d0-92837e386502
description: 翻訳サービスやさまざまなルーティングコンポーネントなど、Skype for Business Server のフロントエンドサーバーにあるエンタープライズボイスコンポーネントについて説明します。
ms.openlocfilehash: eae2f389720a6c359f442a7a163d5b4b5aef6e26
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41802967"
---
# <a name="front-end-server-voip-components-for-skype-for-business-server"></a><span data-ttu-id="d73c3-103">Skype for Business Server 用のフロントエンドサーバー VoIP コンポーネント</span><span class="sxs-lookup"><span data-stu-id="d73c3-103">Front End Server VoIP components for Skype for Business Server</span></span>

<span data-ttu-id="d73c3-104">翻訳サービスやさまざまなルーティングコンポーネントなど、Skype for Business Server のフロントエンドサーバーにあるエンタープライズボイスコンポーネントについて説明します。</span><span class="sxs-lookup"><span data-stu-id="d73c3-104">Learn about the Enterprise Voice components that are located on Front End Servers in Skype for Business Server, including translation service and various routing components.</span></span>

<span data-ttu-id="d73c3-105">フロントエンドサーバーにある VoIP コンポーネントは、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="d73c3-105">The VoIP components located on Front End Servers are as follows:</span></span>

- <span data-ttu-id="d73c3-106">変換サービス</span><span class="sxs-lookup"><span data-stu-id="d73c3-106">Translation Service</span></span>

- <span data-ttu-id="d73c3-107">着信ルーティング コンポーネント</span><span class="sxs-lookup"><span data-stu-id="d73c3-107">Inbound Routing component</span></span>

- <span data-ttu-id="d73c3-108">発信ルーティング コンポーネント</span><span class="sxs-lookup"><span data-stu-id="d73c3-108">Outbound Routing component</span></span>

- <span data-ttu-id="d73c3-109">Exchange UM ルーティング コンポーネント</span><span class="sxs-lookup"><span data-stu-id="d73c3-109">Exchange UM Routing component</span></span>

- <span data-ttu-id="d73c3-110">内部クラスター ルーティング コンポーネント</span><span class="sxs-lookup"><span data-stu-id="d73c3-110">Intercluster Routing component</span></span>

- [<span data-ttu-id="d73c3-111">Skype for Business Server の仲介サーバーコンポーネント</span><span class="sxs-lookup"><span data-stu-id="d73c3-111">Mediation Server component in Skype for Business Server</span></span>](mediation-server.md)

## <a name="translation-service"></a><span data-ttu-id="d73c3-112">変換サービス</span><span class="sxs-lookup"><span data-stu-id="d73c3-112">Translation Service</span></span>

<span data-ttu-id="d73c3-p101">変換サービスは、ダイヤルされた電話番号を、管理者が定義した正規化ルールに基づいて E.164 形式またはその他の形式に変換するサーバー コンポーネントです。変換サービスでは、独自の番号付けシステムを使用する組織や E.164 をサポートしていないゲートウェイまたは PBX を使用する組織の場合は、E.164 以外の形式に変換できます。</span><span class="sxs-lookup"><span data-stu-id="d73c3-p101">The Translation Service is the server component that is responsible for translating a dialed number into the E.164 format or another format, according to the normalization rules that are defined by the administrator. The Translation Service can translate to formats other than E.164 if your organization uses a private numbering system or uses a gateway or PBX that does not support E.164.</span></span>

## <a name="inbound-routing-component"></a><span data-ttu-id="d73c3-115">着信ルーティング コンポーネント</span><span class="sxs-lookup"><span data-stu-id="d73c3-115">Inbound Routing Component</span></span>

<span data-ttu-id="d73c3-116">着信ルーティングコンポーネントは、エンタープライズボイスクライアント上のユーザーによって指定された環境設定に従って、着信通話を処理します。</span><span class="sxs-lookup"><span data-stu-id="d73c3-116">The Inbound Routing component handles incoming calls largely according to preferences that are specified by users on their Enterprise Voice clients.</span></span> <span data-ttu-id="d73c3-117">また、着信ルーティング コンポーネントは、ユーザーが設定した場合に、代理人着信および同時着信を行います。</span><span class="sxs-lookup"><span data-stu-id="d73c3-117">It also facilitates delegate ringing and simultaneous ringing, if configured by the user.</span></span> <span data-ttu-id="d73c3-118">たとえば、ユーザーは、不在時の着信を転送するか、それとも単に通知として記録するかを指定します。</span><span class="sxs-lookup"><span data-stu-id="d73c3-118">For example, users specify whether unanswered calls are forwarded or simply logged for notification.</span></span> <span data-ttu-id="d73c3-119">着信の転送が有効になっている場合、ユーザーは、不在着信を別の番号に転送するか、通話応答を提供するように構成されている Exchange UM サーバーに転送するかを指定できます。</span><span class="sxs-lookup"><span data-stu-id="d73c3-119">If call forwarding is enabled, users can specify whether unanswered calls should be forwarded to another number or to a Exchange UM server that has been configured to provide call answering.</span></span> <span data-ttu-id="d73c3-120">着信ルーティングコンポーネントは、既定ですべての Standard Edition サーバーとフロントエンドサーバーにインストールされます。</span><span class="sxs-lookup"><span data-stu-id="d73c3-120">The Inbound Routing component is installed by default on all Standard Edition server and Front End Servers.</span></span>

## <a name="outbound-routing-component"></a><span data-ttu-id="d73c3-121">発信ルーティング コンポーネント</span><span class="sxs-lookup"><span data-stu-id="d73c3-121">Outbound Routing Component</span></span>

<span data-ttu-id="d73c3-122">発信ルーティング コンポーネントは、発信通話を通話先の PBX または PSTN にルーティングします。</span><span class="sxs-lookup"><span data-stu-id="d73c3-122">The Outbound Routing component routes calls to PBX or PSTN destinations.</span></span> <span data-ttu-id="d73c3-123">ユーザーのボイスポリシーによって定義された通話承認規則が発信者に適用され、各通話をルーティングするための最適な PSTN ゲートウェイが決定されます。</span><span class="sxs-lookup"><span data-stu-id="d73c3-123">It applies call authorization rules, as defined by the user's voice policy, to callers and determines the optimal PSTN gateway for routing each call.</span></span> <span data-ttu-id="d73c3-124">送信ルーティングコンポーネントは、既定ですべての Standard Edition サーバーとフロントエンドサーバーにインストールされます。</span><span class="sxs-lookup"><span data-stu-id="d73c3-124">The Outbound Routing component is installed by default on all Standard Edition server and Front End Servers.</span></span>

<span data-ttu-id="d73c3-125">発信ルーティング コンポーネントで使用されるルーティング ロジックは、主にネットワーク管理者またはテレフォニー管理者が組織の要件に従って構成します。</span><span class="sxs-lookup"><span data-stu-id="d73c3-125">The routing logic that is used by the Outbound Routing component is in large measure configured by network or telephony administrators according to the requirements of their organizations.</span></span>

## <a name="exchange-um-routing-component"></a><span data-ttu-id="d73c3-126">Exchange UM ルーティング コンポーネント</span><span class="sxs-lookup"><span data-stu-id="d73c3-126">Exchange UM Routing Component</span></span>

<span data-ttu-id="d73c3-127">Exchange UM ルーティングコンポーネントは、skype for Business Server と Exchange ユニファイドメッセージング (UM) を実行しているサーバーの間のルーティングを処理します。これにより、Skype for business Server とユニファイドメッセージング機能が統合されます。</span><span class="sxs-lookup"><span data-stu-id="d73c3-127">The Exchange UM routing component handles routing between Skype for Business Server and servers running Exchange Unified Messaging (UM), to integrate Skype for Business Server with Unified Messaging features.</span></span>

<span data-ttu-id="d73c3-128">Exchange um ルーティングコンポーネントは、Exchange UM サーバーが利用できない場合に、PSTN 経由のボイスメールの再ルーティングも処理します。</span><span class="sxs-lookup"><span data-stu-id="d73c3-128">The Exchange UM routing component also handles rerouting of voice mail over the PSTN if Exchange UM servers are unavailable.</span></span> <span data-ttu-id="d73c3-129">セントラルサイトへの回復可能な WAN リンクを持っていない支社サイトのエンタープライズ Voip ユーザーがいる場合、ブランチサイトに展開した Survivable Branch Appliance は、WAN の停止中に支店ユーザー用のボイスメール survivability を提供します。</span><span class="sxs-lookup"><span data-stu-id="d73c3-129">If you have Enterprise Voice users at branch sites that do not have a resilient WAN link to a central site, the Survivable Branch Appliance that you deploy at the branch site provides voice mail survivability for branch users during a WAN outage.</span></span> <span data-ttu-id="d73c3-130">WAN リンクが利用できない場合、Survivable Branch Appliance は次の処理を実行します。</span><span class="sxs-lookup"><span data-stu-id="d73c3-130">When the WAN link is unavailable, the Survivable Branch Appliance does the following:</span></span>

- <span data-ttu-id="d73c3-131">中央サイトの Exchange ユニファイド メッセージング サーバーに、PSTN を介して不在時の着信を再ルーティングします。</span><span class="sxs-lookup"><span data-stu-id="d73c3-131">reroutes unanswered calls over the PSTN to the Exchange Unified Messaging server in the central site</span></span>

- <span data-ttu-id="d73c3-132">ユーザーが PSTN を介してボイス メール メッセージを取得できるようにします。</span><span class="sxs-lookup"><span data-stu-id="d73c3-132">provides the ability for a user to retrieve voice mail messages over the PSTN</span></span>

- <span data-ttu-id="d73c3-133">不在着信通知をキューに入れ、WAN リンクが回復したときに Exchange UM サーバーへそれらをアップロードします。</span><span class="sxs-lookup"><span data-stu-id="d73c3-133">queues missed call notifications, and then uploads them to the Exchange UM server when the WAN link is restored.</span></span>

<span data-ttu-id="d73c3-134">ボイスメールの再ルーティングを有効にするには、Exchange 管理者が Exchange UM 自動応答 (AA) でメッセージのみを受け入れるように構成することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="d73c3-134">To enable voice mail rerouting, we recommend that your Exchange administrator configure Exchange UM Auto Attendant (AA) to accept messages only.</span></span>

<span data-ttu-id="d73c3-135">これらの機能の詳細については、「[On-Premises Exchange Unified Messaging Integration](https://technet.microsoft.com/library/e7c63a71-2d99-4aa9-b649-36c1a431bdf1.aspx)」および「[Planning for Enterprise Voice Resiliency](https://technet.microsoft.com/library/ca116700-1055-4ca5-9b87-4c7f380c3655.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d73c3-135">For details about these features, see [On-Premises Exchange Unified Messaging Integration](https://technet.microsoft.com/library/e7c63a71-2d99-4aa9-b649-36c1a431bdf1.aspx) and [Planning for Enterprise Voice Resiliency](https://technet.microsoft.com/library/ca116700-1055-4ca5-9b87-4c7f380c3655.aspx), respectively.</span></span>

## <a name="intercluster-routing-component"></a><span data-ttu-id="d73c3-136">内部クラスター ルーティング コンポーネント</span><span class="sxs-lookup"><span data-stu-id="d73c3-136">Intercluster Routing Component</span></span>

<span data-ttu-id="d73c3-137">Intercluster ルーティングコンポーネントは、呼び出し先のプライマリレジストラープールへの呼び出しをルーティングする役割を担います。</span><span class="sxs-lookup"><span data-stu-id="d73c3-137">The Intercluster routing component is responsible for routing calls to the callee's primary Registrar pool.</span></span> <span data-ttu-id="d73c3-138">それが利用できない場合、コンポーネントは呼び出し元のバックアップレジストラープールに呼び出しをルーティングします。</span><span class="sxs-lookup"><span data-stu-id="d73c3-138">If that is unavailable, the component routes the call to the callee's backup Registrar pool.</span></span> <span data-ttu-id="d73c3-139">呼び出し先のプライマリとバックアップのレジストラープールが IP ネットワーク経由で接続されていない場合、Intercluster ルーティングコンポーネントによって、着信が PSTN 経由でユーザーの電話番号に再ルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="d73c3-139">If the callee's primary and backup Registrar pools are unreachable over the IP network, the Intercluster routing component reroutes the call over the PSTN to the user's telephone number.</span></span>

## <a name="other-front-end-server-components-required-for-voip"></a><span data-ttu-id="d73c3-140">VoIP に必要なその他のフロント エンド サーバー コンポーネント</span><span class="sxs-lookup"><span data-stu-id="d73c3-140">Other Front End Server Components Required for VoIP</span></span>

<span data-ttu-id="d73c3-141">フロントエンドサーバーまたはディレクターに常駐するその他のコンポーネントは VoIP をサポートしていますが、VoIP コンポーネントには含まれていません。次のような機能を備えています。</span><span class="sxs-lookup"><span data-stu-id="d73c3-141">Other components residing on the Front End Server or Director that provide essential support for VoIP, but are not themselves VoIP components, include the following:</span></span>

- <span data-ttu-id="d73c3-142">**ユーザー サービス。**</span><span class="sxs-lookup"><span data-stu-id="d73c3-142">**User Services.**</span></span> <span data-ttu-id="d73c3-143">各着信通話の通話先電話番号に対して逆引き番号検索を実行し、その電話番号を通話先ユーザーの SIP URI と照合します。</span><span class="sxs-lookup"><span data-stu-id="d73c3-143">Perform reverse number lookup on the destination phone number of each incoming call and match that number to the SIP URI of the destination user.</span></span> <span data-ttu-id="d73c3-144">この情報を使って、着信ルーティングコンポーネントによって、ユーザーの登録済み SIP エンドポイントへの通話が配布されます。</span><span class="sxs-lookup"><span data-stu-id="d73c3-144">Using this information, the Inbound Routing component distributes the call to that user's registered SIP endpoints.</span></span> <span data-ttu-id="d73c3-145">ユーザーサービスは、すべてのフロントエンドサーバーおよびディレクターのコアコンポーネントです。</span><span class="sxs-lookup"><span data-stu-id="d73c3-145">User Services is a core component on all Front End Servers and Directors.</span></span>

- <span data-ttu-id="d73c3-146">**ユーザー レプリケーター。**</span><span class="sxs-lookup"><span data-stu-id="d73c3-146">**User Replicator.**</span></span> <span data-ttu-id="d73c3-147">Active Directory ドメインサービスからユーザーの電話番号を抽出し、RTC データベース内のテーブルに書き込みます。この機能は、ユーザーサービスとアドレス帳サーバーで利用できます。</span><span class="sxs-lookup"><span data-stu-id="d73c3-147">Extracts user phone numbers from Active Directory Domain Services and writes them to tables in the RTC database, where they are available to User Services and Address Book Server.</span></span> <span data-ttu-id="d73c3-148">ユーザーレプリケーターは、すべてのフロントエンドサーバー上のコアコンポーネントです。</span><span class="sxs-lookup"><span data-stu-id="d73c3-148">User Replicator is a core component on all Front End Servers.</span></span>

- <span data-ttu-id="d73c3-149">**アドレス帳サーバー。**</span><span class="sxs-lookup"><span data-stu-id="d73c3-149">**Address Book Server.**</span></span> <span data-ttu-id="d73c3-150">Active Directory ドメインサービスから Skype for Business Server クライアントにグローバルアドレス一覧情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="d73c3-150">Provides global address list information from Active Directory Domain Services to Skype for Business Server clients.</span></span> <span data-ttu-id="d73c3-151">また、RTC データベースからユーザーと連絡先の情報を取得し、その情報をアドレス帳ファイルに書き込んだ後、Skype for Business クライアントによってダウンロードされた共有フォルダーにファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="d73c3-151">It also retrieves user and contact information from the RTC database, writes the information to the Address Book files, and then stores the files on a shared folder where they are downloaded by Skype for Business clients.</span></span> <span data-ttu-id="d73c3-152">アドレス帳サーバーは、情報を RTCAb データベースに書き込みます。これは、アドレス帳 Web クエリサービスが Skype for Business mobile からユーザー検索クエリに応答するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="d73c3-152">The Address Book Server writes the information to the RTCAb database, which is used by the Address Book Web Query service to respond to user search queries from Skype for Business mobile.</span></span> <span data-ttu-id="d73c3-153">必要に応じて、Skype for Business でユーザーの連絡先をプロビジョニングするために、RTC データベースに記載されているエンタープライズユーザーの電話番号を正規化します。</span><span class="sxs-lookup"><span data-stu-id="d73c3-153">It optionally normalizes enterprise user phone numbers that are written to the RTC database for the purpose of provisioning user contacts in Skype for Business.</span></span> <span data-ttu-id="d73c3-154">アドレス帳サービスは、既定ですべてのフロントエンドサーバーにインストールされます。</span><span class="sxs-lookup"><span data-stu-id="d73c3-154">The Address Book service is installed by default on all Front End Servers.</span></span> <span data-ttu-id="d73c3-155">アドレス帳 Web クエリサービスは、各フロントエンドサーバー上の Web サービスに既定でインストールされます。</span><span class="sxs-lookup"><span data-stu-id="d73c3-155">The Address Book Web Query service is installed by default with the Web services on each Front End Servers.</span></span>


