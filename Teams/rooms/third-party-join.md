---
title: デバイスTeams ミーティングサードパーティ会議への参加を有効にする
ms.author: dstrome
author: dstrome
manager: serdars
ms.reviewer: sohailta
audience: ITPro
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
localization_priority: Normal
description: この記事では、Cisco WebEx と Zoom へのサードパーティの会議参加をサポートTeams ミーティングデバイスを構成する方法について説明します。
ms.openlocfilehash: ef14d1f342c6f2b34ad7c948a2688fa39a09801d
ms.sourcegitcommit: 8ad05b37c0b714adb069bc2503e88366ab75c57d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/07/2021
ms.locfileid: "52796691"
---
# <a name="enable-teams-room-devices-to-join-third-party-meetings"></a><span data-ttu-id="07781-103">ルーム Teamsサード パーティ会議への参加を有効にする</span><span class="sxs-lookup"><span data-stu-id="07781-103">Enable Teams Room devices to join third-party meetings</span></span>

<span data-ttu-id="07781-104">Microsoft Teams ミーティングデバイスは、サード パーティのオンライン会議 (直接ゲスト参加とも呼ばれます) に参加するワンタッチ エクスペリエンスをサポートします。</span><span class="sxs-lookup"><span data-stu-id="07781-104">Microsoft Teams Rooms devices support a one-touch experience for joining third-party online meetings, also referred to as Direct guest join.</span></span> <span data-ttu-id="07781-105">有効にすると、Teams ミーティング デバイスを使用して、Cisco WebEx および Zoom でホストされている会議に、Microsoft Teams でホストされている会議に参加できるのと同じ方法で簡単に参加できます。</span><span class="sxs-lookup"><span data-stu-id="07781-105">When enabled, you can use a Teams Rooms device to join meetings hosted on Cisco WebEx and Zoom just as easily as you can join meetings hosted in Microsoft Teams.</span></span>

<span data-ttu-id="07781-106">デバイスからサードパーティの会議に参加するにはTeams ミーティング、次の操作を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="07781-106">Before you can join third-party meetings from a Teams Rooms device, you need to do the following:</span></span>

1. <span data-ttu-id="07781-107">サード パーティTeams ミーティング招待を処理Exchange Onlineデバイスのメールボックスを構成します。</span><span class="sxs-lookup"><span data-stu-id="07781-107">Configure the Teams Rooms device's Exchange Online room mailbox to process invites for third-party meetings.</span></span>
2. <span data-ttu-id="07781-108">組織に、サードパーティの会議サービスへの接続を妨げるポリシーが設定されていないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="07781-108">Make sure your organization doesn't have any policies that would prevent you from connecting to third-party meeting services.</span></span>
3. <span data-ttu-id="07781-109">サード パーティTeams ミーティングを許可するデバイスを構成します。</span><span class="sxs-lookup"><span data-stu-id="07781-109">Configure your Teams Rooms devices to allow third-party meetings.</span></span>

<span data-ttu-id="07781-110">次のセクションでは、これらの各手順を実行する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="07781-110">The following sections show you how to do each of these steps.</span></span>

## <a name="step-1-allow-calendar-invite-processing-for-third-party-meetings"></a><span data-ttu-id="07781-111">手順 1: サードパーティ会議の予定表の招待処理を許可する</span><span class="sxs-lookup"><span data-stu-id="07781-111">Step 1: Allow calendar invite processing for third-party meetings</span></span>

<span data-ttu-id="07781-112">Team Rooms デバイスからワンタッチ参加エクスペリエンスを有効にするには、まず、デバイスの会議室メールボックスの予定表処理ルールをExchange Onlineがあります。</span><span class="sxs-lookup"><span data-stu-id="07781-112">The first thing you need to do to enable a one-touch join experience from a Team Rooms device is set the calendar processing rules for the device's Exchange Online room mailbox.</span></span> <span data-ttu-id="07781-113">会議室メールボックスは、外部会議を許可し、メッセージの本文と件名を保持して、サード パーティ会議に参加するために必要な URL を確認できる必要があります。</span><span class="sxs-lookup"><span data-stu-id="07781-113">The room mailbox needs to allow external meetings and keep the message body and subject so it can see the URL needed to join the third-party meeting.</span></span> <span data-ttu-id="07781-114">[Set-CalendarProcessing](/powershell/module/exchange/set-calendarprocessing?view=exchange-ps.)コマンドレットを使用してこれらのルーム メールボックス オプションを設定するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="07781-114">To set these room mailbox options using the [Set-CalendarProcessing](/powershell/module/exchange/set-calendarprocessing?view=exchange-ps.) cmdlet, do the following:</span></span>

