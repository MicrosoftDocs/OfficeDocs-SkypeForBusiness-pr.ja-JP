---
title: Skype ビジネス サーバーのフロント エンド サーバーの VoIP コンポーネント
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 310e81a7-da45-47d4-95d0-92837e386502
description: ビジネス サーバーには、翻訳サービスなど、さまざまなルーティング コンポーネント、Skype でのフロント エンド サーバー上に配置されているエンタープライズ VoIP のコンポーネントについて説明します。
ms.openlocfilehash: 7262f15d5763fa4a22b6bc6bb56fdc600f48bab2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33924242"
---
# <a name="front-end-server-voip-components-for-skype-for-business-server"></a><span data-ttu-id="9b021-103">Skype ビジネス サーバーのフロント エンド サーバーの VoIP コンポーネント</span><span class="sxs-lookup"><span data-stu-id="9b021-103">Front End Server VoIP components for Skype for Business Server</span></span>

<span data-ttu-id="9b021-104">ビジネス サーバーには、翻訳サービスなど、さまざまなルーティング コンポーネント、Skype でのフロント エンド サーバー上に配置されているエンタープライズ VoIP のコンポーネントについて説明します。</span><span class="sxs-lookup"><span data-stu-id="9b021-104">Learn about the Enterprise Voice components that are located on Front End Servers in Skype for Business Server, including translation service and various routing components.</span></span>

<span data-ttu-id="9b021-105">フロント エンド サーバーの VoIP コンポーネントは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="9b021-105">The VoIP components located on Front End Servers are as follows:</span></span>

- <span data-ttu-id="9b021-106">変換サービス</span><span class="sxs-lookup"><span data-stu-id="9b021-106">Translation Service</span></span>

- <span data-ttu-id="9b021-107">着信ルーティング コンポーネント</span><span class="sxs-lookup"><span data-stu-id="9b021-107">Inbound Routing component</span></span>

- <span data-ttu-id="9b021-108">発信ルーティング コンポーネント</span><span class="sxs-lookup"><span data-stu-id="9b021-108">Outbound Routing component</span></span>

- <span data-ttu-id="9b021-109">Exchange UM ルーティング コンポーネント</span><span class="sxs-lookup"><span data-stu-id="9b021-109">Exchange UM Routing component</span></span>

- <span data-ttu-id="9b021-110">内部クラスター ルーティング コンポーネント</span><span class="sxs-lookup"><span data-stu-id="9b021-110">Intercluster Routing component</span></span>

- [<span data-ttu-id="9b021-111">Skype ビジネス サーバー用の仲介サーバーのコンポーネント</span><span class="sxs-lookup"><span data-stu-id="9b021-111">Mediation Server component in Skype for Business Server</span></span>](mediation-server.md)

## <a name="translation-service"></a><span data-ttu-id="9b021-112">変換サービス</span><span class="sxs-lookup"><span data-stu-id="9b021-112">Translation Service</span></span>

<span data-ttu-id="9b021-p101">変換サービスは、ダイヤルされた電話番号を、管理者が定義した正規化ルールに基づいて E.164 形式またはその他の形式に変換するサーバー コンポーネントです。変換サービスでは、独自の番号付けシステムを使用する組織や E.164 をサポートしていないゲートウェイまたは PBX を使用する組織の場合は、E.164 以外の形式に変換できます。</span><span class="sxs-lookup"><span data-stu-id="9b021-p101">The Translation Service is the server component that is responsible for translating a dialed number into the E.164 format or another format, according to the normalization rules that are defined by the administrator. The Translation Service can translate to formats other than E.164 if your organization uses a private numbering system or uses a gateway or PBX that does not support E.164.</span></span>

## <a name="inbound-routing-component"></a><span data-ttu-id="9b021-115">着信ルーティング コンポーネント</span><span class="sxs-lookup"><span data-stu-id="9b021-115">Inbound Routing Component</span></span>

