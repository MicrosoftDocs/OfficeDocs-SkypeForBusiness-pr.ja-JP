---
title: クライアント バージョン ルール
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/23/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.ClientCVPolicyRuleEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6e7e94c2-1475-4334-b8da-716b24a4c255
description: クライアント バージョン ポリシーは、一連のクライアント バージョン ルールで構成されます。これらのルールでは、ユーザーが特定のクライアントおよびクライアント バージョンでログオンしようとしたときに実行するアクションが定義されています。
ms.openlocfilehash: 870f0d46ff50b4fabab9b4f098cb569ae2c9ee82
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41823060"
---
# <a name="client-version-rule"></a><span data-ttu-id="d8a2f-104">クライアント バージョン ルール</span><span class="sxs-lookup"><span data-stu-id="d8a2f-104">Client Version Rule</span></span>

<span data-ttu-id="d8a2f-p102">クライアント バージョン ポリシーは、一連のクライアント バージョン ルールで構成されます。これらのルールでは、ユーザーが特定のクライアントおよびクライアント バージョンでログオンしようとしたときに実行するアクションが定義されています。</span><span class="sxs-lookup"><span data-stu-id="d8a2f-p102">A client version policy is made up of a set of client version rules. These rules define the actions that should be taken when users attempt to log on with specific clients and client versions.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="d8a2f-107">実行できるタスク</span><span class="sxs-lookup"><span data-stu-id="d8a2f-107">Tasks you can perform</span></span>

<span data-ttu-id="d8a2f-108">[**新規 クライアント バージョンの構成**] または [**編集 クライアント バージョンの構成**] ページでは、次のタスクを実行できます。</span><span class="sxs-lookup"><span data-stu-id="d8a2f-108">You can perform the following tasks on the **New Client Version Configuration** or **Edit Client Version Configuration** page:</span></span>

- <span data-ttu-id="d8a2f-109">クライアント バージョン ポリシーに新しいルールを追加する。</span><span class="sxs-lookup"><span data-stu-id="d8a2f-109">Add new rules to a client version policy.</span></span>

- <span data-ttu-id="d8a2f-110">既存のクライアント バージョン ポリシーを構成するルールを変更する。</span><span class="sxs-lookup"><span data-stu-id="d8a2f-110">Modify the rules that make up an existing client version policy</span></span>

## <a name="ui-reference"></a><span data-ttu-id="d8a2f-111">UI リファレンス</span><span class="sxs-lookup"><span data-stu-id="d8a2f-111">UI Reference</span></span>

<span data-ttu-id="d8a2f-112">以下は、ページ上のメニュー、コマンド、フィールド、およびプロパティについての説明です。</span><span class="sxs-lookup"><span data-stu-id="d8a2f-112">The following lists describe the menus, command, fields, and properties on the page.</span></span>

- <span data-ttu-id="d8a2f-113">**ユーザーエージェント**リストからクライアントの種類を選ぶことができます。</span><span class="sxs-lookup"><span data-stu-id="d8a2f-113">**User agent** You can select a client type from the list.</span></span> <span data-ttu-id="d8a2f-114">次の表は、ユーザーエージェントコードを定義しています。</span><span class="sxs-lookup"><span data-stu-id="d8a2f-114">The following table defines user agent codes.</span></span>

