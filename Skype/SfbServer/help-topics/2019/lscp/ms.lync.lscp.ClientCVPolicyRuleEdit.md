---
title: クライアント バージョン ルール
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.ClientCVPolicyRuleEdit
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: 6e7e94c2-1475-4334-b8da-716b24a4c255
ROBOTS: NOINDEX, NOFOLLOW
description: クライアント バージョン ポリシーは、一連のクライアント バージョン ルールで構成されます。これらのルールでは、ユーザーが特定のクライアントおよびクライアント バージョンでログオンしようとしたときに実行するアクションが定義されています。
ms.openlocfilehash: a461dad500f0c7d3095ef56483a6b592cec6c20d
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51109623"
---
# <a name="client-version-rule"></a><span data-ttu-id="6417d-104">クライアント バージョン ルール</span><span class="sxs-lookup"><span data-stu-id="6417d-104">Client Version Rule</span></span>

<span data-ttu-id="6417d-p102">クライアント バージョン ポリシーは、一連のクライアント バージョン ルールで構成されます。これらのルールでは、ユーザーが特定のクライアントおよびクライアント バージョンでログオンしようとしたときに実行するアクションが定義されています。</span><span class="sxs-lookup"><span data-stu-id="6417d-p102">A client version policy is made up of a set of client version rules. These rules define the actions that should be taken when users attempt to log on with specific clients and client versions.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="6417d-107">実行できるタスク</span><span class="sxs-lookup"><span data-stu-id="6417d-107">Tasks you can perform</span></span>

<span data-ttu-id="6417d-108">[**新規 クライアント バージョンの構成**] または [**編集 クライアント バージョンの構成**] ページでは、次のタスクを実行できます。</span><span class="sxs-lookup"><span data-stu-id="6417d-108">You can perform the following tasks on the **New Client Version Configuration** or **Edit Client Version Configuration** page:</span></span>

- <span data-ttu-id="6417d-109">クライアント バージョン ポリシーに新しいルールを追加する。</span><span class="sxs-lookup"><span data-stu-id="6417d-109">Add new rules to a client version policy.</span></span>

- <span data-ttu-id="6417d-110">既存のクライアント バージョン ポリシーを構成するルールを変更する。</span><span class="sxs-lookup"><span data-stu-id="6417d-110">Modify the rules that make up an existing client version policy</span></span>

## <a name="ui-reference"></a><span data-ttu-id="6417d-111">UI リファレンス</span><span class="sxs-lookup"><span data-stu-id="6417d-111">UI Reference</span></span>

<span data-ttu-id="6417d-112">以下は、ページ上のメニュー、コマンド、フィールド、およびプロパティについての説明です。</span><span class="sxs-lookup"><span data-stu-id="6417d-112">The following lists describe the menus, command, fields, and properties on the page.</span></span>

- <span data-ttu-id="6417d-113">**ユーザー エージェント** リストからクライアントの種類を選択できます。</span><span class="sxs-lookup"><span data-stu-id="6417d-113">**User agent** You can select a client type from the list.</span></span> <span data-ttu-id="6417d-114">次の表は、ユーザー エージェント コードを定義します。</span><span class="sxs-lookup"><span data-stu-id="6417d-114">The following table defines user agent codes.</span></span> <span data-ttu-id="6417d-115">この一覧には従来のクライアントの種類が含まれています。一部はサポートされなくなりました。</span><span class="sxs-lookup"><span data-stu-id="6417d-115">This list includes legacy client types, some of which are no longer supported.</span></span>

