---
title: ポリシーを使用してTeamsを管理する
author: mkbond007
ms.author: mabond
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: ''
search.appverid: ''
description: Teams ポリシーについて説明します。
audience: admin
ms.localizationpriority: medium
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 932fed6b2a735aabee0511b6f1c6b863e01e403c
ms.sourcegitcommit: 9532eb79310cd653010565607fa394f2b8dd182d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/23/2022
ms.locfileid: "65646486"
---
# <a name="manage-teams-with-policies"></a>ポリシーを使用してTeamsを管理する

ポリシーは、Teamsを管理する上で重要な部分です。 この記事を使用して、ポリシーを使用して組織に利益をもたらす方法を説明します。

## <a name="what-you-use-policies-for"></a>ポリシーを使用する対象

ポリシーは、メッセージング、会議、アプリケーションなど、さまざまな分野で組織内の多くのタスクを実行するために使用されます。 ユーザーがチーム チャネルで会議をスケジュールできるようにする、送信メッセージを編集できるようにする、ユーザーがアプリを Teams アプリ バーにピン留めできるかどうかを制御するなど、できることがいくつかあります。

## <a name="how-to-assign-policies"></a>ポリシーを割り当てる方法

ポリシーは、組織が達成しようとしている内容に応じて、いくつかの異なる方法で割り当てることができます。 Teams管理センターで割り当てを作成して表示できます。

![グループ ポリシーの割り当てのスクリーンショット。](media/group-policy-assignment.png)

ポリシーの割り当ての詳細については、 [こちらを参照してください](policy-assignment-overview.md)。

## <a name="how-to-manage-policies"></a>ポリシーを管理する方法

ポリシーは、Microsoft Teams管理センターまたは [PowerShell を使用して](./teams-powershell-managing-teams.md#manage-policies-via-powershell)管理されます。

たとえば、アプリ設定ポリシーを使用すると、ユーザーがカスタム アプリをアップロードしたり、ユーザーに代わってアプリをインストールしたり、アプリをTeams アプリ バーにピン留めしたりできます。 これらのポリシーは、Teams管理センターで構成されます。

![アプリのセットアップ ポリシーのスクリーンショット。](media/app-setup-policy.png)

さらに、会議ポリシーを使用して、文字起こし、クラウドレコーディング、IP オーディオ/ビデオなどのTeams会議のオーディオとビデオの設定を制御できます。

![会議ポリシーのスクリーンショット。](media/engineering-meeting-policy.png)

### <a name="teams-for-education"></a>教育機関用 Teams

[Microsoft Teams for Education ポリシー ウィザード](easy-policy-setup-edu.md)を使用して、学習環境のポリシーを簡単に設定および管理することもできます。

![Microsoft Teams for Education ポリシー ウィザードのスクリーンショット。](media/easy-policy-setup-quick-setup.png)

## <a name="types-of-policies"></a>ポリシーの種類

次のポリシーは、Microsoft Teamsで管理できます。

ポリシーの種類 | 説明
------------|------------
[ポリシー パッケージ](manage-policy-packages.md) | Microsoft Teamsのポリシー パッケージは、組織内で同様のロールを持つユーザーに割り当てることができる定義済みのポリシーと設定のコレクションです。
[会議ポリシー](meeting-policies-overview.md) | 会議ポリシーは、組織内のユーザーがスケジュールした会議の会議参加者が利用できる機能を制御するために使用されます。 会議ポリシーには、次のトピックが含まれます。<br> - オーディオポリシーとビデオ ポリシー<br> - コンテンツと画面共有ポリシー<br> - 参加者、ゲスト、アクセス ポリシー<br> - 一般的なポリシー
[音声ポリシーと通話ポリシー](voice-and-calling-policies.md)| 音声ポリシーと通話ポリシーは、緊急通話、通話ルーティング、発信者 ID などのチームを通じてこれらの設定を管理します。
[アプリのポリシー](app-policies.md)| アプリ ポリシーは、Microsoft Teams内のアプリケーションを制御するために使用されます。 管理者は、ユーザーがインストールできるアプリを許可またはブロックしたり、ユーザーのTeams アプリ バーにアプリケーションをピン留めしたり、ユーザーに代わってアプリケーションをインストールしたりできます。
[メッセージング ポリシー](messaging-policies-in-teams.md)| メッセージング ポリシーは、チャットとチャネル機能の可用性を制御します。

## <a name="related-topics"></a>関連項目

* [Teamsでポリシーを割り当てる - 作業の開始](policy-assignment-overview.md)
* [Microsoft Teams でフィードバック ポリシーを管理する](manage-feedback-policies-in-teams.md)
* [Microsoft Teams でチーム ポリシーを管理する](teams-policies.md)
* [Microsoft Teams でのライブ イベントのセットアップ](teams-live-events/set-up-for-teams-live-events.md)
* [Microsoft Teams for Education ポリシーとポリシー パッケージ](policy-packages-edu.md)