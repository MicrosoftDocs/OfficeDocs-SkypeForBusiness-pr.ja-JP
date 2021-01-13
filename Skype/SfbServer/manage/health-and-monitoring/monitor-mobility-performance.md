---
title: Skype for Business Server でモビリティのパフォーマンスを監視する
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
ms.assetid: 9c831c63-9a7d-48ec-9118-f8a7e80ddd04
description: '概要: Skype for Business Server の Mobility Service (Mcx) と Unified Communications Web API (UCWA) について説明します。'
ms.openlocfilehash: d7473d22f2de0576bf6214ae43719c8bfc70d49a
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816837"
---
# <a name="monitor-mobility-for-performance-in-skype-for-business-server"></a>Skype for Business Server でモビリティのパフォーマンスを監視する
 
**概要:** Skype for Business Server の Mobility Service (Mcx) と Unified Communications Web API (UCWA) について説明します。
  
Skype for Business Server Mobility Service (Mcx) および Unified Communications Web API (UCWA) を使用すると、フロントエンド サーバーとフロントエンド プールの負荷が増加します。 Lync 2010 Mobile を実行している Android デバイスや Nokia デバイス、および Lync 2013 Mobile を実行している Android デバイスや Apple デバイスなど、モバイル アプリケーションが最小化されている場合でも、サーバーへの接続を維持するモバイル デバイスは、モバイル アプリケーションが最小化されているときにサーバーへの接続を終了するデバイスよりも大きな負荷を課します。 モビリティの使用が増加するに応じて、モビリティのパフォーマンスを監視して、容量を増やす必要がある場合を判断する必要があります。

> [!NOTE]
> 従来のモバイル クライアントの MCX (モビリティ サービス) サポートは、Skype for Business Server 2019 では利用できなくなりました。 現在のすべての Skype for Business モバイル クライアントはUnified Communications Web API (UCWA) を使用して、インスタント メッセージング (IM)、プレゼンス、および連絡先をサポートしています。 MCX を使用している従来のクライアントを持っているユーザーは、現在のクライアントにアップグレードする必要があります。
  
モビリティのパフォーマンスに影響を与えるいくつかの制限値があります。 
  
- 使用可能なメモリ
    
- 要求キューの制限
    
- 同時接続数
    
- IIS キューの長さ
    
モビリティのパフォーマンスに影響を与える可能性があるサーバーのその他の制限は、最大 12 の同時サインイン、認証、セッションの更新、および終了です。 ただし、ほとんどの展開でこれらの最大値を変更する必要はありません。
  
## <a name="in-this-section"></a>このセクションの内容

- [Skype for Business Server でサーバーのメモリ容量制限を監視する](server-memory-capacity-limits.md)
    
- [Skype for Business Server での Mobility Service と UCWA の使用状況の監視](service-and-ucwa-usage.md)
    
- [Skype for Business Server で高パフォーマンスを実現する Mobility Service の構成](configure-service.md)
    
- [Skype for Business Server での IIS 要求トレース ログ ファイルの監視](iis-request-tracing-log-files.md)
    
- [Skype for Business Server のモビリティ パフォーマンス カウンター](performance-counters.md)
    

