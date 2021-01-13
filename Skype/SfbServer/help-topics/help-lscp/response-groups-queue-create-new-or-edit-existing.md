---
title: 応答グループ キューの作成、または既存の編集
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/24/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.RgsQueueEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: cbdde536-8668-4a08-9862-8615e8691fd7
description: 応答グループ キューは、エージェントが通話に応答するまで、応答グループへの通話を保持します。
ms.openlocfilehash: cfe2d212f90f8dcdf83b8f827ebf470245ce87fa
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49829317"
---
# <a name="response-groups-queue-create-new-or-edit-existing"></a>応答グループのキュー: 新規作成または現在の形式のままで編集

応答グループ キューは、エージェントが応答するまで応答グループへの通話を保持します。

## <a name="ui-reference"></a>UI リファレンス

次の一覧に、このページのフィールドを示します。

- **名前** 各キューには名前が必要です。 キューのわかりやすい名前を入力します。

- **説明** このフィールドは省略可能です。 キューに関する追加の詳細を提供するために使用します。

- **グループ** キューに割り当てるエージェント グループを選択します。 [ **選択] を** クリックして、エージェント グループをリストに追加します。 [ **削除]** をクリックして、選択したエージェント グループを一覧から削除します。

    上下の矢印を使用すると、選択したエージェント グループが一覧内で上下に移動します。 エージェント グループの順序は、Skype for Business Server が使用可能なエージェントを検索する順序に影響します。 つまり、リスト内の最初のグループが最初に検索され、使用可能なエージェントが検索され、次に 2 番目のグループが検索されます。

- **キューのタイム アウトを有効にする** エージェントが通話に応答するまで発信者が保留を待機する最大時間を指定するには、このチェック ボックスをオンにします。 このオプションを選択する場合は、次の項目も指定する必要があります。

  - **タイム アウト期間 (秒)** エージェントが通話に応答するまで発信者が待機できる最大待機時間を選択または入力します。

  - **通話アクション** 通話がタイム アウトした場合に発生するアクションを選択します。次の項目を選択できます。

  - **Disconnect**

  - **ボイス メールに転送する** このオプションを選択した場合は **、SIP** アドレスにボイス メール アドレスを sip: の形式で入力します (たとえば <username> @ <domainname> 、sip:bob@contoso.com)。

  - **電話番号に転送する** このオプションを選択した場合 **、SIP** アドレスに電話番号を sip: の形式で入力します (たとえば <number> @ <domainname> 、sip:+14255550121@contoso.com)。

  - **SIP アドレスに転送する** 通話を別のユーザーに転送するには、このオプションを選択します。 SIP **アドレスに、** ユーザーの URI を sip: の形式で入力します <username> @ <domainname> 。

  - **別のキューに転送する** このオプションを選択した場合は、通話のタイム アウト時に通話を受信するキューを参照します。

- **キューオーバーフローを有効にする** キューが保持できる通話の最大数を指定するには、このチェック ボックスをオンにします。 このオプションを選択する場合は、次の項目も指定する必要があります。

  - **最大通話数** キューが保持できる通話の最大数を選択または入力します。

  - **通話を転送する** キューのオーバーフローしきい値に達した場合にアクションを実行する通話を選択します。

  - **通話アクション** キューのオーバーフローしきい値に達した場合に発生するアクションを選択します。 次のどちらかを選択できます。

  - **Disconnect**

  - **ボイス メールに転送する** このオプションを選択した場合は **、SIP** アドレスにボイス メール アドレスを sip: の形式で入力します (たとえば <username> @ <domainname> 、sip:bob@contoso.com)。

  - **電話番号に転送する** このオプションを選択した場合 **、SIP** アドレスに電話番号を sip: の形式で入力します (たとえば <number> @ <domainname> 、sip:+14255550121@contoso.com)。

  - **SIP アドレスに転送** 通話を別のユーザーに転送するには、このオプションを選択します。 SIP **アドレスに、** ユーザーの URI を sip: の形式で入力します <username> @ <domainname> 。

  - **別のキューに転送する** このオプションを選択した場合は、キューオーバーフローのしきい値に達した場合に呼び出しを受信するキューを参照します。

応答グループの機能の詳細については、「計画」のドキュメントの [「Plan for the Response Group application in Skype for Business Server 2015」](../../plan-your-deployment/enterprise-voice-solution/response-group.md) を参照してください。 キューの使用の詳細については、「操作」のドキュメントの「[Managing Response Group Queues](https://technet.microsoft.com/library/1e91720c-ab67-4dfb-b30c-0ef2a8012310.aspx)」を参照してください。


