---
title: Teams 管理センターでチームの所有者とメンバー Microsoft割り当てる
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.reviewer: dansteve
search.appverid: MET150
description: チームを作成する権限など、Microsoft Teams でチーム所有者やメンバーに役割と権限を割り当る方法について説明します。
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.custom: chat-teams-channels-revamp
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: b25a5d654e4bd7a807918aa86e0bfd52aff2ca04
ms.sourcegitcommit: dc5b3870fd338f7e9ab0a602a44eaf9feb595b2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/30/2022
ms.locfileid: "69198759"
---
# <a name="assign-team-owners-and-members-in-microsoft-teams-admin-center"></a>Teams 管理センターでチームの所有者とメンバー Microsoft割り当てる

**所有者** と **メンバー** は、Microsoft Teams 内の 2 つのユーザー ロールです。 新しいチームを作成するユーザーには、既定で所有者の状態が付与されます。 所有者とメンバーは、チームとそのチャネルと対話するときに、さまざまな種類のアクセス許可と機能を持ちます。 Teams の役割の詳細については、「[Microsoft Teams のチームとチャネルの概要](teams-channels-overview.md)」を参照してください。

> [!NOTE]
> 既存の Microsoft 365 グループからチームを作成した場合は、アクセス許可が継承されます。

## <a name="assign-a-user-role-in-teams-admin-center"></a>Teams 管理センターでユーザー ロールを割り当てる

1. Teams 管理センターで、[ **Teams** ] を展開し、[ **チームの管理**] を選択します。
2. [表示名] 列の下にあるチーム名を選択します。
3. [メンバー] タブでは、メンバーを追加または削除し、所有者ロールとモデレーター ロールをメンバーに割り当てることができます。

## <a name="restrict-permission-to-create-teams"></a>チームを作成するためのアクセス許可を制限する

Exchange Onlineのメールボックスを持つすべてのユーザーは、Microsoft Teams 内Microsoft 365 グループとチームを作成するアクセス許可を持っています。 グループの作成と管理権限を一連のユーザーに委任することで、ユーザーが新しいチームを作成できないように制限し、365 グループをMicrosoftします。 この制限が有効な場合、チーム所有者もメンバーも新しいチームを作成できません。 詳細については、「[グループを作成できるユーザーを管理する](https://support.office.com/article/manage-who-can-create-office-365-groups-4c46c8cb-17d0-44b5-9776-005fced8e618)」をご覧ください。

## <a name="user-permissions-based-on-assigned-roles"></a>割り当てられたロールに基づくユーザーのアクセス許可

所有者とメンバーの権限の違いを以下の表に示します。

### <a name="teams"></a>Teams

|Teams タスク| チーム所有者 | チーム メンバー |
|---------|---------|---------|
|チームの作成/削除  |    Yes     |     いいえ    |
|チーム名/説明の編集   |     Yes    |     いいえ     |
|プライベート チームにメンバーを追加する    |     Yes    |  いいえ |
|パブリック チームにメンバーを追加する    |     Yes    |     Yes   |
|新しいメンバーの追加を要求する   |     該当なし    |    はい   |
|ユーザーの状態を昇格/降格する | Yes | いいえ |
|チームを抜ける  |    Yes     |     Yes    |
|アプリの追加と削除   |     Yes    |     はい(チーム所有者が有効にした場合)     |

### <a name="channels"></a>チャネル

|***標準チャネル タスク** _ | _ *Team 所有者** | **チーム メンバー**|
|----|----|----|
|チャネルの作成/削除  |     Yes    |    はい(チーム所有者が有効にした場合)      |
|チャネル名/説明の編集    |    Yes     |     はい(チーム所有者が有効にした場合)    |
|***プライベート チャネル タスク***|
|チャネルを作成する    |    Yes     |    はい(チーム所有者が有効にした場合)      |
|チャネルを削除する    |    Yes     |    いいえ     |
|チャネル名/説明の編集 |     いいえ    |    該当なし     |
|***共有チャネル タスク***
|チャネルを作成する    |    Yes     |     いいえ    |
|チャネルを削除する | Yes | いいえ |
|チャネル名/説明の編集    |    いいえ     |     いいえ    |
