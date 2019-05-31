---
title: Outlook で Microsoft Teams の会議アドインを使用する
author: ChuckEdmonson
ms.author: chucked
manager: serdars
audience: Admin
ms.date: 05/29/2019
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
ms.openlocfilehash: c9a5a17f729c8899c5fb7f7f97a65f9bc36c3080
ms.sourcegitcommit: e487637fc122727b41b37961f208ddc0d20a3fce
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/30/2019
ms.locfileid: "34591640"
---
<a name="use-the-teams-meeting-add-in-in-outlook"></a><span data-ttu-id="6b0c5-103">Outlook で Teams の会議アドインを使用する</span><span class="sxs-lookup"><span data-stu-id="6b0c5-103">Use the Teams Meeting add-in in Outlook</span></span>
=======================================

<span data-ttu-id="6b0c5-104">Teams 会議アドインを使用すると、ユーザーは Outlook から Teams 会議をスケジュールできます。</span><span class="sxs-lookup"><span data-stu-id="6b0c5-104">The Teams Meeting add-in lets users schedule a Teams meeting from Outlook.</span></span> <span data-ttu-id="6b0c5-105">Windows、Mac、web、モバイルの Outlook でアドインを使用できます。</span><span class="sxs-lookup"><span data-stu-id="6b0c5-105">The add-in is available for Outlook on Windows, Mac, web, and mobile.</span></span>

## <a name="teams-meeting-add-in-in-outlook-for-windows"></a><span data-ttu-id="6b0c5-106">Windows 版 Outlook の Teams 会議アドイン</span><span class="sxs-lookup"><span data-stu-id="6b0c5-106">Teams Meeting add-in in Outlook for Windows</span></span>

<span data-ttu-id="6b0c5-107">Teams の会議アドインは、Microsoft Teams と Office 2013 または Office 2016 を自分の Windows PC にインストール済みのユーザーに対して、自動的にインストールされます。</span><span class="sxs-lookup"><span data-stu-id="6b0c5-107">The Teams Meeting add-in is automatically installed for users who have Microsoft Teams and either Office 2013 or Office 2016 installed on their Windows PC.</span></span> <span data-ttu-id="6b0c5-108">Teams の会議アドインは、ユーザーが使用する Outlook の [予定表] リボン上に表示されます。</span><span class="sxs-lookup"><span data-stu-id="6b0c5-108">Users will see the Teams Meeting add-in on the Outlook Calendar ribbon.</span></span>

![Outlook リボンの Teams 会議アドインのスクリーンショット](media/Teams-add-in-for-Outlook.png)

