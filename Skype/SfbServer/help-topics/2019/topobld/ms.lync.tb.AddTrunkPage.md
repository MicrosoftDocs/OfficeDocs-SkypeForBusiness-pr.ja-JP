---
title: 新しいトランクの定義
ms.reviewer: ''
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddTrunkPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e5d97b27-5ae8-41e0-8ee9-0c3f6d5dd123
ROBOTS: NOINDEX, NOFOLLOW
description: 新しいセッション開始プロトコル (SIP) トランクを定義するには、次の情報を提供します。
ms.openlocfilehash: eba7dec862cf359a8670bcfbf7f0b475575a26ec
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32220826"
---
# <a name="define-a-new-trunk"></a>新しいトランクの定義

新しいセッション開始プロトコル (SIP) トランクを定義するには、次の情報を提供します。

- **トランクの名前**: このトランクを識別するトポロジでは、一意の名前

- **関連付けられている PSTN ゲートウェイ**: ボックスの一覧から、配置に配置され構成されている PSTN ゲートウェイを選択

- **IP または PSTN ゲートウェイのリッスンするポート**: IP PBX または PSTN ゲートウェイがリッスンするポートです。 すべて他のトランク リスニング ・ ポートからの展開で構成されている一意である必要があります。

- **SIP トランスポート プロトコル**: TCP または TLS のいずれかを一覧から選択

- **仲介サーバーの関連付けられている**: 仲介サーバーを展開し、展開の構成を一覧から選択

- **仲介サーバーの関連付けられているポート**: ポートの値をこの SIP トランクを使用する仲介サーバーの TCP または TLS ポートの値に設定

## <a name="see-also"></a>関連項目

[Skype ビジネス サーバーは M:N trunk](../../../plan-your-deployment/enterprise-voice-solution/m-n-trunk.md)

[SIP トランクを実装する方法は?](https://technet.microsoft.com/library/273a22b1-8a4c-4187-acf8-c57d5c6598ce.aspx)
