---
title: データ収集方法
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, allancar
ms.topic: reference
ms.assetid: c17e8ea6-b83b-4345-9401-47a6c8b13aad
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-collaboration
search.appverid: MET150
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Legal
- seo-marvel-mar2020
hideEdit: true
description: 製品の改善を計画するために、Microsoft が全数調査、使用状況、およびエラーデータを収集して、チームと Skype for Business の使用状況と問題を理解する方法について説明します。
ms.openlocfilehash: b7f1f7b63645adfb0cfa0c492a680059ef383402
ms.sourcegitcommit: 1807ea5509f8efa6abba8462bce2f3646117e8bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/10/2020
ms.locfileid: "44691533"
---
# <a name="skype-for-business-and-microsoft-teams-data-collection-practices"></a><span data-ttu-id="28db5-103">Skype for Business と Microsoft Teams のデータ収集方法</span><span class="sxs-lookup"><span data-stu-id="28db5-103">Skype for Business and Microsoft Teams data collection practices</span></span>

<span data-ttu-id="28db5-104">Skype for Business Server および Skype for business Online と共に、Skype for Business および Microsoft Teams アプリを使用すると、これらの製品がどのように使われているか、サインインエラーなどのエラーの種類を Microsoft が理解するのに役立つデータが収集されます。</span><span class="sxs-lookup"><span data-stu-id="28db5-104">Skype for Business Server and Skype for Business Online, along with Skype for Business and Microsoft Teams apps, collect data to help Microsoft understand how these products are being used and what kinds of errors, such as sign-in errors, have occurred.</span></span> <span data-ttu-id="28db5-105">Microsoft は、使用パターンの理解、将来の機能の計画、問題の領域のトラブルシューティングと修正のためにこれらの情報を活用できます。</span><span class="sxs-lookup"><span data-stu-id="28db5-105">This information helps us understand usage patterns, plan new features, and troubleshoot and fix problem areas.</span></span>

<span data-ttu-id="28db5-p102">一部の使用データは自動的に収集されますが、管理者またはユーザーによって許可された場合にのみ収集できるデータもあります。収集されるデータは、次の 3 つのカテゴリに分類されます。</span><span class="sxs-lookup"><span data-stu-id="28db5-p102">While some usage data is collected automatically, other data can only be collected when the admin and/or user chooses to allow it. Data collection falls into these three categories:</span></span>

- <span data-ttu-id="28db5-108">全数調査データ</span><span class="sxs-lookup"><span data-stu-id="28db5-108">Census data</span></span>

- <span data-ttu-id="28db5-109">使用状況データ</span><span class="sxs-lookup"><span data-stu-id="28db5-109">Usage data</span></span>

- <span data-ttu-id="28db5-110">エラー報告データ</span><span class="sxs-lookup"><span data-stu-id="28db5-110">Error reporting data</span></span>

## <a name="census-data"></a><span data-ttu-id="28db5-111">全数調査データ</span><span class="sxs-lookup"><span data-stu-id="28db5-111">Census data</span></span>

<span data-ttu-id="28db5-112">全数調査データは、Skype for Business の提供、サポート、改善のためだけに取得されます。</span><span class="sxs-lookup"><span data-stu-id="28db5-112">Census data is acquired solely to provide, support, and improve Skype for Business.</span></span> <span data-ttu-id="28db5-113">Microsoft Teams、Skype for Business Online。</span><span class="sxs-lookup"><span data-stu-id="28db5-113">Microsoft Teams, and Skype for Business Online.</span></span> <span data-ttu-id="28db5-114">これには、デバイスとオペレーティング システムのバージョン、地域と言語の設定などの環境情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="28db5-114">It includes environmental information such as device and operating system versions, and regional and language settings.</span></span> <span data-ttu-id="28db5-115">サインイン試行と失敗のカウンターも含まれます。</span><span class="sxs-lookup"><span data-stu-id="28db5-115">It also includes counters for sign-in attempts and failures.</span></span> <span data-ttu-id="28db5-116">次に、収集される全数調査データの具体例をいくつか示します。</span><span class="sxs-lookup"><span data-stu-id="28db5-116">Here are some specific examples of the census data that's collected:</span></span>

