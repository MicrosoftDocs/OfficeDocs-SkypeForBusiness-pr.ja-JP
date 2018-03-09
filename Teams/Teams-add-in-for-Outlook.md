---
title: "Outlook で Microsoft Teams の会議アドインを使用する"
author: ChuckEdmonson
ms.author: chucked
manager: serdars
ms.date: 01/23/2018
ms.topic: article
ms.service: msteams
ms.reviewer: ninadara
description: "Microsoft Teams は、ユーザーが  Outlook から Teams の会議をスケジュール設定することができるようになるアドインを Outlook にインストールします。"
ms.custom:
- NewAdminCenter_Update
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: a2fb35e720d100e6bb2130fbacf16197397f201c
ms.sourcegitcommit: 85105cb4e42ae8eb6e7e76eaf6d4dd5b9568cf41
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2018
---
<a name="use-the-teams-meeting-add-in-in-outlook"></a><span data-ttu-id="449cc-103">Outlook で Teams の会議アドインを使用する</span><span class="sxs-lookup"><span data-stu-id="449cc-103">Use the Teams Meeting add-in in Outlook</span></span>
=======================================

<span data-ttu-id="449cc-104">Teams の会議アドインは、Microsoft Teams と Office 2013 または Office 2016 を自分の Windows PC にインストール済みのユーザーに対して、自動的にインストールされます。</span><span class="sxs-lookup"><span data-stu-id="449cc-104">The Teams Meeting add-in is automatically installed for users who have Microsoft Teams and either Office 2013 or Office 2016 installed on their Windows PC.</span></span> <span data-ttu-id="449cc-105">Teams の会議アドインは、ユーザーが使用する Outlook の [予定表] リボン上に表示されます。</span><span class="sxs-lookup"><span data-stu-id="449cc-105">Users will see the Teams Meeting add-in on the Outlook Calendar ribbon.</span></span> 

![Outlook リボン上の Teams アドインのスクリーンショット。](media/Teams-add-in-for-Outlook.png)

<span data-ttu-id="449cc-107">Teams の会議アドインが表示されないユーザーに対しては、Outlook と Teams を閉じて、先に Teams クライアントを再起動してから Teams にサインインし、次に Outlook クライアントを再起動する操作を順に行うよう指示します。</span><span class="sxs-lookup"><span data-stu-id="449cc-107">If users do not see the Teams Meeting add-in, instruct them to close Outlook and Teams, then restart the Teams client first, then sign in to Teams, and then restart the Outlook client, in that specific order.</span></span>

> [!NOTE]
> <span data-ttu-id="449cc-108">Outlook 用の Teams の会議アドインは、現時点では Mac ユーザーは利用できません。</span><span class="sxs-lookup"><span data-stu-id="449cc-108">The Teams Meeting add-in for Outlook is currently not available for Mac users.</span></span>

## <a name="authentication-requirements"></a><span data-ttu-id="449cc-109">認証要件</span><span class="sxs-lookup"><span data-stu-id="449cc-109">Authentication requirements</span></span>

<span data-ttu-id="449cc-110">Teams の会議アドインでは、ユーザーが認証要件を使用して Teams にサインインすることが必要になります。</span><span class="sxs-lookup"><span data-stu-id="449cc-110">The Teams Meeting add-in requires users to sign in to Teams using Modern Authentication.</span></span> <span data-ttu-id="449cc-111">ユーザーがこの方法を使用せずにサインインしても、Teams クライアントを使用することはできますが、Outlook アドインを使用して Teams のオンライン会議をスケジュール設定することはできません。</span><span class="sxs-lookup"><span data-stu-id="449cc-111">If users do not use this method to sign in, they’ll still be able to use the Teams client, but will be unable to schedule Teams online meetings using the Outlook add-in.</span></span> <span data-ttu-id="449cc-112">これを修正するには、次のいずれかを実行します。</span><span class="sxs-lookup"><span data-stu-id="449cc-112">You can fix this by doing one of the following:</span></span>

- <span data-ttu-id="449cc-113">先進認証が組織に対して構成されていない場合は、先進認証を構成します。</span><span class="sxs-lookup"><span data-stu-id="449cc-113">If Modern Authentication is not configured for your organization, you should configure Modern Authentication.</span></span>
- <span data-ttu-id="449cc-114">先進認証が構成されていているのにダイアログ ボックスでユーザーが無効になってしまう場合は、それらのユーザーに対して多要素認証を使用してサインインし直すよう指示します。</span><span class="sxs-lookup"><span data-stu-id="449cc-114">If Modern Authentication is configured, but they cancelled out on the dialog box, you should instruct users to sign in again using multi-factor authentication.</span></span>

