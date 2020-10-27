---
title: Microsoft Teams と予約アプリを使用した仮想アクセス
author: msdmaguire
ms.author: dmaguire
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
search.appverid: ''
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: ''
ms.reviewer: ''
description: 予約アプリを使用した Microsoft Teams と仮想アクセス
ms.openlocfilehash: 0c88feec8a90b2794e93fb9c51bffafabf942748
ms.sourcegitcommit: 0a51738879b13991986a3a872445daa8bd20533d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "48766960"
---
# <a name="virtual-visits-with-microsoft-teams-and-the-bookings-app"></a><span data-ttu-id="8825b-103">Microsoft Teams と予約アプリを使用した仮想アクセス</span><span class="sxs-lookup"><span data-stu-id="8825b-103">Virtual visits with Microsoft Teams and the Bookings app</span></span>

<span data-ttu-id="8825b-104">Microsoft Teams の予約アプリでは、医療機関の訪問、財務相談、面接、カスタマサポート、教育機関の時間など、個人や仮想の予定をスケジュールするための簡単な方法が用意されています。</span><span class="sxs-lookup"><span data-stu-id="8825b-104">The Bookings app in Microsoft Teams offers a simple way to schedule in-person and virtual appointments, such as healthcare visits, financial consultations, interviews, customer support, education office hours, and much more.</span></span>

<span data-ttu-id="8825b-105">スケジューラは、1つのエクスペリエンスから複数の部門とスタッフの予定表を管理したり、内部および外部の出席者との通信を管理したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="8825b-105">Schedulers can manage multiple department and staff calendars, as well as communications with internal and external attendees, from a single experience.</span></span> <span data-ttu-id="8825b-106">仮想の予定は Microsoft Teams の会議によって開催されます。これには、強力なビデオ会議機能が備わっています。</span><span class="sxs-lookup"><span data-stu-id="8825b-106">The virtual appointments themselves are held via Microsoft Teams Meetings, which offers robust videoconferencing capabilities.</span></span>

> [!NOTE]
> <span data-ttu-id="8825b-107">Teams で予約アプリをインストールする必要があるのは、スケジューラだけです。</span><span class="sxs-lookup"><span data-stu-id="8825b-107">Only schedulers need to have the Bookings app installed in Teams.</span></span> <span data-ttu-id="8825b-108">仮想予定を開催または参加しているスタッフには、アプリは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="8825b-108">Staff conducting or participating in virtual appointments do not need the app.</span></span> <span data-ttu-id="8825b-109">自分の Outlook または Teams の予定表から、または予約確認メールのリンクから、予定を簡単に追加することができます。</span><span class="sxs-lookup"><span data-stu-id="8825b-109">They can simply join appointments from their Outlook or Teams calendar or from a link in their booking confirmation email.</span></span>

## <a name="prerequisites-for-using-the-bookings-app-in-teams"></a><span data-ttu-id="8825b-110">Teams で予約アプリを使用するための前提条件</span><span class="sxs-lookup"><span data-stu-id="8825b-110">Prerequisites for using the Bookings app in Teams</span></span>

- <span data-ttu-id="8825b-111">Exchange メールボックスは Exchange Online にある必要があります。</span><span class="sxs-lookup"><span data-stu-id="8825b-111">The Exchange mailbox must be in Exchange Online.</span></span> <span data-ttu-id="8825b-112">オンプレミスの Exchange Server メールボックスはサポートされません。</span><span class="sxs-lookup"><span data-stu-id="8825b-112">On-premises Exchange Server mailboxes are not supported.</span></span>

- <span data-ttu-id="8825b-113">組織で Microsoft 予約を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="8825b-113">Microsoft Bookings must be turned on for the organization.</span></span>

