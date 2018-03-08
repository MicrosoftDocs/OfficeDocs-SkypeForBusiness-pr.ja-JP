---
title: "データ収集方法"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, allancar
ms.date: 01/22/2018
ms.topic: article
ms.assetid: c17e8ea6-b83b-4345-9401-47a6c8b13aad
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Legal
hideEdit: 
description: "Microsoft は、Skype for Business の使用方法と、ユーザーが問題が発生する詳細については、調査、使用、およびエラーのデータを収集します。データは、製品の改善の計画に使用されます。"
ms.openlocfilehash: f58a5650da1b6f489c63fdb5e5870321e0f06727
ms.sourcegitcommit: 2d84f687ccc44220d5ec9d8b429dfae65cced5a7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/01/2018
---
# <a name="skype-for-business-and-microsoft-teams-data-collection-practices"></a><span data-ttu-id="f9e9e-104">Skype for Business とチームの Microsoft のデータ収集方法</span><span class="sxs-lookup"><span data-stu-id="f9e9e-104">Skype for Business and Microsoft Teams data collection practices</span></span>

<span data-ttu-id="f9e9e-p102">Skype for Business Server 2015、Skype for Business Online Skype for Business とチームの Microsoft アプリとは、Microsoft がこれらの製品をどのように使用されているし、どのようなサインイン エラーなどのエラーが発生したを理解するためのデータを収集します。この情報は、状況を把握の新機能は、計画のトラブルシューティングを行うし、問題を解決するへのご協力役立ちます。</span><span class="sxs-lookup"><span data-stu-id="f9e9e-p102">Skype for Business Server 2015, Skype for Business Online, along with Skype for Business and Microsoft Teams apps collect data to help Microsoft understand how these products are being used and what kinds of errors, such as sign-in errors, have occurred. This information helps us understand usage patterns, plan new features, and troubleshoot and fix problem areas.</span></span>
  
<span data-ttu-id="f9e9e-p103">一部の利用状況のデータが自動的に収集された、中に他のデータを収集のみ管理者またはユーザーがでも使用できるようにします。データの収集は、次の 3 つのカテゴリに分類されます。</span><span class="sxs-lookup"><span data-stu-id="f9e9e-p103">While some usage data is collected automatically, other data can only be collected when the admin and/or user chooses to allow it. Data collection falls into these three categories:</span></span>
  
- <span data-ttu-id="f9e9e-109">データの調査</span><span class="sxs-lookup"><span data-stu-id="f9e9e-109">Census data</span></span>
    
- <span data-ttu-id="f9e9e-110">利用状況のデータ</span><span class="sxs-lookup"><span data-stu-id="f9e9e-110">Usage data</span></span>
    
- <span data-ttu-id="f9e9e-111">エラー報告データ</span><span class="sxs-lookup"><span data-stu-id="f9e9e-111">Error reporting data</span></span>
    
## <a name="census-data"></a><span data-ttu-id="f9e9e-112">データの調査</span><span class="sxs-lookup"><span data-stu-id="f9e9e-112">Census data</span></span>

<span data-ttu-id="f9e9e-p104">提供、サポート、Skype for Business を向上させるためにのみ調査のデータを取得します。Microsoft チームと Skype for Business Online します。これには、デバイス、オペレーティング システムのバージョン、地域と言語の設定などの環境の情報が含まれます。また、サインインが試行および障害のカウンターも含まれます。収集される調査データの具体的な例を紹介します。</span><span class="sxs-lookup"><span data-stu-id="f9e9e-p104">Census data is acquired solely to provide, support, and improve Skype for Business. Microsoft Teams and Skype for Business Online. It includes environmental information such as device and operating system versions, and regional and language settings. It also includes counters for sign-in attempts and failures. Here are some specific examples of the census data that's collected:</span></span>

