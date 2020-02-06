---
title: PSTN ゲートウェイ設定エキスパンダー
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/26/2015
audience: ITPro
ms.topic: article
f1.keywords:
- NOCSH
ms.custom:
- ms.lync.tb.PstnGatewaySettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0fd103df-150d-4ea8-b522-18dbc50f5061
description: PSTN (公衆交換電話網) ゲートウェイの設定を編集または変更するには、次のフィールドを変更します。
ms.openlocfilehash: 1fa72dfc91f75994be4afadfea1d6f526af5607f
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41819419"
---
# <a name="pstn-gateway-settings-expander"></a>PSTN ゲートウェイ設定エキスパンダー
 
PSTN (公衆交換電話網) ゲートウェイの設定を編集または変更するには、次のフィールドを変更します。
  
ゲートウェイの FQDN または IP アドレスは必須のエントリであり、PSTN ゲートウェイの**完全修飾ドメイン名 (FQDN)** をドメイン ネーム システム (DNS) ホスト (A) レコード、静的 HOSTS ファイル エントリ、または PSTN ゲートウェイの IP アドレスのいずれとして定義するのかを定義します。
  
SIP トランスポート プロトコルは、伝送制御プロトコル (TCP) の場合とトランスポート層セキュリティ (TLS) の場合があります。TLS が既定です。ゲートウェイでサポートされるプロトコルについては、ゲートウェイ ベンダーのドキュメントを参照してください。既定は TLS で、ゲートウェイが TLS をサポートしている場合は、こちらがより安全性の高い選択肢と考えられます。
  
ゲートウェイで IPv4 および IPv6 を有効にするかどうかを選択します。
  
**代替メディアの ip アドレス**は、展開された PSTN ゲートウェイが、既定で構成されている ip アドレス (通常は SIP トラフィック専用) とは異なる ip アドレスを持つ仲介サーバーの定義です。 このパラメーターを定義すると、PSTN ゲートウェイで、異なるネットワーク インターフェイス、つまりメディアのパスがサポートされます。 このアドレスを空白にすると、PSTN ゲートウェイではメディアの代替パスはサポートされません。
  

