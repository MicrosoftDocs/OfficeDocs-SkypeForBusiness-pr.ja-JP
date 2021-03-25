---
title: エージェントの選択
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.RgsSelAgent
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: b5cf912b-8273-4c2c-a1e5-f25530b264d0
ROBOTS: NOINDEX, NOFOLLOW
description: エージェントは、応答グループの呼び出しに応答するために指定されたユーザーです。 応答グループには、そのグループへの呼び出しを受信できるエージェントを示すエージェント グループが割り当てられている必要があります。 エージェント グループを作成する方法の 1 つは、適格なユーザーを選択してカスタム グループを定義することです。 対象となるユーザーは、Skype for Business Server およびビジネス サーバーエンタープライズ VoIP。
ms.openlocfilehash: 399ad65a2fe232d217ce4891061aeed8284277b9
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51118786"
---
# <a name="select-agents"></a>エージェントの選択

エージェントは、応答グループの呼び出しに応答するために指定されたユーザーです。 応答グループには、そのグループへの呼び出しを受信できるエージェントを示すエージェント グループが割り当てられている必要があります。 エージェント グループを作成する方法の 1 つは、適格なユーザーを選択してカスタム グループを定義することです。 対象となるユーザーは、Skype for Business Server およびビジネス サーバーエンタープライズ VoIP。

[**エージェントの選択**] ダイアログ ボックスを使用して、エージェント グループに追加するユーザーを選択します。

## <a name="ui-reference"></a>UI リファレンス

[**エージェントの選択**] ダイアログ ボックスには次のコントロールがあります。

- **検索** ユーザーの SIP アドレスまたは表示名を検索します。 アドレスまたは名前のすべてまたは一部を入力します。 検索ボックスを空のままにすると、Skype for Business Server および Skype サーバーに対して有効になっているすべてのユーザーが表示エンタープライズ VoIP。

- **表示する最大ユーザー数** 表示される結果の数を変更します。 多くの結果が予想される場合は、このカウンターを使用して検索を制限します。

[**エージェントの選択**] ダイアログ ボックスには次のフィールドがあります。

- **エージェント** 検索によって返されるユーザー名を表示します。

- **SIP アドレス** 検索によって返されるユーザー SIP アドレスを表示します。

- **テレフォニー** ユーザーに対して定義された **テレフォニー** フィールドの値を表示します。

- **有効** ユーザーに対して定義されている **[Lync Server の有効** ] フィールドの値を表示します。

エージェント グループの使用の詳細については、「操作」のドキュメントの「[Managing Agent Groups](/previous-versions/office/lync-server-2013/lync-server-2013-managing-response-group-agent-groups)」を参照してください。