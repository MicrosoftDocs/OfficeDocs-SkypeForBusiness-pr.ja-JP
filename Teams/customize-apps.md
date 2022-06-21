---
title: 組織のTeams ストア内のアプリの外観を変更する
author: guptaashish
ms.author: guptaashish
manager: prkosh
ms.reviewer: v-tbasra
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: アプリの詳細とメタデータを編集して、アプリの外観を変更し、アプリのブランドを変更する方法について説明します。
ms.openlocfilehash: 62924c6b3ffb4561427d921a4edc26d4888b4d6b
ms.sourcegitcommit: 9946c6c1faa78617ccd7bdf115457090ebce5619
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/21/2022
ms.locfileid: "66190347"
---
# <a name="customize-appearance-of-apps-in-your-organizations-teams-store"></a>組織のTeams ストアでアプリの外観をカスタマイズする

Microsoft Teamsでは、管理者はTeams アプリをカスタマイズして、ストア エクスペリエンスを向上させ、組織のブランド化に従うことができます。 アプリ開発者は、Teams管理者によるアプリのカスタマイズを許可できます。その後、管理センターの [アプリの管理] ページで、組織のニーズに基づいてアプリのプロパティTeams更新できます。 カスタマイズできる詳細は次のとおりです。

* 短い名前
* 簡単な説明
* 完全な説明
* プライバシー ポリシーの URL
* Web サイトの URL
* 使用条件 URL
* アプリ アイコン
* アイコンのアウトラインの色
* アクセントの色

アプリのさまざまなメタデータ フィールドの詳細については、開発者向けドキュメントの[Teams マニフェスト スキーマ](/microsoftteams/platform/resources/schema/manifest-schema)を参照してください。

> [!NOTE]
> サイドロードされたアプリは、どの組織でもカスタマイズできません。 Government Community Cloud High (GCCH) または国防総省 (DoD) クラウド内のアプリをカスタマイズすることはできません。

## <a name="customize-details-of-an-app"></a>アプリの詳細をカスタマイズする

アプリをカスタマイズするには、次の手順を実行します。

1. Teams 管理センターにサインインします。

