---
title: Skype for Business での Mac クライアントのエクスペリエンスをカスタマイズする
ms.author: v-lanac
author: lanachin
manager: serdars
ms.reviewer: PhillipGarding
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d1d9cfec-e923-4d02-a306-ee40a9114cb8
description: この記事では、Mac クライアント用の Skype for Business で利用できる、クライアントの基本設定と既定値について説明します。また、それらをアプリ以外から編集する方法についても説明します。
ms.openlocfilehash: ac398ec928ac4f00b107a2fb9bff1dda8e65cd68
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33893491"
---
# <a name="customize-the-mac-client-experience-in-skype-for-business"></a><span data-ttu-id="4365c-103">Skype for Business での Mac クライアントのエクスペリエンスをカスタマイズする</span><span class="sxs-lookup"><span data-stu-id="4365c-103">Customize the Mac client experience in Skype for Business</span></span>
 
<span data-ttu-id="4365c-104">この記事では、Mac クライアント用の Skype for Business で利用できる、クライアントの基本設定と既定値について説明します。また、それらをアプリ以外から編集する方法についても説明します。</span><span class="sxs-lookup"><span data-stu-id="4365c-104">This article describes the client preferences and defaults available for the Skype for Business on Mac client, and how to edit them from outside the App.</span></span>
  
## <a name="skype-for-business-on-mac-client-preference-settings"></a><span data-ttu-id="4365c-105">Mac クライアント用の Skype for Business の基本設定</span><span class="sxs-lookup"><span data-stu-id="4365c-105">Skype for Business on Mac client preference settings</span></span>

<span data-ttu-id="4365c-106">特定の機能および Mac クライアントのビジネス用の Skype を利用可能な動作は、クライアント上でのプリファレンス設定によって決定されます。</span><span class="sxs-lookup"><span data-stu-id="4365c-106">Certain features and behaviors that are available to Skype for Business on Mac clients are determined by preference settings on the client.</span></span> <span data-ttu-id="4365c-107">次のパスにあるビジネス クライアント用の Skype がインストールされている Mac 上のファイルは、Mac の環境設定でビジネス用の Skype を参照ください。</span><span class="sxs-lookup"><span data-stu-id="4365c-107">The Skype for Business on Mac preferences are found in a file located on Macs that have installed the Skype for Business client located at the following path:</span></span> 
  
 <span data-ttu-id="4365c-108">**~/Library/Containers/com.microsoft.SkypeForBusiness/Data/Library/Preferences/com.microsoft.SkypeForBusiness.plist**</span><span class="sxs-lookup"><span data-stu-id="4365c-108">**~/Library/Containers/com.microsoft.SkypeForBusiness/Data/Library/Preferences/com.microsoft.SkypeForBusiness.plist**</span></span>
  
<span data-ttu-id="4365c-109">これらの環境設定を設定するのにはクライアントの Mac のターミナルのプロンプトを表示し、として必要な既定値ライト com.microsoft.SkypeForBusiness のキー操作が次の表に記載されている基本設定キーを使用して、入力します。</span><span class="sxs-lookup"><span data-stu-id="4365c-109">To set these preferences, get to a terminal prompt on the client's Mac and as needed enter defaults write com.microsoft.SkypeForBusiness key commands using the preference keys described in the following table.</span></span>
  
<span data-ttu-id="4365c-110">**クライアントの基本設定のキー**</span><span class="sxs-lookup"><span data-stu-id="4365c-110">**Client preference keys**</span></span>


