---
title: クライアント バージョン ルール
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/23/2015
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.ClientCVPolicyRuleEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6e7e94c2-1475-4334-b8da-716b24a4c255
description: クライアント バージョン ポリシーは、一連のクライアント バージョン ルールで構成されます。これらのルールでは、ユーザーが特定のクライアントおよびクライアント バージョンでログオンしようとしたときに実行するアクションが定義されています。
ms.openlocfilehash: 6fa3ca3f59756c8a6fedb9fd8f1f457ca3f2df40
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34277931"
---
# <a name="client-version-rule"></a><span data-ttu-id="e1bb1-104">クライアント バージョン ルール</span><span class="sxs-lookup"><span data-stu-id="e1bb1-104">Client Version Rule</span></span>

<span data-ttu-id="e1bb1-p102">クライアント バージョン ポリシーは、一連のクライアント バージョン ルールで構成されます。これらのルールでは、ユーザーが特定のクライアントおよびクライアント バージョンでログオンしようとしたときに実行するアクションが定義されています。</span><span class="sxs-lookup"><span data-stu-id="e1bb1-p102">A client version policy is made up of a set of client version rules. These rules define the actions that should be taken when users attempt to log on with specific clients and client versions.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="e1bb1-107">実行できるタスク</span><span class="sxs-lookup"><span data-stu-id="e1bb1-107">Tasks you can perform</span></span>

<span data-ttu-id="e1bb1-108">[**新規 クライアント バージョンの構成**] または [**編集 クライアント バージョンの構成**] ページでは、次のタスクを実行できます。</span><span class="sxs-lookup"><span data-stu-id="e1bb1-108">You can perform the following tasks on the **New Client Version Configuration** or **Edit Client Version Configuration** page:</span></span>

- <span data-ttu-id="e1bb1-109">クライアント バージョン ポリシーに新しいルールを追加する。</span><span class="sxs-lookup"><span data-stu-id="e1bb1-109">Add new rules to a client version policy.</span></span>

- <span data-ttu-id="e1bb1-110">既存のクライアント バージョン ポリシーを構成するルールを変更する。</span><span class="sxs-lookup"><span data-stu-id="e1bb1-110">Modify the rules that make up an existing client version policy</span></span>

## <a name="ui-reference"></a><span data-ttu-id="e1bb1-111">UI リファレンス</span><span class="sxs-lookup"><span data-stu-id="e1bb1-111">UI Reference</span></span>

<span data-ttu-id="e1bb1-112">以下は、ページ上のメニュー、コマンド、フィールド、およびプロパティについての説明です。</span><span class="sxs-lookup"><span data-stu-id="e1bb1-112">The following lists describe the menus, command, fields, and properties on the page.</span></span>

- <span data-ttu-id="e1bb1-113">**ユーザーエージェント**リストからクライアントの種類を選ぶことができます。</span><span class="sxs-lookup"><span data-stu-id="e1bb1-113">**User agent** You can select a client type from the list.</span></span> <span data-ttu-id="e1bb1-114">次の表は、ユーザーエージェントコードを定義しています。</span><span class="sxs-lookup"><span data-stu-id="e1bb1-114">The following table defines user agent codes.</span></span>

