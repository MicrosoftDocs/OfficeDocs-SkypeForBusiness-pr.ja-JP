---
title: Outlook で Microsoft Teams の会議アドインを使用する
author: LanaChin
ms.author: v-lanac
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
ms.openlocfilehash: 26eb3af88b6e16de0535d25d4b5205a72626b7b2
ms.sourcegitcommit: df4dde0fe6ce9e26cb4b3da4e4b878538d31decc
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/15/2020
ms.locfileid: "43521533"
---
<a name="use-the-teams-meeting-add-in-in-outlook"></a><span data-ttu-id="5952b-103">Outlook で Teams の会議アドインを使用する</span><span class="sxs-lookup"><span data-stu-id="5952b-103">Use the Teams Meeting add-in in Outlook</span></span>
=======================================

<span data-ttu-id="5952b-104">Teams 会議アドインを使用すると、ユーザーは Outlook から Teams 会議をスケジュールできます。</span><span class="sxs-lookup"><span data-stu-id="5952b-104">The Teams Meeting add-in lets users schedule a Teams meeting from Outlook.</span></span> <span data-ttu-id="5952b-105">このアドインは、Outlook for Windows、Mac、Web、モバイルで使用できます。</span><span class="sxs-lookup"><span data-stu-id="5952b-105">The add-in is available for Outlook on Windows, Mac, web, and mobile.</span></span>

## <a name="teams-meeting-add-in-in-outlook-for-windows"></a><span data-ttu-id="5952b-106">Windows 用 Outlook の Teams 会議アドイン</span><span class="sxs-lookup"><span data-stu-id="5952b-106">Teams Meeting add-in in Outlook for Windows</span></span>

<span data-ttu-id="5952b-107">Teams の会議アドインは、Microsoft Teams と Office 2010、Office 2013 または Office 2016 を自分の Windows PC にインストール済みのユーザーに対して、自動的にインストールされます。</span><span class="sxs-lookup"><span data-stu-id="5952b-107">The Teams Meeting add-in is automatically installed for users who have Microsoft Teams and either Office 2010, Office 2013 or Office 2016 installed on their Windows PC.</span></span> <span data-ttu-id="5952b-108">Teams の会議アドインは、ユーザーが使用する Outlook の [予定表] リボン上に表示されます。</span><span class="sxs-lookup"><span data-stu-id="5952b-108">Users will see the Teams Meeting add-in on the Outlook Calendar ribbon.</span></span>

![Outlook リボン上の Teams 会議アドインのスクリーンショット](media/Teams-add-in-for-Outlook.png)

