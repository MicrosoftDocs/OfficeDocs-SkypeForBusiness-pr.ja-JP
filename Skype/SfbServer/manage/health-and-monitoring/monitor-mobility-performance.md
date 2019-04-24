---
title: Skype でのパフォーマンスをビジネスのサーバーの移動を監視します。
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9c831c63-9a7d-48ec-9118-f8a7e80ddd04
description: '概要: は、ビジネスのサーバーに、モビリティ サービス (Mcx)、Skype では、ユニファイド コミュニケーション Web API (UCWA) について説明します。'
ms.openlocfilehash: 476d03fa17cad163fa9426ca35853cfe29f87bb1
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32199729"
---
# <a name="monitor-mobility-for-performance-in-skype-for-business-server"></a>Skype でのパフォーマンスをビジネスのサーバーの移動を監視します。
 
**の概要:** Business Server には、モビリティ サービス (Mcx)、Skype では、ユニファイド コミュニケーション Web API (UCWA) について説明します。
  
ビジネス サーバー移動サービス (Mcx) と、ユニファイド コミュニケーション Web API (UCWA) の Skype では、フロント エンド サーバーとフロント エンド プールの負荷が増加します。 Lync 2013 モバイルを実行しているアプリとアップルのデバイスと同様に Lync 2010 のモバイルを実行している Android および Nokia のデバイスなど、モバイル アプリケーションが最小化されている場合でも、サーバーへの接続を維持するモバイル デバイスがデバイスよりも大きな負荷を課すことモバイル アプリケーションが最小化したときに、サーバーへの接続を終了します。 モビリティの使用量が増えるにつれて、モビリティのパフォーマンス、容量を増やす必要がある場合を決定するを監視する必要があります。

> [!NOTE]
> 従来のモバイル クライアント用の MCX (移動サービス) サポートがビジネス サーバー 2019 の Skype で利用可能ではありません。 ビジネスのモバイル クライアントのすべての現在 Skype は、インスタント メッセージング (IM)、プレゼンス、および取引先担当者をサポートするために既にユニファイド コミュニケーション Web API (UCWA) を使用します。 MCX を使用する従来のクライアントを持つユーザーは、現在のクライアントにアップグレードする必要があります。
  
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
    

