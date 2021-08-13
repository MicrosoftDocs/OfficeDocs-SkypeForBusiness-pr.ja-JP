---
title: モビリティ サービスを構成して、パフォーマンスを高Skype for Business Server
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
ms.assetid: c2b8aadb-cffb-49f0-ba7a-e8541a1ff475
description: '概要: モビリティ サービスの詳細については、Skype for Business Server。'
ms.openlocfilehash: 3029877aa6f252ada9bbb38bca0148b8a96908ad5cf4deded7cf48e6451ec833
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "54298137"
---
# <a name="configure-mobility-service-for-high-performance-in-skype-for-business-server"></a>モビリティ サービスを構成して、パフォーマンスを高Skype for Business Server
 
**概要:** モビリティ サービスの詳細については、Skype for Business Server。
  
> [!IMPORTANT]
> このトピックは Skype for Business Server Mobility Service (Mcx) にのみ適用され、Lync Server 2013 の累積的な更新プログラム: 2013 年 2 月に配信されるユニファイド コミュニケーション Web API (UCWA) には適用されません。 
  
モビリティ サービス (Mcx) を インターネット インフォメーション サービス (IIS) 7.5 にインストールすると、Mobility Service インストーラーはフロントエンド サーバーでパフォーマンス設定を構成します。 モビリティでは IIS 7.5 を使用することをお勧めします。 これらの設定は、同時ユーザー要求の最大数と、Mobility Service で利用できるスレッドの最大数に影響します。
  
パフォーマンス設定は次のとおりです。
  
### <a name="settings-for-mcx-on-iis-75"></a>設定 7.5 の Mcx の詳細

1. **maxConcurrentThreadsPerCPU** は、ゼロ (0) に設定されます。
    
2. **maxConcurrentRequestsPerCPU** は、ゼロ (0) に設定されます。
    
3. ASP.NET プロセス モデルは、AutoConfig に設定されます (IIS 7.5 のみ)。
    
4. HTTP.sys のキューの制限は 1,000 に設定されます (既定)。
    

