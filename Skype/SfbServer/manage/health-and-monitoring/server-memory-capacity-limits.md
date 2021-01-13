---
title: Skype for Business Server でサーバーのメモリ容量制限を監視する
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
ms.assetid: 1697ea71-6fcf-480d-b4e9-cd79f94d247e
description: '概要: Skype for Business Server でサーバーのメモリ容量制限を監視する方法について学習します。'
ms.openlocfilehash: f1423d840fdf690332081a8083617c3a072b373c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814297"
---
# <a name="monitor-for-server-memory-capacity-limits-in-skype-for-business-server"></a>Skype for Business Server でサーバーのメモリ容量制限を監視する
 
**概要:** Skype for Business Server でサーバーのメモリ容量制限を監視する方法について学習します。
  
> [!CAUTION]
> 容量計画に関するこのトピックの情報は、Lync 2010 Mobile クライアントおよび Mobility Service (Mcx) にのみ関係します。 Lync 2013 Mobile クライアントで使用される Unified Communications Web API (UCWA) の容量計画は、Lync Server 2013 計画ツールによって提供されます。 

> [!NOTE]
> 従来のモバイル クライアントの MCX (モビリティ サービス) サポートは、Skype for Business Server 2019 では利用できなくなりました。 現在のすべての Skype for Business モバイル クライアントはUnified Communications Web API (UCWA) を使用して、インスタント メッセージング (IM)、プレゼンス、および連絡先をサポートしています。 MCX を使用している従来のクライアントを持っているユーザーは、現在のクライアントにアップグレードする必要があります。
  
2 つのモビリティ パフォーマンス カウンターを使用すると、現在の使用状況を判断し、Skype for Business Server Mobility Service (Mcx) の容量を計画し、UCWA のメモリ使用量を監視するのに役立ちます。 UCWA の場合、カウンター カテゴリは **LS:WEB - UCWA です**。 Mobility Service (Mcx) のカウンターは **、LS:WEB - Mobile Communication Service のカテゴリに含まれています**。 監視するカウンターは次のとおりです。
  
- **Currently Active Session Count with Active Presence Subscriptions**,これは、UCWA または Mobility Service (Mcx) を通じて登録された、アクティブなプレゼンス サブスクリプションを持つエンドポイントの現在の数 (常時接続されたモバイル ユーザーの数) です。
    
- **Currently Active Session Count**(UCWA または Mobility Service 経由で登録された現在のエンドポイント数)
    
アクティブ プレゼンス サブスクリプションを使用した **Currently Active Session Count** と Currently Active Session **Count** の差が時間のかかると小さい場合、ほとんどのモバイル デバイス ユーザーは Android や Nokia モバイル デバイスなどの常時接続されたデバイスを持っています (Mcx の場合のみ)。 UCWA の常時接続デバイスには、Lync 2013 Mobile クライアントを実行している Apple デバイスと Android デバイスが含まれます。 現在アクティブなセッション数が、Active **Presence Subscription** を使用した Currently Active Session Count よりもずっと多い場合、より多くのユーザーがバックグラウンド エンドポイント デバイス (Apple iOS デバイスや Mcx の Windows Phone など) を使用している場合を示します。 (Windows Phone は、これを登録する唯一の Lync 2013 Mobile クライアントです)。
  
予想される使用状況、容量計画の結果、および Mobility Service および他のフロントエンド サーバー カウンターの継続的な監視に基づいて、[Currently **Active Session Count with Active Presence Subscriptions]** および **[Currently Active Session Count]** パフォーマンス カウンターに制限を設定する必要があります。 制限を設定すると、サーバーの容量を評価し、容量を超えたときにアラートを発生できます。
  
適切な制限を決定するには、まず Mobility Service のフロント エンド サーバーで使用可能なメモリ容量を確認する必要があります。 カウンターを監視し、次の式に従って、追加容量を計画する必要がある場合を判断します。
  
Mcx Mobility Service が使用する合計メモリ (MB) = 164 + (400 + 134) / 1024 * Currently **Active Session Count with Active Presence Subscriptions** + 400 / 1024 * ( Currently Active Session Count Currently Active Session **Count** with Active  -  **Presence Subscriptions**)
  
> [!IMPORTANT]
> Microsoft Lync Server 2010 Capacity Calculator は、CPU、メモリ、ハード ドライブなど、Skype for Business サーバーの要件をプランナーが判断できるすべての数式が事前に入力されたスプレッドシートです。 スプレッドシートと [関連するドキュメントをダウンロードできます](https://go.microsoft.com/fwlink/p/?LinkID=212657)。 
  
フロントエンド サーバーには、フェールオーバーの状況で Mobility Service をサポートするのに十分なメモリが必要です。 フロント エンド サーバーで現在使用可能なメモリを監視するには **、Memory\Available Mbytes** カウンターを使用するか、前述の式を使用して、Mobility Service で使用するメモリ容量を計画します。
  
予想されるモビリティ ユーザー数を計画するときにフロント エンド サーバーで使用可能なメモリ容量が 1,500 MB 未満の場合は、Mobility Service をサポートするためにハードウェアを追加する必要があります。 詳細については、「操作」のドキュメントの [「Skype for Business Server](monitor-mobility-performance.md) のモビリティでパフォーマンスを監視する」を参照してください。
  
## <a name="see-also"></a>関連項目

[Skype for Business Server でモビリティのパフォーマンスを監視する](monitor-mobility-performance.md)
