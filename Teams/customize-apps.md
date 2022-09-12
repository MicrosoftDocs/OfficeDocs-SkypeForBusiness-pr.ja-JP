---
title: アプリのカスタマイズを使用して、組織のニーズに合わせてアプリをブランド化する
author: ashishguptaiitb
ms.author: guptaashish
manager: prkosh
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: 組織での導入を改善するために、アプリのメタデータと外観を変更してブランドを変更する方法について説明します。
ms.openlocfilehash: 0a1ae462933768e0c5a53db6c7379e5cd8b9bf05
ms.sourcegitcommit: 41a75f1ba5ceb09f8db7d468aa41b63a89ab9c30
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/12/2022
ms.locfileid: "67647481"
---
# <a name="use-app-customization-to-update-branding-of-apps-in-your-organizations-teams-store"></a>アプリのカスタマイズを使用して、組織の Teams ストア内のアプリのブランド化を更新する

Microsoft Teams 管理者は、一部の Teams アプリの外観を変更して、組織のエンド ユーザーにパーソナライズされたブランド化されたエクスペリエンスを提供できます。 このような変更により、エンド ユーザーの Teams ストア エクスペリエンスが向上し、組織のブランド化に準拠するのに役立ちます。 たとえば、管理者はアプリの説明とアイコンを変更して、組織のエンド ユーザーがアプリを識別しやすくし、その使用方法を理解し、目立つようにすることができます。 管理者は、アプリの一部のメタデータまたはプロパティを変更して、これらの変更を行います。 変更は組織内でのみ使用できます。 この機能は、アプリのカスタマイズと呼ばれます。

管理者は、アプリ開発者がアプリのカスタマイズを許可している場合にのみ、アプリをカスタマイズできます。 Teams にはいくつかのプロパティをカスタマイズするオプションがありますが、アプリ開発者は、管理者が実際にカスタマイズできるプロパティを制御します。

管理者は、次のプロパティをカスタマイズできます。

* 短い形式の名前
* 簡潔な説明
* 詳細な説明
* プライバシー ポリシーの URL
* Web サイトの URL
* 使用条件の URL
* アプリ アイコン
* アイコンのアウトラインの色
* アクセント カラー

これらの各メタデータ フィールドの詳細については、Teams 開発者向けドキュメントの [Teams マニフェスト スキーマ](/microsoftteams/platform/resources/schema/manifest-schema) を参照してください。

> [!NOTE]
> アプリのカスタマイズ機能は、カスタム アプリでは使用できません。 管理者は、Government Community Cloud High (GCCH) 環境と国防総省 (DoD) 環境のアプリをカスタマイズできません。

## <a name="verify-if-an-app-is-customizable"></a>アプリがカスタマイズ可能かどうかを確認する

すべてのアプリはカスタマイズできません。 アプリ開発者がアプリのカスタマイズを許可している場合にのみ、アプリのカスタマイズ機能を使用してアプリの外観を変更できます。 任意のアプリがカスタマイズ可能かどうかを確認するには、次の手順に従います。

