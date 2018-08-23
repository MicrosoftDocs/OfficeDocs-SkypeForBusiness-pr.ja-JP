---
title: クライアント バージョン ルール
ms.author: dianef
author: dianef77
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.ClientCVPolicyRuleEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6e7e94c2-1475-4334-b8da-716b24a4c255
ROBOTS: NOINDEX, NOFOLLOW
description: クライアント バージョン ポリシーは、一連のクライアント バージョン ルールで構成されます。これらのルールでは、ユーザーが特定のクライアントおよびクライアント バージョンでログオンしようとしたときに実行するアクションが定義されています。
ms.openlocfilehash: ddebab20af21be8a6c3cbff558cec6d118dd60d0
ms.sourcegitcommit: c85211a22921d02ffa9f300a4f8350ffbb90b38c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/10/2018
ms.locfileid: "22601914"
---
# <a name="client-version-rule"></a><span data-ttu-id="ebffa-104">クライアント バージョン ルール</span><span class="sxs-lookup"><span data-stu-id="ebffa-104">Client Version Rule</span></span>
 
<span data-ttu-id="ebffa-p102">クライアント バージョン ポリシーは、一連のクライアント バージョン ルールで構成されます。これらのルールでは、ユーザーが特定のクライアントおよびクライアント バージョンでログオンしようとしたときに実行するアクションが定義されています。</span><span class="sxs-lookup"><span data-stu-id="ebffa-p102">A client version policy is made up of a set of client version rules. These rules define the actions that should be taken when users attempt to log on with specific clients and client versions.</span></span>
  
## <a name="tasks-you-can-perform"></a><span data-ttu-id="ebffa-107">実行できるタスク</span><span class="sxs-lookup"><span data-stu-id="ebffa-107">Tasks you can perform</span></span>

<span data-ttu-id="ebffa-108">[**新規 クライアント バージョンの構成**] または [**編集 クライアント バージョンの構成**] ページでは、次のタスクを実行できます。</span><span class="sxs-lookup"><span data-stu-id="ebffa-108">You can perform the following tasks on the **New Client Version Configuration** or **Edit Client Version Configuration** page:</span></span>
  
- <span data-ttu-id="ebffa-109">クライアント バージョン ポリシーに新しいルールを追加する。</span><span class="sxs-lookup"><span data-stu-id="ebffa-109">Add new rules to a client version policy.</span></span>
    
- <span data-ttu-id="ebffa-110">既存のクライアント バージョン ポリシーを構成するルールを変更する。</span><span class="sxs-lookup"><span data-stu-id="ebffa-110">Modify the rules that make up an existing client version policy</span></span>
    
## <a name="ui-reference"></a><span data-ttu-id="ebffa-111">UI リファレンス</span><span class="sxs-lookup"><span data-stu-id="ebffa-111">UI Reference</span></span>

<span data-ttu-id="ebffa-112">以下は、ページ上のメニュー、コマンド、フィールド、およびプロパティについての説明です。</span><span class="sxs-lookup"><span data-stu-id="ebffa-112">The following lists describe the menus, command, fields, and properties on the page.</span></span>
  
- <span data-ttu-id="ebffa-113">**ユーザー エージェント**クライアントの種類を一覧から選択できます。</span><span class="sxs-lookup"><span data-stu-id="ebffa-113">**User agent** You can select a client type from the list.</span></span> <span data-ttu-id="ebffa-114">次の表は、ユーザー エージェントのコードを定義します。</span><span class="sxs-lookup"><span data-stu-id="ebffa-114">The following table defines user agent codes.</span></span> <span data-ttu-id="ebffa-115">このリストには、レガシ クライアントの種類、それらの一部がサポートされていませんが含まれています。</span><span class="sxs-lookup"><span data-stu-id="ebffa-115">This list includes legacy client types, some of which are no longer supported.</span></span>  
    
