---
title: PSTN ゲートウェイ設定エキスパンダー
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.PstnGatewaySettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0fd103df-150d-4ea8-b522-18dbc50f5061
ROBOTS: NOINDEX, NOFOLLOW
description: PSTN (公衆交換電話網) ゲートウェイの設定を編集または変更するには、次のフィールドを変更します。
ms.openlocfilehash: 80e3f6b0f6e0afa4b28b384cfe9a64ac8bbd6ebc
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34302183"
---
# <a name="pstn-gateway-settings-expander"></a>PSTN ゲートウェイ設定エキスパンダー
 
PSTN (公衆交換電話網) ゲートウェイの設定を編集または変更するには、次のフィールドを変更します。
  
ゲートウェイの FQDN または IP アドレスは必須のエントリであり、PSTN ゲートウェイの**完全修飾ドメイン名 (FQDN)** をドメイン ネーム システム (DNS) ホスト (A) レコード、静的 HOSTS ファイル エントリ、または PSTN ゲートウェイの IP アドレスのいずれとして定義するのかを定義します。
  
SIP トランスポート プロトコルは、伝送制御プロトコル (TCP) の場合とトランスポート層セキュリティ (TLS) の場合があります。TLS が既定です。ゲートウェイでサポートされるプロトコルについては、ゲートウェイ ベンダーのドキュメントを参照してください。既定は TLS で、ゲートウェイが TLS をサポートしている場合は、こちらがより安全性の高い選択肢と考えられます。
  
ゲートウェイで IPv4 および IPv6 を有効にするかどうかを選択します。
  
**代替メディアの ip アドレス**は、展開された PSTN ゲートウェイが、既定で構成されている ip アドレス (通常は SIP トラフィック専用) とは異なる ip アドレスを持つ仲介サーバーの定義です。 このパラメーターを定義すると、PSTN ゲートウェイで、異なるネットワーク インターフェイス、つまりメディアのパスがサポートされます。 このアドレスを空白にすると、PSTN ゲートウェイではメディアの代替パスはサポートされません。
  