|<span data-ttu-id="e1bb1-115">**クライアント名**</span><span class="sxs-lookup"><span data-stu-id="e1bb1-115">**Client Name**</span></span>|<span data-ttu-id="e1bb1-116">**ユーザー エージェント**</span><span class="sxs-lookup"><span data-stu-id="e1bb1-116">**User Agent**</span></span>|
|:-----|:-----|
|<span data-ttu-id="e1bb1-117">Lync 2013、Lync 2010、Office Communicator</span><span class="sxs-lookup"><span data-stu-id="e1bb1-117">Lync 2013, Lync 2010, Office Communicator</span></span>  <br/> |<span data-ttu-id="e1bb1-118">OC</span><span class="sxs-lookup"><span data-stu-id="e1bb1-118">OC</span></span>  <br/> |
|<span data-ttu-id="e1bb1-119">Lync Web App, Communicator Web Access</span><span class="sxs-lookup"><span data-stu-id="e1bb1-119">Lync Web App, Communicator Web Access</span></span>  <br/> |<span data-ttu-id="e1bb1-120">CWA</span><span class="sxs-lookup"><span data-stu-id="e1bb1-120">CWA</span></span>  <br/> |
|<span data-ttu-id="e1bb1-121">Lync Phone Edition、Office Communicator フォン</span><span class="sxs-lookup"><span data-stu-id="e1bb1-121">Lync Phone Edition, Office Communicator Phone</span></span>  <br/> |<span data-ttu-id="e1bb1-122">OCPhone</span><span class="sxs-lookup"><span data-stu-id="e1bb1-122">OCPhone</span></span>  <br/> |
|<span data-ttu-id="e1bb1-123">Communicator Phone Edition プラットフォーム</span><span class="sxs-lookup"><span data-stu-id="e1bb1-123">Communicator Phone Edition Platform</span></span>  <br/> |<span data-ttu-id="e1bb1-124">CPE</span><span class="sxs-lookup"><span data-stu-id="e1bb1-124">CPE</span></span>  <br/> |
|<span data-ttu-id="e1bb1-125">統合コミュニケーション プラットフォーム</span><span class="sxs-lookup"><span data-stu-id="e1bb1-125">Unified Communications Platform</span></span>  <br/> |<span data-ttu-id="e1bb1-126">UCCP</span><span class="sxs-lookup"><span data-stu-id="e1bb1-126">UCCP</span></span>  <br/> |
|<span data-ttu-id="e1bb1-127">Lync 2010 Attendee</span><span class="sxs-lookup"><span data-stu-id="e1bb1-127">Lync 2010 Attendee</span></span>  <br/> |<span data-ttu-id="e1bb1-128">AOC</span><span class="sxs-lookup"><span data-stu-id="e1bb1-128">AOC</span></span>  <br/> |
|<span data-ttu-id="e1bb1-129">Live Meeting アドイン</span><span class="sxs-lookup"><span data-stu-id="e1bb1-129">Live Meeting Add-In</span></span>  <br/> |<span data-ttu-id="e1bb1-130">LiveMeetingAddins</span><span class="sxs-lookup"><span data-stu-id="e1bb1-130">LiveMeetingAddins</span></span>  <br/> |
|<span data-ttu-id="e1bb1-131">Office Live Meeting</span><span class="sxs-lookup"><span data-stu-id="e1bb1-131">Office Live Meeting</span></span>  <br/> |<span data-ttu-id="e1bb1-132">LMC</span><span class="sxs-lookup"><span data-stu-id="e1bb1-132">LMC</span></span>  <br/> |
|<span data-ttu-id="e1bb1-133">Windows Messenger</span><span class="sxs-lookup"><span data-stu-id="e1bb1-133">Windows Messenger</span></span>  <br/> |<span data-ttu-id="e1bb1-134">WM</span><span class="sxs-lookup"><span data-stu-id="e1bb1-134">WM</span></span>  <br/> |
|<span data-ttu-id="e1bb1-135">リアルタイム通信クライアント</span><span class="sxs-lookup"><span data-stu-id="e1bb1-135">Real-time Communications Client</span></span>  <br/> |<span data-ttu-id="e1bb1-136">RTC</span><span class="sxs-lookup"><span data-stu-id="e1bb1-136">RTC</span></span>  <br/> |
|<span data-ttu-id="e1bb1-137">Lync 2010 for iPad</span><span class="sxs-lookup"><span data-stu-id="e1bb1-137">Lync 2010 for iPad</span></span>  <br/> |<span data-ttu-id="e1bb1-138">iPadLync</span><span class="sxs-lookup"><span data-stu-id="e1bb1-138">iPadLync</span></span>  <br/> |
|<span data-ttu-id="e1bb1-139">Lync 2010 for iPhone</span><span class="sxs-lookup"><span data-stu-id="e1bb1-139">Lync 2010 for iPhone</span></span>  <br/> |<span data-ttu-id="e1bb1-140">iPhoneLync</span><span class="sxs-lookup"><span data-stu-id="e1bb1-140">iPhoneLync</span></span>  <br/> |
|<span data-ttu-id="e1bb1-141">Windows Phone 版 Lync 2010</span><span class="sxs-lookup"><span data-stu-id="e1bb1-141">Lync 2010 for Windows Phone</span></span>  <br/> |<span data-ttu-id="e1bb1-142">WPLync</span><span class="sxs-lookup"><span data-stu-id="e1bb1-142">WPLync</span></span>  <br/> |
|<span data-ttu-id="e1bb1-143">Lync 2010 for Nokia</span><span class="sxs-lookup"><span data-stu-id="e1bb1-143">Lync 2010 for Nokia</span></span>  <br/> |<span data-ttu-id="e1bb1-144">NokiaLync</span><span class="sxs-lookup"><span data-stu-id="e1bb1-144">NokiaLync</span></span>  <br/> |
|<span data-ttu-id="e1bb1-145">Lync 2010 for Android</span><span class="sxs-lookup"><span data-stu-id="e1bb1-145">Lync 2010 for Android</span></span>  <br/> |<span data-ttu-id="e1bb1-146">AndroidLync</span><span class="sxs-lookup"><span data-stu-id="e1bb1-146">AndroidLync</span></span>  <br/> |
|<span data-ttu-id="e1bb1-147">Mobility Service</span><span class="sxs-lookup"><span data-stu-id="e1bb1-147">Mobility service</span></span>  <br/> |<span data-ttu-id="e1bb1-148">McxService</span><span class="sxs-lookup"><span data-stu-id="e1bb1-148">McxService</span></span>  <br/> |

