---
title: Teams 室のデバイスでサードパーティの会議に参加できるようにする
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
description: この記事では、組織とチーム室のデバイスを構成して、サードパーティの会議への参加をサポートする方法について説明します。
ms.openlocfilehash: 708fb7f9d243559a571b2b9016fab1e38aa63114
ms.sourcegitcommit: 3e5cac88911611c94c0330bf50af9c34db308cdf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/22/2020
ms.locfileid: "45372216"
---
# <a name="enable-teams-room-devices-to-join-third-party-meetings"></a><span data-ttu-id="e68d6-103">Teams Room デバイスでサードパーティの会議に参加できるようにする</span><span class="sxs-lookup"><span data-stu-id="e68d6-103">Enable Teams Room devices to join third-party meetings</span></span>

<span data-ttu-id="e68d6-104">Microsoft Teams の会議室のデバイスは、サードパーティのオンライン会議に参加するためのワンタッチエクスペリエンスをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="e68d6-104">Microsoft Teams Rooms devices support a one-touch experience for joining third-party online meetings.</span></span> <span data-ttu-id="e68d6-105">有効にすると、チームルームデバイスを使って、Cisco WebEx でホストされている会議に参加したり、Microsoft Teams でホストされている会議に参加したりするのと同じように簡単<sup>にズームする</sup> ことができます。</span><span class="sxs-lookup"><span data-stu-id="e68d6-105">When enabled, you can use a Teams Rooms device to join meetings hosted on Cisco WebEx and Zoom<sup>1</sup> just as easily as you can join meetings hosted in Microsoft Teams.</span></span>

<span data-ttu-id="e68d6-106">Teams 室のデバイスからサードパーティの会議に参加するには、次の手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e68d6-106">Before you can join third-party meetings from a Teams Rooms device, you need to do the following:</span></span>

1. <span data-ttu-id="e68d6-107">サードパーティの会議の招待を処理するために Teams 室デバイスの Exchange Online room メールボックスを構成する</span><span class="sxs-lookup"><span data-stu-id="e68d6-107">Configure the Teams Rooms device's Exchange Online room mailbox to process invites for third-party meetings</span></span>
2. <span data-ttu-id="e68d6-108">サードパーティの会議サービスに接続できないポリシーが組織にないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="e68d6-108">Make sure your organization doesn't have any policies that would prevent you from connecting to third-party meeting services</span></span>
3. <span data-ttu-id="e68d6-109">サードパーティの会議を許可するようにチームルームデバイスを構成する</span><span class="sxs-lookup"><span data-stu-id="e68d6-109">Configure your Teams Rooms devices to allow third-party meetings</span></span>

<span data-ttu-id="e68d6-110">以下のセクションでは、これらの各手順を実行する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="e68d6-110">The following sections show you how to do each of these steps.</span></span>

## <a name="step-1-allow-calendar-invite-processing-for-third-party-meetings"></a><span data-ttu-id="e68d6-111">手順 1: サードパーティの会議の予定表の招待処理を許可する</span><span class="sxs-lookup"><span data-stu-id="e68d6-111">Step 1: Allow calendar invite processing for third-party meetings</span></span>

<span data-ttu-id="e68d6-112">チームルームデバイスからワンタッチの参加を有効にするには、まず、デバイスの Exchange Online room メールボックスの予定表処理ルールを設定します。</span><span class="sxs-lookup"><span data-stu-id="e68d6-112">The first thing you need to do to enable a one-touch join experience from a Team Rooms device is set the calendar processing rules for the device's Exchange Online room mailbox.</span></span> <span data-ttu-id="e68d6-113">会議室メールボックスでは、第三者の会議に参加するために必要な URL が表示されるように、外部会議を許可し、メッセージ本文と件名を保持する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e68d6-113">The room mailbox needs to allow external meetings and keep the message body and subject so it can see the URL needed to join the third-party meeting.</span></span> <span data-ttu-id="e68d6-114">[ [カレンダーの設定](https://docs.microsoft.com/powershell/module/exchange/set-calendarprocessing?view=exchange-ps.) ] コマンドレットを使用して、会議室のメールボックスのオプションを設定するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="e68d6-114">To set these room mailbox options using the [Set-CalendarProcessing](https://docs.microsoft.com/powershell/module/exchange/set-calendarprocessing?view=exchange-ps.) cmdlet, do the following:</span></span>

