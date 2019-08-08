---
title: Outlook で Microsoft Teams の会議アドインを使用する
author: ChuckEdmonson
ms.author: chucked
manager: serdars
audience: Admin
ms.date: 06/25/2019
ms.topic: article
ms.service: msteams
ms.reviewer: sonua
localization_priority: Normal
search.appverid: MET150
description: Microsoft Teams は、ユーザーが  Outlook から Teams の会議をスケジュール設定することができるようになるアドインを Outlook にインストールします。
ms.custom:
- NewAdminCenter_Update
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8e2c7bae819037d0140fab1fed3625e250b8a4c1
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/07/2019
ms.locfileid: "36241789"
---
<a name="use-the-teams-meeting-add-in-in-outlook"></a><span data-ttu-id="d9d61-103">Outlook で Teams の会議アドインを使用する</span><span class="sxs-lookup"><span data-stu-id="d9d61-103">Use the Teams Meeting add-in in Outlook</span></span>
=======================================

<span data-ttu-id="d9d61-104">Teams 会議アドインを使用すると、ユーザーは Outlook から Teams 会議をスケジュールできます。</span><span class="sxs-lookup"><span data-stu-id="d9d61-104">The Teams Meeting add-in lets users schedule a Teams meeting from Outlook.</span></span> <span data-ttu-id="d9d61-105">Windows、Mac、web、モバイルの Outlook でアドインを使用できます。</span><span class="sxs-lookup"><span data-stu-id="d9d61-105">The add-in is available for Outlook on Windows, Mac, web, and mobile.</span></span>

## <a name="teams-meeting-add-in-in-outlook-for-windows"></a><span data-ttu-id="d9d61-106">Windows 版 Outlook の Teams 会議アドイン</span><span class="sxs-lookup"><span data-stu-id="d9d61-106">Teams Meeting add-in in Outlook for Windows</span></span>

<span data-ttu-id="d9d61-107">Microsoft Teams を所有しているユーザーと、Office 2010、Office 2013、または Office 2016 が Windows PC にインストールされている場合は、Teams 会議アドインが自動的にインストールされます。</span><span class="sxs-lookup"><span data-stu-id="d9d61-107">The Teams Meeting add-in is automatically installed for users who have Microsoft Teams and either Office 2010, Office 2013 or Office 2016 installed on their Windows PC.</span></span> <span data-ttu-id="d9d61-108">Teams の会議アドインは、ユーザーが使用する Outlook の [予定表] リボン上に表示されます。</span><span class="sxs-lookup"><span data-stu-id="d9d61-108">Users will see the Teams Meeting add-in on the Outlook Calendar ribbon.</span></span>

![Outlook リボンの Teams 会議アドインのスクリーンショット](media/Teams-add-in-for-Outlook.png)

