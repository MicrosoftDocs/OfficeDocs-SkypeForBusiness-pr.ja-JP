---
title: トランク設定エキスパンダー
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.TrunkSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3d00e8f4-e599-4094-a4a1-34fd6e8a5580
ROBOTS: NOINDEX, NOFOLLOW
description: SIP トランクの設定を編集または変更するには、次の操作を行います。
ms.openlocfilehash: 97c1578418fdf46ad39256312d7aa15abd44ff84
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41797408"
---
# <a name="trunk-settings-expander"></a>トランク設定エキスパンダー

SIP トランクの設定を編集または変更するには、次の操作を行います。

 [**トランク名**] は必須のエントリで、展開の中の SIP トランクを一意に特定します。

 [**PSTN ゲートウェイの関連付け**]: 展開で定義された既存の PSTN ゲートウェイを選択します。

 [**IP/PSTN ゲートウェイのリッスン ポート**]: ゲートウェイが要求をリッスンする TCP/IP ポートを示します。必要な値はゲートウェイのベンダーによって異なる場合がありますが、既定はポート 5067 です。

 [**SIP 転送プロトコル**]: 使用されるプロトコルは TCP または TLS です。TLS が既定です。ゲートウェイでサポートされるプロトコルについては、ゲートウェイ ベンダーのドキュメントを参照してください。既定は TLS で、ゲートウェイが TLS をサポートしている場合、既定がより安全性の高い選択肢と考えられます。

 **関連付けられている仲介サーバー**: 展開から既存の仲介サーバーを選び、SIP トランクに関連付けます。

> [!NOTE]
> ルートトランクのみを仲介サーバーに関連付けることができます。

 **関連付けられている仲介サーバーのポート**: 必須の値。これは、仲介サーバーがリッスンするように構成されている値に設定されます。

![トランク設定エキスパンダー](../../../media/Trunk_Settings_Expander.jpg)

## <a name="see-also"></a>関連項目

[SIP トランキングの展開チェックリスト](https://technet.microsoft.com/library/94f4f03e-19d5-4198-92be-e4076dbb959a.aspx)

[SIP トランクのコンポーネントとトポロジー](https://technet.microsoft.com/library/8ed9a9d0-517e-4f36-a131-22cdafa257fa.aspx)
