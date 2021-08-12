---
title: PSTN ゲートウェイ設定の展開
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.PstnGatewaySettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0fd103df-150d-4ea8-b522-18dbc50f5061
ROBOTS: NOINDEX, NOFOLLOW
description: PSTN (公衆交換電話網) ゲートウェイの設定を編集または変更するには、次のフィールドを変更します。
ms.openlocfilehash: da993cc36cfbb4195df68417cb16db5909c6baa5e21fed9f6316337dd1fd0d21
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "54281860"
---
# <a name="pstn-gateway-settings-expander"></a>PSTN ゲートウェイ設定エキスパンダー
 
PSTN (公衆交換電話網) ゲートウェイの設定を編集または変更するには、次のフィールドを変更します。
  
ゲートウェイの FQDN または IP アドレスは必須のエントリであり、PSTN ゲートウェイの **完全修飾ドメイン名 (FQDN)** をドメイン ネーム システム (DNS) ホスト (A) レコード、静的 HOSTS ファイル エントリ、または PSTN ゲートウェイの IP アドレスのいずれとして定義するのかを定義します。
  
SIP トランスポート プロトコルは、伝送制御プロトコル (TCP) の場合とトランスポート層セキュリティ (TLS) の場合があります。TLS が既定です。ゲートウェイでサポートされるプロトコルについては、ゲートウェイ ベンダーのドキュメントを参照してください。既定は TLS で、ゲートウェイが TLS をサポートしている場合は、こちらがより安全性の高い選択肢と考えられます。
  
ゲートウェイで IPv4 および IPv6 を有効にするかどうかを選択します。
  
**代替メディア IP アドレス** は、展開されている PSTN ゲートウェイがメディア トラフィック用に、通常は SIP トラフィック専用の既定の構成済みの IP アドレスである、異なる IP アドレスを持っている仲介サーバー用の定義です。このパラメーターを定義すると、PSTN ゲートウェイで、異なるネットワーク インターフェイス、つまりメディアのパスがサポートされます。このアドレスを空白にすると、PSTN ゲートウェイではメディアの代替パスはサポートされません。
  

