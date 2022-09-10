---
title: ポリシーを使用して Teams を管理する
author: mkbond007
ms.author: mabond
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: ''
search.appverid: ''
description: Teams ポリシーを検討する。
audience: admin
ms.localizationpriority: medium
appliesto:
- Microsoft Teams
ms.collection:
- M365-collaboration
ms.openlocfilehash: e369403e17136aaec6341e46b4851d18fb778a89
ms.sourcegitcommit: 5abfb6f1abe10b6d32cf6eb97a890cf3138ed0e6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2022
ms.locfileid: "67641868"
---
# <a name="manage-teams-with-policies"></a>ポリシーを使用して Teams を管理する

ポリシーは、Teams を管理する上で重要な部分です。 この記事を使用して、ポリシーを使用して組織に利益をもたらす方法を説明します。

## <a name="what-you-use-policies-for"></a>ポリシーを使用する対象

ポリシーは、メッセージング、会議、アプリケーションなど、さまざまな分野で組織内の多くのタスクを実行するために使用されます。 実行できる操作には、ユーザーがチーム チャネルで会議をスケジュールできるようにする、送信メッセージを編集できるようにする、ユーザーが Teams アプリ バーにアプリをピン留めできるかどうかを制御するなどがあります。

## <a name="how-to-assign-policies"></a>ポリシーを割り当てる方法

ポリシーは、組織が達成しようとしている内容に応じて、いくつかの異なる方法で割り当てることができます。 Teams 管理センターで割り当てを作成して表示できます。

:::image type="content" source="media/group-policy-assignment.png" alt-text="Teams グループ ポリシーの割り当てのスクリーンショット。" lightbox="media/group-policy-assignment.png":::

ポリシーの割り当ての詳細については、 [こちらを参照してください](policy-assignment-overview.md)。

> [!NOTE]
> ポリシーの割り当てを解除するには、ポリシーに直接割り当てられているすべてのユーザーの割り当てを一括で削除できます。 詳細については、「ポリシーの [割り当てを一括で割り当て解除する」](assign-policies-users-and-groups.md#unassign-policies-in-bulk)を参照してください。

## <a name="how-to-manage-policies"></a>ポリシーを管理する方法

ポリシーは、Microsoft Teams 管理センターまたは [PowerShell を使用して](./teams-powershell-managing-teams.md#manage-policies-via-powershell)管理されます。

たとえば、アプリ設定ポリシーを使用すると、ユーザーがカスタム アプリをアップロードしたり、ユーザーに代わってアプリをインストールしたり、Teams アプリ バーにアプリをピン留めしたりできます。 これらのポリシーは、Teams 管理センターで構成されます。

:::image type="content" source="media/app-setup-policy.png" alt-text="アプリのセットアップ ポリシーのスクリーンショット。" lightbox="media/app-setup-policy.png":::

さらに、会議ポリシーを使用して、文字起こし、クラウドレコーディング、IP オーディオ/ビデオなどの Teams 会議のオーディオとビデオの設定を制御できます。

:::image type="content" source="media/engineering-meeting-policy.png" alt-text="会議ポリシーのスクリーンショット。" lightbox="media/engineering-meeting-policy.png":::

### <a name="teams-for-education"></a>教育機関用 Teams

[Microsoft Teams for Education ポリシー ウィザード](easy-policy-setup-edu.md)を使用して、学習環境のポリシーを簡単に設定および管理することもできます。

:::image type="content" source="media/easy-policy-setup-quick-setup.png" alt-text="Microsoft Teams for Education ポリシー ウィザードのスクリーンショット。" lightbox="media/easy-policy-setup-quick-setup.png":::

## <a name="types-of-policies"></a>ポリシーの種類

次のポリシーは、Microsoft Teams で管理できます。

ポリシーの種類 | 説明
------------|------------
[ポリシー パッケージ](manage-policy-packages.md) | Microsoft Teams のポリシー パッケージは、組織内で同様のロールを持つユーザーに割り当てることができる定義済みのポリシーと設定のコレクションです。
[会議ポリシー](meeting-policies-overview.md) | 会議ポリシーは、組織内のユーザーがスケジュールした会議の会議参加者が利用できる機能を制御するために使用されます。 会議ポリシーには、次のトピックが含まれます。<br> - オーディオポリシーとビデオ ポリシー<br> - コンテンツと画面共有ポリシー<br> - 参加者、ゲスト、アクセス ポリシー<br> - 一般的なポリシー
[音声ポリシーと通話ポリシー](voice-and-calling-policies.md)| 音声ポリシーと通話ポリシーは、緊急通話、通話ルーティング、発信者 ID などのチームを通じてこれらの設定を管理します。
[アプリのポリシー](app-policies.md)| アプリ ポリシーは、Microsoft Teams のアプリケーションを制御するために使用されます。 管理者は、ユーザーがインストールできるアプリを許可またはブロックし、ユーザーの Teams アプリ バーにアプリケーションをピン留めし、ユーザーに代わってアプリケーションをインストールできます。
[メッセージング ポリシー](messaging-policies-in-teams.md)| メッセージング ポリシーは、チャットとチャネル機能の可用性を制御します。

## <a name="related-topics"></a>関連項目

* [Teams でポリシーを割り当てる - 作業の開始](policy-assignment-overview.md)
* [Microsoft Teams でフィードバック ポリシーを管理する](manage-feedback-policies-in-teams.md)
* [Microsoft Teams でチーム ポリシーを管理する](teams-policies.md)
* [Microsoft Teams でのライブ イベントのセットアップ](teams-live-events/set-up-for-teams-live-events.md)
* [Microsoft Teams for Education ポリシーとポリシー パッケージ](policy-packages-edu.md)
