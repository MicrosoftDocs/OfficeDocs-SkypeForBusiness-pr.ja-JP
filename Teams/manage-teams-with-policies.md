---
title: ポリシーを使用して Teams を管理する
author: karlistites
ms.author: kastites
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: ''
search.appverid: ''
description: ''
audience: admin
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 368e71820100ba8cfccb28eef63864f47cd8ce85
ms.sourcegitcommit: 6f7b91f573e2a034f8c5474be2c5cb2971f4b5ab
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/04/2021
ms.locfileid: "50421302"
---
# <a name="manage-teams-with-policies"></a>ポリシーを使用して Teams を管理する

ポリシーは、Teams 管理の重要な部分です。 この記事では、ポリシーを使用して組織に利益をもたらす方法について説明します。

## <a name="what-you-use-policies-for"></a>ポリシーの使用

ポリシーは、メッセージング、会議、アプリケーションなど、さまざまな分野にわたって組織内の多くのタスクを実行するために使用されます。 ユーザーがチーム チャネルで会議をスケジュールできるようにしたり、ユーザーが送信したメッセージを編集したり、ユーザーがアプリを Teams アプリ バーにピン留めできるかどうかを制御したりすることもできます。

## <a name="how-to-assign-policies"></a>ポリシーを割り当てる方法

組織が達成しようとしている内容に応じて、いくつかの方法でポリシーを割り当てることができます。 Teams 管理センターで課題を作成および表示できます。

![グループ ポリシーの割り当てのスクリーンショット。](media/group-policy-assignment.png)

ポリシーの割り当てに関する詳細については、こちらを参照 [してください](assign-policies.md)。

## <a name="how-to-manage-policies"></a>ポリシーを管理する方法

ポリシーは、Microsoft Teams 管理センターまたは [PowerShell を使用して管理されます](https://docs.microsoft.com/microsoftteams/teams-powershell-managing-teams#manage-policies-via-powershell)。

たとえば、アプリセットアップ ポリシーを使用すると、ユーザーがカスタム アプリをアップロードし、ユーザーの代わりにアプリをインストールし、アプリを Teams アプリ バーにピン留めすることができます。 これらのポリシーは、Teams 管理センターで構成されます。

![アプリセットアップ ポリシーのスクリーンショット。](media/app-setup-policy.png)

さらに、会議ポリシーを使用して、議事書き、クラウドレコーディング、IP オーディオ/ビデオなどの Teams 会議の音声とビデオの設定を制御できます。

![会議ポリシーのスクリーンショット。](media/engineering-meeting-policy.png)

### <a name="teams-for-education"></a>教育機関用 Teams

[Teams for Education](easy-policy-setup-edu.md)ポリシー ウィザードを使用して、学習環境のポリシーを簡単に設定および管理することもできます。

![Teams for Education ポリシー ウィザードのスクリーンショット。](media/easy-policy-setup-quick-setup.png)

## <a name="types-of-policies"></a>ポリシーの種類

次のポリシーは、Microsoft Teams で管理できます。

ポリシーの種類 | 説明
------------|------------
[ポリシー パッケージ](manage-policy-packages.md) | Microsoft Teams のポリシー パッケージは、組織内で同様の役割を持つユーザーに割り当て可能な定義済みのポリシーと設定のコレクションです。
[会議ポリシー](meeting-policies-in-teams.md) | 会議ポリシーは、組織内のユーザーがスケジュールした会議の会議参加者が使用できる機能を制御するために使用されます。 会議ポリシーには、次のトピックが含まれます。<br> - オーディオ ポリシーとビデオ ポリシー<br> - コンテンツと画面の共有ポリシー<br> - 参加者、ゲスト、アクセス ポリシー<br> - 一般的なポリシー
[音声と通話のポリシー](voice-and-calling-policies.md)| 音声および通話ポリシーは、緊急通話、通話ルーティング、発信者番号などのチームを通じてこれらの設定を管理します。
[アプリ ポリシー](app-policies.md)| アプリ ポリシーは、Microsoft Teams でアプリケーションを制御するために使用されます。 管理者は、ユーザーがインストールできるアプリを許可またはブロックしたり、ユーザーの Teams アプリ バーにアプリケーションをピン留めしたり、ユーザーの代わりにアプリケーションをインストールすることができます。
[メッセージング ポリシー](messaging-policies-in-teams.md)| メッセージング ポリシーは、チャットとチャネル機能の可用性を制御します。

## <a name="related-topics"></a>関連トピック

* [Microsoft Teams でフィードバック ポリシーを管理する](manage-feedback-policies-in-teams.md)
* [Microsoft Teams でチーム ポリシーを管理する](teams-policies.md)
* [Microsoft Teams でのライブ イベントのセットアップ](teams-live-events/set-up-for-teams-live-events.md)
* [Teams for Education ポリシーとポリシー パッケージ](policy-packages-edu.md)
