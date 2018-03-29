---
title: Skype for Business Server 2015 でのモビリティ サービスおよび UCWA の使用状況の監視
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8389b37a-ca3e-4047-8b51-85bc07da87e8
description: '概要: は移動サービス (Mcx) とユニファイド コミュニケーション Web API (UCWA) をビジネス サーバー 2015 の Skype で管理します。'
ms.openlocfilehash: e71d18fe90eb9a7f2fd7b6563e6d6930f2473e74
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="monitor-mobility-service-and-ucwa-usage-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 でのモビリティ サービスおよび UCWA の使用状況の監視
 
**の概要:**ビジネス サーバー 2015 の Skype のモビリティ サービス (Mcx) とユニファイド コミュニケーション Web API (UCWA) を管理します。
  
、継続的にビジネス サーバー移動サービス (Mcx) と、ユニファイド コミュニケーション Web API (UCWA) は、Skype で使用されるメモリ、CPU を監視する必要があります。 使用状況を監視するには、次のように使用できます。
  
 **Unified Communications Web API (UCWA):**
  
- インターネット インフォメーション サービス (IIS) マネージャーで**LyncUcwa**のワーカー プロセス。 [**ワーカー プロセス**] ウィンドウで、[**CPU %**] および [**プライベート バイト (KB)**] (メモリ) の列を確認します。
    
- [**CPU**] および [**プロセッサ**] パフォーマンス カウンター。
    
ほとんどの展開で、UCWA の CPU 使用率は平均で 15% を下回っている必要があります。 メモリ使用量は、[ビジネス サーバー 2015 の Skype のサーバーのメモリ容量制限のためのモニター](server-memory-capacity-limits.md)で説明されている制限内に収まるようにします。
  
CPU とメモリの使用状況カウンターに加えて、以下のパフォーマンス カウンターを使用すると、サーバーが要求で過負荷になっていないかどうかを確認するのに役立つ場合があります。
  
- **LS:WEB の調整と Authentication\WEB の合計の要求の処理に**、保留中のサーバー上の web 要求の数を示します。 このカウンターでは、10,000 に達すると、後続の要求は失敗します、エラー メッセージが「503 - サービスを使用できません」
    
- **ASP.NET\Requests キュー**(常にゼロのはず)。
    
> [!NOTE]
> これらの値に達するか、これらの値を超えた場合、Web サービスをホストしているコンピューターの CPU、コア数、およびメモリの適切な規模設定の容量計画を再検討して、再計算する必要があります。 
  
 **Mobility Service (Mcx):**
  
- **CSIntMcxAppPool** 、 **CSExtMcxAppPool**ワーカー プロセスのインターネット インフォメーション サービス (IIS) マネージャー。 [**ワーカー プロセス**] ウィンドウで、[**CPU %**] および [**プライベート バイト (KB)**] (メモリ) の列を確認します。
    
- [**CPU**] および [**プロセッサ**] パフォーマンス カウンター。
    
ほとんどの展開で、Mobility Service の CPU 使用率は平均で 15% を下回っている必要があります。 メモリ使用量は、[ビジネス サーバー 2015 の Skype のサーバーのメモリ容量制限のためのモニター](server-memory-capacity-limits.md)で説明されている制限内に収まるようにします。
  
CPU とメモリの使用状況カウンターに加えて、以下の ASP.NET パフォーマンス カウンターを使用すると、サーバーが要求で過負荷になっていないかどうかを確認するのに役立つ場合があります。
  
- **ASP.NET v2.0.50727\Requests 現在**、保留中のサーバー上の web 要求の数を示します。 「503 - サービスを使用できません」のエラー メッセージとそれ以降の要求は失敗しますこのカウンターでは、5,000 に達すると、
    
- **ASP.NET\Requests キュー**(常にゼロのはず)。
    
> [!NOTE]
> これらの値に達するか、これらの値を超えた場合、Web サービスをホストしているコンピューターの CPU、コア数、およびメモリの適切な規模設定の容量計画を再検討して、再計算する必要があります。 
  
## <a name="see-also"></a>関連項目

#### 

[ビジネス サーバー 2015 の Skype のサーバーのメモリ容量制限のためのモニター](server-memory-capacity-limits.md)