1. Teams 管理センターにサインインし、**Teams アプリ** の **[管理アプリ](https://admin.teams.microsoft.com/policies/manage-apps)** > にアクセスします。

1. アプリ名を使用して、カスタマイズするアプリを検索します。 アプリ開発者がアプリのカスタマイズを許可しているかどうかを、[ **カスタマイズ可能]** 列で確認します。 列が表示されない場合は、[列 :::image type="icon" source="media/settings-icon-16px.svg"::: の編集] を選択し、[ **カスタマイズ可能]** オプションを **[オン]** に切り替えます。

   :::image type="content" source="media/customizable-apps-in-tac.png" alt-text="スクリーンショットは、管理センターのカスタマイズ可能な列が、アプリがカスタマイズ可能かどうかを確認するのに役立つことを示しています。":::

Teams ストア内のすべてのカスタマイズ可能なアプリを確認するには、カスタマイズ可能な列を並べ替えます。

## <a name="customize-the-details-of-an-app"></a>アプリの詳細をカスタマイズする

組織の Teams ストアに表示されるアプリの外観を変更するには、次の手順に従います。

1. Teams 管理センターにサインインし、**Teams アプリ** の **[管理アプリ](https://admin.teams.microsoft.com/policies/manage-apps)** > にアクセスします。

1. アプリ名を使用してカスタマイズするアプリを検索し、カスタマイズできることを確認します。

1. UI を開いて個々のメタデータ フィールドをカスタマイズするには、次のいずれかの手順に従います。

   * アプリの行を選択し、[アプリの管理] ページのツール バーで [**カスタマイズ**:::image type="icon" source="media/edit-pen-icon.png":::] を選択します。

   * アプリ名を選択してアプリの詳細ページを開き、[**カスタマイズ可能]** の下にある編集アイコン:::image type="icon" source="media/edit-pen-icon.png":::を選択します。

   * アプリ名を選択し、[ **アクション]** を選択して、[カスタマイズ] を選択 **します**。

     :::image type="content" source="media/customize-action-menu.png" alt-text="スクリーンショットは、[アクション] メニューを開き、アプリの詳細ページから [カスタマイズ] オプションを選択して、アプリをカスタマイズするオプションを示しています。" lightbox="media/customize-action-menu-expanded.png":::

1. 使用可能なフィールドの 1 つ以上をカスタマイズします。 アプリ開発者は、一部のメタデータ フィールドのみをカスタマイズできます。 [カスタマイズ可能なフィールドの考慮事項と制限事項](#considerations-and-limitations-of-app-customization)を参照してください。

   :::image type="content" source="media/customize-settings.png" alt-text="スクリーンショットには、カスタマイズ ユーザー インターフェイスの名前と説明が表示されます。":::

1. アプリをカスタマイズしたら、**[適用]** を選択します。 行った変更を確認するには、 [プレビュー アプリの詳細](#preview-app-details)を参照してください。 変更を元に戻すには、「 [アプリの詳細を既定値にリセットする」を](#reset-app-details-to-default-values)参照してください。

1. [ **発行]** を選択してカスタマイズしたアプリを発行し、[ **アプリの管理** ] ページに一覧表示されます。

<!---
   :::image type="content" source="media/customize-app-colors.png" alt-text="Screenshot showing the icon color options that can be customized.":::
--->

## <a name="preview-app-details"></a>プレビュー アプリの詳細

カスタマイズを保存した後に変更を表示するには、アプリの詳細ページを表示します。

1. Teams 管理センターにサインインし、**Teams アプリ** の **[管理アプリ](https://admin.teams.microsoft.com/policies/manage-apps)** > にアクセスします。

1. アプリの詳細ページを開くには、アプリ名を選択します。

1. **[発行元からの短い** 名前] フィールドに元のアプリ名を含むアプリの詳細を表示します。 このフィールドは、アプリの短い名前を変更した場合にのみ表示されます。

   :::image type="content" source="media/original-app-version.png" alt-text="スクリーンショットは、変更されたアプリの短い名前を示しています。":::

Teams ユーザーは、カスタマイズされたアプリをクライアントの Teams ストアに表示できます。

   :::image type="content" source="media/contoso-app.png" alt-text="スクリーンショットは、Teams クライアントでカスタマイズされたアプリを示しています。":::

## <a name="considerations-and-limitations-of-app-customization"></a>アプリのカスタマイズに関する考慮事項と制限事項

アプリのカスタマイズ機能に関する次の詳細を検討してください。

* アプリの機能をカスタマイズしてもアプリのコピーは作成されないため、アプリのバージョンは 1 つだけです。

* アプリとアプリに関連する説明をカスタマイズする場合は、アプリ開発者がドキュメントまたは使用条件で提供するガイドラインに従っていることを確認します。 サード パーティ製の画像を使用する場合は、著作権に関する法律に従います。

* 管理者から提供されたカスタマイズ データは、最も近い地域に格納されます。

* お客様は、利用規約またはプライバシー ポリシーへのリンクが有効であることを確認する責任があります。

* アプリ開発者がフィールドのカスタマイズを許可しなくなった場合、アプリの詳細ページにメッセージが表示され、カスタマイズできなくなるフィールドについて管理者に通知されます。 そのフィールドに加えられたすべての変更は、元の値に戻されます。

* 運用環境でこれらの変更を行う前に、Teams テスト テナントでアプリのカスタマイズ変更をテストすることをお勧めします。 テスト テナントを取得するには、テスト テナントを [作成](/microsoftteams/platform/concepts/build-and-test/prepare-your-o365-tenant)する手順に従います。

* 変更がすべてのユーザーに反映されるまでに最大 24 時間かかります。

* アプリをカスタマイズ可能にする場合、開発者は新しいバージョンのアプリを提供できます。 新しいバージョンをアップロードし、以前のバージョンのアプリを削除します。 アプリをカスタマイズして発行した場合、アプリカスタマイズ機能を使用してカスタマイズされた新しいアプリは、現在のアプリに置き換わることはありません。

* [アプリの使用状況レポート](teams-analytics-and-reports/app-usage-report.md)には、発行元によって提供されたアプリの元の名前が表示されます。

* Microsoft Graph のアクセス許可の同意ダイアログには、発行元によって提供されたアプリの元の名前が表示されます。 これは、アプリにアクセス許可を提供しながら、アプリを正確に識別するのに役立ちます。

カスタマイズ可能なフィールドの制限事項は次のとおりです。

| カスタマイズ可能なフィールド | 考察 |
|:---|:---|
| 任意の URL フィールド | を使用して `https`、有効でセキュリティで保護された URL を確認します。 |
| 簡潔な説明 | 短い説明は 80 文字未満にする必要があり、完全な説明では繰り返しません。 |
| アイコン | PNG 形式の透明なアウトライン アイコン。解像度は 32 x 32 ピクセルです。 |
| 色アイコン | 解像度が 192 x 192 ピクセルの PNG 形式のフル カラー アイコン。 |
| アクセント カラー | 色は、アイコンの背景と一致する必要があります。 |

## <a name="reset-app-details-to-default-values"></a>アプリの詳細を既定値にリセットする

アプリの詳細は、アプリ開発者が提供する元の値にリセットできます。 このオプションは、カスタマイズしたアプリでのみ使用できます。

1. Teams 管理センターで、**[Teams アプリ]** >  **[[管理アプリ]](https://admin.teams.microsoft.com/policies/manage-apps)** の順にアクセスします。

1. アプリの詳細ページを開くには、アプリ名を選択します。

1. **[アクション]** メニューの [**既定値にリセット**] を選択します。

   :::image type="content" source="media/reset-app-customization.png" alt-text="スクリーンショットは、カスタマイズされたアプリの既定のオプションへのリセットを示しています。":::

## <a name="related-articles"></a>関連記事

* [組織のアプリ ストアをカスタマイズする](customize-your-app-store.md)
* [アプリのブランドを変更する](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/rebrand-apps-to-your-own-organization-s-branding-with-app/ba-p/2376296)