|<span data-ttu-id="d8a2f-115">**クライアント名**</span><span class="sxs-lookup"><span data-stu-id="d8a2f-115">**Client Name**</span></span>|<span data-ttu-id="d8a2f-116">**ユーザー エージェント**</span><span class="sxs-lookup"><span data-stu-id="d8a2f-116">**User Agent**</span></span>|
|:-----|:-----|
|<span data-ttu-id="d8a2f-117">Lync 2013、Lync 2010、Office Communicator</span><span class="sxs-lookup"><span data-stu-id="d8a2f-117">Lync 2013, Lync 2010, Office Communicator</span></span>  <br/> |<span data-ttu-id="d8a2f-118">OC</span><span class="sxs-lookup"><span data-stu-id="d8a2f-118">OC</span></span>  <br/> |
|<span data-ttu-id="d8a2f-119">Lync Web App, Communicator Web Access</span><span class="sxs-lookup"><span data-stu-id="d8a2f-119">Lync Web App, Communicator Web Access</span></span>  <br/> |<span data-ttu-id="d8a2f-120">CWA</span><span class="sxs-lookup"><span data-stu-id="d8a2f-120">CWA</span></span>  <br/> |
|<span data-ttu-id="d8a2f-121">Lync Phone Edition、Office Communicator フォン</span><span class="sxs-lookup"><span data-stu-id="d8a2f-121">Lync Phone Edition, Office Communicator Phone</span></span>  <br/> |<span data-ttu-id="d8a2f-122">OCPhone</span><span class="sxs-lookup"><span data-stu-id="d8a2f-122">OCPhone</span></span>  <br/> |
|<span data-ttu-id="d8a2f-123">Communicator Phone Edition プラットフォーム</span><span class="sxs-lookup"><span data-stu-id="d8a2f-123">Communicator Phone Edition Platform</span></span>  <br/> |<span data-ttu-id="d8a2f-124">CPE</span><span class="sxs-lookup"><span data-stu-id="d8a2f-124">CPE</span></span>  <br/> |
|<span data-ttu-id="d8a2f-125">統合コミュニケーション プラットフォーム</span><span class="sxs-lookup"><span data-stu-id="d8a2f-125">Unified Communications Platform</span></span>  <br/> |<span data-ttu-id="d8a2f-126">UCCP</span><span class="sxs-lookup"><span data-stu-id="d8a2f-126">UCCP</span></span>  <br/> |
|<span data-ttu-id="d8a2f-127">Lync 2010 Attendee</span><span class="sxs-lookup"><span data-stu-id="d8a2f-127">Lync 2010 Attendee</span></span>  <br/> |<span data-ttu-id="d8a2f-128">AOC</span><span class="sxs-lookup"><span data-stu-id="d8a2f-128">AOC</span></span>  <br/> |
|<span data-ttu-id="d8a2f-129">Live Meeting アドイン</span><span class="sxs-lookup"><span data-stu-id="d8a2f-129">Live Meeting Add-In</span></span>  <br/> |<span data-ttu-id="d8a2f-130">LiveMeetingAddins</span><span class="sxs-lookup"><span data-stu-id="d8a2f-130">LiveMeetingAddins</span></span>  <br/> |
|<span data-ttu-id="d8a2f-131">Office Live Meeting</span><span class="sxs-lookup"><span data-stu-id="d8a2f-131">Office Live Meeting</span></span>  <br/> |<span data-ttu-id="d8a2f-132">LMC</span><span class="sxs-lookup"><span data-stu-id="d8a2f-132">LMC</span></span>  <br/> |
|<span data-ttu-id="d8a2f-133">Windows Messenger</span><span class="sxs-lookup"><span data-stu-id="d8a2f-133">Windows Messenger</span></span>  <br/> |<span data-ttu-id="d8a2f-134">WM</span><span class="sxs-lookup"><span data-stu-id="d8a2f-134">WM</span></span>  <br/> |
|<span data-ttu-id="d8a2f-135">リアルタイム通信クライアント</span><span class="sxs-lookup"><span data-stu-id="d8a2f-135">Real-time Communications Client</span></span>  <br/> |<span data-ttu-id="d8a2f-136">RTC</span><span class="sxs-lookup"><span data-stu-id="d8a2f-136">RTC</span></span>  <br/> |
|<span data-ttu-id="d8a2f-137">Lync 2010 for iPad</span><span class="sxs-lookup"><span data-stu-id="d8a2f-137">Lync 2010 for iPad</span></span>  <br/> |<span data-ttu-id="d8a2f-138">iPadLync</span><span class="sxs-lookup"><span data-stu-id="d8a2f-138">iPadLync</span></span>  <br/> |
|<span data-ttu-id="d8a2f-139">Lync 2010 for iPhone</span><span class="sxs-lookup"><span data-stu-id="d8a2f-139">Lync 2010 for iPhone</span></span>  <br/> |<span data-ttu-id="d8a2f-140">iPhoneLync</span><span class="sxs-lookup"><span data-stu-id="d8a2f-140">iPhoneLync</span></span>  <br/> |
|<span data-ttu-id="d8a2f-141">Windows Phone 版 Lync 2010</span><span class="sxs-lookup"><span data-stu-id="d8a2f-141">Lync 2010 for Windows Phone</span></span>  <br/> |<span data-ttu-id="d8a2f-142">WPLync</span><span class="sxs-lookup"><span data-stu-id="d8a2f-142">WPLync</span></span>  <br/> |
|<span data-ttu-id="d8a2f-143">Lync 2010 for Nokia</span><span class="sxs-lookup"><span data-stu-id="d8a2f-143">Lync 2010 for Nokia</span></span>  <br/> |<span data-ttu-id="d8a2f-144">NokiaLync</span><span class="sxs-lookup"><span data-stu-id="d8a2f-144">NokiaLync</span></span>  <br/> |
|<span data-ttu-id="d8a2f-145">Lync 2010 for Android</span><span class="sxs-lookup"><span data-stu-id="d8a2f-145">Lync 2010 for Android</span></span>  <br/> |<span data-ttu-id="d8a2f-146">AndroidLync</span><span class="sxs-lookup"><span data-stu-id="d8a2f-146">AndroidLync</span></span>  <br/> |
|<span data-ttu-id="d8a2f-147">Mobility Service</span><span class="sxs-lookup"><span data-stu-id="d8a2f-147">Mobility service</span></span>  <br/> |<span data-ttu-id="d8a2f-148">McxService</span><span class="sxs-lookup"><span data-stu-id="d8a2f-148">McxService</span></span>  <br/> |

