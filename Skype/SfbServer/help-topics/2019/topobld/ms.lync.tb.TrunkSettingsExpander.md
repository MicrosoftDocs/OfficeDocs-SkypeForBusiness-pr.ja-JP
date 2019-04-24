---
title: トランク設定エキスパンダー
ms.reviewer: ''
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.TrunkSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3d00e8f4-e599-4094-a4a1-34fd6e8a5580
ROBOTS: NOINDEX, NOFOLLOW
description: SIP トランクの設定を編集または変更するには、次の操作を行います。
ms.openlocfilehash: 7ebf0ff7b62a6715929d535eb17ba18ab6976dfe
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32201527"
---
# <a name="trunk-settings-expander"></a>トランク設定エキスパンダー

SIP トランクの設定を編集または変更するには、次の操作を行います。

 [**トランク名**] は必須のエントリで、展開の中の SIP トランクを一意に特定します。

 [**PSTN ゲートウェイの関連付け**]: 展開で定義された既存の PSTN ゲートウェイを選択します。

 [**IP/PSTN ゲートウェイのリッスン ポート**]: ゲートウェイが要求をリッスンする TCP/IP ポートを示します。必要な値はゲートウェイのベンダーによって異なる場合がありますが、既定はポート 5067 です。

 [**SIP 転送プロトコル**]: 使用されるプロトコルは TCP または TLS です。TLS が既定です。ゲートウェイでサポートされるプロトコルについては、ゲートウェイ ベンダーのドキュメントを参照してください。既定は TLS で、ゲートウェイが TLS をサポートしている場合、既定がより安全性の高い選択肢と考えられます。

 **仲介サーバーの関連付けられている**: SIP トランクに関連付ける展開から既存の仲介サーバーを選択します。

> [!NOTE]
> ルート トランクだけは、仲介サーバーを関連付けることができます。

 **仲介サーバーの関連付けられているポート**: 必要な値では、仲介サーバーが構成されている値に設定これは上でリッスンします。

![トランク設定エキスパンダー](../../../media/Trunk_Settings_Expander.jpg)

## <a name="see-also"></a>関連項目

[SIP トランクの展開のチェックリスト](https://technet.microsoft.com/library/94f4f03e-19d5-4198-92be-e4076dbb959a.aspx)

[コンポーネントおよび SIP トランキングのトポロジ](https://technet.microsoft.com/library/8ed9a9d0-517e-4f36-a131-22cdafa257fa.aspx)
