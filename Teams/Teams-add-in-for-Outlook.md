---
title: Outlook で Microsoft Teams の会議アドインを使用する
author: ChuckEdmonson
ms.author: chucked
manager: serdars
audience: Admin
ms.date: 07/16/2018
ms.topic: article
ms.service: msteams
ms.reviewer: ''
localization_priority: Normal
search.appverid: MET150
description: Microsoft Teams は、ユーザーが  Outlook から Teams の会議をスケジュール設定することができるようになるアドインを Outlook にインストールします。
ms.custom:
- NewAdminCenter_Update
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 07cc04f47da980bfb5a637c1cfe6bc2b72a26f8f
ms.sourcegitcommit: 6212645c485c41aafe1206bf7d39171ce35837b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/22/2018
ms.locfileid: "24967360"
---
<a name="use-the-teams-meeting-add-in-in-outlook"></a><span data-ttu-id="0973c-103">Outlook で Teams の会議アドインを使用する</span><span class="sxs-lookup"><span data-stu-id="0973c-103">Use the Teams Meeting add-in in Outlook</span></span>
=======================================
> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

<span data-ttu-id="0973c-104">Teams の会議アドインは、Microsoft Teams と Office 2013 または Office 2016 を自分の Windows PC にインストール済みのユーザーに対して、自動的にインストールされます。</span><span class="sxs-lookup"><span data-stu-id="0973c-104">The Teams Meeting add-in is automatically installed for users who have Microsoft Teams and either Office 2013 or Office 2016 installed on their Windows PC.</span></span> <span data-ttu-id="0973c-105">Teams の会議アドインは、ユーザーが使用する Outlook の [予定表] リボン上に表示されます。</span><span class="sxs-lookup"><span data-stu-id="0973c-105">Users will see the Teams Meeting add-in on the Outlook Calendar ribbon.</span></span> 

![Outlook リボン上の Teams アドインのスクリーンショット。](media/Teams-add-in-for-Outlook.png)

<span data-ttu-id="0973c-107">Teams の会議アドインが表示されないユーザーに対しては、Outlook と Teams を閉じて、先に Teams クライアントを再起動してから Teams にサインインし、次に Outlook クライアントを再起動する操作を順に行うよう指示します。</span><span class="sxs-lookup"><span data-stu-id="0973c-107">If users do not see the Teams Meeting add-in, instruct them to close Outlook and Teams, then restart the Teams client first, then sign in to Teams, and then restart the Outlook client, in that specific order.</span></span>

> [!NOTE]
> <span data-ttu-id="0973c-108">Outlook 用の Teams の会議アドインは、現時点では Mac ユーザーは利用できません。</span><span class="sxs-lookup"><span data-stu-id="0973c-108">The Teams Meeting add-in for Outlook is currently not available for Mac users.</span></span>

## <a name="authentication-requirements"></a><span data-ttu-id="0973c-109">認証要件</span><span class="sxs-lookup"><span data-stu-id="0973c-109">Authentication requirements</span></span>

<span data-ttu-id="0973c-110">Teams の会議アドインでは、ユーザーが認証要件を使用して Teams にサインインすることが必要になります。</span><span class="sxs-lookup"><span data-stu-id="0973c-110">The Teams Meeting add-in requires users to sign in to Teams using Modern Authentication.</span></span> <span data-ttu-id="0973c-111">ユーザーがこの方法を使用せずにサインインしても、Teams クライアントを使用することはできますが、Outlook アドインを使用して Teams のオンライン会議をスケジュール設定することはできません。</span><span class="sxs-lookup"><span data-stu-id="0973c-111">If users do not use this method to sign in, they’ll still be able to use the Teams client, but will be unable to schedule Teams online meetings using the Outlook add-in.</span></span> <span data-ttu-id="0973c-112">これを修正するには、次のいずれかを実行します。</span><span class="sxs-lookup"><span data-stu-id="0973c-112">You can fix this by doing one of the following:</span></span>

