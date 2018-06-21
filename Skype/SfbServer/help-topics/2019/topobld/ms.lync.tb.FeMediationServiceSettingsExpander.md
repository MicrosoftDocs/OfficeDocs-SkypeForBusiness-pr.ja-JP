---
title: 仲介サービス設定エキスパンダー
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.FeMediationServiceSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 142c1acd-cdaa-4922-8379-aa1bdf56a964
description: 仲介サーバーでは、次のように指定できます。
ms.openlocfilehash: b1d7f088165c1287599d19e103b3a418d5f4a5f8
ms.sourcegitcommit: 08cf97296fb9ba6fbc4d68c3e380c8f37e86dd02
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/21/2018
ms.locfileid: "19997088"
---
# <a name="mediation-service-settings-expander"></a>仲介サービス設定エキスパンダー
 
[**仲介サーバー**] では、次の情報を指定できます。
  
仲介サーバーをフロント エンド プールまたは Standard Edition サーバーを配置するが場合、は、**仲介サーバーを 1 か所に配置を有効に**するチェック ボックスを選択します。 仲介サーバーを連結する場合は、このセクションで定義できる設定はありません。 
  
仲介サーバーのコロケーションを有効にした場合は、トランスポート層セキュリティ (TLS) のサーバー上でリッスンしているポートの範囲を定義する必要があります。 既定では、このポートは 5067 です。 **有効にする TCP ポート**を選択する場合は、配置されている仲介サーバーの伝送制御プロトコル (TCP) ポートを定義してください。 これは、オプションの設定、およびゲートウェイの要件や、これが必要なかどうかを決定するのには公衆交換電話網 (PSTN) の要件を参照してください。 既定では、TCP ポートの値は 5068 がします。
  
配置されている仲介サーバーに関連付けられている PSTN ゲートウェイを定義します。 ゲートウェイが定義されている場合は、仲介サーバーに関連付けるに使用されます。 
  
仲介サーバーに関連付けられている 1 つ以上のゲートウェイがある場合は、関連付けられている最初のゲートウェイがデフォルト ゲートウェイになります。 既定のゲートウェイとして別のゲートウェイを選択する必要がある場合は、既定にするゲートウェイを選択して、[**既定にする**] をクリックします。 既定のゲートウェイとしての選択を解除するには、[**既定値の解除**] をクリックします。
  
詳細を定義して、エンタープライズ エディションのフロント エンド プールまたは Standard Edition サーバーの設定の構成について[を定義してトポロジの構成](http://technet.microsoft.com/library/51d1601e-4f83-48d4-ad08-3b4d5e2003aa.aspx)、および[仲介サーバーの展開、および同等の定義](http://technet.microsoft.com/library/a684f1da-6671-4011-adf6-2db49e2528e2.aspx)を参照してください。
  

