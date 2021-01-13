---
title: Skype for Business での Mac クライアント エクスペリエンスのカスタマイズ
ms.author: v-cichur
author: cichur
manager: serdars
ms.reviewer: PhillipGarding
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: d1d9cfec-e923-4d02-a306-ee40a9114cb8
description: この記事では、Skype for Business on Mac クライアントで使用できるクライアントの基本設定と既定値、およびアプリの外部からそれらを編集する方法について説明します。
ms.openlocfilehash: cdbd1c109fffddf6d922657285f60d9b4f06924a
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49805757"
---
# <a name="customize-the-mac-client-experience-in-skype-for-business"></a><span data-ttu-id="5ad7a-103">Skype for Business での Mac クライアント エクスペリエンスのカスタマイズ</span><span class="sxs-lookup"><span data-stu-id="5ad7a-103">Customize the Mac client experience in Skype for Business</span></span>
 
<span data-ttu-id="5ad7a-104">この記事では、Skype for Business on Mac クライアントで使用できるクライアントの基本設定と既定値、およびアプリの外部からそれらを編集する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="5ad7a-104">This article describes the client preferences and defaults available for the Skype for Business on Mac client, and how to edit them from outside the App.</span></span>
  
## <a name="skype-for-business-on-mac-client-preference-settings"></a><span data-ttu-id="5ad7a-105">Mac での Skype for Business クライアントの基本設定</span><span class="sxs-lookup"><span data-stu-id="5ad7a-105">Skype for Business on Mac client preference settings</span></span>

<span data-ttu-id="5ad7a-106">Mac クライアント上の Skype for Business で使用できる特定の機能と動作は、クライアントのユーザー設定によって決まります。</span><span class="sxs-lookup"><span data-stu-id="5ad7a-106">Certain features and behaviors that are available to Skype for Business on Mac clients are determined by preference settings on the client.</span></span> <span data-ttu-id="5ad7a-107">Mac での Skype for Business の基本設定は、次のパスにある Skype for Business クライアントをインストールした Mac 上のファイルに含まれます。</span><span class="sxs-lookup"><span data-stu-id="5ad7a-107">The Skype for Business on Mac preferences are found in a file located on Macs that have installed the Skype for Business client located at the following path:</span></span> 
  
 <span data-ttu-id="5ad7a-108">**~/Library/Containers/com.microsoft.SkypeForBusiness/Data/Library/Preferences/com.microsoft.SkypeForBusiness.plist**</span><span class="sxs-lookup"><span data-stu-id="5ad7a-108">**~/Library/Containers/com.microsoft.SkypeForBusiness/Data/Library/Preferences/com.microsoft.SkypeForBusiness.plist**</span></span>
  
<span data-ttu-id="5ad7a-109">これらの基本設定を設定するには、クライアントの Mac でターミナル プロンプトにアクセスし、必要に応じて、次の表に示す基本設定キーを使用して com.microsoft.SkypeForBusiness キー コマンドを書き込みます。</span><span class="sxs-lookup"><span data-stu-id="5ad7a-109">To set these preferences, get to a terminal prompt on the client's Mac and as needed enter defaults write com.microsoft.SkypeForBusiness key commands using the preference keys described in the following table.</span></span>
  
<span data-ttu-id="5ad7a-110">**クライアントの基本設定キー**</span><span class="sxs-lookup"><span data-stu-id="5ad7a-110">**Client preference keys**</span></span>


