---
title: Microsoft Teams Rooms リファレンス
author: donnah007
ms.author: v-donnahill
manager: serdars
ms.reviewer: ''
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- m365initiative-meetings
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: 参考資料
f1keywords: ''
ms.openlocfilehash: 5f3b23078f29cba82809b5ef22440dd0ddf838fb
ms.sourcegitcommit: 268660f101609852f02f3f9d1a8436f2a99dade7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/19/2022
ms.locfileid: "62071025"
---
# <a name="managing-room-software-stack"></a>Room ソフトウェア スタックの管理  
すべての部屋で、ソフトウェア スタックのさまざまな部分がすべて連携してエクスペリエンスを提供します。 高いレベルでは、次のようにまとめることができます。 

![ソフトウェア スタックの概要のスクリーンショット](../media/update-management-006.jpg)

すべての部屋で毎日良い会議エクスペリエンスを実現するには、各会議室で実行 **されているすべてのソフトウェアを標準化** し、構成に応じて部屋で修正プログラムを展開することが重要です。 また、お客様が保留中の修正に対する信頼を得るために独自の検証プロセスを設定し、組織が変更の準備を整えるために、発生している可能性のある問題が本当に修正されていることを確認したり、機能をプレビューしたりするのも一般的です。  

Managed Services for Microsoft Teams Rooms では、更新プログラムの取得や更新に関する問題のトラブルシューティングについて心配する必要がないように、上記をすべて処理します。 このセクションでは、マネージド ソフトウェア更新プログラムのしくみについて説明します。  

## <a name="managing-to-a-good-state"></a>良好な状態に管理する 
私たちの主な目標は、会議室を実行し、組織で利用できるようにすることです。 マネージド サービスの専門家は、運用ルームの更新プログラムをキュレーション、検証、デプロイするために、常にお客様の代わりに取り組んでいます。 場合によっては、ロールアウトする前に検証する新機能やリリースよりも部屋の正常性に優先順位を付けることを意味する場合があります。

最も重要なのは、これらの更新プログラムの詳細を学習し、自分で検証するために時間を投資する必要がないことを意味します。 特定の更新プログラムや特定の部屋に問題がある場合は、お客様と連携してトラブルシューティングと解決を行います。  

そのため、更新プログラムをロールアウトするプロセスは、次のように分類できます。

- Managed Services チームは、更新プログラムを事前に特定して検証し、環境へのリリースを促進します。
- ルームに配信される更新プログラムは、競合や相互作用を回避するように注文され、通常の営業時間を回避するようにスケジュールされます。
- リング システムを使用すると、足回りを行わなくても、ルームに適用されている更新プログラムを把握できます。
- Managed Services は、更新プログラムを監視し、問題をフォローアップし、解決するためにお客様と協力するよう、ルームオペレーション センターに自動的に通知します。
