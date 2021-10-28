---
title: ポリシー Teamsを管理する
author: karlistites
ms.author: kastites
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: ''
search.appverid: ''
description: ポリシーをTeamsしてください。
audience: admin
ms.localizationpriority: medium
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: a08e48a37b90a7d8a99053d01a844c3451314e00
ms.sourcegitcommit: 3a8bec0445cee5cd776fb1991f093a0ec4351852
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/28/2021
ms.locfileid: "60605593"
---
# <a name="manage-teams-with-policies"></a>ポリシー Teamsを管理する

ポリシーは、管理の重要な部分Teams。 この記事では、ポリシーを使用して組織の利益を得る方法について説明します。

## <a name="what-you-use-policies-for"></a>ポリシーの使用

ポリシーは、メッセージング、会議、アプリケーションなど、さまざまな領域にわたって組織内の多くのタスクを実行するために使用されます。 ユーザーがチーム チャネルで会議をスケジュールできるようにしたり、ユーザーが送信されたメッセージを編集したり、ユーザーが Teams アプリ バーにアプリをピン留めできるかどうかを制御したりすることができます。

## <a name="how-to-assign-policies"></a>ポリシーを割り当てる方法

ポリシーは、組織が何を達成しようとしているかによって、さまざまな方法で割り当てることができます。 管理者センターで、割り当てをTeams表示できます。

![グループ ポリシーの割り当てのスクリーンショット。](media/group-policy-assignment.png)

ポリシーの割り当ての詳細については、こちらを参照 [してください](policy-assignment-overview.md)。

## <a name="how-to-manage-policies"></a>ポリシーを管理する方法

ポリシーは、管理センター Microsoft Teams PowerShell を使用[して管理されます](./teams-powershell-managing-teams.md#manage-policies-via-powershell)。

たとえば、アプリセットアップ ポリシーを使用すると、ユーザーがカスタム アプリをアップロードし、ユーザーに代わってアプリをインストールし、アプリを Teams アプリ バーにピン留めできます。 これらのポリシーは、管理センター Teams構成されます。

![アプリセットアップ ポリシーのスクリーンショット。](media/app-setup-policy.png)

さらに、会議ポリシーを使用して、トランスクリプション、クラウド録画、IP オーディオ/ビデオなどの Teams 会議の音声とビデオの設定を制御できます。

![会議ポリシーのスクリーンショット。](media/engineering-meeting-policy.png)

### <a name="teams-for-education"></a>教育機関用 Teams

また、新しいMicrosoft Teams for Education[ウィザードを](easy-policy-setup-edu.md)使用して、学習環境のポリシーを簡単に設定および管理することもできます。

![ポリシー ウィザードMicrosoft Teams for Educationスクリーンショット。](media/easy-policy-setup-quick-setup.png)

## <a name="types-of-policies"></a>ポリシーの種類

次のポリシーは、次のポリシーを使用Microsoft Teams。

ポリシーの種類 | 説明
------------|------------
[ポリシー パッケージ](manage-policy-packages.md) | Microsoft Teams のポリシー パッケージは、組織内で同様のロールを持つユーザーに割り当て可能な定義済みのポリシーと設定のコレクションです。
[会議ポリシー](meeting-policies-overview.md) | 会議ポリシーは、組織内のユーザーがスケジュールした会議に対して会議参加者が使用できる機能を制御するために使用されます。 会議ポリシーには、次のトピックが含まれます。<br> - オーディオポリシーとビデオ ポリシー<br> - コンテンツと画面共有ポリシー<br> - 参加者、ゲスト、アクセス ポリシー<br> - 一般的なポリシー
[音声と通話のポリシー](voice-and-calling-policies.md)| 音声および通話ポリシーは、緊急通話、通話ルーティング、発信者番号などのチームを通じてこれらの設定を管理します。
[アプリ ポリシー](app-policies.md)| アプリ ポリシーは、アプリケーションを管理するために使用Microsoft Teams。 管理者は、ユーザーがインストールできるアプリを許可またはブロックしたり、ユーザーの Teams アプリ バーにアプリケーションをピン留めしたり、ユーザーに代わってアプリケーションをインストールすることができます。
[メッセージング ポリシー](messaging-policies-in-teams.md)| メッセージング ポリシーは、チャットとチャネル機能の可用性を制御します。

## <a name="related-topics"></a>関連トピック

* [ポリシーの割り当Teams - 使用を開始する](policy-assignment-overview.md)
* [Microsoft Teams でフィードバック ポリシーを管理する](manage-feedback-policies-in-teams.md)
* [Microsoft Teams でチーム ポリシーを管理する](teams-policies.md)
* [Microsoft Teams でのライブ イベントのセットアップ](teams-live-events/set-up-for-teams-live-events.md)
* [Microsoft Teams for Educationポリシーとポリシー パッケージ](policy-packages-edu.md)