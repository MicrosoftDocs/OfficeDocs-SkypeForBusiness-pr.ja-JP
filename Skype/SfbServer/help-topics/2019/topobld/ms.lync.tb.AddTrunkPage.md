---
title: 新しいトランクを定義する
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddTrunkPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e5d97b27-5ae8-41e0-8ee9-0c3f6d5dd123
ROBOTS: NOINDEX, NOFOLLOW
description: 以下の情報を指定することにより、新しいセッション開始プロトコル (SIP) トランクを定義します。
ms.openlocfilehash: 540076814d2916f74a5e11be42f99b57711da2b7
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51093275"
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

[Skype for Business Server の M:N トランク](../../../plan-your-deployment/enterprise-voice-solution/m-n-trunk.md)

[SIP トランキングを実装する方法](/previous-versions/office/lync-server-2013/lync-server-2013-how-do-i-implement-sip-trunking)