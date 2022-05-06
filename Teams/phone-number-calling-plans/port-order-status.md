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
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Calling Plans
description: 'Learn how to get the status of your port orders, and what the different actions you can take on them. '
ms.openlocfilehash: 3699a7ccbc2aa7a54c70c9cd99c9277f56ea40fc
ms.sourcegitcommit: bf350ea47032bd926e75a5433eadce3905e731ca
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/03/2021
ms.locfileid: "60733098"
---
# <a name="whats-the-status-of-your-port-orders"></a>番号移行注文の状況

ポート注文の状態を確認するには、Microsoft Teams管理センターの左側のナビゲーションで **、VoicePort** >  **の注文**>移動し、[**注文履歴**] をクリックします。 各ポートの順序の状態が [ **状態]** 列に一覧表示されます。 注文プロセスの詳細については [、ポート番号にかかる時間](../phone-number-calling-plans/port-order-overview.md#how-long-does-it-take-to-port-numbers) を確認してください。 

次の表に、ポートの順序の状態と、必要に応じて実行できるアクションを示します。

|**ステータス**|**注文を表示できますか?**|**注文を編集できますか?**|**注文をキャンセルできますか?**|**注文を削除できますか?**|**説明**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|**処理** <br/> |Yes  <br/> |いいえ  <br/> |Yes  <br/> |いいえ  <br/> |管理者が注文を作成し、Microsoft から受け取った。  <br/> |
|**通信事業者に問い合わせる** <br/> |Yes  <br/> |いいえ  <br/> |Yes  <br/> |いいえ  <br/> |この注文は Microsoft によって受け取られ、承認されており、失われた運送業者と協力して承認を受け取っています。  <br/> |
|**譲渡が承認済み** <br/> |Yes  <br/> |いいえ  <br/> |Yes  <br/> |いいえ  <br/> |この注文は、失われた運送業者によって受け入れられ、確定注文コミットメント (FOC) の日付が設定されています。  <br/> |
|**転送保留中** <br/> |Yes  <br/> |いいえ  <br/> |いいえ  <br/> |いいえ  <br/> |転送は 24 時間以内であるため、注文を編集または取り消す必要はありません。  <br/> |
|**エラー** <br/> |いいえ  <br/> |Yes  <br/> |Yes  <br/> |はい (現時点では、エラーが発生した場合はポートの順序を削除できません。 ポートの順序を再作成するか、 [TNS サービス デスク](../manage-phone-numbers-for-your-organization/contact-tns-service-desk.md)に問い合わせる必要があります。  <br/> |失った運送業者が注文を拒否しました。  <br/> |
|**完了** <br/> |Yes  <br/> |いいえ  <br/> |いいえ  <br/> |いいえ  <br/> |番号が正常に転送されました。  <br/> |
|**キャンセル** <br/> |いいえ  <br/> |Yes  <br/> |いいえ  <br/> |いいえ  <br/> |管理者が注文を取り消しました。  <br/> |

詳細な手順については、「[Teamsに電話番号を転送する」を](transfer-phone-numbers-to-teams.md)参照してください。

ヘルプが必要な場合、または電話番号を増やす必要がある場合は、 [TNS サービス デスク](../manage-phone-numbers-for-your-organization/contact-tns-service-desk.md)にお問い合わせください。

## <a name="related-topics"></a>関連項目

- [番号移行注文について](port-order-overview.md)
- [通話プランで使用されるさまざまな種類の電話番号](../different-kinds-of-phone-numbers-used-for-calling-plans.md)
- [組織の電話番号を管理する](../manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)
- [緊急通話の利用条件](../emergency-calling-terms-and-conditions.md)
- [緊急通話の免責事項ラベル](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)
