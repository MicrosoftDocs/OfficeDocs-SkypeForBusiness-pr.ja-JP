---
title: 番号移行注文の状況
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Calling Plans
description: 'Learn how to get the status of your port orders, and what the different actions you can take on them. '
ms.openlocfilehash: 8290ffba7be56f3ede0e275c801110f8c9d9539e
ms.sourcegitcommit: 693205da865111380b55c514955ac264031eb2fd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/02/2020
ms.locfileid: "44205688"
---
# <a name="whats-the-status-of-your-port-orders"></a>番号移行注文の状況

ポート注文の状態を表示するには、Microsoft Teams 管理センターの左側のナビゲーションで、[> **Voice** Port orders] に移動し、[注文履歴]  >  **をクリックします**。 各ポート注文の状態は、[状態] 列に **一覧表示** されます。 注文 [プロセスの詳細については、ポート番号](../phone-number-calling-plans/port-order-overview.md#how-long-does-it-take-to-port-numbers) にかかる時間を確認してください。 

次の表に、ポート注文の状態と、必要に応じて実行できるアクションを示します。

|**状態**|**注文を表示できますか?**|**注文を編集できますか?**|**注文をキャンセルできますか?**|**注文を削除できますか?**|**説明**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|**処理** <br/> |はい  <br/> |いいえ  <br/> |はい  <br/> |いいえ  <br/> |管理者が注文を作成し、Microsoft が注文を受け取った。  <br/> |
|**通信業者に問い合わせ** <br/> |はい  <br/> |いいえ  <br/> |はい  <br/> |いいえ  <br/> |注文は Microsoft によって受け取り、承認され、Microsoft は負けている運送業者と一緒に承認を受け取る作業を行います。  <br/> |
|**譲渡が承認されました** <br/> |はい  <br/> |いいえ  <br/> |はい  <br/> |いいえ  <br/> |この注文は、負けている運送業者によって受け入れ、会社注文コミットメント (FOC) の日付が設定されています。  <br/> |
|**転送保留中** <br/> |はい  <br/> |いいえ  <br/> |いいえ  <br/> |いいえ  <br/> |譲渡から 24 時間以内なので、注文の編集や取り消しは行えなくなりました。  <br/> |
|**エラー** <br/> |いいえ  <br/> |はい  <br/> |はい  <br/> |はい (現時点では、エラーが発生した場合はポート注文を削除できます)。 ポート注文を再作成するか、PSTN サービス デスクのヘルプ に問い [合わせる必要があります](../manage-phone-numbers-for-your-organization/contact-pstn-service-desk.md)。  <br/> |負けた運送業者は注文を拒否しました。  <br/> |
|**完了** <br/> |はい  <br/> |いいえ  <br/> |いいえ  <br/> |いいえ  <br/> |番号は正常に転送されました。  <br/> |
|**Cancelled** <br/> |いいえ  <br/> |はい  <br/> |いいえ  <br/> |いいえ  <br/> |管理者が注文をキャンセルしました。  <br/> |

詳しい手順については、「電話番号を電話番号に転送する」を[参照Teams。](transfer-phone-numbers-to-teams.md)

サポートが必要な場合、または電話番号を追加する必要がある場合は、PSTN サービス デスク にお問 [い合わせください](../manage-phone-numbers-for-your-organization/contact-pstn-service-desk.md)。

## <a name="related-topics"></a>関連トピック

- [番号移行注文について](port-order-overview.md)
- [通話プランで使用されるさまざまな種類の電話番号](../different-kinds-of-phone-numbers-used-for-calling-plans.md)
- [組織の電話番号を管理する](../manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)
- [緊急通話の利用条件](../emergency-calling-terms-and-conditions.md)
- [緊急通話の免責事項ラベル](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)
