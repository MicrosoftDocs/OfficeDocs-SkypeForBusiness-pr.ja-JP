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
description: Microsoft Teams で PDF ファイルを表示および編集するための既定の PDF ビューアーとして Adobe Acrobat を設定する方法について説明します。
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
ms.openlocfilehash: fd74ece7ba59b437fcd8b47bd184cdcfd150438d
ms.sourcegitcommit: 4708fc1c2b8523e1074aed06b1dd6950c039f200
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/25/2022
ms.locfileid: "67002340"
---
# <a name="adobe-acrobat-as-a-default-pdf-viewer-in-teams"></a>Teams の既定の PDF ビューアーとしての Adobe Acrobat

> [!NOTE]
> Teams の既定の PDF エクスペリエンスとしての Adobe Acrobat は、現在パブリック プレビューでのみ使用できます。 この機能を使用する前に、テナントの[パブリック プレビューを有効にします](public-preview-doc-updates.md#enable-public-preview)。 エンド ユーザーが Teams クライアントのバージョンをパブリック プレビューに変更して、Teams で Adobe Acrobat を PDF ビューアーとして体験できるようにします。

管理者は、Microsoft Teams で PDF ファイルを表示および編集する既定のアプリとして Adobe Acrobat を設定できます。 エンド ユーザーは、PDF ファイルの表示、検索、コメント付け、注釈を付けるために Adobe Acrobat サブスクリプションや Adobe ID を必要としません。

## <a name="set-up-adobe-acrobat-app"></a>Adobe Acrobat アプリを設定する

PDF ファイルを表示する既定のアプリとして Adobe Acrobat を設定するには、次の手順に従います。

1. Teams 管理センターにサインインし、**Teams アプリの****[管理アプリ](https://admin.teams.microsoft.com/policies/manage-apps)** > に移動します。

1. Adobe Acrobat アプリを検索し、 **Adobe Acrobat** アプリを選択します。

   > [!NOTE]
   >
   > * Adobe Acrobat アプリの状態が **[許可]** に設定されていることを確認します。 それ以外の場合は、[ **許可]** トグルを有効にします。
   > * アプリのアクセス許可ポリシーまたは組織全体のアプリ設定に、アプリをブロックしている既存の管理者設定がある場合は、 [アプリのアクセス許可ポリシー](teams-app-permission-policies.md) または [組織全体のアプリ設定](teams-app-permission-policies.md)でアプリを許可することを確認します。

1. [ **アクセス許可** ] タブで、[ **アクセス許可の確認**] を選択します。

1. [ **承諾]** を選択します。

   :::image type="content" source="media/permission-policy.png" alt-text="Teams 管理センターのアプリのアクセス許可のスクリーンショット。" lightbox="media/teams-app-adobe-acrobat-permission.png":::

## <a name="install-adobe-acrobat-app-for-all-users"></a>すべてのユーザーに Adobe Acrobat アプリをインストールする

グローバル (組織全体の既定) ポリシーを使用して、Adobe Acrobat アプリを割り当ててすべてのユーザーが使用できるようにします。 この手順では、Teams のシグナルをトリガーして、アプリを PDF ファイルの既定のファイル ハンドラーとして設定します。 すべてのユーザーに Adobe Acrobat アプリを割り当てるには、次の手順に従います。

1. Teams 管理センターで、 **Teams アプリ** > [**のセットアップ ポリシー**](https://admin.teams.microsoft.com/policies/app-setup)に移動します。

1. [ **ポリシーの管理** ] タブで、[ **グローバル ] (組織全体の既定値)** を選択し、[ **編集]** を選択します。

   :::image type="content" source="media/setup-policies.png" alt-text="Teams 管理センターの Adobe Acrobat アプリのセットアップ ポリシーのスクリーンショット。":::

1. [インストール済みアプリ] で、[ **アプリの追加**] を選択します。

1. **Adobe Acrobat** を検索し、アプリ名の横にある [**追加**] を選択し、[**追加**] を選択します。

   :::image type="content" source="media/add-adobe-acrobat.png" alt-text="すべてのユーザーに Adobe Acrobat アプリを追加する方法を示すスクリーンショット。" lightbox="media/add-adobe-acrobat-app.png":::

1. **[保存]** を選択します。

保存を選択すると、Adobe Acrobat アプリは Teams で構成され、チャット、チャネル、またはファイル アプリから Adobe Acrobat アプリ内の PDF ファイルを開きます。

少数の特定のユーザーまたはグループに対して Adobe Acrobat アプリを選択的に許可する場合は、 [カスタム アプリのアクセス許可ポリシー](teams-app-permission-policies.md)を割り当てることができます。

この機能に関する次の情報を確認します。

* ポリシーが設定されると、通常、アプリがユーザーに利用できるようになるまでに [数時間](teams-app-setup-policies.md) かかります。
ポリシーが設定されると、数時間後にインストールされたアプリをユーザーが利用できるようになります。
* チャネルにタブとしてピン留めされた PDF ファイルの表示と、割り当てアプリでの PDF ファイルの表示は、引き続きネイティブ Teams エクスペリエンスによって強化されます。
* Teams の既定の PDF ビューアーとしての Adobe Acrobat は、デスクトップ クライアントと Web クライアントでのみ機能します。 モバイル クライアントではサポートされていません。
* Pdf のエクスポート、ページの整理、ファイルの結合、PDF の圧縮、PDF の保護などのプレミアム ツールを使用するには、Adobe Acrobat プランが必要です。

> [!NOTE]
> Teams デスクトップ クライアントから、Adobe Acrobat アプリへのサインイン中に問題が発生した場合は、ブラウザーで Teams を開いてサインインできます。 これは既知の問題であり、2022 年 9 月までに解決される予定です。

## <a name="faqs"></a>Faq

* Teams クライアントから Adobe Acrobat アプリを削除する方法
  
  エンド ユーザーは Teams クライアントからアプリをアンインストールでき、管理者はセットアップ ポリシーから Adobe Acrobat アプリを削除できます。

* 管理者は、既定のハンドラーとして設定された Adobe Acrobat アプリをブロックできますか?
  
  はい。ただし、管理者がアプリをブロックする前に、セットアップ ポリシーを削除して、エンド ユーザーが Teams の既定のエクスペリエンスに安全に戻っていることを確認します。