<span data-ttu-id="9b021-116">着信ルーティング コンポーネントは、エンタープライズ VoIP クライアントのユーザーが指定されている設定に従って主の着信呼び出しを処理します。</span><span class="sxs-lookup"><span data-stu-id="9b021-116">The Inbound Routing component handles incoming calls largely according to preferences that are specified by users on their Enterprise Voice clients.</span></span> <span data-ttu-id="9b021-117">また、着信ルーティング コンポーネントは、ユーザーが設定した場合に、代理人着信および同時着信を行います。</span><span class="sxs-lookup"><span data-stu-id="9b021-117">It also facilitates delegate ringing and simultaneous ringing, if configured by the user.</span></span> <span data-ttu-id="9b021-118">たとえば、ユーザーは、不在時の着信を転送するか、それとも単に通知として記録するかを指定します。</span><span class="sxs-lookup"><span data-stu-id="9b021-118">For example, users specify whether unanswered calls are forwarded or simply logged for notification.</span></span> <span data-ttu-id="9b021-119">呼び出しの転送を有効にすると、ユーザーが別の番号や通話応答を提供するように構成された Exchange UM サーバーに不在時の着信を転送するかどうかを指定できます。</span><span class="sxs-lookup"><span data-stu-id="9b021-119">If call forwarding is enabled, users can specify whether unanswered calls should be forwarded to another number or to a Exchange UM server that has been configured to provide call answering.</span></span> <span data-ttu-id="9b021-120">着信ルーティング コンポーネントは、すべての Standard Edition サーバーおよびフロント エンド サーバーに既定でインストールされます。</span><span class="sxs-lookup"><span data-stu-id="9b021-120">The Inbound Routing component is installed by default on all Standard Edition server and Front End Servers.</span></span>

## <a name="outbound-routing-component"></a><span data-ttu-id="9b021-121">発信ルーティング コンポーネント</span><span class="sxs-lookup"><span data-stu-id="9b021-121">Outbound Routing Component</span></span>

<span data-ttu-id="9b021-122">発信ルーティング コンポーネントは、発信通話を通話先の PBX または PSTN にルーティングします。</span><span class="sxs-lookup"><span data-stu-id="9b021-122">The Outbound Routing component routes calls to PBX or PSTN destinations.</span></span> <span data-ttu-id="9b021-123">呼び出し元のユーザーの音声ポリシーで定義されている呼び出しの承認規則を適用し、各呼び出しをルーティングするための最適な PSTN ゲートウェイを指定します。</span><span class="sxs-lookup"><span data-stu-id="9b021-123">It applies call authorization rules, as defined by the user's voice policy, to callers and determines the optimal PSTN gateway for routing each call.</span></span> <span data-ttu-id="9b021-124">発信ルーティング コンポーネントは、すべての Standard Edition サーバーおよびフロント エンド サーバーに既定でインストールされます。</span><span class="sxs-lookup"><span data-stu-id="9b021-124">The Outbound Routing component is installed by default on all Standard Edition server and Front End Servers.</span></span>

<span data-ttu-id="9b021-125">発信ルーティング コンポーネントで使用されるルーティング ロジックは、主にネットワーク管理者またはテレフォニー管理者が組織の要件に従って構成します。</span><span class="sxs-lookup"><span data-stu-id="9b021-125">The routing logic that is used by the Outbound Routing component is in large measure configured by network or telephony administrators according to the requirements of their organizations.</span></span>

## <a name="exchange-um-routing-component"></a><span data-ttu-id="9b021-126">Exchange UM ルーティング コンポーネント</span><span class="sxs-lookup"><span data-stu-id="9b021-126">Exchange UM Routing Component</span></span>

<span data-ttu-id="9b021-127">Exchange UM のルーティング コンポーネントは、ビジネス サーバーのユニファイド メッセージング機能を備えた Skype を統合するために Skype ビジネス サーバーおよび Exchange ユニファイド メッセージング (UM) を実行しているサーバー間のルーティングを処理します。</span><span class="sxs-lookup"><span data-stu-id="9b021-127">The Exchange UM routing component handles routing between Skype for Business Server and servers running Exchange Unified Messaging (UM), to integrate Skype for Business Server with Unified Messaging features.</span></span>

<span data-ttu-id="9b021-128">Exchange UM のルーティング コンポーネントはまた、Exchange UM サーバーが利用できない場合、PSTN 上のボイス メール再ルーティングを処理します。</span><span class="sxs-lookup"><span data-stu-id="9b021-128">The Exchange UM routing component also handles rerouting of voice mail over the PSTN if Exchange UM servers are unavailable.</span></span> <span data-ttu-id="9b021-129">エンタープライズ VoIP のユーザーがいる場合弾力性のある WAN がセントラル サイト、ブランチ サイトに展開するリカバリ性に優れたブランチ アプライアンスへのリンクがないブランチ サイトは、WAN の障害時にブランチ ユーザーのボイス メールの存続可能性を提供します。</span><span class="sxs-lookup"><span data-stu-id="9b021-129">If you have Enterprise Voice users at branch sites that do not have a resilient WAN link to a central site, the Survivable Branch Appliance that you deploy at the branch site provides voice mail survivability for branch users during a WAN outage.</span></span> <span data-ttu-id="9b021-130">WAN リンクが利用できない場合は、リカバリ性に優れたブランチ アプライアンスは、次の。</span><span class="sxs-lookup"><span data-stu-id="9b021-130">When the WAN link is unavailable, the Survivable Branch Appliance does the following:</span></span>

