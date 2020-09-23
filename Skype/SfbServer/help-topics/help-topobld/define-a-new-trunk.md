---
title: 新しいトランクを定義する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddTrunkPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e5d97b27-5ae8-41e0-8ee9-0c3f6d5dd123
description: 以下の情報を指定することにより、新しいセッション開始プロトコル (SIP) トランクを定義します。
ms.openlocfilehash: 4addcfbdb854de223f7942f55e2e2180136f9bbc
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/23/2020
ms.locfileid: "48218558"
---
# <a name="define-a-new-trunk"></a>新しいトランクを定義する

以下の情報を指定することにより、新しいセッション開始プロトコル (SIP) トランクを定義します。

- [**トランク名**]: トポロジ内でこのトランクを識別する一意の名前。

- [**PSTN ゲートウェイの関連付け**]: 展開内の展開済みで構成済みの PSTN ゲートウェイをリストから選択します。

- [**IP/PSTN ゲートウェイのリッスン ポート**]: IP-PBX または PSTN ゲートウェイがリッスンするポート。展開内で構成されている他のすべてのトランク リッスン ポートと異なるものであることが必要です。

- [**SIP 転送プロトコル**]: リストから TCP または TLS を選択します。

- [**関連付けられている仲介サーバー**]: 展開で展開および構成されている仲介サーバーを一覧から選択します。

- **関連付けられている仲介サーバーのポート**: この SIP トランクが使用する仲介サーバーの TCP ポート値または TLS ポート値と等しいポート値を設定します。

## <a name="see-also"></a>関連項目

[Skype for Business Server 2015 の M:N トランク](../../plan-your-deployment/enterprise-voice-solution/m-n-trunk.md)

[SIP トランキングの実装方法](https://technet.microsoft.com/library/273a22b1-8a4c-4187-acf8-c57d5c6598ce.aspx)
