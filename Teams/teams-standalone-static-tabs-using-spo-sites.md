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
ms.openlocfilehash: 772063a7444e9c31d2740ac48635dc0f2e367435
ms.sourcegitcommit: aaae9df142ebb844a1fea27d3ae3b95130903d6a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/01/2020
ms.locfileid: "43100365"
---
# <a name="create-a-teams-intranet-portal-app-from-a-sharepoint-online-site-or-page"></a>SharePoint Online のサイトまたはページから Teams のイントラネットポータルアプリを作成する

この記事の手順を使用して、組織のイントラネットサイトにリンクされたスタンドアロンの静的アプリを Teams 内に作成します。

SharePoint イントラネットサイトの*Teams Personal アプリ*が作成され、teams 内にタブとして表示されます。 このタブには、すべてのチームユーザーにとって重要な情報を含めることができます。 これは、チームユーザーがタブをクリックするだけで更新情報にアクセスできるようにするための、すばやく簡単な方法です。

表示されるプロセスでは、*最新*の SharePoint サイトまたはページを**使用する必要が**あることに注意してください。 このプロセスは、*クラシック*サイトやページでは使用できません。

> [!IMPORTANT]
> テナントで Teams アプリのサイドローディングが有効になっていることを確認します。 Teams 管理ポータルの移行プロセスのどこにいるかによって、[Teams > 管理者] の下で有効にする必要がある場合があります。または、以前のバージョンのポータルで、[管理者 > > 設定] の下にある [Microsoft Teams > アプリ > 外部アプリ > ます。 

## <a name="use-app-studio-to-create-your-standalone-sharepoint-online-app"></a>アプリ Studio を使用して、スタンドアロンの SharePoint Online アプリを作成する

始める前に:
1. SharePoint Online の最新通信またはチームサイトの URL、またはページを知っている必要があります。
    - これらのサイトのパスには、常に/ *teams/* または */sites/* があります。

2. 自分のテナントのサブドメインが、 **{{サブドメイン}}** で使用されていることを確認する必要があります。

3. この記事では、選択したサイトまたはページの*URL*として **{{siteUrl}}** プレースホルダーを使用します。
    - *Url*の例https://contoso.sharepoint.com/teams/Contoso:*または*   https://contoso.sharepoint.com/sites/Contoso 
4. また、 **{{Sitepath}}** は URL の*パス*を示すために使用されます (例:/teams s/Contoso)。
    - *パス*の例:/teams/xml*または*/sites/Contoso 

次の手順に従って開始します。

1. Teams ストアに移動します。

2. App Studio をインストールするか、開きます。

3. [アプリ] オプションの横にある [**開く**] をクリックします。

4. App Studio を開いた状態で、[**マニフェストエディター**] をクリックします。

5. **新しいアプリを作成**します。

6. すべての**アプリの詳細**を入力します。

7. [機能] の下の**タブ**をクリックします。

8. [個人用] タブの [**追加**] をクリックします。

9. **名前**を入力し、**新しい一意のエンティティ ID を**選択します。

10. **Contenturl と Web サイトの url**を入力します。 

- **Contenturl**: {{siteUrl}}/_layouts/15/teamslogon.aspxSPFX = true&dest = {{sitePath}}  
- **websiteUrl**: {{siteUrl}} 

    **Contenturl**の例:https://contoso.sharepoint.com/sites/ContosoHub/_layouts/15/teamslogon.aspx?SPFX=true&dest=/sites/ContosoHub 

11. **[ドメインと権限**] に移動します。 有効なドメインセクションに SharePoint online のドメイン名が含まれていることを確認します。

    例: contoso.sharepoint.com

12. 次の web アプリ**シングルサインオン**プロパティを追加します。 
     
     例: **AAD アプリケーション ID**: 00000003-0000-0ff1-ce00-000000000000**リソース Url**: {{サブドメイン}}. .com

    ![ID と URL の Web アプリシングルサインオン。](media/personal-app.png)

13. これらのプロパティを**保存**して、[**テストと配布**] に移動します。 

14. アプリをインストールして、アプリケーションを個人的にテストします。

> [!IMPORTANT]
> Teams アプリ Studio を使っていない場合は、マニフェストを .zip にする必要があります。作成した JSON ファイルで、Teams の [App Store] に移動し、[**カスタムアプリのアップロード**] (app store の右下) をクリックします。 これにより、アプリが利用できるようになります。

15. これで、アプリは [静的] タブとして使用できるようになり、チームで読み込みと表示を行うことができます。

## <a name="test-and-view-your-new-static-tab"></a>新しい静的タブをテストして表示する

Teams のデスクトップで新しいタブを表示するには、アプリバーの左側にある省略記号 (**...**) に移動します。 新しいアプリを見つけて読み込んで、Teams でスタンドアロンアプリケーションをテストします。

新しいアプリを左側のメニューでより高い位置で利用できるようにする場合は、そのためにアプリのポリシー設定を使用する必要があります。 この設定は、[チーム管理者] セクションの [アプリポリシーの >、固定されたアプリケーションの追加 > ます。 ユーザーにポリシーを割り当ててテストすると、その変更は24時間後に表示されます。 この点を念頭に置いて、遅延を回避するために、アプリを最も早い都合でどこに表示するかを決定してください。

モバイルデバイスで新しいアプリを表示してテストするには、画面の下部にあるタブバーの**^** 上にあるシェブロン () をタップして、アプリの引き出しを開きます。 アプリを見つけて、モバイルデバイスで探します。

> [!CAUTION]
> モバイルのサポートは、現在の開発者プレビューに含まれています。 開発者プレビューを有効にするには、[設定 > に移動し、[開発者用] プレビューモードを有効にします。

## <a name="a-sample-manifestjson-file"></a>サンプルマニフェストファイル

生成した JSON ファイルは、次のようになります。

```JSON
{ 

    "$schema": "https://developer.microsoft.com/en-us/json-schemas/teams/v1.5/MicrosoftTeams.schema.json", 

    "manifestVersion": "1.5", 

    "version": "1.0.0", 

    "id": "33ebded3-931c-4333-b0c5-b51dd8738873", 

    "packageName": "com.contoso.teams.devapp", 

    "developer": { 

        "name": "Contoso", 

        "websiteUrl": "https://www.contoso.com", 

        "privacyUrl": "https://www.contoso.com/privacy", 

        "termsOfUseUrl": "https://www.contoso.com/terms" 

    }, 

    "icons": { 

        "color": "color.png", 

        "outline": "outline.png" 

    }, 

    "name": { 

        "short": "Contoso Intranet", 

        "full": "Intranet Portal for Contoso" 

    }, 

    "description": { 

        "short": "Intranet portal for Contoso", 

        "full": "This app is to demonstrate the capabilities of hosting a SharePoint communication and team site as a standalone app in Teams" 

    }, 

    "accentColor": "#FFFFFF", 

    "staticTabs": [ 

        { 

            "entityId": "communicationSiteTab", 

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