|<span data-ttu-id="6417d-116">**クライアント名**</span><span class="sxs-lookup"><span data-stu-id="6417d-116">**Client Name**</span></span>|<span data-ttu-id="6417d-117">**ユーザー エージェント**</span><span class="sxs-lookup"><span data-stu-id="6417d-117">**User Agent**</span></span>|
|:-----|:-----|
|<span data-ttu-id="6417d-118">Lync 2013、Lync 2010、Office Communicator</span><span class="sxs-lookup"><span data-stu-id="6417d-118">Lync 2013, Lync 2010, Office Communicator</span></span>  <br/> |<span data-ttu-id="6417d-119">OC</span><span class="sxs-lookup"><span data-stu-id="6417d-119">OC</span></span>  <br/> |
|<span data-ttu-id="6417d-120">Lync Web App、Communicator Web Access</span><span class="sxs-lookup"><span data-stu-id="6417d-120">Lync Web App, Communicator Web Access</span></span>  <br/> |<span data-ttu-id="6417d-121">CWA</span><span class="sxs-lookup"><span data-stu-id="6417d-121">CWA</span></span>  <br/> |
|<span data-ttu-id="6417d-122">Lync Phone Edition, Office Communicator Phone</span><span class="sxs-lookup"><span data-stu-id="6417d-122">Lync Phone Edition, Office Communicator Phone</span></span>  <br/> |<span data-ttu-id="6417d-123">OCPhone</span><span class="sxs-lookup"><span data-stu-id="6417d-123">OCPhone</span></span>  <br/> |
|<span data-ttu-id="6417d-124">Communicator Phone Edition プラットフォーム</span><span class="sxs-lookup"><span data-stu-id="6417d-124">Communicator Phone Edition Platform</span></span>  <br/> |<span data-ttu-id="6417d-125">CPE</span><span class="sxs-lookup"><span data-stu-id="6417d-125">CPE</span></span>  <br/> |
|<span data-ttu-id="6417d-126">統合コミュニケーション プラットフォーム</span><span class="sxs-lookup"><span data-stu-id="6417d-126">Unified Communications Platform</span></span>  <br/> |<span data-ttu-id="6417d-127">UCCP</span><span class="sxs-lookup"><span data-stu-id="6417d-127">UCCP</span></span>  <br/> |
|<span data-ttu-id="6417d-128">Lync 2010 Attendee</span><span class="sxs-lookup"><span data-stu-id="6417d-128">Lync 2010 Attendee</span></span>  <br/> |<span data-ttu-id="6417d-129">AOC</span><span class="sxs-lookup"><span data-stu-id="6417d-129">AOC</span></span>  <br/> |
|<span data-ttu-id="6417d-130">Live Meeting アドイン</span><span class="sxs-lookup"><span data-stu-id="6417d-130">Live Meeting Add-In</span></span>  <br/> |<span data-ttu-id="6417d-131">LiveMeetingAddins</span><span class="sxs-lookup"><span data-stu-id="6417d-131">LiveMeetingAddins</span></span>  <br/> |
|<span data-ttu-id="6417d-132">Office Live Meeting</span><span class="sxs-lookup"><span data-stu-id="6417d-132">Office Live Meeting</span></span>  <br/> |<span data-ttu-id="6417d-133">LMC</span><span class="sxs-lookup"><span data-stu-id="6417d-133">LMC</span></span>  <br/> |
|<span data-ttu-id="6417d-134">Windows Messenger</span><span class="sxs-lookup"><span data-stu-id="6417d-134">Windows Messenger</span></span>  <br/> |<span data-ttu-id="6417d-135">WM</span><span class="sxs-lookup"><span data-stu-id="6417d-135">WM</span></span>  <br/> |
|<span data-ttu-id="6417d-136">リアルタイム通信クライアント</span><span class="sxs-lookup"><span data-stu-id="6417d-136">Real-time Communications Client</span></span>  <br/> |<span data-ttu-id="6417d-137">RTC</span><span class="sxs-lookup"><span data-stu-id="6417d-137">RTC</span></span>  <br/> |
|<span data-ttu-id="6417d-138">Lync 2010 for iPad</span><span class="sxs-lookup"><span data-stu-id="6417d-138">Lync 2010 for iPad</span></span>  <br/> |<span data-ttu-id="6417d-139">iPadLync</span><span class="sxs-lookup"><span data-stu-id="6417d-139">iPadLync</span></span>  <br/> |
|<span data-ttu-id="6417d-140">Lync 2010 for iPhone</span><span class="sxs-lookup"><span data-stu-id="6417d-140">Lync 2010 for iPhone</span></span>  <br/> |<span data-ttu-id="6417d-141">iPhoneLync</span><span class="sxs-lookup"><span data-stu-id="6417d-141">iPhoneLync</span></span>  <br/> |
|<span data-ttu-id="6417d-142">Lync 2010 for Windows Phone</span><span class="sxs-lookup"><span data-stu-id="6417d-142">Lync 2010 for Windows Phone</span></span>  <br/> |<span data-ttu-id="6417d-143">WPLync</span><span class="sxs-lookup"><span data-stu-id="6417d-143">WPLync</span></span>  <br/> |
|<span data-ttu-id="6417d-144">Lync 2010 for Nokia</span><span class="sxs-lookup"><span data-stu-id="6417d-144">Lync 2010 for Nokia</span></span>  <br/> |<span data-ttu-id="6417d-145">NokiaLync</span><span class="sxs-lookup"><span data-stu-id="6417d-145">NokiaLync</span></span>  <br/> |
|<span data-ttu-id="6417d-146">Android 用 Lync 2010</span><span class="sxs-lookup"><span data-stu-id="6417d-146">Lync 2010 for Android</span></span>  <br/> |<span data-ttu-id="6417d-147">AndroidLync</span><span class="sxs-lookup"><span data-stu-id="6417d-147">AndroidLync</span></span>  <br/> |
|<span data-ttu-id="6417d-148">Mobility Service</span><span class="sxs-lookup"><span data-stu-id="6417d-148">Mobility service</span></span>  <br/> |<span data-ttu-id="6417d-149">McxService</span><span class="sxs-lookup"><span data-stu-id="6417d-149">McxService</span></span>  <br/> |