> [!NOTE]
> - <span data-ttu-id="d9d61-110">Teams の会議アドインが表示されないユーザーに対しては、Outlook と Teams を閉じて、先に Teams クライアントを再起動してから Teams にサインインし、次に Outlook クライアントを再起動する操作を順に行うよう指示します。</span><span class="sxs-lookup"><span data-stu-id="d9d61-110">If users do not see the Teams Meeting add-in, instruct them to close Outlook and Teams, then restart the Teams client first, then sign in to Teams, and then restart the Outlook client, in that specific order.</span></span>
> - <span data-ttu-id="d9d61-111">Windows 7 ユーザーは、Teams 会議アドインを使用するために windows の[windows でユニバーサル C ランタイムの更新プログラム](https://support.microsoft.com/help/2999226/update-for-universal-c-runtime-in-windows)をインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="d9d61-111">Windows 7 users must install the [Update for Universal C Runtime in Windows](https://support.microsoft.com/help/2999226/update-for-universal-c-runtime-in-windows) in Windows for the Teams Meeting add-in to work.</span></span>

## <a name="teams-meeting-add-in-in-outlook-for-mac"></a><span data-ttu-id="d9d61-112">Outlook for Mac の Teams 会議アドイン</span><span class="sxs-lookup"><span data-stu-id="d9d61-112">Teams Meeting add-in in Outlook for Mac</span></span>

<span data-ttu-id="d9d61-113">Outlook for Mac の office の [会議] ボタンは、16.24.414.0 を実行している場合、outlook for mac のリボンに表示されます。</span><span class="sxs-lookup"><span data-stu-id="d9d61-113">The Teams Meeting button in Outlook for Mac will appear in the Outlook for Mac ribbon if Outlook is running Production Build 16.24.414.0 and later.</span></span>

<span data-ttu-id="d9d61-114">ユーザーが [**送信**] をクリックすると、会議の座標 (チームの参加リンクとダイヤルイン番号) が会議の出席依頼に追加されます。</span><span class="sxs-lookup"><span data-stu-id="d9d61-114">The meeting coordinates (the Teams join link and dial-in numbers) will be added to the meeting invite after the user clicks **Send**.</span></span>  

## <a name="teams-meeting-add-in-in-outlook-web-app"></a><span data-ttu-id="d9d61-115">Outlook Web App の Teams 会議アドイン</span><span class="sxs-lookup"><span data-stu-id="d9d61-115">Teams Meeting add-in in Outlook Web App</span></span>

<span data-ttu-id="d9d61-116">ユーザーが新しい Outlook on the Web の以前のバージョンをお持ちの場合、Outlook Web App の [Teams 会議] ボタンが新しいイベントの作成の一部として表示されます。</span><span class="sxs-lookup"><span data-stu-id="d9d61-116">The Teams Meetings button in Outlook Web App will appear as part of new event creation if the user is on an early version of the new Outlook on the web.</span></span> <span data-ttu-id="d9d61-117">ユーザーが新しい Outlook on the web の初期バージョンを試す方法については、 [Outlook ブログ](https://techcommunity.microsoft.com/t5/Outlook-Blog/Designed-to-be-fast-The-Outlook-on-the-web-user-experience-gets/ba-p/234909?utm_source=t.co&utm_medium=referral)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d9d61-117">See the [Outlook Blog](https://techcommunity.microsoft.com/t5/Outlook-Blog/Designed-to-be-fast-The-Outlook-on-the-web-user-experience-gets/ba-p/234909?utm_source=t.co&utm_medium=referral) to learn about how users can try the early version of the new Outlook on the web.</span></span>

![Outlook Web App の Teams 会議アドインのスクリーンショット](media/teams-meeting-add-in-web.png)

<span data-ttu-id="d9d61-119">ユーザーが [**送信**] をクリックすると、会議の座標 (チームの参加リンクとダイヤルイン番号) が会議の出席依頼に追加されます。</span><span class="sxs-lookup"><span data-stu-id="d9d61-119">The meeting coordinates (the Teams join link and dial-in numbers) will be added to the meeting invite after the user clicks **Send**.</span></span>  

## <a name="teams-meeting-add-in-in-outlook-mobile-ios-and-android"></a><span data-ttu-id="d9d61-120">Outlook mobile (iOS と Android) での Teams 会議アドイン</span><span class="sxs-lookup"><span data-stu-id="d9d61-120">Teams Meeting add-in in Outlook mobile (iOS and Android)</span></span>

<span data-ttu-id="d9d61-121">[Teams 会議] ボタンは、Outlook iOS と Android アプリの最新のビルドに表示されます。</span><span class="sxs-lookup"><span data-stu-id="d9d61-121">The Teams Meeting button shows up in latest builds of the Outlook iOS and Android app.</span></span>

![Outlook mobile の Teams 会議アドインのスクリーンショット](media/teams-meeting-add-in-mobile.png)

<span data-ttu-id="d9d61-123">ユーザーが [**送信**] をクリックすると、会議の座標 (チームの参加リンクとダイヤルイン番号) が会議の出席依頼に追加されます。</span><span class="sxs-lookup"><span data-stu-id="d9d61-123">The meeting coordinates (the Teams join link and dial-in numbers) will be added to the meeting invite after the user clicks **Send**.</span></span>  

## <a name="teams-meeting-add-in-in-and-findtime-for-outlook"></a><span data-ttu-id="d9d61-124">Outlook の Teams 会議アドインとそのタイミング</span><span class="sxs-lookup"><span data-stu-id="d9d61-124">Teams Meeting add-in in and FindTime for Outlook</span></span>
<span data-ttu-id="d9d61-125">FindTime は、Outlook 用のアドインであり、ユーザーが会社間の会議の時間について合意したときに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="d9d61-125">FindTime is an add-in for Outlook that helps users reach a consensus on a meeting time across companies.</span></span> <span data-ttu-id="d9d61-126">会議の出席者が希望する時間を指定すると、指定した時間にユーザーの代わりに会議出席依頼が送信されます。</span><span class="sxs-lookup"><span data-stu-id="d9d61-126">Once the meeting invitees have provided their preferred times, FindTime sends out the meeting invite on the user's behalf.</span></span> <span data-ttu-id="d9d61-127">[**オンライン会議**] オプションが [findtime] で選択されている場合、Findtime は Skype for business または Microsoft Teams の会議をスケジュールします。</span><span class="sxs-lookup"><span data-stu-id="d9d61-127">If the **Online meeting** option is selected in FindTime, FindTime will schedule a Skype for Business or Microsoft Teams meeting.</span></span> <span data-ttu-id="d9d61-128">(FindTime は、組織によって既定のオンライン会議チャンネルとして設定されたものを使用します)。</span><span class="sxs-lookup"><span data-stu-id="d9d61-128">(FindTime will use whichever has been set by your organization as the default online meeting channel.)</span></span>

> [!NOTE]  
> <span data-ttu-id="d9d61-129">お客様の[findtime ダッシュボード](https://findtime.microsoft.com/UserDashboard)に Skype for business の設定を保存した場合、findtime では Microsoft Teams の代わりにそれが使用されます。</span><span class="sxs-lookup"><span data-stu-id="d9d61-129">If you saved a Skype for Business setting in your [Findtime dashboard](https://findtime.microsoft.com/UserDashboard), FindTime will use that instead of Microsoft Teams.</span></span> <span data-ttu-id="d9d61-130">Microsoft Teams を使用する場合は、ダッシュボードの Skype for Business の設定を削除します。</span><span class="sxs-lookup"><span data-stu-id="d9d61-130">If you want to use Microsoft Teams, delete the Skype for Business setting in your dashboard.</span></span>

<span data-ttu-id="d9d61-131">詳細については、「 [FindTime での会議のスケジュール](https://support.office.com/article/scheduling-meetings-with-findtime-4dc806ed-fde3-4ea7-8c5e-b5d1fddab4a6)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d9d61-131">See [Schedule meetings with FindTime](https://support.office.com/article/scheduling-meetings-with-findtime-4dc806ed-fde3-4ea7-8c5e-b5d1fddab4a6) for more information.</span></span>

## <a name="authentication-requirements"></a><span data-ttu-id="d9d61-132">認証要件</span><span class="sxs-lookup"><span data-stu-id="d9d61-132">Authentication requirements</span></span>

<span data-ttu-id="d9d61-133">Teams の会議アドインでは、ユーザーが認証要件を使用して Teams にサインインすることが必要になります。</span><span class="sxs-lookup"><span data-stu-id="d9d61-133">The Teams Meeting add-in requires users to sign in to Teams using Modern Authentication.</span></span> <span data-ttu-id="d9d61-134">ユーザーがこの方法を使用せずにサインインしても、Teams クライアントを使用することはできますが、Outlook アドインを使用して Teams のオンライン会議をスケジュール設定することはできません。</span><span class="sxs-lookup"><span data-stu-id="d9d61-134">If users do not use this method to sign in, they’ll still be able to use the Teams client, but will be unable to schedule Teams online meetings using the Outlook add-in.</span></span> <span data-ttu-id="d9d61-135">これを修正するには、次のいずれかを実行します。</span><span class="sxs-lookup"><span data-stu-id="d9d61-135">You can fix this by doing one of the following:</span></span>

- <span data-ttu-id="d9d61-136">先進認証が組織に対して構成されていない場合は、先進認証を構成します。</span><span class="sxs-lookup"><span data-stu-id="d9d61-136">If Modern Authentication is not configured for your organization, you should configure Modern Authentication.</span></span>
- <span data-ttu-id="d9d61-137">モダン認証が設定されているが、ダイアログボックスでキャンセルされた場合は、多要素認証を使用してもう一度サインインするようにユーザーに指示する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d9d61-137">If Modern Authentication is configured, but they canceled out on the dialog box, you should instruct users to sign in again using multi-factor authentication.</span></span>

<span data-ttu-id="d9d61-138">認証を構成する方法の詳細については、「[Microsoft Teams での ID モデルと認証](identify-models-authentication.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="d9d61-138">To learn more about how to configure authentication, see [Identity models and authentication in Microsoft Teams](identify-models-authentication.md).</span></span>

## <a name="enable-private-meetings"></a><span data-ttu-id="d9d61-139">プライベート会議を有効にする</span><span class="sxs-lookup"><span data-stu-id="d9d61-139">Enable private meetings</span></span>

<span data-ttu-id="d9d61-140">アドインを展開できるようにするには、Microsoft Teams 管理センターで**プライベート会議のスケジュール**を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="d9d61-140">**Allow scheduling for private meetings** must be enabled in the Microsoft Teams admin center for the add-in to get deployed.</span></span> <span data-ttu-id="d9d61-141">管理センターで**Meetings** > **Meeting Policies**に行き、**一般的な**セクションで、**Allow scheduling private meetings**をオンに切り替えるます。)</span><span class="sxs-lookup"><span data-stu-id="d9d61-141">In the admin center, go to **Meetings** > **Meeting Policies**, and in the **General** section, toggle **Allow scheduling private meetings** to On.)</span></span>

![Microsoft Teams管理センターの設定のスクリーンショット。](media/teams-add-in-for-outlook-image1.png)

<span data-ttu-id="d9d61-143">Teams クライアントはユーザーが必要としているのが 32 ビット版か 64 ビット版かを判断して正しいアドインをインストールします。</span><span class="sxs-lookup"><span data-stu-id="d9d61-143">The Teams client installs the correct add-in by determining if users need the 32-bit or 64-bit version.</span></span>

> [!NOTE]
> <span data-ttu-id="d9d61-144">ユーザーは最新のアドインを利用できるようになるために Teams のインストールまたはアップグレード後に Outlook の再起動が必要になる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="d9d61-144">Users might need to restart Outlook after an installation or upgrade of Teams to get the latest add-in.</span></span>

## <a name="teams-upgrade-policy-and-the-teams-meeting-add-in-for-outlook"></a><span data-ttu-id="d9d61-145">Teams のアップグレードポリシーと Outlook 用 Teams 会議アドイン</span><span class="sxs-lookup"><span data-stu-id="d9d61-145">Teams upgrade policy and the Teams Meeting add-in for Outlook</span></span>

<span data-ttu-id="d9d61-146">お客様は[、Skype For business から Teams へのアップグレードを選ぶ](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)ことができます。</span><span class="sxs-lookup"><span data-stu-id="d9d61-146">Customers can [choose their upgrade journey from Skype for Business to Teams](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md).</span></span> <span data-ttu-id="d9d61-147">テナント管理者は、チームの共存モードを使用して、ユーザーに対してこのような旅を定義できます。</span><span class="sxs-lookup"><span data-stu-id="d9d61-147">Tenant admins can use the Teams co-existence mode to define this journey for their users.</span></span> <span data-ttu-id="d9d61-148">テナント管理者は、ユーザーが Skype for Business (諸島モード) と共にチームを使用できるようにするオプションを備えています。</span><span class="sxs-lookup"><span data-stu-id="d9d61-148">Tenant admins have the option to enable users to use Teams alongside Skype for Business (Islands mode).</span></span> 

<span data-ttu-id="d9d61-149">孤島モードのユーザーが Outlook で会議をスケジュールする場合、通常は、Skype for Business と Teams のどちらの会議をスケジュールするかを選ぶことができます。</span><span class="sxs-lookup"><span data-stu-id="d9d61-149">When users who are in Island mode schedule a meeting in Outlook, they typically expect to be able to choose whether to schedule a Skype for Business or a Teams meeting.</span></span> <span data-ttu-id="d9d61-150">Outlook on the web、Outlook Windows、Outlook Mac では、島々モードでは、ユーザーに Skype for Business アドインと Teams アドインの両方が表示されます。</span><span class="sxs-lookup"><span data-stu-id="d9d61-150">In Outlook on the web, Outlook Windows, and Outlook Mac, users see both Skype for Business and Teams add-ins when in Islands mode.</span></span> <span data-ttu-id="d9d61-151">初期リリースの一部の制限により、Outlook mobile では、Skype for Business**または**Teams 会議の作成のみがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="d9d61-151">Due to certain limitations in the initial release, Outlook mobile can only support creating Skype for Business **or** Teams meetings.</span></span> <span data-ttu-id="d9d61-152">詳細については、次の表を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d9d61-152">See the following table for details.</span></span>

| <span data-ttu-id="d9d61-153">Teams 管理センターでの共存モード</span><span class="sxs-lookup"><span data-stu-id="d9d61-153">Coexistence mode in the Teams admin center</span></span> | <span data-ttu-id="d9d61-154">Outlook mobile の既定の会議プロバイダー</span><span class="sxs-lookup"><span data-stu-id="d9d61-154">Default meetings provider in Outlook mobile</span></span> |
| --------------------------------------|---------------------------------------------|
| <span data-ttu-id="d9d61-155">アイランド</span><span class="sxs-lookup"><span data-stu-id="d9d61-155">Islands</span></span> | <span data-ttu-id="d9d61-156">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="d9d61-156">Skype for Business</span></span> |
| <span data-ttu-id="d9d61-157">Skype for Business のみ</span><span class="sxs-lookup"><span data-stu-id="d9d61-157">Skype for Business only</span></span> | <span data-ttu-id="d9d61-158">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="d9d61-158">Skype for Business</span></span> |
| <span data-ttu-id="d9d61-159">Skype for Business と Teams でのコラボレーション</span><span class="sxs-lookup"><span data-stu-id="d9d61-159">Skype for Business with Teams collaboration</span></span> | <span data-ttu-id="d9d61-160">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="d9d61-160">Skype for Business</span></span> |
| <span data-ttu-id="d9d61-161">Skype for Business と Teams でのコラボレーションおよび会議</span><span class="sxs-lookup"><span data-stu-id="d9d61-161">Skype for Business with Teams collaboration and meetings</span></span> | <span data-ttu-id="d9d61-162">Teams</span><span class="sxs-lookup"><span data-stu-id="d9d61-162">Teams</span></span> |
| <span data-ttu-id="d9d61-163">Teams のみ</span><span class="sxs-lookup"><span data-stu-id="d9d61-163">Teams only</span></span> | <span data-ttu-id="d9d61-164">Teams</span><span class="sxs-lookup"><span data-stu-id="d9d61-164">Teams</span></span> |

## <a name="other-considerations"></a><span data-ttu-id="d9d61-165">その他の考慮事項</span><span class="sxs-lookup"><span data-stu-id="d9d61-165">Other considerations</span></span>

<span data-ttu-id="d9d61-166">Teams の会議アドインは継続して機能が開発されていますので、次について認識しておいてください。</span><span class="sxs-lookup"><span data-stu-id="d9d61-166">The Teams Meeting add-in is still building functionality, so be aware of the following:</span></span>

- <span data-ttu-id="d9d61-167">このアドインは、特定の参加者でスケジュール設定された会議向けで、チャネル内の会議向けではありません。</span><span class="sxs-lookup"><span data-stu-id="d9d61-167">The add-in is for scheduled meetings with specific participants, not for meetings in a channel.</span></span> <span data-ttu-id="d9d61-168">チャネル会議は Teams 内でスケジュール設定される必要があります。</span><span class="sxs-lookup"><span data-stu-id="d9d61-168">Channel meetings must be scheduled from within Teams.</span></span>
- <span data-ttu-id="d9d61-169">認証プロキシがユーザーの PC および Teams サービスのネットワーク パス内にある場合、アドインは機能しません。</span><span class="sxs-lookup"><span data-stu-id="d9d61-169">The add-in will not work if an Authentication Proxy is in the network path of user's PC and Teams Services.</span></span>
- <span data-ttu-id="d9d61-170">ユーザーは Outlook 内からライブイベントをスケジュールできません。</span><span class="sxs-lookup"><span data-stu-id="d9d61-170">Users can't schedule live events from within Outlook.</span></span> <span data-ttu-id="d9d61-171">[チームに移動して、ライブイベントのスケジュールを設定します。</span><span class="sxs-lookup"><span data-stu-id="d9d61-171">Go to Teams to schedule live events.</span></span> <span data-ttu-id="d9d61-172">詳細については、「 [Microsoft Teams のライブイベントとは](teams-live-events/what-are-teams-live-events.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d9d61-172">For more information, see [What are Microsoft Teams live events?](teams-live-events/what-are-teams-live-events.md).</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="d9d61-173">トラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="d9d61-173">Troubleshooting</span></span>

<span data-ttu-id="d9d61-174">Teams Meeting add-in for Outlook のアドインをインストールできない場合は、次のトラブルシューティングの手順を試してください。</span><span class="sxs-lookup"><span data-stu-id="d9d61-174">If you cannot get the Teams Meeting add-in for Outlook to install, try these troubleshooting steps.</span></span>

- <span data-ttu-id="d9d61-175">Outlook デスクトップクライアントで利用できるすべての更新プログラムが適用されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="d9d61-175">Ensure all available updates for Outlook desktop client have been applied.</span></span>
- <span data-ttu-id="d9d61-176">Teamsのデスクトップ クライアントを再起動します。</span><span class="sxs-lookup"><span data-stu-id="d9d61-176">Restart the Teams desktop client.</span></span>
- <span data-ttu-id="d9d61-177">[Teamsのデスクトップ クライアント]からサインアウトして、もう一度サインインします。</span><span class="sxs-lookup"><span data-stu-id="d9d61-177">Sign out and then sign back in to the Teams desktop client.</span></span>
- <span data-ttu-id="d9d61-178">Outlook デスクトップ クライアントを再起動します。</span><span class="sxs-lookup"><span data-stu-id="d9d61-178">Restart the Outlook desktop client.</span></span> <span data-ttu-id="d9d61-179">(管理者モードで Outlook が実行されていないことを確認してください。)</span><span class="sxs-lookup"><span data-stu-id="d9d61-179">(Make sure Outlook isn’t running in admin mode.)</span></span>
- <span data-ttu-id="d9d61-180">ログインしているユーザー アカウント名にスペースが含まれていないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="d9d61-180">Make sure the logged-in user account name does not contain spaces.</span></span> <span data-ttu-id="d9d61-181">これは既知の問題であり、今後のビルドで修正される予定です。</span><span class="sxs-lookup"><span data-stu-id="d9d61-181">(This is a known issue, and will be fixed in a future update.)</span></span>
- <span data-ttu-id="d9d61-182">シングル サインオン (SSO) が有効になっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="d9d61-182">Make sure single sign-on (SSO) is enabled.</span></span>

<span data-ttu-id="d9d61-183">管理者が[Exchange Web Server (EWS) へのアクセスを制御](https://docs.microsoft.com/en-us/exchange/client-developer/exchange-web-services/how-to-control-access-to-ews-in-exchange)するように Microsoft Exchange を構成している場合は、代理人が上司の代わりに Teams 会議をスケジュールすることはできません。</span><span class="sxs-lookup"><span data-stu-id="d9d61-183">If your administrator has configured Microsoft Exchange to [control access to Exchange Web Server (EWS)](https://docs.microsoft.com/en-us/exchange/client-developer/exchange-web-services/how-to-control-access-to-ews-in-exchange), a delegate won't be able to schedule a Teams meeting on behalf of the boss.</span></span> <span data-ttu-id="d9d61-184">この構成の解決策は開発中であり、今後リリースされる予定です。</span><span class="sxs-lookup"><span data-stu-id="d9d61-184">The solution for this configuration is under development and will be released in the future.</span></span> 

<span data-ttu-id="d9d61-185">アドインを無効にする方法につぃての全般的なガイドラインについては、「[Office プログラムでアドインを表示、管理、インストールする](https://support.office.com/article/View-manage-and-install-add-ins-in-Office-programs-16278816-1948-4028-91E5-76DCA5380F8D)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="d9d61-185">For general guidance about how to disable add-ins, see [View, manage, and install add-ins in Office programs](https://support.office.com/article/View-manage-and-install-add-ins-in-Office-programs-16278816-1948-4028-91E5-76DCA5380F8D).</span></span>

<span data-ttu-id="d9d61-186">Microsoft Teams での会議と通話については[こちら](https://support.office.com/article/Meetings-and-calls-d92432d5-dd0f-4d17-8f69-06096b6b48a8)をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="d9d61-186">Learn more about [meetings and calling in Microsoft Teams](https://support.office.com/article/Meetings-and-calls-d92432d5-dd0f-4d17-8f69-06096b6b48a8).</span></span>
