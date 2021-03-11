---
title: Outlook で Microsoft Teams の会議アドインを使用する
author: cichur
ms.author: v-cichur
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: sonua
localization_priority: Priority
search.appverid: MET150
description: Microsoft Teams は、ユーザーが  Outlook から Teams の会議をスケジュール設定することができるようになるアドインを Outlook にインストールします。
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
ms.collection:
- M365-collaboration
- m365initiative-meetings
appliesto:
- Microsoft Teams
ms.openlocfilehash: fe8b9192c9d1b85e23f2d17daa067630cebd15f2
ms.sourcegitcommit: 31a585cc0fe6350efacf3a7771d1e590d5e4233c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/10/2021
ms.locfileid: "50614933"
---
<a name="use-the-teams-meeting-add-in-in-outlook"></a><span data-ttu-id="b0949-103">Outlook で Teams の会議アドインを使用する</span><span class="sxs-lookup"><span data-stu-id="b0949-103">Use the Teams Meeting add-in in Outlook</span></span>
=======================================

<span data-ttu-id="b0949-104">Teams 会議アドインを使用すると、ユーザーは Outlook から Teams 会議をスケジュールできます。</span><span class="sxs-lookup"><span data-stu-id="b0949-104">The Teams Meeting add-in lets users schedule a Teams meeting from Outlook.</span></span> <span data-ttu-id="b0949-105">このアドインは、Outlook for Windows、Mac、Web、モバイルで使用できます。</span><span class="sxs-lookup"><span data-stu-id="b0949-105">The add-in is available for Outlook on Windows, Mac, web, and mobile.</span></span>

## <a name="teams-meeting-add-in-in-outlook-for-windows"></a><span data-ttu-id="b0949-106">Windows 用 Outlook の Teams 会議アドイン</span><span class="sxs-lookup"><span data-stu-id="b0949-106">Teams Meeting add-in in Outlook for Windows</span></span>

<span data-ttu-id="b0949-107">Teams の会議アドインは、Microsoft Teams と Office 2013、Office 2016 または Office 2019 を自分の Windows PC にインストール済みのユーザーに対して、自動的にインストールされます。</span><span class="sxs-lookup"><span data-stu-id="b0949-107">The Teams Meeting add-in is automatically installed for users who have Microsoft Teams and either Office 2013, Office 2016, or Office 2019 installed on their Windows PC.</span></span> <span data-ttu-id="b0949-108">Teams の会議アドインは、ユーザーが使用する Outlook の [予定表] リボン上に表示されます。</span><span class="sxs-lookup"><span data-stu-id="b0949-108">Users will see the Teams Meeting add-in on the Outlook Calendar ribbon.</span></span>

![Outlook リボン上の Teams 会議アドインのスクリーンショット](media/Teams-add-in-for-Outlook.png)