- <span data-ttu-id="e1bb1-149">**バージョン番号**次のフィールドのバージョン番号を指定するか、ワイルドカードを使用してクライアントのバージョン番号を示すことができます。</span><span class="sxs-lookup"><span data-stu-id="e1bb1-149">**Version number** You can specify the version numbers for the following fields, or use wildcards to indicate the client version number.</span></span>

  - <span data-ttu-id="e1bb1-150">**メジャーバージョン**クライアントのメジャーリリースに対応する番号を指定します。</span><span class="sxs-lookup"><span data-stu-id="e1bb1-150">**Major version** Specifies the number that corresponds to the major release of the client.</span></span>

  - <span data-ttu-id="e1bb1-151">**マイナーバージョン**クライアントのマイナーリリースに対応する番号を指定します。</span><span class="sxs-lookup"><span data-stu-id="e1bb1-151">**Minor version** Specifies the number that corresponds to the minor release of the client.</span></span>

  - <span data-ttu-id="e1bb1-152">**ビルド**クライアントのメジャーとマイナーのリリースに対応するビルド番号を指定します。</span><span class="sxs-lookup"><span data-stu-id="e1bb1-152">**Build** Specifies the build number that corresponds to the major and minor release of the client.</span></span>

  - <span data-ttu-id="e1bb1-153">**更新**クライアントの更新されたリリースに対応する番号を指定します。</span><span class="sxs-lookup"><span data-stu-id="e1bb1-153">**Update** Specifies the number that corresponds to the updated release of the client.</span></span>

- <span data-ttu-id="e1bb1-154">**比較演算**前の手順で指定したクライアントバージョンの照合操作を指定できます。</span><span class="sxs-lookup"><span data-stu-id="e1bb1-154">**Comparison operation** You can specify the matching operation for the client version you specified in the preceding steps.</span></span> <span data-ttu-id="e1bb1-155">次の操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="e1bb1-155">The following operations are available:</span></span>

  - <span data-ttu-id="e1bb1-156">**[同じ]**</span><span class="sxs-lookup"><span data-stu-id="e1bb1-156">**Same as**</span></span>

  - <span data-ttu-id="e1bb1-157">**[等しくない]**</span><span class="sxs-lookup"><span data-stu-id="e1bb1-157">**Is not**</span></span>

  - <span data-ttu-id="e1bb1-158">**[より新しい]**</span><span class="sxs-lookup"><span data-stu-id="e1bb1-158">**Newer than**</span></span>

  - <span data-ttu-id="e1bb1-159">**[より新しいか同じ]**</span><span class="sxs-lookup"><span data-stu-id="e1bb1-159">**Newer than or same as**</span></span>

  - <span data-ttu-id="e1bb1-160">**[より古い]**</span><span class="sxs-lookup"><span data-stu-id="e1bb1-160">**Older than**</span></span>

  - <span data-ttu-id="e1bb1-161">**[より古いか同じ]**</span><span class="sxs-lookup"><span data-stu-id="e1bb1-161">**Older than or same as**</span></span>

