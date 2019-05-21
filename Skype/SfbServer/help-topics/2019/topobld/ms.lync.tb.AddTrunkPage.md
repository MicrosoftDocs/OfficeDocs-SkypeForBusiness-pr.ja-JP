---
title: 新しいトランクの定義
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddTrunkPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e5d97b27-5ae8-41e0-8ee9-0c3f6d5dd123
ROBOTS: NOINDEX, NOFOLLOW
description: 新しいセッション開始プロトコル (SIP) トランクを定義するには、次の情報を指定します。
ms.openlocfilehash: c6586f9da069c3a3fc149b086562592db113b31e
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34282481"
---
# <a name="define-a-new-trunk"></a>新しいトランクの定義

新しいセッション開始プロトコル (SIP) トランクを定義するには、次の情報を指定します。

- **トランク名**: このトランクを識別するトポロジの一意の名前

- **関連付けられている Pstn ゲートウェイ**: 展開済みの pstn ゲートウェイを一覧から選びます。

- **Ip/pstn ゲートウェイのリスニングポート**: ip PBX または pstn ゲートウェイがリッスンするポート。 展開で構成されている他のすべてのトランクリッスンポートから一意である必要があります

- **SIP トランスポートプロトコル**: TCP または TLS の一覧から選択します。

- **関連付けられている仲介サーバー**: 展開で展開され構成されている仲介サーバーを一覧から選びます。

- **関連付けられている仲介サーバーポート**: この SIP トランクで使用する仲介サーバーの TCP または TLS ポートの値としてポート値を設定します

## <a name="see-also"></a>関連項目

[Skype for Business Server の M:N トランク](../../../plan-your-deployment/enterprise-voice-solution/m-n-trunk.md)

[SIP トランキングの実装方法を教えてください。](https://technet.microsoft.com/library/273a22b1-8a4c-4187-acf8-c57d5c6598ce.aspx)