| <span data-ttu-id="4365c-111">キー</span><span class="sxs-lookup"><span data-stu-id="4365c-111">Key</span></span> | <span data-ttu-id="4365c-112">型</span><span class="sxs-lookup"><span data-stu-id="4365c-112">Type</span></span> | <span data-ttu-id="4365c-113">値</span><span class="sxs-lookup"><span data-stu-id="4365c-113">Value</span></span> | <span data-ttu-id="4365c-114">説明</span><span class="sxs-lookup"><span data-stu-id="4365c-114">Description</span></span> |
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="4365c-115">AutoDetectAutoDiscoveryURLs</span><span class="sxs-lookup"><span data-stu-id="4365c-115">AutoDetectAutoDiscoveryURLs</span></span>    |<span data-ttu-id="4365c-116">ブール</span><span class="sxs-lookup"><span data-stu-id="4365c-116">Bool</span></span>    |<span data-ttu-id="4365c-117">0 = 手動のサーバー構成</span><span class="sxs-lookup"><span data-stu-id="4365c-117">0 = manual server configuration</span></span>  <br/> <span data-ttu-id="4365c-118">1 = 自動のサーバー構成 (既定)</span><span class="sxs-lookup"><span data-stu-id="4365c-118">1 = automatic server detection (default)</span></span>    |<span data-ttu-id="4365c-119">ビジネス用の Skype でのトランスポートおよびサインイン時に使用するサーバーを識別する方法を指定します。</span><span class="sxs-lookup"><span data-stu-id="4365c-119">Specify how Skype for Business identifies the transport and server to use during sign-in.</span></span> <span data-ttu-id="4365c-120">このポリシー設定を有効にする場合は、**internalAutoDiscoveryURL** および **externalAutoDiscoveryURL** を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="4365c-120">If you enable this policy setting, you must specify **internalAutoDiscoveryURL** and **externalAutoDiscoveryURL**.</span></span>   |
|<span data-ttu-id="4365c-121">internalAutoDiscoveryURL</span><span class="sxs-lookup"><span data-stu-id="4365c-121">internalAutoDiscoveryURL</span></span>    |<span data-ttu-id="4365c-122">String</span><span class="sxs-lookup"><span data-stu-id="4365c-122">String</span></span>    |<span data-ttu-id="4365c-123">完全な自動検出 URL</span><span class="sxs-lookup"><span data-stu-id="4365c-123">Full autodiscover URL</span></span>    |<span data-ttu-id="4365c-124">内部自動検出 URL</span><span class="sxs-lookup"><span data-stu-id="4365c-124">Internal autodiscover URL</span></span>    |
|<span data-ttu-id="4365c-125">externalAutoDiscoveryURL</span><span class="sxs-lookup"><span data-stu-id="4365c-125">externalAutoDiscoveryURL</span></span>    |<span data-ttu-id="4365c-126">String</span><span class="sxs-lookup"><span data-stu-id="4365c-126">String</span></span>    |<span data-ttu-id="4365c-127">完全な自動検出 URL</span><span class="sxs-lookup"><span data-stu-id="4365c-127">Full autodiscover URL</span></span>    |<span data-ttu-id="4365c-128">外部自動検出 URL</span><span class="sxs-lookup"><span data-stu-id="4365c-128">External autodiscover URL</span></span>    |
|<span data-ttu-id="4365c-129">httpProxyDomain</span><span class="sxs-lookup"><span data-stu-id="4365c-129">httpProxyDomain</span></span>    |<span data-ttu-id="4365c-130">String</span><span class="sxs-lookup"><span data-stu-id="4365c-130">String</span></span>    ||<span data-ttu-id="4365c-131">HTTP プロキシ ドメイン</span><span class="sxs-lookup"><span data-stu-id="4365c-131">HTTP Proxy Domain</span></span>    |
|<span data-ttu-id="4365c-132">httpProxyUserName</span><span class="sxs-lookup"><span data-stu-id="4365c-132">httpProxyUserName</span></span>    |<span data-ttu-id="4365c-133">String</span><span class="sxs-lookup"><span data-stu-id="4365c-133">String</span></span>    ||<span data-ttu-id="4365c-134">HTTP プロキシ ユーザー名</span><span class="sxs-lookup"><span data-stu-id="4365c-134">HTTP Proxy Username</span></span>    |
|<span data-ttu-id="4365c-135">httpProxyPassword</span><span class="sxs-lookup"><span data-stu-id="4365c-135">httpProxyPassword</span></span>    |<span data-ttu-id="4365c-136">文字列</span><span class="sxs-lookup"><span data-stu-id="4365c-136">String</span></span>    ||<span data-ttu-id="4365c-137">HTTP プロキシ パスワード</span><span class="sxs-lookup"><span data-stu-id="4365c-137">HTTP Proxy Password</span></span>    |
|<span data-ttu-id="4365c-138">trustedDomainList</span><span class="sxs-lookup"><span data-stu-id="4365c-138">trustedDomainList</span></span>    |<span data-ttu-id="4365c-139">配列</span><span class="sxs-lookup"><span data-stu-id="4365c-139">Array</span></span>    ||<span data-ttu-id="4365c-140">HTTP リダイレクトでの信頼済みのドメインのリスト。</span><span class="sxs-lookup"><span data-stu-id="4365c-140">List of trusted domains for HTTP redirects.</span></span>    |
|<span data-ttu-id="4365c-141">autoAcceptTimeout</span><span class="sxs-lookup"><span data-stu-id="4365c-141">autoAcceptTimeout</span></span>    |<span data-ttu-id="4365c-142">数値</span><span class="sxs-lookup"><span data-stu-id="4365c-142">Number</span></span>    |<span data-ttu-id="4365c-143">300 (既定)</span><span class="sxs-lookup"><span data-stu-id="4365c-143">300 (default)</span></span>    |<span data-ttu-id="4365c-144">サーバー側の会話履歴がないユーザーの自動承認タイムアウト。</span><span class="sxs-lookup"><span data-stu-id="4365c-144">Auto-Accept timeout for users without Server-side Conversation History.</span></span>    |
|<span data-ttu-id="4365c-145">warnWhenUnknownLocationForE911</span><span class="sxs-lookup"><span data-stu-id="4365c-145">warnWhenUnknownLocationForE911</span></span>    |<span data-ttu-id="4365c-146">ブール値</span><span class="sxs-lookup"><span data-stu-id="4365c-146">Bool</span></span>    |<span data-ttu-id="4365c-147">0 = 無効</span><span class="sxs-lookup"><span data-stu-id="4365c-147">0 = Disabled</span></span>  <br/> <span data-ttu-id="4365c-148">1 = 有効</span><span class="sxs-lookup"><span data-stu-id="4365c-148">1 = Enabled</span></span>    |<span data-ttu-id="4365c-149">不明な場所から緊急電話番号にダイヤルするときにユーザーに警告します。</span><span class="sxs-lookup"><span data-stu-id="4365c-149">Warns the user when dialing an emergency number from an unknown location.</span></span>    |
|<span data-ttu-id="4365c-150">sipAddress</span><span class="sxs-lookup"><span data-stu-id="4365c-150">sipAddress</span></span>    |<span data-ttu-id="4365c-151">String</span><span class="sxs-lookup"><span data-stu-id="4365c-151">String</span></span>    ||<span data-ttu-id="4365c-152">SIP アドレス (電子メール) ビジネスのための Skype にサインインするために使用します。</span><span class="sxs-lookup"><span data-stu-id="4365c-152">The SIP address (Email) used to sign-in to Skype for Business.</span></span>    |
|<span data-ttu-id="4365c-153">userName</span><span class="sxs-lookup"><span data-stu-id="4365c-153">userName</span></span>    |<span data-ttu-id="4365c-154">文字列</span><span class="sxs-lookup"><span data-stu-id="4365c-154">String</span></span>    ||<span data-ttu-id="4365c-155">UPN (ユーザー名) ビジネスのための Skype にサインインするために使用します。</span><span class="sxs-lookup"><span data-stu-id="4365c-155">The UPN (UserName) used to sign-in to Skype for Business.</span></span>    |
|<span data-ttu-id="4365c-156">userNameInAdvancedOnly</span><span class="sxs-lookup"><span data-stu-id="4365c-156">userNameInAdvancedOnly</span></span>    |<span data-ttu-id="4365c-157">ブール</span><span class="sxs-lookup"><span data-stu-id="4365c-157">Bool</span></span>    |<span data-ttu-id="4365c-158">0 = サインイン用のメイン画面にし、[詳細プロパティ] ダイアログ ボックスで、[ユーザー名] フィールドを表示</span><span class="sxs-lookup"><span data-stu-id="4365c-158">0 = display the User Name field on the main sign-in screen and in the Advanced Properties dialog box</span></span>  <br/> <span data-ttu-id="4365c-159">1 = [詳細プロパティ] ダイアログ ボックス (既定値) でのみ、[ユーザー名] フィールドを表示</span><span class="sxs-lookup"><span data-stu-id="4365c-159">1 = display the User Name field only in the Advanced Properties dialog box (default)</span></span>    |<span data-ttu-id="4365c-160">サインイン時にユーザー名フィールドが表示される場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="4365c-160">Specify where the User Name field is displayed during sign-in.</span></span>    |
   
