---
title: マイクロソフトのチームでのライブ イベントを構成します。
author: tonysmith
ms.author: tonysmit
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: tonysmit
search.appverid: MET150
description: 出席者の表示/非表示を設定して、レコーディングのオプションを含む、Microsoft のチームのライブ イベントの設定を構成する方法について説明します。
appliesto:
- Microsoft Teams
ms.openlocfilehash: fcd9bc02257d67f1af959d2158042ea73545a25e
ms.sourcegitcommit: 6447a3aa060452c8d6879524cd6a56aecf33b152
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/01/2018
ms.locfileid: "25354357"
---
# <a name="configure-live-events-in-microsoft-teams"></a><span data-ttu-id="34363-103">マイクロソフトのチームでのライブ イベントを構成します。</span><span class="sxs-lookup"><span data-stu-id="34363-103">Configure live events in Microsoft Teams</span></span>
> [!INCLUDE [Preview customer token](../includes/preview-feature.md)]

## <a name="set-up-event-support-link"></a><span data-ttu-id="34363-104">イベントのサポートのリンクを設定します。</span><span class="sxs-lookup"><span data-stu-id="34363-104">Set up event support link</span></span>
<span data-ttu-id="34363-105">これは、ライブ イベントの参加者に表示されるリンクです。</span><span class="sxs-lookup"><span data-stu-id="34363-105">This is the link that will be shown to the live event attendees.</span></span> 

<span data-ttu-id="34363-106">Windows PowerShell で、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="34363-106">In Windows PowerShell, run the following:</span></span>
```
Set-CsTeamsMeetingBroadcastConfiguration -SupportURL “{your URL}” 
```
## <a name="configure-attendee-visibility-options"></a><span data-ttu-id="34363-107">出席者の表示/非表示のオプションを構成します。</span><span class="sxs-lookup"><span data-stu-id="34363-107">Configure attendee visibility options</span></span>
<span data-ttu-id="34363-108">これにより、適切な参加者の可視性を持つイベントを作成するライブ イベントを開催します。</span><span class="sxs-lookup"><span data-stu-id="34363-108">This allows live event organizers to create events with appropriate attendee visibility.</span></span>

|<span data-ttu-id="34363-109">**値**</span><span class="sxs-lookup"><span data-stu-id="34363-109">**Values**</span></span>  |<span data-ttu-id="34363-110">**動作**</span><span class="sxs-lookup"><span data-stu-id="34363-110">**Behavior**</span></span>  |
|---------|---------|
|<span data-ttu-id="34363-111">全員</span><span class="sxs-lookup"><span data-stu-id="34363-111">Everyone</span></span>     |<span data-ttu-id="34363-112">ライブ イベントを次の出席者の可視性を作成するオプションをユーザーが持っている: 会社、および特定のユーザーのすべてのメンバーを公開します。</span><span class="sxs-lookup"><span data-stu-id="34363-112">The user has an option to create live events with the following attendee visibility: Public, Everyone in company, and Specific people.</span></span> |
|<span data-ttu-id="34363-113">EveryoneInCompany</span><span class="sxs-lookup"><span data-stu-id="34363-113">EveryoneInCompany</span></span>     |<span data-ttu-id="34363-114">ユーザーは、ライブ イベントを次の出席者の可視性を作成するオプションを持っている: 会社および特定のユーザーのすべてのメンバーです。</span><span class="sxs-lookup"><span data-stu-id="34363-114">The user has an option to create live events with the following attendee visibility: Everyone in company and Specific people.</span></span> <span data-ttu-id="34363-115">ユーザーは、匿名ユーザーが参加できるライブ イベントを作成できません。</span><span class="sxs-lookup"><span data-stu-id="34363-115">The user cannot create live events that can be attended by anonymous users.</span></span>|
|<span data-ttu-id="34363-116">InvitedUsers</span><span class="sxs-lookup"><span data-stu-id="34363-116">InvitedUsers</span></span> |<span data-ttu-id="34363-117">ユーザーは、イベント開催者によって入力されたとおりに、特定の人に制限されているライブのイベントのみを作成できます。</span><span class="sxs-lookup"><span data-stu-id="34363-117">The user can only create live events that are limited to specific people as entered by the event organizer.</span></span> <span data-ttu-id="34363-118">ユーザーは、公開キーと認証の会社のすべてのメンバーでライブ イベントを作成できません。</span><span class="sxs-lookup"><span data-stu-id="34363-118">The user cannot create live events with Public and Everyone in company authentication.</span></span> |

