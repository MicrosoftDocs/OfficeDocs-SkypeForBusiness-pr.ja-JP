---
title: クライアント バージョン ルール
ms.reviewer: ''
ms.author: dianef
author: dianef77
manager: serdars
ms.date: 3/23/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.ClientCVPolicyRuleEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6e7e94c2-1475-4334-b8da-716b24a4c255
description: クライアント バージョン ポリシーは、一連のクライアント バージョン ルールで構成されます。これらのルールでは、ユーザーが特定のクライアントおよびクライアント バージョンでログオンしようとしたときに実行するアクションが定義されています。
ms.openlocfilehash: c70d831d88948bd50f14b9591807e2ce1f36611a
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32234729"
---
# <a name="client-version-rule"></a><span data-ttu-id="6bff1-104">クライアント バージョン ルール</span><span class="sxs-lookup"><span data-stu-id="6bff1-104">Client Version Rule</span></span>

<span data-ttu-id="6bff1-p102">クライアント バージョン ポリシーは、一連のクライアント バージョン ルールで構成されます。これらのルールでは、ユーザーが特定のクライアントおよびクライアント バージョンでログオンしようとしたときに実行するアクションが定義されています。</span><span class="sxs-lookup"><span data-stu-id="6bff1-p102">A client version policy is made up of a set of client version rules. These rules define the actions that should be taken when users attempt to log on with specific clients and client versions.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="6bff1-107">実行できるタスク</span><span class="sxs-lookup"><span data-stu-id="6bff1-107">Tasks you can perform</span></span>

<span data-ttu-id="6bff1-108">[**新規 クライアント バージョンの構成**] または [**編集 クライアント バージョンの構成**] ページでは、次のタスクを実行できます。</span><span class="sxs-lookup"><span data-stu-id="6bff1-108">You can perform the following tasks on the **New Client Version Configuration** or **Edit Client Version Configuration** page:</span></span>

- <span data-ttu-id="6bff1-109">クライアント バージョン ポリシーに新しいルールを追加する。</span><span class="sxs-lookup"><span data-stu-id="6bff1-109">Add new rules to a client version policy.</span></span>

- <span data-ttu-id="6bff1-110">既存のクライアント バージョン ポリシーを構成するルールを変更する。</span><span class="sxs-lookup"><span data-stu-id="6bff1-110">Modify the rules that make up an existing client version policy</span></span>

## <a name="ui-reference"></a><span data-ttu-id="6bff1-111">UI リファレンス</span><span class="sxs-lookup"><span data-stu-id="6bff1-111">UI Reference</span></span>

<span data-ttu-id="6bff1-112">以下は、ページ上のメニュー、コマンド、フィールド、およびプロパティについての説明です。</span><span class="sxs-lookup"><span data-stu-id="6bff1-112">The following lists describe the menus, command, fields, and properties on the page.</span></span>

- <span data-ttu-id="6bff1-113">**ユーザー エージェント**クライアントの種類を一覧から選択できます。</span><span class="sxs-lookup"><span data-stu-id="6bff1-113">**User agent** You can select a client type from the list.</span></span> <span data-ttu-id="6bff1-114">次の表は、ユーザー エージェントのコードを定義します。</span><span class="sxs-lookup"><span data-stu-id="6bff1-114">The following table defines user agent codes.</span></span>

