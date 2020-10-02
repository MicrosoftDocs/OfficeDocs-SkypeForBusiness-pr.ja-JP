---
title: Microsoft Teams のリリース ノート
author: tonysmit
ms.author: tonysmit
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: ''
audience: admin
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
description: Microsoft Teams の管理者向け機能のリリースノート。
ms.openlocfilehash: 5e3abb22f3ac5e8cd830ea367ab259422d88e8a6
ms.sourcegitcommit: fd7d5ba09ef30cf4594e352c36f62b950e0e41a6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/02/2020
ms.locfileid: "48336996"
---
# <a name="release-notes-for-microsoft-teams-admin-features"></a><span data-ttu-id="94b21-103">Microsoft Teams の管理者向け機能のリリースノート</span><span class="sxs-lookup"><span data-stu-id="94b21-103">Release notes for Microsoft Teams admin features</span></span>

<span data-ttu-id="94b21-104">これらのリリースノートでは、Microsoft Teams の新しい管理機能について説明します。</span><span class="sxs-lookup"><span data-stu-id="94b21-104">These release notes provide information about new admin features for Microsoft Teams.</span></span>

## <a name="october-1-2020"></a><span data-ttu-id="94b21-105">2020年10月1日</span><span class="sxs-lookup"><span data-stu-id="94b21-105">October 1, 2020</span></span>

### <a name="view-app-permissions-and-grant-admin-consent-in-the-microsoft-teams-admin-center"></a><span data-ttu-id="94b21-106">Microsoft Teams 管理センターでアプリのアクセス許可を表示し、管理者の同意を与える</span><span class="sxs-lookup"><span data-stu-id="94b21-106">View app permissions and grant admin consent in the Microsoft Teams admin center</span></span>

