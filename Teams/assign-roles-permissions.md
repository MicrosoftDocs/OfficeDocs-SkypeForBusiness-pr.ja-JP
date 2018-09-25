---
title: チーム所有者およびマイクロソフトのチームのメンバーを割り当てる
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 08/27/2018
ms.topic: article
ms.service: msteams
ms.reviewer: dansteve
search.appverid: MET150
description: チームを作成する権限など、Microsoft Teams でチーム所有者やメンバーに役割と権限を割り当る方法について説明します。
localization_priority: Normal
MS.collection: Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1d5b3f52caf7de455d2b579a3360d17e18602450
ms.sourcegitcommit: 9acf2f80cbd55ba2ff6aab034757cc053287485f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/25/2018
ms.locfileid: "25014292"
---
<a name="assign-team-owners-and-members-in-microsoft-teams"></a>チーム所有者およびマイクロソフトのチームのメンバーを割り当てる
=================================================

> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

マイクロソフトのチーム内では、2 つのユーザー ロール:**所有者**と**メンバー**です。 既定では、新しいチームを作成したユーザーに所有者のステータスが与えられます。 チームが既存の Office 365 グループから作成されると、アクセス許可は継承されます。

所有者とメンバーの権限の違いを以下の表に示します。

|  |チーム所有者  |チーム メンバー  |
|---------|---------|---------|
|**チームの作成**     |はい        |いいえ         |
|**チームを抜ける**     |はい         |はい         |
|**チーム名/説明の編集**      |はい         |いいえ         |
|**チームの削除**      |はい         |いいえ         |
|**チャネルの追加**      |はい         |はい*         |
|**チャネル名/説明の編集**      |はい         |はい*         |
|**チャネルの削除**      |はい         |はい*         |
|**メンバーの追加**      |はい**         |いいえ         |
|**タブの追加**      |はい         |はい*         |
|**コネクタの追加**      |はい         |はい*         |
|**ボットの追加**      |はい         |はい*         |
\*これらの項目がオフにするチーム レベルでは、所有者によって場合、メンバーにはアクセスすることはありません。

\*\*チームへのメンバーの追加後、所有者はメンバーを所有者の状態に昇格させることもできます。また、所有者は自分のステータスをメンバーに降格させることもできます。



> [!NOTE]
> 所有者は [チームの表示] オプションでメンバーを所有者に昇格させることができます。 1 つのチームで最大 100 人の所有者を含むことができます。 チームを管理しやすくするために、複数名の所有者を含めることをお勧めします。所有者が 1 人だけの場合、その所有者が組織からいなくなると、グループが孤立した状態になってしまいます。複数の所有者がいれば、これを避けることができます。 孤立したグループの詳細については、「[孤立したグループに新しい所有者を割り当てる](https://support.office.com/article/Assign-a-new-owner-to-an-orphaned-group-86bb3db6-8857-45d1-95c8-f6d540e45732)」をご覧ください。


<a name="permissions-to-create-teams"></a>チームを作成するためのアクセス許可
---------------------------

既定では、Exchange Online にメールボックスを持つすべてのユーザーは、Office 365 のグループとマイクロソフトのチーム内ではチームを作成する権限を持っています。 厳重に管理し、グループを作成し、一連のユーザーに管理権限を委任することで、新しいチームの作成と Office 365 の新しいグループの作成を制限できます。 手順については、 [Office 365 のグループを作成できるユーザーの管理](https://support.office.com/article/manage-who-can-create-office-365-groups-4c46c8cb-17d0-44b5-9776-005fced8e618)を参照してください。


||||
|---------|---------|---------|
| ![判断ポイント アイコン。](media/Assign_roles_and_permissions_in_Microsoft_Teams_image2.png)     |判断ポイント         |Microsoft Teams のすべてのユーザーがチームを作成できますか (作成できることを推奨)?         |
| ![次のステップ アイコン。](media/Assign_roles_and_permissions_in_Microsoft_Teams_image3.png)    |次のステップ         |チームを作成できるユーザーを制限する場合は、Office 365 グループの既定の作成権限を変更します。         |
