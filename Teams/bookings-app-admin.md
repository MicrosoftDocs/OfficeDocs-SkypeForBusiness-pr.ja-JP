---
title: Microsoft Teams と Bookings アプリを使用した仮想訪問
author: msdmaguire
ms.author: dmaguire
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
search.appverid: ''
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- microsoftcloud-healthcare
- m365solution-healthcare
- m365solution-scenario
ms.reviewer: ''
description: Microsoft Teams と、Bookings アプリを使用した仮想訪問
ms.openlocfilehash: e65e0b8c4af7397ebe0b152d2f977b2bf8cbb667
ms.sourcegitcommit: f0e5da6136656261567ffe0fa3f2fedd901209a8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/19/2021
ms.locfileid: "51891264"
---
# <a name="virtual-visits-with-microsoft-teams-and-the-bookings-app"></a><span data-ttu-id="6a9d7-103">Microsoft Teams と Bookings アプリを使用した仮想訪問</span><span class="sxs-lookup"><span data-stu-id="6a9d7-103">Virtual visits with Microsoft Teams and the Bookings app</span></span>

<span data-ttu-id="6a9d7-104">Microsoft Teams の Bookings アプリでは、医療訪問、財務相談、インタビュー、カスタマー サポート、教育用のオフィス時間など、対面および仮想的な予定を簡単にスケジュールできます。</span><span class="sxs-lookup"><span data-stu-id="6a9d7-104">The Bookings app in Microsoft Teams offers a simple way to schedule in-person and virtual appointments, such as healthcare visits, financial consultations, interviews, customer support, education office hours, and much more.</span></span>

<span data-ttu-id="6a9d7-105">スケジュール担当者は、1 つの操作環境から、複数の部門とスタッフの予定表、および組織内外の出席者との通信を管理できます。</span><span class="sxs-lookup"><span data-stu-id="6a9d7-105">Schedulers can manage multiple department and staff calendars, as well as communications with internal and external attendees, from a single experience.</span></span> <span data-ttu-id="6a9d7-106">仮想予定自体は、強力なビデオ会議機能を提供する Microsoft Teams 会議を介して開催されます。</span><span class="sxs-lookup"><span data-stu-id="6a9d7-106">The virtual appointments themselves are held via Microsoft Teams Meetings, which offers robust videoconferencing capabilities.</span></span>

> [!NOTE]
> <span data-ttu-id="6a9d7-107">Bookings アプリを Teams にインストールする必要があるのはスケジュール担当者だけです。</span><span class="sxs-lookup"><span data-stu-id="6a9d7-107">Only schedulers need to have the Bookings app installed in Teams.</span></span> <span data-ttu-id="6a9d7-108">仮想予定を実施または参加するスタッフは、アプリを必要としません。</span><span class="sxs-lookup"><span data-stu-id="6a9d7-108">Staff conducting or participating in virtual appointments do not need the app.</span></span> <span data-ttu-id="6a9d7-109">Outlook または Teams の予定表から、または予約確認メールのリンクから、予定に参加できます。</span><span class="sxs-lookup"><span data-stu-id="6a9d7-109">They can simply join appointments from their Outlook or Teams calendar or from a link in their booking confirmation email.</span></span>

## <a name="prerequisites-for-using-the-bookings-app-in-teams"></a><span data-ttu-id="6a9d7-110">Teams で Bookings アプリを使用するための前提条件</span><span class="sxs-lookup"><span data-stu-id="6a9d7-110">Prerequisites for using the Bookings app in Teams</span></span>

- <span data-ttu-id="6a9d7-111">Exchange メールボックスは Exchange Online にある必要があります。</span><span class="sxs-lookup"><span data-stu-id="6a9d7-111">The Exchange mailbox must be in Exchange Online.</span></span> <span data-ttu-id="6a9d7-112">オンプレミスの Exchange Server メールボックスはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="6a9d7-112">On-premises Exchange Server mailboxes are not supported.</span></span>

- <span data-ttu-id="6a9d7-113">Microsoft Bookings を組織で有効にしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="6a9d7-113">Microsoft Bookings must be turned on for the organization.</span></span>

