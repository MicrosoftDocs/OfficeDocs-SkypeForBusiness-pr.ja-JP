---
title: Outlook で Microsoft Teams の会議アドインを使用する
author: ChuckEdmonson
ms.author: chucked
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: sonua
localization_priority: Normal
search.appverid: MET150
description: Microsoft Teams は、ユーザーが  Outlook から Teams の会議をスケジュール設定することができるようになるアドインを Outlook にインストールします。
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: e1cdd071dfe19c50650d6f18605a5aeed5b39300
ms.sourcegitcommit: c16451519e05b47bbb77e09dacd13ff212617e91
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/28/2020
ms.locfileid: "42327849"
---
<a name="use-the-teams-meeting-add-in-in-outlook"></a><span data-ttu-id="b951d-103">Outlook で Teams の会議アドインを使用する</span><span class="sxs-lookup"><span data-stu-id="b951d-103">Use the Teams Meeting add-in in Outlook</span></span>
=======================================

<span data-ttu-id="b951d-104">Teams 会議アドインを使用すると、ユーザーは Outlook から Teams 会議をスケジュールできます。</span><span class="sxs-lookup"><span data-stu-id="b951d-104">The Teams Meeting add-in lets users schedule a Teams meeting from Outlook.</span></span> <span data-ttu-id="b951d-105">このアドインは、Outlook for Windows、Mac、Web、モバイルで使用できます。</span><span class="sxs-lookup"><span data-stu-id="b951d-105">The add-in is available for Outlook on Windows, Mac, web, and mobile.</span></span>

## <a name="teams-meeting-add-in-in-outlook-for-windows"></a><span data-ttu-id="b951d-106">Windows 用 Outlook の Teams 会議アドイン</span><span class="sxs-lookup"><span data-stu-id="b951d-106">Teams Meeting add-in in Outlook for Windows</span></span>

<span data-ttu-id="b951d-107">Teams の会議アドインは、Microsoft Teams と Office 2010、Office 2013 または Office 2016 を自分の Windows PC にインストール済みのユーザーに対して、自動的にインストールされます。</span><span class="sxs-lookup"><span data-stu-id="b951d-107">The Teams Meeting add-in is automatically installed for users who have Microsoft Teams and either Office 2010, Office 2013 or Office 2016 installed on their Windows PC.</span></span> <span data-ttu-id="b951d-108">Teams の会議アドインは、ユーザーが使用する Outlook の [予定表] リボン上に表示されます。</span><span class="sxs-lookup"><span data-stu-id="b951d-108">Users will see the Teams Meeting add-in on the Outlook Calendar ribbon.</span></span>

![Outlook リボン上の Teams 会議アドインのスクリーンショット](media/Teams-add-in-for-Outlook.png)

> [!NOTE]
> - <span data-ttu-id="b951d-110">Regsvr32.exe ファイルを実行するユーザーのアクセス許可は、コンピューターに Teams 会議アドインをインストールするための最小要件です。</span><span class="sxs-lookup"><span data-stu-id="b951d-110">User permissions to execute the Regsvr32.exe file is a minimum requirement for the Teams Meeting add-in to be installed on the computer.</span></span>
> - <span data-ttu-id="b951d-111">Teams の会議アドインが表示されないユーザーに対しては、Outlook と Teams を閉じて、先に Teams クライアントを再起動してから Teams にサインインし、次に Outlook クライアントを再起動する操作を順に行うよう指示します。</span><span class="sxs-lookup"><span data-stu-id="b951d-111">If users do not see the Teams Meeting add-in, instruct them to close Outlook and Teams, then restart the Teams client first, then sign in to Teams, and then restart the Outlook client, in that specific order.</span></span>
> - <span data-ttu-id="b951d-112">Microsoft ストアから Office Outlook のインストールを使用している場合、Teams 会議アドインはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="b951d-112">If you are using an Office Outlook installation from the Microsoft Store, the Teams Meeting add-in isn't supported.</span></span> <span data-ttu-id="b951d-113">このアドインが必要なユーザーは、「[S モードでの Windows 10 の Office](https://support.office.com/article/faq-office-on-windows-10-in-s-mode-717193b5-ff9f-4388-84c0-277ddf07fe3f)」の記事で説明されているとおり、Office のクイック実行バージョンをインストールすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="b951d-113">Users who require this add-in are advised to install Click-to-Run version of Office, as outlined in [Office on Windows 10 in S mode](https://support.office.com/article/faq-office-on-windows-10-in-s-mode-717193b5-ff9f-4388-84c0-277ddf07fe3f) article.</span></span>