- <span data-ttu-id="8825b-114">ユーザーは適切なライセンスを持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="8825b-114">Users must have an appropriate license.</span></span> <span data-ttu-id="8825b-115">Office 365 A3、A5、E3、E5、および Microsoft 365 Business Standard、A3、A5、E3、E5 がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="8825b-115">Office 365 A3, A5, E3, and E5, as well as Microsoft 365 Business Standard, A3, A5, E3, and E5 are supported.</span></span>

- <span data-ttu-id="8825b-116">予約アプリのすべてのユーザーと会議に参加しているすべてのスタッフは、チーム会議のスケジュールをサポートするライセンスを持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="8825b-116">All users of the Bookings app and all staff participating in meetings must have a license that supports Teams Meeting scheduling.</span></span>

- <span data-ttu-id="8825b-117">システムは、 [ソフトウェアとブラウザーのすべての前提条件を](hardware-requirements-for-the-teams-app.md)満たしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="8825b-117">Your systems must meet all [Software and browser prerequisites](hardware-requirements-for-the-teams-app.md).</span></span>

## <a name="availability-of-bookings-in-teams"></a><span data-ttu-id="8825b-118">Teams での予約の利用</span><span class="sxs-lookup"><span data-stu-id="8825b-118">Availability of Bookings in Teams</span></span>

