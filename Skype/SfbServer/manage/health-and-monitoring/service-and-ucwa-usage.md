---
title: Skype for Business Server での Mobility Service と UCWA の使用状況の監視
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 8389b37a-ca3e-4047-8b51-85bc07da87e8
description: '概要: Skype for Business Server で Mobility Service (Mcx) と Unified Communications Web API (UCWA) を管理します。'
ms.openlocfilehash: 76bcf8727d3abbb417595f033ce9a59ec00a39ff
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814247"
---
# <a name="monitor-mobility-service-and-ucwa-usage-in-skype-for-business-server"></a>Skype for Business Server での Mobility Service と UCWA の使用状況の監視
 
**概要:** Skype for Business Server で Mobility Service (Mcx) と Unified Communications Web API (UCWA) を管理します。

> [!NOTE]
> 従来のモバイル クライアントの MCX (モビリティ サービス) サポートは、Skype for Business Server 2019 では利用できなくなりました。 現在のすべての Skype for Business モバイル クライアントはUnified Communications Web API (UCWA) を使用して、インスタント メッセージング (IM)、プレゼンス、および連絡先をサポートしています。 MCX を使用している従来のクライアントを持っているユーザーは、現在のクライアントにアップグレードする必要があります。
  
Skype for Business Server Mobility Service (Mcx) および Unified Communications Web API (UCWA) で使用される CPU とメモリを継続的に監視する必要があります。 使用状況を監視するには、以下を使用できます。
  
 **Unified Communications Web API (UCWA) の場合:**
  
- インターネット インフォメーション サービス (IIS) マネージャーの **LyncUcwa** ワーカー プロセス。 [**ワーカー プロセス**] ウィンドウで、[**CPU %**] および [**プライベート バイト (KB)**] (メモリ) の列を確認します。
    
- [**CPU**] および [**プロセッサ**] パフォーマンス カウンター
    
ほとんどの展開では、UCWA CPU 使用率は平均で 15% を下回る必要があります。 メモリ使用量は、Skype for Business Server のサーバー メモリ容量制限の監視で説明 [されている制限の範囲内に入る必要があります](server-memory-capacity-limits.md)。
  
CPU およびメモリ使用量カウンターに加えて、次のパフォーマンス カウンターを使用して、サーバーが要求で過負荷状態にあるかどうかを判断できます。
  
- **LS:WEB - 調整と認証\WEB - サーバー** 上の保留中の Web 要求の数を示す、処理中の要求の総数。 このカウンターが 10,000 に達すると、後続の要求は失敗し、"503 - Service Unavailable" というエラー メッセージが表示されます。
    
- **ASP.NET\Requests Queued** (常にゼロである必要があります)。
    
> [!NOTE]
> これらの値を満たすか、この値を超える場合は、Web サービスをホストするコンピューターの CPU、コア数、およびメモリの適切なサイズ変更に関する容量計画を再検討し、再計算する必要があります。 
  
 **Mobility Service (Mcx) の場合:**
  
- インターネット インフォメーション サービス (IIS) マネージャーの **CSIntMcxAppPool** ワーカー プロセスと **CSExtMcxAppPool** ワーカー プロセス。 [**ワーカー プロセス**] ウィンドウで、[**CPU %**] および [**プライベート バイト (KB)**] (メモリ) の列を確認します。
    
- [**CPU**] および [**プロセッサ**] パフォーマンス カウンター
    
ほとんどの展開では、Mobility Service の CPU 使用率は平均で 15% を下回る必要があります。 メモリ使用量は、Skype for Business Server のサーバー メモリ容量制限の監視で説明 [されている制限の範囲内に入る必要があります](server-memory-capacity-limits.md)。
  
CPU とメモリの使用状況カウンターに加えて、以下の ASP.NET パフォーマンス カウンターを使用すると、サーバーが要求で過負荷になっていないかどうかを確認するのに役立つ場合があります。
  
- **ASP.NET v2.0.50727\Requests Current**。サーバー上の保留中の Web 要求の数を示します。 このカウンターが 5,000 に達すると、後続の要求は失敗し、"503 - サービスを利用できません" というエラー メッセージが表示されます。
    
- **ASP.NET\Requests Queued** (常にゼロである必要があります)。
    
> [!NOTE]
> これらの値を満たすか、この値を超える場合は、Web サービスをホストするコンピューターの CPU、コア数、メモリの適切なサイズ変更について、容量計画を再検討して再コンパイルする必要があります。 

> [!NOTE]
> 従来のモバイル クライアントの MCX (モビリティ サービス) サポートは、Skype for Business Server 2019 では利用できなくなりました。 現在のすべての Skype for Business モバイル クライアントはUnified Communications Web API (UCWA) を使用して、インスタント メッセージング (IM)、プレゼンス、および連絡先をサポートしています。 MCX を使用している従来のクライアントを持っているユーザーは、現在のクライアントにアップグレードする必要があります。
  
## <a name="see-also"></a>関連項目

[Skype for Business Server でサーバーのメモリ容量制限を監視する](server-memory-capacity-limits.md)
