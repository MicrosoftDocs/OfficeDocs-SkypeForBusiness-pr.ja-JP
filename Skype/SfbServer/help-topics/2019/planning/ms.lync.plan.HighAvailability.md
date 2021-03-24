---
title: 高可用性 (計画ツール)
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
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
ROBOTS: NOINDEX, NOFOLLOW
description: Skype for Business Server のほとんどのサーバーの役割の主な高可用性スキームは、プールによるサーバーの冗長性に基づいて行います。 あるサーバーの役割を実行しているサーバーが失敗すると、プール内で同じサーバーの役割を実行している別のサーバーがそのサーバーの負荷を引き継ぎます。
ms.openlocfilehash: 36b2d9fad34e16daf11fb7539f73c815264a55a6
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51093315"
---
# <a name="high-availability-planning-tool"></a>高可用性 (計画ツール)
 
Skype for Business Server のほとんどのサーバーの役割の主な高可用性スキームは、プールによるサーバーの冗長性に基づいて行います。 あるサーバーの役割を実行しているサーバーが失敗すると、プール内で同じサーバーの役割を実行している別のサーバーがそのサーバーの負荷を引き継ぎます。
  
Skype for Business Server では、高可用性を有効にするには、少なくとも 2 つのフロント エンド サーバーが必要です。 計画ツールは、次の条件を使用して、高可用性をサポートするために追加のサーバーを追加するかどうかを判断します。
  
- 展開に 2 つ以上のフロント エンド サーバーが含まれている場合、計画ツールは追加のサーバーを追加しません。
    
- 展開にエッジ サーバーが含まれている場合は、追加のサーバーが追加されます。 
    
- 展開に常設チャットが含まれている場合、計画ツールは追加のサーバーを追加しますが、プール番号は増やしません。 たとえば、展開に既に 4 台のサーバーが含まれている場合、計画ツールは追加のサーバー (合計 5 台のサーバー) の追加を提案しますが、1 つのプールを維持します。 

    > [!NOTE] 
    > 常設チャットは Skype for Business Server 2015 で使用できますが、Skype for Business Server 2019 ではサポートされなくなりました。 Teams でも同じ機能を使用できます。 詳細については [、「Skype for Business to Microsoft Teams のアップグレード」を参照してください](/MicrosoftTeams/upgrade-start-here)。 常設チャットを使用する必要がある場合は、この機能を必要とするユーザーを Teams に移行するか、Skype for Business Server 2015 を引き続き使用します。 

    
また、計画ツールは、すべてのデータベースSQLミラー データベースを追加します。 たとえば、フロントエンド SQL Server データベースがある場合、計画ツールはもう一方のデータベースをミラー データベースとして追加し、それを "フロントエンド ミラー SQL データベース" と名付けします。
  
高可用性のために環境を準備する方法の詳細については、「Skype for Business Server で高可用性と障害復旧を計画する [」を参照してください](../../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)。
