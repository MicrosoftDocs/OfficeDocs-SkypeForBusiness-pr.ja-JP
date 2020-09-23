---
title: エッジ サーバーの FQDN 設定エキスパンダー
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/25/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.EdgeFqdnsSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9e4e9445-0147-4dd6-84f0-b41de142b332
description: エッジサーバーの外部設定を編集または指定するには、まず、セッション開始プロトコル (SIP) アクセス、Web 会議エッジサービス、および音声ビデオエッジサービスに個別の IP アドレスを使用するかどうかを決定する必要があります。
ms.openlocfilehash: f04cdcb16678825d9ab7cc4696c4e649676587b2
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/23/2020
ms.locfileid: "48218218"
---
# <a name="edge-server-fqdns-settings-expander"></a>エッジ サーバーの FQDN 設定エキスパンダー

エッジサーバーの **外部設定** を編集または指定するには、まず、セッション開始プロトコル (SIP) アクセス、Web 会議エッジサービス、および音声ビデオエッジサービスに個別の IP アドレスを使用するかどうかを決定する必要があります。

各サービスで別々の IP アドレスを使用する場合は、**[Web 会議と音声ビデオで別々の FQDN と IP アドレスを有効にする]** チェック ボックスをオンにします。それぞれのサービスでは、そのサービス用に、対応するドメイン ネーム システム (DNS) ホスト (A) レコードが作成されている必要があります。

外部に提供されるサービスのそれぞれで、完全修飾ドメイン名 (FQDN) と、関連付けられたポートを指定します。たとえば、[**SIP アドレス**] として、関連付けられたポートを 5061 にして sip.contoso.com を使用できます。

> [!IMPORTANT]
> 外部に提供される各サービスで別々の FQDN を使用する場合は、各サービスに固有のポート値を関連付ける必要があります。既定では、SIP がポート 5061/TLS、Web 会議エッジ サービスがポート 444/TLS、および音声ビデオ会議エッジ サービスがポート 443/TLS で提供されます。別々の FQDN と IP アドレス、またはポートを使用することを含め、これらの設定に変更を加える場合は、最初に構成された値に依存する他のすべてのサービスを更新する必要があります。

外部に提供されるサービスのために、組織では 1 つの FQDN と IP アドレスを使用することを決定した場合は、[**Web 会議と音声ビデオで別々の FQDN と IP アドレスを有効にする**] チェック ボックスをオフにします。必要に応じて、[**SIP アクセス**] のプールの FQDN とポート値を編集できます。

> [!IMPORTANT]
> 別々の FQDN および IP アドレスまたはポートを使用することを含め、これらの設定のいずれかに変更を加える場合は、最初に構成された値に依存する他のすべてのサービスを更新する必要があります。

エッジサービスの設定の定義および構成の詳細については、「 [Define Your Edge Topology](https://technet.microsoft.com/library/787b23f1-8fa0-4c37-abf2-c516c5dd66f0.aspx)」を参照してください。