- <span data-ttu-id="d8a2f-149">**バージョン番号**次のフィールドのバージョン番号を指定するか、ワイルドカードを使用してクライアントのバージョン番号を示すことができます。</span><span class="sxs-lookup"><span data-stu-id="d8a2f-149">**Version number** You can specify the version numbers for the following fields, or use wildcards to indicate the client version number.</span></span>

  - <span data-ttu-id="d8a2f-150">**メジャーバージョン**クライアントのメジャーリリースに対応する番号を指定します。</span><span class="sxs-lookup"><span data-stu-id="d8a2f-150">**Major version** Specifies the number that corresponds to the major release of the client.</span></span>

  - <span data-ttu-id="d8a2f-151">**マイナーバージョン**クライアントのマイナーリリースに対応する番号を指定します。</span><span class="sxs-lookup"><span data-stu-id="d8a2f-151">**Minor version** Specifies the number that corresponds to the minor release of the client.</span></span>

  - <span data-ttu-id="d8a2f-152">**ビルド**クライアントのメジャーとマイナーのリリースに対応するビルド番号を指定します。</span><span class="sxs-lookup"><span data-stu-id="d8a2f-152">**Build** Specifies the build number that corresponds to the major and minor release of the client.</span></span>

  - <span data-ttu-id="d8a2f-153">**更新**クライアントの更新されたリリースに対応する番号を指定します。</span><span class="sxs-lookup"><span data-stu-id="d8a2f-153">**Update** Specifies the number that corresponds to the updated release of the client.</span></span>

- <span data-ttu-id="d8a2f-154">**比較演算**前の手順で指定したクライアントバージョンの照合操作を指定できます。</span><span class="sxs-lookup"><span data-stu-id="d8a2f-154">**Comparison operation** You can specify the matching operation for the client version you specified in the preceding steps.</span></span> <span data-ttu-id="d8a2f-155">次の操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="d8a2f-155">The following operations are available:</span></span>

  - <span data-ttu-id="d8a2f-156">**[同じ]**</span><span class="sxs-lookup"><span data-stu-id="d8a2f-156">**Same as**</span></span>

  - <span data-ttu-id="d8a2f-157">**[等しくない]**</span><span class="sxs-lookup"><span data-stu-id="d8a2f-157">**Is not**</span></span>

  - <span data-ttu-id="d8a2f-158">**[より新しい]**</span><span class="sxs-lookup"><span data-stu-id="d8a2f-158">**Newer than**</span></span>

  - <span data-ttu-id="d8a2f-159">**[より新しいか同じ]**</span><span class="sxs-lookup"><span data-stu-id="d8a2f-159">**Newer than or same as**</span></span>

  - <span data-ttu-id="d8a2f-160">**[より古い]**</span><span class="sxs-lookup"><span data-stu-id="d8a2f-160">**Older than**</span></span>

  - <span data-ttu-id="d8a2f-161">**[より古いか同じ]**</span><span class="sxs-lookup"><span data-stu-id="d8a2f-161">**Older than or same as**</span></span>

