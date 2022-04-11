---
title: ダイヤル プランとルーティング
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
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
description: Microsoft Teamsでのダイヤル プランとルーティング
ms.openlocfilehash: 1d99b5edef1cf6c4440a218097933e4ff5843f1d
ms.sourcegitcommit: 4847f24e8c644336d2b2f48aa09e2cf91360e4dd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/06/2022
ms.locfileid: "64686717"
---
# <a name="overview"></a>概要

このセクションの記事では、Microsoft Teamsでのダイヤル プランと通話ルーティングについて説明します。 

- [ダイヤル プランとは](what-are-dial-plans.md)
- [ダイヤル プランを作成および管理する](create-and-manage-dial-plans.md)
- [割り当てられていない numbes に呼び出しをルーティングする](routing-calls-to-unassigned-numbers.md)

このセクションの記事は、公衆交換電話網 (PSTN) に接続するためのすべてのオプション (通話プラン、オペレーター接続、およびダイレクト ルーティング) に適用されます。 すべての PSTN 接続オプションの詳細については、「 [PSTN 接続オプション」](pstn-connectivity.md)を参照してください。

通話プランまたはオペレーター接続を選択した場合、ほとんどの通話ルーティングは Microsoft またはプロバイダーによって処理されます。 ただし、ダイレクト ルーティングには、通話ルーティングを構成するための追加の手順が必要です。 

ダイレクト ルーティングの場合は、音声ルートを指定し、音声ルーティング ポリシーをユーザーに割り当てることで、通話ルーティングを構成する必要があります。 番号変換のダイヤル プランをトランク レベルで構成して、セッション ボーダー コントローラー (SBC) との相互運用性を確保できます。 詳細については、「 [ダイレクト ルーティングの音声ルーティングの構成](direct-routing-voice-routing.md)、 [音声ルーティング ポリシーの管理](manage-voice-routing-policies.md) 、 [および電話番号の変換](direct-routing-translate-numbers.md)」を参照してください。

通話プランとオペレーター接続 ユーザーにダイレクト ルーティング オンライン音声ルーティング ポリシーを割り当てることができることに注意してください。 たとえば、ユーザーがコール センターに直接ダイヤルインできるようにするには、これを行う必要があります。 コール センターに直接ルーティング トランクを設定できます。

たとえば、ユーザーが通話プラン ライセンスを持っている場合、そのユーザーの発信通話は、Microsoft 通話プラン PSTN インフラストラクチャを介して自動的にルーティングされます。 ダイレクト ルーティング オンライン音声ルーティング ポリシーを構成してユーザーに割り当てる場合、ユーザーの発信通話がチェックされ、ダイヤルされた番号がオンライン音声ルーティング ポリシーで定義されている番号パターンと一致するかどうかを判断します。 一致する場合は、ダイレクト ルーティング トランク経由で呼び出しがルーティングされます。 一致しない場合、通話は通話プラン PSTN インフラストラクチャ経由でルーティングされます。

詳細については、「 [ダイレクト ルーティング音声ルーティング ポリシーに関する考慮事項](direct-routing-voice-routing.md#voice-routing-policy-considerations)」を参照してください。