### <a name="usage-examples"></a><span data-ttu-id="4365c-161">使用例</span><span class="sxs-lookup"><span data-stu-id="4365c-161">Usage examples</span></span>

<span data-ttu-id="4365c-162">信頼されたドメインの一覧に 1 つのドメイン (Contoso.com) を追加するには、ように、trustedDomainList キーを使用します。</span><span class="sxs-lookup"><span data-stu-id="4365c-162">To add a single domain (Contoso.com) to the trusted domain list you would use the trustedDomainList key as shown:</span></span>
  
<span data-ttu-id="4365c-163">com.microsoft.SkypeForBusiness trustedDomainList を作成する既定値の配列の"Contoso.com"を追加</span><span class="sxs-lookup"><span data-stu-id="4365c-163">defaults write com.microsoft.SkypeForBusiness trustedDomainList -array-add "Contoso.com"</span></span>
  
<span data-ttu-id="4365c-164">複数のドメインを信頼済みのドメインのリストに追加するには、次に示すような trustedDomainList キーを使用します。</span><span class="sxs-lookup"><span data-stu-id="4365c-164">To add several domains to the trusted domain list you would use the trustedDomainList key as shown:</span></span>
  
<span data-ttu-id="4365c-165">com.microsoft.SkypeForBusiness trustedDomainList を作成する既定値の配列-"sfb.com"「abc.com」「test.org」を追加</span><span class="sxs-lookup"><span data-stu-id="4365c-165">defaults write com.microsoft.SkypeForBusiness trustedDomainList -array-add "sfb.com" "abc.com" "test.org"</span></span>
  