1. <span data-ttu-id="07781-115">Exchange Online PowerShell に接続します。</span><span class="sxs-lookup"><span data-stu-id="07781-115">Connect to Exchange Online PowerShell.</span></span> <span data-ttu-id="07781-116">詳細については、「基本認証を使用して[PowerShell](/powershell/exchange/connect-to-exchange-online-powershell?view=exchange-ps) ConnectをExchange Onlineする」を参照するか、認証方法に応じて、Connect から Exchange Online [PowerShell](/powershell/exchange/mfa-connect-to-exchange-online-powershell?view=exchange-ps)に対して多要素認証を使用する方法に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="07781-116">For more information, see [Connect to Exchange Online PowerShell with Basic authentication](/powershell/exchange/connect-to-exchange-online-powershell?view=exchange-ps) or [Connect to Exchange Online PowerShell using multi-factor authentication](/powershell/exchange/mfa-connect-to-exchange-online-powershell?view=exchange-ps), depending on your authentication method.</span></span>

2. <span data-ttu-id="07781-117">次のコマンドを実行して、ルーム メールボックスのユーザー プリンシパル名 (UPN) を取得します (知らない場合)。</span><span class="sxs-lookup"><span data-stu-id="07781-117">Get the User Principal Name (UPN) of the room mailbox if you don't know it by running the following command:</span></span>

    ```powershell
    Get-Mailbox | Where {$_.RoomMailboxAccountEnabled -eq $True} | Format-Table Name, UserPrincipalName
    ```
    
3. <span data-ttu-id="07781-118">デバイスに関連付けられているルーム メールボックスの名前Teams ミーティング、その UPN をメモします。</span><span class="sxs-lookup"><span data-stu-id="07781-118">Find the name of the room mailbox associated with your Teams Rooms device and make note of its UPN.</span></span>

4. <span data-ttu-id="07781-119">ルーム メールボックスの UPN が見つけたら、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="07781-119">After you find the room mailbox's UPN, run the following command.</span></span> <span data-ttu-id="07781-120">を `<UserPrincipalName>` ルーム メールボックスの UPN に置き換える:</span><span class="sxs-lookup"><span data-stu-id="07781-120">Replace `<UserPrincipalName>` with the room mailbox's UPN:</span></span>

    ```powershell
    Set-CalendarProcessing <UserPrincipalName> -ProcessExternalMeetingMessages $True -DeleteComments $False -DeleteSubject $False
    ```

<span data-ttu-id="07781-121">PowerShell の詳細[Exchange Onlineを参照してください](/powershell/exchange/exchange-online-powershell?view=exchange-ps)。</span><span class="sxs-lookup"><span data-stu-id="07781-121">Learn more about [Exchange Online PowerShell](/powershell/exchange/exchange-online-powershell?view=exchange-ps).</span></span>

## <a name="step-2-configure-office-365-threat-protection-and-link-rewrite"></a><span data-ttu-id="07781-122">手順 2: Threat Protection とOffice 365書き換えを構成する</span><span class="sxs-lookup"><span data-stu-id="07781-122">Step 2: Configure Office 365 Threat Protection and link rewrite</span></span>

<span data-ttu-id="07781-123">ワンタッチ参加エクスペリエンスを有効にするには、サードパーティの会議からの会議参加リンク情報が会議の招待に表示され、読み取り可能である必要があります。</span><span class="sxs-lookup"><span data-stu-id="07781-123">To enable the one-touch join experience, meeting join link information from the third-party meeting needs to be present and readable in the meeting invite.</span></span> <span data-ttu-id="07781-124">組織で Office 365 [Advanced Threat Protection セーフ リンク](/microsoft-365/security/office-365-security/atp-safe-links)機能を使用している場合、またはすべての受信 URL と送信 URL をスキャンして脅威を検出するサード パーティ製ソリューションを使用している場合は、会議参加 URL が変更され、Teams ミーティング デバイスで会議が認識できない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="07781-124">If your organization uses the [Office 365 Advanced Threat Protection Safe Links](/microsoft-365/security/office-365-security/atp-safe-links) feature, or if you use a third-party solution that scans all incoming and outgoing URLs for threats, it may change the meeting join URLs and make the meeting unrecognizable by the Teams Rooms device.</span></span> <span data-ttu-id="07781-125">これが発生しない場合は、サード パーティの会議サービスの URL を ATP セーフ リンクの "書き換えない" リストまたはサード パーティの URL 書き換え例外リストに追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="07781-125">To make sure this doesn't happen, you need to add the third-party meeting service's URLs to the ATP Safe Links "do not rewrite" list or the third-party URL rewrite exception list.</span></span>

