---
title: 仲介サービス設定の展開
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/26/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.FeMediationServiceSettingsExpander
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 142c1acd-cdaa-4922-8379-aa1bdf56a964
description: '[仲介サーバー] では、次の情報を指定できます。'
ms.openlocfilehash: 2e21c1d21b7b951dfc1ac23c7e3414243eedc884
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/05/2022
ms.locfileid: "62416640"
---
# <a name="mediation-service-settings-expander"></a>仲介サービス設定エキスパンダー

[**仲介サーバー**] では、次の情報を指定できます。

仲介サーバーをフロントエンド プールまたは Standard Edition サーバーにコロケーションする場合は、[仲介サーバーを有効にする] チェック **ボックスをオンにします**。 仲介サーバーを併置しない場合、このセクションで定義可能な設定はありません。

仲介サーバーの併置を有効にした場合は、サーバーでのトランスポート層セキュリティ (TLS) のリッスン ポートの範囲を定義する必要があります。既定のポートは 5067 です。[**TCP ポートを有効にする**] を選択した場合は、併置される仲介サーバーの 伝送制御プロトコル (TCP) ポートを定義する必要があります。これは省略可能な設定です。この設定が必要かどうかは、ゲートウェイまたは公衆交換電話網 (PSTN) の要件を参照して判断してください。既定では、TCP ポートの値は 5068 です。

併置された仲介サーバーに関連付ける PSTN ゲートウェイを定義します。このゲートウェイを既に定義している場合は、それらのゲートウェイを仲介サーバーに関連付けることができます。

仲介サーバーに複数のゲートウェイを関連付けている場合は、関連付けた最初のゲートウェイが既定のゲートウェイとなります。既定のゲートウェイとして別のゲートウェイを選択する必要がある場合は、既定にするゲートウェイを選択して、[**既定にする**] をクリックします。既定のゲートウェイとしての選択を解除するには、[**既定値の解除**] をクリックします。

Enterprise Edition フロントエンド プールまたは Standard Edition サーバーの設定の定義と構成の詳細については、「トポロジの定義と構成」および「仲介サーバーの[](/previous-versions/office/lync-server-2013/lync-server-2013-defining-and-configuring-the-topology)展開」および「ピアの定義」を[](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-mediation-servers-and-defining-peers)参照してください。