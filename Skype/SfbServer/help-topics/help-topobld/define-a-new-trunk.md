---
title: 新しいトランクの定義
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- NOCSH
ms.custom:
- ms.lync.tb.AddTrunkPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e5d97b27-5ae8-41e0-8ee9-0c3f6d5dd123
description: 新しいセッション開始プロトコル (SIP) トランクを定義するには、次の情報を指定します。
ms.openlocfilehash: 9b3d42500c57723b13d9c74668b3c4ad7159301b
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41820219"
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

[Skype for Business Server 2015 の M:N トランク](../../plan-your-deployment/enterprise-voice-solution/m-n-trunk.md)

[SIP トランキングの実装方法を教えてください。](https://technet.microsoft.com/library/273a22b1-8a4c-4187-acf8-c57d5c6598ce.aspx)
