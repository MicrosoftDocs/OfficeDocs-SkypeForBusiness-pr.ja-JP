---
title: 高可用性 (計画ツール)
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
  - CSH
ms.custom:
  - ms.lync.plan.HighAvailability
  - ms.lync.plan.HighAvailability
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 14a897b3-2406-46c7-b08f-490085b3d048
ROBOTS: 'NOINDEX, NOFOLLOW'
description: サーバー内のほとんどのサーバー の役割の主な高可用性スキームはSkype for Business Serverによるサーバーの冗長性に基づいて行います。 あるサーバーの役割を実行しているサーバーが失敗すると、プール内で同じサーバーの役割を実行している別のサーバーがそのサーバーの負荷を引き継ぎます。
---

# <a name="high-availability-planning-tool"></a>高可用性 (計画ツール)
 
サーバー内のほとんどのサーバー の役割の主な高可用性スキームはSkype for Business Serverによるサーバーの冗長性に基づいて行います。 あるサーバーの役割を実行しているサーバーが失敗すると、プール内で同じサーバーの役割を実行している別のサーバーがそのサーバーの負荷を引き継ぎます。
  
Skype for Business Serverを有効にするには、少なくとも 2 台のフロント エンド サーバーが必要です。 計画ツールは、次の条件を使用して、高可用性をサポートするために追加のサーバーを追加するかどうかを判断します。
  
- 展開に 2 つ以上のフロント エンド サーバーが含まれている場合、計画ツールは追加のサーバーを追加しません。
    
- 展開にエッジ サーバーが含まれている場合は、追加のサーバーが追加されます。 
    
- 展開に常設チャットが含まれている場合、計画ツールは追加のサーバーを追加しますが、プール番号は増やしません。 たとえば、展開に既に 4 台のサーバーが含まれている場合、計画ツールは追加のサーバー (合計 5 台のサーバー) の追加を提案しますが、1 つのプールを維持します。 

    > [!NOTE] 
    > 常設チャットは 2015 Skype for Business Serverで使用できますが、2019 年Skype for Business Serverではサポートされていません。 同じ機能は、Teams。 詳細については、「Skype for Business[アップグレードMicrosoft Teams参照してください](/MicrosoftTeams/upgrade-start-here)。 常設チャットを使用する必要がある場合は、この機能を必要とするユーザーを 2015 年に移行するか、Teamsを使用Skype for Business Server選択します。 

    
また、計画ツールは、すべてのデータベースSQLミラー データベースを追加します。 たとえば、フロントエンド SQL Server データベースがある場合、計画ツールはもう一方のデータベースをミラー データベースとして追加し、"フロントエンド ミラー SQL データベース" と名付けします。
  
高可用性のために環境を準備する方法の詳細については、「[高可用性と](../../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)障害復旧を計画する」を参照Skype for Business Server。
