---
title: SharePoint Online サイトまたはページから Terms の「イントラネット ポータル アプリ」を作成する
author: LanaChin
ms.author: heidip
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_RemoteWorkers
- remotework
ms.reviewer: vinbel
search.appverid: MET150
description: 既存の SharePoint Online サイトまたはページを取得し、組織のイントラネット ポータルとして使用できるスタンドアロンの静的タブを作成します。
localization_priority: Priority
ms.openlocfilehash: 4777b744d76415f45718cb274f402556e1e28240
ms.sourcegitcommit: b381d8f0b9fc45133d52175fa85901b66e744abd
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2020
ms.locfileid: "44326584"
---
# <a name="create-a-teams-intranet-portal-app-from-a-sharepoint-online-site-or-page"></a><span data-ttu-id="bfe2c-103">SharePoint Online サイトまたはページから Terms の「イントラネット ポータル アプリ」を作成する</span><span class="sxs-lookup"><span data-stu-id="bfe2c-103">Create a Teams 'Intranet Portal app' from a SharePoint Online site or page</span></span>

<span data-ttu-id="bfe2c-104">この記事の手順を使用して、組織のイントラネット サイトにリンクされたスタンドアロンの静的アプリを Teams 内に作成します。</span><span class="sxs-lookup"><span data-stu-id="bfe2c-104">Use the steps in this article to create a standalone and static app inside of Teams that links to the intranet site for your org.</span></span>

<span data-ttu-id="bfe2c-105">SharePoint イントラネット サイトの *Teams 個人用アプリ*が作成され、Teams 内にタブとして表示されます。</span><span class="sxs-lookup"><span data-stu-id="bfe2c-105">A *Teams Personal App* of your SharePoint intranet site is created, and will appear as a tab inside of Teams.</span></span> <span data-ttu-id="bfe2c-106">このタブには、すべての Teams ユーザーにとって重要な情報を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="bfe2c-106">This tab can contain information important to all your Teams users.</span></span> <span data-ttu-id="bfe2c-107">これは、Teams ユーザーが、タブをクリックするだけで更新情報にアクセスできるようにするための、すばやく簡単な方法です。</span><span class="sxs-lookup"><span data-stu-id="bfe2c-107">It is a quick and convenient way for Teams users to access updates just a tab click away.</span></span>

<span data-ttu-id="bfe2c-108">示されているプロセスが機能するには、*最新の* SharePoint サイトまたはページを**使用する必要がある**ことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="bfe2c-108">Be aware that the process shown **must use** a *modern* SharePoint site or page to work.</span></span> <span data-ttu-id="bfe2c-109">このプロセスは、*クラシック* サイトやページでは使用できません。</span><span class="sxs-lookup"><span data-stu-id="bfe2c-109">This process is not available for *classical* sites or pages.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="bfe2c-110">テナントで Teams アプリのサイドローディングが有効になっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="bfe2c-110">Make certain that side-loading of Teams apps is enabled for your tenant.</span></span> <span data-ttu-id="bfe2c-111">Teams 管理ポータルの移行プロセスの段階によっては、ポータルの以前のバージョン内の [Teams] > [管理者] の下、または [管理者] > [設定] > [サービスとアドイン] > [Microsoft Teams] > [アプリ] > [外部アプリ] の下のいずれかで Teams アプリのサイドローディングを有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="bfe2c-111">Depending on where you are in the migration process of the Teams Admin portal, you might need to enable it either under Teams > Admin, or under Admin > Settings > Services and Add-ins > Microsoft Teams > Apps > External Apps, in the previous version of the portal!</span></span>

## <a name="use-app-studio-to-create-your-standalone-sharepoint-online-app"></a><span data-ttu-id="bfe2c-112">App Studio を使用して、スタンドアロンの SharePoint Online アプリを作成する</span><span class="sxs-lookup"><span data-stu-id="bfe2c-112">Use App Studio to create your standalone SharePoint Online app</span></span>

<span data-ttu-id="bfe2c-113">開始する前に、</span><span class="sxs-lookup"><span data-stu-id="bfe2c-113">Before you begin:</span></span>

