---
title: SharePoint Online のサイトまたはページから Teams のイントラネットポータルアプリを作成する
author: LanaChin
ms.author: heidip
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
ms.reviewer: vinbel
search.appverid: MET150
description: 既存の SharePoint Online のサイトまたはページに移動して、組織のイントラネットポータルとして使用できるスタンドアロンの静的タブを作成します。
localization_priority: Normal
ms.openlocfilehash: 0215a2e1f79627f55bc14c00a099b25d2859b6f9
ms.sourcegitcommit: f0f2fa999c1ca4a1118377c7938a247f79217609
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/02/2020
ms.locfileid: "43106634"
---
# <a name="create-a-teams-intranet-portal-app-from-a-sharepoint-online-site-or-page"></a><span data-ttu-id="1209a-103">SharePoint Online のサイトまたはページから Teams のイントラネットポータルアプリを作成する</span><span class="sxs-lookup"><span data-stu-id="1209a-103">Create a Teams 'Intranet Portal app' from a SharePoint Online site or page</span></span>

<span data-ttu-id="1209a-104">この記事の手順を使用して、組織のイントラネットサイトにリンクされたスタンドアロンの静的アプリを Teams 内に作成します。</span><span class="sxs-lookup"><span data-stu-id="1209a-104">Use the steps in this article to create a standalone and static app inside of Teams that links to the intranet site for your org.</span></span>

<span data-ttu-id="1209a-105">SharePoint イントラネットサイトの*Teams Personal アプリ*が作成され、teams 内にタブとして表示されます。</span><span class="sxs-lookup"><span data-stu-id="1209a-105">A *Teams Personal App* of your SharePoint intranet site is created, and will appear as a tab inside of Teams.</span></span> <span data-ttu-id="1209a-106">このタブには、すべてのチームユーザーにとって重要な情報を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="1209a-106">This tab can contain information important to all your Teams users.</span></span> <span data-ttu-id="1209a-107">これは、チームユーザーがタブをクリックするだけで更新情報にアクセスできるようにするための、すばやく簡単な方法です。</span><span class="sxs-lookup"><span data-stu-id="1209a-107">It is a quick and convenient way for Teams users to access updates just a tab click away.</span></span>

<span data-ttu-id="1209a-108">表示されるプロセスでは、*最新*の SharePoint サイトまたはページを**使用する必要が**あることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="1209a-108">Be aware that the process shown **must use** a *modern* SharePoint site or page to work.</span></span> <span data-ttu-id="1209a-109">このプロセスは、*クラシック*サイトやページでは使用できません。</span><span class="sxs-lookup"><span data-stu-id="1209a-109">This process is not available for *classical* sites or pages.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1209a-110">テナントで Teams アプリのサイドローディングが有効になっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="1209a-110">Make certain that side-loading of Teams apps is enabled for your tenant.</span></span> <span data-ttu-id="1209a-111">Teams 管理ポータルの移行プロセスのどこにいるかによって、[Teams > 管理者] の下で有効にする必要がある場合があります。または、以前のバージョンのポータルで、[管理者 > > 設定] の下にある [Microsoft Teams > アプリ > 外部アプリ > ます。</span><span class="sxs-lookup"><span data-stu-id="1209a-111">Depending on where you are in the migration process of the Teams Admin portal, you might need to enable it either under Teams > Admin, or under Admin > Settings > Services and Add-ins > Microsoft Teams > Apps > External Apps, in the previous version of the portal!</span></span> 