|<span data-ttu-id="6bff1-115">**クライアント名**</span><span class="sxs-lookup"><span data-stu-id="6bff1-115">**Client Name**</span></span>|<span data-ttu-id="6bff1-116">**ユーザー エージェント**</span><span class="sxs-lookup"><span data-stu-id="6bff1-116">**User Agent**</span></span>|
|:-----|:-----|
|<span data-ttu-id="6bff1-117">Lync 2013 では、Lync 2010 では、Office Communicator</span><span class="sxs-lookup"><span data-stu-id="6bff1-117">Lync 2013, Lync 2010, Office Communicator</span></span>  <br/> |<span data-ttu-id="6bff1-118">OC</span><span class="sxs-lookup"><span data-stu-id="6bff1-118">OC</span></span>  <br/> |
|<span data-ttu-id="6bff1-119">Lync Web アプリケーションでは、Communicator Web Access</span><span class="sxs-lookup"><span data-stu-id="6bff1-119">Lync Web App, Communicator Web Access</span></span>  <br/> |<span data-ttu-id="6bff1-120">CWA</span><span class="sxs-lookup"><span data-stu-id="6bff1-120">CWA</span></span>  <br/> |
|<span data-ttu-id="6bff1-121">Office Communicator の電話、Lync の電話のエディション</span><span class="sxs-lookup"><span data-stu-id="6bff1-121">Lync Phone Edition, Office Communicator Phone</span></span>  <br/> |<span data-ttu-id="6bff1-122">OCPhone</span><span class="sxs-lookup"><span data-stu-id="6bff1-122">OCPhone</span></span>  <br/> |
|<span data-ttu-id="6bff1-123">Communicator Phone Edition プラットフォーム</span><span class="sxs-lookup"><span data-stu-id="6bff1-123">Communicator Phone Edition Platform</span></span>  <br/> |<span data-ttu-id="6bff1-124">CPE</span><span class="sxs-lookup"><span data-stu-id="6bff1-124">CPE</span></span>  <br/> |
|<span data-ttu-id="6bff1-125">統合コミュニケーション プラットフォーム</span><span class="sxs-lookup"><span data-stu-id="6bff1-125">Unified Communications Platform</span></span>  <br/> |<span data-ttu-id="6bff1-126">UCCP</span><span class="sxs-lookup"><span data-stu-id="6bff1-126">UCCP</span></span>  <br/> |
|<span data-ttu-id="6bff1-127">Lync 2010 Attendee</span><span class="sxs-lookup"><span data-stu-id="6bff1-127">Lync 2010 Attendee</span></span>  <br/> |<span data-ttu-id="6bff1-128">AOC</span><span class="sxs-lookup"><span data-stu-id="6bff1-128">AOC</span></span>  <br/> |
|<span data-ttu-id="6bff1-129">Live Meeting アドイン</span><span class="sxs-lookup"><span data-stu-id="6bff1-129">Live Meeting Add-In</span></span>  <br/> |<span data-ttu-id="6bff1-130">LiveMeetingAddins</span><span class="sxs-lookup"><span data-stu-id="6bff1-130">LiveMeetingAddins</span></span>  <br/> |
|<span data-ttu-id="6bff1-131">Office Live Meeting</span><span class="sxs-lookup"><span data-stu-id="6bff1-131">Office Live Meeting</span></span>  <br/> |<span data-ttu-id="6bff1-132">LMC</span><span class="sxs-lookup"><span data-stu-id="6bff1-132">LMC</span></span>  <br/> |
|<span data-ttu-id="6bff1-133">Windows Messenger</span><span class="sxs-lookup"><span data-stu-id="6bff1-133">Windows Messenger</span></span>  <br/> |<span data-ttu-id="6bff1-134">WM</span><span class="sxs-lookup"><span data-stu-id="6bff1-134">WM</span></span>  <br/> |
|<span data-ttu-id="6bff1-135">リアルタイム通信クライアント</span><span class="sxs-lookup"><span data-stu-id="6bff1-135">Real-time Communications Client</span></span>  <br/> |<span data-ttu-id="6bff1-136">RTC</span><span class="sxs-lookup"><span data-stu-id="6bff1-136">RTC</span></span>  <br/> |
|<span data-ttu-id="6bff1-137">IPad の Lync 2010</span><span class="sxs-lookup"><span data-stu-id="6bff1-137">Lync 2010 for iPad</span></span>  <br/> |<span data-ttu-id="6bff1-138">iPadLync</span><span class="sxs-lookup"><span data-stu-id="6bff1-138">iPadLync</span></span>  <br/> |
|<span data-ttu-id="6bff1-139">IPhone の Lync 2010</span><span class="sxs-lookup"><span data-stu-id="6bff1-139">Lync 2010 for iPhone</span></span>  <br/> |<span data-ttu-id="6bff1-140">iPhoneLync</span><span class="sxs-lookup"><span data-stu-id="6bff1-140">iPhoneLync</span></span>  <br/> |
|<span data-ttu-id="6bff1-141">Windows Phone の Lync 2010</span><span class="sxs-lookup"><span data-stu-id="6bff1-141">Lync 2010 for Windows Phone</span></span>  <br/> |<span data-ttu-id="6bff1-142">WPLync</span><span class="sxs-lookup"><span data-stu-id="6bff1-142">WPLync</span></span>  <br/> |
|<span data-ttu-id="6bff1-143">Nokia の Lync 2010</span><span class="sxs-lookup"><span data-stu-id="6bff1-143">Lync 2010 for Nokia</span></span>  <br/> |<span data-ttu-id="6bff1-144">NokiaLync</span><span class="sxs-lookup"><span data-stu-id="6bff1-144">NokiaLync</span></span>  <br/> |
|<span data-ttu-id="6bff1-145">Android の Lync 2010</span><span class="sxs-lookup"><span data-stu-id="6bff1-145">Lync 2010 for Android</span></span>  <br/> |<span data-ttu-id="6bff1-146">AndroidLync</span><span class="sxs-lookup"><span data-stu-id="6bff1-146">AndroidLync</span></span>  <br/> |
|<span data-ttu-id="6bff1-147">Mobility Service</span><span class="sxs-lookup"><span data-stu-id="6bff1-147">Mobility service</span></span>  <br/> |<span data-ttu-id="6bff1-148">McxService</span><span class="sxs-lookup"><span data-stu-id="6bff1-148">McxService</span></span>  <br/> |

