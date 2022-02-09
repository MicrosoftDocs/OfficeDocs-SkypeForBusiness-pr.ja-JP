---
title: モバイル のパフォーマンスを監視Skype for Business Server
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 9c831c63-9a7d-48ec-9118-f8a7e80ddd04
description: '概要: モビリティ サービス (Mcx) とユニファイド コミュニケーション Web API (UCWA) Skype for Business Server。'
ms.openlocfilehash: 57f892c06c1db979463385715d8c941b92e5d739
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/05/2022
ms.locfileid: "62416550"
---
# <a name="monitor-mobility-for-performance-in-skype-for-business-server"></a>モバイル のパフォーマンスを監視Skype for Business Server
 
**概要:** モビリティ サービス (Mcx) とユニファイド コミュニケーション Web API (UCWA) の詳細については、Skype for Business Server。
  
モバイル Skype for Business Server サービス (Mcx) とユニファイド コミュニケーション Web API (UCWA) は、フロントエンド サーバーとフロントエンド プールの負荷を増加します。 Lync 2010 Mobile を実行している Android デバイスや Nokia デバイス、Lync 2013 Mobile を実行している Android デバイスや Apple デバイスなど、モバイル アプリケーションが最小化された場合でも、サーバーへの接続を維持するモバイル デバイスは、モバイル アプリケーションが最小化された場合にサーバーへの接続を終了するデバイスよりも大きな負荷を課します。 モビリティの使用状況が増加するに応じて、モビリティのパフォーマンスを監視して、容量を増やす必要がある場合を判断する必要があります。

> [!NOTE]
> 従来のモバイル クライアントの MCX (モビリティ サービス) サポートは、Skype for Business Server 2019 では利用できなくなりました。 現在のすべての Skype for Business モバイル クライアントはUnified Communications Web API (UCWA) を使用して、インスタント メッセージング (IM)、プレゼンス、および連絡先をサポートしています。 MCX を使用している従来のクライアントを持っているユーザーは、現在のクライアントにアップグレードする必要があります。
  
モビリティのパフォーマンスに影響を与えるいくつかの制限値があります。 
  
- 使用可能なメモリ
    
- 要求キューの制限
    
- 同時接続数
    
- IIS キューの長さ
    
モビリティのパフォーマンスに影響を与える可能性があるサーバーのその他の制限は、最大 12 の同時サインイン、認証、セッション更新、および終了です。 ただし、ほとんどの展開でこれらの最大値を変更する必要はありません。
  
## <a name="in-this-section"></a>このセクションの内容

- [サーバーのメモリ容量の制限を監視Skype for Business Server](server-memory-capacity-limits.md)
    
- [モビリティ サービスと UCWA の使用状況を監視Skype for Business Server](service-and-ucwa-usage.md)
    
- [モビリティ サービスを構成して、パフォーマンスを高Skype for Business Server](configure-service.md)
    
- [IIS 要求トレース ログ ファイルを監視するSkype for Business Server](iis-request-tracing-log-files.md)
    
- [モバイル パフォーマンス カウンター (Skype for Business Server](performance-counters.md)
    