1. **Teamsアプリを** 展開し、[アプリの **[管理](https://admin.teams.microsoft.com/policies/manage-apps)**] を選択します。

1. アプリの一覧の **[カスタマイズ可能]** 列を確認し、カスタマイズ可能なアプリで並べ替えます。

   ![管理センターの [カスタマイズ] 列は、カスタマイズ可能なアプリを表示するのに役立ちます。](media/customizable-apps-in-tac.png)

   カスタマイズ機能にアクセスするには、次の 3 つのエントリ ポイントがあります。

   * カスタマイズするアプリの横にあるを選択し、[ **カスタマイズ**] を選択します。

     ![カスタマイズ選択オプション 1。](media/select-app-to-customize1.png)

   * アプリ名を選択し、[ **カスタマイズ可能]** で編集アイコンを選択します。

     ![カスタマイズ選択オプション 2。](media/communities-microsoft.png)

   * アプリ名を選択し、[**アクション]** で **[オーバーフロー] メニュー** をクリックし、[カスタマイズ] を選択します。

     ![カスタマイズ選択オプション 3。](media/customize-action-menu.png)

1. **[詳細**] セクションを展開し、次の 1 つ以上のフィールドをカスタマイズします。 開発者がカスタマイズ可能として割り当てたフィールドが表示されます。

    * 短い名前
    * 簡単な説明
    * 完全な説明
    * Web サイト
    * プライバシー ポリシーの URL
    * 使用条件 URL

   ![カスタマイズ設定。](media/customize-settings.png)

1. **[アイコン**] セクションを展開します。

1. アイコンをアップロードします。 PNG 形式で 1 つのアイコン (192 x 192) ピクセルを使用します。

1. アイコンのアウトラインの色を選択します。 PNG 形式で 1 つの透明なアウトライン (32x32) ピクセルを使用します。

1. アイコンに一致するアプリのアクセントの色を選択します。

   ![アイコン パネルの色オプションをカスタマイズします。](media/customize-app-colors.png)

1. アプリをカスタマイズしたら、[適用] を選択 **します**。

1. [ **発行]** を選択して、カスタマイズしたアプリを発行します。

   カスタマイズしたアプリが [アプリの **管理** ] ページに一覧表示されます。 アプリの機能をカスタマイズしてもアプリのコピーは作成されないため、アプリのバージョンは 1 つだけです。

これで、Teamsエンド ユーザーは、カスタマイズされたアプリをクライアントに表示できるようになりました。

   ![Teams クライアントでカスタマイズされたアプリ。](media/contoso-app.png)

アプリのカスタマイズに関する次の詳細に注意してください。

* アプリをカスタマイズする場合、およびアプリに関連するすべての説明は、アプリ発行元がドキュメントまたは使用条件で提供する場合は、カスタマイズ ガイドラインに従っていることを確認します。 また、お客様は、使用する可能性があるサードパーティの画像に関する他者の権利を尊重する責任も負います。

* 管理提供されたカスタマイズ データは、最も近いリージョンに格納されます。

* お客様は、利用規約またはプライバシー ポリシーへのリンクが有効であることを確認する責任があります。

* アプリ発行元がフィールドのカスタマイズを許可しなくなった場合、アプリの詳細ページにメッセージが表示され、カスタマイズできないフィールドについて管理者に通知されます。 そのフィールドに加えられたすべての変更は、元の値に戻されます。

* 運用環境でこれらの変更を行う前に、Teamsテスト テナントでアプリカスタマイズの変更をテストすることをお勧めします。

* ブランドの変更は、すべてのユーザーに反映されるまでに最大 24 時間かかる場合があります。

* アプリをカスタマイズ可能にするには、開発者は新しいバージョンのアプリを提供できます。 新しいバージョンをアップロードし、以前のバージョンのアプリを削除します。 アプリをカスタマイズして発行した場合、アプリカスタマイズ機能を使用してカスタマイズされた新しいアプリは、現在のアプリに置き換わることはありません。

* [アプリの使用状況レポート](teams-analytics-and-reports/app-usage-report.md)には、発行元によって提供されたアプリの元の名前が表示されます。

* Microsoft Graphアクセス許可の同意ダイアログには、発行元によって提供されたアプリの元の名前が表示されます。 アプリに対するアクセス許可を提供しながら、アプリを正確に識別するのに役立ちます。

## <a name="review-app-details"></a>アプリの詳細を確認する

アプリの詳細を表示して情報を確認することもできます。

1. Teams 管理センターにサインインします。

1. **Teamsアプリを** 展開し、[アプリの **[管理](https://admin.teams.microsoft.com/policies/manage-apps)**] を選択します。

1. アプリ名を選択します。

1. 発行元の元のアプリ名 **の短い名前** を含む、アプリの詳細を表示します。

   ![アイコン パネルのアプリ名をカスタマイズします。](media/original-app-version.png)

   [ **発行元からの短い名前** ] フィールドは、アプリの短い名前を変更した場合にのみ表示されます。

## <a name="reset-app-details-to-default-values"></a>アプリの詳細を既定値にリセットする

アプリの詳細は、アプリ開発者が提供する元の値にリセットできます。 このオプションは、カスタマイズしたアプリでのみ使用できます。

1. Teams管理センターで、**アプリ管理アプリTeams** > アクセス **[します](https://admin.teams.microsoft.com/policies/manage-apps)**。

1. アプリ名を選択します。

1. **[アクション]** メニューから [**既定値にリセット**] を選択します。

   ![[既定値にリセット] を選択します。強調表示されています。](media/select-reset.png)

## <a name="related-article"></a>関連記事

* [アプリを管理する](manage-apps.md)
* [組織のアプリ ストアをカスタマイズする](customize-your-app-store.md)
* [アプリのブランドを変更する](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/rebrand-apps-to-your-own-organization-s-branding-with-app/ba-p/2376296)