- <span data-ttu-id="6417d-150">**バージョン番号** 次のフィールドのバージョン番号を指定するか、ワイルドカードを使用してクライアントのバージョン番号を示します。</span><span class="sxs-lookup"><span data-stu-id="6417d-150">**Version number** You can specify the version numbers for the following fields, or use wildcards to indicate the client version number.</span></span>

  - <span data-ttu-id="6417d-151">**メジャー バージョン** クライアントのメジャー リリースに対応する番号を指定します。</span><span class="sxs-lookup"><span data-stu-id="6417d-151">**Major version** Specifies the number that corresponds to the major release of the client.</span></span>

  - <span data-ttu-id="6417d-152">**マイナー バージョン** クライアントのマイナー リリースに対応する番号を指定します。</span><span class="sxs-lookup"><span data-stu-id="6417d-152">**Minor version** Specifies the number that corresponds to the minor release of the client.</span></span>

  - <span data-ttu-id="6417d-153">**ビルド** クライアントのメジャー リリースとマイナー リリースに対応するビルド番号を指定します。</span><span class="sxs-lookup"><span data-stu-id="6417d-153">**Build** Specifies the build number that corresponds to the major and minor release of the client.</span></span>

  - <span data-ttu-id="6417d-154">**更新** クライアントの更新されたリリースに対応する番号を指定します。</span><span class="sxs-lookup"><span data-stu-id="6417d-154">**Update** Specifies the number that corresponds to the updated release of the client.</span></span>

- <span data-ttu-id="6417d-155">**比較操作** 前の手順で指定したクライアント バージョンに一致する操作を指定できます。</span><span class="sxs-lookup"><span data-stu-id="6417d-155">**Comparison operation** You can specify the matching operation for the client version you specified in the preceding steps.</span></span> <span data-ttu-id="6417d-156">次の操作を使用できます。</span><span class="sxs-lookup"><span data-stu-id="6417d-156">The following operations are available:</span></span>

  - <span data-ttu-id="6417d-157">**同じ**</span><span class="sxs-lookup"><span data-stu-id="6417d-157">**Same as**</span></span>

  - <span data-ttu-id="6417d-158">**異なる**</span><span class="sxs-lookup"><span data-stu-id="6417d-158">**Is not**</span></span>

  - <span data-ttu-id="6417d-159">**より新しい**</span><span class="sxs-lookup"><span data-stu-id="6417d-159">**Newer than**</span></span>

  - <span data-ttu-id="6417d-160">**以上**</span><span class="sxs-lookup"><span data-stu-id="6417d-160">**Newer than or same as**</span></span>

  - <span data-ttu-id="6417d-161">**より古い**</span><span class="sxs-lookup"><span data-stu-id="6417d-161">**Older than**</span></span>

  - <span data-ttu-id="6417d-162">**以前**</span><span class="sxs-lookup"><span data-stu-id="6417d-162">**Older than or same as**</span></span>