### <a name="sample-unedited-settings"></a><span data-ttu-id="4365c-166">未編集の設定のサンプル</span><span class="sxs-lookup"><span data-stu-id="4365c-166">Sample unedited settings</span></span>

<span data-ttu-id="4365c-167">参考用として、既定の設定のみを使用したサンプル設定ファイルをここで提供します。</span><span class="sxs-lookup"><span data-stu-id="4365c-167">For reference, here is a sample settings file using default settings only:</span></span> 
  
```
{
    BITApplicationDidEnterBackgroundTime = "1496164840.505589";
    BITApplicationWasLaunched = 1;
    CallHistorySelectedFilterIndex = 0;
    HockeySDKAutomaticallySendCrashReports = 0;
    HockeySDKCrashReportActivated = 1;
    "LastSignOut_me" = "2017-05-30 17:22:17 +0000";
    "NSSplitView Subview Frames CallHistoryListDetailSplit" =     (
        "0.000000, 0.000000, 291.500000, 473.000000, NO, NO",
        "292.500000, 0.000000, 408.500000, 473.000000, NO, NO"
    );
    "NSSplitView Subview Frames calendarListSplitView" =     (
        "0.000000, 0.000000, 320.000000, 473.000000, NO, NO",
        "321.000000, 0.000000, 380.000000, 473.000000, NO, NO"
    );
   "NSSplitView Subview Frames conversationListSplitView" =     (
        "0.000000, 0.000000, 320.000000, 473.000000, NO, NO",
        "321.000000, 0.000000, 380.000000, 473.000000, NO, NO"
    );
    "NSWindow Frame HomeWindow" = "511 134 769 473 0 0 1280 778 ";
    "NSWindow Frame SignInWindow" = "388 208 512 518 0 0 1280 778 ";
    RawCameraSupportVersion = 7030;
    appRunning = 1;
    buildTime = "May 22 2017 12:37:28";
    "user@contoso.com_userPreferences" =     {
        ContactsListState =         {
            expandedGroupState =             {
                "/me/pendingContacts" = 0;
                "/ucwa/v1/applications/414177012058/people/groups/HR6ZQDk_JUI9WUR0Gq0TEAUYfYDk8OwzsPAuDxZfjxg=" = 0;
                "/ucwa/v1/applications/414177012058/people/groups/N-kLDW4VAs4O3PDv36MNyaYxhuqkRGD1eWpzDGdaHnw=" = 0;
                "/ucwa/v1/applications/414177012058/people/groups/RJk1X9SsFDq-MbvPe2eUyKTdPizt7-eMxij-ef1SGWQ=" = 0;
                "/ucwa/v1/applications/414177012058/people/groups/UulRAGZQL3JnSpYCDqy4KsZCboNF2pqmp-ru3sqiDPQ=" = 0;
                "/ucwa/v1/applications/414177012058/people/groups/Wsbhk9lfd8OUv_0aCtHmYPfm0Wal0mzoM5WFbkxaNjM=" = 0;
                "/ucwa/v1/applications/414177012058/people/groups/afYHfnLUqTmnwac55OaqHUNqLLCqFTZuDezsBeSLOko=" = 0;
                "/ucwa/v1/applications/414177012058/people/groups/aok8RuCx35GbuVLMp-_Zi4gnBK_c5qO7mANf4Drf8Ak=" = 0;
                "/ucwa/v1/applications/414177012058/people/groups/hSrWaq6LWhzvT6sRxpyQimwfXzMgLyEc3O4FgSokesc=" = 0;
                "/ucwa/v1/applications/414177012058/people/groups/mDdgSHulTTkweoDbjXVp7Y308xM70eFDDZn2j7sAytM=" = 0;
                "/ucwa/v1/applications/414177012058/people/groups/nj3ApLemRK23ChI-K3x_RRGjlEeqTh6_9w6kYwKWldQ=" = 1;
                "/ucwa/v1/applications/414177012058/people/groups/oRX0pDJ2zEP-DQOfynLdvnTEFFNnsv95uvCmVfHjSik=" = 0;
            };
        };
    };
    defaultAudioPlaybackDevice = <62706c69 73743030 d4010203 04050618 19582476 65727369 6f6e5824 6f626a65 63747359 24617263 68697665 72542474 6f701200 0186a0a5 07080f10 1155246e 756c6cd3 090a0b0c 0d0e5b64 6973706c 61794e61 6d655624 636c6173 735a6964 656e7469 66696572 80038004 80025f10 5a417070 6c655553 42417564 696f456e 67696e65 3a432d4d 65646961 20456c65 6374726f 6e696373 20496e63 2e202020 2020203a 4d696372 6f736f66 74204c69 66654368 6174204c 582d3330 30303a31 34313030 3030303a 322c315f 101a4d69 63726f73 6f667420 4c696665 43686174 204c582d 33303030 d2121314 155a2463 6c617373 6e616d65 5824636c 61737365 735f1016 4d6f6465 6c2e4175 64696f56 6964656f 44657669 6365a216 175f1016 4d6f6465 6c2e4175 64696f56 6964656f 44657669 6365584e 534f626a 6563745f 100f4e53 4b657965 64417263 68697665 72d11a1b 54726f6f 74800100 08001100 1a002300 2d003200 37003d00 43004a00 56005d00 68006a00 6c006e00 cb00e800 ed00f801 01011a01 1d013601 3f015101 54015900 00000000 00020100 00000000 00001c00 00000000 00000000 00000000 00015b>;
    defaultAudioRecordingDevice = <62706c69 73743030 d4010203 04050618 19582476 65727369 6f6e5824 6f626a65 63747359 24617263 68697665 72542474 6f701200 0186a0a5 07080f10 1155246e 756c6cd3 090a0b0c 0d0e5b64 6973706c 61794e61 6d655624 636c6173 735a6964 656e7469 66696572 80038004 80025f10 5a417070 6c655553 42417564 696f456e 67696e65 3a432d4d 65646961 20456c65 6374726f 6e696373 20496e63 2e202020 2020203a 4d696372 6f736f66 74204c69 66654368 6174204c 582d3330 30303a31 34313030 3030303a 322c315f 101a4d69 63726f73 6f667420 4c696665 43686174 204c582d 33303030 d2121314 155a2463 6c617373 6e616d65 5824636c 61737365 735f1016 4d6f6465 6c2e4175 64696f56 6964656f 44657669 6365a216 175f1016 4d6f6465 6c2e4175 64696f56 6964656f 44657669 6365584e 534f626a 6563745f 100f4e53 4b657965 64417263 68697665 72d11a1b 54726f6f 74800100 08001100 1a002300 2d003200 37003d00 43004a00 56005d00 68006a00 6c006e00 cb00e800 ed00f801 01011a01 1d013601 3f015101 54015900 00000000 00020100 00000000 00001c00 00000000 00000000 00000000 00015b>;
    firstRun = 0;
    showEndCallDialog = 1;
}
```
