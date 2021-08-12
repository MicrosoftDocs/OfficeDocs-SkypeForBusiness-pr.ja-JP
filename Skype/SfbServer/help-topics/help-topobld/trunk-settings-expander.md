---
title: トランク設定の展開
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.TrunkSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3d00e8f4-e599-4094-a4a1-34fd6e8a5580
description: SIP トランクの設定を編集または変更するには、次の操作を行います。
ms.openlocfilehash: c29f7e62b047e06bfce20324a7edc8dc33d635ac416fb78ae31efaba63538141
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "54290615"
---
# <a name="trunk-settings-expander"></a>トランク設定エキスパンダー

SIP トランクの設定を編集または変更するには、次の操作を行います。

 [**トランク名**] は必須のエントリで、展開の中の SIP トランクを一意に特定します。

 [**PSTN ゲートウェイの関連付け**]: 展開で定義された既存の PSTN ゲートウェイを選択します。

 [**IP/PSTN ゲートウェイのリッスン ポート**]: ゲートウェイが要求をリッスンする TCP/IP ポートを示します。必要な値はゲートウェイのベンダーによって異なる場合がありますが、既定はポート 5067 です。

 [**SIP 転送プロトコル**]: 使用されるプロトコルは TCP または TLS です。TLS が既定です。ゲートウェイでサポートされるプロトコルについては、ゲートウェイ ベンダーのドキュメントを参照してください。既定は TLS で、ゲートウェイが TLS をサポートしている場合、既定がより安全性の高い選択肢と考えられます。

 **関連する仲介サーバー**: SIP トランクに関連付ける展開から既存の仲介サーバーを選択します。

> [!NOTE]
> ルート トランクのみを Lync Server 2010 または Lync Server 2013 仲介サーバーに関連付けできます。

 **関連付けられた仲介サーバー** ポート: 必須の値で、仲介サーバーがリッスンするように構成されている値に設定されます。

![トランク設定エキスパンダー](../../media/Trunk_Settings_Expander.jpg)

## <a name="see-also"></a>関連項目

[SIP トランキング展開チェックリスト](/previous-versions/office/lync-server-2013/lync-server-2013-sip-trunk-deployment-checklist)

[SIP トランキングのコンポーネントおよびトポロジ](/previous-versions/office/lync-server-2013/lync-server-2013-components-and-topologies-for-sip-trunking)