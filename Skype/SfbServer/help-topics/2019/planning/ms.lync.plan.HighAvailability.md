---
title: High Availability (Planning Tool)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.plan.HighAvailability
- ms.lync.plan.HighAvailability
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 14a897b3-2406-46c7-b08f-490085b3d048
ROBOTS: NOINDEX, NOFOLLOW
description: Skype for Business Server のほとんどのサーバーの役割に関する高可用性の主要なスキームは、プールによるサーバーの冗長性に基づいています。 あるサーバーの役割を実行しているサーバーに障害が発生すると、プール内で同じサーバーの役割を実行している別のサーバーがそのサーバーの負荷を引き継ぎます。
ms.openlocfilehash: 2a3327bcf5b17df7bc6eb4880a9966764786560d
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34281591"
---
# <a name="high-availability-planning-tool"></a>High Availability (Planning Tool)
 
Skype for Business Server のほとんどのサーバーの役割に関する高可用性の主要なスキームは、プールによるサーバーの冗長性に基づいています。 あるサーバーの役割を実行しているサーバーに障害が発生すると、プール内で同じサーバーの役割を実行している別のサーバーがそのサーバーの負荷を引き継ぎます。
  
高可用性を有効にするには、Skype for Business Server で少なくとも2台のフロントエンドサーバーが必要です。 計画ツールでは、高可用性をサポートするために追加のサーバーが追加されるかどうかを判断するために、次の条件を使用します。
  
- 展開に2台以上のフロントエンドサーバーが含まれている場合、計画ツールでは追加のサーバーは追加されません。
    
- 展開にエッジサーバーが含まれている場合は、追加のサーバーが追加されます。 
    
- 展開に永続的なチャットが含まれている場合、計画ツールでは、余分なサーバーが追加されますが、プール番号は増えません。 たとえば、展開に既に4台のサーバーが含まれている場合、計画ツールでは、(合計5台の) サーバーを追加することが推奨されますが、1つのプールを維持します。 

    > [!NOTE] 
    > 常設チャットは Skype for Business Server 2015 で使用できますが、Skype for Business Server 2019 ではサポートされなくなりました。 Teams でも同じ機能を使用できます。 詳細については、「 [Skype For business から Microsoft Teams へのアップグレード](https://docs.microsoft.com/MicrosoftTeams/journey-skypeforbusiness-teams)」を参照してください。 常設チャットを使用する必要がある場合は、この機能が必要なユーザーを Teams に移行するか、Skype for Business Server 2015 を使い続けるかのどちらかを選択できます。 

    
計画ツールでは、すべてのデータベースのミラー SQL データベースも追加されます。 たとえば、フロントエンドの SQL Server データベースがある場合は、計画ツールによって、そのデータベースがこのデータベースのミラーデータベースとして追加され、"フロントエンドミラー SQL データベース" という名前が付けられます。
  
高可用性を実現するための環境の準備について詳しくは、「 [Skype For Business Server で高可用性と障害回復を計画する](../../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)」をご覧ください。
  

