---
title: Skype for Business Server 2015 でのモビリティのパフォーマンスの監視
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9c831c63-9a7d-48ec-9118-f8a7e80ddd04
description: '概要: では、ビジネス サーバー 2015 の Skype のモビリティ サービス (Mcx) とユニファイド コミュニケーション Web API (UCWA) について説明します。'
ms.openlocfilehash: 1981bff8398f3fab9206f9dab748c545268f7edf
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="monitor-mobility-for-performance-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 でのモビリティのパフォーマンスの監視
 
**の概要:**ビジネス サーバー 2015 の Skype のモビリティ サービス (Mcx) とユニファイド コミュニケーション Web API (UCWA) について説明します。
  
ビジネス サーバー移動サービス (Mcx) と、ユニファイド コミュニケーション Web API (UCWA) の Skype では、フロント エンド サーバーとフロント エンド プールの負荷が増加します。 Lync 2013 モバイルを実行しているアプリとアップルのデバイスと同様に Lync 2010 のモバイルを実行している Android および Nokia のデバイスなど、モバイル アプリケーションが最小化されている場合でも、サーバーへの接続を維持するモバイル デバイスがデバイスよりも大きな負荷を課すことモバイル アプリケーションが最小化したときに、サーバーへの接続を終了します。 モビリティの使用量が増えるにつれて、モビリティのパフォーマンス、容量を増やす必要がある場合を決定するを監視する必要があります。
  
モビリティのパフォーマンスに影響を与えるいくつかの制限値があります。 
  
- 使用可能なメモリ
    
- 要求キューの制限
    
- 同時接続数
    
- IIS キューの長さ
    
モビリティのパフォーマンスに影響する可能性のある、サーバーへのその他の制限値として、最大 12 の同時サインイン数、認証数、セッションの更新数、および終了数があります。ただし、ほとんどの展開でこれらの最大値を変更する必要はありません。
  
## <a name="in-this-section"></a>このセクションの内容

- [ビジネス サーバー 2015 の Skype のサーバーのメモリ容量制限のためのモニター](server-memory-capacity-limits.md)
    
- [ビジネス サーバー 2015 の Skype での移動サービスおよび UCWA の使用状況を監視します。](service-and-ucwa-usage.md)
    
- [Skype ビジネス サーバー 2015 の高パフォーマンスのモバイル サービスを構成します。](configure-service.md)
    
- [監視 IIS 要求トレース ログ ファイルでは、Skype ビジネス サーバー 2015 の](iis-request-tracing-log-files.md)
    
- [ビジネス サーバー 2015 の Skype のモビリティ パフォーマンス カウンター](performance-counters.md)
    

