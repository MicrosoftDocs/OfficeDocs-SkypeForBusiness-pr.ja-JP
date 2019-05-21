---
title: Skype for Business Server のパフォーマンスを監視する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9c831c63-9a7d-48ec-9118-f8a7e80ddd04
description: '概要: Skype for Business Server のモビリティサービス (Mcx) とユニファイドコミュニケーション Web API (UCWA) について説明します。'
ms.openlocfilehash: 7b8340d90b5e1fa18c4dfaa7d61f986344ccbb33
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34279922"
---
# <a name="monitor-mobility-for-performance-in-skype-for-business-server"></a>Skype for Business Server のパフォーマンスを監視する
 
**概要:** Skype for Business Server のモビリティサービス (Mcx) とユニファイドコミュニケーション Web API (UCWA) について説明します。
  
Skype for Business Server Mobility Service (Mcx) とユニファイドコミュニケーション Web API (UCWA) では、フロントエンドサーバーとフロントエンドプールの負荷が高くなります。 モバイルアプリケーションが最小化されている場合でもサーバーへの接続を維持するモバイルデバイス (lync 2010 Mobile を実行している Android や Nokia デバイス、Lync 2013 Mobile を実行している Android および Apple デバイスなど) には、高負荷の負荷がかかることがあります。モバイルアプリケーションが最小化されているときに、サーバーとの接続を終了します。 モバイル使用の増加に応じて、容量を増やす必要があるタイミングを判断するために、モビリティのパフォーマンスを監視する必要があります。

> [!NOTE]
> Skype for Business Server 2019 では、従来のモバイルクライアントに対する MCX (モバイルサービス) のサポートは利用できなくなりました。 現在のすべての Skype for Business のモバイルクライアントでは、インスタントメッセージング (IM)、プレゼンス、連絡先をサポートするために、既にユニファイドコミュニケーション Web API (UCWA) を使用しています。 MCX を使用するレガシクライアントを使っているユーザーは、現在のクライアントにアップグレードする必要があります。
  
モビリティのパフォーマンスに影響を与えるいくつかの制限値があります。 
  
- 使用可能なメモリ
    
- 要求キューの制限
    
- 同時接続数
    
- IIS キューの長さ
    
モビリティのパフォーマンスに影響する可能性のある、サーバーへのその他の制限値として、最大 12 の同時サインイン数、認証数、セッションの更新数、および終了数があります。ただし、ほとんどの展開でこれらの最大値を変更する必要はありません。
  
## <a name="in-this-section"></a>このセクションの内容

- [Skype for Business Server でサーバーのメモリ容量の上限を監視する](server-memory-capacity-limits.md)
    
- [Skype for Business Server のモビリティサービスと UCWA の使用状況を監視する](service-and-ucwa-usage.md)
    
- [Skype for Business Server で高パフォーマンスのモビリティサービスを構成する](configure-service.md)
    
- [Skype for Business Server で IIS 要求トレースログファイルを監視する](iis-request-tracing-log-files.md)
    
- [Skype for Business Server のモバイルパフォーマンスカウンター](performance-counters.md)
    