- <span data-ttu-id="0973c-113">先進認証が組織に対して構成されていない場合は、先進認証を構成します。</span><span class="sxs-lookup"><span data-stu-id="0973c-113">If Modern Authentication is not configured for your organization, you should configure Modern Authentication.</span></span>
- <span data-ttu-id="0973c-114">先進認証が構成されていているのにダイアログ ボックスでユーザーが無効になってしまう場合は、それらのユーザーに対して多要素認証を使用してサインインし直すよう指示します。</span><span class="sxs-lookup"><span data-stu-id="0973c-114">If Modern Authentication is configured, but they cancelled out on the dialog box, you should instruct users to sign in again using multi-factor authentication.</span></span>

<span data-ttu-id="0973c-115">認証を構成する方法の詳細については、「[Microsoft Teams での ID モデルと認証](identify-models-authentication.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="0973c-115">To learn more about how to configure authentication, see [Identity models and authentication in Microsoft Teams](identify-models-authentication.md).</span></span>

## <a name="enable-private-meetings"></a><span data-ttu-id="0973c-116">プライベート会議を有効にする</span><span class="sxs-lookup"><span data-stu-id="0973c-116">Enable private meetings</span></span>

<span data-ttu-id="0973c-117">チームと Skype プラグインのビジネス管理センターの配置を取得するを有効にする必要があります秘密の会議のスケジュール設定を使用できます。</span><span class="sxs-lookup"><span data-stu-id="0973c-117">Allow scheduling for private meetings must be enabled in the Teams & Skype for Business Admin Center for the plug-in to get deployed.</span></span> <span data-ttu-id="0973c-118">**会議**には、管理センターで、 > **ミーティングのポリシー**、し、 **[全般**] セクションで、表示または非表示**プライベートな会議のスケジュールを許可する**にします)。</span><span class="sxs-lookup"><span data-stu-id="0973c-118">In the admin center, go to **Meetings** > **Meeting Policies**, and in the **General** section, toggle **Allow scheduling private meetings** to On.)</span></span>

![チームとビジネス管理センターの Skype の設定のスクリーン ショットです。](media/teams-add-in-for-outlook-image1.png)

<span data-ttu-id="0973c-120">Teams クライアントはユーザーが必要としているのが 32 ビット版か 64 ビット版かを判断して正しいアドインをインストールします。</span><span class="sxs-lookup"><span data-stu-id="0973c-120">The Teams client installs the correct add-in by determining if users need the 32-bit or 64-bit version.</span></span>

> [!NOTE]
> <span data-ttu-id="0973c-121">ユーザーは最新のアドインを利用できるようになるために Teams のインストールまたはアップグレード後に Outlook の再起動が必要になる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="0973c-121">Users might need to restart Outlook after an installation or upgrade of Teams to get the latest add-in.</span></span>

## <a name="other-considerations"></a><span data-ttu-id="0973c-122">その他の考慮事項</span><span class="sxs-lookup"><span data-stu-id="0973c-122">Other considerations</span></span>

<span data-ttu-id="0973c-123">Teams の会議アドインは継続して機能が開発されていますので、次について認識しておいてください。</span><span class="sxs-lookup"><span data-stu-id="0973c-123">The Teams Meeting add-in is still building functionality, so be aware of the following:</span></span>
- <span data-ttu-id="0973c-124">記録、投票、ホワイトボードの使用などの、一部のオンライン会議の機能はまだ利用できません。</span><span class="sxs-lookup"><span data-stu-id="0973c-124">Some online meeting features, such as recording, polling, and whiteboarding are not yet available.</span></span>
- <span data-ttu-id="0973c-125">会議のオプションは現時点では使用できません。</span><span class="sxs-lookup"><span data-stu-id="0973c-125">Meeting options are currently not available.</span></span>
- <span data-ttu-id="0973c-126">現在のところ、会議に招待できるのは自分の会社内のユーザーのみで、外部ユーザーは会議に参加することができません。</span><span class="sxs-lookup"><span data-stu-id="0973c-126">Currently, you can only invite people from within your company, as it is not yet possible for external users to join meetings.</span></span>
- <span data-ttu-id="0973c-127">このアドインは、特定の参加者でスケジュール設定された会議向けで、チャネル内の会議向けではありません。</span><span class="sxs-lookup"><span data-stu-id="0973c-127">The add-in is for scheduled meetings with specific participants, not for meetings in a channel.</span></span> <span data-ttu-id="0973c-128">チャネル会議は Teams 内でスケジュール設定される必要があります。</span><span class="sxs-lookup"><span data-stu-id="0973c-128">Channel meetings must be scheduled from within Teams.</span></span> <span data-ttu-id="0973c-129">現在、Outlook の Teams の会議アドインを利用できるのは Windows ユーザーのみですが、Mac 向けのサポートも近日中に予定されています。</span><span class="sxs-lookup"><span data-stu-id="0973c-129">Currently, the Teams Meeting add-in in Outlook is only available for Windows users, but support for Mac is coming.</span></span>
- <span data-ttu-id="0973c-130">認証プロキシがユーザーの PC および Teams サービスのネットワーク パス内にある場合、アドインは機能しません。</span><span class="sxs-lookup"><span data-stu-id="0973c-130">The add-in will not work if an Authentication Proxy is in the network path of user's PC and Teams Services.</span></span>
- <span data-ttu-id="0973c-131">アドインを段階的ロールアウトされているが、組織にまだ利用できない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="0973c-131">The add-in is being rolled out incrementally and might not be available for your organization yet.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="0973c-132">トラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="0973c-132">Troubleshooting</span></span>

