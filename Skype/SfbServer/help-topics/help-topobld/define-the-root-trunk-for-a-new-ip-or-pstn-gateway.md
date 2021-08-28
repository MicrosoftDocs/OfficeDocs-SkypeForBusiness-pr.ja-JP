---
title: 新しい IP または PSTN ゲートウェイのルート トランクを定義する
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddPstnGatewayTrunkPage
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 22203d9a-4612-45c7-9375-69ae9964ce1e
description: IP または公衆交換電話網 (PSTN) 用のルート トランクを定義するには、次の項目を構成します。
ms.openlocfilehash: cf6cead37d229e2d276990434fa4b490d3eda472
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2021
ms.locfileid: "58605046"
---
# <a name="define-the-root-trunk-for-a-new-ip-or-pstn-gateway"></a>新しい IP または PSTN ゲートウェイのルート トランクの定義

IP または公衆交換電話網 (PSTN) 用のルート トランクを定義するには、次の項目を構成します。

- [**トランク名**]: トランクに関連付けられた完全修飾ドメイン名を定義します。

- [**IP/PSTN ゲートウェイのリッスン ポート**]: このトランクがリッスンするポートを定義します。

- [**SIP 転送プロトコル**]: トランク要件に基づき、リストから **TCP** または **TLS** のどちらかを選択します。

- **関連する仲介サーバー**: 展開で使用可能な仲介サーバーの一覧から選択します。

- **関連付けられた仲介サーバーの** ポート: 選択した仲介サーバーがリッスンしているポートを定義します。

## <a name="see-also"></a>関連項目

[2015 年にメディア バイパスを使用してトランクSkype for Business Serverする](../../deploy/deploy-enterprise-voice/configure-trunk-with-media-bypass.md)

[2015 年にメディア バイパスのないトランクSkype for Business Serverする](../../deploy/deploy-enterprise-voice/configure-trunk-without-media-bypass.md)

[SIP トランキングのサポート](/previous-versions/office/lync-server-2013/lync-server-2013-sip-trunking-support)