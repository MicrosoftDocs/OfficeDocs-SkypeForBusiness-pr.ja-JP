---
title: Microsoft Teams で組織全体のチームを使用して、全員の共同作業を支援する
ms.author: mikeplum
author: MikePlumleyMSFT
ms.reviewer: phlouie
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Teams で組織全体のチームを作成および管理し、小規模から中規模の組織のすべてのユーザーが共同作業を行う方法を提供する方法について説明します。
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- EngageScoreOct2022
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 3ae5ffc68d14b9998721010e8f6b8ed595ac26e9
ms.sourcegitcommit: 6d2e4f5e09b22a8192405f4eba90960a152032d9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/08/2022
ms.locfileid: "68885080"
---
# <a name="use-organization-wide-teams-in-microsoft-teams-to-help-everyone-collaborate"></a>Microsoft Teams で組織全体のチームを使用して、全員の共同作業を支援する

グローバル管理者は、小規模から中規模の組織のすべてのユーザーが 1 つの共同作業チームの一員になる方法を提供する組織全体のチームを作成できます。 組織全体のチームは、組織内のすべてのユーザーを自動的に含め、ユーザーが組織に参加して脱退するにつれてメンバーシップを最新の状態に保ちます。

組織が Teams を初めて使用し、ユーザー数が 5,000 人以下の場合、組織全体のチームが自動的に作成されます。 組織全体のチームは、10,000 人以下のユーザーを持つ組織に限定されます。 組織全体で最大 5 つのチームを持つことができます。 

## <a name="create-an-organization-wide-team"></a>組織全体のチームを作成する

組織全体のチームを作成するには、次の 2 つの方法があります。

- 既存のチームを組織全体のチームに変換します。 チーム名に移動し、[**その他のオプション** > ] [**チームの編集**] をクリックします。

- [新しいチームをゼロから作成](https://support.microsoft.com/office/174adf5f-846b-4780-b765-de1a0a737e2b) し、[ **組織全体** ] オプションを選択します。

    ![組織全体のチームを作成するための [組織全体] オプションのスクリーンショット。](media/create-org-wide-team.png "組織全体のチームを作成するための [組織全体] オプションのスクリーンショット。")

## <a name="types-of-users-in-an-organization-wide-team"></a>組織全体のチームのユーザーの種類

組織全体のチームが作成されると、すべてのグローバル管理者と Teams 管理者がチームの所有者として追加され、すべてのアクティブなユーザーがチーム メンバーとして追加されます。 チーム メンバーは組織全体のチームから離れることはできませんが、必要に応じてチーム所有者は手動でユーザーを追加または削除できます。 Teams が自動的にユーザーを追加または削除すると、通知が [全般] チャネルに送信されます。

ライセンス未付与のユーザーもチームに追加されます。 ライセンスのないユーザーが初めて Teams にサインインすると、Microsoft Teams Exploratory ライセンスが割り当てられます。 Exploratory ライセンスの詳細については、「[Microsoft Teams Exploratory ライセンスの管理](teams-exploratory.md)」をご覧ください。

以下の種類のアカウントは、組織全体のチームには追加されません。

- サインインがブロックされているアカウント
- ゲスト
- リソース アカウントやサービス アカウント (自動応答や通話キューに関連するアカウントなど)
- 会議室または備品用のアカウント
- 共有メール ボックスでサポートされているアカウント

> [!NOTE]
> Rooms that aren't a part of a room list, equipment, and resource accounts might be added or synced to the organization-wide team. Team owners can easily remove these accounts from the team.

## <a name="options-to-get-the-most-out-of-an-organization-wide-team"></a>組織全体のチームを最大限に活用するためのオプション

組織全体のチームを最大限に利用するために、チーム所有者に次のタスクを行うことをお勧めします。

### <a name="allow-only-team-owners-to-post-to-the-general-channel"></a>チームの所有者のみが一般チャネルに投稿できるようにする

チームの所有者だけが一般チャネルに投稿することで、チャネルのノイズを低減します。

1. チームに移動し、[全般] チャネルを見つけて、[..] を選択します **。その他のオプション** > **チャネルの管理**。
2. **[チャネル設定]** タブで、**[アクセス許可]** をクリックし、**[所有者のみがメッセージを投稿する]** を選択します。

### <a name="turn-off-team-and-team-name-mentions"></a>@team と @[チーム名] のメンションを無効にする

@メンションを減らして、組織全体がオーバー ロードしないようにします。

1. チームに移動し、[...] をクリックします **。その他のオプション** \> **チームの管理**。
2. [**設定]** タブ **@mentions**\>クリックし、[**メンバーを表示] オプションをオフにして、@teamまたは @[チーム名] をオン** にします。

### <a name="automatically-show-important-channels"></a>重要なチャネルを自動的に表示する

重要なチャネルを表示して、組織内の全ユーザーが特定の会話に参加できるようにします。 詳細については、「[チーム全体に対してチャネルをお気に入りに自動追加する](https://support.office.com/article/auto-favorite-channels-for-the-whole-team-a948272c-5aa5-429c-863c-4e1e1cd6b0f6)」を参照してください。

### <a name="set-up-channel-moderation"></a>チャネル モデレーションを設定する

チャネル モデレーションをセットアップし、特定のチームメンバーにモデレーター機能を付与することを検討してください。 (モデレーションが設定されると、チーム所有者に自動的にモデレーターの機能が付与されます。) モデレーターは以下のことを行うことができます。

- チャネルで新しいページを開始することができるユーザーをコントロールする
- モデレーターの追加と削除
- チーム メンバーが既存のチャネル メッセージに返信できるかどうかを制御します。
- ボットとコネクタがチャネル メッセージを送信できるようにするかどうかを制御します。

詳細については、「[Microsoft Teams でチャネル モデレーションをセットアップして管理する](manage-channel-moderation-in-teams.md)」を参照してください。

### <a name="remove-accounts-that-might-not-belong"></a>所属していない可能性のあるアカウントの削除

メンバーは組織全体のチームから抜けることはできませんが、チームの所有者は、所属していないアカウントを削除することにより、チームの参加者名簿を管理できます。 **組織全体のチームからユーザーを削除するには、必ず Teams を使用してください**。 Microsoft 365 管理センターや Outlook のグループなど、別の方法でユーザーを削除した場合、そのユーザーは組織全体のチームに再び追加される可能性があります。

## <a name="related-topics"></a>関連項目

[Microsoft Teams で組織全体のチームを作成する方法](https://www.youtube.com/watch?v=x3qGlwwCz_w)に関するビデオをご覧ください。