## <a name="teams-meeting-add-in-in-outlook-for-mac"></a><span data-ttu-id="b951d-114">Outlook for Mac の Teams 会議アドイン</span><span class="sxs-lookup"><span data-stu-id="b951d-114">Teams Meeting add-in in Outlook for Mac</span></span>

<span data-ttu-id="b951d-115">Outlook for Mac の [Teams 会議] ボタンが、Office 365 クライアントサブスクリプションで実行されていて、outlook for mac のリボンに表示されます。</span><span class="sxs-lookup"><span data-stu-id="b951d-115">The Teams Meeting button in Outlook for Mac will appear in the Outlook for Mac ribbon if Outlook is running production build 16.24.414.0 and later and is activated with an Office 365 client subscription.</span></span>

<span data-ttu-id="b951d-116">ユーザーが [**送信**] をクリックすると、会議の調整 (Teams への参加リンクおよびダイヤルイン番号) が会議出席依頼に追加されます。</span><span class="sxs-lookup"><span data-stu-id="b951d-116">The meeting coordinates (the Teams join link and dial-in numbers) will be added to the meeting invite after the user clicks **Send**.</span></span>  

## <a name="teams-meeting-add-in-in-outlook-web-app"></a><span data-ttu-id="b951d-117">Outlook Web App の Teams 会議アドイン</span><span class="sxs-lookup"><span data-stu-id="b951d-117">Teams Meeting add-in in Outlook Web App</span></span>