- <span data-ttu-id="e1bb1-162">**操作**前の手順の条件が満たされたときに実行するアクションを指定できます。</span><span class="sxs-lookup"><span data-stu-id="e1bb1-162">**Action** You can specify the action to perform when the criteria in the preceding steps are met.</span></span> <span data-ttu-id="e1bb1-163">次の操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="e1bb1-163">The following actions are available:</span></span>

  - <span data-ttu-id="e1bb1-164">**許可**クライアントがログオンできるようにします。</span><span class="sxs-lookup"><span data-stu-id="e1bb1-164">**Allow** Allows the client to log on.</span></span>

  - <span data-ttu-id="e1bb1-165">**許可とアップグレード**クライアントが Windows Server Update Service または Microsoft Update からログオンして更新プログラムを受信できるようにします。</span><span class="sxs-lookup"><span data-stu-id="e1bb1-165">**Allow and Upgrade** Allows the client to log on and receive updates from Windows Server Update Service or Microsoft Update.</span></span> <span data-ttu-id="e1bb1-166">この操作は、ユーザーエージェント**OC**が選択されている場合にのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="e1bb1-166">This action is available only when user agent **OC** is selected.</span></span>

    > [!NOTE]
    > <span data-ttu-id="e1bb1-167">このアクションを選ぶと、次回ユーザーが Skype for Business にサインインしたときに通知が表示されます。</span><span class="sxs-lookup"><span data-stu-id="e1bb1-167">Selecting this action causes a notification to appear the next time users sign in to Skype for Business.</span></span> <span data-ttu-id="e1bb1-168">この通知では、Windows Server Update Service または Microsoft Update に更新がまだリリースされていなくても、更新が利用できるようになったことが伝えられます。</span><span class="sxs-lookup"><span data-stu-id="e1bb1-168">The notification states that an update is available, even if updates have not yet been released to Windows Server Update Service or Microsoft Update.</span></span> <span data-ttu-id="e1bb1-169">混乱を避けるため、このアクションは必ず更新が利用できるようになってから選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e1bb1-169">To avoid confusion, you should choose this action only after updates become available.</span></span>

  - <span data-ttu-id="e1bb1-170">**URL で許可**クライアントがログオンして、別のクライアントバージョンをダウンロードする場所に関するメッセージを表示することを許可します。</span><span class="sxs-lookup"><span data-stu-id="e1bb1-170">**Allow with URL** Allows the client to log on and displays a message about where to download another client version.</span></span> <span data-ttu-id="e1bb1-171">[**URL**] フィールドで URL を指定します。</span><span class="sxs-lookup"><span data-stu-id="e1bb1-171">You specify the URL in the **URL** field.</span></span>

  - <span data-ttu-id="e1bb1-172">**ブロック**クライアントがログオンできないようにします。</span><span class="sxs-lookup"><span data-stu-id="e1bb1-172">**Block** Prevents the client from logging on.</span></span>

  - <span data-ttu-id="e1bb1-173">**ブロックとアップグレード**クライアントがログオンし、Windows Server Update Service または Microsoft Update から更新プログラムを受信できるようにします。</span><span class="sxs-lookup"><span data-stu-id="e1bb1-173">**Block and Upgrade** Prevents the client from logging on and allows the client to receive updates from Windows Server Update Service or Microsoft Update.</span></span> <span data-ttu-id="e1bb1-174">この操作は、ユーザーエージェント**OC**が選択されている場合にのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="e1bb1-174">This action is available only when user agent **OC** is selected.</span></span>

  - <span data-ttu-id="e1bb1-p110">[**URL を使用した禁止**]   クライアントがログオンし、他のクライアント バージョンをダウンロードする場所についてのメッセージを表示することを禁止します。[**URL**] フィールドで URL を指定します。</span><span class="sxs-lookup"><span data-stu-id="e1bb1-p110">**Block with URL** prevents the client from logging on and displays a message about where to download another client version. You specify the URL in the **URL** field.</span></span>

<span data-ttu-id="e1bb1-p111">クライアントとクライアント バージョンの間の相互運用性の詳細については、「計画」のドキュメントの「[Client Interoperability in Lync 2013 Preview](https://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx)」を参照してください。クライアント バージョンの構成の使用の詳細については、「操作」のドキュメントの「[Modify the Default Action for Clients Not Explicitly Supported or Restricted](https://technet.microsoft.com/library/548dd0f5-62fe-4c3f-8952-2b9fd4c5fff3.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e1bb1-p111">For details about interoperability among clients and client versions, see [Client Interoperability in Lync 2013 Preview](https://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx) in the Planning documentation. For details about working with client version configurations, see [Modify the Default Action for Clients Not Explicitly Supported or Restricted](https://technet.microsoft.com/library/548dd0f5-62fe-4c3f-8952-2b9fd4c5fff3.aspx) in the Operations documentation.</span></span>