<span data-ttu-id="8825b-119">Teams 用 Microsoft 予約アプリは、デスクトップと web で利用できます。</span><span class="sxs-lookup"><span data-stu-id="8825b-119">Microsoft Bookings App for Teams is available on the desktop and web.</span></span> <span data-ttu-id="8825b-120">[ [Microsoft teams 内のアプリ](https://teams.microsoft.com/l/app/4c4ec2e8-4a2c-4bce-8d8f-00fc664a4e5b?source=store-copy-link) ] および [Teams 管理センター内の **アプリを管理** する] の下にあります。</span><span class="sxs-lookup"><span data-stu-id="8825b-120">It can be found under [Apps within Microsoft Teams](https://teams.microsoft.com/l/app/4c4ec2e8-4a2c-4bce-8d8f-00fc664a4e5b?source=store-copy-link) and under **Manage Apps** within Teams Admin Center.</span></span>

### <a name="control-access-to-bookings-within-your-organization"></a><span data-ttu-id="8825b-121">組織内の予約へのアクセスを制御する</span><span class="sxs-lookup"><span data-stu-id="8825b-121">Control access to Bookings within your organization</span></span>

<span data-ttu-id="8825b-122">予約アプリへのアクセス権を持つユーザーとアプリの特定の機能を制御するには、いくつかの方法があります。</span><span class="sxs-lookup"><span data-stu-id="8825b-122">There are several ways to control who has access to the Bookings app and to specific features of the app.</span></span> <span data-ttu-id="8825b-123">Microsoft 365 管理センターで Microsoft の予約を有効または無効にする方法、および選択したユーザーが予約予定表を作成できるようにするための予約アプリポリシーを作成する方法については、「 [Microsoft 予約へのアクセスを取得](https://support.microsoft.com/en-us/office/get-access-to-microsoft-bookings-5382dc07-aaa5-45c9-8767-502333b214ce)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8825b-123">To learn how to turn Microsoft Bookings on or off in the Microsoft 365 admin center, as well as how to create a Bookings app policy to allow selected users to create Bookings calendars, see [Get access to Microsoft Bookings](https://support.microsoft.com/en-us/office/get-access-to-microsoft-bookings-5382dc07-aaa5-45c9-8767-502333b214ce).</span></span> <span data-ttu-id="8825b-124">また、 [選択したユーザーのために予約アプリをピン留めする Teams アプリポリシーを作成](teams-app-setup-policies.md)する方法についても説明します。</span><span class="sxs-lookup"><span data-stu-id="8825b-124">You can also learn how to [Create a Teams app policy to pin the Bookings app for select users](teams-app-setup-policies.md).</span></span>

## <a name="recommended-meeting-policy-settings"></a><span data-ttu-id="8825b-125">推奨される会議のポリシー設定</span><span class="sxs-lookup"><span data-stu-id="8825b-125">Recommended Meeting Policy Settings</span></span>

<span data-ttu-id="8825b-126">予約に最適なエクスペリエンスを実現するには、スタッフ会議ポリシーを作成し **て、組織内の全員** に自動的に参加するようにします。</span><span class="sxs-lookup"><span data-stu-id="8825b-126">To enable the best experience for Bookings, create a staff meeting policy to automatically admit **Everyone in your organization** .</span></span> <span data-ttu-id="8825b-127">これにより、スタッフは予定に自動的に参加できるようになり、外部の出席者に対してロビーエクスペリエンスを有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="8825b-127">This will allow staff to join the appointment automatically and enable lobby experience for external attendees.</span></span> <span data-ttu-id="8825b-128">[会議へのユーザーの自動 admitting](meeting-policies-in-teams.md#automatically-admit-people)の詳細については、こちらを参照してください。</span><span class="sxs-lookup"><span data-stu-id="8825b-128">You can learn more about [automatically admitting people to meetings](meeting-policies-in-teams.md#automatically-admit-people).</span></span>

### <a name="optional-staff-approvals-setting"></a><span data-ttu-id="8825b-129">省略可能なスタッフ承認設定</span><span class="sxs-lookup"><span data-stu-id="8825b-129">Optional staff approvals setting</span></span>

<span data-ttu-id="8825b-130">追加のプライバシー設定として、[空き時間情報のスケジュールを設定する] をオンにしておくことを選択できます。そのためには、予約で予約されていない場合は、予約で予約することができます。</span><span class="sxs-lookup"><span data-stu-id="8825b-130">As an extra privacy setting, you can choose to require staff to opt in before their schedule availability information is shared through Bookings and before they can be booked for an appointment.</span></span>  

<span data-ttu-id="8825b-131">この設定を有効にするには、 **Microsoft 365 管理センター** の設定に移動して \> **Settings** \> **Settings** 、[ **予約** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="8825b-131">To enable this setting, go to **Microsoft 365 admin center** \> **Settings** \> **Settings** , then select **Bookings** .</span></span>

<span data-ttu-id="8825b-132">この設定を有効にすると、スタッフは、予約予定表へのメンバーシップを承認するように求められるメールを受信します。</span><span class="sxs-lookup"><span data-stu-id="8825b-132">With this setting turned on, staff will receive an email in which they are asked to approve membership to a booking calendar.</span></span>  

<span data-ttu-id="8825b-133">この機能は、世界中の Microsoft 365 および Office 365 のユーザーに段階的に展開されています。</span><span class="sxs-lookup"><span data-stu-id="8825b-133">This feature is gradually being rolled out worldwide to Microsoft 365 and Office 365 customers.</span></span> <span data-ttu-id="8825b-134">すべてのオプションが現在の環境で利用できない場合は、しばらくお待ちください。</span><span class="sxs-lookup"><span data-stu-id="8825b-134">If all options are not yet available in your environment, check back soon.</span></span>

## <a name="changing-your-default-domain-when-setting-up-bookings-mailboxes"></a><span data-ttu-id="8825b-135">予約メールボックスの設定時に既定のドメインを変更する</span><span class="sxs-lookup"><span data-stu-id="8825b-135">Changing your default domain when setting up Bookings mailboxes</span></span>

<span data-ttu-id="8825b-136">予約メールボックスをセットアップするときに、Microsoft 365 または Office 365 組織の既定のメールドメインが使用されます。</span><span class="sxs-lookup"><span data-stu-id="8825b-136">When setting up a Bookings mailbox, the default email domain of your Microsoft 365 or Office 365 organization is used.</span></span> <span data-ttu-id="8825b-137">ただし、外部の受信者に会議の出席依頼を送信するときに問題が発生する可能性があります。招待状はスパムとしてマークされ、受信者の [迷惑メール] フォルダーに移動されることがあります。そのため、受信者には招待が表示されない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="8825b-137">However, this can cause problems when sending meeting invites to external recipients; your invite might be flagged as spam and moved to the recipient’s junk folder, so the recipient might never see your invite.</span></span>

<span data-ttu-id="8825b-138">予約メールボックスを作成する前に、既定のドメインを変更することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="8825b-138">We recommend that you change the default domain prior to creating your Bookings mailbox.</span></span> <span data-ttu-id="8825b-139">この方法については、「ドメインに関する [FAQ](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq#how-do-i-set-or-change-the-default-domain-in-office-365)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8825b-139">For information on how to do this, see the [Domains FAQ](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq#how-do-i-set-or-change-the-default-domain-in-office-365).</span></span>

<span data-ttu-id="8825b-140">予約メールボックスが既に作成された後で既定のドメインを変更する必要がある場合は、PowerShell で次の操作を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="8825b-140">If you need to change the default domain after your Bookings mailbox has already been created, you can do so with PowerShell:</span></span>

```PowerShell
Set-Mailbox -identity business@domain.onmicrosoft.com -WindowsEmailAddress business@domain.com -EmailAddresses business@domain.com
```

<span data-ttu-id="8825b-141">詳細については、「 [Set-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-mailbox) 」コマンドレットの PowerShell ドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="8825b-141">For more information, see the PowerShell documentation for the [Set-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-mailbox) cmdlet.</span></span>

> [!NOTE]
> <span data-ttu-id="8825b-142">Exchange ハイブリッド構成を使用している場合は、既定のドメインを変更するときに、オンプレミスの Exchange と Exchange Online の間のメールフローを徹底的にテストすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="8825b-142">If you are using an Exchange hybrid configuration, we recommend that you thoroughly test mail flow between on-premises Exchange and Exchange Online when changing the default domain.</span></span>

## <a name="sending-feedback"></a><span data-ttu-id="8825b-143">フィードバックの送信</span><span class="sxs-lookup"><span data-stu-id="8825b-143">Sending feedback</span></span>

<span data-ttu-id="8825b-144">お客様からのフィードバックを歓迎します。</span><span class="sxs-lookup"><span data-stu-id="8825b-144">We welcome your feedback on:</span></span>

  - <span data-ttu-id="8825b-145">ユーザーエクスペリエンスまたは使いやすさ</span><span class="sxs-lookup"><span data-stu-id="8825b-145">User experience or ease of use</span></span>
  - <span data-ttu-id="8825b-146">機能のギャップまたは不足している機能</span><span class="sxs-lookup"><span data-stu-id="8825b-146">Feature gaps or missing functionality</span></span>
  - <span data-ttu-id="8825b-147">バグまたは問題</span><span class="sxs-lookup"><span data-stu-id="8825b-147">Bugs or issues</span></span>
  
<span data-ttu-id="8825b-148">フィードバックを送信するには、Teams の左側のナビゲーションバーの下部にある [ **ヘルプ** ] ボタンをクリックし、[問題の **報告** **] をクリック** します。</span><span class="sxs-lookup"><span data-stu-id="8825b-148">To send feedback, click the **Help** button near the bottom of the Teams left navigation bar, then click **Report a Problem** for **ALL** issues.</span></span> <span data-ttu-id="8825b-149">予約の問題を簡単に特定できるように、フィードバックレポートの最初に、"予約" についてのフィードバックを送信していることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="8825b-149">Please note at the beginning of your feedback report that you are sending feedback about "Bookings" so we can easily identify Bookings issues.</span></span>

## <a name="related-topics"></a><span data-ttu-id="8825b-150">関連項目</span><span class="sxs-lookup"><span data-stu-id="8825b-150">Related topics</span></span>

[<span data-ttu-id="8825b-151">エンドユーザー向けの予約ドキュメント</span><span class="sxs-lookup"><span data-stu-id="8825b-151">Bookings documentation for end users</span></span>](https://support.office.com/en-us/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b?ui=en-US&rs=en-US&ad=US#PickTab=Bookings)
