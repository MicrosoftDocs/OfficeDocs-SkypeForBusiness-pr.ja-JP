---
title: 仲介サービス設定の展開
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/26/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.FeMediationServiceSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 142c1acd-cdaa-4922-8379-aa1bdf56a964
description: '[仲介サーバー] では、次の情報を指定できます。'
ms.openlocfilehash: 0e6e9101b8b0a530b0f47411f1d8ce1eaa2e01b5
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49810277"
---
# <a name="mediation-service-settings-expander"></a>仲介サービス設定エキスパンダー

[**仲介サーバー**] では、次の情報を指定できます。

仲介サーバーをフロントエンド プールまたは Standard Edition サーバーに共置する場合は、[仲介サーバーの一覧を有効にする] チェック **ボックスをオンにします**。 仲介サーバーを併置しない場合、このセクションで定義可能な設定はありません。

仲介サーバーの併置を有効にした場合は、サーバーでのトランスポート層セキュリティ (TLS) のリッスン ポートの範囲を定義する必要があります。既定のポートは 5067 です。[**TCP ポートを有効にする**] を選択した場合は、併置される仲介サーバーの 伝送制御プロトコル (TCP) ポートを定義する必要があります。これは省略可能な設定です。この設定が必要かどうかは、ゲートウェイまたは公衆交換電話網 (PSTN) の要件を参照して判断してください。既定では、TCP ポートの値は 5068 です。

併置された仲介サーバーに関連付ける PSTN ゲートウェイを定義します。このゲートウェイを既に定義している場合は、それらのゲートウェイを仲介サーバーに関連付けることができます。

仲介サーバーに複数のゲートウェイを関連付けている場合は、関連付けた最初のゲートウェイが既定のゲートウェイとなります。既定のゲートウェイとして別のゲートウェイを選択する必要がある場合は、既定にするゲートウェイを選択して、[**既定にする**] をクリックします。既定のゲートウェイとしての選択を解除するには、[**既定値の解除**] をクリックします。

Enterprise Edition フロントエンド プールまたは Standard Edition サーバーの設定の定義と構成の詳細については [、「Defining and Configuring the Topology](https://technet.microsoft.com/library/51d1601e-4f83-48d4-ad08-3b4d5e2003aa.aspx) and [Deploying Mediation Servers and Defining Peers](https://technet.microsoft.com/library/a684f1da-6671-4011-adf6-2db49e2528e2.aspx)」を参照してください。