|<span data-ttu-id="28db5-117">**データ型**</span><span class="sxs-lookup"><span data-stu-id="28db5-117">**Data type**</span></span>|<span data-ttu-id="28db5-118">**例**</span><span class="sxs-lookup"><span data-stu-id="28db5-118">**Example**</span></span>|<span data-ttu-id="28db5-119">**メモ**</span><span class="sxs-lookup"><span data-stu-id="28db5-119">**Notes**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="28db5-120">AppName</span><span class="sxs-lookup"><span data-stu-id="28db5-120">AppName</span></span>  <br/> |<span data-ttu-id="28db5-121">iPhoneSkype</span><span class="sxs-lookup"><span data-stu-id="28db5-121">iPhoneSkype</span></span>  <br/> ||
|<span data-ttu-id="28db5-122">DeviceModel</span><span class="sxs-lookup"><span data-stu-id="28db5-122">DeviceModel</span></span>  <br/> |<span data-ttu-id="28db5-123">iPhone</span><span class="sxs-lookup"><span data-stu-id="28db5-123">iPhone</span></span>  <br/> ||
|<span data-ttu-id="28db5-124">OSName</span><span class="sxs-lookup"><span data-stu-id="28db5-124">OSName</span></span>  <br/> |<span data-ttu-id="28db5-125">iPhoneiOS</span><span class="sxs-lookup"><span data-stu-id="28db5-125">iPhoneiOS</span></span>  <br/> ||
|<span data-ttu-id="28db5-126">OSVersion</span><span class="sxs-lookup"><span data-stu-id="28db5-126">OSVersion</span></span>  <br/> |<span data-ttu-id="28db5-127">8.3</span><span class="sxs-lookup"><span data-stu-id="28db5-127">8.3</span></span>  <br/> ||
|<span data-ttu-id="28db5-128">UserLanguage</span><span class="sxs-lookup"><span data-stu-id="28db5-128">UserLanguage</span></span>  <br/> |<span data-ttu-id="28db5-129">EN-US</span><span class="sxs-lookup"><span data-stu-id="28db5-129">EN-US</span></span>  <br/> ||
|<span data-ttu-id="28db5-130">UserID</span><span class="sxs-lookup"><span data-stu-id="28db5-130">UserID</span></span>  <br/> |<span data-ttu-id="28db5-131">E296D735-4F36-4E18-7C3B-52E1A02A0164</span><span class="sxs-lookup"><span data-stu-id="28db5-131">E296D735-4F36-4E18-7C3B-52E1A02A0164</span></span>  <br/> |<span data-ttu-id="28db5-p104">ID は、2 回ハッシュされます (クライアントで 1 回、利用統計情報サービスでもう一回)。ハッシュによって、ID を特定のユーザーに結び付けることができなくなります。</span><span class="sxs-lookup"><span data-stu-id="28db5-p104">The ID is hashed twice: once on the client and again on the telemetry service. The hashing ensures the ID cannot be linked to a specific user.</span></span>  <br/> |
|<span data-ttu-id="28db5-134">DeviceID</span><span class="sxs-lookup"><span data-stu-id="28db5-134">DeviceID</span></span>  <br/> |<span data-ttu-id="28db5-135">5E872200-F546-4CCD-8F23-AF5F507AA2DD</span><span class="sxs-lookup"><span data-stu-id="28db5-135">5E872200-F546-4CCD-8F23-AF5F507AA2DD</span></span>  <br/> |<span data-ttu-id="28db5-136">デバイス ID は、デバイス上でランダムに生成される GUID であり、利用統計情報サービスに送信されます。</span><span class="sxs-lookup"><span data-stu-id="28db5-136">The device ID is a GUID that's randomly generated once on the device and sent to the telemetry service.</span></span>  <br/> |

