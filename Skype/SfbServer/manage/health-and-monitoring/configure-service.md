---
title: Skype for Business Server 2015 での高いパフォーマンスを実現する Mobility Service の構成
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c2b8aadb-cffb-49f0-ba7a-e8541a1ff475
description: '概要: は、ビジネス サーバー 2015 の Skype では、モビリティ サービスについて説明します。'
ms.openlocfilehash: 12f64ed75195bb94365686d76cdfca841e6c9c8e
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="configure-mobility-service-for-high-performance-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 での高いパフォーマンスを実現する Mobility Service の構成
 
**の概要:**ビジネス サーバー 2015、Skype では、モビリティ サービスについて説明します。
  
> [!IMPORTANT]
> このトピックは、ビジネス サーバー 2015 モビリティ サービス (Mcx) を Skype にのみ適用され、Lync Server 2013 の累積的な更新プログラムで提供されるようにユニファイド コミュニケーション Web API (UCWA) では適用されません: 年 2013年 2 月。 
  
モビリティ サービス (Mcx) では、インターネット インフォメーション サービス (IIS) 7.5 をインストールするとモビリティ サービスのインストーラーは、フロント エンド サーバー上でいくつかのパフォーマンス設定を構成します。 モビリティでは IIS 7.5 を使用することをお勧めします。 これらの設定は、同時ユーザー要求の最大数と、Mobility Service で利用できるスレッドの最大数に影響します。
  
以下にパフォーマンス設定を示します。
  
### <a name="settings-for-mcx-on-iis-75"></a>IIS 7.5 での Mcx の設定

1. **maxConcurrentThreadsPerCPU**は、ゼロ (0) に設定されています。
    
2. **maxConcurrentRequestsPerCPU**は、ゼロ (0) に設定されています。
    
3. ASP.NET プロセス モデルは、AutoConfig に設定されます (IIS 7.5 のみ)。
    
4. HTTP.sys のキューの制限は 1,000 に設定されます (既定)。
    

