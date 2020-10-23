---
title: Microsoft Teams でチーム所有者とメンバーを割り当てます
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.reviewer: dansteve
search.appverid: MET150
description: チームを作成する権限など、Microsoft Teams でチーム所有者やメンバーに役割と権限を割り当る方法について説明します。
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: bc85b682ee24b466514e297532dc9ac0deb56924
ms.sourcegitcommit: 1db39fde090809d9abc6d7346dda55814d88993a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/23/2020
ms.locfileid: "48739285"
---
<a name="assign-team-owners-and-members-in-microsoft-teams"></a>Microsoft Teams でチーム所有者とメンバーを割り当てます
=================================================

> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

Microsoft Teams には、**所有者**と**メンバー**という 2 つのユーザー ロールがあります。 既定では、新しいチームを作成したユーザーには所有者ステータスが付与されます。 また、チームの所有者とメンバーには、チャネルに対するモデレーターの機能を割り当てることができます (モデレートが設定されている場合)。 既存の Microsoft 365 グループからチームを作成する場合は、アクセス許可が継承されます。

所有者とメンバーの権限の違いを以下の表に示します。


|    タスク                               | チーム所有者 | チーム メンバー |
|-----------------------------------|------------|-------------|
|          **チームを作成する**          |    Yes<sup>1</sup>     |     いいえ      |
|          **チームを抜ける**           |    はい     |     はい     |
|  **チーム名/説明の編集**   |    はい     |     いいえ      |
|          **チームを削除する**          |    はい     |     不要      |
|          **標準チャネルの追加**          |    必要     |    はい<sup>2</sup>|
| **標準チャネル名/説明の編集** |    必要     |    はい<sup>2</sup>|
|        **標準チャネルの削除**         |    必要     |    はい<sup>2</sup>|
|          **_プライベートチャネルを追加する_*          |    はい     |    はい<sup>2</sup>|
| **_プライベートチャネルの名前と説明を編集する_* |    いいえ     |    該当なし|
|        **_プライベートチャネルを削除する_*         |    はい     |    不要|
|          **メンバーの追加**          |  はい<sup>3</sup>   |     いいえ<sup>4</sup>    |
|          **メンバーを追加する要求**          |  N/A   |     はい<sup>5</sup>     |
|           **アプリの追加**            |    はい     |    Yes<sup>2</sup>|

<sup>1</sup> 制限されていない限り、チームオーナーはチームを作成できます。 後述の「[チームを作成するためのアクセス許可](#permissions-to-create-teams)」をご覧ください。<br>
<sup>2</sup> 所有者はこれらの項目をチーム レベルでオフにできます。その場合、メンバーは項目にアクセスできなくなります。<br>
<sup>3</sup>チームにメンバーを追加した後、所有者はメンバーを所有者ステータスに昇格することができます。 所有者が自分自身のステータスをメンバーに降格することも可能です。<br>
<sup>4</sup>チーム メンバーはパブリック チームにその他のメンバーを追加することができます。<br>
<sup>5</sup>チーム メンバーは、プライベートのチームにメンバーを直接追加することはできませんが、既にメンバーであるチームへの他のユーザーの追加を要求することができます。 メンバーが誰かのチームへの追加を要求すると、チームの所有者はアラートを受け取り、保留中の要求を承認または拒否できます。

* プライベート チャネルのアクセス許可の詳細については、「[Microsoft Teams のプライベート チャネル](private-channels.md)」をご覧ください。

> [!NOTE]
> 所有者は **[チームの表示]** オプションでメンバーを所有者に昇格させることができます。 1 つのチームで最大 100 人の所有者を含むことができます。 チームを管理しやすくするために、複数名の所有者を含めることをお勧めします。所有者が 1 人だけの場合、その所有者が組織からいなくなると、グループが孤立した状態になってしまいます。複数の所有者がいれば、これを避けることができます。 孤立したグループの詳細については、「[孤立したグループに新しい所有者を割り当てる](https://support.office.com/article/Assign-a-new-owner-to-an-orphaned-group-86bb3db6-8857-45d1-95c8-f6d540e45732)」をご覧ください。

## <a name="moderator-capabilities"></a>モデレーターの機能

他の機能に加え、チームの所有者とメンバーには、チャネルに対するモデレーターの機能を割り当てることができます (チームのモデレートが有効になっている場合)。 モデレーターは、チャネルで新しい投稿を開始することと、チームのメンバーが既存のチャネル メッセージに返信できるようするかどうかを制御することができます。 また、ボットとコネクタがチャネル メッセージを送信できるようにするかどうかも制御できます。

モデレーターの機能は、チャネル レベルで割り当てられます。 チーム所有者には、既定でモデレーターの機能が割り当てられています。 チームのメンバーはモデレーターの機能が既定で無効になっていますが、チーム所有者はチャネルごとのモデレーターの機能をチームのメンバーに付与できます。 チャネル内のモデレーターは、そのチャネル内で別のモデレーターを追加および削除できます。

モデレーターの機能の詳細については、「[Microsoft Teams でチャネル モデレーションをセットアップして管理する](manage-channel-moderation-in-teams.md)」をご覧ください。

## <a name="assign-a-user-role"></a>ユーザー ロールの割り当て

ユーザー ロールを割り当てるには、Teams でチーム名を選択し、**[その他のオプション]**  >  **[チームを管理]** をクリックします。 **[メンバー]** タブでは、メンバーを追加し、必要なアクセス許可がある場合は所有者とモデレーターを選択できます。 詳細については、「[Teams でのチーム設定の変更](https://support.office.com/article/ce053b04-1b8e-4796-baa8-90dc427b3acc)」を参照してください。

## <a name="permissions-to-create-teams"></a>チームを作成するためのアクセス許可

デフォルト設定では、Exchange Online にメールボックスを持つすべてのユーザーは Microsoft 365 グループ作成権限があり、すなわち Microsoft Teams でチームを作成する権限があります。 グループの作成と管理に関する権限を特定のユーザーに委任することで、新しいチームおよび Microsoft 365 のグループの作成をより厳重に管理し制限することができます。 手順については、[Microsoft 365 グループを作成できるユーザーを管理する](https://support.office.com/article/manage-who-can-create-office-365-groups-4c46c8cb-17d0-44b5-9776-005fced8e618)を参照してください。


|最小化|タイトル|説明|
|---------|---------|---------|
| ![判断ポイントを表すアイコン](media/Assign_roles_and_permissions_in_Microsoft_Teams_image2.png)     |判断ポイント         |Microsoft Teams のすべてのユーザーがチームを作成できますか (作成できることを推奨)?         |
| ![次の手順を示すアイコン](media/Assign_roles_and_permissions_in_Microsoft_Teams_image3.png)    |次の手順         |チームを作成できるユーザーを制限する場合は、Microsoft 365 グループの既定の作成権限を変更します。         |