## <a name="use-app-studio-to-create-your-standalone-sharepoint-online-app"></a><span data-ttu-id="1209a-112">アプリ Studio を使用して、スタンドアロンの SharePoint Online アプリを作成する</span><span class="sxs-lookup"><span data-stu-id="1209a-112">Use App Studio to create your standalone SharePoint Online app</span></span>
<span data-ttu-id="1209a-113">「」を開始する前に、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="1209a-113">''' Before you begin:</span></span>
1. <span data-ttu-id="1209a-114">SharePoint Online の最新通信またはチームサイトの URL、またはページを知っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="1209a-114">You'll need to know the URL of a SharePoint Online modern Communication or Team site, or page.</span></span>
    - <span data-ttu-id="1209a-115">これらのサイトのパスには、常に/ *teams/* または */sites/* があります。</span><span class="sxs-lookup"><span data-stu-id="1209a-115">These sites will always have either */teams/* or */sites/* in their paths.</span></span>

2. <span data-ttu-id="1209a-116">自分のテナントのサブドメインが、 **{{サブドメイン}}** で使用されていることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1209a-116">You'll need to know your tenant's subdomain, which will be used in the placeholder **{{subdomain}}**.</span></span>

3. <span data-ttu-id="1209a-117">この記事では、選択したサイトまたはページの*URL*として **{{siteUrl}}** プレースホルダーを使用します。</span><span class="sxs-lookup"><span data-stu-id="1209a-117">This article will use **{{siteUrl}}** placeholder for your the *URL* of the site or page you chose.</span></span>
    - <span data-ttu-id="1209a-118">*Url*の例https://contoso.sharepoint.com/teams/Contoso:*または*   https://contoso.sharepoint.com/sites/Contoso</span><span class="sxs-lookup"><span data-stu-id="1209a-118">Example *URLs*:   https://contoso.sharepoint.com/teams/Contoso   *or* https://contoso.sharepoint.com/sites/Contoso</span></span> 
4. <span data-ttu-id="1209a-119">また、 **{{Sitepath}}** は URL の*パス*を示すために使用されます (例:/teams s/Contoso)。</span><span class="sxs-lookup"><span data-stu-id="1209a-119">Also, **{{sitePath}}** will be used to denote the *path* of the URL (ex: /teams/Contoso).</span></span>
    - <span data-ttu-id="1209a-120">*パス*の例:/teams/xml*または*/sites/Contoso</span><span class="sxs-lookup"><span data-stu-id="1209a-120">Example *paths*:   /teams/Contoso   *or* /sites/Contoso</span></span> 

<span data-ttu-id="1209a-121">次の手順に従って開始します。</span><span class="sxs-lookup"><span data-stu-id="1209a-121">Begin by following the steps below:</span></span>

1. <span data-ttu-id="1209a-122">Teams ストアに移動します。</span><span class="sxs-lookup"><span data-stu-id="1209a-122">Go to the Teams Store.</span></span>

2. <span data-ttu-id="1209a-123">App Studio をインストールするか、開きます。</span><span class="sxs-lookup"><span data-stu-id="1209a-123">Install or open App Studio.</span></span>

3. <span data-ttu-id="1209a-124">[アプリ] オプションの横にある [**開く**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1209a-124">Click **Open**, next to the App option.</span></span>

4. <span data-ttu-id="1209a-125">App Studio を開いた状態で、[**マニフェストエディター**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1209a-125">With App Studio open, click on **Manifest Editor**.</span></span>

5. <span data-ttu-id="1209a-126">**新しいアプリを作成**します。</span><span class="sxs-lookup"><span data-stu-id="1209a-126">**Create a new app**.</span></span>

6. <span data-ttu-id="1209a-127">すべての**アプリの詳細**を入力します。</span><span class="sxs-lookup"><span data-stu-id="1209a-127">Fill in all **App Details**.</span></span>

7. <span data-ttu-id="1209a-128">[機能] の下の**タブ**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1209a-128">Click on **Tabs** under Capabilities.</span></span>

8. <span data-ttu-id="1209a-129">[個人用] タブの [**追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1209a-129">Click **Add** under Personal Tab.</span></span>

9. <span data-ttu-id="1209a-130">**名前**を入力し、**新しい一意のエンティティ ID を**選択します。</span><span class="sxs-lookup"><span data-stu-id="1209a-130">Fill in the **Name** and choose **a new unique Entity ID**.</span></span>

10. <span data-ttu-id="1209a-131">**Contenturl と Web サイトの url**を入力します。</span><span class="sxs-lookup"><span data-stu-id="1209a-131">Fill in the **contentURL and Website URL**.</span></span> 

- <span data-ttu-id="1209a-132">**Contenturl**: {{siteUrl}}/_layouts/15/teamslogon.aspxSPFX = true&dest = {{sitePath}}</span><span class="sxs-lookup"><span data-stu-id="1209a-132">**contentUrl**: {{siteUrl}}/_layouts/15/teamslogon.aspx?SPFX=true&dest={{sitePath}}</span></span>  
- <span data-ttu-id="1209a-133">**web'iteUrl**: {{siteUrl}} ' ' **Contenturl**の例:https://contoso.sharepoint.com/sites/ContosoHub/_layouts/15/teamslogon.aspx?SPFX=true&dest=/sites/ContosoHub</span><span class="sxs-lookup"><span data-stu-id="1209a-133">**web'iteUrl**: {{siteUrl}} ''   Example **contentURL**: https://contoso.sharepoint.com/sites/ContosoHub/_layouts/15/teamslogon.aspx?SPFX=true&dest=/sites/ContosoHub</span></span> 

11. <span data-ttu-id="1209a-134">**[Domains And Permissi'ns**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="1209a-134">Navigate to **Domains and Permissi'ns**.</span></span> <span data-ttu-id="1209a-135">有効なドメインセクションに SharePoint online のドメイン名が含まれていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="1209a-135">Make sure the valid domains section contains your SharePoint online domain name.</span></span>
<span data-ttu-id="1209a-136">' ' 例: contoso.sharepoint.com</span><span class="sxs-lookup"><span data-stu-id="1209a-136">'' Example: contoso.sharepoint.com</span></span>

12. <span data-ttu-id="1209a-137">次の web アプリの**シングルサインオン**のプロパティを追加します。 ' ' ' ' は、 **AAD アプリケーション ID**: 00000003-0000-0ff1-Ce00-000000000000**リソースの url**: {{サブドメイン}}。 ID と![Url を含む sharepoint のシングルサインオン。](media/personal-app.png)</span><span class="sxs-lookup"><span data-stu-id="1209a-137">Add the following web app **single sign-on** properties:  ''  Example:''''  **AAD application ID**: 00000003-0000-0ff1-ce00-000000000000  **Resource Url**: {{subdomain}}.sharepoint.com' '' ![Web app single sign-on, with ID and URL.](media/personal-app.png)</span></span>

