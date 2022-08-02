---
title: Teams の既定の PDF ビューアーとしての Adobe Acrobat
author: guptaashish
ms.author: guptaashish
manager: prkosh
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: ''
search.appverid: ''
f1keywords: ''
description: Adobe Acrobat を既定の PDF ビューアーとして設定して、Microsoft Teamsで PDF ファイルを表示および編集する方法について説明します。
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
ms.openlocfilehash: 913081ee0efc87d66ed304f3de5e9f00b69232fa
ms.sourcegitcommit: 07761c26b53d92fc36b82cab7b3e38a6de4ff945
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/02/2022
ms.locfileid: "67156745"
---
# <a name="adobe-acrobat-as-a-default-pdf-viewer-in-microsoft-teams"></a>Microsoft Teamsの既定の PDF ビューアーとしての Adobe Acrobat

> [!NOTE]
> Microsoft Teamsの既定の PDF エクスペリエンスとしての Adobe Acrobat は、現在パブリック プレビューでのみ使用できます。 この機能を使用するには、管理者はテナントの [パブリック プレビューを有効に](public-preview-doc-updates.md#enable-public-preview) し、エンド ユーザーが Teams クライアントのバージョンをパブリック プレビューに変更することを確認する必要があります。

管理者は、Adobe Acrobat を既定のアプリとして設定して、Microsoft Teamsで PDF ファイルを表示および編集できます。 エンド ユーザーは、Adobe Acrobat サブスクリプションや Adobe ID を使用せずに、PDF ファイルを表示、検索、コメント付け、注釈付けできます。

## <a name="set-up-adobe-acrobat-app"></a>Adobe Acrobat アプリを設定する

アプリを設定する前に、テナントでのアプリの使用を許可すること、Adobe Acrobat アプリを特に許可していること、およびアプリのアクセス許可ポリシーで許可されていることを確認します。 PDF ファイルの既定のアプリとして Adobe Acrobat を設定するには、次の手順に従います。

1. Teams 管理センターにサインインし、**Teams アプリの****[管理アプリ](https://admin.teams.microsoft.com/policies/manage-apps)** > に移動します。

1. Adobe Acrobat アプリを検索して選択します。

1. [ **アクセス許可** ] タブで、[ **アクセス許可の確認**] を選択します。

   :::image type="content" source="media/permission-policy.png" alt-text="Teams 管理センターのアプリのアクセス許可のスクリーンショット。" lightbox="media/teams-app-adobe-acrobat-permission.png":::

1. [ **承諾]** を選択します。

## <a name="install-adobe-acrobat-app-for-all-users"></a>すべてのユーザーに Adobe Acrobat アプリをインストールする

すべてのユーザーが Adobe Acrobat アプリを割り当てて使用できるようにするには、次の手順に従います。

1. Teams 管理センターで、 **Teams アプリ** > [**のセットアップ ポリシー**](https://admin.teams.microsoft.com/policies/app-setup)に移動します。

1. [ **ポリシーの管理** ] タブで、[ **グローバル ] (組織全体の既定値)** を選択し、[ **編集]** を選択します。

   :::image type="content" source="media/setup-policies.png" alt-text="Teams 管理センターの Adobe Acrobat アプリのセットアップ ポリシーのスクリーンショット。":::

1. [インストール済みアプリ] で、[ **アプリの追加**] を選択します。

1. **Adobe Acrobat** を検索し、アプリ名の横にある [**追加**] を選択し、[**追加**] を選択します。

   :::image type="content" source="media/add-adobe-acrobat.png" alt-text="すべてのユーザーに Adobe Acrobat アプリを追加する方法を示すスクリーンショット。" lightbox="media/add-adobe-acrobat-app.png":::

1. **[保存]** を選択します。

保存を選択すると、Teams は ADOBE Acrobat アプリを PDF ファイルの既定のファイル ハンドラーとして使用します。

少数のユーザーまたはグループに対して Adobe Acrobat アプリを選択的に許可する場合は、 [カスタム アプリのアクセス許可ポリシー](teams-app-permission-policies.md)を割り当てることができます。

この機能に関する次の情報を確認します。

* ポリシーが設定されると、通常、アプリがユーザーに利用できるようになるまでに [数時間](teams-app-setup-policies.md) かかります。
* ポリシーが設定されると、数時間後にインストールされたアプリをユーザーが利用できるようになります。
* タブとしてチャネルにピン留めされた PDF ファイルの表示と、割り当てアプリでの PDF ファイルの表示は、引き続きネイティブ Teams エクスペリエンスによって強化されます。
* Teams の既定の PDF ビューアーとしての Adobe Acrobat は、デスクトップ クライアントと Web クライアントでのみ機能します。 モバイル クライアントではサポートされていません。
* Pdf のエクスポート、ページの整理、ファイルの結合、PDF の圧縮、PDF の保護などのプレミアム ツールを使用するには、Adobe Acrobat プランが必要です。
* アプリをアンインストールするために、エンド ユーザーは Teams クライアントからアプリを削除できます。 管理セットアップ ポリシーを使用して Adobe Acrobat アプリを削除できます。
* Adobe Acrobat アプリをブロックする場合は、セットアップ ポリシーから削除します。 これにより、エンド ユーザー エクスペリエンスがネイティブ PDF ファイル ビューアーの使用に戻ります。
* Teams デスクトップ クライアントから、Adobe Acrobat アプリへのサインイン中に問題が発生した場合は、ブラウザーで Teams を使用してサインインします。