1. <span data-ttu-id="bfe2c-114">SharePoint Online の最新のコミュニケーションや Teams サイトの URL、またはページを知っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="bfe2c-114">You'll need to know the URL of a SharePoint Online modern Communication or Team site, or page.</span></span>
    - <span data-ttu-id="bfe2c-115">これらのサイトのパスには、常に */teams/* または */sites/* があります。</span><span class="sxs-lookup"><span data-stu-id="bfe2c-115">These sites will always have either */teams/* or */sites/* in their paths.</span></span>

2. <span data-ttu-id="bfe2c-116">自分のテナントのサブドメインを知っておく必要があります。これはプレースホルダーの **{{subdomain}}** で使用します。</span><span class="sxs-lookup"><span data-stu-id="bfe2c-116">You'll need to know your tenant's subdomain, which will be used in the placeholder **{{subdomain}}**.</span></span>

3. <span data-ttu-id="bfe2c-117">この記事では、選択したサイトまたはページの *URL* のプレースホルダーとして **{{siteUrl}}** を使用します。</span><span class="sxs-lookup"><span data-stu-id="bfe2c-117">This article will use **{{siteUrl}}** as a placeholder for the *URL* of the site or page you chose.</span></span>
    - <span data-ttu-id="bfe2c-118">*URL* の例:   https://contoso.sharepoint.com/teams/Contoso   \* または \* https://contoso.sharepoint.com/sites/Contoso</span><span class="sxs-lookup"><span data-stu-id="bfe2c-118">Example *URLs*:   https://contoso.sharepoint.com/teams/Contoso   *or* https://contoso.sharepoint.com/sites/Contoso</span></span>
4. <span data-ttu-id="bfe2c-119">また、URL の*パス*を示すために **{{sitePath}}** を使用します (例: /teams/Contoso)。</span><span class="sxs-lookup"><span data-stu-id="bfe2c-119">Also, **{{sitePath}}** will be used to denote the *path* of the URL (ex: /teams/Contoso).</span></span>
    - <span data-ttu-id="bfe2c-120">*パス*の例:   /teams/Contoso   \* または \* /sites/Contoso</span><span class="sxs-lookup"><span data-stu-id="bfe2c-120">Example *paths*:   /teams/Contoso   *or* /sites/Contoso</span></span>

<span data-ttu-id="bfe2c-121">次の手順に従って開始します。</span><span class="sxs-lookup"><span data-stu-id="bfe2c-121">Begin by following the steps below:</span></span>

1. <span data-ttu-id="bfe2c-122">Teams ストアに移動します。</span><span class="sxs-lookup"><span data-stu-id="bfe2c-122">Go to the Teams Store.</span></span>

2. <span data-ttu-id="bfe2c-123">App Studio をインストールするか、開きます。</span><span class="sxs-lookup"><span data-stu-id="bfe2c-123">Install or open App Studio.</span></span>

3. <span data-ttu-id="bfe2c-124">アプリのオプションの横にある **[開く]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bfe2c-124">Click **Open**, next to the App option.</span></span>

4. <span data-ttu-id="bfe2c-125">App Studio を開いた状態で、**[マニフェスト エディター]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bfe2c-125">With App Studio open, click on **Manifest Editor**.</span></span>

5. <span data-ttu-id="bfe2c-126">**新しいアプリを作成**します。</span><span class="sxs-lookup"><span data-stu-id="bfe2c-126">**Create a new app**.</span></span>

6. <span data-ttu-id="bfe2c-127">すべての**アプリの詳細**を入力します。</span><span class="sxs-lookup"><span data-stu-id="bfe2c-127">Fill in all **App Details**.</span></span>

7. <span data-ttu-id="bfe2c-128">[機能] の下の**タブ**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bfe2c-128">Click on **Tabs** under Capabilities.</span></span>

8. <span data-ttu-id="bfe2c-129">[個人用] タブの **[追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bfe2c-129">Click **Add** under Personal Tab.</span></span>

9. <span data-ttu-id="bfe2c-130">**名前**を入力し、**新しい一意のエンティティ ID** を選択します。</span><span class="sxs-lookup"><span data-stu-id="bfe2c-130">Fill in the **Name** and choose **a new unique Entity ID**.</span></span>

10. <span data-ttu-id="bfe2c-131">**contentURL と Web サイトの URL** を入力します。</span><span class="sxs-lookup"><span data-stu-id="bfe2c-131">Fill in the **contentURL and Website URL**.</span></span>

- <span data-ttu-id="bfe2c-132">**contentUrl**: {{siteUrl}}/_layouts/15/teamslogon.aspx?SPFX=true&dest={{sitePath}}</span><span class="sxs-lookup"><span data-stu-id="bfe2c-132">**contentUrl**: {{siteUrl}}/_layouts/15/teamslogon.aspx?SPFX=true&dest={{sitePath}}</span></span>  
- <span data-ttu-id="bfe2c-133">**websiteUrl**: {{siteUrl}}</span><span class="sxs-lookup"><span data-stu-id="bfe2c-133">**websiteUrl**: {{siteUrl}}</span></span>

    <span data-ttu-id="bfe2c-134">**contentURL** の例: https://contoso.sharepoint.com/sites/ContosoHub/_layouts/15/teamslogon.aspx?SPFX=true&dest=/sites/ContosoHub</span><span class="sxs-lookup"><span data-stu-id="bfe2c-134">Example **contentURL**: https://contoso.sharepoint.com/sites/ContosoHub/_layouts/15/teamslogon.aspx?SPFX=true&dest=/sites/ContosoHub</span></span>

11. <span data-ttu-id="bfe2c-135">**[ドメインとアクセス許可]** に移動します。</span><span class="sxs-lookup"><span data-stu-id="bfe2c-135">Navigate to **Domains and Permissions**.</span></span> <span data-ttu-id="bfe2c-136">有効なドメイン セクションに SharePoint Online のドメイン名が含まれていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="bfe2c-136">Make sure the valid domains section contains your SharePoint online domain name.</span></span>

    <span data-ttu-id="bfe2c-137">例: contoso.sharepoint.com</span><span class="sxs-lookup"><span data-stu-id="bfe2c-137">Example: contoso.sharepoint.com</span></span>

12. <span data-ttu-id="bfe2c-138">次の Web アプリの**シングル サインオン**のプロパティを追加します。</span><span class="sxs-lookup"><span data-stu-id="bfe2c-138">Add the following web app **single sign-on** properties:</span></span>

     <span data-ttu-id="bfe2c-139">例:  **AAD アプリケーション ID**: 00000003-0000-0ff1-ce00-000000000000  **リソースの URL**: {{subdomain}}.sharepoint.com</span><span class="sxs-lookup"><span data-stu-id="bfe2c-139">Example:  **AAD application ID**: 00000003-0000-0ff1-ce00-000000000000  **Resource Url**: {{subdomain}}.sharepoint.com</span></span>

    ![ID と URL を使用した Web アプリのシングル サインオン。](media/personal-app.png)

13. <span data-ttu-id="bfe2c-141">これらのプロパティを**保存**して、**[テストと配布]** に移動します。</span><span class="sxs-lookup"><span data-stu-id="bfe2c-141">**Save** these properties and then navigate to **Test and distribute**.</span></span>

14. <span data-ttu-id="bfe2c-142">アプリをインストールして、アプリケーションを個人でテストします。</span><span class="sxs-lookup"><span data-stu-id="bfe2c-142">Install the app to test the application personally.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="bfe2c-143">Teams App Studio を使用していない場合は、作成した manifest.JSON ファイルを .zip にする必要があります。Teams 内の [App Store] に移動し、**[カスタム アプリのアップロード]** リンク (App Store の右下部分) をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bfe2c-143">If you aren't using Teams App Studio, you will have to .zip the manifest.JSON file you just created, navigate to the App Store in Teams, and click  **upload custom app** link (at the bottom right of the App Store).</span></span> <span data-ttu-id="bfe2c-144">これにより、アプリが利用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="bfe2c-144">This will make the app available to you.</span></span>

15. <span data-ttu-id="bfe2c-145">これで、アプリを静的タブとして使用できるようになり、Teams で読み込みと表示を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="bfe2c-145">Now the app is available as a static tab for you to load and view in Teams.</span></span>

## <a name="test-and-view-your-new-static-tab"></a><span data-ttu-id="bfe2c-146">新しい静的タブをテストして表示する</span><span class="sxs-lookup"><span data-stu-id="bfe2c-146">Test and view your new static tab</span></span>

<span data-ttu-id="bfe2c-147">Teams デスクトップで新しいタブを表示するには、アプリ バーの左側にある省略記号 (**…**) に移動します。</span><span class="sxs-lookup"><span data-stu-id="bfe2c-147">To view the new tab on the Teams desktop, navigate to the ellipses (**…**) in the left-hand side of your app bar.</span></span> <span data-ttu-id="bfe2c-148">新しいアプリを見つけて読み込んで、スタンドアロン アプリケーションを Teams でテストします。</span><span class="sxs-lookup"><span data-stu-id="bfe2c-148">Find your new app, load it, and test your standalone application in Teams.</span></span>

<span data-ttu-id="bfe2c-149">新しいアプリを左側のメニューのより高い位置で使用できるようにするには、そのためにアプリのポリシー設定を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bfe2c-149">If you want to make the new app available in the left menu at a higher position, you must use an app policy setting for this.</span></span> <span data-ttu-id="bfe2c-150">この設定は、[Teams 管理セクション] > [アプリ ポリシー] > [固定されたアプリケーションの追加] の下にあります。</span><span class="sxs-lookup"><span data-stu-id="bfe2c-150">This setting can be found under the Team admin section > app policy > add a pinned application.</span></span> <span data-ttu-id="bfe2c-151">テストのためにユーザーにポリシーを割り当てると、その変更は数時間後に表示されます。</span><span class="sxs-lookup"><span data-stu-id="bfe2c-151">When you assign the policy to a user for testing, the change will appear a few hours later.</span></span> <span data-ttu-id="bfe2c-152">この点を念頭に置いて、遅延を回避するために、アプリを表示する位置をできるだけ早く決定してください。</span><span class="sxs-lookup"><span data-stu-id="bfe2c-152">With this in mind, please decide where the app should appear at your earliest convenience to help avoid delays.</span></span>

<span data-ttu-id="bfe2c-153">モバイル デバイスで新しいアプリを表示してテストするには、画面の下部にあるタブ バーの上のシェブロン (**^**) をタップして、アプリ ドロワーを開きます。</span><span class="sxs-lookup"><span data-stu-id="bfe2c-153">To view and test the new app on a mobile device, open the app drawer by tapping on the chevron (**^**) above the tab bar near the bottom of your screen.</span></span> <span data-ttu-id="bfe2c-154">アプリを見つけて、モバイル デバイスでそのアプリに移動します。</span><span class="sxs-lookup"><span data-stu-id="bfe2c-154">Find your app and navigate to it on your mobile device.</span></span>

> [!CAUTION]
> <span data-ttu-id="bfe2c-155">現在、モバイル サポートは開発者プレビューに含まれています。</span><span class="sxs-lookup"><span data-stu-id="bfe2c-155">Mobile support is currently in Developer Preview.</span></span> <span data-ttu-id="bfe2c-156">開発者プレビューを有効にするには、[設定] > [バージョン情報] に移動して、開発者プレビュー モードを有効にします。</span><span class="sxs-lookup"><span data-stu-id="bfe2c-156">To enable Developer Preview, navigate to Settings > About and then enable Developer Preview mode.</span></span>

## <a name="a-sample-manifestjson-file"></a><span data-ttu-id="bfe2c-157">Manifest.JSON ファイルのサンプル</span><span class="sxs-lookup"><span data-stu-id="bfe2c-157">A Sample Manifest.JSON file</span></span>

<span data-ttu-id="bfe2c-158">生成される JSON ファイルは、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="bfe2c-158">The JSO        file you generate will look something like the one below.</span></span>

```JSON'
{

    "$schema": "https://developer.microsoft.com/en-us/json-schemas/teams/v1.5/MicrosoftTeams.schema.json",

    "manifestVersion": "1.5",

    "version": "1.0.0",

    "id": "33ebded3-931c-4333-b0c5-b51dd8738873",

    "packageName": "com.contoso.teams.devapp",

    "developer": {

        "name": "Contoso", ''

        "websiteUrl": "https://www.contoso.com",

        "privacyUrl": "https://www.contoso.com/privacy",

        "termsOfUseUrl": "https://www.contoso.com/terms"

    },

    "icons": {

        "color": "color.png",

        "outline": "outline.png"

    },

    "name": {

        "short": "Contoso Intranet", '

        "full": "Intranet Portal for Contoso"

    },

    "des    ription": {

        "short": "Intranet portal for Contoso",

        "full": "This app is to demonstrate the capabilities of hosting a SharePoint communication and team site as a standalone app in Teams"

    },

    "accentColor": "#FFFFFF",

    "staticTabs": [

        {

                     "       nti        Id":       "com    unicat    onSi    eTab",

            "name": "Contoso Net",

            "contentUrl": "https://contoso.sharepoint.com/sites/ContosoNet/_layouts/15/teamslogon.aspx?SPFX=true&dest=/sites/ContosoNet/",

            "websiteUrl": "https://contoso.sharepoint.com/sites/ContosoNet",

            "scopes": [

                "personal"

            ]

        },

        {

            "entityId": "teamSiteTab",

            "name": "Team Contoso",

            "contentUrl": "https://contoso.sharepoint.com/teams/TeamContoso/_layouts/15/teamslogon.aspx?SPFX=true&dest=/teams/TeamContoso/",

            "websiteUrl": "https://contoso.sharepoint.com/teams/TeamContoso",

            "scopes": [

                "personal"

            ]

        }

    ],

    "permissions": [

        "identity",

        "messageTeamMembers"

    ],

    "validDomains": [

        "contoso.sharepoint.com"

    ],

    "webApplicationInfo": {

        "id": "00000003-0000-0ff1-ce00-000000000000",

        "resource": "https://contoso.sharepoint.com"

    }

}
```
