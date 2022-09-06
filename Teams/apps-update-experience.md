---
title: Microsoft Teams でのアプリの更新エクスペリエンス
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
description: この記事では、Microsoft Teams の Microsoft アプリ、カスタム アプリ、およびサードパーティ アプリが更新される方法と、管理者がそれを促進する方法について説明します。
ms.openlocfilehash: b947e8b77bc167ccbdfb6a90bfa7c4ab96476efc
ms.sourcegitcommit: 75dfc3cd9b59282d68e35e4d7185da572eb3795c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/06/2022
ms.locfileid: "67606096"
---
# <a name="teams-app-updates-and-admin-role"></a>Teams アプリの更新プログラムと管理者ロール

Teams 管理者は、エンド ユーザーが最新バージョンのアプリを入手できるように支援できます。 これを行うには、次のいずれかのタスクまたは両方のタスクを実行します。

* 新しいバージョンがアプリ開発者またはベンダーによって提供されたときに Teams ストアで使用できる[サード パーティ](#updates-to-third-party-apps)製アプリを更新します。
* 開発者が新しいバージョンを送信したときに、組織内でのみ使用できる[カスタム アプリを更新](#updates-to-custom-apps)します。

## <a name="updates-to-third-party-apps"></a>サード パーティ製アプリへの更新

ユーザーがアプリをインストールして使用するには、必要なサービスと情報にアクセスするためのアクセス許可をアプリに付与する必要があります。 ほとんどの場合、インストールされているアプリの新しいバージョンが Teams ストアで使用できる場合、アプリはすべてのユーザーに対して自動的に更新されます。 ただし、アプリの新しいバージョンでいくつかの特定の変更を行うには、ユーザーのアクセス許可をもう一度必要とします。 この繰り返しユーザー受け入れにより、機能や個人情報へのアクセスなどの変更に対する認識が保証されます。 Teams 管理者は、 [ユーザーに代わってアプリにアクセス許可を付与](app-permissions-admin-center.md)できます。

アプリ開発者が次の 1 つ以上の変更をアプリに加えた場合、エンド ユーザーはアプリの更新を承認する必要があります。

* ボットを追加または削除します。 プロパティを使用してボットの ID を変更します `botId` 。
* ボットの通知を `isNotificationOnly` 変更する可能性がある既存のボットのプロパティを変更します。
* 既存のボットの変更、`SupportsVideo`プロパティ`SupportsFiles`を変更`SupportsCalling`して、ビデオの呼び出し、再生、ファイルのアップロードまたはダウンロードを行う機能を追加します。
* 承認でアクセス許可を追加または削除します。
* メッセージング拡張機能の追加または削除、グループ タブの追加、コネクタの追加、またはチャネルの追加。
* マニフェスト ファイル内の [`webApplicationInfo`](/microsoftteams/platform/resources/schema/manifest-schema#webapplicationinfo) パラメーターを変更します。

<!--- image update
:::image type="content" source="media/manage-your-custom-apps-update1.png" alt-text="New version available." lightbox="media/manage-your-custom-apps-update1.png":::

:::image type="content" source="media/manage-your-custom-apps-update2.png" alt-text="Upgrade option for an app." lightbox="media/manage-your-custom-apps-update2.png":::
--->

## <a name="updates-to-custom-apps"></a>カスタム アプリへの更新

組織内で作成および展開されるカスタム アプリは、テナントまたは組織のユーザーが利用できます。 Teams 管理者は、組織内の開発者が提供するカスタム アプリを新しいバージョンに更新します。 詳細については、 [管理者がカスタム アプリを管理する方法に関するページを](custom-app-overview.md)参照してください。

## <a name="related-article"></a>関連記事

* [アプリで行われる更新のマニフェスト スキーマを理解する](/microsoftteams/platform/resources/schema/manifest-schema)。
* [カスタム アプリ管理について知る](custom-app-overview.md)。