<span data-ttu-id="94b21-107">チーム管理センターでは、グローバル管理者は、チームに保存されている情報の読み取り、またはユーザーの代理としてのメールの送信など、アプリが要求している権限について、Azure Active Directory に登録されている Graph API のアクセス許可に対する同意を確認して付与することができます。</span><span class="sxs-lookup"><span data-stu-id="94b21-107">Now in Teams admin center global admins will be able to review and grant consent to Graph API permissions registered in Azure Active Directory, on behalf of the entire tenant for the permissions an app is requesting such as reading information stored in a team or sending an email on behalf of users.</span></span> <span data-ttu-id="94b21-108">これで IT 管理者は、Teams 管理センター内のアプリのリソース固有の同意 (RSC) 権限を確認できるようになります。</span><span class="sxs-lookup"><span data-stu-id="94b21-108">Now IT admins will be able to review resource-specific consent (RSC) permissions for the apps within Teams admin center.</span></span> <span data-ttu-id="94b21-109">これにより、管理者は、組織で既に確認および承認されているサードパーティ製アプリのユーザーのブロックを解除できるようになります。</span><span class="sxs-lookup"><span data-stu-id="94b21-109">With that admins will be able to unblock their users for the third-party apps they have already reviewed and approved to use in their organization.</span></span> <span data-ttu-id="94b21-110">[詳細情報を参照してください](https://docs.microsoft.com/MicrosoftTeams/app-permissions-admin-center)。</span><span class="sxs-lookup"><span data-stu-id="94b21-110">[Learn more](https://docs.microsoft.com/MicrosoftTeams/app-permissions-admin-center).</span></span>
## <a name="september-29-2020"></a><span data-ttu-id="94b21-111">2020年9月29日</span><span class="sxs-lookup"><span data-stu-id="94b21-111">September 29, 2020</span></span>

### <a name="meeting-policy-settings"></a><span data-ttu-id="94b21-112">会議ポリシーの設定</span><span class="sxs-lookup"><span data-stu-id="94b21-112">Meeting policy settings</span></span>

<span data-ttu-id="94b21-113">Teams 会議ポリシーで IP オーディオと IP ビデオの2つのポリシー設定を追加する: ip オーディオと ip ビデオ用モードのモード。</span><span class="sxs-lookup"><span data-stu-id="94b21-113">Adding two policy settings for IP audio and IP video in Teams meetings policies: Mode for IP audio and Mode for IP video.</span></span> <span data-ttu-id="94b21-114">Teams 会議のポリシーで、着信と発信の IP オーディオと IP ビデオを設定できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="94b21-114">You can now set incoming and outgoing IP audio and IP video in Teams meeting policies.</span></span> <span data-ttu-id="94b21-115">[詳細情報を参照してください](../meeting-policies-in-teams.md#meeting-policy-settings---audio--video)。</span><span class="sxs-lookup"><span data-stu-id="94b21-115">[Learn more](../meeting-policies-in-teams.md#meeting-policy-settings---audio--video).</span></span>

## <a name="september-27-2020"></a><span data-ttu-id="94b21-116">2020年9月27日</span><span class="sxs-lookup"><span data-stu-id="94b21-116">September 27, 2020</span></span>

### <a name="simplified-notification-setting"></a><span data-ttu-id="94b21-117">簡単な通知設定</span><span class="sxs-lookup"><span data-stu-id="94b21-117">Simplified notification setting</span></span>

<span data-ttu-id="94b21-118">ユーザーは、強化された機能を使用して、より簡単な方法で通知設定を管理できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="94b21-118">Users can now manage their notifications settings in a more simplified manner with enhanced functionalities.</span></span>

## <a name="september-24-2020"></a><span data-ttu-id="94b21-119">2020年9月24日</span><span class="sxs-lookup"><span data-stu-id="94b21-119">September 24, 2020</span></span>

### <a name="teams-integration-with-android-contacts"></a><span data-ttu-id="94b21-120">Android の連絡先とのチームとの統合</span><span class="sxs-lookup"><span data-stu-id="94b21-120">Teams integration with Android contacts</span></span>

<span data-ttu-id="94b21-121">Android の電話帳から直接 Teams を使って通話を発信できます。</span><span class="sxs-lookup"><span data-stu-id="94b21-121">Call using Teams directly through your Android Phonebook.</span></span>

## <a name="september-21-2020"></a><span data-ttu-id="94b21-122">2020年9月21日</span><span class="sxs-lookup"><span data-stu-id="94b21-122">September 21, 2020</span></span>

### <a name="manage-microsoft-power-platform-apps-in-the-microsoft-teams-admin-center"></a><span data-ttu-id="94b21-123">Microsoft Teams 管理センターで Microsoft Power Platform アプリを管理する</span><span class="sxs-lookup"><span data-stu-id="94b21-123">Manage Microsoft Power Platform apps in the Microsoft Teams admin center</span></span>

<span data-ttu-id="94b21-124">管理者は、Teams の [アプリ] ページで、ユーザーが自分の同僚によって構築された Microsoft Power Platform アプリを表示してインストールできるかどうかを制御できます。</span><span class="sxs-lookup"><span data-stu-id="94b21-124">As an admin, you can control whether users can see and install Microsoft Power Platform apps in Built by your colleagues on the Apps page in Teams.</span></span> <span data-ttu-id="94b21-125">[ [アプリの管理](../manage-apps.md) ] ページの組織レベルで、または [アプリのアクセス許可ポリシー](../teams-app-permission-policies.md)を使用する特定のユーザーに対して、Power Apps または power Virtual agent で作成されたすべてのアプリを、一括ブロックまたは許可することができます。</span><span class="sxs-lookup"><span data-stu-id="94b21-125">You can collectively block or allow all apps created in Power Apps or all apps created in Power Virtual Agents at the org level on the [Manage apps](../manage-apps.md) page or for specific users using [app permission policies](../teams-app-permission-policies.md).</span></span> <span data-ttu-id="94b21-126">[詳細情報を参照してください](../manage-power-platform-apps.md)。</span><span class="sxs-lookup"><span data-stu-id="94b21-126">[Learn more](../manage-power-platform-apps.md).</span></span>

## <a name="september-19-2020"></a><span data-ttu-id="94b21-127">2020年9月19日</span><span class="sxs-lookup"><span data-stu-id="94b21-127">September 19, 2020</span></span>

### <a name="sharing-files-in-microsoft-teams"></a><span data-ttu-id="94b21-128">Microsoft Teams でのファイル共有</span><span class="sxs-lookup"><span data-stu-id="94b21-128">Sharing files in Microsoft Teams</span></span>

<span data-ttu-id="94b21-129">Microsoft Teams では、ユーザーは組織内外の他の Teams ユーザーとコンテンツを共有できます。</span><span class="sxs-lookup"><span data-stu-id="94b21-129">In Microsoft Teams, users can share content with other Teams users within and outside their organization.</span></span> <span data-ttu-id="94b21-130">Teams での共有は、SharePoint と OneDrive で構成されている設定に基づいているため、SharePoint と OneDrive のどちらを設定しても、Teams での共有が制御されます。</span><span class="sxs-lookup"><span data-stu-id="94b21-130">Sharing in Teams is based on the settings configured in SharePoint and OneDrive, so whatever you set up for SharePoint and OneDrive will control sharing in Teams as well.</span></span> <span data-ttu-id="94b21-131">[詳細情報を参照してください](https://docs.microsoft.com/MicrosoftTeams/sharing-files-in-teams)。</span><span class="sxs-lookup"><span data-stu-id="94b21-131">[Learn more](https://docs.microsoft.com/MicrosoftTeams/sharing-files-in-teams).</span></span>

## <a name="september-16-2020"></a><span data-ttu-id="94b21-132">2020年9月16日</span><span class="sxs-lookup"><span data-stu-id="94b21-132">September 16, 2020</span></span>

### <a name="new-third-party-video-provider-riverbed"></a><span data-ttu-id="94b21-133">サードパーティのビデオプロバイダの新製品</span><span class="sxs-lookup"><span data-stu-id="94b21-133">New third-party video provider Riverbed</span></span>

<span data-ttu-id="94b21-134">Teams のライブ イベント設定を使用して、組織で保持されているライブ イベントの設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="94b21-134">Use Teams live events settings to configure settings for live events that are held in your organization.</span></span> <span data-ttu-id="94b21-135">サポート URL を設定して、サード パーティ製のビデオ配信プロバイダーを設定できます。</span><span class="sxs-lookup"><span data-stu-id="94b21-135">You can set up a support URL and configure a third-party video distribution provider.</span></span> <span data-ttu-id="94b21-136">この設定は、組織で作成したすべてのライブ イベントに適用します。</span><span class="sxs-lookup"><span data-stu-id="94b21-136">These settings apply to all live events that are created in your organization.</span></span> <span data-ttu-id="94b21-137">Riverbed は、新しいサードパーティのプロバイダーです。</span><span class="sxs-lookup"><span data-stu-id="94b21-137">Riverbed is a new third-party provider.</span></span> <span data-ttu-id="94b21-138">[詳細情報を参照してください](https://docs.microsoft.com/microsoftteams/teams-live-events/configure-teams-live-events#configure-a-third-party-video-distribution-provider)。</span><span class="sxs-lookup"><span data-stu-id="94b21-138">[Learn more](https://docs.microsoft.com/microsoftteams/teams-live-events/configure-teams-live-events#configure-a-third-party-video-distribution-provider).</span></span>

## <a name="september-15-2020"></a><span data-ttu-id="94b21-139">2020年9月15日</span><span class="sxs-lookup"><span data-stu-id="94b21-139">September 15, 2020</span></span>

### <a name="skype-for-business-online-connector-integrated-to-teams-powershell-module"></a><span data-ttu-id="94b21-140">Teams PowerShell モジュールに統合された Skype for Business Online Connector</span><span class="sxs-lookup"><span data-stu-id="94b21-140">Skype for Business Online Connector integrated to Teams PowerShell module</span></span>

<span data-ttu-id="94b21-141">最新の Teams PowerShell パブリック リリースは Skype for Business Online コネクタと統合され、Teams PowerShell 管理用の単一モジュールを提供します。</span><span class="sxs-lookup"><span data-stu-id="94b21-141">The latest Teams PowerShell public release is integrated with Skype for Business Online Connector, providing a single module for Teams PowerShell management.</span></span> <span data-ttu-id="94b21-142">[詳細情報を参照してください](../teams-powershell-overview.md#manage-teams-with-powershell)。</span><span class="sxs-lookup"><span data-stu-id="94b21-142">[Learn more](../teams-powershell-overview.md#manage-teams-with-powershell).</span></span>

## <a name="september-8-2020"></a><span data-ttu-id="94b21-143">2020年9月8日</span><span class="sxs-lookup"><span data-stu-id="94b21-143">September 8, 2020</span></span>

### <a name="porting-pin"></a><span data-ttu-id="94b21-144">ピンの移植</span><span class="sxs-lookup"><span data-stu-id="94b21-144">Porting PIN</span></span>

<span data-ttu-id="94b21-145">電話番号の移植または転送に使用する PIN をセットアップして管理する機能が追加されました。</span><span class="sxs-lookup"><span data-stu-id="94b21-145">We added the ability to set up and manage a PIN used for porting or transferring phone numbers.</span></span> <span data-ttu-id="94b21-146">Microsoft からサービスプロバイダに番号を発信する場合は、PSTN サービスデスクにこの PIN を提供します。</span><span class="sxs-lookup"><span data-stu-id="94b21-146">You will provide this PIN to the PSTN service desk when you want to port numbers out to a service provider from Microsoft.</span></span> <span data-ttu-id="94b21-147">[詳細情報を参照してください](https://docs.microsoft.com/microsoftteams/phone-number-calling-plans/port-order-overview#can-i-port-out-my-numbers-from-teams-to-a-different-phone-service-provider-or-carrier)。</span><span class="sxs-lookup"><span data-stu-id="94b21-147">[Learn more](https://docs.microsoft.com/microsoftteams/phone-number-calling-plans/port-order-overview#can-i-port-out-my-numbers-from-teams-to-a-different-phone-service-provider-or-carrier).</span></span>

## <a name="september-3-2020"></a><span data-ttu-id="94b21-148">2020年9月3日</span><span class="sxs-lookup"><span data-stu-id="94b21-148">September 3, 2020</span></span>

### <a name="custom-apps-store-in-microsoft-teams"></a><span data-ttu-id="94b21-149">Microsoft Teams のカスタムアプリストア</span><span class="sxs-lookup"><span data-stu-id="94b21-149">Custom apps store in Microsoft Teams</span></span>

<span data-ttu-id="94b21-150">これで、ロゴ、カスタム背景、ユーザー設定のテキストの色を追加して、組織のブランドを持つ Teams アプリストアをカスタマイズして、エンドユーザーに招待することができます。</span><span class="sxs-lookup"><span data-stu-id="94b21-150">Now you can customize the Teams Apps store with your organizational branding by adding your logo, custom backgrounds, and custom text colors to make it more inviting to end users.</span></span> <span data-ttu-id="94b21-151">[詳細情報を参照してください](https://docs.microsoft.com/MicrosoftTeams/customize-your-app-store)。</span><span class="sxs-lookup"><span data-stu-id="94b21-151">[Learn more](https://docs.microsoft.com/MicrosoftTeams/customize-your-app-store).</span></span>

## <a name="september-1-2020"></a><span data-ttu-id="94b21-152">2020年9月1日</span><span class="sxs-lookup"><span data-stu-id="94b21-152">September 1, 2020</span></span>

### <a name="on-demand-translation-in-android"></a><span data-ttu-id="94b21-153">Android でのオンデマンド翻訳</span><span class="sxs-lookup"><span data-stu-id="94b21-153">On-demand translation in Android</span></span>

<span data-ttu-id="94b21-154">インラインメッセージの翻訳は、ユーザーがチームのメッセージを個人の言語設定で指定された言語に翻訳できる Microsoft Teams の機能です。</span><span class="sxs-lookup"><span data-stu-id="94b21-154">Inline message translation is a Microsoft Teams feature that lets users translate Teams messages into the language specified by their personal language settings.</span></span> <span data-ttu-id="94b21-155">翻訳設定は既定で **オンに** なっています。</span><span class="sxs-lookup"><span data-stu-id="94b21-155">The translation setting is **On** by default.</span></span> <span data-ttu-id="94b21-156">[詳細情報を参照してください](https://docs.microsoft.com/microsoftteams/inline-message-translation-teams)。</span><span class="sxs-lookup"><span data-stu-id="94b21-156">[Learn more](https://docs.microsoft.com/microsoftteams/inline-message-translation-teams).</span></span>

## <a name="august-17-2020"></a><span data-ttu-id="94b21-157">2020年8月17日</span><span class="sxs-lookup"><span data-stu-id="94b21-157">August 17, 2020</span></span>

### <a name="group-chat-size-increase"></a><span data-ttu-id="94b21-158">グループチャットのサイズの拡大</span><span class="sxs-lookup"><span data-stu-id="94b21-158">Group chat size increase</span></span>

<span data-ttu-id="94b21-159">グループチャットに250参加者を追加する機能が追加されました。</span><span class="sxs-lookup"><span data-stu-id="94b21-159">We added the ability to now have 250 participants in a group chat.</span></span> <span data-ttu-id="94b21-160">[詳細情報を参照してください](../limits-specifications-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="94b21-160">[Learn more](../limits-specifications-teams.md).</span></span>

### <a name="manage-the-praise-app"></a><span data-ttu-id="94b21-161">称賛アプリを管理する</span><span class="sxs-lookup"><span data-stu-id="94b21-161">Manage the Praise app</span></span>

<span data-ttu-id="94b21-162">Microsoft Teams の称賛アプリを使用すると、ユーザーは組織または教室のメンバーに対する感謝を示すことができます。</span><span class="sxs-lookup"><span data-stu-id="94b21-162">The Praise app in Microsoft Teams helps users show appreciation to members of their organization or classroom.</span></span> <span data-ttu-id="94b21-163">称賛アプリでは、選択できるバッジセットが選択されており、独自のバッジを作成するオプションが用意されています。</span><span class="sxs-lookup"><span data-stu-id="94b21-163">The Praise app has a selection of badge sets to choose from and provides the option to create your own badges.</span></span> <span data-ttu-id="94b21-164">称賛は、チームユーザーが担当するさまざまな作業について、教育者から Firstline 員まで、さまざまな作業を認識できるように設計されています。</span><span class="sxs-lookup"><span data-stu-id="94b21-164">Praise is designed to help recognize the effort that goes into the wide range of work that Teams users do, from educators to Firstline Workers.</span></span> <span data-ttu-id="94b21-165">[詳細情報を参照してください](../manage-praise-app.md)。</span><span class="sxs-lookup"><span data-stu-id="94b21-165">[Learn more](../manage-praise-app.md).</span></span>

### <a name="set-up-coordinated-meetings-with-microsoft-teams-rooms-and-surface-hub"></a><span data-ttu-id="94b21-166">Microsoft Teams のルームと Surface Hub でコーディネートされた会議をセットアップする</span><span class="sxs-lookup"><span data-stu-id="94b21-166">Set up Coordinated Meetings with Microsoft Teams Rooms and Surface Hub</span></span>

<span data-ttu-id="94b21-167">会議室に1つ以上の Microsoft Teams ルームデバイスまたは Surface Hub がある場合は、調和のとれた会議を設定することができます。</span><span class="sxs-lookup"><span data-stu-id="94b21-167">If you have one or more Microsoft Teams Rooms devices or Surface Hubs in a meeting room, you can set up Coordinated Meetings.</span></span> <span data-ttu-id="94b21-168">コーディネートされた会議では、チームルームデバイスと Surface Hub をセットアップして、1つのデバイスで会議に参加するときに、その他のデバイスも同じ会議に参加するようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="94b21-168">Coordinated Meetings lets you set up your Teams Rooms devices and Surface Hubs so that when you join a meeting on one device, the other devices in the room are also joined to the same meeting.</span></span> <span data-ttu-id="94b21-169">[詳細情報を参照してください](../rooms/coordinated-meetings.md)。</span><span class="sxs-lookup"><span data-stu-id="94b21-169">[Learn more](../rooms/coordinated-meetings.md).</span></span>

### <a name="tagging-by-shift"></a><span data-ttu-id="94b21-170">Shift でのタグ付け</span><span class="sxs-lookup"><span data-stu-id="94b21-170">Tagging by shift</span></span>

<span data-ttu-id="94b21-171">この機能を使用すると、チーム内のシフトアプリのスケジュールとシフトグループ名に一致するタグが自動的に割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="94b21-171">With this feature, people are automatically assigned tags that match their schedule and shift group name in the Shifts app in Teams.</span></span> <span data-ttu-id="94b21-172">[詳細情報を参照してください](../manage-tags.md)。</span><span class="sxs-lookup"><span data-stu-id="94b21-172">[Learn more](../manage-tags.md).</span></span>

## <a name="august-14-2020"></a><span data-ttu-id="94b21-173">2020年8月14日</span><span class="sxs-lookup"><span data-stu-id="94b21-173">August 14, 2020</span></span>

### <a name="cortana-voice-skills-in-teams"></a><span data-ttu-id="94b21-174">Teams での Cortana の音声スキル</span><span class="sxs-lookup"><span data-stu-id="94b21-174">Cortana voice skills in Teams</span></span>

<span data-ttu-id="94b21-175">Teams のモバイルアプリで Cortana の音声スキルを利用すれば、会話、コミュニケーション、共同作業などの作業を簡単に自然な言語で実行できるようになります。</span><span class="sxs-lookup"><span data-stu-id="94b21-175">Cortana voice skills in Teams mobile app help users perform meeting, communication, and collaboration tasks simply using spoken natural language.</span></span> <span data-ttu-id="94b21-176">ユーザーは、Teams アプリの [マイク] ボタンをクリックして、"通話 Megan" または "次の会議にメッセージを送信" のような要求を行うことができます。これには、仕事の最中や、外出先でも、他のユーザーと連絡を取る必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="94b21-176">Users can speak to Cortana by clicking on the microphone button in Teams app and make requests like “Call Megan” or “Send a message to my next meeting” if they need to connect with someone while juggling household chores or walking the dog or generally on the go.</span></span> <span data-ttu-id="94b21-177">ユーザーが会議に参加するには、"次の会議に参加する" というメッセージが表示されるか、または自分の予定表を確認します。</span><span class="sxs-lookup"><span data-stu-id="94b21-177">Users can join meetings simply by saying “Join my next meeting” or check their calendar by asking “what do I have this morning”.</span></span> <span data-ttu-id="94b21-178">会議または通話中に、会議ステージのオーバーフローメニューから Cortana を呼び出し、名前または番号でのユーザーの追加、デッキプレゼンテーション (「四半期のレビューデッキの開催」)、スライドへの移動などの一般的な会議のタスクを実行することができます (「付録のスライドに移動する」を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="94b21-178">Once in a meeting or a call, they can invoke Cortana from the overflow menu in the meeting stage and perform typical in-meeting tasks like adding people by name or number (“Add Megan to the call”), deck presentation (“present the quarterly review deck”) or navigating slides (“Go to the appendix slide”).</span></span> <span data-ttu-id="94b21-179">この機能でサポートされているその他の機能は、Teams アプリ内でのファイルの検索、共有、検索、移動です (「John とチャットを開く」の「私の未読アクティビティに移動する」を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="94b21-179">Other things that the feature supports are finding and sharing files, search, and navigating within the Teams app (“Open my chat with John, Go to my unread activity, Go to my mentions etc.).</span></span>

<span data-ttu-id="94b21-180">Teams の cortana は、 [オンラインサービス利用規約 (OST)](https://www.microsoft.com/licensing/product-licensing/products?rtc=1)に反映された、cortana enterprise サービスのエンタープライズレベルのプライバシー、セキュリティ、コンプライアンスに関する約束を満たしています。</span><span class="sxs-lookup"><span data-stu-id="94b21-180">Cortana in Teams meets the same enterprise-level privacy, security, and compliance promises for Cortana enterprise services, as reflected in the [Online Services Terms (OST)](https://www.microsoft.com/licensing/product-licensing/products?rtc=1).</span></span>

### <a name="teams-devices-administrator"></a><span data-ttu-id="94b21-181">Teams デバイス管理者</span><span class="sxs-lookup"><span data-stu-id="94b21-181">Teams Devices Administrator</span></span>

<span data-ttu-id="94b21-182">この役割を持つユーザーは、teams 管理センターからチームの認定済みデバイスを管理できます。</span><span class="sxs-lookup"><span data-stu-id="94b21-182">Users with this role can manage Teams certified devices from the Teams admin center.</span></span> <span data-ttu-id="94b21-183">サインインしたアカウントや、デバイスのメーカーとモデルなど、各デバイスの詳細情報を確認できます。</span><span class="sxs-lookup"><span data-stu-id="94b21-183">They can check details of each device including the account that is signed in, and the make and model of the device.</span></span> <span data-ttu-id="94b21-184">デバイスの設定を変更したり、ソフトウェアを更新したり、デバイスをリモートで再起動したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="94b21-184">They can change the settings on the device, update the software, and restart devices remotely.</span></span> <span data-ttu-id="94b21-185">[詳細情報を参照してください](../using-admin-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="94b21-185">[Learn more](../using-admin-roles.md).</span></span>

## <a name="august-12-2020"></a><span data-ttu-id="94b21-186">2020年8月12日</span><span class="sxs-lookup"><span data-stu-id="94b21-186">August 12, 2020</span></span>

### <a name="lists-app-in-teams"></a><span data-ttu-id="94b21-187">Teams でのアプリの一覧</span><span class="sxs-lookup"><span data-stu-id="94b21-187">Lists app in Teams</span></span>

<span data-ttu-id="94b21-188">Teams ユーザーは、[リスト] アプリタブを使って、リストの管理、作成、管理を直接行うことができるようになりました。リストアプリは、すべてのチームクライアントで動作し、リストアイテムに関する共同作業とコミュニケーションを可能にします。</span><span class="sxs-lookup"><span data-stu-id="94b21-188">Teams users can now directly manage, create, and maintain their lists using the Lists app tab. The Lists app works on all Teams clients and enables collaboration and communication around list items.</span></span> <span data-ttu-id="94b21-189">リストアプリの管理方法の詳細については、「 [組織のリストアプリを管理](https://docs.microsoft.com/MicrosoftTeams/manage-lists-app)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="94b21-189">For more information about how to manage the Lists apps, see [Manage the Lists app for your organization](https://docs.microsoft.com/MicrosoftTeams/manage-lists-app).</span></span>

## <a name="august-6-2020"></a><span data-ttu-id="94b21-190">2020年8月6日</span><span class="sxs-lookup"><span data-stu-id="94b21-190">August 6, 2020</span></span>

### <a name="approve-custom-apps"></a><span data-ttu-id="94b21-191">カスタムアプリを承認する</span><span class="sxs-lookup"><span data-stu-id="94b21-191">Approve custom apps</span></span>

<span data-ttu-id="94b21-192">Teams アプリ申請 API を通じて送信されたカスタムアプリを承認します。</span><span class="sxs-lookup"><span data-stu-id="94b21-192">Approve custom apps submitted through the Teams App Submission API.</span></span> <span data-ttu-id="94b21-193">[詳細情報を参照してください](../submit-approve-custom-apps.md)。</span><span class="sxs-lookup"><span data-stu-id="94b21-193">[Learn more](../submit-approve-custom-apps.md).</span></span>

## <a name="august-3-2020"></a><span data-ttu-id="94b21-194">2020年8月3日</span><span class="sxs-lookup"><span data-stu-id="94b21-194">August 3, 2020</span></span>

### <a name="purchase-services-for-teams-third-party-apps-in-the-microsoft-teams-admin-center"></a><span data-ttu-id="94b21-195">Microsoft Teams 管理センターでの Teams のサードパーティ製アプリの購入サービス</span><span class="sxs-lookup"><span data-stu-id="94b21-195">Purchase services for Teams third-party apps in the Microsoft Teams admin center</span></span>

<span data-ttu-id="94b21-196">Teams アプリは無料でインストールでき、アプリの完全な機能と範囲を体験するためにサービスの購入が必要になる場合もあります。</span><span class="sxs-lookup"><span data-stu-id="94b21-196">Teams apps are free to install and some may require purchasing service subscriptions to experience the app's full functionality and scope.</span></span> <span data-ttu-id="94b21-197">これらのサービス月額プランは、サービス (SaaS) オファーとして提供されます。これは、アプリソースと、Microsoft Teams 管理センターを通じて購入することができます。</span><span class="sxs-lookup"><span data-stu-id="94b21-197">These service subscriptions are called Software as a Service (SaaS) offers, which are available for purchase through AppSource and now through the Microsoft Teams admin center.</span></span> <span data-ttu-id="94b21-198">[詳細情報を参照してください](../purchase-third-party-apps.md)。</span><span class="sxs-lookup"><span data-stu-id="94b21-198">[Learn more](../purchase-third-party-apps.md).</span></span>

### <a name="publish-a-custom-app-submitted-through-the-teams-app-submission-api"></a><span data-ttu-id="94b21-199">Teams アプリ申請 API を通じて送信されたカスタムアプリを公開する</span><span class="sxs-lookup"><span data-stu-id="94b21-199">Publish a custom app submitted through the Teams App Submission API</span></span>

<span data-ttu-id="94b21-200">開発者は、Teams App submit API を使って、管理者がレビューおよび承認できるように、Microsoft Teams 管理センターにカスタムアプリを直接送信できます。</span><span class="sxs-lookup"><span data-stu-id="94b21-200">Developers can use the Teams App Submission API to submit custom apps directly to the Microsoft Teams admin center for admins to review and approve.</span></span> <span data-ttu-id="94b21-201">[詳細情報を参照してください](https://docs.microsoft.com/microsoftteams/submit-approve-custom-apps)。</span><span class="sxs-lookup"><span data-stu-id="94b21-201">[Learn more](https://docs.microsoft.com/microsoftteams/submit-approve-custom-apps).</span></span>

## <a name="july-31-2020"></a><span data-ttu-id="94b21-202">2020年7月31日</span><span class="sxs-lookup"><span data-stu-id="94b21-202">July 31, 2020</span></span>

### <a name="admins-can-configure-shift-based-presence-on-shift-off-shift-for-their-firstline-workers"></a><span data-ttu-id="94b21-203">管理者は、Firstline Worker のシフトベースのプレゼンス (シフトの場合はシフト) を構成できます。</span><span class="sxs-lookup"><span data-stu-id="94b21-203">Admins can configure shift-based presence (On shift, Off shift) for their Firstline Workers</span></span>

<span data-ttu-id="94b21-204">管理者は、シフトベースのプレゼンス状態を使用するように firstline ワーカーを構成できます。シフト、取り込み中 (シフト中は切り替え可能)、shift キーをオフにすることができます。</span><span class="sxs-lookup"><span data-stu-id="94b21-204">Admins can configure their firstline workers to have shift-based presence states: On shift, Busy (can be toggled when on shift), and Off shift.</span></span>

## <a name="july-29-2020"></a><span data-ttu-id="94b21-205">2020年7月29日</span><span class="sxs-lookup"><span data-stu-id="94b21-205">July 29, 2020</span></span>

### <a name="enhanced-manageability-using-device-tagging-functionality"></a><span data-ttu-id="94b21-206">デバイスタグ機能を使用した管理性の向上</span><span class="sxs-lookup"><span data-stu-id="94b21-206">Enhanced Manageability using Device Tagging functionality</span></span>

<span data-ttu-id="94b21-207">管理性の向上の一環として、デバイスタグ機能をリリースしています。</span><span class="sxs-lookup"><span data-stu-id="94b21-207">As part of enhanced manageability, we are releasing Device Tagging functionality.</span></span> <span data-ttu-id="94b21-208">これにより、IT 管理者は、ユーザーによって生成されたタグを持つグループ固有のデバイスのセットに対して、同じ操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="94b21-208">It will enable IT admins to group-specific set of devices with user-generated Tags and perform actions on the same.</span></span> <span data-ttu-id="94b21-209">[詳細情報を参照してください](/../../manage-device-tags.md)。</span><span class="sxs-lookup"><span data-stu-id="94b21-209">[Learn more](/../../manage-device-tags.md).</span></span>

### <a name="view-only-in-meetings"></a><span data-ttu-id="94b21-210">会議でのみ表示する</span><span class="sxs-lookup"><span data-stu-id="94b21-210">View-only in meetings</span></span>

<span data-ttu-id="94b21-211">[表示のみ] では、2万のリッスン専用参加者が、上級通信アドオン SKU のライセンスを持っている会議に参加することができます。1これは、プレビュー版または初期リリースの機能です。</span><span class="sxs-lookup"><span data-stu-id="94b21-211">View-only allows for up to 20,000 listen-only participants to join a meeting in which the organizer has a license for the Advanced Communications add-on SKU.1 This is a preview or early release feature.</span></span> [<span data-ttu-id="94b21-212">詳細情報</span><span class="sxs-lookup"><span data-stu-id="94b21-212">Learn more</span></span>](https://docs.microsoft.com/MicrosoftTeams/limits-specifications-teams-preview#meetings-and-calls)

## <a name="july-28-2020"></a><span data-ttu-id="94b21-213">2020年7月28日</span><span class="sxs-lookup"><span data-stu-id="94b21-213">July 28, 2020</span></span>

### <a name="create-your-own-teams-template"></a><span data-ttu-id="94b21-214">独自のチームテンプレートを作成する</span><span class="sxs-lookup"><span data-stu-id="94b21-214">Create your own Teams template</span></span>

<span data-ttu-id="94b21-215">管理コンソールからテンプレートを使用して、独自のチームテンプレートを作成したり、既存のテンプレートから Teams テンプレートを作成したりできるようになりました。</span><span class="sxs-lookup"><span data-stu-id="94b21-215">You can now use templates from the Admin console to create your own Teams template or create a Teams template from existing templates.</span></span> <span data-ttu-id="94b21-216">[詳細情報を参照してください](../get-started-with-teams-templates-in-the-admin-console.md)。</span><span class="sxs-lookup"><span data-stu-id="94b21-216">[Learn more](../get-started-with-teams-templates-in-the-admin-console.md).</span></span>

## <a name="july-20-2020"></a><span data-ttu-id="94b21-217">2020年7月20日</span><span class="sxs-lookup"><span data-stu-id="94b21-217">July 20, 2020</span></span>

### <a name="admins-can-control-outgoing-webhooks-at-the-user-level"></a><span data-ttu-id="94b21-218">管理者は、発信 web フックをユーザーレベルで制御できます。</span><span class="sxs-lookup"><span data-stu-id="94b21-218">Admins can control outgoing webhooks at the user level</span></span>

<span data-ttu-id="94b21-219">管理者は、アプリのアクセス許可ポリシーで送信 Web フックアプリを許可またはブロックすることにより、ユーザーレベルで送信 web フックを制御できます。</span><span class="sxs-lookup"><span data-stu-id="94b21-219">Admins can control outgoing webhooks at the user level by allowing or blocking the Outgoing Webhooks app in app permission policies.</span></span> <span data-ttu-id="94b21-220">[詳細情報を参照してください](../manage-apps.md)。</span><span class="sxs-lookup"><span data-stu-id="94b21-220">[Learn more](../manage-apps.md).</span></span>

## <a name="july-17-2020"></a><span data-ttu-id="94b21-221">2020年7月17日</span><span class="sxs-lookup"><span data-stu-id="94b21-221">July 17, 2020</span></span>

### <a name="ndi-out-for-teams-meetings"></a><span data-ttu-id="94b21-222">Teams 会議用の NDI</span><span class="sxs-lookup"><span data-stu-id="94b21-222">NDI-out for Teams meetings</span></span>

<span data-ttu-id="94b21-223">チーム会議への NDI を有効にする機能が追加されました。</span><span class="sxs-lookup"><span data-stu-id="94b21-223">We added the ability to enable NDI-Out to a Teams meeting.</span></span> <span data-ttu-id="94b21-224">NDI Out は、会議の音声とビデオをビデオ製造ツールで利用できるようにすることを可能にします。</span><span class="sxs-lookup"><span data-stu-id="94b21-224">NDI-Out allows for the audio and video of a meeting to be utilized by video production tools.</span></span> <span data-ttu-id="94b21-225">[詳細情報を参照してください](../use-ndi-in-meetings.md)。</span><span class="sxs-lookup"><span data-stu-id="94b21-225">[Learn more](../use-ndi-in-meetings.md).</span></span>

## <a name="july-15-2020"></a><span data-ttu-id="94b21-226">2020年7月15日</span><span class="sxs-lookup"><span data-stu-id="94b21-226">July 15, 2020</span></span>

### <a name="enable-suggested-replies"></a><span data-ttu-id="94b21-227">返信の候補を有効にする</span><span class="sxs-lookup"><span data-stu-id="94b21-227">Enable suggested replies</span></span>

<span data-ttu-id="94b21-228">チャットメッセージの返信の候補を有効にするには、この設定をオンにします。</span><span class="sxs-lookup"><span data-stu-id="94b21-228">Turn this setting on to enable suggested replies for chat messages.</span></span> [<span data-ttu-id="94b21-229">詳細情報</span><span class="sxs-lookup"><span data-stu-id="94b21-229">Learn more</span></span>](../messaging-policies-in-teams.md)

## <a name="july-9-2020"></a><span data-ttu-id="94b21-230">2020年7月9日</span><span class="sxs-lookup"><span data-stu-id="94b21-230">July 9, 2020</span></span>

### <a name="voicemail-support-in-call-queues"></a><span data-ttu-id="94b21-231">通話キューでのボイスメールのサポート</span><span class="sxs-lookup"><span data-stu-id="94b21-231">Voicemail support in call queues</span></span>

<span data-ttu-id="94b21-232">共有ボイスメールボックスを使用するために、通話キューのサポートを追加しました。</span><span class="sxs-lookup"><span data-stu-id="94b21-232">We added support for call queues to use a shared voicemail box.</span></span> <span data-ttu-id="94b21-233">[詳細情報を参照してください](../create-a-phone-system-call-queue.md)。</span><span class="sxs-lookup"><span data-stu-id="94b21-233">[Learn more](../create-a-phone-system-call-queue.md).</span></span>

## <a name="july-8-2020"></a><span data-ttu-id="94b21-234">2020年7月8日</span><span class="sxs-lookup"><span data-stu-id="94b21-234">July 8, 2020</span></span>

### <a name="policy-packaging-batch-assignment"></a><span data-ttu-id="94b21-235">ポリシーパッケージのバッチ割り当て</span><span class="sxs-lookup"><span data-stu-id="94b21-235">Policy packaging batch assignment</span></span>

<span data-ttu-id="94b21-236">PowerShell を使用して、ユーザーとグループのポリシーパッケージを割り当てることができました。</span><span class="sxs-lookup"><span data-stu-id="94b21-236">We made it possible to use PowerShell to batch assign a Policy Package for user and groups.</span></span>

## <a name="july-7-2020"></a><span data-ttu-id="94b21-237">2020年7月7日</span><span class="sxs-lookup"><span data-stu-id="94b21-237">July 7, 2020</span></span>

### <a name="sensitivity-labels-for-teams"></a><span data-ttu-id="94b21-238">Teams の機密度ラベル</span><span class="sxs-lookup"><span data-stu-id="94b21-238">Sensitivity labels for Teams</span></span>

<span data-ttu-id="94b21-239">機密ラベルを使用すると、チームの管理者はチーム内で共同作業を行って作成された機密組織のコンテンツへのアクセスを規制できます。</span><span class="sxs-lookup"><span data-stu-id="94b21-239">Sensitivity labels allow Teams admins to regulate access to sensitive organizational content created during collaboration within teams.</span></span> <span data-ttu-id="94b21-240">[詳細情報を参照してください](../sensitivity-labels.md)。</span><span class="sxs-lookup"><span data-stu-id="94b21-240">[Learn more](../sensitivity-labels.md).</span></span>

## <a name="july-2-2020"></a><span data-ttu-id="94b21-241">2020年7月2日</span><span class="sxs-lookup"><span data-stu-id="94b21-241">July 2, 2020</span></span>

### <a name="suggested-replies"></a><span data-ttu-id="94b21-242">返信の候補</span><span class="sxs-lookup"><span data-stu-id="94b21-242">Suggested replies</span></span>

<span data-ttu-id="94b21-243">チームユーザーが自分の会話に対して提案された返信を持つ機能を追加しました。</span><span class="sxs-lookup"><span data-stu-id="94b21-243">We added the ability for Teams users to have a suggested reply to their conversations.</span></span> <span data-ttu-id="94b21-244">この候補は、チャットメッセージが有効になっている場合に、そのメッセージの下部に表示されます。</span><span class="sxs-lookup"><span data-stu-id="94b21-244">These suggestions will appear at the bottom of a chat message if they are enabled.</span></span> <span data-ttu-id="94b21-245">メッセージにすばやく簡単に返信することができます。</span><span class="sxs-lookup"><span data-stu-id="94b21-245">They make replying to messages quick and easy!</span></span> <span data-ttu-id="94b21-246">[詳細情報を参照してください](../messaging-policies-in-teams.md#messaging-policy-settings)。</span><span class="sxs-lookup"><span data-stu-id="94b21-246">[Learn more](../messaging-policies-in-teams.md#messaging-policy-settings).</span></span>

### <a name="transferring-incoming-calls"></a><span data-ttu-id="94b21-247">着信通話の転送</span><span class="sxs-lookup"><span data-stu-id="94b21-247">Transferring incoming calls</span></span>

<span data-ttu-id="94b21-248">自動応答と通話キューの着信通話を外部 PSTN 電話番号に転送する機能が追加されました。</span><span class="sxs-lookup"><span data-stu-id="94b21-248">We added the ability for auto attendants and call queue incoming calls to be transferred to an external PSTN phone number.</span></span>  <span data-ttu-id="94b21-249">[詳細情報を参照してください](../business-voice/set-up-auto-attendants.md)。</span><span class="sxs-lookup"><span data-stu-id="94b21-249">[Learn more](../business-voice/set-up-auto-attendants.md).</span></span>

## <a name="june-30-2020"></a><span data-ttu-id="94b21-250">2020年6月30日</span><span class="sxs-lookup"><span data-stu-id="94b21-250">June 30, 2020</span></span>

### <a name="install-apps-on-behalf-of-others"></a><span data-ttu-id="94b21-251">他のユーザーの代わりにアプリをインストールする</span><span class="sxs-lookup"><span data-stu-id="94b21-251">Install apps on behalf of others</span></span>

<span data-ttu-id="94b21-252">ユーザーが Teams を起動したときに既定でインストールされるアプリを選択します。</span><span class="sxs-lookup"><span data-stu-id="94b21-252">You choose which apps are installed by default for users when they start Teams.</span></span> <span data-ttu-id="94b21-253">[詳細情報を参照してください](../teams-app-setup-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="94b21-253">[Learn more](../teams-app-setup-policies.md).</span></span>

### <a name="screen-sharing-on-behalf-of-others"></a><span data-ttu-id="94b21-254">他のユーザーの代わりに表示される画面共有</span><span class="sxs-lookup"><span data-stu-id="94b21-254">Screen sharing on behalf of others</span></span>

<span data-ttu-id="94b21-255">多くの IT 管理者は、AllowPrivateCalling ポリシーを無効にするときに、チャットから従業員の画面共有を行うことができないと訴えています。</span><span class="sxs-lookup"><span data-stu-id="94b21-255">Many IT Admins have complained that they can't have their employees screen share from chat when they disable the AllowPrivateCalling policy.</span></span> <span data-ttu-id="94b21-256">この機能は、AllowPrivateCalling ポリシーからのチャットから画面を開始する機能を分離していますが、AllowPrivateCalling のポリシーが無効になっている場合は、ユーザーが音声/ビデオを画面共有セッションに追加するのをブロックします。</span><span class="sxs-lookup"><span data-stu-id="94b21-256">This feature work has decoupled the ability to start a screens hare from chat from the AllowPrivateCalling policy, but it still blocks users from adding audio/video to the screen share session if their AllowPrivateCalling policy is disabled.</span></span>

## <a name="june-29-2020"></a><span data-ttu-id="94b21-257">2020年6月29日</span><span class="sxs-lookup"><span data-stu-id="94b21-257">June 29, 2020</span></span>

### <a name="walkie-talkie-app-in-microsoft-teams"></a><span data-ttu-id="94b21-258">Microsoft Teams での ie トランシーバーアプリの解説</span><span class="sxs-lookup"><span data-stu-id="94b21-258">Walkie Talkie app in Microsoft Teams</span></span>

<span data-ttu-id="94b21-259">プッシュツートークを使ったインスタント音声通信。</span><span class="sxs-lookup"><span data-stu-id="94b21-259">Instant voice communication using push-to-talk.</span></span>

## <a name="june-25-2020"></a><span data-ttu-id="94b21-260">2020年6月25日</span><span class="sxs-lookup"><span data-stu-id="94b21-260">June 25, 2020</span></span>

### <a name="teams-filter-option"></a><span data-ttu-id="94b21-261">Teams のフィルターオプション</span><span class="sxs-lookup"><span data-stu-id="94b21-261">Teams filter option</span></span>

<span data-ttu-id="94b21-262">コマンドバーに新しいフィルターオプションを追加して、特定のチームを検索するときに特定のパラメーターを設定できるようにしました。</span><span class="sxs-lookup"><span data-stu-id="94b21-262">We added a new filter option in the command bar so you can set specific parameters when searching for specific teams.</span></span>

### <a name="users-widgets"></a><span data-ttu-id="94b21-263">ユーザーウィジェット</span><span class="sxs-lookup"><span data-stu-id="94b21-263">Users widgets</span></span>

<span data-ttu-id="94b21-264">チームおよびチャネルを追加するときに使用できる新しいユーザーの概要ウィジェットを追加しました。</span><span class="sxs-lookup"><span data-stu-id="94b21-264">We added a new User summary widget that's available when you're adding teams and channels.</span></span>

## <a name="june-21-2020"></a><span data-ttu-id="94b21-265">2020年6月21日</span><span class="sxs-lookup"><span data-stu-id="94b21-265">June 21, 2020</span></span>

### <a name="sign-in-restrictions-for-android-and-ios-users"></a><span data-ttu-id="94b21-266">Android および iOS ユーザー向けのサインイン制限</span><span class="sxs-lookup"><span data-stu-id="94b21-266">Sign in restrictions for Android and iOS users</span></span>

<span data-ttu-id="94b21-267">ユーザーが Microsoft 365 アカウントにサインインしていない場合は、組織でのモバイルサインインポリシーの設定に応じて、単一要素認証または多要素認証 (SFA または MFA) を提供するように求められます。</span><span class="sxs-lookup"><span data-stu-id="94b21-267">If user isn't signed in to their Microsoft 365 account anywhere else, they'll be asked to provide single-factor or multi-factor authentication (SFA or MFA), depending on what your organization has configured for mobile sign-in policies.</span></span> <span data-ttu-id="94b21-268">[詳細情報を参照してください](../sign-in-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="94b21-268">[Learn more](../sign-in-teams.md).</span></span>

## <a name="june-15-2020"></a><span data-ttu-id="94b21-269">2020年6月15日</span><span class="sxs-lookup"><span data-stu-id="94b21-269">June 15, 2020</span></span>

### <a name="monitor-shifts-with-audit-logs"></a><span data-ttu-id="94b21-270">監査ログでシフトを監視する</span><span class="sxs-lookup"><span data-stu-id="94b21-270">Monitor shifts with audit logs</span></span>

<span data-ttu-id="94b21-271">監査ログを検索して、組織内のシフトアクティビティを表示できます。</span><span class="sxs-lookup"><span data-stu-id="94b21-271">You can search the audit log to view Shifts activity in your organization.</span></span> <span data-ttu-id="94b21-272">[詳細情報](<https://docs.microsoft.com/microsoftteams/audit-log-events>.</span><span class="sxs-lookup"><span data-stu-id="94b21-272">[Learn more](<https://docs.microsoft.com/microsoftteams/audit-log-events>.</span></span>

## <a name="june-11-2020"></a><span data-ttu-id="94b21-273">2020年6月11日</span><span class="sxs-lookup"><span data-stu-id="94b21-273">June 11, 2020</span></span>

### <a name="call-queues---presence-based-routing"></a><span data-ttu-id="94b21-274">通話キュー-プレゼンスベースのルーティング</span><span class="sxs-lookup"><span data-stu-id="94b21-274">Call queues - Presence-based routing</span></span>

<span data-ttu-id="94b21-275">オフにすると、ログイン状態に関係なく通話を受信するように設定したエージェントに、通話がルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="94b21-275">When turned off, calls will be routed to agents who have opted in to receive calls, regardless of their presence state.</span></span> <span data-ttu-id="94b21-276">オンにした場合、オプトインされたエージェントは、プレゼンス状態が利用可能な場合にのみ、通話を受信します。</span><span class="sxs-lookup"><span data-stu-id="94b21-276">When turned on, opted-in agents will receive calls only when their presence state is Available.</span></span> <span data-ttu-id="94b21-277">[詳細情報を参照してください](../create-a-phone-system-call-queue.md)。</span><span class="sxs-lookup"><span data-stu-id="94b21-277">[Learn more](../create-a-phone-system-call-queue.md).</span></span>

## <a name="june-10-2020"></a><span data-ttu-id="94b21-278">2020年6月10日</span><span class="sxs-lookup"><span data-stu-id="94b21-278">June 10, 2020</span></span>

### <a name="call-queues---longest-idle-routing"></a><span data-ttu-id="94b21-279">通話キュー-最長アイドルルーティング</span><span class="sxs-lookup"><span data-stu-id="94b21-279">Call queues - Longest-idle routing</span></span>

<span data-ttu-id="94b21-280">このオプションを選ぶと、最長時間の間、着信に応答していない通話エージェントに着信が転送されます。</span><span class="sxs-lookup"><span data-stu-id="94b21-280">When you choose this, incoming calls will be routed to call agents who haven't answered an incoming call for the longest period of time.</span></span> <span data-ttu-id="94b21-281">[詳細情報を参照してください](../create-a-phone-system-call-queue.md)。</span><span class="sxs-lookup"><span data-stu-id="94b21-281">[Learn more](../create-a-phone-system-call-queue.md).</span></span>

## <a name="june-1-2020"></a><span data-ttu-id="94b21-282">2020年6月1日</span><span class="sxs-lookup"><span data-stu-id="94b21-282">June 1, 2020</span></span>

### <a name="raise-hand-in-meetings"></a><span data-ttu-id="94b21-283">会議で手を上げる</span><span class="sxs-lookup"><span data-stu-id="94b21-283">Raise hand in meetings</span></span>

<span data-ttu-id="94b21-284">ユーザーが会議で仮想手を上げることができるようになりました。</span><span class="sxs-lookup"><span data-stu-id="94b21-284">Users can now raise a virtual hand in a meeting!</span></span> <span data-ttu-id="94b21-285">他の参加者には、会議ステージの自分の名前の横にある、または名簿で自分の名前の横に、発生した針が表示されます。</span><span class="sxs-lookup"><span data-stu-id="94b21-285">Other participants will see your raised hand next to your name in the meeting stage and next to your name in the roster.</span></span> <span data-ttu-id="94b21-286">[詳細情報を参照してください](../raise-hand-meetings.md)。</span><span class="sxs-lookup"><span data-stu-id="94b21-286">[Learn more](../raise-hand-meetings.md).</span></span>

## <a name="may-15-2020"></a><span data-ttu-id="94b21-287">2020年5月15</span><span class="sxs-lookup"><span data-stu-id="94b21-287">May 15, 2020</span></span>

### <a name="add-more-people-to-a-chat"></a><span data-ttu-id="94b21-288">チャットに他のユーザーを追加する</span><span class="sxs-lookup"><span data-stu-id="94b21-288">Add more people to a chat</span></span>

<span data-ttu-id="94b21-289">1つのチャットスレッドに最大350人のユーザーを追加できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="94b21-289">We made it possible to now add up to 350 people to a single chat thread.</span></span>

## <a name="may-5-2020"></a><span data-ttu-id="94b21-290">2020年5月5日</span><span class="sxs-lookup"><span data-stu-id="94b21-290">May 5, 2020</span></span>

### <a name="easily-access-meeting-options-from-within-a-teams-meeting-in-progress"></a><span data-ttu-id="94b21-291">進行中の Teams 会議内から会議オプションに簡単にアクセスする</span><span class="sxs-lookup"><span data-stu-id="94b21-291">Easily access meeting options from within a Teams meeting in progress</span></span>

<span data-ttu-id="94b21-292">会議の開催者は、[参加者] ウィンドウで簡単にアクセスできるリンクを提供して、会議の開催者が発表者とロビーの設定をすばやく簡単に変更できるようにしています。</span><span class="sxs-lookup"><span data-stu-id="94b21-292">We're making it easier for meeting organizers to quickly and easily change their presenter and lobby settings once a Teams meeting starts by providing an easy to access link directly in the participants pane.</span></span> <span data-ttu-id="94b21-293">この新機能は、スケジュールされた会議と "今すぐミーティング" の両方の会議に表示されます。</span><span class="sxs-lookup"><span data-stu-id="94b21-293">This new functionality will be present for both scheduled and “Meet now” meetings.</span></span>

### <a name="download-a-participant-report-in-a-teams-meeting"></a><span data-ttu-id="94b21-294">Teams 会議で参加者レポートをダウンロードする</span><span class="sxs-lookup"><span data-stu-id="94b21-294">Download a participant report in a Teams meeting</span></span>

<span data-ttu-id="94b21-295">会議の開催者、特に教師は、チーム会議に参加したユーザーを知っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="94b21-295">Meeting organizers, especially teachers, often need to know who joined their Teams meetings.</span></span> <span data-ttu-id="94b21-296">間もなく参加者への参加と休暇を含む、リストビューに表示された参加者レポートをダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="94b21-296">Soon you will be able to download a participant report, found in the roster view that includes join and leave times for participants.</span></span> <span data-ttu-id="94b21-297">[リスト] ビューでは、会議の開催者は開催者の表示中に参加したユーザーを含むレポートをダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="94b21-297">Available in the roster view, meeting organizers can download the report that includes those users who joined while the organizer was present.</span></span> <span data-ttu-id="94b21-298">この機能は、会議がアクティブな間のみ会議で使用できます。</span><span class="sxs-lookup"><span data-stu-id="94b21-298">This feature is only available within the meeting while the meeting is active.</span></span> <span data-ttu-id="94b21-299">デスクトップ (Windows と Mac) と web で利用できます。</span><span class="sxs-lookup"><span data-stu-id="94b21-299">Available on desktop (Windows and Mac) and the web.</span></span> <span data-ttu-id="94b21-300">[詳細情報を参照してください](../teams-analytics-and-reports/meeting-attendance-report.md)。</span><span class="sxs-lookup"><span data-stu-id="94b21-300">[Learn more](../teams-analytics-and-reports/meeting-attendance-report.md).</span></span>

## <a name="april-26-2020"></a><span data-ttu-id="94b21-301">2020年4月26日</span><span class="sxs-lookup"><span data-stu-id="94b21-301">April 26, 2020</span></span>

### <a name="include-system-audio-in-live-events"></a><span data-ttu-id="94b21-302">ライブイベントにシステムオーディオを含める</span><span class="sxs-lookup"><span data-stu-id="94b21-302">Include system audio in live events</span></span>

<span data-ttu-id="94b21-303">ライブイベントの発表者とプロデューサーは、ライブイベント中にデスクトップまたはウィンドウ画面を共有するときに、システムオーディオを含めることができるようになりました。</span><span class="sxs-lookup"><span data-stu-id="94b21-303">Presenters and producers in live events can now include system audio when sharing a desktop or window screen during the live event.</span></span> <span data-ttu-id="94b21-304">これにより、ユーザーは共有しているコンテンツのオーディオ部分を音声で聞くことができます。</span><span class="sxs-lookup"><span data-stu-id="94b21-304">This will allow your users to hear any audio part of the content you are sharing.</span></span>

## <a name="april-24-2020"></a><span data-ttu-id="94b21-305">2020年4月24日</span><span class="sxs-lookup"><span data-stu-id="94b21-305">April 24, 2020</span></span>

### <a name="team-and-channel-analytics"></a><span data-ttu-id="94b21-306">チームとチャネルの分析</span><span class="sxs-lookup"><span data-stu-id="94b21-306">Team and channel analytics</span></span>

<span data-ttu-id="94b21-307">また、チームの分析に加えて、チャネルレベルのメトリックと分析を表示することもできます。</span><span class="sxs-lookup"><span data-stu-id="94b21-307">In addition to team analytics, now you can also view channel level metrics and insights.</span></span> <span data-ttu-id="94b21-308">また、期間が90日に拡張され、長期間のデータ分析が可能になりました。</span><span class="sxs-lookup"><span data-stu-id="94b21-308">We've also enhanced the time period to 90 days so you can analyze data for longer periods.</span></span> <span data-ttu-id="94b21-309">このリリースには、チームまたはチャネルの投稿、返信、会議の数に関する新しい指標とグラフも含まれています。</span><span class="sxs-lookup"><span data-stu-id="94b21-309">Apart from that, this release also includes new metrics and charts around the count of posts, replies, and meetings for a team or channel.</span></span> <span data-ttu-id="94b21-310">[詳細情報を参照してください](../teams-analytics-and-reports/view-analytics.md)。</span><span class="sxs-lookup"><span data-stu-id="94b21-310">[Learn more](../teams-analytics-and-reports/view-analytics.md).</span></span>

## <a name="april-20-2020"></a><span data-ttu-id="94b21-311">2020年4月20日</span><span class="sxs-lookup"><span data-stu-id="94b21-311">April 20, 2020</span></span>

### <a name="enable-organizers-to-change-lobby-settings-for-dial-in-participants"></a><span data-ttu-id="94b21-312">開催者がダイヤルイン参加者のロビー設定を変更できるようにする</span><span class="sxs-lookup"><span data-stu-id="94b21-312">Enable organizers to change lobby settings for dial-in participants</span></span>

<span data-ttu-id="94b21-313">この設定では、スマートフォンでダイヤル インするユーザーが会議に直接参加するのか、[**ユーザーの参加を自動的に許可する**] の設定に関わらずロビーで待機するのかを制御します。</span><span class="sxs-lookup"><span data-stu-id="94b21-313">This setting controls whether people who dial in by phone join the meeting directly or wait in the lobby regardless of the **Automatically admit people** setting.</span></span>

## <a name="april-8-2020"></a><span data-ttu-id="94b21-314">2020年4月8日</span><span class="sxs-lookup"><span data-stu-id="94b21-314">April 8, 2020</span></span>

### <a name="customize-meeting-video-backgrounds"></a><span data-ttu-id="94b21-315">会議のビデオの背景をカスタマイズする</span><span class="sxs-lookup"><span data-stu-id="94b21-315">Customize meeting video backgrounds</span></span>

<span data-ttu-id="94b21-316">ビデオを使って会議しているときに、使用する静的な背景画像を選択できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="94b21-316">When you are meeting with video, you now have the choice of different static background images to use.</span></span> <span data-ttu-id="94b21-317">これにより、この画像が表示され、実際の操作を行っているときの背景として表示されなくなります。</span><span class="sxs-lookup"><span data-stu-id="94b21-317">This will let you show this image and not the actual background of where you are sitting.</span></span> <span data-ttu-id="94b21-318">[詳細情報を参照してください](../meeting-policies-in-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="94b21-318">[Learn more](../meeting-policies-in-teams.md).</span></span>

## <a name="april-1-2020"></a><span data-ttu-id="94b21-319">2020年4月1日</span><span class="sxs-lookup"><span data-stu-id="94b21-319">April 1, 2020</span></span>

### <a name="teams-for-realwear"></a><span data-ttu-id="94b21-320">リアルな磨耗のチーム</span><span class="sxs-lookup"><span data-stu-id="94b21-320">Teams for RealWear</span></span>

<span data-ttu-id="94b21-321">Microsoft Teams クライアントでは、realwear の ruggedized ヘッドマウントされたウェアラブル機器を使用して、チームのビデオ通話を使用して専門家からリモートアシスタンスを利用できるようにすること100ができます。</span><span class="sxs-lookup"><span data-stu-id="94b21-321">Microsoft Teams client for RealWear enables Firstline Workers using RealWear's ruggedized head-mounted wearables to operate Teams 100 percent hands-free and seek remote assistance from experts using Teams video calling.</span></span> <span data-ttu-id="94b21-322">[詳細情報を参照してください](../flw-realwear.md)。</span><span class="sxs-lookup"><span data-stu-id="94b21-322">[Learn more](../flw-realwear.md).</span></span>

## <a name="march-31-2020"></a><span data-ttu-id="94b21-323">2020年3月31日</span><span class="sxs-lookup"><span data-stu-id="94b21-323">March 31, 2020</span></span>

### <a name="tag-youre-it"></a><span data-ttu-id="94b21-324">タグが表示されている</span><span class="sxs-lookup"><span data-stu-id="94b21-324">Tag, you're it</span></span>

<span data-ttu-id="94b21-325">グループ、役割、部門などの @mention できるように、タグを作成してユーザーをそのユーザーに割り当てることができます。チームの所有者は、長らくにお試しください。</span><span class="sxs-lookup"><span data-stu-id="94b21-325">Create tags and assign people to them so you can @mention a group, role, department, etc. Team owners, try it out for yourselves.</span></span> <span data-ttu-id="94b21-326">チームに移動し、[**その他のオプション**] の [タグの管理] を選択し  >  **Manage tags**ます。</span><span class="sxs-lookup"><span data-stu-id="94b21-326">Go to a team, select **More options** > **Manage tags**.</span></span> <span data-ttu-id="94b21-327">[詳細情報を参照してください](../manage-tags.md)。</span><span class="sxs-lookup"><span data-stu-id="94b21-327">[Learn more](../manage-tags.md).</span></span>

## <a name="march-30-2020"></a><span data-ttu-id="94b21-328">2020年3月30日</span><span class="sxs-lookup"><span data-stu-id="94b21-328">March 30, 2020</span></span>

### <a name="policy-based-recording-for-teams-calls-and-meetings"></a><span data-ttu-id="94b21-329">チームの通話と会議のポリシーベースのレコーディング</span><span class="sxs-lookup"><span data-stu-id="94b21-329">Policy-based recording for Teams calls and meetings</span></span>

<span data-ttu-id="94b21-330">この機能により、Microsoft 認定ソフトウェアベンダーを介して、チームの通話と会議のポリシーベースの自動レコーディングが可能になります。</span><span class="sxs-lookup"><span data-stu-id="94b21-330">This feature enables automatic policy-based recordings of Teams calls and meetings via Microsoft-certified software vendors.</span></span>

## <a name="march-25-2020"></a><span data-ttu-id="94b21-331">2020年3月25日</span><span class="sxs-lookup"><span data-stu-id="94b21-331">March 25, 2020</span></span>

### <a name="manage-your-collaboration-bar-devices-in-microsoft-teams"></a><span data-ttu-id="94b21-332">Microsoft Teams でコラボレーションバーデバイスを管理する</span><span class="sxs-lookup"><span data-stu-id="94b21-332">Manage your Collaboration Bar devices in Microsoft Teams</span></span>

<span data-ttu-id="94b21-333">管理者は、Microsoft Teams 管理センターからすべてのコラボレーションバーデバイスを管理する必要があります。</span><span class="sxs-lookup"><span data-stu-id="94b21-333">As an admin, you want to manage all your Collaboration Bar devices from Microsoft Teams admin center.</span></span> <span data-ttu-id="94b21-334">デバイスのインベントリを表示したり、デバイスで特定の操作を実行したり、すべてのデバイスにコマンドをリモートで提供したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="94b21-334">You can view inventory of devices, take specific actions on the devices and give commands remotely to all the devices.</span></span>