<span data-ttu-id="07781-126">サードパーティの会議サービス URL を ATP セーフ リンクの "書き換えない" リストに追加するには、「ATP セーフ リンクを使用してカスタムの書き換えない URL リストを設定する」の[手順に従](/microsoft-365/security/office-365-security/set-up-a-custom-do-not-rewrite-urls-list-with-atp?view=o365-worldwide)います。</span><span class="sxs-lookup"><span data-stu-id="07781-126">To add third-party meeting service URLs to the ATP Safe Links "do not rewrite" list, follow the steps in [Set up a custom do-not-rewrite URLs list using ATP Safe Links](/microsoft-365/security/office-365-security/set-up-a-custom-do-not-rewrite-urls-list-with-atp?view=o365-worldwide).</span></span> <span data-ttu-id="07781-127">サード パーティのソリューションを使用する場合は、そのソリューションの手順を参照して、URL 書き換え例外リストに URL を追加します。</span><span class="sxs-lookup"><span data-stu-id="07781-127">If you use a third-party solution, refer to the instructions for that solution to add URLs to its URL rewrite exception list.</span></span>

<span data-ttu-id="07781-128">ATP セーフ リンク "書き換えない" リストまたはサード パーティの URL 書き換え例外リストに追加する必要があるエントリの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="07781-128">Here are some example entries that you may need to add to your ATP Safe Links "do not rewrite" list or third-party URL rewrite exception list:</span></span>

- <span data-ttu-id="07781-129">**Cisco WebEx**`*.webex.com*`</span><span class="sxs-lookup"><span data-stu-id="07781-129">**Cisco WebEx** `*.webex.com*`</span></span>
- <span data-ttu-id="07781-130">**ズーム** `*.zoom.us*` `*.zoom.com*` 、、、 `*.zoomgov.com*`</span><span class="sxs-lookup"><span data-stu-id="07781-130">**Zoom** `*.zoom.us*`, `*.zoom.com*`, `*.zoomgov.com*`</span></span>

<span data-ttu-id="07781-131">ATP セーフ リンク "書き換えない" リストまたはサード パーティの URL 書き換え例外リストに追加する URL の完全な一覧については、会議の招待を受け入れるサードパーティの会議サービス プロバイダーにお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="07781-131">For a complete list of URLs to add to your ATP Safe Links "do not rewrite" list or third-party URL rewrite exception list, contact the third-party meeting service provider you want to accept meeting invites from.</span></span> 

> [!CAUTION]
> <span data-ttu-id="07781-132">信頼できる URL のみを ATP セーフリンク "書き換えない" リストまたはサード パーティの URL 書き換え例外リストに追加します。</span><span class="sxs-lookup"><span data-stu-id="07781-132">Only add URLs that you trust to your ATP Safe Links "do not rewrite" list or third-party URL rewrite exception list.</span></span>

## <a name="step-3-enable-third-party-meetings-on-device"></a><span data-ttu-id="07781-133">手順 3: デバイスでサードパーティの会議を有効にする</span><span class="sxs-lookup"><span data-stu-id="07781-133">Step 3: Enable third-party meetings on device</span></span>

<span data-ttu-id="07781-134">最後に行う必要がある手順は、デバイスTeams ミーティングサードパーティ会議への参加を許可します。</span><span class="sxs-lookup"><span data-stu-id="07781-134">The last step you need to do is allow each Teams Rooms device to join third-party meetings.</span></span> <span data-ttu-id="07781-135">サードパーティ会議に参加するには、ユーザー名とメール アドレスが必要です。</span><span class="sxs-lookup"><span data-stu-id="07781-135">Third-party meetings require a username and email address to join them.</span></span> <span data-ttu-id="07781-136">使用する必要があるユーザー名とメール アドレスがデバイスのルーム メールボックスと異なる場合は、デバイスに追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="07781-136">If the username and email address that you need to use is different than the device's room mailbox, you need to add them to your device.</span></span> <span data-ttu-id="07781-137">これは、デバイス設定または XML 構成ファイルで行います。</span><span class="sxs-lookup"><span data-stu-id="07781-137">You can do this in the device settings or in the XML config file.</span></span>

### <a name="use-device-settings"></a><span data-ttu-id="07781-138">デバイス設定を使用する</span><span class="sxs-lookup"><span data-stu-id="07781-138">Use device settings</span></span>

<span data-ttu-id="07781-139">タッチスクリーンを使用Teams ミーティングデバイスを構成するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="07781-139">To configure the Teams Rooms device using its touchscreen, do the following:</span></span>

