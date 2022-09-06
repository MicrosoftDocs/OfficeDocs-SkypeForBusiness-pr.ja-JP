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
description: Microsoft Teams でのダイヤル プランとルーティング
ms.openlocfilehash: 89332b5e5756bc33c92a67b641bab85b826bfe70
ms.sourcegitcommit: 75dfc3cd9b59282d68e35e4d7185da572eb3795c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/06/2022
ms.locfileid: "67606786"
---
# <a name="overview"></a>概要

このセクションの記事では、Microsoft Teams でのダイヤル プランと通話ルーティングについて説明します。 

- [ダイヤル プランとは](what-are-dial-plans.md)
- [ダイヤル プランを作成および管理する](create-and-manage-dial-plans.md)
- [割り当てられていない numbes に呼び出しをルーティングする](routing-calls-to-unassigned-numbers.md)

このセクションの記事は、通話プラン、オペレーター接続、オペレーター コネクト モバイル (パブリック プレビュー リリース)、ダイレクト ルーティングなど、公衆交換電話網 (PSTN) に接続するためのすべてのオプションに適用されます。 すべての PSTN 接続オプションの詳細については、「 [PSTN 接続オプション」](pstn-connectivity.md)を参照してください。

通話プラン、オペレーター接続、またはオペレーター コネクト モバイルを選択した場合、ほとんどの通話ルーティングは Microsoft またはプロバイダーによって処理されます。 ただし、ダイレクト ルーティングには、通話ルーティングを構成するための追加の手順が必要です。 

ダイレクト ルーティングの場合は、音声ルートを指定し、音声ルーティング ポリシーをユーザーに割り当てることで、通話ルーティングを構成する必要があります。 番号変換のダイヤル プランをトランク レベルで構成して、セッション ボーダー コントローラー (SBC) との相互運用性を確保できます。 詳細については、「 [ダイレクト ルーティングの音声ルーティングの構成](direct-routing-voice-routing.md)、 [音声ルーティング ポリシーの管理](manage-voice-routing-policies.md) 、 [および電話番号の変換](direct-routing-translate-numbers.md)」を参照してください。

通話プランとオペレーター接続ユーザーにダイレクト ルーティング オンライン音声ルーティング ポリシーを割り当てることができることに注意してください。 たとえば、ユーザーがコール センターに直接ダイヤルインできるようにするには、これを行う必要があります。 コール センターに直接ルーティング トランクを設定できます。

たとえば、ユーザーが通話プラン ライセンスを持っている場合、そのユーザーの発信通話は、Microsoft 通話プラン PSTN インフラストラクチャを介して自動的にルーティングされます。 ダイレクト ルーティング オンライン音声ルーティング ポリシーを構成してユーザーに割り当てる場合、ユーザーの発信通話がチェックされ、ダイヤルされた番号がオンライン音声ルーティング ポリシーで定義されている番号パターンと一致するかどうかを判断します。 一致する場合は、ダイレクト ルーティング トランク経由で呼び出しがルーティングされます。 一致しない場合、通話は通話プラン PSTN インフラストラクチャ経由でルーティングされます。

詳細については、「 [ダイレクト ルーティング音声ルーティング ポリシーに関する考慮事項](direct-routing-voice-routing.md#voice-routing-policy-considerations)」を参照してください。



