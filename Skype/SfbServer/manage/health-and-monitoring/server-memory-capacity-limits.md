---
title: Skype for Business Server でサーバーのメモリ容量の上限を監視する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 1697ea71-6fcf-480d-b4e9-cd79f94d247e
description: '概要: Skype for Business Server でサーバーのメモリ容量の上限を監視する方法について説明します。'
ms.openlocfilehash: f089ab9b5be693872754691050133ad27e992896
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34279824"
---
# <a name="monitor-for-server-memory-capacity-limits-in-skype-for-business-server"></a>Skype for Business Server でサーバーのメモリ容量の上限を監視する
 
**概要:** Skype for Business Server でサーバーのメモリ容量の上限を監視する方法について説明します。
  
> [!CAUTION]
> このトピックでは、キャパシティ計画を参照している情報は、Lync 2010 モバイルクライアントとモビリティサービス (Mcx) のみに関連しています。 Lync 2013 モバイルクライアントで使用されるユニファイドコミュニケーション Web API (UCWA) のキャパシティ計画は、Lync Server 2013、計画ツールによって提供されます。 

> [!NOTE]
> Skype for Business Server 2019 では、従来のモバイルクライアントに対する MCX (モバイルサービス) のサポートは利用できなくなりました。 現在のすべての Skype for Business のモバイルクライアントでは、インスタントメッセージング (IM)、プレゼンス、連絡先をサポートするために、既にユニファイドコミュニケーション Web API (UCWA) を使用しています。 MCX を使用するレガシクライアントを使っているユーザーは、現在のクライアントにアップグレードする必要があります。
  
2つのモビリティーパフォーマンスカウンターは、現在の使用状況を特定し、Skype for Business Server Mobility Service (Mcx) の容量を計画して、UCWA のメモリ使用量を監視するのに役立ちます。 UCWA では、カウンターカテゴリは**LS: WEB-UCWA**です。 モバイルサービス (Mcx) については、カウンターは "カテゴリ**LS: WEB モバイル通信サービス**" の下にあります。 監視するカウンターは次のとおりです。
  
- **Currently Active Session Count with Active Presence Subscriptions**。これは、UCWA または Mobility Service (Mcx) 経由で登録されたエンドポイントのうち、アクティブなプレゼンス サブスクリプションを持つエンドポイントの現在数 (常時接続されたモバイル ユーザーの数) です。
    
- **Currently Active Session Count**。これは、UCWA または Mobility Service 経由で登録されたエンドポイントの現在数です。
    
**アクティブなセッション数と**現在アクティブな**セッション数**の差が時間の経過と共に小さい場合は、モバイルデバイスのほとんどのユーザーが、Android などの常に接続されたデバイスを使用していることを意味します。Nokia モバイルデバイス (Mcx のみ)。 UCWA 常に接続されたデバイスには、Lync 2013 モバイルクライアントを実行している Apple と Android デバイスが含まれます。 現在アクティブな**セッション数**が、アクティブな**プレゼンスのサブスクリプションによって現在アクティブなセッション数**を超えている場合は、次のように Apple IOS デバイスまたは Windows Phone などのバックグラウンドエンドポイントデバイスを使用しているユーザーが多いことを示しています。Mcx。 (Windows Phone は、これとして登録される唯一の Lync 2013 モバイルクライアントです)。
  
現在アクティブになっている**セッション数**の制限を設定する必要があり**** ます。これには、想定される使用状況、キャパシティ計画の結果、および継続的な監視が含まれます。モビリティサービスおよびその他のフロントエンドサーバーカウンター。 制限を設定することで、キャパシティを超えたときにサーバーの容量を評価し、警告を発生させることができるようになります。
  
適切な制限を決定するには、まず、モビリティサービスのフロントエンドサーバーで利用可能なメモリ量を決定する必要があります。 カウンターを監視し、次の式に従って、追加容量の計画が必要な時期を確認します。
  
Mcx Mobility Service (MB) によって使用された合計メモリ = 164 + (400 + 134)/1024 ***現在アクティブな**セッション400数 **(** - 現在のアクティブなセッション数、現在アクティブなセッション数:**アクティブなプレゼンスサブスクリプション**)
  
> [!IMPORTANT]
> Microsoft Lync Server 2010 キャパシティの計算機は、CPU、メモリ、ハードドライブなど、Skype for Business サーバーの要件を決定するためのすべての数式で事前に用意されたスプレッドシートです。 [スプレッドシートと関連ドキュメントをダウンロード](https://go.microsoft.com/fwlink/p/?LinkID=212657)できます。 
  
フロントエンドサーバーには、フェールオーバーの状況でモビリティサービスをサポートするための十分なメモリが必要です。 フロントエンドサーバーで現在利用可能なメモリを監視するには、 **memory(Available m** ) カウンターを使用するか、前に説明した式を使用して、モビリティサービスで使用する必要のあるメモリ量を計画します。
  
フロントエンドサーバーで利用可能なメモリの量が 1500 MB よりも小さい場合は、モビリティユーザーの想定される数を計画するときに、モビリティサービスをサポートするためにハードウェアを追加する必要があります。 詳細については、操作のドキュメントの「 [Skype For Business Server のパフォーマンスを監視する](monitor-mobility-performance.md)」を参照してください。
  
## <a name="see-also"></a>関連項目

[Skype for Business Server のパフォーマンスを監視する](monitor-mobility-performance.md)