- <span data-ttu-id="9b021-131">中央サイトの Exchange ユニファイド メッセージング サーバーに、PSTN を介して不在時の着信を再ルーティングします。</span><span class="sxs-lookup"><span data-stu-id="9b021-131">reroutes unanswered calls over the PSTN to the Exchange Unified Messaging server in the central site</span></span>

- <span data-ttu-id="9b021-132">ユーザーが PSTN を介してボイス メール メッセージを取得できるようにします。</span><span class="sxs-lookup"><span data-stu-id="9b021-132">provides the ability for a user to retrieve voice mail messages over the PSTN</span></span>

- <span data-ttu-id="9b021-133">不在着信通知をキューに入れ、WAN リンクが回復したときに Exchange UM サーバーへそれらをアップロードします。</span><span class="sxs-lookup"><span data-stu-id="9b021-133">queues missed call notifications, and then uploads them to the Exchange UM server when the WAN link is restored.</span></span>

<span data-ttu-id="9b021-134">ボイス メール再ルーティングを有効にするには、Exchange 管理者が Exchange UM 自動応答 (AA) メッセージだけを許可するを構成することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="9b021-134">To enable voice mail rerouting, we recommend that your Exchange administrator configure Exchange UM Auto Attendant (AA) to accept messages only.</span></span>