| <span data-ttu-id="5ad7a-111">キー</span><span class="sxs-lookup"><span data-stu-id="5ad7a-111">Key</span></span> | <span data-ttu-id="5ad7a-112">型</span><span class="sxs-lookup"><span data-stu-id="5ad7a-112">Type</span></span> | <span data-ttu-id="5ad7a-113">値</span><span class="sxs-lookup"><span data-stu-id="5ad7a-113">Value</span></span> | <span data-ttu-id="5ad7a-114">説明</span><span class="sxs-lookup"><span data-stu-id="5ad7a-114">Description</span></span> |
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="5ad7a-115">autoDetectAutoDicoveryURLs</span><span class="sxs-lookup"><span data-stu-id="5ad7a-115">autoDetectAutoDicoveryURLs</span></span>    |<span data-ttu-id="5ad7a-116">ブール</span><span class="sxs-lookup"><span data-stu-id="5ad7a-116">Bool</span></span>    |<span data-ttu-id="5ad7a-117">0 = 手動サーバー構成</span><span class="sxs-lookup"><span data-stu-id="5ad7a-117">0 = manual server configuration</span></span>  <br/> <span data-ttu-id="5ad7a-118">1 = サーバーの自動検出 (既定)</span><span class="sxs-lookup"><span data-stu-id="5ad7a-118">1 = automatic server detection (default)</span></span>    |<span data-ttu-id="5ad7a-119">サインイン時に使用するトランスポートとサーバーを Skype for Business で識別する方法を指定します。</span><span class="sxs-lookup"><span data-stu-id="5ad7a-119">Specify how Skype for Business identifies the transport and server to use during sign-in.</span></span> <span data-ttu-id="5ad7a-120">このポリシー設定を有効にする場合は **、internalAutoDiscoveryURL** と **externalAutoDiscoveryURL を指定する必要があります**。</span><span class="sxs-lookup"><span data-stu-id="5ad7a-120">If you enable this policy setting, you must specify **internalAutoDiscoveryURL** and **externalAutoDiscoveryURL**.</span></span>   |
|<span data-ttu-id="5ad7a-121">internalAutoDiscoveryURL</span><span class="sxs-lookup"><span data-stu-id="5ad7a-121">internalAutoDiscoveryURL</span></span>    |<span data-ttu-id="5ad7a-122">String</span><span class="sxs-lookup"><span data-stu-id="5ad7a-122">String</span></span>    |<span data-ttu-id="5ad7a-123">完全な自動検出 URL</span><span class="sxs-lookup"><span data-stu-id="5ad7a-123">Full autodiscover URL</span></span>    |<span data-ttu-id="5ad7a-124">内部自動検出 URL</span><span class="sxs-lookup"><span data-stu-id="5ad7a-124">Internal autodiscover URL</span></span>    |
|<span data-ttu-id="5ad7a-125">externalAutoDiscoveryURL</span><span class="sxs-lookup"><span data-stu-id="5ad7a-125">externalAutoDiscoveryURL</span></span>    |<span data-ttu-id="5ad7a-126">String</span><span class="sxs-lookup"><span data-stu-id="5ad7a-126">String</span></span>    |<span data-ttu-id="5ad7a-127">完全な自動検出 URL</span><span class="sxs-lookup"><span data-stu-id="5ad7a-127">Full autodiscover URL</span></span>    |<span data-ttu-id="5ad7a-128">外部自動検出 URL</span><span class="sxs-lookup"><span data-stu-id="5ad7a-128">External autodiscover URL</span></span>    |
|<span data-ttu-id="5ad7a-129">httpProxyDomain</span><span class="sxs-lookup"><span data-stu-id="5ad7a-129">httpProxyDomain</span></span>    |<span data-ttu-id="5ad7a-130">String</span><span class="sxs-lookup"><span data-stu-id="5ad7a-130">String</span></span>    ||<span data-ttu-id="5ad7a-131">HTTP プロキシ ドメイン</span><span class="sxs-lookup"><span data-stu-id="5ad7a-131">HTTP Proxy Domain</span></span>    |
|<span data-ttu-id="5ad7a-132">httpProxyUserName</span><span class="sxs-lookup"><span data-stu-id="5ad7a-132">httpProxyUserName</span></span>    |<span data-ttu-id="5ad7a-133">String</span><span class="sxs-lookup"><span data-stu-id="5ad7a-133">String</span></span>    ||<span data-ttu-id="5ad7a-134">HTTP プロキシ ユーザー名</span><span class="sxs-lookup"><span data-stu-id="5ad7a-134">HTTP Proxy Username</span></span>    |
|<span data-ttu-id="5ad7a-135">httpProxyPassword</span><span class="sxs-lookup"><span data-stu-id="5ad7a-135">httpProxyPassword</span></span>    |<span data-ttu-id="5ad7a-136">String</span><span class="sxs-lookup"><span data-stu-id="5ad7a-136">String</span></span>    ||<span data-ttu-id="5ad7a-137">HTTP プロキシ パスワード</span><span class="sxs-lookup"><span data-stu-id="5ad7a-137">HTTP Proxy Password</span></span>    |
|<span data-ttu-id="5ad7a-138">trustedDomainList</span><span class="sxs-lookup"><span data-stu-id="5ad7a-138">trustedDomainList</span></span>    |<span data-ttu-id="5ad7a-139">配列</span><span class="sxs-lookup"><span data-stu-id="5ad7a-139">Array</span></span>    ||<span data-ttu-id="5ad7a-140">HTTP リダイレクトの信頼されたドメインの一覧。</span><span class="sxs-lookup"><span data-stu-id="5ad7a-140">List of trusted domains for HTTP redirects.</span></span>    |
|<span data-ttu-id="5ad7a-141">autoAcceptTimeout</span><span class="sxs-lookup"><span data-stu-id="5ad7a-141">autoAcceptTimeout</span></span>    |<span data-ttu-id="5ad7a-142">数字</span><span class="sxs-lookup"><span data-stu-id="5ad7a-142">Number</span></span>    |<span data-ttu-id="5ad7a-143">300 (既定値)</span><span class="sxs-lookup"><span data-stu-id="5ad7a-143">300 (default)</span></span>    |<span data-ttu-id="5ad7a-144">サーバー側の会話履歴がないユーザーの自動承諾タイムアウト。</span><span class="sxs-lookup"><span data-stu-id="5ad7a-144">Auto-Accept timeout for users without Server-side Conversation History.</span></span>    |
|<span data-ttu-id="5ad7a-145">warnWhenUnknownLocationForE911</span><span class="sxs-lookup"><span data-stu-id="5ad7a-145">warnWhenUnknownLocationForE911</span></span>    |<span data-ttu-id="5ad7a-146">ブール</span><span class="sxs-lookup"><span data-stu-id="5ad7a-146">Bool</span></span>    |<span data-ttu-id="5ad7a-147">0 = 無効</span><span class="sxs-lookup"><span data-stu-id="5ad7a-147">0 = Disabled</span></span>  <br/> <span data-ttu-id="5ad7a-148">1 = 有効</span><span class="sxs-lookup"><span data-stu-id="5ad7a-148">1 = Enabled</span></span>    |<span data-ttu-id="5ad7a-149">不明な場所から緊急電話番号をダイヤルするときにユーザーに警告します。</span><span class="sxs-lookup"><span data-stu-id="5ad7a-149">Warns the user when dialing an emergency number from an unknown location.</span></span>    |
|<span data-ttu-id="5ad7a-150">sipAddress</span><span class="sxs-lookup"><span data-stu-id="5ad7a-150">sipAddress</span></span>    |<span data-ttu-id="5ad7a-151">String</span><span class="sxs-lookup"><span data-stu-id="5ad7a-151">String</span></span>    ||<span data-ttu-id="5ad7a-152">Skype for Business へのサインインに使用される SIP アドレス (電子メール)。</span><span class="sxs-lookup"><span data-stu-id="5ad7a-152">The SIP address (Email) used to sign-in to Skype for Business.</span></span>    |
|<span data-ttu-id="5ad7a-153">userName</span><span class="sxs-lookup"><span data-stu-id="5ad7a-153">userName</span></span>    |<span data-ttu-id="5ad7a-154">String</span><span class="sxs-lookup"><span data-stu-id="5ad7a-154">String</span></span>    ||<span data-ttu-id="5ad7a-155">Skype for Business にサインインするために使用される UPN (UserName)。</span><span class="sxs-lookup"><span data-stu-id="5ad7a-155">The UPN (UserName) used to sign-in to Skype for Business.</span></span>    |
|<span data-ttu-id="5ad7a-156">userNameInAdvancedOnly</span><span class="sxs-lookup"><span data-stu-id="5ad7a-156">userNameInAdvancedOnly</span></span>    |<span data-ttu-id="5ad7a-157">ブール</span><span class="sxs-lookup"><span data-stu-id="5ad7a-157">Bool</span></span>    |<span data-ttu-id="5ad7a-158">0 = メインのサインイン画面と [プロパティの詳細設定] ダイアログ ボックスに [ユーザー名] フィールドを表示する</span><span class="sxs-lookup"><span data-stu-id="5ad7a-158">0 = display the User Name field on the main sign-in screen and in the Advanced Properties dialog box</span></span>  <br/> <span data-ttu-id="5ad7a-159">1 = [詳細プロパティ] ダイアログ ボックスにのみ [ユーザー名] フィールドを表示する (既定)</span><span class="sxs-lookup"><span data-stu-id="5ad7a-159">1 = display the User Name field only in the Advanced Properties dialog box (default)</span></span>    |<span data-ttu-id="5ad7a-160">サインイン時にユーザー名フィールドを表示する場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="5ad7a-160">Specify where the User Name field is displayed during sign-in.</span></span>    |
   