<span data-ttu-id="b951d-118">ユーザーが新しい Outlook on the Web の初期バージョンを使用している場合、Outlook Web App の [Teams 会議] ボタンが新しいイベント作成の一部として表示されます。</span><span class="sxs-lookup"><span data-stu-id="b951d-118">The Teams Meetings button in Outlook Web App will appear as part of new event creation if the user is on an early version of the new Outlook on the web.</span></span> <span data-ttu-id="b951d-119">ユーザーが Outlook on the Web の初期バージョンを試す方法については、「[Outlook のブログ](https://techcommunity.microsoft.com/t5/Outlook-Blog/Designed-to-be-fast-The-Outlook-on-the-web-user-experience-gets/ba-p/234909?utm_source=t.co&utm_medium=referral)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b951d-119">See the [Outlook Blog](https://techcommunity.microsoft.com/t5/Outlook-Blog/Designed-to-be-fast-The-Outlook-on-the-web-user-experience-gets/ba-p/234909?utm_source=t.co&utm_medium=referral) to learn about how users can try the early version of the new Outlook on the web.</span></span>

![Outlook Web App の Teams 会議アドインのスクリーンショット](media/teams-meeting-add-in-web.png)

<span data-ttu-id="b951d-121">ユーザーが [**送信**] をクリックすると、会議の調整 (Teams への参加リンクおよびダイヤルイン番号) が会議出席依頼に追加されます。</span><span class="sxs-lookup"><span data-stu-id="b951d-121">The meeting coordinates (the Teams join link and dial-in numbers) will be added to the meeting invite after the user clicks **Send**.</span></span>  

## <a name="teams-meeting-add-in-in-outlook-mobile-ios-and-android"></a><span data-ttu-id="b951d-122">Outlook モバイル (iOS および Android) の Teams 会議アドイン</span><span class="sxs-lookup"><span data-stu-id="b951d-122">Teams Meeting add-in in Outlook mobile (iOS and Android)</span></span>

<span data-ttu-id="b951d-123">iOS と Android の Outlook アプリの最新ビルドには、Teams 会議ボタンが表示されます。</span><span class="sxs-lookup"><span data-stu-id="b951d-123">The Teams Meeting button shows up in latest builds of the Outlook iOS and Android app.</span></span>

![Outlook モバイルの Teams 会議アドインのスクリーンショット](media/teams-meeting-add-in-mobile.png)

<span data-ttu-id="b951d-125">ユーザーが [**送信**] をクリックすると、会議の調整 (Teams への参加リンクおよびダイヤルイン番号) が会議出席依頼に追加されます。</span><span class="sxs-lookup"><span data-stu-id="b951d-125">The meeting coordinates (the Teams join link and dial-in numbers) will be added to the meeting invite after the user clicks **Send**.</span></span>  

## <a name="teams-meeting-add-in-in-and-findtime-for-outlook"></a><span data-ttu-id="b951d-126">Outlook の Teams 会議アドインと FindTime</span><span class="sxs-lookup"><span data-stu-id="b951d-126">Teams Meeting add-in in and FindTime for Outlook</span></span>
<span data-ttu-id="b951d-127">FindTime は、Outlook 用のアドインです。これは、企業全体の会議時間に関してユーザが合意できるようにします。</span><span class="sxs-lookup"><span data-stu-id="b951d-127">FindTime is an add-in for Outlook that helps users reach a consensus on a meeting time across companies.</span></span> <span data-ttu-id="b951d-128">会議の招待者が希望の時間を提示したら、FindTime はユーザーの代わりに会議出席依頼を送信します。</span><span class="sxs-lookup"><span data-stu-id="b951d-128">Once the meeting invitees have provided their preferred times, FindTime sends out the meeting invite on the user's behalf.</span></span> <span data-ttu-id="b951d-129">FindTime で [**オンライン会議**] オプションが選択されている場合、FindTime は Skype for Business または Microsoft Teams の会議をスケジュールします。</span><span class="sxs-lookup"><span data-stu-id="b951d-129">If the **Online meeting** option is selected in FindTime, FindTime will schedule a Skype for Business or Microsoft Teams meeting.</span></span> <span data-ttu-id="b951d-130">(FindTime は、既定のオンライン会議チャネルとして、組織が設定したものを使用します。)</span><span class="sxs-lookup"><span data-stu-id="b951d-130">(FindTime will use whichever has been set by your organization as the default online meeting channel.)</span></span>

> [!NOTE]  
> <span data-ttu-id="b951d-131">[Findtime ダッシュボード](https://findtime.microsoft.com/UserDashboard)で Skype for Business の設定を保存した場合、FindTime は Microsoft Teams の代わりにその設定を使用します。</span><span class="sxs-lookup"><span data-stu-id="b951d-131">If you saved a Skype for Business setting in your [Findtime dashboard](https://findtime.microsoft.com/UserDashboard), FindTime will use that instead of Microsoft Teams.</span></span> <span data-ttu-id="b951d-132">Microsoft Teams を使用する場合は、ダッシュボードの Skype for Business の設定を削除します。</span><span class="sxs-lookup"><span data-stu-id="b951d-132">If you want to use Microsoft Teams, delete the Skype for Business setting in your dashboard.</span></span>

<span data-ttu-id="b951d-133">詳細については、「[FindTime で会議をスケジュールする](https://support.office.com/article/scheduling-meetings-with-findtime-4dc806ed-fde3-4ea7-8c5e-b5d1fddab4a6)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b951d-133">See [Schedule meetings with FindTime](https://support.office.com/article/scheduling-meetings-with-findtime-4dc806ed-fde3-4ea7-8c5e-b5d1fddab4a6) for more information.</span></span>

## <a name="authentication-requirements"></a><span data-ttu-id="b951d-134">認証要件</span><span class="sxs-lookup"><span data-stu-id="b951d-134">Authentication requirements</span></span>

<span data-ttu-id="b951d-135">Teams の会議アドインでは、ユーザーが認証要件を使用して Teams にサインインすることが必要になります。</span><span class="sxs-lookup"><span data-stu-id="b951d-135">The Teams Meeting add-in requires users to sign in to Teams using Modern Authentication.</span></span> <span data-ttu-id="b951d-136">ユーザーがこの方法を使用せずにサインインしても、Teams クライアントを使用することはできますが、Outlook アドインを使用して Teams のオンライン会議をスケジュール設定することはできません。</span><span class="sxs-lookup"><span data-stu-id="b951d-136">If users do not use this method to sign in, they’ll still be able to use the Teams client, but will be unable to schedule Teams online meetings using the Outlook add-in.</span></span> <span data-ttu-id="b951d-137">これを修正するには、次のいずれかを実行します。</span><span class="sxs-lookup"><span data-stu-id="b951d-137">You can fix this by doing one of the following:</span></span>

- <span data-ttu-id="b951d-138">先進認証が組織に対して構成されていない場合は、先進認証を構成します。</span><span class="sxs-lookup"><span data-stu-id="b951d-138">If Modern Authentication is not configured for your organization, you should configure Modern Authentication.</span></span>
- <span data-ttu-id="b951d-139">先進認証が構成されていているのにダイアログ ボックスでユーザーが無効になってしまう場合は、それらのユーザーに対して多要素認証を使用してサインインし直すよう指示します。</span><span class="sxs-lookup"><span data-stu-id="b951d-139">If Modern Authentication is configured, but they canceled out on the dialog box, you should instruct users to sign in again using multi-factor authentication.</span></span>

<span data-ttu-id="b951d-140">認証を構成する方法の詳細については、「[Microsoft Teams での ID モデルと認証](identify-models-authentication.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="b951d-140">To learn more about how to configure authentication, see [Identity models and authentication in Microsoft Teams](identify-models-authentication.md).</span></span>

## <a name="enable-private-meetings"></a><span data-ttu-id="b951d-141">プライベート会議を有効にする</span><span class="sxs-lookup"><span data-stu-id="b951d-141">Enable private meetings</span></span>

<span data-ttu-id="b951d-142">アドインを展開するには、Microsoft Teams 管理センターで [**プライベート会議のスケジュールを設定できるようになります**] を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="b951d-142">**Allow scheduling for private meetings** must be enabled in the Microsoft Teams admin center for the add-in to get deployed.</span></span> <span data-ttu-id="b951d-143">管理センターで**Meetings** > **Meeting Policies**に行き、**一般的な**セクションで、**Allow scheduling private meetings**をオンに切り替えるます。)</span><span class="sxs-lookup"><span data-stu-id="b951d-143">In the admin center, go to **Meetings** > **Meeting Policies**, and in the **General** section, toggle **Allow scheduling private meetings** to On.)</span></span>

![Microsoft Teams管理センターの設定のスクリーンショット。](media/teams-add-in-for-outlook-image1.png)

<span data-ttu-id="b951d-145">Teams クライアントはユーザーが必要としているのが 32 ビット版か 64 ビット版かを判断して正しいアドインをインストールします。</span><span class="sxs-lookup"><span data-stu-id="b951d-145">The Teams client installs the correct add-in by determining if users need the 32-bit or 64-bit version.</span></span>

> [!NOTE]
> <span data-ttu-id="b951d-146">ユーザーは最新のアドインを利用できるようになるために Teams のインストールまたはアップグレード後に Outlook の再起動が必要になる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="b951d-146">Users might need to restart Outlook after an installation or upgrade of Teams to get the latest add-in.</span></span>

## <a name="teams-upgrade-policy-and-the-teams-meeting-add-in-for-outlook"></a><span data-ttu-id="b951d-147">Teams のアップグレード ポリシーと Outlook 用 Teams 会議アドイン</span><span class="sxs-lookup"><span data-stu-id="b951d-147">Teams upgrade policy and the Teams Meeting add-in for Outlook</span></span>

<span data-ttu-id="b951d-148">お客様は、[Skype for Business から Teams へのアップグレード手順を選択する](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)ことができます。</span><span class="sxs-lookup"><span data-stu-id="b951d-148">Customers can [choose their upgrade journey from Skype for Business to Teams](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md).</span></span> <span data-ttu-id="b951d-149">テナント管理者は、Teams の共存モードを使用して、ユーザーにこの手順を定義できます。</span><span class="sxs-lookup"><span data-stu-id="b951d-149">Tenant admins can use the Teams co-existence mode to define this journey for their users.</span></span> <span data-ttu-id="b951d-150">テナント管理者には、ユーザーが Skype for Business (アイランド モード) と共に Teams を使用できるようにするオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="b951d-150">Tenant admins have the option to enable users to use Teams alongside Skype for Business (Islands mode).</span></span> 

<span data-ttu-id="b951d-151">アイランド モードのユーザは、Outlook で会議をスケジュールする場合、通常は Skype for Business と Teams の会議のどちらをスケジュールするか選択できると想定しています。</span><span class="sxs-lookup"><span data-stu-id="b951d-151">When users who are in Island mode schedule a meeting in Outlook, they typically expect to be able to choose whether to schedule a Skype for Business or a Teams meeting.</span></span> <span data-ttu-id="b951d-152">Outlook on the web、Outlook Windows、および Outlook Mac では、アイランド モードの場合、Skype for Business および Teams アドインの両方が表示されます。</span><span class="sxs-lookup"><span data-stu-id="b951d-152">In Outlook on the web, Outlook Windows, and Outlook Mac, users see both Skype for Business and Teams add-ins when in Islands mode.</span></span> <span data-ttu-id="b951d-153">初期リリースではいくつかの制限があるため、Outlook モバイルは Skype for Business **または** Teams の会議の作成のみをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="b951d-153">Due to certain limitations in the initial release, Outlook mobile can only support creating Skype for Business **or** Teams meetings.</span></span> <span data-ttu-id="b951d-154">詳細は次の表を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b951d-154">See the following table for details.</span></span>

| <span data-ttu-id="b951d-155">Teams 管理センターの共存モード</span><span class="sxs-lookup"><span data-stu-id="b951d-155">Coexistence mode in the Teams admin center</span></span> | <span data-ttu-id="b951d-156">Outlook モバイルの既定の会議プロバイダー</span><span class="sxs-lookup"><span data-stu-id="b951d-156">Default meetings provider in Outlook mobile</span></span> |
| --------------------------------------|---------------------------------------------|
| <span data-ttu-id="b951d-157">アイランド</span><span class="sxs-lookup"><span data-stu-id="b951d-157">Islands</span></span> | <span data-ttu-id="b951d-158">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="b951d-158">Skype for Business</span></span> |
| <span data-ttu-id="b951d-159">Skype for Business のみ</span><span class="sxs-lookup"><span data-stu-id="b951d-159">Skype for Business only</span></span> | <span data-ttu-id="b951d-160">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="b951d-160">Skype for Business</span></span> |
| <span data-ttu-id="b951d-161">Skype for Business と Teams の共同作業</span><span class="sxs-lookup"><span data-stu-id="b951d-161">Skype for Business with Teams collaboration</span></span> | <span data-ttu-id="b951d-162">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="b951d-162">Skype for Business</span></span> |
| <span data-ttu-id="b951d-163">Skype for Business と Teams の共同作業と会議</span><span class="sxs-lookup"><span data-stu-id="b951d-163">Skype for Business with Teams collaboration and meetings</span></span> | <span data-ttu-id="b951d-164">Teams</span><span class="sxs-lookup"><span data-stu-id="b951d-164">Teams</span></span> |
| <span data-ttu-id="b951d-165">Teams のみ</span><span class="sxs-lookup"><span data-stu-id="b951d-165">Teams only</span></span> | <span data-ttu-id="b951d-166">Teams</span><span class="sxs-lookup"><span data-stu-id="b951d-166">Teams</span></span> |

## <a name="other-considerations"></a><span data-ttu-id="b951d-167">その他の考慮事項</span><span class="sxs-lookup"><span data-stu-id="b951d-167">Other considerations</span></span>

<span data-ttu-id="b951d-168">Teams の会議アドインは継続して機能が開発されていますので、次について認識しておいてください。</span><span class="sxs-lookup"><span data-stu-id="b951d-168">The Teams Meeting add-in is still building functionality, so be aware of the following:</span></span>

- <span data-ttu-id="b951d-169">このアドインは、特定の参加者でスケジュール設定された会議向けで、チャネル内の会議向けではありません。</span><span class="sxs-lookup"><span data-stu-id="b951d-169">The add-in is for scheduled meetings with specific participants, not for meetings in a channel.</span></span> <span data-ttu-id="b951d-170">チャネル会議は Teams 内でスケジュール設定される必要があります。</span><span class="sxs-lookup"><span data-stu-id="b951d-170">Channel meetings must be scheduled from within Teams.</span></span>
- <span data-ttu-id="b951d-171">認証プロキシがユーザーの PC および Teams サービスのネットワーク パス内にある場合、アドインは機能しません。</span><span class="sxs-lookup"><span data-stu-id="b951d-171">The add-in will not work if an Authentication Proxy is in the network path of user's PC and Teams Services.</span></span>
- <span data-ttu-id="b951d-172">ユーザーが Outlook 内でライブ イベントをスケジュールすることはできません。</span><span class="sxs-lookup"><span data-stu-id="b951d-172">Users can't schedule live events from within Outlook.</span></span> <span data-ttu-id="b951d-173">Teams に移動し、ライブ イベントをスケジュールします。</span><span class="sxs-lookup"><span data-stu-id="b951d-173">Go to Teams to schedule live events.</span></span> <span data-ttu-id="b951d-174">詳細については、「[Microsoft Teams のライブ イベントについて](teams-live-events/what-are-teams-live-events.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b951d-174">For more information, see [What are Microsoft Teams live events?](teams-live-events/what-are-teams-live-events.md).</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="b951d-175">トラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="b951d-175">Troubleshooting</span></span>

<span data-ttu-id="b951d-176">Teams Meeting add-in for Outlook のアドインをインストールできない場合は、次のトラブルシューティングの手順を試してください。</span><span class="sxs-lookup"><span data-stu-id="b951d-176">If you cannot get the Teams Meeting add-in for Outlook to install, try these troubleshooting steps.</span></span>

- <span data-ttu-id="b951d-177">Outlook デスクトップ クライアントのすべての利用可能な更新プログラムが適用されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="b951d-177">Ensure all available updates for Outlook desktop client have been applied.</span></span>
- <span data-ttu-id="b951d-178">Teamsのデスクトップ クライアントを再起動します。</span><span class="sxs-lookup"><span data-stu-id="b951d-178">Restart the Teams desktop client.</span></span>
- <span data-ttu-id="b951d-179">[Teamsのデスクトップ クライアント]からサインアウトして、もう一度サインインします。</span><span class="sxs-lookup"><span data-stu-id="b951d-179">Sign out and then sign back in to the Teams desktop client.</span></span>
- <span data-ttu-id="b951d-180">Outlook デスクトップ クライアントを再起動します。</span><span class="sxs-lookup"><span data-stu-id="b951d-180">Restart the Outlook desktop client.</span></span> <span data-ttu-id="b951d-181">(管理者モードで Outlook が実行されていないことを確認してください。)</span><span class="sxs-lookup"><span data-stu-id="b951d-181">(Make sure Outlook isn’t running in admin mode.)</span></span>
- <span data-ttu-id="b951d-182">ログインしているユーザー アカウント名にスペースが含まれていないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="b951d-182">Make sure the logged-in user account name does not contain spaces.</span></span> <span data-ttu-id="b951d-183">これは既知の問題であり、今後のビルドで修正される予定です。</span><span class="sxs-lookup"><span data-stu-id="b951d-183">(This is a known issue, and will be fixed in a future update.)</span></span>
- <span data-ttu-id="b951d-184">シングル サインオン (SSO) が有効になっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="b951d-184">Make sure single sign-on (SSO) is enabled.</span></span>

<span data-ttu-id="b951d-185">管理者が、[Exchange Web Server (EWS) へのアクセスを制御する](https://docs.microsoft.com/exchange/client-developer/exchange-web-services/how-to-control-access-to-ews-in-exchange)ように Microsoft Exchange を構成している場合、代理人は上司の代わりに Teams 会議をスケジュールできません。</span><span class="sxs-lookup"><span data-stu-id="b951d-185">If your administrator has configured Microsoft Exchange to [control access to Exchange Web Server (EWS)](https://docs.microsoft.com/exchange/client-developer/exchange-web-services/how-to-control-access-to-ews-in-exchange), a delegate won't be able to schedule a Teams meeting on behalf of the boss.</span></span> <span data-ttu-id="b951d-186">この構成のソリューションは開発中で、今後リリースされる予定です。</span><span class="sxs-lookup"><span data-stu-id="b951d-186">The solution for this configuration is under development and will be released in the future.</span></span> 

<span data-ttu-id="b951d-187">アドインを無効にする方法につぃての全般的なガイドラインについては、「[Office プログラムでアドインを表示、管理、インストールする](https://support.office.com/article/View-manage-and-install-add-ins-in-Office-programs-16278816-1948-4028-91E5-76DCA5380F8D)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="b951d-187">For general guidance about how to disable add-ins, see [View, manage, and install add-ins in Office programs](https://support.office.com/article/View-manage-and-install-add-ins-in-Office-programs-16278816-1948-4028-91E5-76DCA5380F8D).</span></span>

<span data-ttu-id="b951d-188">Microsoft Teams での会議と通話については[こちら](https://support.office.com/article/Meetings-and-calls-d92432d5-dd0f-4d17-8f69-06096b6b48a8)をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="b951d-188">Learn more about [meetings and calling in Microsoft Teams](https://support.office.com/article/Meetings-and-calls-d92432d5-dd0f-4d17-8f69-06096b6b48a8).</span></span>