> [!NOTE]
> - <span data-ttu-id="b0949-110">Teams アドインにリンクする **ダイレクト URL はありません**。</span><span class="sxs-lookup"><span data-stu-id="b0949-110">There is **no direct URL** that links to the Teams add-in.</span></span>
> - <span data-ttu-id="b0949-111">組織で Teams と Skype for Business の両方を使用している場合、その他にも考慮事項があります。</span><span class="sxs-lookup"><span data-stu-id="b0949-111">There are additional considerations if your organization runs both Teams and Skype for Business.</span></span> <span data-ttu-id="b0949-112">状況によっては、Teams アドインは Outlook では使用できません。</span><span class="sxs-lookup"><span data-stu-id="b0949-112">Under some circumstances, the Teams add-in is not available in Outlook.</span></span> <span data-ttu-id="b0949-113">詳細については、「[Skype for Business から Teams へのアップグレード](https://docs.microsoft.com/microsoftteams/upgrade-to-teams-on-prem-overview#meetings)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b0949-113">See [Upgrade from Skype for Business to Teams](https://docs.microsoft.com/microsoftteams/upgrade-to-teams-on-prem-overview#meetings) for details.</span></span>
> - <span data-ttu-id="b0949-114">Regsvr32.exe ファイルを実行するユーザーのアクセス許可は、コンピューターに Teams 会議アドインをインストールするための最小要件です。</span><span class="sxs-lookup"><span data-stu-id="b0949-114">User permissions to execute the Regsvr32.exe file is a minimum requirement for the Teams Meeting add-in to be installed on the computer.</span></span>
> - <span data-ttu-id="b0949-115">Teams の会議アドインが表示されないユーザーに対しては、Outlook と Teams を閉じて、先に Teams クライアントを再起動してから Teams にサインインし、次に Outlook クライアントを再起動する操作を順に行うよう指示します。</span><span class="sxs-lookup"><span data-stu-id="b0949-115">If users do not see the Teams Meeting add-in, instruct them to close Outlook and Teams, then restart the Teams client first, then sign in to Teams, and then restart the Outlook client, in that specific order.</span></span>
> - <span data-ttu-id="b0949-116">Microsoft ストアから Office Outlook のインストールを使用している場合、Teams 会議アドインはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="b0949-116">If you are using an Office Outlook installation from the Microsoft Store, the Teams Meeting add-in isn't supported.</span></span> <span data-ttu-id="b0949-117">このアドインが必要なユーザーは、「[S モードでの Windows 10 の Office](https://support.office.com/article/faq-office-on-windows-10-in-s-mode-717193b5-ff9f-4388-84c0-277ddf07fe3f)」の記事で説明されているとおり、Office のクイック実行バージョンをインストールすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="b0949-117">Users who require this add-in are advised to install Click-to-Run version of Office, as outlined in [Office on Windows 10 in S mode](https://support.office.com/article/faq-office-on-windows-10-in-s-mode-717193b5-ff9f-4388-84c0-277ddf07fe3f) article.</span></span>

## <a name="teams-meeting-add-in-in-outlook-for-mac"></a><span data-ttu-id="b0949-118">Outlook for Mac の Teams 会議アドイン</span><span class="sxs-lookup"><span data-stu-id="b0949-118">Teams Meeting add-in in Outlook for Mac</span></span>

<span data-ttu-id="b0949-119">Outlook の製品版 16.24.414.0 以降が実行されていて、Microsoft 365 または Office 365 クライアント サブスクリプションでアクティブになっている場合、Outlook for Mac で [Teams 会議] ボタンは Outlook for Mac のリボンに表示されます。</span><span class="sxs-lookup"><span data-stu-id="b0949-119">The Teams Meeting button in Outlook for Mac will appear in the Outlook for Mac ribbon if Outlook is running production build 16.24.414.0 and later and is activated with a Microsoft 365 or Office 365 client subscription.</span></span>

<span data-ttu-id="b0949-120">ユーザーが [**送信**] をクリックすると、会議の調整 (Teams への参加リンクおよびダイヤルイン番号) が会議出席依頼に追加されます。</span><span class="sxs-lookup"><span data-stu-id="b0949-120">The meeting coordinates (the Teams join link and dial-in numbers) will be added to the meeting invite after the user clicks **Send**.</span></span>  

## <a name="teams-meeting-add-in-in-outlook-web-app"></a><span data-ttu-id="b0949-121">Outlook Web App の Teams 会議アドイン</span><span class="sxs-lookup"><span data-stu-id="b0949-121">Teams Meeting add-in in Outlook Web App</span></span>

<span data-ttu-id="b0949-122">ユーザーが新しい Outlook on the Web の初期バージョンを使用している場合、Outlook Web App の [Teams 会議] ボタンが新しいイベント作成の一部として表示されます。</span><span class="sxs-lookup"><span data-stu-id="b0949-122">The Teams Meetings button in Outlook Web App will appear as part of new event creation if the user is on an early version of the new Outlook on the web.</span></span> <span data-ttu-id="b0949-123">ユーザーが Outlook on the Web の初期バージョンを試す方法については、「[Outlook のブログ](https://techcommunity.microsoft.com/t5/Outlook-Blog/Designed-to-be-fast-The-Outlook-on-the-web-user-experience-gets/ba-p/234909?utm_source=t.co&utm_medium=referral)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b0949-123">See the [Outlook Blog](https://techcommunity.microsoft.com/t5/Outlook-Blog/Designed-to-be-fast-The-Outlook-on-the-web-user-experience-gets/ba-p/234909?utm_source=t.co&utm_medium=referral) to learn about how users can try the early version of the new Outlook on the web.</span></span>

![Outlook Web App の Teams 会議アドインのスクリーンショット](media/teams-meeting-add-in-web.png)

<span data-ttu-id="b0949-125">ユーザーが [**送信**] をクリックすると、会議の調整 (Teams への参加リンクおよびダイヤルイン番号) が会議出席依頼に追加されます。</span><span class="sxs-lookup"><span data-stu-id="b0949-125">The meeting coordinates (the Teams join link and dial-in numbers) will be added to the meeting invite after the user clicks **Send**.</span></span>  

## <a name="teams-meeting-add-in-in-outlook-mobile-ios-and-android"></a><span data-ttu-id="b0949-126">Outlook モバイル (iOS および Android) の Teams 会議アドイン</span><span class="sxs-lookup"><span data-stu-id="b0949-126">Teams Meeting add-in in Outlook mobile (iOS and Android)</span></span>

<span data-ttu-id="b0949-127">iOS と Android の Outlook アプリの最新ビルドには、Teams 会議ボタンが表示されます。</span><span class="sxs-lookup"><span data-stu-id="b0949-127">The Teams Meeting button shows up in latest builds of the Outlook iOS and Android app.</span></span>

![Outlook モバイルの Teams 会議アドインのスクリーンショット](media/teams-meeting-add-in-mobile.png)

<span data-ttu-id="b0949-129">ユーザーが [**送信**] をクリックすると、会議の調整 (Teams への参加リンクおよびダイヤルイン番号) が会議出席依頼に追加されます。</span><span class="sxs-lookup"><span data-stu-id="b0949-129">The meeting coordinates (the Teams join link and dial-in numbers) will be added to the meeting invite after the user clicks **Send**.</span></span>  

## <a name="teams-meeting-add-in-and-findtime-for-outlook"></a><span data-ttu-id="b0949-130">Teams 会議アドインと Outlook 用 FindTime</span><span class="sxs-lookup"><span data-stu-id="b0949-130">Teams Meeting add-in and FindTime for Outlook</span></span>

<span data-ttu-id="b0949-131">FindTime は、Outlook 用のアドインです。これは、企業全体での会議時間に関するユーザーの合意形成を支援します。</span><span class="sxs-lookup"><span data-stu-id="b0949-131">FindTime is an add-in for Outlook that helps users reach consensus on a meeting time across companies.</span></span> <span data-ttu-id="b0949-132">会議の招待者が希望の時間を提示したら、FindTime はユーザーの代わりに会議出席依頼を送信します。</span><span class="sxs-lookup"><span data-stu-id="b0949-132">Once the meeting invitees have provided their preferred times, FindTime sends out the meeting invite on the user's behalf.</span></span> <span data-ttu-id="b0949-133">FindTime で [**オンライン会議**] オプションが選択されている場合、FindTime は Skype for Business または Microsoft Teams の会議をスケジュールします。</span><span class="sxs-lookup"><span data-stu-id="b0949-133">If the **Online meeting** option is selected in FindTime, FindTime will schedule a Skype for Business or Microsoft Teams meeting.</span></span> <span data-ttu-id="b0949-134">(FindTime は、既定のオンライン会議チャネルとして、組織が設定したものを使用します。)</span><span class="sxs-lookup"><span data-stu-id="b0949-134">(FindTime will use whichever has been set by your organization as the default online meeting channel.)</span></span>

> [!NOTE]  
> <span data-ttu-id="b0949-135">[Findtime ダッシュボード](https://findtime.microsoft.com/UserDashboard)で Skype for Business の設定を保存した場合、FindTime は Microsoft Teams の代わりにその設定を使用します。</span><span class="sxs-lookup"><span data-stu-id="b0949-135">If you saved a Skype for Business setting in your [Findtime dashboard](https://findtime.microsoft.com/UserDashboard), FindTime will use that instead of Microsoft Teams.</span></span> <span data-ttu-id="b0949-136">Microsoft Teams を使用する場合は、ダッシュボードの Skype for Business の設定を削除します。</span><span class="sxs-lookup"><span data-stu-id="b0949-136">If you want to use Microsoft Teams, delete the Skype for Business setting in your dashboard.</span></span>

<span data-ttu-id="b0949-137">詳細については、「[FindTime で会議をスケジュールする](https://support.office.com/article/scheduling-meetings-with-findtime-4dc806ed-fde3-4ea7-8c5e-b5d1fddab4a6)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b0949-137">For more information, see [Schedule meetings with FindTime](https://support.office.com/article/scheduling-meetings-with-findtime-4dc806ed-fde3-4ea7-8c5e-b5d1fddab4a6).</span></span>

## <a name="authentication-requirements"></a><span data-ttu-id="b0949-138">認証要件</span><span class="sxs-lookup"><span data-stu-id="b0949-138">Authentication requirements</span></span>

<span data-ttu-id="b0949-139">Teams の会議アドインでは、ユーザーが認証要件を使用して Teams にサインインすることが必要になります。</span><span class="sxs-lookup"><span data-stu-id="b0949-139">The Teams Meeting add-in requires users to sign in to Teams using Modern Authentication.</span></span> <span data-ttu-id="b0949-140">ユーザーがこの方法を使用せずにサインインした場合、Teams クライアントを使用することはできますが、Outlook アドインを使用して [Teams のオンライン会議](https://www.microsoft.com/microsoft-teams/online-meetings)をスケジュール設定することはできません。</span><span class="sxs-lookup"><span data-stu-id="b0949-140">If users do not use this method to sign in, they'll still be able to use the Teams client, but will be unable to schedule [Teams online meetings](https://www.microsoft.com/microsoft-teams/online-meetings) using the Outlook add-in.</span></span> <span data-ttu-id="b0949-141">これを修正するには、次のいずれかを実行します。</span><span class="sxs-lookup"><span data-stu-id="b0949-141">You can fix this by doing one of the following:</span></span>

- <span data-ttu-id="b0949-142">先進認証が組織に対して構成されていない場合は、先進認証を構成します。</span><span class="sxs-lookup"><span data-stu-id="b0949-142">If Modern Authentication is not configured for your organization, you should configure Modern Authentication.</span></span>
- <span data-ttu-id="b0949-143">先進認証が構成されていているのにダイアログ ボックスでユーザーが無効になってしまう場合は、それらのユーザーに対して多要素認証を使用してサインインし直すよう指示します。</span><span class="sxs-lookup"><span data-stu-id="b0949-143">If Modern Authentication is configured, but they canceled out on the dialog box, you should instruct users to sign in again using multi-factor authentication.</span></span>

<span data-ttu-id="b0949-144">認証を構成する方法の詳細については、「[Microsoft Teams での ID モデルと認証](identify-models-authentication.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="b0949-144">To learn more about how to configure authentication, see [Identity models and authentication in Microsoft Teams](identify-models-authentication.md).</span></span>

## <a name="enable-private-meetings"></a><span data-ttu-id="b0949-145">プライベート会議を有効にする</span><span class="sxs-lookup"><span data-stu-id="b0949-145">Enable private meetings</span></span>

<span data-ttu-id="b0949-146">アドインを展開するには、Microsoft Teams 管理センターで [**プライベート会議のスケジュールを設定できるようになります**] を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="b0949-146">**Allow scheduling for private meetings** must be enabled in the Microsoft Teams admin center for the add-in to get deployed.</span></span> <span data-ttu-id="b0949-147">管理センターで **Meetings** > **Meeting Policies** に行き、**一般的な** セクションで、**Allow scheduling private meetings** をオンに切り替えるます。)</span><span class="sxs-lookup"><span data-stu-id="b0949-147">In the admin center, go to **Meetings** > **Meeting Policies**, and in the **General** section, toggle **Allow scheduling private meetings** to On.)</span></span>

![Microsoft Teams管理センターの設定のスクリーンショット。](media/teams-add-in-for-outlook-image1.png)

<span data-ttu-id="b0949-149">Teams クライアントはユーザーが必要としているのが 32 ビット版か 64 ビット版かを判断して正しいアドインをインストールします。</span><span class="sxs-lookup"><span data-stu-id="b0949-149">The Teams client installs the correct add-in by determining if users need the 32-bit or 64-bit version.</span></span>

> [!NOTE]
> <span data-ttu-id="b0949-150">ユーザーは最新のアドインを利用できるようになるために Teams のインストールまたはアップグレード後に Outlook の再起動が必要になる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="b0949-150">Users might need to restart Outlook after an installation or upgrade of Teams to get the latest add-in.</span></span>

## <a name="teams-upgrade-policy-and-the-teams-meeting-add-in-for-outlook"></a><span data-ttu-id="b0949-151">Teams のアップグレード ポリシーと Outlook 用 Teams 会議アドイン</span><span class="sxs-lookup"><span data-stu-id="b0949-151">Teams upgrade policy and the Teams Meeting add-in for Outlook</span></span>

<span data-ttu-id="b0949-152">お客様は、[Skype for Business から Teams へのアップグレード手順を選択する](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)ことができます。</span><span class="sxs-lookup"><span data-stu-id="b0949-152">Customers can [choose their upgrade journey from Skype for Business to Teams](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md).</span></span> <span data-ttu-id="b0949-153">テナント管理者は、Teams の共存モードを使用して、ユーザーにこの手順を定義できます。</span><span class="sxs-lookup"><span data-stu-id="b0949-153">Tenant admins can use the Teams co-existence mode to define this journey for their users.</span></span> <span data-ttu-id="b0949-154">テナント管理者には、ユーザーが Skype for Business (アイランド モード) と共に Teams を使用できるようにするオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="b0949-154">Tenant admins have the option to enable users to use Teams alongside Skype for Business (Islands mode).</span></span> 

<span data-ttu-id="b0949-155">アイランド モードのユーザは、Outlook で会議をスケジュールする場合、通常は Skype for Business と Teams の会議のどちらをスケジュールするか選択できると想定しています。</span><span class="sxs-lookup"><span data-stu-id="b0949-155">When users who are in Island mode schedule a meeting in Outlook, they typically expect to be able to choose whether to schedule a Skype for Business or a Teams meeting.</span></span> <span data-ttu-id="b0949-156">Outlook on the web、Outlook Windows、および Outlook Mac では、アイランド モードの場合は、既定で Skype for Business および Teams アドインの両方が表示されます。</span><span class="sxs-lookup"><span data-stu-id="b0949-156">In Outlook on the web, Outlook Windows, and Outlook Mac, users see both Skype for Business and Teams add-ins when in Islands mode by default.</span></span> <span data-ttu-id="b0949-157">Teams 会議ポリシー設定を構成して、アイランド モードのユーザーが Teams 会議アドインのみを使用するか、Teams 会議アドインと Skype for Business 会議アドインの両方を使用するかを制御できます。</span><span class="sxs-lookup"><span data-stu-id="b0949-157">You can configure a Teams meeting policy setting to control whether users in Islands mode can only use the Teams Meeting add-in or both the Teams Meeting and Skype for Business Meeting add-ins.</span></span>

<span data-ttu-id="b0949-158">初期リリースではいくつかの制限があるため、Outlook モバイルは Skype for Business **または** Teams の会議の作成のみをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="b0949-158">Due to certain limitations in the initial release, Outlook mobile can only support creating Skype for Business **or** Teams meetings.</span></span> <span data-ttu-id="b0949-159">詳細は次の表を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b0949-159">See the following table for details.</span></span>

| <span data-ttu-id="b0949-160">Teams 管理センターの共存モード</span><span class="sxs-lookup"><span data-stu-id="b0949-160">Coexistence mode in the Teams admin center</span></span> | <span data-ttu-id="b0949-161">Outlook モバイルの既定の会議プロバイダー</span><span class="sxs-lookup"><span data-stu-id="b0949-161">Default meetings provider in Outlook mobile</span></span> |
| --------------------------------------|---------------------------------------------|
| <span data-ttu-id="b0949-162">アイランド</span><span class="sxs-lookup"><span data-stu-id="b0949-162">Islands</span></span> | <span data-ttu-id="b0949-163">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="b0949-163">Skype for Business</span></span> |
| <span data-ttu-id="b0949-164">Skype for Business のみ</span><span class="sxs-lookup"><span data-stu-id="b0949-164">Skype for Business only</span></span> | <span data-ttu-id="b0949-165">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="b0949-165">Skype for Business</span></span> |
| <span data-ttu-id="b0949-166">Skype for Business と Teams の共同作業</span><span class="sxs-lookup"><span data-stu-id="b0949-166">Skype for Business with Teams collaboration</span></span> | <span data-ttu-id="b0949-167">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="b0949-167">Skype for Business</span></span> |
| <span data-ttu-id="b0949-168">Skype for Business と Teams の共同作業と会議</span><span class="sxs-lookup"><span data-stu-id="b0949-168">Skype for Business with Teams collaboration and meetings</span></span> | <span data-ttu-id="b0949-169">Teams</span><span class="sxs-lookup"><span data-stu-id="b0949-169">Teams</span></span> |
| <span data-ttu-id="b0949-170">Teams のみ</span><span class="sxs-lookup"><span data-stu-id="b0949-170">Teams only</span></span> | <span data-ttu-id="b0949-171">Teams</span><span class="sxs-lookup"><span data-stu-id="b0949-171">Teams</span></span> |

### <a name="set-whether-users-in-islands-mode-can-only-use-the-teams-meeting-add-in-or-both-the-teams-meeting-and-skype-for-business-meeting-add-ins"></a><span data-ttu-id="b0949-172">アイランド モードのユーザーが Teams 会議アドインのみを使用するか、Teams 会議アドインと Skype for Business 会議アドインの両方を使用するかを設定する</span><span class="sxs-lookup"><span data-stu-id="b0949-172">Set whether users in Islands mode can only use the Teams Meeting add-in or both the Teams Meeting and Skype for Business Meeting add-ins</span></span>

<span data-ttu-id="b0949-173">管理者として、組織の Teams 会議ポリシー設定を構成して、*アイランド モードのユーザー* がどの Outlook 会議アドインを使用するかを制御できます。</span><span class="sxs-lookup"><span data-stu-id="b0949-173">As an admin, you can configure a Teams meeting policy setting to control which Outlook meeting add-in is used for *users who are in Islands mode*.</span></span> <span data-ttu-id="b0949-174">Teams 会議アドインのみを使用するか、Teams 会議アドインと Skype for Business 会議アドインの両方を使用するかを指定して、Outlook で会議をスケジュールできます。</span><span class="sxs-lookup"><span data-stu-id="b0949-174">You can specify whether users can only use the Teams Meeting add-in or both the Teams Meeting and Skype for Business Meeting add-ins to schedule meetings in Outlook.</span></span>

<span data-ttu-id="b0949-175">このポリシーは、アイランドモードで、Teams の会議ポリシーで **AllowOutlookAddIn** パラメーターが **True** に設定されているユーザーにのみ適用できます。</span><span class="sxs-lookup"><span data-stu-id="b0949-175">You can only apply this policy to users who are in Islands mode and have the **AllowOutlookAddIn** parameter set to **True** in their Teams meeting policy.</span></span> <span data-ttu-id="b0949-176">このポリシーの設定方法の詳細については、「[アイランド モードのユーザーの会議プロバイダーを設定する](meeting-policies-in-teams.md#meeting-policy-settings---meeting-provider-for-islands-mode)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b0949-176">For steps on how to set this policy, see [set the meeting provider for users in Islands mode](meeting-policies-in-teams.md#meeting-policy-settings---meeting-provider-for-islands-mode).</span></span>

## <a name="other-considerations"></a><span data-ttu-id="b0949-177">その他の考慮事項</span><span class="sxs-lookup"><span data-stu-id="b0949-177">Other considerations</span></span>

<span data-ttu-id="b0949-178">Teams の会議アドインは継続して機能が開発されていますので、次について認識しておいてください。</span><span class="sxs-lookup"><span data-stu-id="b0949-178">The Teams Meeting add-in is still building functionality, so be aware of the following:</span></span>

- <span data-ttu-id="b0949-179">Teams 会議アドインには、会議をスケジュールするプライマリ ユーザーの Exchange メールボックスが必要です。</span><span class="sxs-lookup"><span data-stu-id="b0949-179">The Teams Meeting add-in requires an Exchange mailbox for the primary user scheduling the meeting.</span></span> <span data-ttu-id="b0949-180">Outlook プロファイルに少なくとも 1 つの Exchange メールボックスが構成されていることを確認し、アドインを使用してTeams の会議をスケジュールします。</span><span class="sxs-lookup"><span data-stu-id="b0949-180">Ensure that you have at least one Exchange mailbox configured in your Outlook profile and use it to schedule Teams meetings with the add-in.</span></span> <span data-ttu-id="b0949-181">Exchange の要件の詳細については、「[Exchange とTeams の連携](https://docs.microsoft.com/microsoftteams/exchange-teams-interact)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b0949-181">For Exchange requirements, see [How Exchange and Teams interact](https://docs.microsoft.com/microsoftteams/exchange-teams-interact).</span></span>
- <span data-ttu-id="b0949-182">このアドインは、特定の参加者でスケジュール設定された会議向けで、チャネル内の会議向けではありません。</span><span class="sxs-lookup"><span data-stu-id="b0949-182">The add-in is for scheduled meetings with specific participants, not for meetings in a channel.</span></span> <span data-ttu-id="b0949-183">チャネル会議は Teams 内でスケジュール設定される必要があります。</span><span class="sxs-lookup"><span data-stu-id="b0949-183">Channel meetings must be scheduled from within Teams.</span></span>
- <span data-ttu-id="b0949-184">認証プロキシがユーザーの PC および Teams サービスのネットワーク パス内にある場合、アドインは機能しません。</span><span class="sxs-lookup"><span data-stu-id="b0949-184">The add-in will not work if an Authentication Proxy is in the network path of the user's PC and Teams Services.</span></span>
- <span data-ttu-id="b0949-185">ユーザーが Outlook 内でライブ イベントをスケジュールすることはできません。</span><span class="sxs-lookup"><span data-stu-id="b0949-185">Users can't schedule live events from within Outlook.</span></span> <span data-ttu-id="b0949-186">Teams に移動し、ライブ イベントをスケジュールします。</span><span class="sxs-lookup"><span data-stu-id="b0949-186">Go to Teams to schedule live events.</span></span> <span data-ttu-id="b0949-187">詳細については、「[Microsoft Teams のライブ イベントについて](teams-live-events/what-are-teams-live-events.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b0949-187">For more information, see [What are Microsoft Teams live events?](teams-live-events/what-are-teams-live-events.md).</span></span>

<span data-ttu-id="b0949-188">[Microsoft Teams での会議と通話](https://support.office.com/article/Meetings-and-calls-d92432d5-dd0f-4d17-8f69-06096b6b48a8)についてご確認ください。</span><span class="sxs-lookup"><span data-stu-id="b0949-188">Learn more about [meetings and calling in Microsoft Teams](https://support.office.com/article/Meetings-and-calls-d92432d5-dd0f-4d17-8f69-06096b6b48a8).</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="b0949-189">トラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="b0949-189">Troubleshooting</span></span>

<span data-ttu-id="b0949-190">次の手順を使用して、Teams 会議アドインの問題のトラブルシューティングを行います。</span><span class="sxs-lookup"><span data-stu-id="b0949-190">Use the following steps to troubleshoot issues with the Teams Meeting add-in.</span></span>

### <a name="teams-meeting-add-in-in-outlook-for-windows-does-not-show"></a><span data-ttu-id="b0949-191">Outlook for Windows の Teams 会議アドインが表示されない</span><span class="sxs-lookup"><span data-stu-id="b0949-191">Teams Meeting add-in in Outlook for Windows does not show</span></span>

<span data-ttu-id="b0949-192">Outlook 用の Teams 会議アドインをインストールできない場合、次のトラブルシューティングの手順をお試しください。</span><span class="sxs-lookup"><span data-stu-id="b0949-192">If you cannot get the Teams Meeting add-in for Outlook to install, try these troubleshooting steps.</span></span>

<span data-ttu-id="b0949-193">[Microsoft Support and Recovery Assistant (Microsoft サポート/回復アシスタント)](https://aka.ms/SaRA-TeamsAddInScenario) をダウンロードして、「[Microsoft サポート/回復アシスタントについて](https://aka.ms/SaRA_Home)」の手順に従って自動修正を実行します。</span><span class="sxs-lookup"><span data-stu-id="b0949-193">[Download](https://aka.ms/SaRA-TeamsAddInScenario) and run the [Microsoft Support Recovery Assistant](https://aka.ms/SaRA_Home) to perform automated troubleshooting steps and fixes.</span></span>

<span data-ttu-id="b0949-194">または、次の手順を手動で実行します。</span><span class="sxs-lookup"><span data-stu-id="b0949-194">Alternatively, perform the following steps manually:</span></span>

- <span data-ttu-id="b0949-195">Windows 7 ユーザーは、Teams 会議アドインを機能させるために、[Windows ユニバーサル C ランタイム更新プログラム](https://support.microsoft.com/help/2999226/update-for-universal-c-runtime-in-windows)をインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="b0949-195">Windows 7 users must install the [Update for Universal C Runtime in Windows](https://support.microsoft.com/help/2999226/update-for-universal-c-runtime-in-windows) for the Teams Meeting add-in to work.</span></span>
- <span data-ttu-id="b0949-196">ユーザーが Teams で会議をスケジュールできる Teams アップグレード ポリシーを持っていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="b0949-196">Check that the user has a Teams Upgrade policy which enables scheduling meetings in Teams.</span></span> <span data-ttu-id="b0949-197">詳細については、「[Skype for Business から Teams へのアップグレード](https://docs.microsoft.com/microsoftteams/upgrade-to-teams-on-prem-overview#meetings)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b0949-197">See [Upgrade from Skype for Business to Teams](https://docs.microsoft.com/microsoftteams/upgrade-to-teams-on-prem-overview#meetings) for more details.</span></span>
- <span data-ttu-id="b0949-198">Outlook アドインを許可する Teams 会議ポリシーが設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="b0949-198">Check that the user has a Teams Meeting policy that permits the Outlook Add-in.</span></span> <span data-ttu-id="b0949-199">詳細については、「[Teams での会議ポリシーを管理する](https://docs.microsoft.com/microsoftteams/meeting-policies-in-teams#allow-the-outlook-add-in)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b0949-199">See [Manage meeting policies in Teams](https://docs.microsoft.com/microsoftteams/meeting-policies-in-teams#allow-the-outlook-add-in) for more details.</span></span>
- <span data-ttu-id="b0949-200">ユーザーが Teams デスクトップ クライアントをインストールしていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="b0949-200">Ensure the user has the Teams desktop client installed.</span></span> <span data-ttu-id="b0949-201">Teams の Web クライアントのみを使用している場合には、会議アドインはインストールされません。</span><span class="sxs-lookup"><span data-stu-id="b0949-201">The meeting add-in will not be installed when only using the Teams web client.</span></span>
- <span data-ttu-id="b0949-202">ユーザーが Outlook 2013 以降をインストールしていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="b0949-202">Ensure the user has Outlook 2013 or later installed.</span></span>
- <span data-ttu-id="b0949-203">ユーザーが regsvr32.exe の実行権限を持っていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="b0949-203">Make sure the user has permission to execute regsvr32.exe.</span></span>
- <span data-ttu-id="b0949-204">Outlook デスクトップ クライアントのすべての利用可能な更新プログラムが適用されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="b0949-204">Ensure that all available updates for Outlook desktop client have been applied.</span></span>
- <span data-ttu-id="b0949-205">次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="b0949-205">Follow these steps:</span></span>
  - <span data-ttu-id="b0949-206">Teamsのデスクトップ クライアントを再起動します。</span><span class="sxs-lookup"><span data-stu-id="b0949-206">Restart the Teams desktop client.</span></span>
  - <span data-ttu-id="b0949-207">[Teamsのデスクトップ クライアント]からサインアウトして、もう一度サインインします。</span><span class="sxs-lookup"><span data-stu-id="b0949-207">Sign out and then sign back in to the Teams desktop client.</span></span>
  - <span data-ttu-id="b0949-208">Outlook デスクトップ クライアントを再起動します。</span><span class="sxs-lookup"><span data-stu-id="b0949-208">Restart the Outlook desktop client.</span></span> <span data-ttu-id="b0949-209">(管理者モードで Outlook が実行されていないことをご確認ください。)</span><span class="sxs-lookup"><span data-stu-id="b0949-209">(Make sure Outlook isn't running in admin mode.)</span></span>

<span data-ttu-id="b0949-210">それでもアドインが表示されない場合、Outlook でアドインが無効になっていないかをご確認ください。</span><span class="sxs-lookup"><span data-stu-id="b0949-210">If you still don't see the add-in, make sure that it isn't disabled in Outlook.</span></span>

- <span data-ttu-id="b0949-211">Outlook で、[**ファイル**]、[**オプション**] の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="b0949-211">In Outlook, choose **File** and then **Options**.</span></span>
- <span data-ttu-id="b0949-212">[**Outlook のオプション**] ダイアログ ボックスの [**アドイン**] タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="b0949-212">Select the **Add-ins** tab of **Outlook Options** dialog box.</span></span>
- <span data-ttu-id="b0949-213">[**Microsoft Office 用の Microsoft Teams 会議アドイン**] が [**有効なアプリケーション アドイン**] の一覧に表示されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="b0949-213">Confirm that **Microsoft Teams Meeting Add-in for Microsoft Office** is listed in the **Active Application Add-ins** list</span></span>
- <span data-ttu-id="b0949-214">Teams 会議アドインが [**無効なアプリケーション アドイン**] の一覧に表示されている場合は、[**管理**] の [**COM アドイン**] を選択し、[**移動**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="b0949-214">If the Teams Meeting Add-in is listed in the **Disabled Application Add-ins** list, select **COM Add-ins** in **Manage** and then select **Go…**</span></span>
- <span data-ttu-id="b0949-215">[**Microsoft Office 用の Microsoft Teams 会議アドイン**] の横にあるチェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="b0949-215">Set the checkbox next to **Microsoft Teams Meeting Add-in for Microsoft Office**.</span></span>
- <span data-ttu-id="b0949-216">すべてのダイアログボックスで [**OK**] をクリックして、Outlook を再起動します。</span><span class="sxs-lookup"><span data-stu-id="b0949-216">Choose **OK** on all dialog boxes and restart Outlook.</span></span>

<span data-ttu-id="b0949-217">アドインを管理する方法に関する全般的なガイドラインについては、「[Office プログラムでアドインを表示、管理、インストールする](https://support.office.com/article/View-manage-and-install-add-ins-in-Office-programs-16278816-1948-4028-91E5-76DCA5380F8D)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="b0949-217">For general guidance about how to manage add-ins, see [View, manage, and install add-ins in Office programs](https://support.office.com/article/View-manage-and-install-add-ins-in-Office-programs-16278816-1948-4028-91E5-76DCA5380F8D).</span></span>

<span data-ttu-id="b0949-218">それでもアドインが表示されない場合には、次の手順でレジストリ設定を確認します。</span><span class="sxs-lookup"><span data-stu-id="b0949-218">If the add-in still does not show, use the following steps to verify the registry settings.</span></span>

> [!NOTE]
> <span data-ttu-id="b0949-219">レジストリを正しく編集しないと、システムが正常に動作しなくなる場合があります。</span><span class="sxs-lookup"><span data-stu-id="b0949-219">Incorrectly editing the registry may severely damage your system.</span></span> <span data-ttu-id="b0949-220">レジストリを変更する前に、コンピューター上の重要なデータをバックアップする必要があります。</span><span class="sxs-lookup"><span data-stu-id="b0949-220">Before making changes to the registry, you should back up any valued data on the computer.</span></span>
- <span data-ttu-id="b0949-221">RegEdit.exe を起動します。</span><span class="sxs-lookup"><span data-stu-id="b0949-221">Launch RegEdit.exe</span></span>
- <span data-ttu-id="b0949-222">HKEY_CURRENT_USER\Software\Microsoft\Office\Outlook\Addins に移動します。</span><span class="sxs-lookup"><span data-stu-id="b0949-222">Navigate to HKEY_CURRENT_USER\Software\Microsoft\Office\Outlook\Addins</span></span>
- <span data-ttu-id="b0949-223">TeamsAddin.FastConnect が存在することを確認します。</span><span class="sxs-lookup"><span data-stu-id="b0949-223">Verify TeamsAddin.FastConnect exists.</span></span>
- <span data-ttu-id="b0949-224">TeamsAddin.FastConnect 内に LoadBehavior が存在し、3 に設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="b0949-224">Within TeamsAddin.FastConnect, verify LoadBehavior exists and is set to 3.</span></span>
  - <span data-ttu-id="b0949-225">LoadBehavior の値が 3 以外の場合には、3 に変更して Outlook を再起動します。</span><span class="sxs-lookup"><span data-stu-id="b0949-225">If LoadBehavior has a value other than 3, change it to 3 and restart Outlook.</span></span>

### <a name="delegate-scheduling-does-not-work"></a><span data-ttu-id="b0949-226">代理人によるスケジュール設定が機能しない</span><span class="sxs-lookup"><span data-stu-id="b0949-226">Delegate scheduling does not work</span></span>

<span data-ttu-id="b0949-227">管理者が、[Exchange Web Server (EWS) へのアクセスを制御する](https://docs.microsoft.com/exchange/client-developer/exchange-web-services/how-to-control-access-to-ews-in-exchange)ように Microsoft Exchange を構成している場合、代理人は上司の代わりに Teams 会議をスケジュールできません。</span><span class="sxs-lookup"><span data-stu-id="b0949-227">If your administrator has configured Microsoft Exchange to [control access to Exchange Web Server (EWS)](https://docs.microsoft.com/exchange/client-developer/exchange-web-services/how-to-control-access-to-ews-in-exchange), a delegate won't be able to schedule a Teams meeting on behalf of the boss.</span></span> <span data-ttu-id="b0949-228">この構成のソリューションは開発中で、今後リリースされる予定です。</span><span class="sxs-lookup"><span data-stu-id="b0949-228">The solution for this configuration is under development and will be released in the future.</span></span> <span data-ttu-id="b0949-229">回避策として、管理者は次の文字列を EWS の許可リストに追加することができます: "*SchedulingService*"。</span><span class="sxs-lookup"><span data-stu-id="b0949-229">As a workaround, your administrator can add the following string to the EWS Allow List: "*SchedulingService*".</span></span> 


## <a name="related-topics"></a><span data-ttu-id="b0949-230">関連項目</span><span class="sxs-lookup"><span data-stu-id="b0949-230">Related topics</span></span>

- [<span data-ttu-id="b0949-231">Teams のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="b0949-231">Teams Troubleshooting</span></span>](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams)

- [<span data-ttu-id="b0949-232">Outlook から Teams の会議のスケジュールを設定する</span><span class="sxs-lookup"><span data-stu-id="b0949-232">Schedule a Teams meeting from Outlook</span></span>](https://support.microsoft.com/office/schedule-a-teams-meeting-from-outlook-883cc15c-580f-441a-92ea-0992c00a9b0f)