<span data-ttu-id="34363-119">ユーザーが匿名の参加者を監視することができますブロードキャストのイベントのスケジュールを設定するかどうかは、PowerShell の TeamsMeetingBroadcastPolicy の BroadcastAttendeeVisibility コントロールの設定を使用します。</span><span class="sxs-lookup"><span data-stu-id="34363-119">Use the setting BroadcastAttendeeVisibility in TeamsMeetingBroadcastPolicy in PowerShell to control whether the users can schedule broadcast events that can be watched by anonymous attendees.</span></span> 

<span data-ttu-id="34363-120">カスタム ポリシーは、ユーザーに割り当てている、しない限り、ユーザーは、EveryoneInCompany に設定する既定値を保持するグローバル ポリシーを取得します。</span><span class="sxs-lookup"><span data-stu-id="34363-120">Unless you have assigned a custom policy to the users, the users get Global policy, which has default set to EveryoneInCompany.</span></span> 
 
<span data-ttu-id="34363-121">Windows PowerShell では、[グローバル ポリシーで匿名イベントを作成するユーザーを許可するのには、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="34363-121">In Windows PowerShell, run the following to allow users to create anonymous events in the global policy:</span></span>
```
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -BroadcastAttendeeVisibility Everyone  
```
## <a name="configure-recording-options"></a><span data-ttu-id="34363-122">レコーディングのオプションを構成します。</span><span class="sxs-lookup"><span data-stu-id="34363-122">Configure recording options</span></span>
> [!NOTE]
> <span data-ttu-id="34363-123">このオプションは、クイック スタートの生産方法のみを使用するイベントに適用されます。</span><span class="sxs-lookup"><span data-stu-id="34363-123">This option is applicable to events that use the Quick start production method only.</span></span>

<span data-ttu-id="34363-124">これにより、ライブ イベントは、常に記録、記録されることはないかどうか、またはイベントの開催者は、かのイベントが記録することができるかどうか制御する管理者です。</span><span class="sxs-lookup"><span data-stu-id="34363-124">This allows admins to control whether the live events are always recorded, never recorded, or whether the event organizer can decide to record the event or not.</span></span>  

|<span data-ttu-id="34363-125">**値**</span><span class="sxs-lookup"><span data-stu-id="34363-125">**Values**</span></span>  |<span data-ttu-id="34363-126">**動作**</span><span class="sxs-lookup"><span data-stu-id="34363-126">**Behavior**</span></span>  |
|---------|---------|
|<span data-ttu-id="34363-127">常に有効になっています。</span><span class="sxs-lookup"><span data-stu-id="34363-127">Always enabled</span></span> |<span data-ttu-id="34363-128">このユーザーごとのライブ イベントは、常に記録されます。</span><span class="sxs-lookup"><span data-stu-id="34363-128">The live events organized by this user are always recorded.</span></span> <span data-ttu-id="34363-129">ユーザー オプションをオーバーライドする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="34363-129">The user doesn’t have an option to override.</span></span> <span data-ttu-id="34363-130">ライブのイベントが記録される場合は、イベントのチーム メンバーは、イベントの後にレコーディングをダウンロードすることと出席者は、イベント終了後のイベントを監視できます。</span><span class="sxs-lookup"><span data-stu-id="34363-130">If the live event is recorded, the event team members are able to download the recording after the event, and the attendees can watch the event after the event is over.</span></span> |
|<span data-ttu-id="34363-131">AlwaysDisabled</span><span class="sxs-lookup"><span data-stu-id="34363-131">AlwaysDisabled</span></span> |<span data-ttu-id="34363-132">このユーザーが開催するライブ イベントが記録されることはありません。</span><span class="sxs-lookup"><span data-stu-id="34363-132">The live events organized by this user are never recorded.</span></span> <span data-ttu-id="34363-133">ユーザー オプションをオーバーライドする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="34363-133">The user doesn’t have an option to override.</span></span> <span data-ttu-id="34363-134">ライブのイベントが記録される場合は、イベント チームのメンバーの記録は作成されず、出席者はイベントが上にあるを見ることはできません。</span><span class="sxs-lookup"><span data-stu-id="34363-134">If the live event is recorded, no recording is created for the event team members, and the attendees cannot watch the event after it is over.</span></span> |
|<span data-ttu-id="34363-135">UserOverride</span><span class="sxs-lookup"><span data-stu-id="34363-135">UserOverride</span></span> |<span data-ttu-id="34363-136">ユーザーは、イベント チームのメンバーの記録ファイルを作成することができ、参加者がイベント終了後のイベントを監視するためにライブ イベントを記録するかどうかを決定できます。</span><span class="sxs-lookup"><span data-stu-id="34363-136">User can decide whether the live event is recorded so that a recording file can be created for the event team members, and attendees can watch the event after the event is over.</span></span> |

<span data-ttu-id="34363-137">レコーディングのライブ イベントの開催者によって作成されたライブ イベントのオプションのコントロールに、PowerShell では、 **TeamsMeetingBroadcastPolicy**で*BroadcastRecordingMode*の設定を使用します。</span><span class="sxs-lookup"><span data-stu-id="34363-137">Use the setting *BroadcastRecordingMode* in **TeamsMeetingBroadcastPolicy** in PowerShell to control recording options of the live events created by the live event organizer.</span></span>

<span data-ttu-id="34363-138">Windows PowerShell のでは、グローバル ポリシーでの記録モードを更新するのには次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="34363-138">In Windows PowerShell, run the following cmdlet to update recording mode in the global policy:</span></span>
```
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -BroadcastRecordingMode AlwaysDisabled 
```
## <a name="configure-real-time-transcription-and-translation-in-teams-live-events-coming-soon"></a><span data-ttu-id="34363-139">(準備中) チームのライブ イベントのリアルタイム議事録を作成し、変換を構成します。</span><span class="sxs-lookup"><span data-stu-id="34363-139">Configure real-time transcription and translation in Teams live events (coming soon)</span></span>
> [!NOTE]
> <span data-ttu-id="34363-140">このオプションは、クイック スタートの生産方法のみを使用するイベントに適用されます。</span><span class="sxs-lookup"><span data-stu-id="34363-140">This option is applicable to events that use the Quick start production method only.</span></span>

<span data-ttu-id="34363-141">これにより、リアルタイムのキャプションとライブ イベントの出席者に対して変換を有効にするのにはライブ イベントを開催します。</span><span class="sxs-lookup"><span data-stu-id="34363-141">This allows live event organizers to turn on real-time captions and translation for the live event attendees.</span></span> 

<span data-ttu-id="34363-142">ライブ イベントの参加者が議事録と翻訳を参照してくださいできるかどうかにコントロールする PowerShell の**TeamsMeetingBroadcastPolicy**で*AllowBroadcastTranscription*の設定を使用します。</span><span class="sxs-lookup"><span data-stu-id="34363-142">Use the setting *AllowBroadcastTranscription* in **TeamsMeetingBroadcastPolicy** in PowerShell to control whether the live event attendees will be able to see transcription and translation.</span></span> <span data-ttu-id="34363-143">ここで、Office 365 の PowerShell では、 **TeamsMeetingBroadcastPolicy**を管理する方法の詳細については。</span><span class="sxs-lookup"><span data-stu-id="34363-143">You can learn more about managing **TeamsMeetingBroadcastPolicy** with Office 365 PowerShell here.</span></span>  

<span data-ttu-id="34363-144">カスタム ポリシーは、ユーザーに割り当てている、しない限り、ユーザーは、議事録作成と翻訳が既定で無効にするグローバル ポリシーを取得します。</span><span class="sxs-lookup"><span data-stu-id="34363-144">Unless you have assigned a custom policy to the users, the users get Global policy, which has transcription and translation disabled by default.</span></span>

<span data-ttu-id="34363-145">Windows PowerShell では、[グローバル ポリシーでの議事録やイベントの出席者のために翻訳を有効にするのには、次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="34363-145">In Windows PowerShell, run the following cmdlet to turn transcription and translation on for event attendees in the global policy:</span></span>
```
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -AllowBroadcastTranscription $true 
```
## <a name="administrative-tools"></a><span data-ttu-id="34363-146">管理ツール</span><span class="sxs-lookup"><span data-stu-id="34363-146">Administrative tools</span></span> 
<span data-ttu-id="34363-147">直接 Microsoft は、Office 365 のオンラインのすべてのデータ センターを制御し、システム全体のパフォーマンスは、ですが、Office 365 のユーザーの合計の経験を提供する要素の一部だけを制御できます。</span><span class="sxs-lookup"><span data-stu-id="34363-147">Although Microsoft directly controls all Office 365 Online data centers and is responsible for overall system performance, it can control only a portion of the elements that combine to provide the total experience for Office 365 users.</span></span> <span data-ttu-id="34363-148">組織自体は、データ センターでお客様のワイド エリア ネットワーク (WAN)、ネットワーク接続を担当し、お客様のローカル エリア ネットワーク (Lan)。</span><span class="sxs-lookup"><span data-stu-id="34363-148">Organizations themselves are responsible for the network connections to the data centers, the customer’s wide area network (WAN), and the customer's local area networks (LANs).</span></span> <span data-ttu-id="34363-149">さらに、ユーザーのデバイスとその構成を担当しています。</span><span class="sxs-lookup"><span data-stu-id="34363-149">Additionally, they are in charge of user devices and their configuration.</span></span><span data-ttu-id="34363-150">必要なライセンスなど、必要な機能は、ユーザーごとの管理を担当する、マイクロソフトが、ユーザーは、機能へのアクセスを必要がある限りのこれらの機能を管理することに。</span><span class="sxs-lookup"><span data-stu-id="34363-150"> They are also responsible for maintaining the required licensing per user for any desired feature, including, but not limited to, the ability to manage these features, for as long as the user needs access to the feature.</span></span>

<span data-ttu-id="34363-151">お客様は、さまざまなチームのライブ イベントの関連タスクを管理するために次のツールを使用できます。</span><span class="sxs-lookup"><span data-stu-id="34363-151">Customers can use the following tools to manage a variety of Teams live events related tasks.</span></span>
- [<span data-ttu-id="34363-152">Microsoft Office 365 管理者センター</span><span class="sxs-lookup"><span data-stu-id="34363-152">Microsoft Office 365 admin center</span></span>](https://technet.microsoft.com/library/exchange-online-administration-and-management.aspx?f=255&MSPPError=-2147217396#BKMK_Office365admincenterl)
- [<span data-ttu-id="34363-153">マイクロソフトのチームと Skype のオンライン ビジネスの管理センター</span><span class="sxs-lookup"><span data-stu-id="34363-153">Microsoft Teams and Skype for Business Online admin center</span></span>](https://technet.microsoft.com/library/exchange-online-administration-and-management.aspx?f=255&MSPPError=-2147217396#BKMK_ExchangeAdministrationCenter)
- [<span data-ttu-id="34363-154">Microsoft ストリーム管理センター</span><span class="sxs-lookup"><span data-stu-id="34363-154">Microsoft Stream admin center</span></span>](https://stream.microsoft.com)
- [<span data-ttu-id="34363-155">リモートの Windows PowerShell の</span><span class="sxs-lookup"><span data-stu-id="34363-155">Remote Windows PowerShell</span></span>](https://technet.microsoft.com/library/exchange-online-administration-and-management.aspx?f=255&MSPPError=-2147217396#BKMK_RemoteWindowsPowerShell)

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="34363-156">Windows PowerShell の詳細情報</span><span class="sxs-lookup"><span data-stu-id="34363-156">Want to know more about Windows PowerShell?</span></span>
<span data-ttu-id="34363-157">に関して Windows PowerShell は、it のすべてのユーザーを管理するか、ユーザーの許可を許可します。</span><span class="sxs-lookup"><span data-stu-id="34363-157">When it comes to Windows PowerShell, it's all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="34363-158">Windows PowerShell では、ビジネス オンラインを行う複数のタスクがある場合、日常的な作業を簡素化する管理の単一ポイントを使用して Office 365 と Skype を管理できます。</span><span class="sxs-lookup"><span data-stu-id="34363-158">With Windows PowerShell, you can manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="34363-159">Windows PowerShell の使用を開始するには、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="34363-159">To get started with Windows PowerShell, see these topics:</span></span>
 - [<span data-ttu-id="34363-160">Windows PowerShell と Skype for Business Online の概要</span><span class="sxs-lookup"><span data-stu-id="34363-160">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
 - [<span data-ttu-id="34363-161">Windows PowerShell で Office 365 を管理するための最善の方法</span><span class="sxs-lookup"><span data-stu-id="34363-161">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)

<span data-ttu-id="34363-p108">Windows PowerShell には、ただ Office 365 管理センターを使用するだけではなく、速度、単純さ、生産性において多くの利点があります。次のトピックでこれらの利点について説明します。</span><span class="sxs-lookup"><span data-stu-id="34363-p108">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center such as when you are making setting changes for many users at one time. Learn about these advantages in the following topics:</span></span>
 - [<span data-ttu-id="34363-164">Windows PowerShell で Office 365 を管理するための最善の方法</span><span class="sxs-lookup"><span data-stu-id="34363-164">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
 - [<span data-ttu-id="34363-165">Windows PowerShell による Skype for Business Online の管理</span><span class="sxs-lookup"><span data-stu-id="34363-165">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
 - [<span data-ttu-id="34363-166">クイック リファレンス: Windows PowerShell を使用した一般的な Lync Online の管理タスクの実行</span><span class="sxs-lookup"><span data-stu-id="34363-166">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
