---
title: 新しいトランクを定義する
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
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
ms.openlocfilehash: 5aaaa05a340a503cf69f8ca78240794d29058655
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/04/2021
ms.locfileid: "60778507"
---
# <a name="define-a-new-trunk"></a>新しいトランクの定義

以下の情報を指定することにより、新しいセッション開始プロトコル (SIP) トランクを定義します。

- [**トランク名**]: トポロジ内でこのトランクを識別する一意の名前。

- [**PSTN ゲートウェイの関連付け**]: 展開内の展開済みで構成済みの PSTN ゲートウェイをリストから選択します。

- [**IP/PSTN ゲートウェイのリッスン ポート**]: IP-PBX または PSTN ゲートウェイがリッスンするポート。展開内で構成されている他のすべてのトランク リッスン ポートと異なるものであることが必要です。

- [**SIP 転送プロトコル**]: リストから TCP または TLS を選択します。

- **関連する仲介サーバー**: 展開で展開および構成されている仲介サーバーを一覧から選択します。

- **関連付けられた仲介サーバー** のポート: この SIP トランクで使用する仲介サーバーの TCP または TLS ポート値とポート値を設定します。

## <a name="see-also"></a>関連項目

[M:N トランク in Skype for Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/m-n-trunk.md)

[SIP トランキングを実装する方法](/previous-versions/office/lync-server-2013/lync-server-2013-how-do-i-implement-sip-trunking)