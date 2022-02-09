---
title: 新しいトランクを定義する
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddTrunkPage
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: e5d97b27-5ae8-41e0-8ee9-0c3f6d5dd123
description: 以下の情報を指定することにより、新しいセッション開始プロトコル (SIP) トランクを定義します。
ms.openlocfilehash: 963a622ed2a7f3c39dca0be5199126ffaf201314
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/05/2022
ms.locfileid: "62416700"
---
# <a name="define-a-new-trunk"></a>新しいトランクの定義

以下の情報を指定することにより、新しいセッション開始プロトコル (SIP) トランクを定義します。

- [**トランク名**]: トポロジ内でこのトランクを識別する一意の名前。

- [**PSTN ゲートウェイの関連付け**]: 展開内の展開済みで構成済みの PSTN ゲートウェイをリストから選択します。

- [**IP/PSTN ゲートウェイのリッスン ポート**]: IP-PBX または PSTN ゲートウェイがリッスンするポート。展開内で構成されている他のすべてのトランク リッスン ポートと異なるものであることが必要です。

- [**SIP 転送プロトコル**]: リストから TCP または TLS を選択します。

- **関連する仲介サーバー**: 展開で展開および構成されている仲介サーバーを一覧から選択します。

- **関連付けられた仲介サーバー** のポート: この SIP トランクが使用する仲介サーバーの TCP ポートまたは TLS ポート値と同じポート値を設定します。

## <a name="see-also"></a>関連項目

[M:N トランク in Skype for Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/m-n-trunk.md)

[SIP トランキングを実装する方法](/previous-versions/office/lync-server-2013/lync-server-2013-how-do-i-implement-sip-trunking)