|<span data-ttu-id="ebffa-116">**クライアント名**</span><span class="sxs-lookup"><span data-stu-id="ebffa-116">**Client Name**</span></span>|<span data-ttu-id="ebffa-117">**ユーザー エージェント**</span><span class="sxs-lookup"><span data-stu-id="ebffa-117">**User Agent**</span></span>|
|:-----|:-----|
|<span data-ttu-id="ebffa-118">Lync 2013 では、Lync 2010 では、Office Communicator</span><span class="sxs-lookup"><span data-stu-id="ebffa-118">Lync 2013, Lync 2010, Office Communicator</span></span>  <br/> |<span data-ttu-id="ebffa-119">OC</span><span class="sxs-lookup"><span data-stu-id="ebffa-119">OC</span></span>  <br/> |
|<span data-ttu-id="ebffa-120">Lync Web アプリケーションでは、Communicator Web Access</span><span class="sxs-lookup"><span data-stu-id="ebffa-120">Lync Web App, Communicator Web Access</span></span>  <br/> |<span data-ttu-id="ebffa-121">CWA</span><span class="sxs-lookup"><span data-stu-id="ebffa-121">CWA</span></span>  <br/> |
|<span data-ttu-id="ebffa-122">Office Communicator の電話、Lync の電話のエディション</span><span class="sxs-lookup"><span data-stu-id="ebffa-122">Lync Phone Edition, Office Communicator Phone</span></span>  <br/> |<span data-ttu-id="ebffa-123">OCPhone</span><span class="sxs-lookup"><span data-stu-id="ebffa-123">OCPhone</span></span>  <br/> |
|<span data-ttu-id="ebffa-124">Communicator Phone Edition プラットフォーム</span><span class="sxs-lookup"><span data-stu-id="ebffa-124">Communicator Phone Edition Platform</span></span>  <br/> |<span data-ttu-id="ebffa-125">CPE</span><span class="sxs-lookup"><span data-stu-id="ebffa-125">CPE</span></span>  <br/> |
|<span data-ttu-id="ebffa-126">統合コミュニケーション プラットフォーム</span><span class="sxs-lookup"><span data-stu-id="ebffa-126">Unified Communications Platform</span></span>  <br/> |<span data-ttu-id="ebffa-127">UCCP</span><span class="sxs-lookup"><span data-stu-id="ebffa-127">UCCP</span></span>  <br/> |
|<span data-ttu-id="ebffa-128">Lync 2010 Attendee</span><span class="sxs-lookup"><span data-stu-id="ebffa-128">Lync 2010 Attendee</span></span>  <br/> |<span data-ttu-id="ebffa-129">AOC</span><span class="sxs-lookup"><span data-stu-id="ebffa-129">AOC</span></span>  <br/> |
|<span data-ttu-id="ebffa-130">Live Meeting アドイン</span><span class="sxs-lookup"><span data-stu-id="ebffa-130">Live Meeting Add-In</span></span>  <br/> |<span data-ttu-id="ebffa-131">LiveMeetingAddins</span><span class="sxs-lookup"><span data-stu-id="ebffa-131">LiveMeetingAddins</span></span>  <br/> |
|<span data-ttu-id="ebffa-132">Office Live Meeting</span><span class="sxs-lookup"><span data-stu-id="ebffa-132">Office Live Meeting</span></span>  <br/> |<span data-ttu-id="ebffa-133">LMC</span><span class="sxs-lookup"><span data-stu-id="ebffa-133">LMC</span></span>  <br/> |
|<span data-ttu-id="ebffa-134">Windows Messenger</span><span class="sxs-lookup"><span data-stu-id="ebffa-134">Windows Messenger</span></span>  <br/> |<span data-ttu-id="ebffa-135">WM</span><span class="sxs-lookup"><span data-stu-id="ebffa-135">WM</span></span>  <br/> |
|<span data-ttu-id="ebffa-136">リアルタイム通信クライアント</span><span class="sxs-lookup"><span data-stu-id="ebffa-136">Real-time Communications Client</span></span>  <br/> |<span data-ttu-id="ebffa-137">RTC</span><span class="sxs-lookup"><span data-stu-id="ebffa-137">RTC</span></span>  <br/> |
|<span data-ttu-id="ebffa-138">IPad の Lync 2010</span><span class="sxs-lookup"><span data-stu-id="ebffa-138">Lync 2010 for iPad</span></span>  <br/> |<span data-ttu-id="ebffa-139">iPadLync</span><span class="sxs-lookup"><span data-stu-id="ebffa-139">iPadLync</span></span>  <br/> |
|<span data-ttu-id="ebffa-140">IPhone の Lync 2010</span><span class="sxs-lookup"><span data-stu-id="ebffa-140">Lync 2010 for iPhone</span></span>  <br/> |<span data-ttu-id="ebffa-141">iPhoneLync</span><span class="sxs-lookup"><span data-stu-id="ebffa-141">iPhoneLync</span></span>  <br/> |
|<span data-ttu-id="ebffa-142">Windows Phone の Lync 2010</span><span class="sxs-lookup"><span data-stu-id="ebffa-142">Lync 2010 for Windows Phone</span></span>  <br/> |<span data-ttu-id="ebffa-143">WPLync</span><span class="sxs-lookup"><span data-stu-id="ebffa-143">WPLync</span></span>  <br/> |
|<span data-ttu-id="ebffa-144">Nokia の Lync 2010</span><span class="sxs-lookup"><span data-stu-id="ebffa-144">Lync 2010 for Nokia</span></span>  <br/> |<span data-ttu-id="ebffa-145">NokiaLync</span><span class="sxs-lookup"><span data-stu-id="ebffa-145">NokiaLync</span></span>  <br/> |
|<span data-ttu-id="ebffa-146">Android の Lync 2010</span><span class="sxs-lookup"><span data-stu-id="ebffa-146">Lync 2010 for Android</span></span>  <br/> |<span data-ttu-id="ebffa-147">AndroidLync</span><span class="sxs-lookup"><span data-stu-id="ebffa-147">AndroidLync</span></span>  <br/> |
|<span data-ttu-id="ebffa-148">Mobility Service</span><span class="sxs-lookup"><span data-stu-id="ebffa-148">Mobility service</span></span>  <br/> |<span data-ttu-id="ebffa-149">McxService</span><span class="sxs-lookup"><span data-stu-id="ebffa-149">McxService</span></span>  <br/> |
   