- <span data-ttu-id="6bff1-149">**バージョン番号**次のフィールドにバージョン番号を指定するか、クライアントのバージョン番号を示すためにワイルドカードを使用できます。</span><span class="sxs-lookup"><span data-stu-id="6bff1-149">**Version number** You can specify the version numbers for the following fields, or use wildcards to indicate the client version number.</span></span>

  - <span data-ttu-id="6bff1-150">**メジャー バージョン**主要なリリースのクライアントに対応する番号を指定します。</span><span class="sxs-lookup"><span data-stu-id="6bff1-150">**Major version** Specifies the number that corresponds to the major release of the client.</span></span>

  - <span data-ttu-id="6bff1-151">**マイナー バージョン**クライアントのマイナー リリースに対応する番号を指定します。</span><span class="sxs-lookup"><span data-stu-id="6bff1-151">**Minor version** Specifies the number that corresponds to the minor release of the client.</span></span>

  - <span data-ttu-id="6bff1-152">**ビルド**クライアントのメジャーおよびマイナー リリースに対応するビルド番号を指定します。</span><span class="sxs-lookup"><span data-stu-id="6bff1-152">**Build** Specifies the build number that corresponds to the major and minor release of the client.</span></span>

  - <span data-ttu-id="6bff1-153">**更新**クライアントの更新のリリースに対応する番号を指定します。</span><span class="sxs-lookup"><span data-stu-id="6bff1-153">**Update** Specifies the number that corresponds to the updated release of the client.</span></span>

- <span data-ttu-id="6bff1-154">**比較演算**上記の手順で指定したクライアント バージョンの一致操作を指定できます。</span><span class="sxs-lookup"><span data-stu-id="6bff1-154">**Comparison operation** You can specify the matching operation for the client version you specified in the preceding steps.</span></span> <span data-ttu-id="6bff1-155">次の操作を紹介します。</span><span class="sxs-lookup"><span data-stu-id="6bff1-155">The following operations are available:</span></span>

  - <span data-ttu-id="6bff1-156">**[同じ]**</span><span class="sxs-lookup"><span data-stu-id="6bff1-156">**Same as**</span></span>

  - <span data-ttu-id="6bff1-157">**[等しくない]**</span><span class="sxs-lookup"><span data-stu-id="6bff1-157">**Is not**</span></span>

  - <span data-ttu-id="6bff1-158">**[より新しい]**</span><span class="sxs-lookup"><span data-stu-id="6bff1-158">**Newer than**</span></span>

  - <span data-ttu-id="6bff1-159">**[より新しいか同じ]**</span><span class="sxs-lookup"><span data-stu-id="6bff1-159">**Newer than or same as**</span></span>

  - <span data-ttu-id="6bff1-160">**[より古い]**</span><span class="sxs-lookup"><span data-stu-id="6bff1-160">**Older than**</span></span>

  - <span data-ttu-id="6bff1-161">**[より古いか同じ]**</span><span class="sxs-lookup"><span data-stu-id="6bff1-161">**Older than or same as**</span></span>

