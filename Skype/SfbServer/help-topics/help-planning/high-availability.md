---
title: 高可用性 (計画ツール)
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 4/8/2016
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.plan.HighAvailability
- ms.lync.plan.HighAvailability
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 14a897b3-2406-46c7-b08f-490085b3d048
description: Skype for Business Server 2015 のほとんどのサーバーの役割の主な高可用性スキームは、プールによるサーバーの冗長性に基づいて行います。 あるサーバーの役割を実行しているサーバーが失敗すると、プール内で同じサーバーの役割を実行している別のサーバーがそのサーバーの負荷を引き継ぎます。
ms.openlocfilehash: a866784f94dd2e2c861aa93c482b40946da7ac7d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49829007"
---
# <a name="high-availability-planning-tool"></a>高可用性 (計画ツール)
 
Skype for Business Server 2015 のほとんどのサーバーの役割の主な高可用性スキームは、プールによるサーバーの冗長性に基づいて行います。 あるサーバーの役割を実行しているサーバーが失敗すると、プール内で同じサーバーの役割を実行している別のサーバーがそのサーバーの負荷を引き継ぎます。
  
Skype for Business Server 2015 では、高可用性を実現するために少なくとも 2 台のフロントエンド サーバーが必要です。 計画ツールは、次の条件を使用して、高可用性をサポートするためにサーバーを追加するかどうかを判断します。
  
- 展開に 2 つ以上のフロントエンド サーバーが含まれる場合、計画ツールは追加のサーバーを追加しません。
    
- 展開にエッジ サーバーが含まれている場合は、追加のサーバーが追加されます。 
    
- 展開に常設チャットが含まれている場合、計画ツールは追加のサーバーを追加しますが、プール番号は増やしません。 たとえば、展開に既に 4 台のサーバーが含まれている場合、計画ツールは (合計 5 台のサーバーに対して) サーバーを追加し、1 つのプールを維持します。 
    
また、計画ツールは、すべてのデータベースSQLミラー データベースを追加します。 たとえば、フロントエンド SQL Server データベースがある場合、計画ツールは、他のデータベースをこのデータベースのミラー データベースとして追加し、"Front End mirror SQL database" という名前を付きます。
  
高可用性を実現するための環境の準備の詳細については [、「Plan for high availability and disaster recovery in Skype for Business Server 2015」](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)を参照してください。
  