- <span data-ttu-id="6a9d7-114">ユーザーは、適切なライセンスを持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="6a9d7-114">Users must have an appropriate license.</span></span> <span data-ttu-id="6a9d7-115">Office 365 A3、A5、E3、E5 だけでなく、Microsoft 365 Business Premium、Microsoft 365 Business Standard、A3、A5、E3、E5 もサポートされています。</span><span class="sxs-lookup"><span data-stu-id="6a9d7-115">Office 365 A3, A5, E3, and E5, as well as Microsoft 365 Business Premium, Microsoft 365 Business Standard, A3, A5, E3, and E5 are supported.</span></span>

- <span data-ttu-id="6a9d7-116">Bookings アプリのすべてのユーザーと会議に参加するすべてのスタッフは、Teams 会議のスケジュールをサポートするライセンスを持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="6a9d7-116">All users of the Bookings app and all staff participating in meetings must have a license that supports Teams Meeting scheduling.</span></span>

- <span data-ttu-id="6a9d7-117">システムは、すべての[ソフトウェアとブラウザーの前提条件](hardware-requirements-for-the-teams-app.md)を満たす必要があります。</span><span class="sxs-lookup"><span data-stu-id="6a9d7-117">Your systems must meet all [Software and browser prerequisites](hardware-requirements-for-the-teams-app.md).</span></span>

## <a name="availability-of-bookings-in-teams"></a><span data-ttu-id="6a9d7-118">Teams での Bookings の利用可能性</span><span class="sxs-lookup"><span data-stu-id="6a9d7-118">Availability of Bookings in Teams</span></span>