- <span data-ttu-id="ebffa-150">**バージョン番号**次のフィールドにバージョン番号を指定するか、クライアントのバージョン番号を示すためにワイルドカードを使用できます。</span><span class="sxs-lookup"><span data-stu-id="ebffa-150">**Version number** You can specify the version numbers for the following fields, or use wildcards to indicate the client version number.</span></span>
    
  - <span data-ttu-id="ebffa-151">**メジャー バージョン**主要なリリースのクライアントに対応する番号を指定します。</span><span class="sxs-lookup"><span data-stu-id="ebffa-151">**Major version** Specifies the number that corresponds to the major release of the client.</span></span>
    
  - <span data-ttu-id="ebffa-152">**マイナー バージョン**クライアントのマイナー リリースに対応する番号を指定します。</span><span class="sxs-lookup"><span data-stu-id="ebffa-152">**Minor version** Specifies the number that corresponds to the minor release of the client.</span></span>
    
  - <span data-ttu-id="ebffa-153">**ビルド**クライアントのメジャーおよびマイナー リリースに対応するビルド番号を指定します。</span><span class="sxs-lookup"><span data-stu-id="ebffa-153">**Build** Specifies the build number that corresponds to the major and minor release of the client.</span></span>
    
  - <span data-ttu-id="ebffa-154">**更新**クライアントの更新のリリースに対応する番号を指定します。</span><span class="sxs-lookup"><span data-stu-id="ebffa-154">**Update** Specifies the number that corresponds to the updated release of the client.</span></span>
    
- <span data-ttu-id="ebffa-155">**比較演算**上記の手順で指定したクライアント バージョンの一致操作を指定できます。</span><span class="sxs-lookup"><span data-stu-id="ebffa-155">**Comparison operation** You can specify the matching operation for the client version you specified in the preceding steps.</span></span> <span data-ttu-id="ebffa-156">次の操作を紹介します。</span><span class="sxs-lookup"><span data-stu-id="ebffa-156">The following operations are available:</span></span>
    
  - <span data-ttu-id="ebffa-157">**[同じ]**</span><span class="sxs-lookup"><span data-stu-id="ebffa-157">**Same as**</span></span>
    
  - <span data-ttu-id="ebffa-158">**[等しくない]**</span><span class="sxs-lookup"><span data-stu-id="ebffa-158">**Is not**</span></span>
    
  - <span data-ttu-id="ebffa-159">**[より新しい]**</span><span class="sxs-lookup"><span data-stu-id="ebffa-159">**Newer than**</span></span>
    
  - <span data-ttu-id="ebffa-160">**[より新しいか同じ]**</span><span class="sxs-lookup"><span data-stu-id="ebffa-160">**Newer than or same as**</span></span>
    
  - <span data-ttu-id="ebffa-161">**[より古い]**</span><span class="sxs-lookup"><span data-stu-id="ebffa-161">**Older than**</span></span>
    
  - <span data-ttu-id="ebffa-162">**[より古いか同じ]**</span><span class="sxs-lookup"><span data-stu-id="ebffa-162">**Older than or same as**</span></span>
    
