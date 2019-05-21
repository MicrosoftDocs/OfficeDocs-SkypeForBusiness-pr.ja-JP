---
title: Skype for Business Server で高パフォーマンスのモビリティサービスを構成する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c2b8aadb-cffb-49f0-ba7a-e8541a1ff475
description: '概要: Skype for Business Server のモビリティサービスについて説明します。'
ms.openlocfilehash: 35e04fa080964495ccd9abed28c0688dd7be45a9
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34305844"
---
# <a name="configure-mobility-service-for-high-performance-in-skype-for-business-server"></a>Skype for Business Server で高パフォーマンスのモビリティサービスを構成する
 
**概要:** Skype for Business Server のモビリティサービスについて説明します。
  
> [!IMPORTANT]
> このトピックは、Skype for business server Mobility Service (mcx) にのみ適用され、Lync Server 2013 2013 の累積更新プログラムで提供されるように、統合コミュニケーション Web API (ucwa) には適用されません。 
  
インターネットインフォメーションサービス (IIS) 7.5 にモバイルサービス (Mcx) をインストールすると、Mobility Service installer によって、フロントエンドサーバーの一部のパフォーマンス設定が構成されます。 モビリティでは IIS 7.5 を使用することをお勧めします。 これらの設定は、同時ユーザー要求の最大数と、Mobility Service で利用できるスレッドの最大数に影響します。
  
以下にパフォーマンス設定を示します。
  
### <a name="settings-for-mcx-on-iis-75"></a>IIS 7.5 での Mcx の設定

1. **maxConcurrentThreadsPerCPU** は、ゼロ (0) に設定されます。
    
2. **maxConcurrentRequestsPerCPU** は、ゼロ (0) に設定されます。
    
3. ASP.NET プロセス モデルは、AutoConfig に設定されます (IIS 7.5 のみ)。
    
4. HTTP.sys のキューの制限は 1,000 に設定されます (既定)。
    