- <span data-ttu-id="6417d-163">**アクション** 前の手順の条件が満たされた場合に実行するアクションを指定できます。</span><span class="sxs-lookup"><span data-stu-id="6417d-163">**Action** You can specify the action to perform when the criteria in the preceding steps are met.</span></span> <span data-ttu-id="6417d-164">次のアクションを使用できます。</span><span class="sxs-lookup"><span data-stu-id="6417d-164">The following actions are available:</span></span>

  - <span data-ttu-id="6417d-165">**許可する** クライアントにログオンを許可します。</span><span class="sxs-lookup"><span data-stu-id="6417d-165">**Allow** Allows the client to log on.</span></span>

  - <span data-ttu-id="6417d-166">**許可とアップグレード** クライアントが Windows Server Update Service または Microsoft Update からログオンして更新プログラムを受信できます。</span><span class="sxs-lookup"><span data-stu-id="6417d-166">**Allow and Upgrade** Allows the client to log on and receive updates from Windows Server Update Service or Microsoft Update.</span></span> <span data-ttu-id="6417d-167">このアクションは、ユーザー エージェント **OC** が選択されている場合にのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="6417d-167">This action is available only when user agent **OC** is selected.</span></span>

    > [!NOTE]
    > <span data-ttu-id="6417d-168">このアクションを選択すると、ユーザーが次に Skype for Business にサインインすると、通知が表示されます。</span><span class="sxs-lookup"><span data-stu-id="6417d-168">Selecting this action causes a notification to appear the next time users sign in to Skype for Business.</span></span> <span data-ttu-id="6417d-169">この通知では、更新プログラムがある場合、Windows Server Update Service または Microsoft Update にまだリリースされていなくても、更新プログラムを利用できることが伝えられます。</span><span class="sxs-lookup"><span data-stu-id="6417d-169">The notification states that an update is available, even if updates have not yet been released to Windows Server Update Service or Microsoft Update.</span></span> <span data-ttu-id="6417d-170">混乱を避けるため、このアクションは更新プログラムが利用できるようになった後でのみ選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6417d-170">To avoid confusion, you should choose this action only after updates become available.</span></span>

  - <span data-ttu-id="6417d-171">**URL で許可する** クライアントがログオンし、別のクライアント バージョンをダウンロードする場所に関するメッセージを表示します。</span><span class="sxs-lookup"><span data-stu-id="6417d-171">**Allow with URL** Allows the client to log on and displays a message about where to download another client version.</span></span> <span data-ttu-id="6417d-172">[**URL**] フィールドで URL を指定します。</span><span class="sxs-lookup"><span data-stu-id="6417d-172">You specify the URL in the **URL** field.</span></span>

  - <span data-ttu-id="6417d-173">**ブロック** クライアントがログオンを防止します。</span><span class="sxs-lookup"><span data-stu-id="6417d-173">**Block** Prevents the client from logging on.</span></span>

  - <span data-ttu-id="6417d-174">**ブロックとアップグレード** クライアントがログオンし、クライアントが Windows Server Update Service または Microsoft Update から更新プログラムを受け取るのを許可します。</span><span class="sxs-lookup"><span data-stu-id="6417d-174">**Block and Upgrade** Prevents the client from logging on and allows the client to receive updates from Windows Server Update Service or Microsoft Update.</span></span> <span data-ttu-id="6417d-175">このアクションは、ユーザー エージェント **OC** が選択されている場合にのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="6417d-175">This action is available only when user agent **OC** is selected.</span></span>

  - <span data-ttu-id="6417d-p110">[**URL を使用した禁止**]   クライアントがログオンし、他のクライアント バージョンをダウンロードする場所についてのメッセージを表示することを禁止します。[**URL**] フィールドで URL を指定します。</span><span class="sxs-lookup"><span data-stu-id="6417d-p110">**Block with URL** prevents the client from logging on and displays a message about where to download another client version. You specify the URL in the **URL** field.</span></span>

<span data-ttu-id="6417d-178">クライアントとクライアント バージョン間の相互運用性の詳細については、「計画」のドキュメントの [「クライアント相互](/previous-versions/office/lync-server-2013/lync-server-2013-client-interoperability-in-lync-2013) 運用性」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6417d-178">For details about interoperability among clients and client versions, see [Client Interoperability](/previous-versions/office/lync-server-2013/lync-server-2013-client-interoperability-in-lync-2013) in the Planning documentation.</span></span> <span data-ttu-id="6417d-179">クライアント バージョンの構成を扱う処理の詳細については、「操作」のドキュメントの「[Modify the Default Action for Clients Not Explicitly Supported or Restricted](/previous-versions/office/lync-server-2013/lync-server-2013-modify-the-default-action-for-clients-not-explicitly-supported-or-restricted)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6417d-179">For details about working with client version configurations, see [Modify the Default Action for Clients Not Explicitly Supported or Restricted](/previous-versions/office/lync-server-2013/lync-server-2013-modify-the-default-action-for-clients-not-explicitly-supported-or-restricted) in the Operations documentation.</span></span>