- <span data-ttu-id="ebffa-163">**アクション**上記の手順で条件が満たされたときに実行するアクションを指定することができます。</span><span class="sxs-lookup"><span data-stu-id="ebffa-163">**Action** You can specify the action to perform when the criteria in the preceding steps are met.</span></span> <span data-ttu-id="ebffa-164">次の操作を紹介します。</span><span class="sxs-lookup"><span data-stu-id="ebffa-164">The following actions are available:</span></span>
    
  - <span data-ttu-id="ebffa-165">**許可します。** ログオンするクライアントを使用できます。</span><span class="sxs-lookup"><span data-stu-id="ebffa-165">**Allow** Allows the client to log on.</span></span>
    
  - <span data-ttu-id="ebffa-166">**許可およびアップグレード**ログオンし、Windows Server の更新サービスまたは Microsoft Update から更新を受信するクライアントを使用できます。</span><span class="sxs-lookup"><span data-stu-id="ebffa-166">**Allow and Upgrade** Allows the client to log on and receive updates from Windows Server Update Service or Microsoft Update.</span></span> <span data-ttu-id="ebffa-167">この操作は、 **OC**のユーザー エージェントが選択した場合のみ利用可能です。</span><span class="sxs-lookup"><span data-stu-id="ebffa-167">This action is available only when user agent **OC** is selected.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="ebffa-168">このアクションを選択すると、次にユーザーがビジネスのための Skype にサインインを表示する通知が発生します。</span><span class="sxs-lookup"><span data-stu-id="ebffa-168">Selecting this action causes a notification to appear the next time users sign in to Skype for Business.</span></span> <span data-ttu-id="ebffa-169">この通知では、Windows Server Update Service または Microsoft Update に更新がまだリリースされていなくても、更新が利用できるようになったことが伝えられます。</span><span class="sxs-lookup"><span data-stu-id="ebffa-169">The notification states that an update is available, even if updates have not yet been released to Windows Server Update Service or Microsoft Update.</span></span> <span data-ttu-id="ebffa-170">混乱を避けるため、このアクションは必ず更新が利用できるようになってから選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ebffa-170">To avoid confusion, you should choose this action only after updates become available.</span></span> 
  
  - <span data-ttu-id="ebffa-171">**URL を許可します。** により、クライアントがログオンして、別のクライアント バージョンをダウンロードする場所についてのメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="ebffa-171">**Allow with URL** Allows the client to log on and displays a message about where to download another client version.</span></span> <span data-ttu-id="ebffa-172">[**URL**] フィールドで URL を指定します。</span><span class="sxs-lookup"><span data-stu-id="ebffa-172">You specify the URL in the **URL** field.</span></span>
    
  - <span data-ttu-id="ebffa-173">**ブロック**クライアントがログオンできないようにします。</span><span class="sxs-lookup"><span data-stu-id="ebffa-173">**Block** Prevents the client from logging on.</span></span>
    
  - <span data-ttu-id="ebffa-174">**ブロックおよびアップグレード**クライアントがログオンできないようにし、クライアントが Windows Server の更新サービスまたは Microsoft Update から更新を受信することができます。</span><span class="sxs-lookup"><span data-stu-id="ebffa-174">**Block and Upgrade** Prevents the client from logging on and allows the client to receive updates from Windows Server Update Service or Microsoft Update.</span></span> <span data-ttu-id="ebffa-175">この操作は、 **OC**のユーザー エージェントが選択した場合のみ利用可能です。</span><span class="sxs-lookup"><span data-stu-id="ebffa-175">This action is available only when user agent **OC** is selected.</span></span>
    
  - <span data-ttu-id="ebffa-p110">[**URL を使用した禁止**]   クライアントがログオンし、他のクライアント バージョンをダウンロードする場所についてのメッセージを表示することを禁止します。[**URL**] フィールドで URL を指定します。</span><span class="sxs-lookup"><span data-stu-id="ebffa-p110">**Block with URL** prevents the client from logging on and displays a message about where to download another client version. You specify the URL in the **URL** field.</span></span>
    
<span data-ttu-id="ebffa-178">クライアントとクライアントのバージョン間での相互運用性に関する詳細については、計画ドキュメントの[クライアントの相互運用性](http://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ebffa-178">For details about interoperability among clients and client versions, see [Client Interoperability](http://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx) in the Planning documentation.</span></span> <span data-ttu-id="ebffa-179">クライアント バージョンの構成の操作に関する詳細については、操作マニュアルの[変更クライアントに明示的にサポートされていないまたは制限付きサイトの既定のアクション](http://technet.microsoft.com/library/548dd0f5-62fe-4c3f-8952-2b9fd4c5fff3.aspx)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ebffa-179">For details about working with client version configurations, see [Modify the Default Action for Clients Not Explicitly Supported or Restricted](http://technet.microsoft.com/library/548dd0f5-62fe-4c3f-8952-2b9fd4c5fff3.aspx) in the Operations documentation.</span></span>

