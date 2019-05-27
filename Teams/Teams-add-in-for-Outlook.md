---
title: Outlook で Microsoft Teams の会議アドインを使用する
author: ChuckEdmonson
ms.author: chucked
manager: serdars
audience: Admin
ms.date: 03/08/2019
ms.topic: article
ms.service: msteams
ms.reviewer: sonua
localization_priority: Normal
search.appverid: MET150
description: Microsoft Teams は、ユーザーが  Outlook から Teams の会議をスケジュール設定することができるようになるアドインを Outlook にインストールします。
ms.custom:
- NewAdminCenter_Update
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: fb6ba92185d797e3925ad56c8747fd504f40dccd
ms.sourcegitcommit: d010c615ee530deb34d79a1a62815ef0a52a2086
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/22/2019
ms.locfileid: "34404228"
---
<a name="use-the-teams-meeting-add-in-in-outlook"></a><span data-ttu-id="ab853-103">Outlook で Teams の会議アドインを使用する</span><span class="sxs-lookup"><span data-stu-id="ab853-103">Use the Teams Meeting add-in in Outlook</span></span>
=======================================
> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

<span data-ttu-id="ab853-104">Teams の会議アドインは、Microsoft Teams と Office 2013 または Office 2016 を自分の Windows PC にインストール済みのユーザーに対して、自動的にインストールされます。</span><span class="sxs-lookup"><span data-stu-id="ab853-104">The Teams Meeting add-in is automatically installed for users who have Microsoft Teams and either Office 2013 or Office 2016 installed on their Windows PC.</span></span> <span data-ttu-id="ab853-105">Teams の会議アドインは、ユーザーが使用する Outlook の [予定表] リボン上に表示されます。</span><span class="sxs-lookup"><span data-stu-id="ab853-105">Users will see the Teams Meeting add-in on the Outlook Calendar ribbon.</span></span> 

![Outlook リボン上の Teams アドインのスクリーンショット。](media/Teams-add-in-for-Outlook.png)

> [!NOTE]
> <span data-ttu-id="ab853-107">Windows 7ユーザーは、Teams Meetingアドインを機能させるために、[Update for Universal C Runtime in Windows](https://support.microsoft.com/help/2999226/update-for-universal-c-runtime-in-windows)をインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="ab853-107">Windows 7 users must install the [Update for Universal C Runtime in Windows](https://support.microsoft.com/help/2999226/update-for-universal-c-runtime-in-windows) for the Teams Meeting add-in to work.</span></span>

<span data-ttu-id="ab853-108">Teams の会議アドインが表示されないユーザーに対しては、Outlook と Teams を閉じて、先に Teams クライアントを再起動してから Teams にサインインし、次に Outlook クライアントを再起動する操作を順に行うよう指示します。</span><span class="sxs-lookup"><span data-stu-id="ab853-108">If users do not see the Teams Meeting add-in, instruct them to close Outlook and Teams, then restart the Teams client first, then sign in to Teams, and then restart the Outlook client, in that specific order.</span></span>

> [!NOTE]
> <span data-ttu-id="ab853-109">Outlook で運用ビルド16.20 以降を実行している場合、outlook for Mac の [Teams 会議] ボタンが outlook for Mac リボンに表示されます。</span><span class="sxs-lookup"><span data-stu-id="ab853-109">The Teams Meeting button in Outlook for Mac will appear in the Outlook for Mac ribbon if Outlook is running Production Build 16.20 and later.</span></span>

## <a name="authentication-requirements"></a><span data-ttu-id="ab853-110">認証要件</span><span class="sxs-lookup"><span data-stu-id="ab853-110">Authentication requirements</span></span>

<span data-ttu-id="ab853-111">Teams の会議アドインでは、ユーザーが認証要件を使用して Teams にサインインすることが必要になります。</span><span class="sxs-lookup"><span data-stu-id="ab853-111">The Teams Meeting add-in requires users to sign in to Teams using Modern Authentication.</span></span> <span data-ttu-id="ab853-112">ユーザーがこの方法を使用せずにサインインしても、Teams クライアントを使用することはできますが、Outlook アドインを使用して Teams のオンライン会議をスケジュール設定することはできません。</span><span class="sxs-lookup"><span data-stu-id="ab853-112">If users do not use this method to sign in, they’ll still be able to use the Teams client, but will be unable to schedule Teams online meetings using the Outlook add-in.</span></span> <span data-ttu-id="ab853-113">これを修正するには、次のいずれかを実行します。</span><span class="sxs-lookup"><span data-stu-id="ab853-113">You can fix this by doing one of the following:</span></span>

- <span data-ttu-id="ab853-114">先進認証が組織に対して構成されていない場合は、先進認証を構成します。</span><span class="sxs-lookup"><span data-stu-id="ab853-114">If Modern Authentication is not configured for your organization, you should configure Modern Authentication.</span></span>
- <span data-ttu-id="ab853-115">先進認証が構成されていているのにダイアログ ボックスでユーザーが無効になってしまう場合は、それらのユーザーに対して多要素認証を使用してサインインし直すよう指示します。</span><span class="sxs-lookup"><span data-stu-id="ab853-115">If Modern Authentication is configured, but they cancelled out on the dialog box, you should instruct users to sign in again using multi-factor authentication.</span></span>

<span data-ttu-id="ab853-116">認証を構成する方法の詳細については、「[Microsoft Teams での ID モデルと認証](identify-models-authentication.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="ab853-116">To learn more about how to configure authentication, see [Identity models and authentication in Microsoft Teams](identify-models-authentication.md).</span></span>

## <a name="enable-private-meetings"></a><span data-ttu-id="ab853-117">プライベート会議を有効にする</span><span class="sxs-lookup"><span data-stu-id="ab853-117">Enable private meetings</span></span>

<span data-ttu-id="ab853-118">プラグインを展開するには、Microsoft Teams管理センターで [Allow scheduling for private meetings (プライベート会議の予約を許可する)]を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="ab853-118">Allow scheduling for private meetings must be enabled in the Microsoft Teams admin center for the plug-in to get deployed.</span></span> <span data-ttu-id="ab853-119">管理センターで**Meetings** > **Meeting Policies**に行き、**一般的な**セクションで、**Allow scheduling private meetings**をオンに切り替えるます。)</span><span class="sxs-lookup"><span data-stu-id="ab853-119">In the admin center, go to **Meetings** > **Meeting Policies**, and in the **General** section, toggle **Allow scheduling private meetings** to On.)</span></span>

