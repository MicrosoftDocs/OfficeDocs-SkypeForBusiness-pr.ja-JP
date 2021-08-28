---
title: モビリティ サービスと UCWA の使用状況を監視Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 8389b37a-ca3e-4047-8b51-85bc07da87e8
description: '概要: モビリティ サービス (Mcx) とユニファイド コミュニケーション Web API (UCWA) を管理Skype for Business Server。'
ms.openlocfilehash: a9cc79e523c3ba6671df302d844dc5e05d3bae28
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2021
ms.locfileid: "58608164"
---
# <a name="monitor-mobility-service-and-ucwa-usage-in-skype-for-business-server"></a>モビリティ サービスと UCWA の使用状況を監視Skype for Business Server
 
**概要:** モビリティ サービス (Mcx) とユニファイド コミュニケーション Web API (UCWA) を管理Skype for Business Server。

> [!NOTE]
> 従来のモバイル クライアントの MCX (モビリティ サービス) サポートは、Skype for Business Server 2019 では利用できなくなりました。 現在のすべての Skype for Business モバイル クライアントはUnified Communications Web API (UCWA) を使用して、インスタント メッセージング (IM)、プレゼンス、および連絡先をサポートしています。 MCX を使用している従来のクライアントを持っているユーザーは、現在のクライアントにアップグレードする必要があります。
  
継続的に、Skype for Business Server Mobility Service (Mcx) とユニファイド コミュニケーション Web API (UCWA) によって使用される CPU とメモリを監視する必要があります。 使用状況を監視するには、次の値を使用できます。
  
 **ユニファイド コミュニケーション Web API (UCWA) の場合:**
  
- **LyncUcwa ワーカー** プロセスは、インターネット インフォメーション サービス (IIS) マネージャーで行います。 [**ワーカー プロセス**] ウィンドウで、[**CPU %**] および [**プライベート バイト (KB)**] (メモリ) の列を確認します。
    
- [**CPU**] および [**プロセッサ**] パフォーマンス カウンター
    
ほとんどの展開では、UCWA CPU 使用率は平均で 15% を下回る必要があります。 メモリ使用量は、「サーバーのメモリ容量制限を監視する」で説明されている制限内[Skype for Business Server。](server-memory-capacity-limits.md)
  
CPU およびメモリ使用率カウンターに加えて、次のパフォーマンス カウンターを使用して、サーバーが要求で過負荷状態である場合の判断に役立ちます。
  
- **LS:WEB - 調整と認証\WEB -** サーバー上の保留中の Web 要求の数を示す[処理] の要求の合計。 このカウンターが 10,000 に達すると、後続の要求は失敗し、「503 - サービスが利用できません」というエラー メッセージが表示されます。
    
- **ASP.NET\Requests Queued** (常にゼロである必要があります)。
    
> [!NOTE]
> これらの値を満たすか超過した場合は、Web サービスをホストするコンピューターの CPU、コア数、メモリの適切なサイズ変更のために、容量計画を再検討して計算しなおす必要があります。 
  
 **モビリティ サービス (Mcx) の場合:**
  
- **CSIntMcxAppPool および** **CSExtMcxAppPool** ワーカー プロセスは、インターネット インフォメーション サービス (IIS) マネージャーで処理します。 [**ワーカー プロセス**] ウィンドウで、[**CPU %**] および [**プライベート バイト (KB)**] (メモリ) の列を確認します。
    
- [**CPU**] および [**プロセッサ**] パフォーマンス カウンター
    
ほとんどの展開では、Mobility Service の CPU 使用率は平均で 15% を下回る必要があります。 メモリ使用量は、「サーバーのメモリ容量制限を監視する」で説明されている制限内[Skype for Business Server。](server-memory-capacity-limits.md)
  
CPU とメモリの使用状況カウンターに加えて、以下の ASP.NET パフォーマンス カウンターを使用すると、サーバーが要求で過負荷になっていないかどうかを確認するのに役立つ場合があります。
  
- **ASP.NET v2.0.50727\Requests Current**(サーバー上の保留中の Web 要求の数を示します)。 このカウンターが 5,000 に達すると、後続の要求が失敗し、「503 - サービスが利用できません」というエラー メッセージが表示されます。
    
- **ASP.NET\Requests Queued** (常にゼロである必要があります)。
    
> [!NOTE]
> これらの値を満たすか超えた場合は、Web サービスをホストするコンピューターの CPU、コア数、およびメモリの適切なサイズ変更のために、容量計画を再検討して再計算する必要があります。 

> [!NOTE]
> 従来のモバイル クライアントの MCX (モビリティ サービス) サポートは、Skype for Business Server 2019 では利用できなくなりました。 現在のすべての Skype for Business モバイル クライアントはUnified Communications Web API (UCWA) を使用して、インスタント メッセージング (IM)、プレゼンス、および連絡先をサポートしています。 MCX を使用している従来のクライアントを持っているユーザーは、現在のクライアントにアップグレードする必要があります。
  
## <a name="see-also"></a>関連項目

[サーバーのメモリ容量の制限を監視Skype for Business Server](server-memory-capacity-limits.md)
