---
title: High Availability (Planning Tool)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.plan.HighAvailability
- ms.lync.plan.HighAvailability
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 14a897b3-2406-46c7-b08f-490085b3d048
ROBOTS: NOINDEX, NOFOLLOW
description: Skype ビジネス サーバー用のほとんどのサーバーの役割の主な高可用性スキームは、プールを使用してサーバーの冗長性に基づいています。 あるサーバーの役割を実行しているサーバーに障害が発生すると、プール内で同じサーバーの役割を実行している別のサーバーがそのサーバーの負荷を引き継ぎます。
ms.openlocfilehash: 38887d576a6e15135d9ea35c1dd286ee8c052063
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33889361"
---
# <a name="high-availability-planning-tool"></a>High Availability (Planning Tool)
 
Skype ビジネス サーバー用のほとんどのサーバーの役割の主な高可用性スキームは、プールを使用してサーバーの冗長性に基づいています。 あるサーバーの役割を実行しているサーバーに障害が発生すると、プール内で同じサーバーの役割を実行している別のサーバーがそのサーバーの負荷を引き継ぎます。
  
ビジネス サーバーの Skype では、高可用性を実現するために少なくとも 2 台のフロント エンド サーバーが必要です。 計画ツールでは、次の条件を使って、かどうかは、高可用性をサポートするために余分なサーバーが追加されますを決定します。
  
- 展開には、2 つまたは複数のフロント エンド サーバーが含まれています、計画ツールでは、予備のサーバーは追加されません。
    
- 展開にエッジ サーバーが含まれている場合は、追加のサーバーが追加されます。 
    
- 展開には、永続的なチャットが含まれています、計画ツールは、余分なサーバーを追加するが、プールの数を増加しません。 など、既に展開には、4 つのサーバーが含まれている場合、計画ツール (合計 5 台のサーバー) に追加のサーバーを追加することが推奨されますが、1 つのプールが維持されます。 

    > [!NOTE] 
    > 永続的なチャットですがビジネス サーバー 2015 の Skype で利用可能なビジネス サーバー 2019 の Skype でサポートされていません。 同じ機能は、チームで使用できます。 詳細については、[マイクロソフトのチームにビジネス用の Skype のアップグレード](https://docs.microsoft.com/MicrosoftTeams/journey-skypeforbusiness-teams)を参照してください。 永続的なチャットの使用が必要な場合、選択肢としてはチームにこの機能を必要とするユーザーを移行するか、ビジネス サーバー 2015 の Skype を使用し続けます。 

    
計画ツールは、すべてのデータベースのミラーの SQL データベースにも追加されます。 などのフロント エンドの SQL Server データベースがある場合は、計画ツールはこの 1 つのミラー データベースとその他のデータベースを追加して名前を"フロント エンド ミラー SQL データベースとします。
  
高可用性環境を準備する方法の詳細については、[高可用性とビジネスのサーバー用の Skype での災害復旧の計画](../../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)を参照してください。
  