![Microsoft Teams管理センターの設定のスクリーンショット。](media/teams-add-in-for-outlook-image1.png)

<span data-ttu-id="ab853-121">Teams クライアントはユーザーが必要としているのが 32 ビット版か 64 ビット版かを判断して正しいアドインをインストールします。</span><span class="sxs-lookup"><span data-stu-id="ab853-121">The Teams client installs the correct add-in by determining if users need the 32-bit or 64-bit version.</span></span>

> [!NOTE]
> <span data-ttu-id="ab853-122">ユーザーは最新のアドインを利用できるようになるために Teams のインストールまたはアップグレード後に Outlook の再起動が必要になる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="ab853-122">Users might need to restart Outlook after an installation or upgrade of Teams to get the latest add-in.</span></span>

## <a name="other-considerations"></a><span data-ttu-id="ab853-123">その他の考慮事項</span><span class="sxs-lookup"><span data-stu-id="ab853-123">Other considerations</span></span>

<span data-ttu-id="ab853-124">Teams の会議アドインは継続して機能が開発されていますので、次について認識しておいてください。</span><span class="sxs-lookup"><span data-stu-id="ab853-124">The Teams Meeting add-in is still building functionality, so be aware of the following:</span></span>
- <span data-ttu-id="ab853-125">会議のオプションは現時点では使用できません。</span><span class="sxs-lookup"><span data-stu-id="ab853-125">Meeting options are currently not available.</span></span>
- <span data-ttu-id="ab853-126">現在のところ、会議に招待できるのは自分の会社内のユーザーのみで、外部ユーザーは会議に参加することができません。</span><span class="sxs-lookup"><span data-stu-id="ab853-126">Currently, you can only invite people from within your company, as it is not yet possible for external users to join meetings.</span></span>
- <span data-ttu-id="ab853-127">このアドインは、特定の参加者でスケジュール設定された会議向けで、チャネル内の会議向けではありません。</span><span class="sxs-lookup"><span data-stu-id="ab853-127">The add-in is for scheduled meetings with specific participants, not for meetings in a channel.</span></span> <span data-ttu-id="ab853-128">チャネル会議は Teams 内でスケジュール設定される必要があります。</span><span class="sxs-lookup"><span data-stu-id="ab853-128">Channel meetings must be scheduled from within Teams.</span></span> <span data-ttu-id="ab853-129">現在、Outlook の Teams の会議アドインを利用できるのは Windows ユーザーのみですが、Mac 向けのサポートも近日中に予定されています。</span><span class="sxs-lookup"><span data-stu-id="ab853-129">Currently, the Teams Meeting add-in in Outlook is only available for Windows users, but support for Mac is coming.</span></span>
- <span data-ttu-id="ab853-130">認証プロキシがユーザーの PC および Teams サービスのネットワーク パス内にある場合、アドインは機能しません。</span><span class="sxs-lookup"><span data-stu-id="ab853-130">The add-in will not work if an Authentication Proxy is in the network path of user's PC and Teams Services.</span></span>
- <span data-ttu-id="ab853-131">アドインを段階的にロールアウト中で、あなたの組織ではまだ利用できない場合があります。</span><span class="sxs-lookup"><span data-stu-id="ab853-131">The add-in is being rolled out incrementally and might not be available for your organization yet.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="ab853-132">トラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="ab853-132">Troubleshooting</span></span>