1. <span data-ttu-id="07781-140">デバイスのMicrosoft Teams ミーティング、[詳細 **...] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="07781-140">On the Microsoft Teams Rooms device, select **More ...**.</span></span>
2. <span data-ttu-id="07781-141">**[設定]** を選択し、デバイス管理者のユーザー名とパスワードを入力します。</span><span class="sxs-lookup"><span data-stu-id="07781-141">Select **Settings**, and then enter the device administrator username and password.</span></span>
3. <span data-ttu-id="07781-142">[会議] タブ **に移動** し **、[Cisco WebEx]、または [\*\*\*\*ズーム**]、または両方を選択します。</span><span class="sxs-lookup"><span data-stu-id="07781-142">Go to the **Meetings** tab and select **Cisco WebEx**, **Zoom**, or both.</span></span>
4. <span data-ttu-id="07781-143">ルーム メールボックスに関連付けられているユーザー名とメール アドレスで会議に参加する場合は、[ルーム情報で参加 **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="07781-143">If you want to join meetings with the username and email address associated with the room mailbox, select **Join with room info**.</span></span>
5. <span data-ttu-id="07781-144">別のユーザー名とメール アドレスで会議に参加する場合は、[カスタム情報で参加] を選択し、使用するユーザー名とメール アドレスを入力します。</span><span class="sxs-lookup"><span data-stu-id="07781-144">If you want to join meetings with an alternate username and email address, select **Join with custom info** and enter username and email address you'd like to use.</span></span>
6. <span data-ttu-id="07781-145">**[保存して終了]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="07781-145">Select **Save and exit**.</span></span> <span data-ttu-id="07781-146">デバイスが再起動します。</span><span class="sxs-lookup"><span data-stu-id="07781-146">Your device will restart.</span></span>

### <a name="use-the-skypesettingsxml-configuration-file"></a><span data-ttu-id="07781-147">構成ファイルSkypeSettings.xml使用する</span><span class="sxs-lookup"><span data-stu-id="07781-147">Use the SkypeSettings.xml configuration file</span></span>

<span data-ttu-id="07781-148">にある ファイルには、次の `SkypeSettings.xml` 設定を追加できます `C:\Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState` 。</span><span class="sxs-lookup"><span data-stu-id="07781-148">The following settings can be added to the `SkypeSettings.xml` file located in `C:\Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState`.</span></span> <span data-ttu-id="07781-149">ファイルの詳細については、「XML 構成ファイルを使用Microsoft Teams ミーティング本体の設定をリモートで管理 `SkypeSettings.xml` [する」を参照してください](xml-config-file.md)。</span><span class="sxs-lookup"><span data-stu-id="07781-149">For more information about the `SkypeSettings.xml` file, see [Manage a Microsoft Teams Rooms console settings remotely with an XML configuration file](xml-config-file.md).</span></span>

<span data-ttu-id="07781-150">Cisco WebEx 会議を有効にするには、次のように XML 要素 `WebExMeetingsEnabled` を **True** に設定します。</span><span class="sxs-lookup"><span data-stu-id="07781-150">To enable Cisco WebEx meetings, set the `WebExMeetingsEnabled` XML element to **True**, as follows.</span></span>

```xml
<WebExMeetingsEnabled>True</WebExMeetingsEnabled>
```

<span data-ttu-id="07781-151">Zoom 会議を有効にするには、 `ZoomMeetingsEnabled` 次のように XML 要素を **True** に設定します。</span><span class="sxs-lookup"><span data-stu-id="07781-151">To enable Zoom meetings, set the `ZoomMeetingsEnabled` XML element to **True**, as follows.</span></span>

```xml
<ZoomMeetingsEnabled>True</ZoomMeetingsEnabled>
```

<span data-ttu-id="07781-152">必要に応じて、カスタム ユーザー名とメール アドレスを指定して、次の XML 要素を使用してサードパーティの会議に参加できます。</span><span class="sxs-lookup"><span data-stu-id="07781-152">You can optionally specify a custom username and email address to join third-party meetings using the following XML elements.</span></span> <span data-ttu-id="07781-153">指定した値が無効な場合、既定ではTeams ミーティングメールボックスのユーザー名とメール アドレスが使用されます。</span><span class="sxs-lookup"><span data-stu-id="07781-153">If the values you provide aren't valid, the Teams Rooms device will default to use room mailbox username and email address.</span></span>

```xml
<UseCustomInfoForThirdPartyMeetings>true</UseCustomInfoForThirdPartyMeetings>

<CustomDisplayNameForThirdPartyMeetings>guestname</CustomDisplayNameForThirdPartyMeetings>

<CustomDisplayEmailForThirdPartyMeetings>guest@contoso.com</CustomDisplayEmailForThirdPartyMeetings>
```

> [!NOTE]
> <span data-ttu-id="07781-154">Teams ミーティング デバイスから Cisco WebEx 会議に参加するには、Cisco WebEx Web アプリケーション バージョン WBS 40.7 以降を使用して、WebEx Meetings Pro で Cisco 会議をホストする必要があります。</span><span class="sxs-lookup"><span data-stu-id="07781-154">To join a Cisco WebEx meeting from a Teams Rooms device, the Cisco meeting needs to be hosted in WebEx Meetings Pro using Cisco WebEx web application version WBS 40.7 or later.</span></span> 