<span data-ttu-id="6a9d7-119">Teams 用の Microsoft Bookings アプリは、デスクトップと Web で利用できます。</span><span class="sxs-lookup"><span data-stu-id="6a9d7-119">Microsoft Bookings App for Teams is available on the desktop and web.</span></span> <span data-ttu-id="6a9d7-120">これは、[Microsoft Teams 内の アプリ](https://teams.microsoft.com/l/app/4c4ec2e8-4a2c-4bce-8d8f-00fc664a4e5b?source=store-copy-link)と Teams 管理センターの **[アプリの管理]** で見つかります。</span><span class="sxs-lookup"><span data-stu-id="6a9d7-120">It can be found under [Apps within Microsoft Teams](https://teams.microsoft.com/l/app/4c4ec2e8-4a2c-4bce-8d8f-00fc664a4e5b?source=store-copy-link) and under **Manage Apps** within Teams Admin Center.</span></span>

### <a name="control-access-to-bookings-within-your-organization"></a><span data-ttu-id="6a9d7-121">組織内の Bookings へのアクセスを制御する</span><span class="sxs-lookup"><span data-stu-id="6a9d7-121">Control access to Bookings within your organization</span></span>

<span data-ttu-id="6a9d7-122">Bookings アプリにアクセスできるユーザーとアプリの特定の機能を制御するには、いくつかの方法があります。</span><span class="sxs-lookup"><span data-stu-id="6a9d7-122">There are several ways to control who has access to the Bookings app and to specific features of the app.</span></span> <span data-ttu-id="6a9d7-123">Microsoft 365 管理センターで Microsoft Bookings をオンまたはオフにする方法、および選択したユーザーが Bookings の予定表を作成できるようにする Bookings アプリ ポリシーを作成する方法については、「[Microsoft Bookings にアクセスする](https://support.microsoft.com/ja-JP/office/get-access-to-microsoft-bookings-5382dc07-aaa5-45c9-8767-502333b214ce)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6a9d7-123">To learn how to turn Microsoft Bookings on or off in the Microsoft 365 admin center, as well as how to create a Bookings app policy to allow selected users to create Bookings calendars, see [Get access to Microsoft Bookings](https://support.microsoft.com/ja-JP/office/get-access-to-microsoft-bookings-5382dc07-aaa5-45c9-8767-502333b214ce).</span></span> <span data-ttu-id="6a9d7-124">[Teams アプリ ポリシーを作成して、一部のユーザーに Bookings アプリをピン留めする方法](teams-app-setup-policies.md)も参照してください。</span><span class="sxs-lookup"><span data-stu-id="6a9d7-124">You can also learn how to [Create a Teams app policy to pin the Bookings app for select users](teams-app-setup-policies.md).</span></span>

## <a name="recommended-meeting-policy-settings"></a><span data-ttu-id="6a9d7-125">推奨される会議ポリシーの設定</span><span class="sxs-lookup"><span data-stu-id="6a9d7-125">Recommended Meeting Policy Settings</span></span>

<span data-ttu-id="6a9d7-126">Bookings で最高のエクスペリエンスを実現するには、スタッフ会議ポリシーを作成して、**組織内のすべてのユーザー** を自動的に承認するようにします。</span><span class="sxs-lookup"><span data-stu-id="6a9d7-126">To enable the best experience for Bookings, create a staff meeting policy to automatically admit **Everyone in your organization**.</span></span> <span data-ttu-id="6a9d7-127">これにより、スタッフは予定に自動的に参加できるようになり、外部出席者のロビー エクスペリエンスを有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="6a9d7-127">This will allow staff to join the appointment automatically and enable lobby experience for external attendees.</span></span> <span data-ttu-id="6a9d7-128">詳細については、「[会議へのユーザーの参加を自動的に許可する](meeting-policies-participants-and-guests.md#automatically-admit-people)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6a9d7-128">You can learn more about [automatically admitting people to meetings](meeting-policies-participants-and-guests.md#automatically-admit-people).</span></span>

### <a name="optional-staff-approvals-setting"></a><span data-ttu-id="6a9d7-129">オプションのスタッフ承認設定</span><span class="sxs-lookup"><span data-stu-id="6a9d7-129">Optional staff approvals setting</span></span>

<span data-ttu-id="6a9d7-130">追加のプライバシー設定として、スケジュールの空き時間情報が Bookings を通じて共有される前や、予定を予約する前に、スタッフに参加を要求することを選択できます。</span><span class="sxs-lookup"><span data-stu-id="6a9d7-130">As an extra privacy setting, you can choose to require staff to opt in before their schedule availability information is shared through Bookings and before they can be booked for an appointment.</span></span>  

<span data-ttu-id="6a9d7-131">この設定を有効にするには、**[Microsoft 365 管理センター]** \> **[設定]** \> **[設定]** に移動し、**[Bookings]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="6a9d7-131">To enable this setting, go to **Microsoft 365 admin center** \> **Settings** \> **Settings**, then select **Bookings**.</span></span>

<span data-ttu-id="6a9d7-132">この設定をオンにすると、予約予定表のメンバーシップを承認するように求めるメールがスタッフに送信されます。</span><span class="sxs-lookup"><span data-stu-id="6a9d7-132">With this setting turned on, staff will receive an email in which they are asked to approve membership to a booking calendar.</span></span>  

<span data-ttu-id="6a9d7-133">この機能は、Microsoft 365 および Office 365 のお客様に向けて世界中で段階的に展開されています。</span><span class="sxs-lookup"><span data-stu-id="6a9d7-133">This feature is gradually being rolled out worldwide to Microsoft 365 and Office 365 customers.</span></span> <span data-ttu-id="6a9d7-134">ご使用の環境ですべてのオプションがまだ利用できない場合は、しばらくしてからもう一度お試しください。</span><span class="sxs-lookup"><span data-stu-id="6a9d7-134">If all options are not yet available in your environment, check back soon.</span></span>

## <a name="changing-your-default-domain-when-setting-up-bookings-mailboxes"></a><span data-ttu-id="6a9d7-135">Bookings メールボックスのセットアップ時に既定のドメインを変更する</span><span class="sxs-lookup"><span data-stu-id="6a9d7-135">Changing your default domain when setting up Bookings mailboxes</span></span>

<span data-ttu-id="6a9d7-136">Bookings メールボックスをセットアップするときに、Microsoft 365 または Office 365 組織の既定のメール ドメインが使用されます。</span><span class="sxs-lookup"><span data-stu-id="6a9d7-136">When setting up a Bookings mailbox, the default email domain of your Microsoft 365 or Office 365 organization is used.</span></span> <span data-ttu-id="6a9d7-137">ただし、それにより外部の受信者に会議出席招待を送信するときに問題が発生する可能性があります。具体的には、招待に迷惑メールのフラグが設定され、受信者の迷惑メール フォルダーに移動される可能性があり、その場合、受信者はその招待を表示しない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="6a9d7-137">However, this can cause problems when sending meeting invites to external recipients; your invite might be flagged as spam and moved to the recipient’s junk folder, so the recipient might never see your invite.</span></span>

<span data-ttu-id="6a9d7-138">Bookings メールボックスを作成する前に、既定のドメインを変更することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="6a9d7-138">We recommend that you change the default domain prior to creating your Bookings mailbox.</span></span> <span data-ttu-id="6a9d7-139">これを行う方法について詳しくは、「[ドメインに関する FAQ](/microsoft-365/admin/setup/domains-faq#how-do-i-set-or-change-the-default-domain-in-office-365)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6a9d7-139">For information on how to do this, see the [Domains FAQ](/microsoft-365/admin/setup/domains-faq#how-do-i-set-or-change-the-default-domain-in-office-365).</span></span>

<span data-ttu-id="6a9d7-140">Bookings メールボックスが既に作成された後に既定のドメインを変更する必要がある場合は、PowerShell で変更できます。</span><span class="sxs-lookup"><span data-stu-id="6a9d7-140">If you need to change the default domain after your Bookings mailbox has already been created, you can do so with PowerShell:</span></span>

```PowerShell
Set-Mailbox -identity business@domain.onmicrosoft.com -WindowsEmailAddress business@domain.com -EmailAddresses business@domain.com
```

<span data-ttu-id="6a9d7-141">詳細については、「[Set-Mailbox](/powershell/module/exchange/mailboxes/set-mailbox)」コマンドレットの PowerShell ドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="6a9d7-141">For more information, see the PowerShell documentation for the [Set-Mailbox](/powershell/module/exchange/mailboxes/set-mailbox) cmdlet.</span></span>

> [!NOTE]
> <span data-ttu-id="6a9d7-142">Exchange ハイブリッド構成を使用している場合は、既定のドメインを変更するときに、オンプレミスの Exchange と Exchange Online 間のメール フローを十分にテストすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="6a9d7-142">If you are using an Exchange hybrid configuration, we recommend that you thoroughly test mail flow between on-premises Exchange and Exchange Online when changing the default domain.</span></span>

## <a name="sending-feedback"></a><span data-ttu-id="6a9d7-143">フィードバックの送信</span><span class="sxs-lookup"><span data-stu-id="6a9d7-143">Sending feedback</span></span>

<span data-ttu-id="6a9d7-144">以下に関するフィードバックをお寄せください。</span><span class="sxs-lookup"><span data-stu-id="6a9d7-144">We welcome your feedback on:</span></span>

  - <span data-ttu-id="6a9d7-145">ユーザー エクスペリエンスまたは使いやすさ</span><span class="sxs-lookup"><span data-stu-id="6a9d7-145">User experience or ease of use</span></span>
  - <span data-ttu-id="6a9d7-146">機能のギャップまたは不足している機能</span><span class="sxs-lookup"><span data-stu-id="6a9d7-146">Feature gaps or missing functionality</span></span>
  - <span data-ttu-id="6a9d7-147">バグや問題</span><span class="sxs-lookup"><span data-stu-id="6a9d7-147">Bugs or issues</span></span>
  
<span data-ttu-id="6a9d7-148">フィードバックを送信するには、Teams の左側のナビゲーション バーの下部にある **[ヘルプ]** ボタンをクリックし、**すべて** の問題に関するフィードバック用の **[問題の報告]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6a9d7-148">To send feedback, click the **Help** button near the bottom of the Teams left navigation bar, then click **Report a Problem** for **ALL** issues.</span></span> <span data-ttu-id="6a9d7-149">フィードバック レポートの先頭に、"Bookings" に関するフィードバックであることを明記してください。それにより、Bookings に関する問題を簡単に識別することができます。</span><span class="sxs-lookup"><span data-stu-id="6a9d7-149">Please note at the beginning of your feedback report that you are sending feedback about "Bookings" so we can easily identify Bookings issues.</span></span>

## <a name="related-topics"></a><span data-ttu-id="6a9d7-150">関連トピック</span><span class="sxs-lookup"><span data-stu-id="6a9d7-150">Related topics</span></span>

<span data-ttu-id="6a9d7-151">
  [エンド ユーザー向け Bookings ドキュメント](https://support.office.com/en-us/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b?ui=en-US&rs=en-US&ad=US#PickTab=Bookings)</span><span class="sxs-lookup"><span data-stu-id="6a9d7-151">[Bookings documentation for end users](https://support.office.com/en-us/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b?ui=en-US&rs=en-US&ad=US#PickTab=Bookings)</span></span>