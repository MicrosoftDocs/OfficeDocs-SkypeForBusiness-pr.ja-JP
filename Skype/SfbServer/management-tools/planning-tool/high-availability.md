---
title: High Availability (Planning Tool)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 4/8/2016
audience: ITPro
ms.topic: article
f1.keywords:
- NOCSH
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 14a897b3-2406-46c7-b08f-490085b3d048
description: Skype for Business Server 2015 のほとんどのサーバーの役割に関する高可用性の主なスキームは、プールによるサーバーの冗長性に基づいています。 あるサーバーの役割を実行しているサーバーに障害が発生すると、プール内で同じサーバーの役割を実行している別のサーバーがそのサーバーの負荷を引き継ぎます。
ms.openlocfilehash: 4b10eab9e2de3741958e2ed17cfc92aa430ed3ea
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816396"
---
# <a name="high-availability-planning-tool"></a>High Availability (Planning Tool)
 
Skype for Business Server 2015 のほとんどのサーバーの役割に関する高可用性の主なスキームは、プールによるサーバーの冗長性に基づいています。 あるサーバーの役割を実行しているサーバーに障害が発生すると、プール内で同じサーバーの役割を実行している別のサーバーがそのサーバーの負荷を引き継ぎます。
  
高可用性を有効にするには、Skype for Business Server 2015 で少なくとも2台のフロントエンドサーバーが必要です。 計画ツールでは、高可用性をサポートするために追加のサーバーが追加されるかどうかを判断するために、次の条件を使用します。
  
- 展開に2台以上のフロントエンドサーバーが含まれている場合、計画ツールでは追加のサーバーは追加されません。
    
- 展開にエッジサーバーが含まれている場合は、追加のサーバーが追加されます。 
    
- 展開に永続的なチャットが含まれている場合、計画ツールでは、余分なサーバーが追加されますが、プール番号は増えません。 たとえば、展開に既に4台のサーバーが含まれている場合、計画ツールでは、(合計5台の) サーバーを追加することが推奨されますが、1つのプールを維持します。 
    
計画ツールでは、すべてのデータベースのミラー SQL データベースも追加されます。 たとえば、フロントエンドの SQL Server データベースがある場合は、計画ツールによって、そのデータベースがこのデータベースのミラーデータベースとして追加され、"フロントエンドミラー SQL データベース" という名前が付けられます。
  
高可用性を実現するための環境の準備について詳しくは、「 [Skype For Business Server 2015 で高可用性と障害回復を計画する](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)」をご覧ください。
  

