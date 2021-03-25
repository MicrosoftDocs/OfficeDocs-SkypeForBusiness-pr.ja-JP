---
title: 新しい IP または PSTN ゲートウェイのルート トランクを定義する
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddPstnGatewayTrunkPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 22203d9a-4612-45c7-9375-69ae9964ce1e
ROBOTS: NOINDEX, NOFOLLOW
description: IP または公衆交換電話網 (PSTN) 用のルート トランクを定義するには、次の項目を構成します。
ms.openlocfilehash: 183787e78fee0fa827bd3cc554fb7d43188014d2
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51116415"
---
# <a name="define-the-root-trunk-for-a-new-ip-or-pstn-gateway"></a>新しい IP または PSTN ゲートウェイのルート トランクの定義

IP または公衆交換電話網 (PSTN) 用のルート トランクを定義するには、次の項目を構成します。

- [**トランク名**]: トランクに関連付けられた完全修飾ドメイン名を定義します。

- [**IP/PSTN ゲートウェイのリッスン ポート**]: このトランクがリッスンするポートを定義します。

- [**SIP 転送プロトコル**]: トランク要件に基づき、リストから **TCP** または **TLS** のどちらかを選択します。

- **関連する仲介サーバー**: 展開で使用可能な仲介サーバーの一覧から選択します。

- **関連付けられた仲介サーバーの** ポート: 選択した仲介サーバーがリッスンしているポートを定義します。

## <a name="see-also"></a>関連項目

[Skype for Business Server でメディア バイパスを使用してトランクを構成する](../../../deploy/deploy-enterprise-voice/configure-trunk-with-media-bypass.md)

[Skype for Business Server でメディア バイパスなしでトランクを構成する](../../../deploy/deploy-enterprise-voice/configure-trunk-without-media-bypass.md)

[SIP トランキングのサポート](/previous-versions/office/lync-server-2013/lync-server-2013-sip-trunking-support)