<span data-ttu-id="9b021-135">これらの機能の詳細については、「[On-Premises Exchange Unified Messaging Integration](https://technet.microsoft.com/library/e7c63a71-2d99-4aa9-b649-36c1a431bdf1.aspx)」および「[Planning for Enterprise Voice Resiliency](https://technet.microsoft.com/library/ca116700-1055-4ca5-9b87-4c7f380c3655.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9b021-135">For details about these features, see [On-Premises Exchange Unified Messaging Integration](https://technet.microsoft.com/library/e7c63a71-2d99-4aa9-b649-36c1a431bdf1.aspx) and [Planning for Enterprise Voice Resiliency](https://technet.microsoft.com/library/ca116700-1055-4ca5-9b87-4c7f380c3655.aspx), respectively.</span></span>

## <a name="intercluster-routing-component"></a><span data-ttu-id="9b021-136">内部クラスター ルーティング コンポーネント</span><span class="sxs-lookup"><span data-stu-id="9b021-136">Intercluster Routing Component</span></span>

<span data-ttu-id="9b021-137">Intercluster ルーティング コンポーネントは、呼び出し先のプライマリ レジストラー プールへの通話のルーティングを行います。</span><span class="sxs-lookup"><span data-stu-id="9b021-137">The Intercluster routing component is responsible for routing calls to the callee's primary Registrar pool.</span></span> <span data-ttu-id="9b021-138">使用できない場合、コンポーネントは、呼び出し先のバックアップ レジストラー プールへの呼び出しをルーティングします。</span><span class="sxs-lookup"><span data-stu-id="9b021-138">If that is unavailable, the component routes the call to the callee's backup Registrar pool.</span></span> <span data-ttu-id="9b021-139">呼び出し先のプライマリおよびバックアップ レジストラー プールで IP ネットワーク経由で到達可能なない場合、Intercluster ルーティング コンポーネントは、ユーザーの電話番号を PSTN 経由で呼び出し再ルーティングします。</span><span class="sxs-lookup"><span data-stu-id="9b021-139">If the callee's primary and backup Registrar pools are unreachable over the IP network, the Intercluster routing component reroutes the call over the PSTN to the user's telephone number.</span></span>

## <a name="other-front-end-server-components-required-for-voip"></a><span data-ttu-id="9b021-140">VoIP に必要なその他のフロント エンド サーバー コンポーネント</span><span class="sxs-lookup"><span data-stu-id="9b021-140">Other Front End Server Components Required for VoIP</span></span>

<span data-ttu-id="9b021-141">ディレクター、フロント エンド サーバー上に存在する、VoIP の基本的なサポートを提供するが、VoIP コンポーネント自体ではない他のコンポーネントを以下に示します。</span><span class="sxs-lookup"><span data-stu-id="9b021-141">Other components residing on the Front End Server or Director that provide essential support for VoIP, but are not themselves VoIP components, include the following:</span></span>

- <span data-ttu-id="9b021-142">**ユーザー サービス。**</span><span class="sxs-lookup"><span data-stu-id="9b021-142">**User Services.**</span></span> <span data-ttu-id="9b021-143">各着信通話の通話先電話番号に対して逆引き番号検索を実行し、その電話番号を通話先ユーザーの SIP URI と照合します。</span><span class="sxs-lookup"><span data-stu-id="9b021-143">Perform reverse number lookup on the destination phone number of each incoming call and match that number to the SIP URI of the destination user.</span></span> <span data-ttu-id="9b021-144">この情報を使用すると、受信ルーティング コンポーネントは、そのユーザーの登録 SIP エンドポイントへの呼び出しを配布します。</span><span class="sxs-lookup"><span data-stu-id="9b021-144">Using this information, the Inbound Routing component distributes the call to that user's registered SIP endpoints.</span></span> <span data-ttu-id="9b021-145">ユーザー サービスは、すべてのフロント エンド サーバーおよびディレクターの主要なコンポーネントです。</span><span class="sxs-lookup"><span data-stu-id="9b021-145">User Services is a core component on all Front End Servers and Directors.</span></span>

- <span data-ttu-id="9b021-146">**ユーザー レプリケーター。**</span><span class="sxs-lookup"><span data-stu-id="9b021-146">**User Replicator.**</span></span> <span data-ttu-id="9b021-147">Active Directory ドメイン サービスからユーザーの電話番号を抽出し、それらがユーザーのサービスとアドレス帳サーバーを利用可能な RTC データベース内のテーブルに書き込みます。</span><span class="sxs-lookup"><span data-stu-id="9b021-147">Extracts user phone numbers from Active Directory Domain Services and writes them to tables in the RTC database, where they are available to User Services and Address Book Server.</span></span> <span data-ttu-id="9b021-148">ユーザー レプリケーターは、すべてのフロント エンド サーバーのコア コンポーネントです。</span><span class="sxs-lookup"><span data-stu-id="9b021-148">User Replicator is a core component on all Front End Servers.</span></span>

- <span data-ttu-id="9b021-149">**アドレス帳サーバー。**</span><span class="sxs-lookup"><span data-stu-id="9b021-149">**Address Book Server.**</span></span> <span data-ttu-id="9b021-150">ビジネス サーバー クライアント用の Skype を Active Directory ドメイン サービスからグローバル アドレス一覧情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="9b021-150">Provides global address list information from Active Directory Domain Services to Skype for Business Server clients.</span></span> <span data-ttu-id="9b021-151">情報をアドレス帳のファイルに書き込みます、およびビジネス クライアント用 Skype がダウンロードされる場所の共有フォルダー上のファイルを保存しも RTC データベースからユーザーおよび連絡先情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="9b021-151">It also retrieves user and contact information from the RTC database, writes the information to the Address Book files, and then stores the files on a shared folder where they are downloaded by Skype for Business clients.</span></span> <span data-ttu-id="9b021-152">アドレス帳サーバーは、モバイル ビジネスの Skype からのユーザーの検索クエリに応答するのにはアドレス帳 Web クエリ サービスによって使用される、RTCAb データベースに情報を書き込みます。</span><span class="sxs-lookup"><span data-stu-id="9b021-152">The Address Book Server writes the information to the RTCAb database, which is used by the Address Book Web Query service to respond to user search queries from Skype for Business mobile.</span></span> <span data-ttu-id="9b021-153">オプションで、ビジネスの Skype のユーザーの連絡先をプロビジョニングするための RTC データベースに書き込まれたエンタープライズ ユーザーの電話番号を正規化します。</span><span class="sxs-lookup"><span data-stu-id="9b021-153">It optionally normalizes enterprise user phone numbers that are written to the RTC database for the purpose of provisioning user contacts in Skype for Business.</span></span> <span data-ttu-id="9b021-154">すべてのフロント エンド サーバーでは既定では、アドレス帳サービスがインストールされています。</span><span class="sxs-lookup"><span data-stu-id="9b021-154">The Address Book service is installed by default on all Front End Servers.</span></span> <span data-ttu-id="9b021-155">アドレス帳 Web クエリ サービスは、各フロント エンド サーバー上の Web サービスでは既定でインストールされます。</span><span class="sxs-lookup"><span data-stu-id="9b021-155">The Address Book Web Query service is installed by default with the Web services on each Front End Servers.</span></span>


