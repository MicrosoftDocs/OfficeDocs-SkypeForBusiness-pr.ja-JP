---
title: サーバーのメモリ容量の制限を監視Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 1697ea71-6fcf-480d-b4e9-cd79f94d247e
description: '概要: サーバーのメモリ容量制限を監視する方法について、Skype for Business Server。'
ms.openlocfilehash: df24f96c8fca1927c1222e2bf42981f5cebf7aac
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/04/2021
ms.locfileid: "60768705"
---
# <a name="monitor-for-server-memory-capacity-limits-in-skype-for-business-server"></a>サーバーのメモリ容量の制限を監視Skype for Business Server
 
**概要:** サーバーのメモリ容量制限を監視する方法については、Skype for Business Server。
  
> [!CAUTION]
> 容量計画を参照するこのトピックの情報は、Lync 2010 Mobile クライアントとモビリティ サービス (Mcx) にのみ関係します。 Lync 2013 Mobile クライアントで使用されるユニファイド コミュニケーション Web API (UCWA) の容量計画は、Lync Server 2013 計画ツールによって提供されます。 

> [!NOTE]
> 従来のモバイル クライアントの MCX (モビリティ サービス) サポートは、Skype for Business Server 2019 では利用できなくなりました。 現在のすべての Skype for Business モバイル クライアントはUnified Communications Web API (UCWA) を使用して、インスタント メッセージング (IM)、プレゼンス、および連絡先をサポートしています。 MCX を使用している従来のクライアントを持っているユーザーは、現在のクライアントにアップグレードする必要があります。
  
2 つのモビリティ パフォーマンス カウンターを使用すると、現在の使用状況を判断し、Skype for Business Server Mobility Service (Mcx) の容量を計画し、UCWA のメモリ使用量を監視するのに役立ちます。 UCWA の場合、カウンター カテゴリは **LS:WEB - UCWA です**。 モビリティ サービス (Mcx) のカウンターは **、LS:WEB - Mobile Communication Service というカテゴリの下にあります**。 監視するカウンターは次のとおりです。
  
- **Active Presence** サブスクリプションを使用した現在アクティブなセッション数 (UCWA またはモビリティ サービス (Mcx) を通じて登録されている現在のエンドポイント数 (常時接続されているモバイル ユーザーの数)
    
- **現在アクティブなセッション数**(UCWA または Mobility Service を通じて登録されているエンドポイントの現在の数)
    
Active **Presence** サブスクリプションを使用する現在アクティブ なセッション数と現在アクティブなセッション数の差が少ない場合、ほとんどのモバイル デバイス ユーザーは、Android や Nokia モバイル デバイス (Mcx のみ) などの常に接続されたデバイスを持っています。 UCWA に常時接続されているデバイスには、Lync 2013 Mobile クライアントを実行している Apple デバイスと Android デバイスが含まれます)。 現在 **アクティブな** セッション数が Active **Presence** サブスクリプションを使用した現在アクティブ なセッション数よりはるかに多い場合は、Apple iOS デバイスや Mcx の下の Windows Phone など、バックグラウンド エンドポイント デバイスを使用しているユーザーが多い場合を示します。 (Windows Phoneとして登録する唯一の Lync 2013 Mobile クライアントです)。
  
期待される使用状況、容量計画結果、およびモビリティ サービスおよび他のフロントエンドサーバー カウンターの継続的な監視に基づいて、[Active **Presence** サブスクリプションを使用して現在アクティブなセッション数] および [現在アクティブなセッション数] パフォーマンス カウンターに制限を設定する必要があります。 制限を設定すると、サーバーの容量を評価し、容量を超えたときにアラートを発生できます。
  
適切な制限を決定するには、まずモビリティ サービスのフロント エンド サーバーで使用可能なメモリの量を確認する必要があります。 カウンターを監視して、次の数式に従って、追加の容量を計画する必要がある場合を判断します。
  
Mcx Mobility Service で使用されるメモリの合計 (MB) = 164 + (400 + 134) / 1024 * Active **Presence** サブスクリプションを使用した現在アクティブなセッション数 + 400 / 1024 * **(** 現在アクティブ なセッション数 アクティブ プレゼンス サブスクリプションを使用して現在アクティブなセッション  -  数 )
  
> [!IMPORTANT]
> Microsoft Lync Server 2010 容量計算機は、CPU、メモリ、ハード ドライブなど、Skype for Business サーバーの要件をプランナーが判断できるすべての数式があらかじめ入力されたスプレッドシートです。 スプレッドシートと [関連するドキュメントをダウンロードできます](https://go.microsoft.com/fwlink/p/?LinkID=212657)。 
  
フロントエンド サーバーには、フェールオーバー状況でモビリティ サービスをサポートするのに十分なメモリが必要です。 フロント エンド サーバーで現在利用可能なメモリを監視するには **、Memory\Available Mbytes** カウンターを使用するか、前述の数式を使用して、Mobility Service が使用するメモリ量を計画します。
  
必要なモビリティ ユーザー数を計画する際に、フロント エンド サーバーで使用可能なメモリ量が 1,500 MB 未満の場合は、モビリティ サービスをサポートするためにハードウェアを追加する必要があります。 詳細については、「Operations」のドキュメントの「パフォーマンスを監視[Skype for Business Server」](monitor-mobility-performance.md)を参照してください。
  
## <a name="see-also"></a>関連項目

[モバイル のパフォーマンスを監視Skype for Business Server](monitor-mobility-performance.md)
