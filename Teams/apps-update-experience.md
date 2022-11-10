---
title: Microsoft Teams でのアプリの更新エクスペリエンス
author: ashishguptaiitb
ms.author: guptaashish
manager: prkosh
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.subservice: teams-apps
audience: Admin
ms.date: 10/22/2022
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: この記事では、Microsoft Teams の Microsoft アプリ、カスタム アプリ、およびサードパーティ アプリが更新される方法と、管理者がそれを促進する方法について説明します。
ms.openlocfilehash: d419e1ed29c6a1cd7a7390bdc0d5eb69371d8547
ms.sourcegitcommit: 22f66e314e631b3c9262c5c7dc5664472f42971e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/10/2022
ms.locfileid: "68912796"
---
# <a name="role-of-an-admin-in-upgrading-teams-apps"></a>Teams アプリのアップグレードにおける管理者の役割

Teams 管理者は、エンド ユーザーが最新バージョンのアプリを入手するのに役立ちます。 これを行うには、次のタスクの 1 つまたは両方を実行します。

* 新しいバージョンがアプリ開発者またはベンダーによって提供されたときに、Teams ストアで使用できる[サード パーティ](#updates-to-third-party-apps)製アプリを更新します。
* 開発者が新しいバージョンを送信したときに、組織内でのみ使用できる[カスタム アプリを更新](#updates-to-custom-apps)します。

## <a name="updates-to-third-party-apps"></a>サード パーティ製アプリへの更新

ユーザーがアプリをインストールして使用するには、必要なサービスと情報にアクセスするためのアクセス許可をアプリに付与する必要があります。 ほとんどの場合、インストールされているアプリの新しいバージョンを Teams ストアで使用できる場合、アプリはすべてのユーザーに対して自動的に更新されます。 ただし、アプリの新しいバージョンのいくつかの特定の変更には、ユーザーのアクセス許可が再び必要です。 この繰り返しユーザーの同意により、機能や個人情報へのアクセスなどの変更に対する認識が保証されます。 Teams 管理者は、 [ユーザーに代わってアプリにアクセス許可を付与](app-permissions-admin-center.md)できます。

アプリ開発者がアプリに対して次の変更を 1 つ以上行う場合、エンド ユーザーはアプリの更新を承認する必要があります。

* ボットを追加します。 プロパティを使用して `botId` ボットの ID を変更します。
* ボットの `isNotificationOnly` 通知を変更する可能性がある既存のボットのプロパティを変更します。
* `SupportsVideo`既存のボットの プロパティ、、および `SupportsFiles` プロパティを変更`SupportsCalling`して、ファイルの呼び出し、ビデオの再生、アップロードまたはダウンロードを行う機能を追加します。
* 承認でアクセス許可を追加または削除します。
* メッセージング拡張機能の追加または削除、グループ タブの追加、コネクタの追加、チャネルの追加を行います。
* マニフェスト ファイル内の の [`webApplicationInfo`](/microsoftteams/platform/resources/schema/manifest-schema#webapplicationinfo) パラメーターを変更します。

<!--- image update
:::image type="content" source="media/manage-your-custom-apps-update1.png" alt-text="New version available." lightbox="media/manage-your-custom-apps-update1.png":::

:::image type="content" source="media/manage-your-custom-apps-update2.png" alt-text="Upgrade option for an app." lightbox="media/manage-your-custom-apps-update2.png":::
--->

## <a name="updates-to-custom-apps"></a>カスタム アプリへの更新

組織内で作成および展開されたカスタム アプリは、テナントまたは組織のユーザーが使用できます。 Teams 管理者は、組織の開発者が新しいバージョンを提供すると、カスタム アプリを新しいバージョンに更新します。 詳細については、「 [管理者がカスタム アプリを管理する方法](custom-app-overview.md)」を参照してください。

## <a name="related-articles"></a>関連記事

* [アプリで行われる更新のマニフェスト スキーマを理解する](/microsoftteams/platform/resources/schema/manifest-schema)。
* [カスタム アプリ管理について知る](custom-app-overview.md)。