<span data-ttu-id="28db5-p105">全数調査データには、組織またはユーザーを特定できる情報は含まれていません。詳細については、「[Skype for Business のプライバシーに関する声明](https://www.microsoft.com/privacystatement/SkypeforBusiness/Default.aspx)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="28db5-p105">Census data DOES NOT contain any information that identifies your organization or users. See the [Skype for Business Privacy Statement](https://www.microsoft.com/privacystatement/SkypeforBusiness/Default.aspx) for more information.</span></span>

<span data-ttu-id="28db5-139">全数調査データは、既定でオンになり、管理者やエンド ユーザーがオフにすることはできません。</span><span class="sxs-lookup"><span data-stu-id="28db5-139">Census data is on by default and cannot be turned off by admins or end users.</span></span>

## <a name="usage-data"></a><span data-ttu-id="28db5-140">使用状況データ</span><span class="sxs-lookup"><span data-stu-id="28db5-140">Usage data</span></span>

<span data-ttu-id="28db5-141">使用状況データには、発信した通話の回数、送受信した IM の数、参加した会議の数、機能を使用した頻度、安定性の問題などの情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="28db5-141">Usage data includes information such as number of calls made, number of IMs sent or received, number of meetings joined, frequency of features used, and stability issues.</span></span>

<span data-ttu-id="28db5-p106">使用状況データには、contoso.com などの組織を特定できる情報が含まれる場合もあります。次に、収集される使用状況データの具体例をいくつか示します。</span><span class="sxs-lookup"><span data-stu-id="28db5-p106">Usage data might contain information that identifies your organization, such as contoso.com. Here are some specific examples of the usage data that's collected:</span></span>

|<span data-ttu-id="28db5-144">**データ型**</span><span class="sxs-lookup"><span data-stu-id="28db5-144">**Data type**</span></span>|<span data-ttu-id="28db5-145">**例**</span><span class="sxs-lookup"><span data-stu-id="28db5-145">**Example**</span></span>|<span data-ttu-id="28db5-146">**メモ**</span><span class="sxs-lookup"><span data-stu-id="28db5-146">**Notes**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="28db5-147">IM Sent (送信済み IM)</span><span class="sxs-lookup"><span data-stu-id="28db5-147">IM Sent</span></span>  <br/> |<span data-ttu-id="28db5-148">以内</span><span class="sxs-lookup"><span data-stu-id="28db5-148">12</span></span>  <br/> ||
|<span data-ttu-id="28db5-149">IM Received (受信済み IM)</span><span class="sxs-lookup"><span data-stu-id="28db5-149">IM Received</span></span>  <br/> |<span data-ttu-id="28db5-150">5</span><span class="sxs-lookup"><span data-stu-id="28db5-150">5</span></span>  <br/> ||
|<span data-ttu-id="28db5-151">Join a meeting (attempts) (会議への参加 (試行))</span><span class="sxs-lookup"><span data-stu-id="28db5-151">Join a meeting (attempts)</span></span>  <br/> |<span data-ttu-id="28db5-152">5</span><span class="sxs-lookup"><span data-stu-id="28db5-152">5</span></span>  <br/> ||
|<span data-ttu-id="28db5-153">Join a meeting (success) (会議への参加 (成功))</span><span class="sxs-lookup"><span data-stu-id="28db5-153">Join a meeting (success)</span></span>  <br/> |<span data-ttu-id="28db5-154">4</span><span class="sxs-lookup"><span data-stu-id="28db5-154">4</span></span>  <br/> ||
|<span data-ttu-id="28db5-155">Call/meeting minutes (通話/会議の時間)</span><span class="sxs-lookup"><span data-stu-id="28db5-155">Call/meeting minutes</span></span>  <br/> |<span data-ttu-id="28db5-156">30 mins (30 分)</span><span class="sxs-lookup"><span data-stu-id="28db5-156">30 mins</span></span>  <br/> ||
|<span data-ttu-id="28db5-157">FederationPartner</span><span class="sxs-lookup"><span data-stu-id="28db5-157">FederationPartner</span></span>  <br/> |<span data-ttu-id="28db5-158">Microsoft.com</span><span class="sxs-lookup"><span data-stu-id="28db5-158">Microsoft.com</span></span>  <br/> |<span data-ttu-id="28db5-159">これは、Office 365 に登録されている組織の名前で、テキスト形式で送信されるため暗号化されません。</span><span class="sxs-lookup"><span data-stu-id="28db5-159">This is the name of the organization registered in Office 365 and is transmitted in cleartext, which means it's not obfuscated.</span></span>  <br/> |

<span data-ttu-id="28db5-160">使用状況データには、ユーザーを特定できる情報は含まれていません。</span><span class="sxs-lookup"><span data-stu-id="28db5-160">Usage data DOES NOT contain any information that identifies users.</span></span>

<span data-ttu-id="28db5-161">利用状況データの収集は既定で有効ですが、オンプレミス管理者は、Skype for Business Server の Disable自動 Sendtracing グループポリシー設定を使用してオフにすることができます。</span><span class="sxs-lookup"><span data-stu-id="28db5-161">Usage data collection is on by default, but on-premises admins can turn it off using the DisableAutomaticSendTracing Group Policy setting on Skype for Business Server.</span></span> <span data-ttu-id="28db5-162">この設定をオフにすると、組織のすべてのユーザーが影響を受けます。</span><span class="sxs-lookup"><span data-stu-id="28db5-162">Turning this setting off affects all users in the organization.</span></span> <span data-ttu-id="28db5-163">詳細については、「[クライアントブートストラップポリシーを構成する](/skypeforbusiness/deploy/deploy-clients/configure-client-bootstrapping-policies)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="28db5-163">See [Configure client bootstrapping policies](/skypeforbusiness/deploy/deploy-clients/configure-client-bootstrapping-policies) for more information.</span></span>

<span data-ttu-id="28db5-164">エンド ユーザーは使用状況データの収集のオンとオフを切り替えることはできません。</span><span class="sxs-lookup"><span data-stu-id="28db5-164">End users cannot turn usage data collection on or off.</span></span>

<span data-ttu-id="28db5-165">Skype 会議アプリと Join Launcher Web ページでは、利用統計情報は次のポリシーによって制御されます。</span><span class="sxs-lookup"><span data-stu-id="28db5-165">For Skype Meetings App and the join launcher web pages, the way to control telemetry is through this policy:</span></span>

`Set-CsWebServiceConfiguration -MeetingUxEnableTelemetry $True`

<span data-ttu-id="28db5-p108">このポリシーの既定値は False であるため、利用統計情報は既定では収集されません。この設定はプールごとに行われ、Skype 会議アプリを使用してそのサーバーでホストされる会議に接続するすべてのユーザーを制御します。</span><span class="sxs-lookup"><span data-stu-id="28db5-p108">This policy defaults to false, so telemetry collection is off by default. This setting is per-pool and controls all users who connect with Skype Meetings App to a meeting hosted on that server.</span></span>

## <a name="error-reporting-data"></a><span data-ttu-id="28db5-168">エラー報告データ</span><span class="sxs-lookup"><span data-stu-id="28db5-168">Error reporting data</span></span>

<span data-ttu-id="28db5-p109">エラー報告データには、パフォーマンスと信頼性、デバイスの構成、ネットワーク接続の品質、エラー コード、エラー ログ、例外などの情報が含まれることがあります。次に、収集されるエラー報告データの具体例をいくつか示します。</span><span class="sxs-lookup"><span data-stu-id="28db5-p109">Error reporting data can include information about performance and reliability, device configuration, network connection quality, error codes, error logs, and exceptions. Here are some specific examples of error reporting data that's collected:</span></span>

|<span data-ttu-id="28db5-171">**データ型**</span><span class="sxs-lookup"><span data-stu-id="28db5-171">**Data type**</span></span>|<span data-ttu-id="28db5-172">**例**</span><span class="sxs-lookup"><span data-stu-id="28db5-172">**Example**</span></span>|<span data-ttu-id="28db5-173">**メモ**</span><span class="sxs-lookup"><span data-stu-id="28db5-173">**Notes**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="28db5-174">Message direction (メッセージの方向)</span><span class="sxs-lookup"><span data-stu-id="28db5-174">Message direction</span></span>  <br/> |<span data-ttu-id="28db5-175">Incoming (受信)</span><span class="sxs-lookup"><span data-stu-id="28db5-175">Incoming</span></span>  <br/> ||
|<span data-ttu-id="28db5-176">Conversation state (会話の状態)</span><span class="sxs-lookup"><span data-stu-id="28db5-176">Conversation state</span></span>  <br/> |<span data-ttu-id="28db5-177">Idle (アイドル)</span><span class="sxs-lookup"><span data-stu-id="28db5-177">Idle</span></span>  <br/> ||
|<span data-ttu-id="28db5-178">Conversation thread ID (会話スレッド ID)</span><span class="sxs-lookup"><span data-stu-id="28db5-178">Conversation thread ID</span></span>  <br/> |<span data-ttu-id="28db5-179">AdDO8hsJqilU93hQHC3OZaPR2saEA = =</span><span class="sxs-lookup"><span data-stu-id="28db5-179">AdDO8hsJqilU93hQHC3OZaPR2saEA==</span></span>  <br/> ||
|<span data-ttu-id="28db5-180">UserID</span><span class="sxs-lookup"><span data-stu-id="28db5-180">UserID</span></span>  <br/> |<span data-ttu-id="28db5-181">amosmarble</span><span class="sxs-lookup"><span data-stu-id="28db5-181">amosmarble</span></span> <br/> |<span data-ttu-id="28db5-182">この ID はテキスト形式で送信され、利用統計情報サービスでハッシュされてから保存されます。</span><span class="sxs-lookup"><span data-stu-id="28db5-182">The ID is sent in cleartext , which the telemetry service hashes before storing it</span></span>  <br/> |

<span data-ttu-id="28db5-p110">エラー報告データには、ユーザーの IP アドレスや SIP URI (Session Initiation Protocol Uniform Resource Identifier) などの個人を特定できる情報が含まれる場合もあります。収集されるデータの詳細な説明については、「[Skype for Business のプライバシーに関する声明](https://www.microsoft.com/privacystatement/SkypeforBusiness/Default.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="28db5-p110">Error reporting data may also contain personally identifiable information such as the user's IP address and Session Initiation Protocol Uniform Resource Identifier (SIP URI). See the [Skype for Business Privacy Statement](https://www.microsoft.com/privacystatement/SkypeforBusiness/Default.aspx) for a detailed explanation of what's collected.</span></span>

<span data-ttu-id="28db5-185">エラー報告には次の 2 つが必要です。</span><span class="sxs-lookup"><span data-stu-id="28db5-185">Error reporting requires two things:</span></span>

- <span data-ttu-id="28db5-186">サーバーまたはテナント管理センターで、Disable自動 Sendtracing グループポリシー設定が False に設定されています (既定の状態)。</span><span class="sxs-lookup"><span data-stu-id="28db5-186">The DisableAutomaticSendTracing Group Policy setting is set to False on the server or in the tenant admin center (this is the default state).</span></span> <span data-ttu-id="28db5-187">詳細については、「[クライアントブートストラップポリシーを構成する](/skypeforbusiness/deploy/deploy-clients/configure-client-bootstrapping-policies)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="28db5-187">See [Configure client bootstrapping policies](/skypeforbusiness/deploy/deploy-clients/configure-client-bootstrapping-policies) for more information.</span></span>
    
- <span data-ttu-id="28db5-188">エンドユーザーは、[全般] タブで個別にオプトインすることができます (歯車アイコンをクリックする ![ と歯車を表すアイコンが表示され、[ ](media/70f1b43f-16d6-4172-9139-71d845c4ed5c.png) **オプション**] ダイアログボックスには、Skype for Business クライアントの [**全般**] タブが表示されます)。</span><span class="sxs-lookup"><span data-stu-id="28db5-188">End users individually opt in from the General tab (click the gear icon ![An icon that represents a gear ](media/70f1b43f-16d6-4172-9139-71d845c4ed5c.png) and then the **Options** dialog opens with the **General** tab displayed) in the Skype for Business client.</span></span>
    
 
![[オプション] ダイアログの [データ収集] チェックボックスのスクリーンショット](media/68bc8f77-deaa-478c-9977-a5259b88df3e.png)
  
<span data-ttu-id="28db5-p112">Skype 会議アプリでは、MeetingUxEnableTelemetry によってエラー報告も制御されます。ただし、Windows のクラッシュに関しては Watson 設定によってクラッシュ情報のアップロードが制御されます。Skype 会議アプリには、デスクトップ クライアントのダイアログ ボックスのようにユーザー設定はありません。</span><span class="sxs-lookup"><span data-stu-id="28db5-p112">For Skype Meetings App, the MeetingUxEnableTelemetry also controls error reporting, although for crashes on Windows, the Watson settings control uploading crash info. There is no user setting for Skype Meetings App like you see in the desktop client dialog box.</span></span>

<span data-ttu-id="28db5-192">詳細については、「[Skype for Business の全般オプションを設定する](https://support.office.com/article/e1a46d3e-dcea-437a-ba7b-6d442a40f439)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="28db5-192">See [Set General options in Skype for Business](https://support.office.com/article/e1a46d3e-dcea-437a-ba7b-6d442a40f439) for more information.</span></span>

<span data-ttu-id="28db5-193">「 [Skype for Business Online 向けにネットワークをセットアップする](https://support.office.com/article/81fa5e16-418d-4698-a5f0-e666211c5c66)」を参照してネットワークをセットアップできます。</span><span class="sxs-lookup"><span data-stu-id="28db5-193">You can see [Set up your network for Skype for Business Online](https://support.office.com/article/81fa5e16-418d-4698-a5f0-e666211c5c66) to set up your network.</span></span>

<span data-ttu-id="28db5-194">中国の21Vianet が運営する Microsoft 365 または Office 365 を使用している場合は、「 [21vianet が運営する Skype For Business Online 用にネットワーク](https://support.office.com/article/d21f89b0-3afc-432e-b735-036b2432fdbf)をセットアップする」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="28db5-194">If you are using Microsoft 365 or Office 365 operated by 21Vianet in China, see [Set up your network for Skype for Business Online operated by 21Vianet](https://support.office.com/article/d21f89b0-3afc-432e-b735-036b2432fdbf).</span></span>

## <a name="related-topics"></a><span data-ttu-id="28db5-195">関連トピック</span><span class="sxs-lookup"><span data-stu-id="28db5-195">Related topics</span></span>
[<span data-ttu-id="28db5-196">国および地域ごとの電話会議および通話プランの利用可能性</span><span class="sxs-lookup"><span data-stu-id="28db5-196">Country and region availability for Audio Conferencing and Calling Plans</span></span>](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)