- <span data-ttu-id="6bff1-162">**アクション**上記の手順で条件が満たされたときに実行するアクションを指定することができます。</span><span class="sxs-lookup"><span data-stu-id="6bff1-162">**Action** You can specify the action to perform when the criteria in the preceding steps are met.</span></span> <span data-ttu-id="6bff1-163">次の操作を紹介します。</span><span class="sxs-lookup"><span data-stu-id="6bff1-163">The following actions are available:</span></span>

  - <span data-ttu-id="6bff1-164">**許可します。** ログオンするクライアントを使用できます。</span><span class="sxs-lookup"><span data-stu-id="6bff1-164">**Allow** Allows the client to log on.</span></span>

  - <span data-ttu-id="6bff1-165">**許可およびアップグレード**ログオンし、Windows Server の更新サービスまたは Microsoft Update から更新を受信するクライアントを使用できます。</span><span class="sxs-lookup"><span data-stu-id="6bff1-165">**Allow and Upgrade** Allows the client to log on and receive updates from Windows Server Update Service or Microsoft Update.</span></span> <span data-ttu-id="6bff1-166">この操作は、 **OC**のユーザー エージェントが選択した場合のみ利用可能です。</span><span class="sxs-lookup"><span data-stu-id="6bff1-166">This action is available only when user agent **OC** is selected.</span></span>

    > [!NOTE]
    > <span data-ttu-id="6bff1-167">このアクションを選択すると、次にユーザーがビジネスのための Skype にサインインを表示する通知が発生します。</span><span class="sxs-lookup"><span data-stu-id="6bff1-167">Selecting this action causes a notification to appear the next time users sign in to Skype for Business.</span></span> <span data-ttu-id="6bff1-168">この通知では、Windows Server Update Service または Microsoft Update に更新がまだリリースされていなくても、更新が利用できるようになったことが伝えられます。</span><span class="sxs-lookup"><span data-stu-id="6bff1-168">The notification states that an update is available, even if updates have not yet been released to Windows Server Update Service or Microsoft Update.</span></span> <span data-ttu-id="6bff1-169">混乱を避けるため、このアクションは必ず更新が利用できるようになってから選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6bff1-169">To avoid confusion, you should choose this action only after updates become available.</span></span>

  - <span data-ttu-id="6bff1-170">**URL を許可します。** により、クライアントがログオンして、別のクライアント バージョンをダウンロードする場所についてのメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="6bff1-170">**Allow with URL** Allows the client to log on and displays a message about where to download another client version.</span></span> <span data-ttu-id="6bff1-171">[**URL**] フィールドで URL を指定します。</span><span class="sxs-lookup"><span data-stu-id="6bff1-171">You specify the URL in the **URL** field.</span></span>

  - <span data-ttu-id="6bff1-172">**ブロック**クライアントがログオンできないようにします。</span><span class="sxs-lookup"><span data-stu-id="6bff1-172">**Block** Prevents the client from logging on.</span></span>

  - <span data-ttu-id="6bff1-173">**ブロックおよびアップグレード**クライアントがログオンできないようにし、クライアントが Windows Server の更新サービスまたは Microsoft Update から更新を受信することができます。</span><span class="sxs-lookup"><span data-stu-id="6bff1-173">**Block and Upgrade** Prevents the client from logging on and allows the client to receive updates from Windows Server Update Service or Microsoft Update.</span></span> <span data-ttu-id="6bff1-174">この操作は、 **OC**のユーザー エージェントが選択した場合のみ利用可能です。</span><span class="sxs-lookup"><span data-stu-id="6bff1-174">This action is available only when user agent **OC** is selected.</span></span>

  - <span data-ttu-id="6bff1-p110">[**URL を使用した禁止**]   クライアントがログオンし、他のクライアント バージョンをダウンロードする場所についてのメッセージを表示することを禁止します。[**URL**] フィールドで URL を指定します。</span><span class="sxs-lookup"><span data-stu-id="6bff1-p110">**Block with URL** prevents the client from logging on and displays a message about where to download another client version. You specify the URL in the **URL** field.</span></span>

<span data-ttu-id="6bff1-p111">クライアントとクライアント バージョンの間の相互運用性の詳細については、「計画」のドキュメントの「[Client Interoperability in Lync 2013 Preview](https://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx)」を参照してください。クライアント バージョンの構成の使用の詳細については、「操作」のドキュメントの「[Modify the Default Action for Clients Not Explicitly Supported or Restricted](https://technet.microsoft.com/library/548dd0f5-62fe-4c3f-8952-2b9fd4c5fff3.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6bff1-p111">For details about interoperability among clients and client versions, see [Client Interoperability in Lync 2013 Preview](https://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx) in the Planning documentation. For details about working with client version configurations, see [Modify the Default Action for Clients Not Explicitly Supported or Restricted](https://technet.microsoft.com/library/548dd0f5-62fe-4c3f-8952-2b9fd4c5fff3.aspx) in the Operations documentation.</span></span>