> [!NOTE]
> - <span data-ttu-id="5952b-110">組織で Teams と Skype for Business の両方を実行している場合は、その他の考慮事項があります。</span><span class="sxs-lookup"><span data-stu-id="5952b-110">There are additional considerations if your organization runs both Teams and Skype for Business.</span></span> <span data-ttu-id="5952b-111">状況によっては、Outlook で Teams アドインを使用できない場合があります。</span><span class="sxs-lookup"><span data-stu-id="5952b-111">Under some circumstances, the Teams add-in is not available in Outlook.</span></span> <span data-ttu-id="5952b-112">詳細については、「 [Skype For business から Teams にアップグレードする](https://docs.microsoft.com/microsoftteams/upgrade-to-teams-on-prem-overview#meetings)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5952b-112">See [Upgrade from Skype for Business to Teams](https://docs.microsoft.com/microsoftteams/upgrade-to-teams-on-prem-overview#meetings) for details.</span></span>
> - <span data-ttu-id="5952b-113">Regsvr32.exe ファイルを実行するユーザーのアクセス許可は、コンピューターに Teams 会議アドインをインストールするための最小要件です。</span><span class="sxs-lookup"><span data-stu-id="5952b-113">User permissions to execute the Regsvr32.exe file is a minimum requirement for the Teams Meeting add-in to be installed on the computer.</span></span>
> - <span data-ttu-id="5952b-114">Teams の会議アドインが表示されないユーザーに対しては、Outlook と Teams を閉じて、先に Teams クライアントを再起動してから Teams にサインインし、次に Outlook クライアントを再起動する操作を順に行うよう指示します。</span><span class="sxs-lookup"><span data-stu-id="5952b-114">If users do not see the Teams Meeting add-in, instruct them to close Outlook and Teams, then restart the Teams client first, then sign in to Teams, and then restart the Outlook client, in that specific order.</span></span>
> - <span data-ttu-id="5952b-115">Microsoft ストアから Office Outlook のインストールを使用している場合、Teams 会議アドインはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="5952b-115">If you are using an Office Outlook installation from the Microsoft Store, the Teams Meeting add-in isn't supported.</span></span> <span data-ttu-id="5952b-116">このアドインが必要なユーザーは、「[S モードでの Windows 10 の Office](https://support.office.com/article/faq-office-on-windows-10-in-s-mode-717193b5-ff9f-4388-84c0-277ddf07fe3f)」の記事で説明されているとおり、Office のクイック実行バージョンをインストールすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="5952b-116">Users who require this add-in are advised to install Click-to-Run version of Office, as outlined in [Office on Windows 10 in S mode](https://support.office.com/article/faq-office-on-windows-10-in-s-mode-717193b5-ff9f-4388-84c0-277ddf07fe3f) article.</span></span>

## <a name="teams-meeting-add-in-in-outlook-for-mac"></a><span data-ttu-id="5952b-117">Outlook for Mac の Teams 会議アドイン</span><span class="sxs-lookup"><span data-stu-id="5952b-117">Teams Meeting add-in in Outlook for Mac</span></span>

<span data-ttu-id="5952b-118">Outlook の製品版 16.24.414.0 以降が実行されていて、Office 365 クライアント サブスクリプションでアクティブになっている場合、Outlook for Mac で [Teams 会議] ボタンは Outlook for Mac のリボンに表示されます。</span><span class="sxs-lookup"><span data-stu-id="5952b-118">The Teams Meeting button in Outlook for Mac will appear in the Outlook for Mac ribbon if Outlook is running production build 16.24.414.0 and later and is activated with an Office 365 client subscription.</span></span>

<span data-ttu-id="5952b-119">ユーザーが [**送信**] をクリックすると、会議の調整 (Teams への参加リンクおよびダイヤルイン番号) が会議出席依頼に追加されます。</span><span class="sxs-lookup"><span data-stu-id="5952b-119">The meeting coordinates (the Teams join link and dial-in numbers) will be added to the meeting invite after the user clicks **Send**.</span></span>  

## <a name="teams-meeting-add-in-in-outlook-web-app"></a><span data-ttu-id="5952b-120">Outlook Web App の Teams 会議アドイン</span><span class="sxs-lookup"><span data-stu-id="5952b-120">Teams Meeting add-in in Outlook Web App</span></span>

<span data-ttu-id="5952b-121">ユーザーが新しい Outlook on the Web の初期バージョンを使用している場合、Outlook Web App の [Teams 会議] ボタンが新しいイベント作成の一部として表示されます。</span><span class="sxs-lookup"><span data-stu-id="5952b-121">The Teams Meetings button in Outlook Web App will appear as part of new event creation if the user is on an early version of the new Outlook on the web.</span></span> <span data-ttu-id="5952b-122">ユーザーが Outlook on the Web の初期バージョンを試す方法については、「[Outlook のブログ](https://techcommunity.microsoft.com/t5/Outlook-Blog/Designed-to-be-fast-The-Outlook-on-the-web-user-experience-gets/ba-p/234909?utm_source=t.co&utm_medium=referral)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5952b-122">See the [Outlook Blog](https://techcommunity.microsoft.com/t5/Outlook-Blog/Designed-to-be-fast-The-Outlook-on-the-web-user-experience-gets/ba-p/234909?utm_source=t.co&utm_medium=referral) to learn about how users can try the early version of the new Outlook on the web.</span></span>

![Outlook Web App の Teams 会議アドインのスクリーンショット](media/teams-meeting-add-in-web.png)

<span data-ttu-id="5952b-124">ユーザーが [**送信**] をクリックすると、会議の調整 (Teams への参加リンクおよびダイヤルイン番号) が会議出席依頼に追加されます。</span><span class="sxs-lookup"><span data-stu-id="5952b-124">The meeting coordinates (the Teams join link and dial-in numbers) will be added to the meeting invite after the user clicks **Send**.</span></span>  

## <a name="teams-meeting-add-in-in-outlook-mobile-ios-and-android"></a><span data-ttu-id="5952b-125">Outlook モバイル (iOS および Android) の Teams 会議アドイン</span><span class="sxs-lookup"><span data-stu-id="5952b-125">Teams Meeting add-in in Outlook mobile (iOS and Android)</span></span>

<span data-ttu-id="5952b-126">iOS と Android の Outlook アプリの最新ビルドには、Teams 会議ボタンが表示されます。</span><span class="sxs-lookup"><span data-stu-id="5952b-126">The Teams Meeting button shows up in latest builds of the Outlook iOS and Android app.</span></span>

![Outlook モバイルの Teams 会議アドインのスクリーンショット](media/teams-meeting-add-in-mobile.png)

<span data-ttu-id="5952b-128">ユーザーが [**送信**] をクリックすると、会議の調整 (Teams への参加リンクおよびダイヤルイン番号) が会議出席依頼に追加されます。</span><span class="sxs-lookup"><span data-stu-id="5952b-128">The meeting coordinates (the Teams join link and dial-in numbers) will be added to the meeting invite after the user clicks **Send**.</span></span>  

## <a name="teams-meeting-add-in-in-and-findtime-for-outlook"></a><span data-ttu-id="5952b-129">Outlook の Teams 会議アドインと FindTime</span><span class="sxs-lookup"><span data-stu-id="5952b-129">Teams Meeting add-in in and FindTime for Outlook</span></span>
<span data-ttu-id="5952b-130">FindTime は、Outlook 用のアドインです。これは、企業全体の会議時間に関してユーザが合意できるようにします。</span><span class="sxs-lookup"><span data-stu-id="5952b-130">FindTime is an add-in for Outlook that helps users reach a consensus on a meeting time across companies.</span></span> <span data-ttu-id="5952b-131">会議の招待者が希望の時間を提示したら、FindTime はユーザーの代わりに会議出席依頼を送信します。</span><span class="sxs-lookup"><span data-stu-id="5952b-131">Once the meeting invitees have provided their preferred times, FindTime sends out the meeting invite on the user's behalf.</span></span> <span data-ttu-id="5952b-132">FindTime で [**オンライン会議**] オプションが選択されている場合、FindTime は Skype for Business または Microsoft Teams の会議をスケジュールします。</span><span class="sxs-lookup"><span data-stu-id="5952b-132">If the **Online meeting** option is selected in FindTime, FindTime will schedule a Skype for Business or Microsoft Teams meeting.</span></span> <span data-ttu-id="5952b-133">(FindTime は、既定のオンライン会議チャネルとして、組織が設定したものを使用します。)</span><span class="sxs-lookup"><span data-stu-id="5952b-133">(FindTime will use whichever has been set by your organization as the default online meeting channel.)</span></span>

> [!NOTE]  
> <span data-ttu-id="5952b-134">[Findtime ダッシュボード](https://findtime.microsoft.com/UserDashboard)で Skype for Business の設定を保存した場合、FindTime は Microsoft Teams の代わりにその設定を使用します。</span><span class="sxs-lookup"><span data-stu-id="5952b-134">If you saved a Skype for Business setting in your [Findtime dashboard](https://findtime.microsoft.com/UserDashboard), FindTime will use that instead of Microsoft Teams.</span></span> <span data-ttu-id="5952b-135">Microsoft Teams を使用する場合は、ダッシュボードの Skype for Business の設定を削除します。</span><span class="sxs-lookup"><span data-stu-id="5952b-135">If you want to use Microsoft Teams, delete the Skype for Business setting in your dashboard.</span></span>

<span data-ttu-id="5952b-136">詳細については、「[FindTime で会議をスケジュールする](https://support.office.com/article/scheduling-meetings-with-findtime-4dc806ed-fde3-4ea7-8c5e-b5d1fddab4a6)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5952b-136">See [Schedule meetings with FindTime](https://support.office.com/article/scheduling-meetings-with-findtime-4dc806ed-fde3-4ea7-8c5e-b5d1fddab4a6) for more information.</span></span>

## <a name="authentication-requirements"></a><span data-ttu-id="5952b-137">認証要件</span><span class="sxs-lookup"><span data-stu-id="5952b-137">Authentication requirements</span></span>

<span data-ttu-id="5952b-138">Teams の会議アドインでは、ユーザーが認証要件を使用して Teams にサインインすることが必要になります。</span><span class="sxs-lookup"><span data-stu-id="5952b-138">The Teams Meeting add-in requires users to sign in to Teams using Modern Authentication.</span></span> <span data-ttu-id="5952b-139">ユーザーがこのメソッドを使用してサインインしていない場合は、引き続き Teams クライアントを使用できますが、Outlook アドインを使用してチームのオンライン会議をスケジュールすることはできません。</span><span class="sxs-lookup"><span data-stu-id="5952b-139">If users do not use this method to sign in, they'll still be able to use the Teams client, but will be unable to schedule Teams online meetings using the Outlook add-in.</span></span> <span data-ttu-id="5952b-140">これを修正するには、次のいずれかを実行します。</span><span class="sxs-lookup"><span data-stu-id="5952b-140">You can fix this by doing one of the following:</span></span>

- <span data-ttu-id="5952b-141">先進認証が組織に対して構成されていない場合は、先進認証を構成します。</span><span class="sxs-lookup"><span data-stu-id="5952b-141">If Modern Authentication is not configured for your organization, you should configure Modern Authentication.</span></span>
- <span data-ttu-id="5952b-142">先進認証が構成されていているのにダイアログ ボックスでユーザーが無効になってしまう場合は、それらのユーザーに対して多要素認証を使用してサインインし直すよう指示します。</span><span class="sxs-lookup"><span data-stu-id="5952b-142">If Modern Authentication is configured, but they canceled out on the dialog box, you should instruct users to sign in again using multi-factor authentication.</span></span>

<span data-ttu-id="5952b-143">認証を構成する方法の詳細については、「[Microsoft Teams での ID モデルと認証](identify-models-authentication.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="5952b-143">To learn more about how to configure authentication, see [Identity models and authentication in Microsoft Teams](identify-models-authentication.md).</span></span>

## <a name="enable-private-meetings"></a><span data-ttu-id="5952b-144">プライベート会議を有効にする</span><span class="sxs-lookup"><span data-stu-id="5952b-144">Enable private meetings</span></span>

<span data-ttu-id="5952b-145">アドインを展開するには、Microsoft Teams 管理センターで [**プライベート会議のスケジュールを設定できるようになります**] を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="5952b-145">**Allow scheduling for private meetings** must be enabled in the Microsoft Teams admin center for the add-in to get deployed.</span></span> <span data-ttu-id="5952b-146">管理センターで**Meetings** > **Meeting Policies**に行き、**一般的な**セクションで、**Allow scheduling private meetings**をオンに切り替えるます。)</span><span class="sxs-lookup"><span data-stu-id="5952b-146">In the admin center, go to **Meetings** > **Meeting Policies**, and in the **General** section, toggle **Allow scheduling private meetings** to On.)</span></span>

![Microsoft Teams管理センターの設定のスクリーンショット。](media/teams-add-in-for-outlook-image1.png)

<span data-ttu-id="5952b-148">Teams クライアントはユーザーが必要としているのが 32 ビット版か 64 ビット版かを判断して正しいアドインをインストールします。</span><span class="sxs-lookup"><span data-stu-id="5952b-148">The Teams client installs the correct add-in by determining if users need the 32-bit or 64-bit version.</span></span>

> [!NOTE]
> <span data-ttu-id="5952b-149">ユーザーは最新のアドインを利用できるようになるために Teams のインストールまたはアップグレード後に Outlook の再起動が必要になる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="5952b-149">Users might need to restart Outlook after an installation or upgrade of Teams to get the latest add-in.</span></span>

## <a name="teams-upgrade-policy-and-the-teams-meeting-add-in-for-outlook"></a><span data-ttu-id="5952b-150">Teams のアップグレード ポリシーと Outlook 用 Teams 会議アドイン</span><span class="sxs-lookup"><span data-stu-id="5952b-150">Teams upgrade policy and the Teams Meeting add-in for Outlook</span></span>

<span data-ttu-id="5952b-151">お客様は、[Skype for Business から Teams へのアップグレード手順を選択する](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)ことができます。</span><span class="sxs-lookup"><span data-stu-id="5952b-151">Customers can [choose their upgrade journey from Skype for Business to Teams](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md).</span></span> <span data-ttu-id="5952b-152">テナント管理者は、Teams の共存モードを使用して、ユーザーにこの手順を定義できます。</span><span class="sxs-lookup"><span data-stu-id="5952b-152">Tenant admins can use the Teams co-existence mode to define this journey for their users.</span></span> <span data-ttu-id="5952b-153">テナント管理者には、ユーザーが Skype for Business (アイランド モード) と共に Teams を使用できるようにするオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="5952b-153">Tenant admins have the option to enable users to use Teams alongside Skype for Business (Islands mode).</span></span> 

<span data-ttu-id="5952b-154">アイランド モードのユーザは、Outlook で会議をスケジュールする場合、通常は Skype for Business と Teams の会議のどちらをスケジュールするか選択できると想定しています。</span><span class="sxs-lookup"><span data-stu-id="5952b-154">When users who are in Island mode schedule a meeting in Outlook, they typically expect to be able to choose whether to schedule a Skype for Business or a Teams meeting.</span></span> <span data-ttu-id="5952b-155">Outlook on the web、Outlook Windows、および Outlook Mac では、アイランド モードの場合、Skype for Business および Teams アドインの両方が表示されます。</span><span class="sxs-lookup"><span data-stu-id="5952b-155">In Outlook on the web, Outlook Windows, and Outlook Mac, users see both Skype for Business and Teams add-ins when in Islands mode.</span></span> <span data-ttu-id="5952b-156">初期リリースではいくつかの制限があるため、Outlook モバイルは Skype for Business **または** Teams の会議の作成のみをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="5952b-156">Due to certain limitations in the initial release, Outlook mobile can only support creating Skype for Business **or** Teams meetings.</span></span> <span data-ttu-id="5952b-157">詳細は次の表を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5952b-157">See the following table for details.</span></span>

| <span data-ttu-id="5952b-158">Teams 管理センターの共存モード</span><span class="sxs-lookup"><span data-stu-id="5952b-158">Coexistence mode in the Teams admin center</span></span> | <span data-ttu-id="5952b-159">Outlook モバイルの既定の会議プロバイダー</span><span class="sxs-lookup"><span data-stu-id="5952b-159">Default meetings provider in Outlook mobile</span></span> |
| --------------------------------------|---------------------------------------------|
| <span data-ttu-id="5952b-160">アイランド</span><span class="sxs-lookup"><span data-stu-id="5952b-160">Islands</span></span> | <span data-ttu-id="5952b-161">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="5952b-161">Skype for Business</span></span> |
| <span data-ttu-id="5952b-162">Skype for Business のみ</span><span class="sxs-lookup"><span data-stu-id="5952b-162">Skype for Business only</span></span> | <span data-ttu-id="5952b-163">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="5952b-163">Skype for Business</span></span> |
| <span data-ttu-id="5952b-164">Skype for Business と Teams の共同作業</span><span class="sxs-lookup"><span data-stu-id="5952b-164">Skype for Business with Teams collaboration</span></span> | <span data-ttu-id="5952b-165">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="5952b-165">Skype for Business</span></span> |
| <span data-ttu-id="5952b-166">Skype for Business と Teams の共同作業と会議</span><span class="sxs-lookup"><span data-stu-id="5952b-166">Skype for Business with Teams collaboration and meetings</span></span> | <span data-ttu-id="5952b-167">Teams</span><span class="sxs-lookup"><span data-stu-id="5952b-167">Teams</span></span> |
| <span data-ttu-id="5952b-168">Teams のみ</span><span class="sxs-lookup"><span data-stu-id="5952b-168">Teams only</span></span> | <span data-ttu-id="5952b-169">Teams</span><span class="sxs-lookup"><span data-stu-id="5952b-169">Teams</span></span> |

## <a name="other-considerations"></a><span data-ttu-id="5952b-170">その他の考慮事項</span><span class="sxs-lookup"><span data-stu-id="5952b-170">Other considerations</span></span>

<span data-ttu-id="5952b-171">Teams の会議アドインは継続して機能が開発されていますので、次について認識しておいてください。</span><span class="sxs-lookup"><span data-stu-id="5952b-171">The Teams Meeting add-in is still building functionality, so be aware of the following:</span></span>

- <span data-ttu-id="5952b-172">このアドインは、特定の参加者でスケジュール設定された会議向けで、チャネル内の会議向けではありません。</span><span class="sxs-lookup"><span data-stu-id="5952b-172">The add-in is for scheduled meetings with specific participants, not for meetings in a channel.</span></span> <span data-ttu-id="5952b-173">チャネル会議は Teams 内でスケジュール設定される必要があります。</span><span class="sxs-lookup"><span data-stu-id="5952b-173">Channel meetings must be scheduled from within Teams.</span></span>
- <span data-ttu-id="5952b-174">認証プロキシがユーザーの PC および Teams サービスのネットワーク パス内にある場合、アドインは機能しません。</span><span class="sxs-lookup"><span data-stu-id="5952b-174">The add-in will not work if an Authentication Proxy is in the network path of user's PC and Teams Services.</span></span>
- <span data-ttu-id="5952b-175">ユーザーが Outlook 内でライブ イベントをスケジュールすることはできません。</span><span class="sxs-lookup"><span data-stu-id="5952b-175">Users can't schedule live events from within Outlook.</span></span> <span data-ttu-id="5952b-176">Teams に移動し、ライブ イベントをスケジュールします。</span><span class="sxs-lookup"><span data-stu-id="5952b-176">Go to Teams to schedule live events.</span></span> <span data-ttu-id="5952b-177">詳細については、「[Microsoft Teams のライブ イベントについて](teams-live-events/what-are-teams-live-events.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5952b-177">For more information, see [What are Microsoft Teams live events?](teams-live-events/what-are-teams-live-events.md).</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="5952b-178">トラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="5952b-178">Troubleshooting</span></span>

<span data-ttu-id="5952b-179">Teams Meeting add-in for Outlook のアドインをインストールできない場合は、次のトラブルシューティングの手順を試してください。</span><span class="sxs-lookup"><span data-stu-id="5952b-179">If you cannot get the Teams Meeting add-in for Outlook to install, try these troubleshooting steps.</span></span>

- <span data-ttu-id="5952b-180">Outlook デスクトップ クライアントのすべての利用可能な更新プログラムが適用されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="5952b-180">Ensure all available updates for Outlook desktop client have been applied.</span></span>
- <span data-ttu-id="5952b-181">Teamsのデスクトップ クライアントを再起動します。</span><span class="sxs-lookup"><span data-stu-id="5952b-181">Restart the Teams desktop client.</span></span>
- <span data-ttu-id="5952b-182">[Teamsのデスクトップ クライアント]からサインアウトして、もう一度サインインします。</span><span class="sxs-lookup"><span data-stu-id="5952b-182">Sign out and then sign back in to the Teams desktop client.</span></span>
- <span data-ttu-id="5952b-183">Outlook デスクトップ クライアントを再起動します。</span><span class="sxs-lookup"><span data-stu-id="5952b-183">Restart the Outlook desktop client.</span></span> <span data-ttu-id="5952b-184">(Outlook が管理者モードで実行されていないことを確認します)。</span><span class="sxs-lookup"><span data-stu-id="5952b-184">(Make sure Outlook isn't running in admin mode.)</span></span>
- <span data-ttu-id="5952b-185">ログインしているユーザー アカウント名にスペースが含まれていないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="5952b-185">Make sure the logged-in user account name does not contain spaces.</span></span> <span data-ttu-id="5952b-186">これは既知の問題であり、今後のビルドで修正される予定です。</span><span class="sxs-lookup"><span data-stu-id="5952b-186">(This is a known issue, and will be fixed in a future update.)</span></span>
- <span data-ttu-id="5952b-187">シングル サインオン (SSO) が有効になっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="5952b-187">Make sure single sign-on (SSO) is enabled.</span></span>

<span data-ttu-id="5952b-188">管理者が、[Exchange Web Server (EWS) へのアクセスを制御する](https://docs.microsoft.com/exchange/client-developer/exchange-web-services/how-to-control-access-to-ews-in-exchange)ように Microsoft Exchange を構成している場合、代理人は上司の代わりに Teams 会議をスケジュールできません。</span><span class="sxs-lookup"><span data-stu-id="5952b-188">If your administrator has configured Microsoft Exchange to [control access to Exchange Web Server (EWS)](https://docs.microsoft.com/exchange/client-developer/exchange-web-services/how-to-control-access-to-ews-in-exchange), a delegate won't be able to schedule a Teams meeting on behalf of the boss.</span></span> <span data-ttu-id="5952b-189">この構成のソリューションは開発中で、今後リリースされる予定です。</span><span class="sxs-lookup"><span data-stu-id="5952b-189">The solution for this configuration is under development and will be released in the future.</span></span> 

<span data-ttu-id="5952b-190">アドインを無効にする方法につぃての全般的なガイドラインについては、「[Office プログラムでアドインを表示、管理、インストールする](https://support.office.com/article/View-manage-and-install-add-ins-in-Office-programs-16278816-1948-4028-91E5-76DCA5380F8D)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="5952b-190">For general guidance about how to disable add-ins, see [View, manage, and install add-ins in Office programs](https://support.office.com/article/View-manage-and-install-add-ins-in-Office-programs-16278816-1948-4028-91E5-76DCA5380F8D).</span></span>

<span data-ttu-id="5952b-191">Microsoft Teams での会議と通話については[こちら](https://support.office.com/article/Meetings-and-calls-d92432d5-dd0f-4d17-8f69-06096b6b48a8)をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="5952b-191">Learn more about [meetings and calling in Microsoft Teams](https://support.office.com/article/Meetings-and-calls-d92432d5-dd0f-4d17-8f69-06096b6b48a8).</span></span>
