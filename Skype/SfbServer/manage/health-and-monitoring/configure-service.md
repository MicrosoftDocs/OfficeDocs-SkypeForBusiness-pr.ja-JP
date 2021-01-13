---
title: Skype for Business Server で高パフォーマンスを実現する Mobility Service の構成
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
description: '概要: Skype for Business Server の Mobility Service について学習します。'
ms.openlocfilehash: 83d8d6dc7a32b05a58c738deddc8c92e43bd5557
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817037"
---
# <a name="configure-mobility-service-for-high-performance-in-skype-for-business-server"></a>Skype for Business Server で高パフォーマンスを実現する Mobility Service の構成
 
**概要:** Skype for Business Server の Mobility Service について学習します。
  
> [!IMPORTANT]
> このトピックは Skype for Business Server Mobility Service (Mcx) にのみ適用され、Lync Server 2013 の累積的な更新プログラム (2013 年 2 月) で提供される Unified Communications Web API (UCWA) には適用されません。 
  
Mobility Service (Mcx) をインターネット インフォメーション サービス (IIS) 7.5 にインストールすると、Mobility Service インストーラーはフロント エンド サーバーで一部のパフォーマンス設定を構成します。 モビリティでは IIS 7.5 を使用することをお勧めします。 これらの設定は、同時ユーザー要求の最大数と、Mobility Service で利用できるスレッドの最大数に影響します。
  
パフォーマンス設定を次に示します。
  
### <a name="settings-for-mcx-on-iis-75"></a>IIS 7.5 での Mcx の設定

1. **maxConcurrentThreadsPerCPU** は、ゼロ (0) に設定されます。
    
2. **maxConcurrentRequestsPerCPU** は、ゼロ (0) に設定されます。
    
3. ASP.NET プロセス モデルは、AutoConfig に設定されます (IIS 7.5 のみ)。
    
4. HTTP.sys のキューの制限は 1,000 に設定されます (既定)。
    

