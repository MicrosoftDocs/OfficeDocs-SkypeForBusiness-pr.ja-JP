---
title: Microsoft Teams でチーム所有者とメンバーを割り当てます
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 08/27/2018
ms.topic: conceptual
ms.service: msteams
ms.reviewer: dansteve
search.appverid: MET150
description: チームを作成する権限など、Microsoft Teams でチーム所有者やメンバーに役割と権限を割り当る方法について説明します。
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 423a12e8fce0c9d7508e97c1f57e17a0ba8a0ff0
ms.sourcegitcommit: 75b2cd0d2d39c50dc1e1513860841e2ae3f84324
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/28/2019
ms.locfileid: "34493803"
---
<a name="assign-team-owners-and-members-in-microsoft-teams"></a>Microsoft Teams でチーム所有者とメンバーを割り当てます
=================================================

> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

Microsoft Teams には、**所有者**と**メンバー**の2つのユーザーロールがあります。 新しいチームを作成したユーザーにはデフォルトで所有者ステータスが付与されます。 チームが既存のOffice 365グループから作成された場合、権限は継承されます。

所有者とメンバーの権限の違いを以下の表に示します。


|                                   | チーム所有者 | チーム メンバー |
|-----------------------------------|------------|-------------|
|          **チームを作成する**          |    Yes<sup>1</sup>     |     いいえ      |
|          **チームを抜ける**           |    はい     |     はい     |
|  **チーム名/説明の編集**   |    はい     |     いいえ      |
|          **チームを削除する**          |    はい     |     いいえ      |
|          **チャネルの追加**          |    はい     |    Yes<sup>2</sup>|
| **チャネル名/説明の編集** |    はい     |    Yes<sup>2</sup>|
|        **チャネルを削除する**         |    はい     |    Yes<sup>2</sup>|
|          **メンバーの追加**          |  はい<sup>3</sup>   |     いいえ<sup>4</sup>    |
|          **メンバーを追加する要求**          |  N/A   |     はい<sup>5</sup>     |
|           **タブの追加**            |    はい     |    Yes<sup>2</sup>|
|        **コネクタの追加**         |    はい     |    Yes<sup>2</sup>|
|           **ボットの追加**            |    はい     |    Yes<sup>2</sup>|

<sup>1</sup> 制限されていない限り、チームオーナーはチームを作成できます。 ”チームを作成するアクセス許可”を参照してください。
>
<sup>2</sup> 所有者はこれらの項目をチーム レベルでオフにできます。その場合、メンバーは項目にアクセスできなくなります。

<sup>3</sup>チームにメンバーを追加した後、所有者はメンバーを所有者ステータスに昇格することができます。 所有者が自分自身のステータスをメンバーに降格することも可能です。

<sup>4</sup>チーム メンバーはパブリック チームにその他のメンバーを追加することができます。

<sup>5</sup>チーム メンバーは、プライベートのチームにメンバーを直接追加することはできませんが、既にメンバーであるチームへの他のユーザーの追加を要求することができます。 メンバーが誰かのチームへの追加を要求すると、チームの所有者はアラートを受け取り、保留中の要求を承認または拒否できます。



> [!NOTE]
> 所有者は [チームの表示] オプションでメンバーを所有者に昇格させることができます。 1 つのチームで最大 100 人の所有者を含むことができます。 チームを管理しやすくするために、複数名の所有者を含めることをお勧めします。所有者が 1 人だけの場合、その所有者が組織からいなくなると、グループが孤立した状態になってしまいます。複数の所有者がいれば、これを避けることができます。 孤立したグループの詳細については、「[孤立したグループに新しい所有者を割り当てる](https://support.office.com/article/Assign-a-new-owner-to-an-orphaned-group-86bb3db6-8857-45d1-95c8-f6d540e45732)」をご覧ください。


<a name="permissions-to-create-teams"></a>チームを作成するためのアクセス許可
---------------------------

デフォルト設定では、Exchange Online にメールボックスを持つすべてのユーザーは Office 365 グループ作成権限があり、すなわちMicrosoft Teams でチームを作成する権限があります。 グループの作成と管理に関する権限を特定のユーザーに委任することで、新しいチームおよび Office 365 のグループの作成をより厳重に管理し制限することができます。 手順については、[Office 365グループを作成できるユーザーを管理する](https://support.office.com/article/manage-who-can-create-office-365-groups-4c46c8cb-17d0-44b5-9776-005fced8e618)を参照してください。


||||
|---------|---------|---------|
| ![判断ポイントを表すアイコン](media/Assign_roles_and_permissions_in_Microsoft_Teams_image2.png)     |判断ポイント         |Microsoft Teams のすべてのユーザーがチームを作成できますか (作成できることを推奨)?         |
| ![次の手順を示すアイコン](media/Assign_roles_and_permissions_in_Microsoft_Teams_image3.png)    |次のステップ         |チームを作成できるユーザーを制限する場合は、Office 365 グループの既定の作成権限を変更します。         |
