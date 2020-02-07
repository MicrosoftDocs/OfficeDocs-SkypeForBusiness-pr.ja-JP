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
ms.openlocfilehash: 2c141bab63990c39ef7fd08837eb4ad99d72682d
ms.sourcegitcommit: bfa5b8db4e42e0480542d61fe05716c52016873c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41827955"
---
# <a name="whats-the-status-of-your-port-orders"></a>番号移行注文の状況

ポート注文の状態を表示するには、Microsoft Teams 管理センターの左側のナビゲーションで > [**音声** > **ポートの注文**] に移動し、[**注文履歴**] をクリックします。 各ポート注文の状態は、[**状態**」列に表示されます。

次の表は、ポート注文の状態と、必要に応じて実行できる操作を示しています。

|**状態**|**注文を表示できますか?**|**注文を編集できますか?**|**注文をキャンセルできますか?**|**注文を削除できますか?**|**説明**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|**処理** <br/> |はい  <br/> |いいえ  <br/> |はい  <br/> |いいえ  <br/> |管理者が注文を作成し、Microsoft によって受信されました。  <br/> |
|**電話会社に連絡中** <br/> |はい  <br/> |いいえ  <br/> |はい  <br/> |いいえ  <br/> |注文は Microsoft によって受領され承認されており、ご利用の承認を得るために、紛失しているキャリアを使用しています。  <br/> |
|**承認済みの転送** <br/> |はい  <br/> |確定注文の確約 (= c)  <br/> |はい  <br/> |いいえ  <br/> |この注文は、紛失しているキャリアによって承認されたため、ドライブ c の日付が設定されています。  <br/> |
|**転送待ち** <br/> |はい  <br/> |なし  <br/> |なし  <br/> |いいえ  <br/> |移動は24時間以内であるため、注文を編集またはキャンセルすることはできません。  <br/> |
|**エラー** <br/> |いいえ  <br/> |はい  <br/> |Yes  <br/> |はい (現時点では、エラーが発生した場合は、ポートの順序を削除できません。 ポート注文を再作成するか、 [PSTN サービスデスクのヘルプ](../manage-phone-numbers-for-your-organization/contact-pstn-service-desk.md)に問い合わせる必要があります。  <br/> |紛失したキャリアが注文を却下しました。  <br/> |
|**時点** <br/> |はい  <br/> |なし  <br/> |なし  <br/> |いいえ  <br/> |番号は正常に転送されました。  <br/> |
|**閉じ** <br/> |いいえ  <br/> |はい  <br/> |なし  <br/> |いいえ  <br/> |管理者が注文をキャンセルしました。  <br/> |

詳細な手順については、「[チームに電話番号を転送する](transfer-phone-numbers-to-teams.md)」を参照してください。

ヘルプが必要な場合や、その他の電話番号を取得する必要がある場合は、 [PSTN サービスデスクのヘルプを参照](../manage-phone-numbers-for-your-organization/contact-pstn-service-desk.md)してください。

## <a name="related-topics"></a>関連トピック

- [番号移行注文について](port-order-overview.md)
- [通話プランで使用されるさまざまな種類の電話番号](../different-kinds-of-phone-numbers-used-for-calling-plans.md)
- [組織の電話番号を管理する](../manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)
- [緊急通話の利用条件](../emergency-calling-terms-and-conditions.md)
- [緊急通話の免責事項ラベル](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)