|<span data-ttu-id="f9e9e-118">**データ型**</span><span class="sxs-lookup"><span data-stu-id="f9e9e-118">**Data type**</span></span>|<span data-ttu-id="f9e9e-119">**{例}**</span><span class="sxs-lookup"><span data-stu-id="f9e9e-119">**Example**</span></span>|<span data-ttu-id="f9e9e-120">**ノート**</span><span class="sxs-lookup"><span data-stu-id="f9e9e-120">**Notes**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="f9e9e-121">アプリケーション</span><span class="sxs-lookup"><span data-stu-id="f9e9e-121">AppName</span></span>  <br/> |<span data-ttu-id="f9e9e-122">iPhoneSkype</span><span class="sxs-lookup"><span data-stu-id="f9e9e-122">iPhoneSkype</span></span>  <br/> ||
|<span data-ttu-id="f9e9e-123">DeviceModel</span><span class="sxs-lookup"><span data-stu-id="f9e9e-123">DeviceModel</span></span>  <br/> |<span data-ttu-id="f9e9e-124">iPhone</span><span class="sxs-lookup"><span data-stu-id="f9e9e-124">iPhone</span></span>  <br/> ||
|<span data-ttu-id="f9e9e-125">OSName</span><span class="sxs-lookup"><span data-stu-id="f9e9e-125">OSName</span></span>  <br/> |<span data-ttu-id="f9e9e-126">iPhoneiOS</span><span class="sxs-lookup"><span data-stu-id="f9e9e-126">iPhoneiOS</span></span>  <br/> ||
|<span data-ttu-id="f9e9e-127">OSVersion</span><span class="sxs-lookup"><span data-stu-id="f9e9e-127">OSVersion</span></span>  <br/> |<span data-ttu-id="f9e9e-128">8.3</span><span class="sxs-lookup"><span data-stu-id="f9e9e-128">8.3</span></span>  <br/> ||
|<span data-ttu-id="f9e9e-129">例</span><span class="sxs-lookup"><span data-stu-id="f9e9e-129">UserLanguage</span></span>  <br/> |<span data-ttu-id="f9e9e-130">EN-US (英語)</span><span class="sxs-lookup"><span data-stu-id="f9e9e-130">EN-US</span></span>  <br/> ||
|<span data-ttu-id="f9e9e-131">ユーザー Id</span><span class="sxs-lookup"><span data-stu-id="f9e9e-131">UserID</span></span>  <br/> |<span data-ttu-id="f9e9e-132">E296D735-4F36-4E18-7C3B-52E1A02A0164</span><span class="sxs-lookup"><span data-stu-id="f9e9e-132">E296D735-4F36-4E18-7C3B-52E1A02A0164</span></span>  <br/> |<span data-ttu-id="f9e9e-p105">ID が 2 回ハッシュ: クライアントに 1 回、もう一度テレメトリ サービスにします。ハッシングに、により、ID は、特定のユーザーにリンクすることはできません。</span><span class="sxs-lookup"><span data-stu-id="f9e9e-p105">The ID is hashed twice: once on the client and again on the telemetry service. The hashing ensures the ID cannot be linked to a specific user.</span></span>  <br/> |
|<span data-ttu-id="f9e9e-135">DeviceID</span><span class="sxs-lookup"><span data-stu-id="f9e9e-135">DeviceID</span></span>  <br/> |<span data-ttu-id="f9e9e-136">5E872200-F546-4CCD-8F23-AF5F507AA2DD</span><span class="sxs-lookup"><span data-stu-id="f9e9e-136">5E872200-F546-4CCD-8F23-AF5F507AA2DD</span></span>  <br/> |<span data-ttu-id="f9e9e-137">デバイス ID は、ランダムに生成をデバイスにあり、テレメトリ サービスに送信する GUID です。</span><span class="sxs-lookup"><span data-stu-id="f9e9e-137">The device ID is a GUID that's randomly generated once on the device and sent to the telemetry service.</span></span>  <br/> |
   
