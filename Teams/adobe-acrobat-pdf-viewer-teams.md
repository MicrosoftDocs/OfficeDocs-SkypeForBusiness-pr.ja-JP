---
title: Teams の既定の PDF ビューアーとしての Adobe Acrobat
author: ashishguptaiitb
ms.author: guptaashish
manager: prkosh
ms.topic: article
ms.service: msteams
audience: admin
ms.subservice: teams-apps
ms.date: 09/25/2022
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: ''
search.appverid: ''
f1keywords: ''
description: Microsoft Teams で PDF ファイルを表示および編集するための既定の PDF ビューアーとして Adobe Acrobat を設定する方法について説明します。
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
ms.openlocfilehash: 546328ade88864f1412a2da6f94caf2d1f44aef8
ms.sourcegitcommit: 22f66e314e631b3c9262c5c7dc5664472f42971e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/10/2022
ms.locfileid: "68912826"
---
# <a name="set-adobe-acrobat-as-the-default-pdf-viewer-in-microsoft-teams"></a>Microsoft Teams で Adobe Acrobat を既定の PDF ビューアーとして設定する

> [!NOTE]
> Microsoft Teams の既定の PDF エクスペリエンスとしての Adobe Acrobat は、現在パブリック プレビューでのみ利用できます。 この機能を使用するには、管理者はテナントの[パブリック プレビューを有効に](public-preview-doc-updates.md#enable-public-preview)し、エンド ユーザーが Teams クライアントのバージョンをパブリック プレビューに変更することを確認する必要があります。

管理者は、Microsoft Teams で PDF ファイルを表示および編集する既定のアプリとして Adobe Acrobat を設定できます。 エンド ユーザーは、Adobe Acrobat サブスクリプションや Adobe ID がなくても、PDF ファイルの表示、検索、コメント、注釈付けを行うことができます。

テナント内の PDF ファイルの既定のハンドラーとして Adobe Acrobat アプリを構成するには、前提条件として次の手順を実行します。

* [Adobe Acrobat アプリを許可します](#allow-adobe-acrobat-app-in-your-tenant)。
* [Adobe Acrobat アプリをインストールします](#install-adobe-acrobat-app-for-all-users)。

## <a name="allow-adobe-acrobat-app-in-your-tenant"></a>テナントで Adobe Acrobat アプリを許可する

アプリを設定する前に、テナントでのアプリの使用を許可すること、Adobe Acrobat アプリを特に許可していること、およびアプリのアクセス許可ポリシーで許可されていることを確認します。 PDF ファイルの既定のアプリとして Adobe Acrobat を設定するには、次の手順に従います。

1. Teams 管理センターにサインインし、**Teams アプリ** にアクセス **[してアプリ](https://admin.teams.microsoft.com/policies/manage-apps)** > を管理します。

1. Adobe Acrobat アプリを検索して選択します。 アプリの詳細ページが開きます。

1. [ **アクセス許可** ] タブを選択し、[ **アクセス許可の確認**] を選択します。

   :::image type="content" source="media/permission-policy.png" alt-text="Teams 管理センターのアプリのアクセス許可のスクリーンショット。" lightbox="media/teams-app-adobe-acrobat-permission.png":::

1. **[同意する]** を選択します。

## <a name="install-adobe-acrobat-app-for-all-users"></a>すべてのユーザー用に Adobe Acrobat アプリをインストールする

すべてのユーザーが Adobe Acrobat アプリを割り当てて使用できるようにするには、次の手順に従います。

1. Teams 管理センターで、**[Teams アプリ]** > [**[セットアップ ポリシー]**](https://admin.teams.microsoft.com/policies/app-setup) に移動します。

1. **[ポリシーの管理]** タブで、**[グローバル] (組織全体の既定値)** を選択し、**[編集]** を選択します。

   :::image type="content" source="media/setup-policies.png" alt-text="Teams 管理センターの Adobe Acrobat アプリのセットアップ ポリシーのスクリーンショット。":::

1. [インストール済みアプリ] で、**[アプリの追加]** を選択します。

1. **Adobe Acrobat** を検索し、アプリ名の横にある **[追加]** を選択し、さらに **[追加]** を選択します。

   :::image type="content" source="media/add-adobe-acrobat.png" alt-text="すべてのユーザーに Adobe Acrobat アプリを追加する方法を示すスクリーンショット。" lightbox="media/add-adobe-acrobat-app.png":::

1. **[保存]** を選択します。

保存を選択すると、Teams は ADOBE Acrobat アプリを PDF ファイルの既定のファイル ハンドラーとして使用します。

少数の個人またはグループに対して Adobe Acrobat アプリを選択的に許可する場合は、 [アプリのアクセス許可にカスタム ポリシーを](teams-app-permission-policies.md)割り当てることができます。

## <a name="considerations-and-limitations"></a>考慮事項と制限事項

この機能に関する次の情報をご確認ください。

* ポリシーを設定した後、通常、アプリをユーザーが使用できるようになるには [数時間かかります](teams-app-setup-policies.md#considerations-and-limitations) 。
* タブとしてチャネルにピン留めされた PDF ファイルの表示と、割り当てアプリでの PDF ファイルの表示は、引き続きネイティブ Teams エクスペリエンスによって提供されます。
* Teams の既定の PDF ビューアーとしての Adobe Acrobat は、デスクトップ クライアントと Web クライアントでのみ機能します。 モバイル クライアントではサポートされていません。
* PDF のエクスポート、ページの整理、ファイルの結合、PDF の圧縮、PDF の保護などのプレミアム ツールを使用するには、Adobe Acrobat プランが必要です。
* アプリをアンインストールするために、エンド ユーザーは Teams クライアントからアプリを削除できます。 管理者は、セットアップ ポリシーを使用して Adobe Acrobat アプリを削除できます。
* Adobe Acrobat アプリをブロックした場合は、セットアップ ポリシーからアプリを削除します。 これにより、エンドユーザーのエクスペリエンスがネイティブ PDF ファイル ビューアーの使用に戻ります。
* Teams デスクトップ クライアントで Adobe Acrobat アプリにサインインしているときに問題が発生した場合は、 [ブラウザーで Teams](https://teams.microsoft.com/) を使用してサインインします。
