---
title: データ収集作業について
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
hideEdit: true
description: Microsoft collects census, usage, and error data to understand how Skype for Business is being used and where users encounter problems. The data is used to plan product improvements.
ms.openlocfilehash: f58a5650da1b6f489c63fdb5e5870321e0f06727
ms.sourcegitcommit: 627d3108e3e2f232e911162d9d2db9558e8ead0c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/03/2018
---
# <a name="skype-for-business-and-microsoft-teams-data-collection-practices"></a><span data-ttu-id="c6b24-104">Skype for Business と Microsoft Teams のデータ収集方法</span><span class="sxs-lookup"><span data-stu-id="c6b24-104">Skype for Business and Microsoft Teams data collection practices</span></span>

<span data-ttu-id="c6b24-105">ビジネス サーバー 2015 の Skype、Skype のビジネス、オンライン ビジネス、マイクロソフトのチームのアプリケーションの Skype とは、Microsoft がこれらの製品の使用方法と、サインインのエラーなど、エラーの種類が発生したを理解するためのデータを収集します。</span><span class="sxs-lookup"><span data-stu-id="c6b24-105">Skype for Business Server 2015, Skype for Business Online, along with Skype for Business and Microsoft Teams apps collect data to help Microsoft understand how these products are being used and what kinds of errors, such as sign-in errors, have occurred.</span></span> <span data-ttu-id="c6b24-106">Microsoft は、使用パターンの理解、将来の機能の計画、問題の領域のトラブルシューティングと修正のためにこれらの情報を活用できます。</span><span class="sxs-lookup"><span data-stu-id="c6b24-106">This information helps us understand usage patterns, plan new features, and troubleshoot and fix problem areas.</span></span>
  
<span data-ttu-id="c6b24-p103">一部の使用データは自動的に収集されますが、管理者またはユーザーによって許可された場合にのみ収集できるデータもあります。収集されるデータは、次の 3 つのカテゴリに分類されます。</span><span class="sxs-lookup"><span data-stu-id="c6b24-p103">While some usage data is collected automatically, other data can only be collected when the admin and/or user chooses to allow it. Data collection falls into these three categories:</span></span>
  
- <span data-ttu-id="c6b24-109">全数調査データ</span><span class="sxs-lookup"><span data-stu-id="c6b24-109">Census data</span></span>
    
- <span data-ttu-id="c6b24-110">使用状況データ</span><span class="sxs-lookup"><span data-stu-id="c6b24-110">Usage data</span></span>
    
- <span data-ttu-id="c6b24-111">エラー報告データ</span><span class="sxs-lookup"><span data-stu-id="c6b24-111">Error reporting data</span></span>
    
## <a name="census-data"></a><span data-ttu-id="c6b24-112">全数調査データ</span><span class="sxs-lookup"><span data-stu-id="c6b24-112">Census data</span></span>

<span data-ttu-id="c6b24-113">調査データは、提供、サポート、およびビジネス用の Skype を改善する目的でのみ取得されます。</span><span class="sxs-lookup"><span data-stu-id="c6b24-113">Census data is acquired solely to provide, support, and improve Skype for Business.</span></span> <span data-ttu-id="c6b24-114">マイクロソフトのチームと Skype ビジネスをオンラインにします。</span><span class="sxs-lookup"><span data-stu-id="c6b24-114">Microsoft Teams and Skype for Business Online.</span></span> <span data-ttu-id="c6b24-115">これには、デバイスとオペレーティング システムのバージョン、地域と言語の設定などの環境情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="c6b24-115">It includes environmental information such as device and operating system versions, and regional and language settings.</span></span> <span data-ttu-id="c6b24-116">サインイン試行と失敗のカウンターも含まれます。</span><span class="sxs-lookup"><span data-stu-id="c6b24-116">It also includes counters for sign-in attempts and failures.</span></span> <span data-ttu-id="c6b24-117">次に、収集される全数調査データの具体例をいくつか示します。</span><span class="sxs-lookup"><span data-stu-id="c6b24-117">Here are some specific examples of the census data that's collected:</span></span>

