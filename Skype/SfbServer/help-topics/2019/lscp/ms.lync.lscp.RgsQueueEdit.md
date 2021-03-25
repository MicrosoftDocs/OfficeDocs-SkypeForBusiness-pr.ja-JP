---
title: 応答グループ キュー の作成 新規または既存の編集
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.RgsQueueEdit
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: cbdde536-8668-4a08-9862-8615e8691fd7
ROBOTS: NOINDEX, NOFOLLOW
description: 応答グループ キューは、エージェントが通話に応答するまで、応答グループへの呼び出しを保持します。
ms.openlocfilehash: ee99ac8cb4f3ea9c2f0e1804914eaf30c909a2b0
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51118806"
---
# <a name="response-groups-queue-create-new-or-edit-existing"></a>応答グループのキュー: 新規作成または現在の形式のままで編集

応答グループ キューは、エージェントが通話に応答するまで、応答グループへの呼び出しを保持します。

## <a name="ui-reference"></a>UI リファレンス

次の一覧に、このページのフィールドを示します。

- **名前** 各キューには名前が必要です。 キューのわかりやすい名前を入力します。

- **説明** このフィールドはオプションです。 キューに関する追加の詳細を提供するために使用します。

- **グループ** キューに割り当てるエージェント グループを選択します。 [選択 **] を** クリックして、エージェント グループをリストに追加します。 [ **削除] を** クリックして、選択したエージェント グループを一覧から削除します。

    上下の矢印は、選択したエージェント グループをリスト内で上下に移動します。 エージェント グループの順序は、Skype for Business Server が使用可能なエージェントを検索する順序に影響します。 つまり、リスト内の最初のグループが最初に検索され、使用可能なエージェントが検索され、次に 2 番目のグループが検索されます。

- **キューのタイム アウトを有効にする** このチェック ボックスをオンにすると、エージェントが通話に応答するまで発信者が待機するまでの最大期間を指定できます。 このオプションを選択する場合は、次の項目も指定する必要があります。

  - **タイム アウト期間 (秒)** エージェントが通話に応答するまで発信者が待機できる最大待機時間を選択または入力します。

  - **通話アクション** 通話がアウトした場合に発生するアクションを選択します。選択項目は次のとおりです。

  - **Disconnect**

  - **ボイス メールへの転送** このオプションを選択した場合は **、[SIP アドレス**] に SIP 形式のボイス メール アドレスを入力します <username> (たとえば @ <domainname> 、sip:bob@contoso.com)。

  - **電話番号に転送する** このオプションを選択した場合は **、SIP アドレスに** SIP の形式で電話番号を入力します <number> (たとえば @ <domainname> 、sip:+14255550121@contoso.com)。

  - **SIP アドレスへの転送** 通話を別のユーザーに転送するには、このオプションを選択します。 **[SIP アドレス]** に、SIP 形式でユーザーの URI を入力します <username> @ <domainname> 。

  - **別のキューに転送する** このオプションを選択した場合は、通話が時間切れ時に呼び出しを受信するキューを参照します。

- **キュー オーバーフローを有効にする** キューが保持できる呼び出しの最大数を指定するには、このチェック ボックスをオンにします。 このオプションを選択する場合は、次の項目も指定する必要があります。

  - **呼び出しの最大数** キューが保持できる呼び出しの最大数を選択または入力します。

  - **通話を転送する** キュー オーバーフローのしきい値が満たされた場合にアクションを実行する呼び出しを選択します。

  - **通話アクション** キュー オーバーフローのしきい値が満たされた場合に発生するアクションを選択します。 次のどちらかを選択できます。

  - **Disconnect**

  - **ボイス メールへの転送** このオプションを選択した場合は **、[SIP アドレス**] に SIP 形式のボイス メール アドレスを入力します <username> (たとえば @ <domainname> 、sip:bob@contoso.com)。

  - **電話番号に転送する** このオプションを選択した場合は **、SIP アドレスに** SIP の形式で電話番号を入力します <number> (たとえば @ <domainname> 、sip:+14255550121@contoso.com)。

  - **SIP アドレスへの転送** 通話を別のユーザーに転送するには、このオプションを選択します。 **[SIP アドレス]** に、SIP 形式でユーザーの URI を入力します <username> @ <domainname> 。

  - **別のキューに転送する** このオプションを選択した場合は、キュー オーバーフローしきい値が満たされた場合に呼び出しを受信するキューを参照します。

応答グループの機能の詳細については、「計画」のドキュメントの「Plan for the [Response Group application in Skype for Business Server」](../../../plan-your-deployment/enterprise-voice-solution/response-group.md) を参照してください。 キューの使用の詳細については、「操作」のドキュメントの「[Managing Response Group Queues](/previous-versions/office/lync-server-2013/lync-server-2013-managing-response-group-queues)」を参照してください。