---
title: 仲介サービス設定エキスパンダー
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.FeMediationServiceSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 142c1acd-cdaa-4922-8379-aa1bdf56a964
ROBOTS: NOINDEX, NOFOLLOW
description: '[仲介サーバー] では、次の情報を指定できます。'
ms.openlocfilehash: 701fe25213211e044a33cd91893a3509df6148a4
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34292746"
---
# <a name="mediation-service-settings-expander"></a>仲介サービス設定エキスパンダー

[**仲介サーバー**] では、次の情報を指定できます。

仲介サーバーをフロントエンドプールまたは Standard Edition サーバーに配置している場合は、[併置された**仲介サーバーを有効に**する] チェックボックスをオンにします。 仲介サーバーを検索しないことにした場合、このセクションには定義されている設定はありません。

仲介サーバーの collocation を有効にしている場合、トランスポート層セキュリティ (TLS) 用にサーバー上のリッスンポートの範囲を定義する必要があります。 既定では、このポートは5067です。 [ **Tcp ポートを有効に**する] を選択した場合、併置された仲介サーバーに対して伝送制御プロトコル (TCP) ポートを定義する必要があります。 これはオプションの設定であり、必要に応じてゲートウェイまたは公衆交換電話網 (PSTN) の要件を確認する必要があります。 既定では、[TCP ポート] の値は5068です。

併置された仲介サーバーに関連付けられている PSTN ゲートウェイを定義します。 既にゲートウェイが定義されている場合は、それらを仲介サーバーと関連付けることができます。

仲介サーバーと関連付けられているゲートウェイが複数ある場合は、最初に関連付けられたゲートウェイが既定のゲートウェイになります。 既定のゲートウェイとして別のゲートウェイを選択する必要がある場合は、既定にするゲートウェイを選択して、[**既定にする**] をクリックします。 既定のゲートウェイとしての選択を解除するには、[**既定値の解除**] をクリックします。

Enterprise Edition フロントエンドプールまたは Standard Edition サーバーの設定と構成の詳細については、「[トポロジの定義と構成](https://technet.microsoft.com/library/51d1601e-4f83-48d4-ad08-3b4d5e2003aa.aspx)」および「[仲介サーバーの展開とピアの定義](https://technet.microsoft.com/library/a684f1da-6671-4011-adf6-2db49e2528e2.aspx)」を参照してください。