|<span data-ttu-id="c6b24-118">**データ型**</span><span class="sxs-lookup"><span data-stu-id="c6b24-118">**Data type**</span></span>|<span data-ttu-id="c6b24-119">**例**</span><span class="sxs-lookup"><span data-stu-id="c6b24-119">**Example**</span></span>|<span data-ttu-id="c6b24-120">**メモ**</span><span class="sxs-lookup"><span data-stu-id="c6b24-120">**Notes**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="c6b24-121">AppName</span><span class="sxs-lookup"><span data-stu-id="c6b24-121">AppName</span></span>  <br/> |<span data-ttu-id="c6b24-122">iPhoneSkype</span><span class="sxs-lookup"><span data-stu-id="c6b24-122">iPhoneSkype</span></span>  <br/> ||
|<span data-ttu-id="c6b24-123">DeviceModel</span><span class="sxs-lookup"><span data-stu-id="c6b24-123">DeviceModel</span></span>  <br/> |<span data-ttu-id="c6b24-124">iPhone</span><span class="sxs-lookup"><span data-stu-id="c6b24-124">iPhone</span></span>  <br/> ||
|<span data-ttu-id="c6b24-125">OSName</span><span class="sxs-lookup"><span data-stu-id="c6b24-125">OSName</span></span>  <br/> |<span data-ttu-id="c6b24-126">iPhoneiOS</span><span class="sxs-lookup"><span data-stu-id="c6b24-126">iPhoneiOS</span></span>  <br/> ||
|<span data-ttu-id="c6b24-127">OSVersion</span><span class="sxs-lookup"><span data-stu-id="c6b24-127">OSVersion</span></span>  <br/> |<span data-ttu-id="c6b24-128">8.3</span><span class="sxs-lookup"><span data-stu-id="c6b24-128">8.3</span></span>  <br/> ||
|<span data-ttu-id="c6b24-129">例</span><span class="sxs-lookup"><span data-stu-id="c6b24-129">UserLanguage</span></span>  <br/> |<span data-ttu-id="c6b24-130">EN-US</span><span class="sxs-lookup"><span data-stu-id="c6b24-130">EN-US</span></span>  <br/> ||
|<span data-ttu-id="c6b24-131">ユーザー Id</span><span class="sxs-lookup"><span data-stu-id="c6b24-131">UserID</span></span>  <br/> |<span data-ttu-id="c6b24-132">E296D735-4F36-4E18-7C3B-52E1A02A0164</span><span class="sxs-lookup"><span data-stu-id="c6b24-132">E296D735-4F36-4E18-7C3B-52E1A02A0164</span></span>  <br/> |<span data-ttu-id="c6b24-p105">ID は、2 回ハッシュされます (クライアントで 1 回、利用統計情報サービスでもう一回)。ハッシュによって、ID を特定のユーザーに結び付けることができなくなります。</span><span class="sxs-lookup"><span data-stu-id="c6b24-p105">The ID is hashed twice: once on the client and again on the telemetry service. The hashing ensures the ID cannot be linked to a specific user.</span></span>  <br/> |
|<span data-ttu-id="c6b24-135">DeviceID</span><span class="sxs-lookup"><span data-stu-id="c6b24-135">DeviceID</span></span>  <br/> |<span data-ttu-id="c6b24-136">5E872200-F546-4CCD-8F23-AF5F507AA2DD</span><span class="sxs-lookup"><span data-stu-id="c6b24-136">5E872200-F546-4CCD-8F23-AF5F507AA2DD</span></span>  <br/> |<span data-ttu-id="c6b24-137">デバイス ID は、デバイス上でランダムに生成される GUID であり、利用統計情報サービスに送信されます。</span><span class="sxs-lookup"><span data-stu-id="c6b24-137">The device ID is a GUID that's randomly generated once on the device and sent to the telemetry service.</span></span>  <br/> |
   
