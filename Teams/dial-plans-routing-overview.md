---
title: Microsoft Teams のダイヤル プランとルーティング
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: jenstr
ms.topic: article
ms.assetid: aa2ec464-3481-4bbb-8c14-e13e18093df5
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
- highpri
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
description: Microsoft Teams でプランとルーティングをダイヤルする
ms.openlocfilehash: b45fd9ec15ae6a9bb8f342096711b58512aead43
ms.sourcegitcommit: aef1ab47fb9cb4502cb49bc3c7ffafcd62e54c82
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/02/2022
ms.locfileid: "69242471"
---
# <a name="microsoft-teams-dial-plans-and-routing"></a>Microsoft Teams のダイヤル プランとルーティング

このセクションの記事では、Microsoft Teams でのダイヤル プランと通話ルーティングについて説明します。 

- [ダイヤル プランとは](what-are-dial-plans.md)
- [ダイヤル プランを作成および管理する](create-and-manage-dial-plans.md)
- [割り当てられていない numbe への呼び出しのルーティング](routing-calls-to-unassigned-numbers.md)

このセクションの記事は、公衆交換電話網 (PSTN): 通話プラン、オペレーター接続、Teams Phone Mobile、およびダイレクト ルーティングに接続するためのすべてのオプションに適用されます。 すべての PSTN 接続オプションの詳細については、「 [PSTN 接続オプション](pstn-connectivity.md)」を参照してください。

通話プラン、オペレーター接続、または Teams Phone Mobile を選択した場合、ほとんどの通話ルーティングは、Microsoftまたはプロバイダーによって処理されます。 ただし、ダイレクト ルーティングでは、通話ルーティングを構成するための追加の手順が必要です。 

ダイレクト ルーティングの場合は、音声ルートを指定し、音声ルーティング ポリシーをユーザーに割り当てることで、通話ルーティングを構成する必要があります。 トランク レベルで番号変換のダイヤル プランを構成して、セッション ボーダー コントローラー (SBC) との相互運用性を確保できます。 詳細については、「 [ダイレクト ルーティングの音声ルーティングの構成」、「音声ルーティング](direct-routing-voice-routing.md) [ポリシーの管理](manage-voice-routing-policies.md) 」、および「 [電話番号の翻訳」を](direct-routing-translate-numbers.md)参照してください。

ダイレクト ルーティング オンライン音声ルーティング ポリシーを通話プランとオペレーター接続ユーザーに割り当てることができることに注意してください。 たとえば、ユーザーがコール センターに直接ダイヤルインできるようにするには、これを行うことができます。 コール センターへのダイレクト ルーティング トランクを設定できます。

たとえば、ユーザーが通話プラン ライセンスを持っている場合、そのユーザーの発信通話は、Microsoft通話プラン PSTN インフラストラクチャを介して自動的にルーティングされます。 ダイレクト ルーティング オンライン音声ルーティング ポリシーを構成してユーザーに割り当てる場合、ユーザーの発信呼び出しがチェックされ、ダイヤルされた番号がオンライン音声ルーティング ポリシーで定義されている番号パターンと一致するかどうかを判断します。 一致する場合、呼び出しはダイレクト ルーティング トランクを介してルーティングされます。 一致するものがない場合、通話は通話プラン PSTN インフラストラクチャを介してルーティングされます。

詳細については、「 [ダイレクト ルーティング音声ルーティング ポリシーに関する考慮事項](direct-routing-voice-routing.md#voice-routing-policy-considerations)」を参照してください。