> [!NOTE]
> - <span data-ttu-id="6b0c5-110">Teams の会議アドインが表示されないユーザーに対しては、Outlook と Teams を閉じて、先に Teams クライアントを再起動してから Teams にサインインし、次に Outlook クライアントを再起動する操作を順に行うよう指示します。</span><span class="sxs-lookup"><span data-stu-id="6b0c5-110">If users do not see the Teams Meeting add-in, instruct them to close Outlook and Teams, then restart the Teams client first, then sign in to Teams, and then restart the Outlook client, in that specific order.</span></span>
> - <span data-ttu-id="6b0c5-111">Windows 7 ユーザーは、Teams 会議アドインを使用するために windows の[windows でユニバーサル C ランタイムの更新プログラム](https://support.microsoft.com/help/2999226/update-for-universal-c-runtime-in-windows)をインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="6b0c5-111">Windows 7 users must install the [Update for Universal C Runtime in Windows](https://support.microsoft.com/help/2999226/update-for-universal-c-runtime-in-windows) in Windows for the Teams Meeting add-in to work.</span></span>

## <a name="teams-meeting-add-in-in-outlook-for-mac"></a><span data-ttu-id="6b0c5-112">Outlook for Mac の Teams 会議アドイン</span><span class="sxs-lookup"><span data-stu-id="6b0c5-112">Teams Meeting add-in in Outlook for Mac</span></span>

<span data-ttu-id="6b0c5-113">Outlook for Mac の office の [会議] ボタンは、16.24.414.0 を実行している場合、outlook for mac のリボンに表示されます。</span><span class="sxs-lookup"><span data-stu-id="6b0c5-113">The Teams Meeting button in Outlook for Mac will appear in the Outlook for Mac ribbon if Outlook is running Production Build 16.24.414.0 and later.</span></span>

<span data-ttu-id="6b0c5-114">ユーザーが [**送信**] をクリックすると、会議の座標 (チームの参加リンクとダイヤルイン番号) が会議の出席依頼に追加されます。</span><span class="sxs-lookup"><span data-stu-id="6b0c5-114">The meeting coordinates (the Teams join link and dial-in numbers) will be added to the meeting invite after the user clicks **Send**.</span></span>  

## <a name="teams-meeting-add-in-in-outlook-web-app"></a><span data-ttu-id="6b0c5-115">Outlook Web App の Teams 会議アドイン</span><span class="sxs-lookup"><span data-stu-id="6b0c5-115">Teams Meeting add-in in Outlook Web App</span></span>

<span data-ttu-id="6b0c5-116">ユーザーが新しい Outlook on the Web の以前のバージョンをお持ちの場合、Outlook Web App の [Teams 会議] ボタンが新しいイベントの作成の一部として表示されます。</span><span class="sxs-lookup"><span data-stu-id="6b0c5-116">The Teams Meetings button in Outlook Web App will appear as part of new event creation if the user is on an early version of the new Outlook on the web.</span></span> <span data-ttu-id="6b0c5-117">ユーザーが新しい Outlook on the web の初期バージョンを試す方法については、 [Outlook ブログ](https://techcommunity.microsoft.com/t5/Outlook-Blog/Designed-to-be-fast-The-Outlook-on-the-web-user-experience-gets/ba-p/234909?utm_source=t.co&utm_medium=referral)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6b0c5-117">See the [Outlook Blog](https://techcommunity.microsoft.com/t5/Outlook-Blog/Designed-to-be-fast-The-Outlook-on-the-web-user-experience-gets/ba-p/234909?utm_source=t.co&utm_medium=referral) to learn about how users can try the early version of the new Outlook on the web.</span></span>

![Outlook Web App の Teams 会議アドインのスクリーンショット](media/teams-meeting-add-in-web.png)

<span data-ttu-id="6b0c5-119">ユーザーが [**送信**] をクリックすると、会議の座標 (チームの参加リンクとダイヤルイン番号) が会議の出席依頼に追加されます。</span><span class="sxs-lookup"><span data-stu-id="6b0c5-119">The meeting coordinates (the Teams join link and dial-in numbers) will be added to the meeting invite after the user clicks **Send**.</span></span>  

## <a name="teams-meeting-add-in-in-outlook-mobile-ios-and-android"></a><span data-ttu-id="6b0c5-120">Outlook mobile (iOS と Android) での Teams 会議アドイン</span><span class="sxs-lookup"><span data-stu-id="6b0c5-120">Teams Meeting add-in in Outlook mobile (iOS and Android)</span></span>

<span data-ttu-id="6b0c5-121">[Teams 会議] ボタンは、Outlook iOS と Android アプリの最新のビルドに表示されます。</span><span class="sxs-lookup"><span data-stu-id="6b0c5-121">The Teams Meeting button shows up in latest builds of the Outlook iOS and Android app.</span></span>

![Outlook mobile の Teams 会議アドインのスクリーンショット](media/teams-meeting-add-in-mobile.png)

<span data-ttu-id="6b0c5-123">ユーザーが [**送信**] をクリックすると、会議の座標 (チームの参加リンクとダイヤルイン番号) が会議の出席依頼に追加されます。</span><span class="sxs-lookup"><span data-stu-id="6b0c5-123">The meeting coordinates (the Teams join link and dial-in numbers) will be added to the meeting invite after the user clicks **Send**.</span></span>  

## <a name="authentication-requirements"></a><span data-ttu-id="6b0c5-124">認証要件</span><span class="sxs-lookup"><span data-stu-id="6b0c5-124">Authentication requirements</span></span>

<span data-ttu-id="6b0c5-125">Teams の会議アドインでは、ユーザーが認証要件を使用して Teams にサインインすることが必要になります。</span><span class="sxs-lookup"><span data-stu-id="6b0c5-125">The Teams Meeting add-in requires users to sign in to Teams using Modern Authentication.</span></span> <span data-ttu-id="6b0c5-126">ユーザーがこの方法を使用せずにサインインしても、Teams クライアントを使用することはできますが、Outlook アドインを使用して Teams のオンライン会議をスケジュール設定することはできません。</span><span class="sxs-lookup"><span data-stu-id="6b0c5-126">If users do not use this method to sign in, they’ll still be able to use the Teams client, but will be unable to schedule Teams online meetings using the Outlook add-in.</span></span> <span data-ttu-id="6b0c5-127">これを修正するには、次のいずれかを実行します。</span><span class="sxs-lookup"><span data-stu-id="6b0c5-127">You can fix this by doing one of the following:</span></span>

- <span data-ttu-id="6b0c5-128">先進認証が組織に対して構成されていない場合は、先進認証を構成します。</span><span class="sxs-lookup"><span data-stu-id="6b0c5-128">If Modern Authentication is not configured for your organization, you should configure Modern Authentication.</span></span>
- <span data-ttu-id="6b0c5-129">モダン認証が設定されているが、ダイアログボックスでキャンセルされた場合は、多要素認証を使用してもう一度サインインするようにユーザーに指示する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6b0c5-129">If Modern Authentication is configured, but they canceled out on the dialog box, you should instruct users to sign in again using multi-factor authentication.</span></span>

<span data-ttu-id="6b0c5-130">認証を構成する方法の詳細については、「[Microsoft Teams での ID モデルと認証](identify-models-authentication.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="6b0c5-130">To learn more about how to configure authentication, see [Identity models and authentication in Microsoft Teams](identify-models-authentication.md).</span></span>

## <a name="enable-private-meetings"></a><span data-ttu-id="6b0c5-131">プライベート会議を有効にする</span><span class="sxs-lookup"><span data-stu-id="6b0c5-131">Enable private meetings</span></span>

<span data-ttu-id="6b0c5-132">アドインを展開できるようにするには、Microsoft Teams 管理センターで**プライベート会議のスケジュール**を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="6b0c5-132">**Allow scheduling for private meetings** must be enabled in the Microsoft Teams admin center for the add-in to get deployed.</span></span> <span data-ttu-id="6b0c5-133">管理センターで**Meetings** > **Meeting Policies**に行き、**一般的な**セクションで、**Allow scheduling private meetings**をオンに切り替えるます。)</span><span class="sxs-lookup"><span data-stu-id="6b0c5-133">In the admin center, go to **Meetings** > **Meeting Policies**, and in the **General** section, toggle **Allow scheduling private meetings** to On.)</span></span>

![Microsoft Teams管理センターの設定のスクリーンショット。](media/teams-add-in-for-outlook-image1.png)

<span data-ttu-id="6b0c5-135">Teams クライアントはユーザーが必要としているのが 32 ビット版か 64 ビット版かを判断して正しいアドインをインストールします。</span><span class="sxs-lookup"><span data-stu-id="6b0c5-135">The Teams client installs the correct add-in by determining if users need the 32-bit or 64-bit version.</span></span>

> [!NOTE]
> <span data-ttu-id="6b0c5-136">ユーザーは最新のアドインを利用できるようになるために Teams のインストールまたはアップグレード後に Outlook の再起動が必要になる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="6b0c5-136">Users might need to restart Outlook after an installation or upgrade of Teams to get the latest add-in.</span></span>

## <a name="teams-upgrade-policy-and-the-teams-meeting-add-in-for-outlook"></a><span data-ttu-id="6b0c5-137">Teams のアップグレードポリシーと Outlook 用 Teams 会議アドイン</span><span class="sxs-lookup"><span data-stu-id="6b0c5-137">Teams upgrade policy and the Teams Meeting add-in for Outlook</span></span>

<span data-ttu-id="6b0c5-138">お客様は[、Skype For business から Teams へのアップグレードを選ぶ](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)ことができます。</span><span class="sxs-lookup"><span data-stu-id="6b0c5-138">Customers can [choose their upgrade journey from Skype for Business to Teams](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md).</span></span> <span data-ttu-id="6b0c5-139">テナント管理者は、チームの共存モードを使用して、ユーザーに対してこのような旅を定義できます。</span><span class="sxs-lookup"><span data-stu-id="6b0c5-139">Tenant admins can use the Teams co-existence mode to define this journey for their users.</span></span> <span data-ttu-id="6b0c5-140">テナント管理者は、ユーザーが Skype for Business (諸島モード) と共にチームを使用できるようにするオプションを備えています。</span><span class="sxs-lookup"><span data-stu-id="6b0c5-140">Tenant admins have the option to enable users to use Teams alongside Skype for Business (Islands mode).</span></span> 

<span data-ttu-id="6b0c5-141">孤島モードのユーザーが Outlook で会議をスケジュールする場合、通常は、Skype for Business と Teams のどちらの会議をスケジュールするかを選ぶことができます。</span><span class="sxs-lookup"><span data-stu-id="6b0c5-141">When users who are in Island mode schedule a meeting in Outlook, they typically expect to be able to choose whether to schedule a Skype for Business or a Teams meeting.</span></span> <span data-ttu-id="6b0c5-142">Outlook on the web、Outlook Windows、Outlook Mac では、島々モードでは、ユーザーに Skype for Business アドインと Teams アドインの両方が表示されます。</span><span class="sxs-lookup"><span data-stu-id="6b0c5-142">In Outlook on the web, Outlook Windows, and Outlook Mac, users see both Skype for Business and Teams add-ins when in Islands mode.</span></span> <span data-ttu-id="6b0c5-143">初期リリースの一部の制限により、Outlook mobile では、Skype for Business**または**Teams 会議の作成のみがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="6b0c5-143">Due to certain limitations in the initial release, Outlook mobile can only support creating Skype for Business **or** Teams meetings.</span></span> <span data-ttu-id="6b0c5-144">詳細については、次の表を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6b0c5-144">See the following table for details.</span></span>

| <span data-ttu-id="6b0c5-145">Teams 管理センターでの共存モード</span><span class="sxs-lookup"><span data-stu-id="6b0c5-145">Coexistence mode in the Teams admin center</span></span> | <span data-ttu-id="6b0c5-146">Outlook mobile の既定の会議プロバイダー</span><span class="sxs-lookup"><span data-stu-id="6b0c5-146">Default meetings provider in Outlook mobile</span></span> |
| --------------------------------------|---------------------------------------------|
| <span data-ttu-id="6b0c5-147">アイランド</span><span class="sxs-lookup"><span data-stu-id="6b0c5-147">Islands</span></span> | <span data-ttu-id="6b0c5-148">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="6b0c5-148">Skype for Business</span></span> |
| <span data-ttu-id="6b0c5-149">Skype for Business のみ</span><span class="sxs-lookup"><span data-stu-id="6b0c5-149">Skype for Business only</span></span> | <span data-ttu-id="6b0c5-150">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="6b0c5-150">Skype for Business</span></span> |
| <span data-ttu-id="6b0c5-151">Skype for Business と Teams でのコラボレーション</span><span class="sxs-lookup"><span data-stu-id="6b0c5-151">Skype for Business with Teams collaboration</span></span> | <span data-ttu-id="6b0c5-152">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="6b0c5-152">Skype for Business</span></span> |
| <span data-ttu-id="6b0c5-153">Skype for Business と Teams でのコラボレーションおよび会議</span><span class="sxs-lookup"><span data-stu-id="6b0c5-153">Skype for Business with Teams collaboration and meetings</span></span> | <span data-ttu-id="6b0c5-154">Teams</span><span class="sxs-lookup"><span data-stu-id="6b0c5-154">Teams</span></span> |
| <span data-ttu-id="6b0c5-155">Teams のみ</span><span class="sxs-lookup"><span data-stu-id="6b0c5-155">Teams only</span></span> | <span data-ttu-id="6b0c5-156">Teams</span><span class="sxs-lookup"><span data-stu-id="6b0c5-156">Teams</span></span> |

## <a name="other-considerations"></a><span data-ttu-id="6b0c5-157">その他の考慮事項</span><span class="sxs-lookup"><span data-stu-id="6b0c5-157">Other considerations</span></span>

<span data-ttu-id="6b0c5-158">Teams の会議アドインは継続して機能が開発されていますので、次について認識しておいてください。</span><span class="sxs-lookup"><span data-stu-id="6b0c5-158">The Teams Meeting add-in is still building functionality, so be aware of the following:</span></span>

- <span data-ttu-id="6b0c5-159">このアドインは、特定の参加者でスケジュール設定された会議向けで、チャネル内の会議向けではありません。</span><span class="sxs-lookup"><span data-stu-id="6b0c5-159">The add-in is for scheduled meetings with specific participants, not for meetings in a channel.</span></span> <span data-ttu-id="6b0c5-160">チャネル会議は Teams 内でスケジュール設定される必要があります。</span><span class="sxs-lookup"><span data-stu-id="6b0c5-160">Channel meetings must be scheduled from within Teams.</span></span>
- <span data-ttu-id="6b0c5-161">認証プロキシがユーザーの PC および Teams サービスのネットワーク パス内にある場合、アドインは機能しません。</span><span class="sxs-lookup"><span data-stu-id="6b0c5-161">The add-in will not work if an Authentication Proxy is in the network path of user's PC and Teams Services.</span></span>
- <span data-ttu-id="6b0c5-162">ユーザーは Outlook 内からライブイベントをスケジュールできません。</span><span class="sxs-lookup"><span data-stu-id="6b0c5-162">Users can't schedule live events from within Outlook.</span></span> <span data-ttu-id="6b0c5-163">[チームに移動して、ライブイベントのスケジュールを設定します。</span><span class="sxs-lookup"><span data-stu-id="6b0c5-163">Go to Teams to schedule live events.</span></span> <span data-ttu-id="6b0c5-164">詳細については、「 [Microsoft Teams のライブイベントとは](teams-live-events/what-are-teams-live-events.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6b0c5-164">For more information, see [What are Microsoft Teams live events?](teams-live-events/what-are-teams-live-events.md).</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="6b0c5-165">トラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="6b0c5-165">Troubleshooting</span></span>

<span data-ttu-id="6b0c5-166">Teams Meeting add-in for Outlook のアドインをインストールできない場合は、次のトラブルシューティングの手順を試してください。</span><span class="sxs-lookup"><span data-stu-id="6b0c5-166">If you cannot get the Teams Meeting add-in for Outlook to install, try these troubleshooting steps.</span></span>

- <span data-ttu-id="6b0c5-167">Outlook デスクトップクライアントで利用できるすべての更新プログラムが適用されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="6b0c5-167">Ensure all available updates for Outlook desktop client have been applied.</span></span>
- <span data-ttu-id="6b0c5-168">Teamsのデスクトップ クライアントを再起動します。</span><span class="sxs-lookup"><span data-stu-id="6b0c5-168">Restart the Teams desktop client.</span></span>
- <span data-ttu-id="6b0c5-169">[Teamsのデスクトップ クライアント]からサインアウトして、もう一度サインインします。</span><span class="sxs-lookup"><span data-stu-id="6b0c5-169">Sign out and then sign back in to the Teams desktop client.</span></span>
- <span data-ttu-id="6b0c5-170">Outlook デスクトップ クライアントを再起動します。</span><span class="sxs-lookup"><span data-stu-id="6b0c5-170">Restart the Outlook desktop client.</span></span> <span data-ttu-id="6b0c5-171">(管理者モードで Outlook が実行されていないことを確認してください。)</span><span class="sxs-lookup"><span data-stu-id="6b0c5-171">(Make sure Outlook isn’t running in admin mode.)</span></span>
- <span data-ttu-id="6b0c5-172">ログインしているユーザー アカウント名にスペースが含まれていないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="6b0c5-172">Make sure the logged-in user account name does not contain spaces.</span></span> <span data-ttu-id="6b0c5-173">これは既知の問題であり、今後のビルドで修正される予定です。</span><span class="sxs-lookup"><span data-stu-id="6b0c5-173">(This is a known issue, and will be fixed in a future update.)</span></span>
- <span data-ttu-id="6b0c5-174">シングル サインオン (SSO) が有効になっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="6b0c5-174">Make sure single sign-on (SSO) is enabled.</span></span>

<span data-ttu-id="6b0c5-175">アドインを無効にする方法につぃての全般的なガイドラインについては、「[Office プログラムでアドインを表示、管理、インストールする](https://support.office.com/article/View-manage-and-install-add-ins-in-Office-programs-16278816-1948-4028-91E5-76DCA5380F8D)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="6b0c5-175">For general guidance about how to disable add-ins, see [View, manage, and install add-ins in Office programs](https://support.office.com/article/View-manage-and-install-add-ins-in-Office-programs-16278816-1948-4028-91E5-76DCA5380F8D).</span></span>

<span data-ttu-id="6b0c5-176">Microsoft Teams での会議と通話については[こちら](https://support.office.com/article/Meetings-and-calls-d92432d5-dd0f-4d17-8f69-06096b6b48a8)をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="6b0c5-176">Learn more about [meetings and calling in Microsoft Teams](https://support.office.com/article/Meetings-and-calls-d92432d5-dd0f-4d17-8f69-06096b6b48a8).</span></span>
