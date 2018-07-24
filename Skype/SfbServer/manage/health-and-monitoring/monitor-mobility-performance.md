---
title: Skype でのパフォーマンスをビジネスのサーバーの移動を監視します。
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9c831c63-9a7d-48ec-9118-f8a7e80ddd04
description: '概要: は、ビジネスのサーバーに、モビリティ サービス (Mcx)、Skype では、ユニファイド コミュニケーション Web API (UCWA) について説明します。'
ms.openlocfilehash: 4affcb532697f24c87d62e18fc26552639dc00e1
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/24/2018
ms.locfileid: "20990638"
---
# <a name="monitor-mobility-for-performance-in-skype-for-business-server"></a>Skype でのパフォーマンスをビジネスのサーバーの移動を監視します。
 
**の概要:** Business Server には、モビリティ サービス (Mcx)、Skype では、ユニファイド コミュニケーション Web API (UCWA) について説明します。
  
ビジネス サーバー移動サービス (Mcx) と、ユニファイド コミュニケーション Web API (UCWA) の Skype では、フロント エンド サーバーとフロント エンド プールの負荷が増加します。 Lync 2013 モバイルを実行しているアプリとアップルのデバイスと同様に Lync 2010 のモバイルを実行している Android および Nokia のデバイスなど、モバイル アプリケーションが最小化されている場合でも、サーバーへの接続を維持するモバイル デバイスがデバイスよりも大きな負荷を課すことモバイル アプリケーションが最小化したときに、サーバーへの接続を終了します。 モビリティの使用量が増えるにつれて、モビリティのパフォーマンス、容量を増やす必要がある場合を決定するを監視する必要があります。

> [!NOTE]
> 従来のモバイル クライアント用の MCX サポートはビジネス サーバー 2019 の Skype で利用可能ではありません。 ユーザーは、現在のクライアントにアップグレードする必要があります。
  
モビリティのパフォーマンスに影響を与えるいくつかの制限値があります。 
  
- 使用可能なメモリ
    
- 要求キューの制限
    
- 同時接続数
    
- IIS キューの長さ
    
モビリティのパフォーマンスに影響する可能性のある、サーバーへのその他の制限値として、最大 12 の同時サインイン数、認証数、セッションの更新数、および終了数があります。ただし、ほとんどの展開でこれらの最大値を変更する必要はありません。
  
## <a name="in-this-section"></a>このセクションの内容

- [Skype ビジネス サーバー用にサーバーのメモリ容量制限のためのモニター](server-memory-capacity-limits.md)
    
- [ビジネス サーバーの Skype での移動サービスおよび UCWA の使用状況を監視します。](service-and-ucwa-usage.md)
    
- [Skype のビジネス サーバー用の高パフォーマンスのモバイル サービスを構成します。](configure-service.md)
    
- [Skype 内のログ ファイルのトレースをビジネスのサーバーを IIS 要求を監視します。](iis-request-tracing-log-files.md)
    
- [Skype ビジネス サーバーの移動のパフォーマンス カウンター](performance-counters.md)
    

