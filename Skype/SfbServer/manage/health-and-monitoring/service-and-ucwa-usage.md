---
title: Skype for Business Server のモビリティサービスと UCWA の使用状況を監視する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 8389b37a-ca3e-4047-8b51-85bc07da87e8
description: '概要: Skype for Business Server のモビリティサービス (Mcx) とユニファイドコミュニケーション Web API (UCWA) を管理します。'
ms.openlocfilehash: 7c41e92b144e1bd4d198c5e9d9f90913ce41400e
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817686"
---
# <a name="monitor-mobility-service-and-ucwa-usage-in-skype-for-business-server"></a>Skype for Business Server のモビリティサービスと UCWA の使用状況を監視する
 
**概要:** Skype for Business Server のモビリティサービス (Mcx) とユニファイドコミュニケーション Web API (UCWA) を管理します。

> [!NOTE]
> Skype for Business Server 2019 では、従来のモバイルクライアントに対する MCX (モバイルサービス) のサポートは利用できなくなりました。 現在のすべての Skype for Business のモバイルクライアントでは、インスタントメッセージング (IM)、プレゼンス、連絡先をサポートするために、既にユニファイドコミュニケーション Web API (UCWA) を使用しています。 MCX を使用するレガシクライアントを使っているユーザーは、現在のクライアントにアップグレードする必要があります。
  
継続的に、Skype for Business Server Mobility Service (Mcx) とユニファイドコミュニケーション Web API (UCWA) で使用されている CPU とメモリを監視する必要があります。 使用状況を監視するには、次の操作を行います。
  
 **Unified Communications Web API (UCWA):**
  
- インターネットインフォメーションサービス (IIS) マネージャーでの**LyncUcwa** worker プロセス。 [**ワーカー プロセス**] ウィンドウで、[**CPU %**] および [**プライベート バイト (KB)**] (メモリ) の列を確認します。
    
- [**CPU**] および [**プロセッサ**] パフォーマンス カウンター。
    
ほとんどの展開で、UCWA の CPU 使用率は平均で 15% を下回っている必要があります。 メモリ使用量は、「 [Skype For Business server のサーバーメモリ容量の上限](server-memory-capacity-limits.md)」に記載されている制限内に収まっている必要があります。
  
CPU とメモリの使用状況カウンターに加えて、以下のパフォーマンス カウンターを使用すると、サーバーが要求で過負荷になっていないかどうかを確認するのに役立つ場合があります。
  
- **LS: web の調整と Authentication\WEB-処理中の要求合計**。サーバー上の保留中の WEB 要求の数を示します。 このカウンターが1万に達すると、その後の要求は失敗し、"503-サービスを利用できません" というエラーメッセージが表示されます。
    
- **ASP.NET\Requests Queued** (常にゼロである必要があります)。
    
> [!NOTE]
> これらの値に達するか、これらの値を超えた場合、Web サービスをホストしているコンピューターの CPU、コア数、およびメモリの適切な規模設定の容量計画を再検討して、再計算する必要があります。 
  
 **Mobility Service (Mcx):**
  
- **Csintmcxapppool**と**csextmcxapppool**ワーカープロセス (インターネットインフォメーションサービス (IIS) マネージャー)。 [**ワーカー プロセス**] ウィンドウで、[**CPU %**] および [**プライベート バイト (KB)**] (メモリ) の列を確認します。
    
- [**CPU**] および [**プロセッサ**] パフォーマンス カウンター。
    
ほとんどの展開で、Mobility Service の CPU 使用率は平均で 15% を下回っている必要があります。 メモリ使用量は、「 [Skype For Business server のサーバーメモリ容量の上限](server-memory-capacity-limits.md)」に記載されている制限内に収まっている必要があります。
  
CPU とメモリの使用状況カウンターに加えて、以下の ASP.NET パフォーマンス カウンターを使用すると、サーバーが要求で過負荷になっていないかどうかを確認するのに役立つ場合があります。
  
- **ASP.NET v 2.0.50727 \ 要求電流**は、サーバー上の保留中の web 要求の数を示します。 このカウンターが5000に達すると、その後の要求は失敗し、"503-サービスを利用できません" というエラーメッセージが表示されます。
    
- **ASP.NET\Requests Queued** (常にゼロである必要があります)。
    
> [!NOTE]
> これらの値に達するか、これらの値を超えた場合、Web サービスをホストしているコンピューターの CPU、コア数、およびメモリの適切な規模設定の容量計画を再検討して、再計算する必要があります。 

> [!NOTE]
> Skype for Business Server 2019 では、従来のモバイルクライアントに対する MCX (モバイルサービス) のサポートは利用できなくなりました。 現在のすべての Skype for Business のモバイルクライアントでは、インスタントメッセージング (IM)、プレゼンス、連絡先をサポートするために、既にユニファイドコミュニケーション Web API (UCWA) を使用しています。 MCX を使用するレガシクライアントを使っているユーザーは、現在のクライアントにアップグレードする必要があります。
  
## <a name="see-also"></a>関連項目

[Skype for Business Server でサーバーのメモリ容量の上限を監視する](server-memory-capacity-limits.md)