### <a name="usage-examples"></a><span data-ttu-id="5ad7a-161">使用例</span><span class="sxs-lookup"><span data-stu-id="5ad7a-161">Usage examples</span></span>

<span data-ttu-id="5ad7a-162">単一のドメイン (Contoso.com) を信頼されたドメインの一覧に追加するには、次のように trustedDomainList キーを使用します。</span><span class="sxs-lookup"><span data-stu-id="5ad7a-162">To add a single domain (Contoso.com) to the trusted domain list you would use the trustedDomainList key as shown:</span></span>
  
<span data-ttu-id="5ad7a-163">defaults write com.microsoft.SkypeForBusiness trustedDomainList -array-add "Contoso.com"</span><span class="sxs-lookup"><span data-stu-id="5ad7a-163">defaults write com.microsoft.SkypeForBusiness trustedDomainList -array-add "Contoso.com"</span></span>
  
<span data-ttu-id="5ad7a-164">複数のドメインを信頼されたドメインの一覧に追加するには、次に示すように trustedDomainList キーを使用します。</span><span class="sxs-lookup"><span data-stu-id="5ad7a-164">To add several domains to the trusted domain list you would use the trustedDomainList key as shown:</span></span>
  
<span data-ttu-id="5ad7a-165">defaults write com.microsoft.SkypeForBusiness trustedDomainList -array-add "sfb.com" "abc.com" "test.org"</span><span class="sxs-lookup"><span data-stu-id="5ad7a-165">defaults write com.microsoft.SkypeForBusiness trustedDomainList -array-add "sfb.com" "abc.com" "test.org"</span></span>
  
### <a name="sample-unedited-settings"></a><span data-ttu-id="5ad7a-166">編集されていない設定のサンプル</span><span class="sxs-lookup"><span data-stu-id="5ad7a-166">Sample unedited settings</span></span>

<span data-ttu-id="5ad7a-167">参考までに、既定の設定のみを使用するサンプル設定ファイルを次に示します。</span><span class="sxs-lookup"><span data-stu-id="5ad7a-167">For reference, here is a sample settings file using default settings only:</span></span> 
  
```console
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