<span data-ttu-id="0973c-133">アドインをインストールするのには Outlook のチーム会議出席できない場合は、これらのトラブルシューティング手順を実行してください。</span><span class="sxs-lookup"><span data-stu-id="0973c-133">If you cannot get the Teams Meeting add-in for Outlook to install, try these troubleshooting steps.</span></span>

- <span data-ttu-id="0973c-134">Outlook デスクトップ クライアントのすべての利用可能な更新プログラムが適用されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="0973c-134">Ensure all available updates for Outlook desktop client have been applied</span></span> 
- <span data-ttu-id="0973c-135">チームのデスクトップ クライアントを再起動します。</span><span class="sxs-lookup"><span data-stu-id="0973c-135">Restart the Teams desktop client.</span></span>
- <span data-ttu-id="0973c-136">サインアウトして、チームのデスクトップ クライアントにもう一度サインインします。</span><span class="sxs-lookup"><span data-stu-id="0973c-136">Sign out and then sign back in to the Teams desktop client.</span></span>
- <span data-ttu-id="0973c-137">Outlook デスクトップ クライアントを再起動します。</span><span class="sxs-lookup"><span data-stu-id="0973c-137">Restart the Outlook desktop client.</span></span> <span data-ttu-id="0973c-138">(Outlook は、管理者モードで実行されていないことを確認してください。)</span><span class="sxs-lookup"><span data-stu-id="0973c-138">(Make sure Outlook isn’t running in admin mode.)</span></span>
- <span data-ttu-id="0973c-139">ログインしているユーザー アカウント名にスペースが含まれていないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="0973c-139">Make sure the logged-in user account name does not contain spaces.</span></span> <span data-ttu-id="0973c-140">(これは既知の問題、今後のアップデートで修正される予定)</span><span class="sxs-lookup"><span data-stu-id="0973c-140">(This is a known issue, and will be fixed in a future update.)</span></span>
- <span data-ttu-id="0973c-141">シングル サインオン (SSO) が有効になっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="0973c-141">Make sure single sign-on (SSO) is enabled.</span></span>

<span data-ttu-id="0973c-142">アドインを無効にする方法につぃての全般的なガイドラインについては、「[Office プログラムでアドインを表示、管理、インストールする](https://support.office.com/article/View-manage-and-install-add-ins-in-Office-programs-16278816-1948-4028-91E5-76DCA5380F8D)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="0973c-142">For general guidance about how to disable add-ins, see [View, manage, and install add-ins in Office programs](https://support.office.com/article/View-manage-and-install-add-ins-in-Office-programs-16278816-1948-4028-91E5-76DCA5380F8D).</span></span>

<span data-ttu-id="0973c-143">Microsoft Teams での会議と通話については[こちら](https://support.office.com/article/Meetings-and-calls-d92432d5-dd0f-4d17-8f69-06096b6b48a8)をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="0973c-143">Learn more about [meetings and calling in Microsoft Teams](https://support.office.com/article/Meetings-and-calls-d92432d5-dd0f-4d17-8f69-06096b6b48a8).</span></span>

[!INCLUDE [new-feature-availability](includes/new-feature-availability.md)]