13. <span data-ttu-id="1209a-138">これらのプロパティを**保存**して、[**テストと配布**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="1209a-138">**Save** these properties and then navigate to **Test and distribute**.</span></span> 

14. <span data-ttu-id="1209a-139">アプリをインストールして、アプリケーションを個人的にテストします。</span><span class="sxs-lookup"><span data-stu-id="1209a-139">Install the app to test the application personally.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1209a-140">Teams アプリ Studio を使っていない場合は、マニフェストを .zip にする必要があります。作成した JSON ファイルで、Teams の [App Store] に移動し、[**カスタムアプリのアップロード**] (app store の右下) をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1209a-140">If you aren't using Teams App Studio, you will have to .zip the manifest.JSON file you just created, navigate to the App Store in Teams, and click  **upload custom app** link (at the bottom right of the App Store).</span></span> <span data-ttu-id="1209a-141">これにより、アプリが利用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="1209a-141">This will make the app available to you.</span></span>

15. <span data-ttu-id="1209a-142">これで、アプリは [静的] タブとして使用できるようになり、チームで読み込みと表示を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="1209a-142">Now the app is available as a static tab for you to load and view in Teams.</span></span>

## <a name="test-and-view-your-new-static-tab"></a><span data-ttu-id="1209a-143">新しい静的タブをテストして表示する</span><span class="sxs-lookup"><span data-stu-id="1209a-143">Test and view your new static tab</span></span>

<span data-ttu-id="1209a-144">Teams のデスクトップで新しいタブを表示するには、アプリバーの左側にある省略記号 (**...**) に移動します。</span><span class="sxs-lookup"><span data-stu-id="1209a-144">To view the new tab on the Teams desktop, navigate to the ellipses (**…**) in the left-hand side of your app bar.</span></span> <span data-ttu-id="1209a-145">新しいアプリを見つけて読み込んで、Teams でスタンドアロンアプリケーションをテストします。</span><span class="sxs-lookup"><span data-stu-id="1209a-145">Find your new app, load it, and test your standalone application in Teams.</span></span>

<span data-ttu-id="1209a-146">新しいアプリを左側のメニューでより高い位置で利用できるようにする場合は、そのためにアプリのポリシー設定を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1209a-146">If you want to make the new app available in the left menu at a higher position, you must use an app policy setting for this.</span></span> <span data-ttu-id="1209a-147">この設定は、[チーム管理者] セクションの [アプリポリシーの >、固定されたアプリケーションの追加 > ます。</span><span class="sxs-lookup"><span data-stu-id="1209a-147">This setting can be found under the Team admin section > app policy > add a pinned application.</span></span> <span data-ttu-id="1209a-148">ユーザーにポリシーを割り当ててテストすると、その変更は24時間後に表示されます。</span><span class="sxs-lookup"><span data-stu-id="1209a-148">When you assign the policy to a user for testing, the change will appear 24 hours later.</span></span> <span data-ttu-id="1209a-149">この点を念頭に置いて、遅延を回避するために、アプリを最も早い都合でどこに表示するかを決定してください。</span><span class="sxs-lookup"><span data-stu-id="1209a-149">With this in mind, please decide where the app should appear at your earliest convenience to help avoid delays.</span></span>

<span data-ttu-id="1209a-150">モバイルデバイスで新しいアプリを表示してテストするには、画面の下部にあるタブバーの**^** 上にあるシェブロン () をタップして、アプリの引き出しを開きます。</span><span class="sxs-lookup"><span data-stu-id="1209a-150">To view and test the new app on a mobile device, open the app drawer by tapping on the chevron (**^**) above the tab bar near the bottom of your screen.</span></span> <span data-ttu-id="1209a-151">アプリを見つけて、モバイルデバイスで探します。</span><span class="sxs-lookup"><span data-stu-id="1209a-151">Find your app and navigate to it on your mobile device.</span></span>
        
> [!CAUTION]
> <span data-ttu-id="1209a-152">モバイルのサポートは、現在の開発者プレビューに含まれています。</span><span class="sxs-lookup"><span data-stu-id="1209a-152">Mobile support is currently in Developer Preview.</span></span> <span data-ttu-id="1209a-153">開発者プレビューを有効にするには、[設定 > に移動し、[開発者用] プレビューモードを有効にします。</span><span class="sxs-lookup"><span data-stu-id="1209a-153">To enable Developer Preview, navigate to Settings > About and then enable Developer Preview mode.</span></span>

## <a name="a-sample-manifestjson-file"></a><span data-ttu-id="1209a-154">サンプルマニフェストファイル</span><span class="sxs-lookup"><span data-stu-id="1209a-154">A Sample Manifest.JSON file</span></span>

<span data-ttu-id="1209a-155">生成される JSO ファイルは、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="1209a-155">The JSO        file you generate will look something like the one below.</span></span>

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
''
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