<span data-ttu-id="449cc-115">認証を構成する方法の詳細については、「[Microsoft Teams での ID モデルと認証](identify-models-authentication.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="449cc-115">To learn more about how to configure authentication, see [Identity models and authentication in Microsoft Teams](identify-models-authentication.md).</span></span>

## <a name="enable-private-meetings"></a><span data-ttu-id="449cc-116">プライベート会議を有効にする</span><span class="sxs-lookup"><span data-stu-id="449cc-116">Enable private meetings</span></span>

<span data-ttu-id="449cc-117">プラグインがデプロイされるようにするには、[Office 365 管理センター](https://portal.office.com/adminportal/home)で [Allow scheduling for private meetings (プライベート会議の予約を許可する)] が有効になっている必要があります。</span><span class="sxs-lookup"><span data-stu-id="449cc-117">Allow scheduling for private meetings must be enabled from the [Office 365 admin center](https://portal.office.com/adminportal/home) for the plug-in to get deployed.</span></span>

![Office 365 管理センターの [通話と会議] セクションの設定を示すスクリーンショット。](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image9.png)

<span data-ttu-id="449cc-119">Teams クライアントはユーザーが必要としているのが 32 ビット版か 64 ビット版かを判断して正しいアドインをインストールします。</span><span class="sxs-lookup"><span data-stu-id="449cc-119">The Teams client installs the correct add-in by determining if users need the 32-bit or 64-bit version.</span></span>

> [!NOTE]
> <span data-ttu-id="449cc-120">ユーザーは最新のアドインを利用できるようになるために Teams のインストールまたはアップグレード後に Outlook の再起動が必要になる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="449cc-120">Users might need to restart Outlook after an installation or upgrade of Teams to get the latest add-in.</span></span>

## <a name="other-considerations"></a><span data-ttu-id="449cc-121">その他の考慮事項</span><span class="sxs-lookup"><span data-stu-id="449cc-121">Other planning considerations</span></span>

<span data-ttu-id="449cc-122">Teams の会議アドインは継続して機能が開発されていますので、次について認識しておいてください。</span><span class="sxs-lookup"><span data-stu-id="449cc-122">The Teams Meeting add-in is still building functionality, so be aware of the following:</span></span>
- <span data-ttu-id="449cc-123">記録、投票、ホワイトボードの使用などの、一部のオンライン会議の機能はまだ利用できません。</span><span class="sxs-lookup"><span data-stu-id="449cc-123">Some online meeting features, such as recording, polling, and whiteboarding are not yet available.</span></span>
- <span data-ttu-id="449cc-124">会議のオプションは現時点では使用できません。</span><span class="sxs-lookup"><span data-stu-id="449cc-124">Meeting options are currently not available.</span></span>
- <span data-ttu-id="449cc-125">現在のところ、会議に招待できるのは自分の会社内のユーザーのみで、外部ユーザーは会議に参加することができません。</span><span class="sxs-lookup"><span data-stu-id="449cc-125">Currently, you can only invite people from within your company, as it is not yet possible for external users to join meetings.</span></span>
- <span data-ttu-id="449cc-126">このアドインは、特定の参加者でスケジュール設定された会議向けで、チャネル内の会議向けではありません。</span><span class="sxs-lookup"><span data-stu-id="449cc-126">The add-in is for scheduled meetings with specific participants, not for meetings in a channel.</span></span> <span data-ttu-id="449cc-127">チャネル会議は Teams 内でスケジュール設定される必要があります。</span><span class="sxs-lookup"><span data-stu-id="449cc-127">Channel meetings must be scheduled from within Teams.</span></span> <span data-ttu-id="449cc-128">現在、Outlook の Teams の会議アドインを利用できるのは Windows ユーザーのみですが、Mac 向けのサポートも近日中に予定されています。</span><span class="sxs-lookup"><span data-stu-id="449cc-128">Currently, the Teams Meeting add-in in Outlook is only available for Windows users, but support for Mac is coming.</span></span>
- <span data-ttu-id="449cc-129">認証プロキシがユーザーの PC および Teams サービスのネットワーク パス内にある場合、アドインは機能しません。</span><span class="sxs-lookup"><span data-stu-id="449cc-129">The add-in will not work if an Authentication Proxy is in the network path of user's PC and Teams Services.</span></span>

<span data-ttu-id="449cc-130">アドインを無効にする方法につぃての全般的なガイドラインについては、「[Office プログラムでアドインを表示、管理、インストールする](https://support.office.com/article/View-manage-and-install-add-ins-in-Office-programs-16278816-1948-4028-91E5-76DCA5380F8D)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="449cc-130">For general guidance about how to disable add-ins, see [View, manage, and install add-ins in Office programs](https://support.office.com/article/View-manage-and-install-add-ins-in-Office-programs-16278816-1948-4028-91E5-76DCA5380F8D).</span></span>

<span data-ttu-id="449cc-131">Microsoft Teams での会議と通話については[こちら](https://support.office.com/article/Meetings-and-calls-d92432d5-dd0f-4d17-8f69-06096b6b48a8)をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="449cc-131">Learn more about [meetings and calling in Microsoft Teams](https://support.office.com/article/Meetings-and-calls-d92432d5-dd0f-4d17-8f69-06096b6b48a8).</span></span>

