---
title: SharePoint Online サイトまたはページから Terms の「イントラネット ポータル アプリ」を作成する
author: cichur
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
ms.openlocfilehash: 1b89a17f81024fba05a1be9fb1dc4d59b1aceafd
ms.sourcegitcommit: 67782296062528bbeade5cb9074143fee0536646
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/24/2020
ms.locfileid: "49731115"
---
# <a name="create-a-teams-intranet-portal-app-from-a-sharepoint-online-site-or-page"></a>SharePoint Online サイトまたはページから Terms の「イントラネット ポータル アプリ」を作成する

この記事の手順を使用して、組織のイントラネット サイトにリンクされたスタンドアロンの静的アプリを Teams 内に作成します。

SharePoint イントラネット サイトの *Teams 個人用アプリ* が作成され、Teams 内にタブとして表示されます。 このタブには、すべての Teams ユーザーにとって重要な情報を含めることができます。 これは、Teams ユーザーが、タブをクリックするだけで更新情報にアクセスできるようにするための、すばやく簡単な方法です。

示されているプロセスが機能するには、*最新の* SharePoint サイトまたはページを **使用する必要がある** ことに注意してください。 このプロセスは、*クラシック* サイトやページでは使用できません。

> [!IMPORTANT]
> テナントで Teams アプリのサイドローディングが有効になっていることを確認します。 Teams 管理ポータルの移行プロセスの段階によっては、ポータルの以前のバージョン内の [Teams] > [管理者] の下、または [管理者] > [設定] > [サービスとアドイン] > [Microsoft Teams] > [アプリ] > [外部アプリ] の下のいずれかで Teams アプリのサイドローディングを有効にする必要があります。

## <a name="use-app-studio-to-create-your-standalone-sharepoint-online-app"></a>App Studio を使用して、スタンドアロンの SharePoint Online アプリを作成する

開始する前に、

1. SharePoint Online の最新のコミュニケーションや Teams サイトの URL、またはページを知っている必要があります。
    - これらのサイトのパスには、常に */teams/* または */sites/* があります。

2. 自分のテナントのサブドメインを知っておく必要があります。これはプレースホルダーの **{{subdomain}}** で使用します。

3. この記事では、選択したサイトまたはページの *URL* のプレースホルダーとして **{{siteUrl}}** を使用します。
    - *URL* の例: `https://contoso.sharepoint.com/teams/Contoso`
        *または* `https://contoso.sharepoint.com/sites/Contoso`
4. また、URL の *パス* を示すために **{{sitePath}}** を使用します (例: /teams/Contoso)。
    - *パス* の例:   /teams/Contoso   *または* /sites/Contoso

次の手順に従って開始します。

1. Teams ストアに移動します。

2. App Studio をインストールするか、開きます。

3. アプリのオプションの横にある **[開く]** をクリックします。

4. App Studio を開いた状態で、**[マニフェスト エディター]** をクリックします。

5. **新しいアプリを作成** します。

6. すべての **アプリの詳細** を入力します。

7. [機能] の下の **タブ** をクリックします。

8. [個人用] タブの **[追加]** をクリックします。

9. **名前** を入力し、**新しい一意のエンティティ ID** を選択します。

10. **contentURL と Web サイトの URL** を入力します。

- **contentUrl**: {{siteUrl}}/_layouts/15/teamslogon.aspx?SPFX=true&dest={{sitePath}}  
- **websiteUrl**: {{siteUrl}}

    **contentURL** の例: `https://contoso.sharepoint.com/sites/ContosoHub/_layouts/15/teamslogon.aspx?SPFX=true&dest=/sites/ContosoHub`

11. **[ドメインとアクセス許可]** に移動します。 有効なドメイン セクションに SharePoint Online のドメイン名が含まれていることを確認します。

    例: `contoso.sharepoint.com`

12. 次の Web アプリの **シングル サインオン** のプロパティを追加します。

     例:  **AAD アプリケーション ID**: 00000003-0000-0ff1-ce00-000000000000  **リソースの URL**: {{subdomain}}.sharepoint.com

    ![ID と URL を使用した Web アプリのシングル サインオン。](media/personal-app.png)

13. これらのプロパティを **保存** して、**[テストと配布]** に移動します。

14. アプリをインストールして、アプリケーションを個人でテストします。

> [!IMPORTANT]
> Teams App Studio を使用していない場合は、作成した manifest.JSON ファイルを .zip にする必要があります。Teams 内の [App Store] に移動し、**[カスタム アプリのアップロード]** リンク (App Store の右下部分) をクリックします。 これにより、アプリが利用できるようになります。

15. これで、アプリを静的タブとして使用できるようになり、Teams で読み込みと表示を行うことができます。

## <a name="test-and-view-your-new-static-tab"></a>新しい静的タブをテストして表示する

Teams デスクトップで新しいタブを表示するには、アプリ バーの左側にある省略記号 (**…**) に移動します。 新しいアプリを見つけて読み込んで、スタンドアロン アプリケーションを Teams でテストします。

新しいアプリを左側のメニューのより高い位置で使用できるようにするには、そのためにアプリのポリシー設定を使用する必要があります。 この設定は、[Teams 管理セクション] > [アプリ ポリシー] > [固定されたアプリケーションの追加] の下にあります。 テストのためにユーザーにポリシーを割り当てると、その変更は数時間後に表示されます。 この点を念頭に置いて、遅延を回避するために、アプリを表示する位置をできるだけ早く決定してください。

モバイル デバイスで新しいアプリを表示してテストするには、画面の下部にあるタブ バーの上のシェブロン (**^**) をタップして、アプリ ドロワーを開きます。 アプリを見つけて、モバイル デバイスでそのアプリに移動します。

> [!CAUTION]
> 現在、モバイル サポートは開発者プレビューに含まれています。 開発者プレビューを有効にするには、[設定] > [バージョン情報] に移動して、開発者プレビュー モードを有効にします。

## <a name="a-sample-manifestjson-file"></a>Manifest.JSON ファイルのサンプル

生成される JSON ファイルは、次のようになります。

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
