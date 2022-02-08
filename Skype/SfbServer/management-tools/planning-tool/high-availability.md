---
title: 高可用性パン ツール
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 4/8/2016
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.plan.HighAvailability
- ms.lync.plan.HighAvailability
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 14a897b3-2406-46c7-b08f-490085b3d048
description: Skype for Business Server 2015 年から 2015 年のほとんどのサーバー の役割の主な高可用性スキームは、プールによるサーバーの冗長性に基づいて行います。 特定のサーバーの役割を実行しているサーバーが失敗した場合、同じ役割を実行するプール内の他のサーバーは、そのサーバーからの負荷を受け取る。
ms.openlocfilehash: 351a8c317c128e37f603f8a64e312c972a76b7cb
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/05/2022
ms.locfileid: "62386475"
---
# <a name="high-availability-planning-tool"></a>高可用性計画ツール
 
Skype for Business Server 2015 年から 2015 年のほとんどのサーバー の役割の主な高可用性スキームは、プールによるサーバーの冗長性に基づいて行います。 あるサーバーの役割を実行しているサーバーが失敗すると、プール内で同じサーバーの役割を実行している別のサーバーがそのサーバーの負荷を引き継ぎます。
  
Skype for Business Server 2015 では、高可用性を有効にするには、少なくとも 2 つのフロント エンド サーバーが必要です。 計画ツールは、次の条件を使用して、高可用性をサポートするために追加のサーバーを追加するかどうかを判断します。
  
- 展開に 2 つ以上のフロント エンド サーバーが含まれている場合、計画ツールは追加のサーバーを追加しません。
    
- 展開にエッジ サーバーが含まれている場合は、別のサーバーが追加されます。 
    
- 展開に常設チャットが含まれている場合、計画ツールは追加のサーバーを追加しますが、プール番号は増やしません。 たとえば、展開に既に 4 台のサーバーが含まれている場合、計画ツールは別のサーバー (合計 5 台のサーバー) の追加を提案しますが、1 つのプールを維持します。 
    
また、計画ツールは、すべてのデータベースSQLミラー データベースを追加します。 たとえば、フロントエンド SQL Server データベースがある場合、計画ツールはもう一方のデータベースをミラー データベースとして追加し、"フロントエンド ミラー SQL データベース" と名付けします。
  
高可用性のための環境の準備の詳細については、「[Plan for high availability and disaster recovery in Skype for Business Server 2015」を参照](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)してください。
  