1. <span data-ttu-id="e68d6-115">Exchange Online PowerShell に接続します。</span><span class="sxs-lookup"><span data-stu-id="e68d6-115">Connect to Exchange Online PowerShell.</span></span> <span data-ttu-id="e68d6-116">詳細については、認証方法に応じて、「Basic 認証を使用して [Exchange Online powershell に接続する](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell?view=exchange-ps) 」または「 [多要素認証を使用して exchange online powershell に](https://docs.microsoft.com/powershell/exchange/mfa-connect-to-exchange-online-powershell?view=exchange-ps)接続する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e68d6-116">For more information, see [Connect to Exchange Online Powershell with Basic authentication](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell?view=exchange-ps) or [Connect to Exchange Online PowerShell using multi-factor authentication](https://docs.microsoft.com/powershell/exchange/mfa-connect-to-exchange-online-powershell?view=exchange-ps), depending on your authentication method.</span></span>

2. <span data-ttu-id="e68d6-117">次のコマンドを実行して、会議室のメールボックスがわからない場合は、ユーザープリンシパル名 (UPN) を取得します。</span><span class="sxs-lookup"><span data-stu-id="e68d6-117">Get the User Principal Name (UPN) of the room mailbox if you don't know it by running the following command:</span></span>

    ```powershell
    Get-Mailbox | Where {$_.RoomMailboxAccountEnabled -eq $True} | Format-Table Name, UserPrincipalName
    ```
3. <span data-ttu-id="e68d6-118">チームルームデバイスに関連付けられている会議室メールボックスの名前を検索し、その UPN をメモしておきます。</span><span class="sxs-lookup"><span data-stu-id="e68d6-118">Find the name of the room mailbox associated with your Teams Rooms device and make note of its UPN</span></span>

4. <span data-ttu-id="e68d6-119">会議室メールボックスの UPN が見つかったら、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="e68d6-119">After you find the room mailbox's UPN, run the following command.</span></span> <span data-ttu-id="e68d6-120">`<UserPrincipalName>`会議室のメールボックスの UPN に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="e68d6-120">Replace `<UserPrincipalName>` with the room mailbox's UPN:</span></span>

    ```powershell
    Set-CalendarProcessing <UserPrincipalName> -ProcessExternalMeetingMessages $True -DeleteComments $False -DeleteSubject $False
    ```

<span data-ttu-id="e68d6-121">詳細については、「 [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell?view=exchange-ps)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e68d6-121">Learn more about [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell?view=exchange-ps).</span></span>

## <a name="step-2-configure-office-365-threat-protection-and-link-rewrite"></a><span data-ttu-id="e68d6-122">手順 2: Office 365 の脅威保護とリンクの書き換えを構成する</span><span class="sxs-lookup"><span data-stu-id="e68d6-122">Step 2: Configure Office 365 Threat Protection and link rewrite</span></span>

<span data-ttu-id="e68d6-123">ワンタッチの参加エクスペリエンスを有効にするには、サードパーティの会議からの会議の参加リンク情報が会議出席依頼に表示され、読むことができる必要があります。</span><span class="sxs-lookup"><span data-stu-id="e68d6-123">To enable the one-touch join experience, meeting join link information from the third-party meeting needs to be present and readable in the meeting invite.</span></span> <span data-ttu-id="e68d6-124">組織で[Office 365 Advanced Threat Protection 安全なリンク](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-safe-links)機能を使用している場合、   またはすべての受信 Url と送信 url をスキャンするサードパーティソリューションを使用している場合は、会議の参加 url を変更して、チームルームデバイスでその会議を認識しないようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="e68d6-124">If your organization uses the [Office 365 Advanced Threat Protection Safe Links](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-safe-links) feature, or if you use a third-party solution that scans all incoming and outgoing URLs for threats, it may change the meeting join URLs and make the meeting unrecognizable by the Teams Rooms device.</span></span> <span data-ttu-id="e68d6-125">この問題が発生しないようにするには、サードパーティの会議サービスの Url を、ATP の安全なリンクの一覧またはサードパーティの URL リライト例外リストに追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e68d6-125">To make sure this doesn't happen, you need to add the third-party meeting service's URLs to the ATP Safe Links "do not rewrite" list or the third-party URL rewrite exception list.</span></span>

<span data-ttu-id="e68d6-126">ATP の安全なリンクの "書き換えない" リストにサードパーティの会議サービスの Url を追加するには、「 [atp の安全なリンクを使用して、上書き不可の url リストを設定](https://docs.microsoft.com/microsoft-365/security/office-365-security/set-up-a-custom-do-not-rewrite-urls-list-with-atp?view=o365-worldwide)する」の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="e68d6-126">To add third-party meeting service URLs to the ATP Safe Links "do not rewrite" list, follow the steps in [Set up a custom do-not-rewrite URLs list using ATP Safe Links](https://docs.microsoft.com/microsoft-365/security/office-365-security/set-up-a-custom-do-not-rewrite-urls-list-with-atp?view=o365-worldwide).</span></span> <span data-ttu-id="e68d6-127">サードパーティのソリューションを使用している場合は、そのソリューションの手順を参照して、URL リライト例外リストに Url を追加します。</span><span class="sxs-lookup"><span data-stu-id="e68d6-127">If you use a third-party solution, refer to the instructions for that solution to add URLs to its URL rewrite exception list.</span></span>

<span data-ttu-id="e68d6-128">ATP の安全なリンクに追加する必要があるエントリの例をいくつか紹介します。リストまたはサードパーティの URL リライト例外の一覧:</span><span class="sxs-lookup"><span data-stu-id="e68d6-128">Here are some example entries that you may need to add to your ATP Safe Links "do not rewrite" list or third-party URL rewrite exception list:</span></span>

- <span data-ttu-id="e68d6-129">**Cisco WebEx**`*.webex.com*`</span><span class="sxs-lookup"><span data-stu-id="e68d6-129">**Cisco WebEx** `*.webex.com*`</span></span>
- <span data-ttu-id="e68d6-130">**ズーム** `*zoom.us*` 、 `*zoom.com*``*zoomgov.com*`</span><span class="sxs-lookup"><span data-stu-id="e68d6-130">**Zoom** `*zoom.us*`, `*zoom.com*`, `*zoomgov.com*`</span></span>

<span data-ttu-id="e68d6-131">ATP の安全なリンクに追加する Url の完全なリストについては、「書き換えない」リストまたはサードパーティの URL リライト例外リストを使用して、会議の招待を承諾するサードパーティの会議サービスプロバイダーにお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="e68d6-131">For a complete list of URLs to add to your ATP Safe Links "do not rewrite" list or third-party URL rewrite exception list, contact the third-party meeting service provider you want to accept meeting invites from.</span></span> 

> [!CAUTION]
> <span data-ttu-id="e68d6-132">ATP の安全なリンクには、信頼できる Url のみを追加することができます。リストまたはサードパーティの URL リライト例外の一覧。</span><span class="sxs-lookup"><span data-stu-id="e68d6-132">Only add URLs that you trust to your ATP Safe Links "do not rewrite" list or third-party URL rewrite exception list.</span></span>

## <a name="step-3-enable-third-party-meetings-on-device"></a><span data-ttu-id="e68d6-133">手順 3: デバイスでサードパーティの会議を有効にする</span><span class="sxs-lookup"><span data-stu-id="e68d6-133">Step 3: Enable third-party meetings on device</span></span>

<span data-ttu-id="e68d6-134">最後の手順では、各チームルームデバイスがサードパーティの会議に参加できるようにします。</span><span class="sxs-lookup"><span data-stu-id="e68d6-134">The last step you need to do is allow each Teams Rooms device to join third-party meetings.</span></span> <span data-ttu-id="e68d6-135">サードパーティの会議に参加するには、ユーザー名とメールアドレスが必要です。</span><span class="sxs-lookup"><span data-stu-id="e68d6-135">Third-party meetings require a username and email address to join them.</span></span> <span data-ttu-id="e68d6-136">使用する必要があるユーザー名とメールアドレスがデバイスの会議室メールボックスと異なる場合は、デバイスに追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e68d6-136">If the username and email address that you need to use is different than the device's room mailbox, you need to add them to your device.</span></span> <span data-ttu-id="e68d6-137">これは、デバイスの設定または XML 構成ファイルで行うことができます。</span><span class="sxs-lookup"><span data-stu-id="e68d6-137">You can do this in the device settings or in the XML config file.</span></span>

### <a name="use-device-settings"></a><span data-ttu-id="e68d6-138">デバイスの設定を使う</span><span class="sxs-lookup"><span data-stu-id="e68d6-138">Use device settings</span></span>

<span data-ttu-id="e68d6-139">タッチスクリーンを使用して Teams 室のデバイスを構成するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="e68d6-139">To configure the Teams Rooms device using its touchscreen, do the following:</span></span>

1. <span data-ttu-id="e68d6-140">Microsoft Teams の会議室のデバイスで、[ **その他.** ..] を選択します。</span><span class="sxs-lookup"><span data-stu-id="e68d6-140">On the Microsoft Teams Rooms device, select **More ...**</span></span>
2. <span data-ttu-id="e68d6-141">[ **設定**] を選択し、デバイス管理者のユーザー名とパスワードを入力します。</span><span class="sxs-lookup"><span data-stu-id="e68d6-141">Select **Settings**, and then enter the device administrator username and password</span></span>
3. <span data-ttu-id="e68d6-142">[ **会議**   ] タブに移動し、[ **Cisco WebEx**]、[ **Zoom**<sup>1</sup>]、または [両方] を選びます。</span><span class="sxs-lookup"><span data-stu-id="e68d6-142">Go to the **Meetings** tab and select **Cisco WebEx**, **Zoom**<sup>1</sup>, or both</span></span>
4. <span data-ttu-id="e68d6-143">会議室のメールボックスに関連付けられたユーザー名とメールアドレスを使って会議に参加する場合は、[会議**室の情報を使用**して参加する] を選択します。</span><span class="sxs-lookup"><span data-stu-id="e68d6-143">If you want to join meetings with the username and email address associated with the room mailbox, select **Join with room info**</span></span>
5. <span data-ttu-id="e68d6-144">代替のユーザー名とメールアドレスを使って会議に参加する場合は、[ **ユーザー設定情報を使用** して参加する] を選択し、使用するユーザー名とメールアドレスを入力します。</span><span class="sxs-lookup"><span data-stu-id="e68d6-144">If you want to join meetings with an alternate username and email address, select **Join with custom info** and enter username and email address you'd like to use</span></span>
6. <span data-ttu-id="e68d6-145">[ **保存して終了**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="e68d6-145">Select **Save and exit**.</span></span> <span data-ttu-id="e68d6-146">デバイスが再起動します。</span><span class="sxs-lookup"><span data-stu-id="e68d6-146">Your device will restart.</span></span>

### <a name="use-the-skypesettingsxml-configuration-file"></a><span data-ttu-id="e68d6-147">SkypeSettings.xml 構成ファイルを使用する</span><span class="sxs-lookup"><span data-stu-id="e68d6-147">Use the SkypeSettings.xml configuration file</span></span>

<span data-ttu-id="e68d6-148">次の設定は、 `SkypeSettings.xml` にあるファイルに追加でき `C:\Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState` ます。</span><span class="sxs-lookup"><span data-stu-id="e68d6-148">The following settings can be added to the `SkypeSettings.xml` file located in `C:\Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState`.</span></span> <span data-ttu-id="e68d6-149">ファイルの詳細につい `SkypeSettings.xml` ては、「 [Microsoft Teams のコンソール設定を XML 構成ファイルを使ってリモートで管理する](xml-config-file.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e68d6-149">For more information about the `SkypeSettings.xml` file, see [Manage a Microsoft Teams Rooms console settings remotely with an XML configuration file](xml-config-file.md).</span></span>

<span data-ttu-id="e68d6-150">Cisco WebEx 会議を有効にするには、 `WebExMeetingsEnabled` 次のように XML 要素を **True**に設定します。</span><span class="sxs-lookup"><span data-stu-id="e68d6-150">To enable Cisco WebEx meetings, set the `WebExMeetingsEnabled` XML element to **True**, as follows.</span></span>

```xml
<WebExMeetingsEnabled>True</WebExMeetingsEnabled>
```

<span data-ttu-id="e68d6-151">ズーム<sup>1</sup> 会議を有効にするには、 `ZoomMeetingsEnabled` 次のように XML 要素を **True**に設定します。</span><span class="sxs-lookup"><span data-stu-id="e68d6-151">To enable Zoom<sup>1</sup> meetings, set the `ZoomMeetingsEnabled` XML element to **True**, as follows.</span></span>

```xml
<ZoomMeetingsEnabled>True</ZoomMeetingsEnabled>
```

<span data-ttu-id="e68d6-152">次の XML 要素を使用して、カスタムのユーザー名とメールアドレスを指定して、サードパーティの会議に参加することができます。</span><span class="sxs-lookup"><span data-stu-id="e68d6-152">You can optionally specify a custom username and email address to join third-party meetings using the following XML elements.</span></span> <span data-ttu-id="e68d6-153">指定した値が有効でない場合は、Teams room デバイスによって、[会議室] メールボックスのユーザー名とメールアドレスが既定で使用されます。</span><span class="sxs-lookup"><span data-stu-id="e68d6-153">If the values you provide aren't valid, the Teams Rooms device will default to use room mailbox username and email address.</span></span>

```xml
<UseCustomInfoForThirdPartyMeetings>true</UseCustomInfoForThirdPartyMeetings>

<CustomDisplayNameForThirdPartyMeetings>guestname</CustomDisplayNameForThirdPartyMeetings>

<CustomDisplayEmailForThirdPartyMeetings>guest@contoso.com</CustomDisplayEmailForThirdPartyMeetings>
```

> [!NOTE]
> <span data-ttu-id="e68d6-154">チームルームデバイスから Cisco WebEx 会議に参加するには、cisco WebEx web アプリケーションバージョン WBS 40.7 以降を使って、cisco の会議をホストする必要があります。</span><span class="sxs-lookup"><span data-stu-id="e68d6-154">To join Cisco WebEx meeting from a Teams Rooms device, the Cisco meeting needs to be hosted using Cisco WebEx web application version WBS 40.7 or later.</span></span>

<span data-ttu-id="e68d6-155"><sup>1</sup> ズーム会議の参加は、現在、テクノロジアクセスプログラムを通じて Microsoft Teams のルームのユーザーを選択する場合のみ利用できます (タップ)。</span><span class="sxs-lookup"><span data-stu-id="e68d6-155"><sup>1</sup> Zoom meetings join is currently only available to select Microsoft Teams Rooms customers through Technology Access Program (TAP).</span></span>
