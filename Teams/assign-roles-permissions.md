---
title: Microsoft Teams でチーム所有者とメンバーを割り当てます
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.reviewer: dansteve
search.appverid: MET150
description: チームを作成する権限など、Microsoft Teams でチーム所有者やメンバーに役割と権限を割り当る方法について説明します。
localization_priority: Normal
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6757f7200535dc8fb687915ec033712b2654723b
ms.sourcegitcommit: 100ba1409bf0af58e4430877c1d29622d793d23f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/01/2019
ms.locfileid: "37516446"
---
<a name="assign-team-owners-and-members-in-microsoft-teams"></a>Microsoft Teams でチーム所有者とメンバーを割り当てます
=================================================

> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

Microsoft Teams では、**所有者**と**メンバー**の2つのユーザーロールがあります。 既定では、新しいチームを作成したユーザーには所有者の状態が与えられます。 また、所有者とメンバーは、チャネルに対してモデレーター機能を持つことができます (モデレートが設定されている場合)。 既存の Office 365 グループからチームを作成する場合、アクセス許可は継承されます。

所有者とメンバーの権限の違いを以下の表に示します。


|                                   | チーム所有者 | チーム メンバー |
|-----------------------------------|------------|-------------|
|          **チームを作成する**          |    Yes<sup>1</sup>     |     いいえ      |
|          **チームを抜ける**           |    はい     |     はい     |
|  **チーム名/説明の編集**   |    あり     |     いいえ      |
|          **チームを削除する**          |    あり     |     いいえ      |
|          **チャネルの追加**          |    はい     |    Yes<sup>2</sup>|
| **チャネル名/説明の編集** |    はい     |    Yes<sup>2</sup>|
|        **チャネルを削除する**         |    はい     |    Yes<sup>2</sup>|
|          **メンバーの追加**          |  はい<sup>3</sup>   |     いいえ<sup>4</sup>    |
|          **メンバーを追加する要求**          |  N/A   |     はい<sup>5</sup>     |
|           **タブの追加**            |    はい     |    Yes<sup>2</sup>|
|        **コネクタの追加**         |    はい     |    Yes<sup>2</sup>|
|           **ボットの追加**            |    はい     |    Yes<sup>2</sup>|

<sup>1</sup> 制限されていない限り、チームオーナーはチームを作成できます。 以下の[チームを作成する権限](#permissions-to-create-teams)。<br>
><sup>2</sup>所有者は、これらの項目をチームレベルで無効にすることができます。その場合、メンバーはそれらのアイテムにアクセスできません。<br>
<sup>3</sup>チームにメンバーを追加した後、所有者はメンバーを所有者ステータスに昇格することができます。 所有者が自分自身のステータスをメンバーに降格することも可能です。<br>
<sup>4</sup>チーム メンバーはパブリック チームにその他のメンバーを追加することができます。<br>
<sup>5</sup>チーム メンバーは、プライベートのチームにメンバーを直接追加することはできませんが、既にメンバーであるチームへの他のユーザーの追加を要求することができます。 メンバーが誰かのチームへの追加を要求すると、チームの所有者はアラートを受け取り、保留中の要求を承認または拒否できます。

> [!NOTE]
> 所有者は、[**チームの表示**] オプションで他のメンバーの所有者を作成できます。 1 つのチームで最大 100 人の所有者を含むことができます。 チームを管理するために、少なくともいくつかの所有者を持っていることをお勧めします。これにより、単独の所有者が組織を離れる場合でも、孤立したグループを防ぐことができます。 孤立したグループの詳細については、「[孤立したグループに新しい所有者を割り当てる](https://support.office.com/article/Assign-a-new-owner-to-an-orphaned-group-86bb3db6-8857-45d1-95c8-f6d540e45732)」をご覧ください。

## <a name="moderator-capabilities"></a>モデレーターの機能

その他の機能に加えて、チーム所有者とメンバーは、チャネルのモデレーター機能を使用できます (モデレートが有効になっている場合)。 モデレーターは、チャネルで新しい投稿を開始し、チームメンバーが既存のチャネルメッセージに返信できるかどうかを制御できます。 また、ボットとコネクタがチャネルメッセージを送信できるかどうかを制御することもできます。

モデレーター機能はチャネルレベルで割り当てられます。 チーム所有者は、既定でモデレーター機能を利用できます。 チームメンバーは、既定でモデレーター機能を無効にしていますが、チーム所有者は、チャネルのモデレーター機能をチームメンバーに提供することができます。 チャネル内のモデレーターは、チャネル内の他のモデレーターを追加および削除することができます。

モデレーターの機能の詳細については、「 [Microsoft Teams でチャネルのモデレーションを設定および管理](manage-channel-moderation-in-teams.md)する」を参照してください。

## <a name="assign-a-user-role"></a>ユーザーロールを割り当てる

ユーザーロールを割り当てるには、チーム名を選び、[**その他のオプション** > ] をクリックして**チームを管理**します。 [**メンバー** ] タブでは、メンバーを追加し、必要な権限がある場合は、[所有者] と [モデレーター] を選ぶことができます。 詳細については、「 [Teams でチーム設定を変更](https://support.office.com/article/ce053b04-1b8e-4796-baa8-90dc427b3acc)する」を参照してください。

## <a name="permissions-to-create-teams"></a>チームを作成するためのアクセス許可

デフォルト設定では、Exchange Online にメールボックスを持つすべてのユーザーは Office 365 グループ作成権限があり、すなわちMicrosoft Teams でチームを作成する権限があります。 グループの作成と管理に関する権限を特定のユーザーに委任することで、新しいチームおよび Office 365 のグループの作成をより厳重に管理し制限することができます。 手順については、[Office 365グループを作成できるユーザーを管理する](https://support.office.com/article/manage-who-can-create-office-365-groups-4c46c8cb-17d0-44b5-9776-005fced8e618)を参照してください。


||||
|---------|---------|---------|
| ![判断ポイントを表すアイコン](media/Assign_roles_and_permissions_in_Microsoft_Teams_image2.png)     |判断ポイント         |Microsoft Teams のすべてのユーザーがチームを作成できますか (作成できることを推奨)?         |
| ![次の手順を示すアイコン](media/Assign_roles_and_permissions_in_Microsoft_Teams_image3.png)    |次のステップ         |チームを作成できるユーザーを制限する場合は、Office 365 グループの既定の作成権限を変更します。         |