<span data-ttu-id="c6b24-p106">全数調査データには、組織またはユーザーを特定できる情報は含まれていません。詳細については、「[Skype for Business のプライバシーに関する声明](https://www.microsoft.com/privacystatement/en-us/SkypeforBusiness/Default.aspx)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="c6b24-p106">Census data DOES NOT contain any information that identifies your organization or users. See the [Skype for Business Privacy Statement](https://www.microsoft.com/privacystatement/en-us/SkypeforBusiness/Default.aspx) for more information.</span></span>
  
<span data-ttu-id="c6b24-140">全数調査データは、既定でオンになり、管理者やエンド ユーザーがオフにすることはできません。</span><span class="sxs-lookup"><span data-stu-id="c6b24-140">Census data is on by default and cannot be turned off by admins or end users.</span></span>
  
## <a name="usage-data"></a><span data-ttu-id="c6b24-141">使用状況データ</span><span class="sxs-lookup"><span data-stu-id="c6b24-141">Usage data</span></span>

<span data-ttu-id="c6b24-142">使用状況データには、発信した通話の回数、送受信した IM の数、参加した会議の数、機能を使用した頻度、安定性の問題などの情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="c6b24-142">Usage data includes information such as number of calls made, number of IMs sent or received, number of meetings joined, frequency of features used, and stability issues.</span></span>
  
<span data-ttu-id="c6b24-143">使用状況データには、contoso.com などの組織を特定できる情報が含まれる場合もあります。次に、収集される使用状況データの具体例をいくつか示します。</span><span class="sxs-lookup"><span data-stu-id="c6b24-143">Usage data might contain information that identifies your organization, such as contoso.com. Here are some specific examples of the usage data that's collected:</span></span>
  
|<span data-ttu-id="c6b24-144">**データ型**</span><span class="sxs-lookup"><span data-stu-id="c6b24-144">**Data type**</span></span>|<span data-ttu-id="c6b24-145">**例**</span><span class="sxs-lookup"><span data-stu-id="c6b24-145">**Example**</span></span>|<span data-ttu-id="c6b24-146">**メモ**</span><span class="sxs-lookup"><span data-stu-id="c6b24-146">**Notes**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="c6b24-147">IM Sent (送信済み IM)</span><span class="sxs-lookup"><span data-stu-id="c6b24-147">IM Sent</span></span>  <br/> |<span data-ttu-id="c6b24-148">12</span><span class="sxs-lookup"><span data-stu-id="c6b24-148">12</span></span>  <br/> ||
|<span data-ttu-id="c6b24-149">IM Received (受信済み IM)</span><span class="sxs-lookup"><span data-stu-id="c6b24-149">IM Received</span></span>  <br/> |<span data-ttu-id="c6b24-150">5</span><span class="sxs-lookup"><span data-stu-id="c6b24-150">5</span></span>  <br/> ||
|<span data-ttu-id="c6b24-151">Join a meeting (attempts) (会議への参加 (試行))</span><span class="sxs-lookup"><span data-stu-id="c6b24-151">Join a meeting (attempts)</span></span>  <br/> |<span data-ttu-id="c6b24-152">5</span><span class="sxs-lookup"><span data-stu-id="c6b24-152">5</span></span>  <br/> ||
|<span data-ttu-id="c6b24-153">Join a meeting (success) (会議への参加 (成功))</span><span class="sxs-lookup"><span data-stu-id="c6b24-153">Join a meeting (success)</span></span>  <br/> |<span data-ttu-id="c6b24-154">4</span><span class="sxs-lookup"><span data-stu-id="c6b24-154">4</span></span>  <br/> ||
|<span data-ttu-id="c6b24-155">Call/meeting minutes (通話/会議の時間)</span><span class="sxs-lookup"><span data-stu-id="c6b24-155">Call/meeting minutes</span></span>  <br/> |<span data-ttu-id="c6b24-156">30 mins (30 分)</span><span class="sxs-lookup"><span data-stu-id="c6b24-156">30 mins</span></span>  <br/> ||
|<span data-ttu-id="c6b24-157">FederationPartner</span><span class="sxs-lookup"><span data-stu-id="c6b24-157">FederationPartner</span></span>  <br/> |<span data-ttu-id="c6b24-158">Microsoft.com</span><span class="sxs-lookup"><span data-stu-id="c6b24-158">Microsoft.com</span></span>  <br/> |<span data-ttu-id="c6b24-159">これは、Office 365 に登録されている組織の名前で、テキスト形式で送信されるため暗号化されません。</span><span class="sxs-lookup"><span data-stu-id="c6b24-159">This is the name of the organization registered in Office 365 and is transmitted in cleartext, which means it's not obfuscated.</span></span>  <br/> |
   
<span data-ttu-id="c6b24-160">使用状況データには、ユーザーを特定できる情報は含まれていません。</span><span class="sxs-lookup"><span data-stu-id="c6b24-160">Usage data DOES NOT contain any information that identifies users.</span></span>
  
<span data-ttu-id="c6b24-p107">使用状況データの収集は、既定でオンになりますが、オンプレミスの管理者が、Skype for Business Server 2015 の DisableAutomaticSendTracing グループ ポリシー設定を使用してオフにすることができます。この設定をオフにすると、組織のすべてのユーザーが影響を受けます。「[Skype for Business Server 2015 でのクライアント ブートストラップ ポリシーの構成](https://technet.microsoft.com/EN-US/library/gg425941.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c6b24-p107">Usage data collection is on by default, but on-premises admins can turn it off using the DisableAutomaticSendTracing Group Policy setting on Skype for Business Server 2015. Turning this setting off affects all users in the organization. See [Configure client bootstrapping policies in Skype for Business Server 2015](https://technet.microsoft.com/EN-US/library/gg425941.aspx) for more information.</span></span>
  
<span data-ttu-id="c6b24-164">エンド ユーザーは使用状況データの収集のオンとオフを切り替えることはできません。</span><span class="sxs-lookup"><span data-stu-id="c6b24-164">End users cannot turn usage data collection on or off.</span></span>
  
<span data-ttu-id="c6b24-165">Skype 会議アプリと Join Launcher Web ページでは、利用統計情報は次のポリシーによって制御されます。</span><span class="sxs-lookup"><span data-stu-id="c6b24-165">For Skype Meetings App and the join launcher web pages, the way to control telemetry is through this policy:</span></span>
  
<span data-ttu-id="c6b24-166">Set-CsWebServiceConfiguration -MeetingUxEnableTelemetry $True</span><span class="sxs-lookup"><span data-stu-id="c6b24-166">Set-CsWebServiceConfiguration -MeetingUxEnableTelemetry $True</span></span>
  
<span data-ttu-id="c6b24-p108">このポリシーの既定値は False であるため、利用統計情報は既定では収集されません。この設定はプールごとに行われ、Skype 会議アプリを使用してそのサーバーでホストされる会議に接続するすべてのユーザーを制御します。</span><span class="sxs-lookup"><span data-stu-id="c6b24-p108">This policy defaults to false, so telemetry collection is off by default. This setting is per-pool and controls all users who connect with Skype Meetings App to a meeting hosted on that server.</span></span>
  
## <a name="error-reporting-data"></a><span data-ttu-id="c6b24-169">エラー報告データ</span><span class="sxs-lookup"><span data-stu-id="c6b24-169">Error reporting data</span></span>

<span data-ttu-id="c6b24-p109">エラー報告データには、パフォーマンスと信頼性、デバイスの構成、ネットワーク接続の品質、エラー コード、エラー ログ、例外などの情報が含まれることがあります。次に、収集されるエラー報告データの具体例をいくつか示します。</span><span class="sxs-lookup"><span data-stu-id="c6b24-p109">Error reporting data can include information about performance and reliability, device configuration, network connection quality, error codes, error logs, and exceptions. Here are some specific examples of error reporting data that's collected:</span></span>

|<span data-ttu-id="c6b24-172">**データ型**</span><span class="sxs-lookup"><span data-stu-id="c6b24-172">**Data type**</span></span>|<span data-ttu-id="c6b24-173">**例**</span><span class="sxs-lookup"><span data-stu-id="c6b24-173">**Example**</span></span>|<span data-ttu-id="c6b24-174">**メモ**</span><span class="sxs-lookup"><span data-stu-id="c6b24-174">**Notes**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="c6b24-175">Message direction (メッセージの方向)</span><span class="sxs-lookup"><span data-stu-id="c6b24-175">Message direction</span></span>  <br/> |<span data-ttu-id="c6b24-176">Incoming (受信)</span><span class="sxs-lookup"><span data-stu-id="c6b24-176">Incoming</span></span>  <br/> ||
|<span data-ttu-id="c6b24-177">Conversation state (会話の状態)</span><span class="sxs-lookup"><span data-stu-id="c6b24-177">Conversation state</span></span>  <br/> |<span data-ttu-id="c6b24-178">Idle (アイドル)</span><span class="sxs-lookup"><span data-stu-id="c6b24-178">Idle</span></span>  <br/> ||
|<span data-ttu-id="c6b24-179">Conversation thread ID (会話スレッド ID)</span><span class="sxs-lookup"><span data-stu-id="c6b24-179">Conversation thread ID</span></span>  <br/> |<span data-ttu-id="c6b24-180">AdDO8hsJqilU93hQHC3OZaPR2saEA = =</span><span class="sxs-lookup"><span data-stu-id="c6b24-180">AdDO8hsJqilU93hQHC3OZaPR2saEA==</span></span>  <br/> ||
|<span data-ttu-id="c6b24-181">ユーザー Id</span><span class="sxs-lookup"><span data-stu-id="c6b24-181">UserID</span></span>  <br/> |<span data-ttu-id="c6b24-182">amosmarble</span><span class="sxs-lookup"><span data-stu-id="c6b24-182">amosmarble</span></span> <br/> |<span data-ttu-id="c6b24-183">この ID はテキスト形式で送信され、利用統計情報サービスでハッシュされてから保存されます。</span><span class="sxs-lookup"><span data-stu-id="c6b24-183">The ID is sent in cleartext , which the telemetry service hashes before storing it</span></span>  <br/> |
   
<span data-ttu-id="c6b24-p110">エラー報告データには、ユーザーの IP アドレスや SIP URI (Session Initiation Protocol Uniform Resource Identifier) などの個人を特定できる情報が含まれる場合もあります。収集されるデータの詳細な説明については、「[Skype for Business のプライバシーに関する声明](https://www.microsoft.com/privacystatement/en-us/SkypeforBusiness/Default.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c6b24-p110">Error reporting data may also contain personally identifiable information such as the user's IP address and Session Initiation Protocol Uniform Resource Identifier (SIP URI). See the [Skype for Business Privacy Statement](https://www.microsoft.com/privacystatement/en-us/SkypeforBusiness/Default.aspx) for a detailed explanation of what's collected.</span></span>
  
<span data-ttu-id="c6b24-186">エラー報告には次の 2 つが必要です。</span><span class="sxs-lookup"><span data-stu-id="c6b24-186">Error reporting requires two things:</span></span>
  
- <span data-ttu-id="c6b24-p111">サーバーまたはテナント管理センターで DisableAutomaticSendTracing グループ ポリシー設定を False に設定する必要があります (これが既定の状態です)。詳細については、「[Skype for Business Server 2015 でのクライアント ブートストラップ ポリシーの構成](https://technet.microsoft.com/EN-US/library/gg425941.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c6b24-p111">The DisableAutomaticSendTracing Group Policy setting be set to False on the server or in the tenant admin center (this is the default state). See [Configure client bootstrapping policies in Skype for Business Server 2015](https://technet.microsoft.com/EN-US/library/gg425941.aspx) for more information.</span></span>
    
- <span data-ttu-id="c6b24-189">エンド ユーザーが Skype for Business クライアントの [全般] タブで個別に選択します (歯車アイコンをクリックすると、[オプション] ダイアログ ボックスに [全般] タブが表示されます)。</span><span class="sxs-lookup"><span data-stu-id="c6b24-189">End users individually opt in from the General tab (click the gear icon and the Option dialog opens with the General tab displayed) in the Skype for Business client.</span></span>
    
     ![歯車アイコン](../images/70f1b43f-16d6-4172-9139-71d845c4ed5c.png)
  
![Skype for Business data collection checkbox in the Options > General dialog](../images/68bc8f77-deaa-478c-9977-a5259b88df3e.png)
  
<span data-ttu-id="c6b24-p112">Skype 会議アプリでは、MeetingUxEnableTelemetry によってエラー報告も制御されます。ただし、Windows のクラッシュに関しては Watson 設定によってクラッシュ情報のアップロードが制御されます。Skype 会議アプリには、デスクトップ クライアントのダイアログ ボックスのようにユーザー設定はありません。</span><span class="sxs-lookup"><span data-stu-id="c6b24-p112">For Skype Meetings App, the MeetingUxEnableTelemetry also controls error reporting, although for crashes on Windows, the Watson settings control uploading crash info. There is no user setting for Skype Meetings App like you see in the desktop client dialog box.</span></span>
  
<span data-ttu-id="c6b24-194">詳細については、「[Skype for Business の全般オプションを設定する](http://support.office.com/article/e1a46d3e-dcea-437a-ba7b-6d442a40f439)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c6b24-194">See [Set General options in Skype for Business](http://support.office.com/article/e1a46d3e-dcea-437a-ba7b-6d442a40f439) for more information.</span></span>
  
<span data-ttu-id="c6b24-195">「 [Skype for Business Online 向けにネットワークをセットアップする](http://support.office.com/article/81fa5e16-418d-4698-a5f0-e666211c5c66)」を参照してネットワークをセットアップできます。</span><span class="sxs-lookup"><span data-stu-id="c6b24-195">You can see [Set up your network for Skype for Business Online](http://support.office.com/article/81fa5e16-418d-4698-a5f0-e666211c5c66) to set up your network.</span></span>
  
<span data-ttu-id="c6b24-196">中国の 21Vianet によって運営されている Office 365 を使用している場合は、「[Set up your network for Lync Online](http://support.office.com/article/d21f89b0-3afc-432e-b735-036b2432fdbf)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c6b24-196">If you are using Office 365 operated by 21Vianet in China, see [Set up your network for Skype for Business Online operated by 21Vianet](http://support.office.com/article/d21f89b0-3afc-432e-b735-036b2432fdbf).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="c6b24-197">このモジュールは、64 ビットのコンピューターでのみサポートされ、Microsoft ダウンロード センターの「Skype for Business Online 用 Windows PowerShell モジュール」からダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="c6b24-197">Related topics</span></span>
[<span data-ttu-id="c6b24-198">カスタマー エクスペリエンス向上プログラム</span><span class="sxs-lookup"><span data-stu-id="c6b24-198">Customer Experience Improvement Program</span></span>](https://www.microsoft.com/products/ceip/en-US/default.mspx)

[<span data-ttu-id="c6b24-199">国および地域ごとの電話会議および通話プランの利用可能性</span><span class="sxs-lookup"><span data-stu-id="c6b24-199">Country and region availability for Audio Conferencing and Calling Plans</span></span>](../country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)