- <span data-ttu-id="d8a2f-162">**操作**前の手順の条件が満たされたときに実行するアクションを指定できます。</span><span class="sxs-lookup"><span data-stu-id="d8a2f-162">**Action** You can specify the action to perform when the criteria in the preceding steps are met.</span></span> <span data-ttu-id="d8a2f-163">次の操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="d8a2f-163">The following actions are available:</span></span>

  - <span data-ttu-id="d8a2f-164">**許可**クライアントがログオンできるようにします。</span><span class="sxs-lookup"><span data-stu-id="d8a2f-164">**Allow** Allows the client to log on.</span></span>

  - <span data-ttu-id="d8a2f-165">**許可とアップグレード**クライアントが Windows Server Update Service または Microsoft Update からログオンして更新プログラムを受信できるようにします。</span><span class="sxs-lookup"><span data-stu-id="d8a2f-165">**Allow and Upgrade** Allows the client to log on and receive updates from Windows Server Update Service or Microsoft Update.</span></span> <span data-ttu-id="d8a2f-166">この操作は、ユーザーエージェント**OC**が選択されている場合にのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="d8a2f-166">This action is available only when user agent **OC** is selected.</span></span>

    > [!NOTE]
    > <span data-ttu-id="d8a2f-167">このアクションを選ぶと、次回ユーザーが Skype for Business にサインインしたときに通知が表示されます。</span><span class="sxs-lookup"><span data-stu-id="d8a2f-167">Selecting this action causes a notification to appear the next time users sign in to Skype for Business.</span></span> <span data-ttu-id="d8a2f-168">この通知では、Windows Server Update Service または Microsoft Update に更新がまだリリースされていなくても、更新が利用できるようになったことが伝えられます。</span><span class="sxs-lookup"><span data-stu-id="d8a2f-168">The notification states that an update is available, even if updates have not yet been released to Windows Server Update Service or Microsoft Update.</span></span> <span data-ttu-id="d8a2f-169">混乱を避けるため、このアクションは必ず更新が利用できるようになってから選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d8a2f-169">To avoid confusion, you should choose this action only after updates become available.</span></span>

  - <span data-ttu-id="d8a2f-170">**URL で許可**クライアントがログオンして、別のクライアントバージョンをダウンロードする場所に関するメッセージを表示することを許可します。</span><span class="sxs-lookup"><span data-stu-id="d8a2f-170">**Allow with URL** Allows the client to log on and displays a message about where to download another client version.</span></span> <span data-ttu-id="d8a2f-171">[**URL**] フィールドで URL を指定します。</span><span class="sxs-lookup"><span data-stu-id="d8a2f-171">You specify the URL in the **URL** field.</span></span>

  - <span data-ttu-id="d8a2f-172">**ブロック**クライアントがログオンできないようにします。</span><span class="sxs-lookup"><span data-stu-id="d8a2f-172">**Block** Prevents the client from logging on.</span></span>

  - <span data-ttu-id="d8a2f-173">**ブロックとアップグレード**クライアントがログオンし、Windows Server Update Service または Microsoft Update から更新プログラムを受信できるようにします。</span><span class="sxs-lookup"><span data-stu-id="d8a2f-173">**Block and Upgrade** Prevents the client from logging on and allows the client to receive updates from Windows Server Update Service or Microsoft Update.</span></span> <span data-ttu-id="d8a2f-174">この操作は、ユーザーエージェント**OC**が選択されている場合にのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="d8a2f-174">This action is available only when user agent **OC** is selected.</span></span>

  - <span data-ttu-id="d8a2f-p110">[**URL を使用した禁止**]   クライアントがログオンし、他のクライアント バージョンをダウンロードする場所についてのメッセージを表示することを禁止します。[**URL**] フィールドで URL を指定します。</span><span class="sxs-lookup"><span data-stu-id="d8a2f-p110">**Block with URL** prevents the client from logging on and displays a message about where to download another client version. You specify the URL in the **URL** field.</span></span>

<span data-ttu-id="d8a2f-p111">クライアントとクライアント バージョンの間の相互運用性の詳細については、「計画」のドキュメントの「[Client Interoperability in Lync 2013 Preview](https://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx)」を参照してください。クライアント バージョンの構成の使用の詳細については、「操作」のドキュメントの「[Modify the Default Action for Clients Not Explicitly Supported or Restricted](https://technet.microsoft.com/library/548dd0f5-62fe-4c3f-8952-2b9fd4c5fff3.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d8a2f-p111">For details about interoperability among clients and client versions, see [Client Interoperability in Lync 2013 Preview](https://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx) in the Planning documentation. For details about working with client version configurations, see [Modify the Default Action for Clients Not Explicitly Supported or Restricted](https://technet.microsoft.com/library/548dd0f5-62fe-4c3f-8952-2b9fd4c5fff3.aspx) in the Operations documentation.</span></span>