<span data-ttu-id="ab853-133">Teams Meeting add-in for Outlook のアドインをインストールできない場合は、次のトラブルシューティングの手順を試してください。</span><span class="sxs-lookup"><span data-stu-id="ab853-133">If you cannot get the Teams Meeting add-in for Outlook to install, try these troubleshooting steps.</span></span>

- <span data-ttu-id="ab853-134">Outlook デスクトップ クライアントのすべての利用可能な更新プログラムが適用されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="ab853-134">Ensure all available updates for Outlook desktop client have been applied</span></span> 
- <span data-ttu-id="ab853-135">Teamsのデスクトップ クライアントを再起動します。</span><span class="sxs-lookup"><span data-stu-id="ab853-135">Restart the Teams desktop client.</span></span>
- <span data-ttu-id="ab853-136">[Teamsのデスクトップ クライアント]からサインアウトして、もう一度サインインします。</span><span class="sxs-lookup"><span data-stu-id="ab853-136">Sign out and then sign back in to the Teams desktop client.</span></span>
- <span data-ttu-id="ab853-137">Outlook デスクトップ クライアントを再起動します。</span><span class="sxs-lookup"><span data-stu-id="ab853-137">Restart the Outlook desktop client.</span></span> <span data-ttu-id="ab853-138">(管理者モードで Outlook が実行されていないことを確認してください。)</span><span class="sxs-lookup"><span data-stu-id="ab853-138">(Make sure Outlook isn’t running in admin mode.)</span></span>
- <span data-ttu-id="ab853-139">ログインしているユーザー アカウント名にスペースが含まれていないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="ab853-139">Make sure the logged-in user account name does not contain spaces.</span></span> <span data-ttu-id="ab853-140">これは既知の問題であり、今後のビルドで修正される予定です。</span><span class="sxs-lookup"><span data-stu-id="ab853-140">(This is a known issue, and will be fixed in a future update.)</span></span>
- <span data-ttu-id="ab853-141">シングル サインオン (SSO) が有効になっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="ab853-141">Make sure single sign-on (SSO) is enabled.</span></span>

<span data-ttu-id="ab853-142">アドインを無効にする方法につぃての全般的なガイドラインについては、「[Office プログラムでアドインを表示、管理、インストールする](https://support.office.com/article/View-manage-and-install-add-ins-in-Office-programs-16278816-1948-4028-91E5-76DCA5380F8D)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="ab853-142">For general guidance about how to disable add-ins, see [View, manage, and install add-ins in Office programs](https://support.office.com/article/View-manage-and-install-add-ins-in-Office-programs-16278816-1948-4028-91E5-76DCA5380F8D).</span></span>

<span data-ttu-id="ab853-143">Microsoft Teams での会議と通話については[こちら](https://support.office.com/article/Meetings-and-calls-d92432d5-dd0f-4d17-8f69-06096b6b48a8)をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="ab853-143">Learn more about [meetings and calling in Microsoft Teams](https://support.office.com/article/Meetings-and-calls-d92432d5-dd0f-4d17-8f69-06096b6b48a8).</span></span>

[!INCLUDE [new-feature-availability](includes/new-feature-availability.md)]

