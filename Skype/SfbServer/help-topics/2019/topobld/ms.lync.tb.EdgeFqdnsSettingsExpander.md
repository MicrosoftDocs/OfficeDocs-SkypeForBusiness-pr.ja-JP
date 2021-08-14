---
title: エッジ サーバーの FQDN 設定エキスパンダー
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.EdgeFqdnsSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9e4e9445-0147-4dd6-84f0-b41de142b332
ROBOTS: NOINDEX, NOFOLLOW
description: エッジ サーバーの外部 設定 を編集または指定するには、まず、セッション開始プロトコル (SIP) アクセス、Web 会議エッジ サービス、およびオーディオ/ビデオ エッジ サービスに個別の IP アドレスを使用する必要があります。
ms.openlocfilehash: 49fddf486877711ebd6ba3b0f20960f475a5268ed9cda81632c3ab21a09b83c7
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "54328492"
---
# <a name="edge-server-fqdns-settings-expander"></a>エッジ サーバーの FQDN 設定エキスパンダー

エッジ サーバーの **外部 設定** を編集または指定するには、まず、セッション開始プロトコル (SIP) アクセス、Web 会議エッジ サービス、およびオーディオ/ビデオ エッジ サービスに個別の IP アドレスを使用する必要があります。

各サービスで別々の IP アドレスを使用する場合は、**[Web 会議と音声ビデオで別々の FQDN と IP アドレスを有効にする]** チェック ボックスをオンにします。それぞれのサービスでは、そのサービス用に、対応するドメイン ネーム システム (DNS) ホスト (A) レコードが作成されている必要があります。

外部に提供されるサービスのそれぞれで、完全修飾ドメイン名 (FQDN) と、関連付けられたポートを指定します。たとえば、[**SIP アドレス**] として、関連付けられたポートを 5061 にして sip.contoso.com を使用できます。

> [!IMPORTANT]
> 外部に提供される各サービスで別々の FQDN を使用する場合は、各サービスに固有のポート値を関連付ける必要があります。既定では、SIP がポート 5061/TLS、Web 会議エッジ サービスがポート 444/TLS、および音声ビデオ会議エッジ サービスがポート 443/TLS で提供されます。別々の FQDN と IP アドレス、またはポートを使用することを含め、これらの設定に変更を加える場合は、最初に構成された値に依存する他のすべてのサービスを更新する必要があります。

外部に提供されるサービスのために、組織では 1 つの FQDN と IP アドレスを使用することを決定した場合は、[**Web 会議と音声ビデオで別々の FQDN と IP アドレスを有効にする**] チェック ボックスをオフにします。必要に応じて、[**SIP アクセス**] のプールの FQDN とポート値を編集できます。

> [!IMPORTANT]
> 別々の FQDN および IP アドレスまたはポートを使用することを含め、これらの設定のいずれかに変更を加える場合は、最初に構成された値に依存する他のすべてのサービスを更新する必要があります。

エッジ サービスの設定の定義と構成の詳細については [、「Define Your Edge Topology 」を参照してください](/previous-versions/office/lync-server-2013/lync-server-2013-define-your-edge-topology)。