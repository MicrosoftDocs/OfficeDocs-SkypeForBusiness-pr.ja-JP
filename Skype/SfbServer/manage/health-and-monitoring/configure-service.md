---
title: Skype のビジネス サーバー用の高パフォーマンスのモバイル サービスを構成します。
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c2b8aadb-cffb-49f0-ba7a-e8541a1ff475
description: '概要: は、ビジネスのサーバーの Skype では、モビリティ サービスについて説明します。'
ms.openlocfilehash: 3e3f0df7550a64236335108453f0c35d902a1713
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32197493"
---
# <a name="configure-mobility-service-for-high-performance-in-skype-for-business-server"></a>Skype のビジネス サーバー用の高パフォーマンスのモバイル サービスを構成します。
 
**の概要:** ビジネス サーバーは、Skype のモビリティ サービスについて説明します。
  
> [!IMPORTANT]
> このトピックは、ビジネス サーバー移動サービス (Mcx) の Skype にのみ適用し、Lync Server 2013 の累積的な更新プログラムで提供されるようにユニファイド コミュニケーション Web API (UCWA) では適用されません: 年 2013年 2 月。 
  
モビリティ サービス (Mcx) では、インターネット インフォメーション サービス (IIS) 7.5 をインストールするとモビリティ サービスのインストーラーは、フロント エンド サーバー上でいくつかのパフォーマンス設定を構成します。 モビリティでは IIS 7.5 を使用することをお勧めします。 これらの設定は、同時ユーザー要求の最大数と、Mobility Service で利用できるスレッドの最大数に影響します。
  
以下にパフォーマンス設定を示します。
  
### <a name="settings-for-mcx-on-iis-75"></a>IIS 7.5 での Mcx の設定

1. **maxConcurrentThreadsPerCPU** は、ゼロ (0) に設定されます。
    
2. **maxConcurrentRequestsPerCPU** は、ゼロ (0) に設定されます。
    
3. ASP.NET プロセス モデルは、AutoConfig に設定されます (IIS 7.5 のみ)。
    
4. HTTP.sys のキューの制限は 1,000 に設定されます (既定)。
    