<span data-ttu-id="f9e9e-p106">調査データではないには、組織またはユーザーを識別する情報が含まれています。詳細については、 [Skype for Business のプライバシーに関する声明](https://www.microsoft.com/privacystatement/en-us/SkypeforBusiness/Default.aspx)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f9e9e-p106">Census data DOES NOT contain any information that identifies your organization or users. See the [Skype for Business Privacy Statement](https://www.microsoft.com/privacystatement/en-us/SkypeforBusiness/Default.aspx) for more information.</span></span>
  
<span data-ttu-id="f9e9e-140">調査データでは、既定でし、管理者またはエンドユーザーをオフにできません。</span><span class="sxs-lookup"><span data-stu-id="f9e9e-140">Census data is on by default and cannot be turned off by admins or end users.</span></span>
  
## <a name="usage-data"></a><span data-ttu-id="f9e9e-141">利用状況のデータ</span><span class="sxs-lookup"><span data-stu-id="f9e9e-141">Usage data</span></span>

<span data-ttu-id="f9e9e-142">利用状況のデータには、通話を行ったの数、送信または受信した Im の番号、会議に参加した数、頻度の機能を使用するには、安定性の問題などの情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="f9e9e-142">Usage data includes information such as number of calls made, number of IMs sent or received, number of meetings joined, frequency of features used, and stability issues.</span></span>
  
<span data-ttu-id="f9e9e-143">利用状況のデータには、contoso.com など、組織を識別する情報が含まれます。利用状況データ収集の具体的な例を紹介します。</span><span class="sxs-lookup"><span data-stu-id="f9e9e-143">Usage data might contain information that identifies your organization, such as contoso.com. Here are some specific examples of the usage data that's collected:</span></span>
  
|<span data-ttu-id="f9e9e-144">**データ型**</span><span class="sxs-lookup"><span data-stu-id="f9e9e-144">**Data type**</span></span>|<span data-ttu-id="f9e9e-145">**{例}**</span><span class="sxs-lookup"><span data-stu-id="f9e9e-145">**Example**</span></span>|<span data-ttu-id="f9e9e-146">**ノート**</span><span class="sxs-lookup"><span data-stu-id="f9e9e-146">**Notes**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="f9e9e-147">IM の送信</span><span class="sxs-lookup"><span data-stu-id="f9e9e-147">IM Sent</span></span>  <br/> |<span data-ttu-id="f9e9e-148">12</span><span class="sxs-lookup"><span data-stu-id="f9e9e-148">12</span></span>  <br/> ||
|<span data-ttu-id="f9e9e-149">受信した IM</span><span class="sxs-lookup"><span data-stu-id="f9e9e-149">IM Received</span></span>  <br/> |<span data-ttu-id="f9e9e-150">5</span><span class="sxs-lookup"><span data-stu-id="f9e9e-150">5</span></span>  <br/> ||
|<span data-ttu-id="f9e9e-151">会議に参加する (試行)</span><span class="sxs-lookup"><span data-stu-id="f9e9e-151">Join a meeting (attempts)</span></span>  <br/> |<span data-ttu-id="f9e9e-152">5</span><span class="sxs-lookup"><span data-stu-id="f9e9e-152">5</span></span>  <br/> ||
|<span data-ttu-id="f9e9e-153">会議に参加する (成功)</span><span class="sxs-lookup"><span data-stu-id="f9e9e-153">Join a meeting (success)</span></span>  <br/> |<span data-ttu-id="f9e9e-154">4</span><span class="sxs-lookup"><span data-stu-id="f9e9e-154">4</span></span>  <br/> ||
|<span data-ttu-id="f9e9e-155">通話と会議の議事録</span><span class="sxs-lookup"><span data-stu-id="f9e9e-155">Call/meeting minutes</span></span>  <br/> |<span data-ttu-id="f9e9e-156">30 分</span><span class="sxs-lookup"><span data-stu-id="f9e9e-156">30 mins</span></span>  <br/> ||
|<span data-ttu-id="f9e9e-157">FederationPartner</span><span class="sxs-lookup"><span data-stu-id="f9e9e-157">FederationPartner</span></span>  <br/> |<span data-ttu-id="f9e9e-158">Microsoft.com</span><span class="sxs-lookup"><span data-stu-id="f9e9e-158">Microsoft.com</span></span>  <br/> |<span data-ttu-id="f9e9e-159">Office 365 に登録されている組織の名前は、このため、解読がクリア テキストで送信されます。</span><span class="sxs-lookup"><span data-stu-id="f9e9e-159">This is the name of the organization registered in Office 365 and is transmitted in cleartext, which means it's not obfuscated.</span></span>  <br/> |
   
<span data-ttu-id="f9e9e-160">利用状況データではないには、ユーザーを識別する情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="f9e9e-160">Usage data DOES NOT contain any information that identifies users.</span></span>
  
<span data-ttu-id="f9e9e-p107">利用状況データの収集には、既定では社内管理者を使用するとで Skype for Business Server 2015 DisableAutomaticSendTracing グループ ポリシー設定を使用してを無効にできます。この設定をオフにすると、組織内のすべてのユーザーに影響します。詳細については、 [Skype for Business Server 2015 でクライアント ブートス トラップ ポリシーを構成する](https://technet.microsoft.com/EN-US/library/gg425941.aspx)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f9e9e-p107">Usage data collection is on by default, but on-premises admins can turn it off using the DisableAutomaticSendTracing Group Policy setting on Skype for Business Server 2015. Turning this setting off affects all users in the organization. See [Configure client bootstrapping policies in Skype for Business Server 2015](https://technet.microsoft.com/EN-US/library/gg425941.aspx) for more information.</span></span>
  
<span data-ttu-id="f9e9e-164">エンドユーザーをオンまたはオフに利用状況データの収集が有効にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="f9e9e-164">End users cannot turn usage data collection on or off.</span></span>
  
<span data-ttu-id="f9e9e-165">Skype 会議のアプリと結合の起動ツールの web ページ、テレメトリを制御する方法はこのポリシーを使用してには。</span><span class="sxs-lookup"><span data-stu-id="f9e9e-165">For Skype Meetings App and the join launcher web pages, the way to control telemetry is through this policy:</span></span>
  
<span data-ttu-id="f9e9e-166">設定 CsWebServiceConfiguration-MeetingUxEnableTelemetry $True</span><span class="sxs-lookup"><span data-stu-id="f9e9e-166">Set-CsWebServiceConfiguration -MeetingUxEnableTelemetry $True</span></span>
  
<span data-ttu-id="f9e9e-p108">このポリシーは既定テレメトリ コレクションが既定でオフは false になります。この設定はプールあたりであり、そのサーバーでホストされている会議に参加する Skype 会議のアプリを使って接続するすべてのユーザーを制御します。</span><span class="sxs-lookup"><span data-stu-id="f9e9e-p108">This policy defaults to false, so telemetry collection is off by default. This setting is per-pool and controls all users who connect with Skype Meetings App to a meeting hosted on that server.</span></span>
  
## <a name="error-reporting-data"></a><span data-ttu-id="f9e9e-169">エラー報告データ</span><span class="sxs-lookup"><span data-stu-id="f9e9e-169">Error reporting data</span></span>

<span data-ttu-id="f9e9e-p109">エラー報告データは、パフォーマンスと信頼性、デバイスの設定、ネットワーク接続の品質、エラー コード、エラーのログ、および例外に関する情報を含めることができます。エラー報告が収集されたデータの具体的な例を紹介します。</span><span class="sxs-lookup"><span data-stu-id="f9e9e-p109">Error reporting data can include information about performance and reliability, device configuration, network connection quality, error codes, error logs, and exceptions. Here are some specific examples of error reporting data that's collected:</span></span>

|<span data-ttu-id="f9e9e-172">**データ型**</span><span class="sxs-lookup"><span data-stu-id="f9e9e-172">**Data type**</span></span>|<span data-ttu-id="f9e9e-173">**{例}**</span><span class="sxs-lookup"><span data-stu-id="f9e9e-173">**Example**</span></span>|<span data-ttu-id="f9e9e-174">**ノート**</span><span class="sxs-lookup"><span data-stu-id="f9e9e-174">**Notes**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="f9e9e-175">メッセージの方向</span><span class="sxs-lookup"><span data-stu-id="f9e9e-175">Message direction</span></span>  <br/> |<span data-ttu-id="f9e9e-176">[受信</span><span class="sxs-lookup"><span data-stu-id="f9e9e-176">Incoming</span></span>  <br/> ||
|<span data-ttu-id="f9e9e-177">会話の状態</span><span class="sxs-lookup"><span data-stu-id="f9e9e-177">Conversation state</span></span>  <br/> |<span data-ttu-id="f9e9e-178">アイドル状態します。</span><span class="sxs-lookup"><span data-stu-id="f9e9e-178">Idle</span></span>  <br/> ||
|<span data-ttu-id="f9e9e-179">会話のスレッド ID</span><span class="sxs-lookup"><span data-stu-id="f9e9e-179">Conversation thread ID</span></span>  <br/> |<span data-ttu-id="f9e9e-180">AdDO8hsJqilU93hQHC3OZaPR2saEA = =</span><span class="sxs-lookup"><span data-stu-id="f9e9e-180">AdDO8hsJqilU93hQHC3OZaPR2saEA==</span></span>  <br/> ||
|<span data-ttu-id="f9e9e-181">ユーザー Id</span><span class="sxs-lookup"><span data-stu-id="f9e9e-181">UserID</span></span>  <br/> |<span data-ttu-id="f9e9e-182">amosmarble</span><span class="sxs-lookup"><span data-stu-id="f9e9e-182">amosmarble</span></span> <br/> |<span data-ttu-id="f9e9e-183">ID は、テレメトリ サービスを格納する前にハッシュ、クリア テキストで送信します。</span><span class="sxs-lookup"><span data-stu-id="f9e9e-183">The ID is sent in cleartext , which the telemetry service hashes before storing it</span></span>  <br/> |
   
<span data-ttu-id="f9e9e-p110">エラー報告データは、ユーザーの IP アドレスとセッション開始プロトコル Uniform Resource Identifier (SIP URI) などの個人情報もあります。収集される機能の詳細については、 [Skype for Business のプライバシーに関する声明](https://www.microsoft.com/privacystatement/en-us/SkypeforBusiness/Default.aspx)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f9e9e-p110">Error reporting data may also contain personally identifiable information such as the user's IP address and Session Initiation Protocol Uniform Resource Identifier (SIP URI). See the [Skype for Business Privacy Statement](https://www.microsoft.com/privacystatement/en-us/SkypeforBusiness/Default.aspx) for a detailed explanation of what's collected.</span></span>
  
<span data-ttu-id="f9e9e-186">エラーの報告には、次の 2 つが必要です。</span><span class="sxs-lookup"><span data-stu-id="f9e9e-186">Error reporting requires two things:</span></span>
  
- <span data-ttu-id="f9e9e-p111">サーバー上で、または (これが既定の状態) テナント管理センターで、DisableAutomaticSendTracing グループ ポリシー設定は False に設定します。詳細については、 [Skype for Business Server 2015 でクライアント ブートス トラップ ポリシーを構成する](https://technet.microsoft.com/EN-US/library/gg425941.aspx)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f9e9e-p111">The DisableAutomaticSendTracing Group Policy setting be set to False on the server or in the tenant admin center (this is the default state). See [Configure client bootstrapping policies in Skype for Business Server 2015](https://technet.microsoft.com/EN-US/library/gg425941.aspx) for more information.</span></span>
    
- <span data-ttu-id="f9e9e-189">エンドユーザー個別に選択で、[全般] タブ (クリックして歯車アイコン、[オプション] ダイアログが表示される [全般] タブで開きます) から Skype for Business クライアントします。</span><span class="sxs-lookup"><span data-stu-id="f9e9e-189">End users individually opt in from the General tab (click the gear icon and the Option dialog opens with the General tab displayed) in the Skype for Business client.</span></span>
    
     ![歯車アイコン](../images/70f1b43f-16d6-4172-9139-71d845c4ed5c.png)
  
![ビジネス データ コレクションのチェック ボックス、オプションでの Skype > [全般] ダイアログ](../images/68bc8f77-deaa-478c-9977-a5259b88df3e.png)
  
<span data-ttu-id="f9e9e-p112">Skype 会議のアプリでは、MeetingUxEnableTelemetry も制御エラー報告、Watson 設定は Windows でクラッシュが発生した、アップロードがクラッシュする情報を制御します。デスクトップ クライアント] ダイアログ ボックスで表示するように、Skype 会議のアプリのユーザー設定はありません。</span><span class="sxs-lookup"><span data-stu-id="f9e9e-p112">For Skype Meetings App, the MeetingUxEnableTelemetry also controls error reporting, although for crashes on Windows, the Watson settings control uploading crash info. There is no user setting for Skype Meetings App like you see in the desktop client dialog box.</span></span>
  
<span data-ttu-id="f9e9e-194">詳細については、 [Skype for Business の [全般設定] のオプション](http://support.office.com/article/e1a46d3e-dcea-437a-ba7b-6d442a40f439)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f9e9e-194">See [Set General options in Skype for Business](http://support.office.com/article/e1a46d3e-dcea-437a-ba7b-6d442a40f439) for more information.</span></span>
  
<span data-ttu-id="f9e9e-195">ネットワークのセットアップに[Skype for Business Online のネットワークのセットアップ](http://support.office.com/article/81fa5e16-418d-4698-a5f0-e666211c5c66)を表示できます。</span><span class="sxs-lookup"><span data-stu-id="f9e9e-195">You can see [Set up your network for Skype for Business Online](http://support.office.com/article/81fa5e16-418d-4698-a5f0-e666211c5c66) to set up your network.</span></span>
  
<span data-ttu-id="f9e9e-196">中国の 21 vianet が運営する Office 365 を使用している場合は、 [Skype for Business Online の 21 vianet が運営するためにネットワークをセットアップする](http://support.office.com/article/d21f89b0-3afc-432e-b735-036b2432fdbf)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f9e9e-196">If you are using Office 365 operated by 21Vianet in China, see [Set up your network for Skype for Business Online operated by 21Vianet](http://support.office.com/article/d21f89b0-3afc-432e-b735-036b2432fdbf).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="f9e9e-197">関連トピック</span><span class="sxs-lookup"><span data-stu-id="f9e9e-197">Related topics</span></span>
[<span data-ttu-id="f9e9e-198">カスタマー エクスペリエンス向上プログラム</span><span class="sxs-lookup"><span data-stu-id="f9e9e-198">Customer Experience Improvement Program</span></span>](https://www.microsoft.com/products/ceip/en-US/default.mspx)

[<span data-ttu-id="f9e9e-199">電話会議とプランの呼び出しの国と地域の空き時間情報</span><span class="sxs-lookup"><span data-stu-id="f9e9e-199">Country and region availability for Audio Conferencing and Calling Plans</span></span>](../country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)
