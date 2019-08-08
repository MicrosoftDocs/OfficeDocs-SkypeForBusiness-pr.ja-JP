---
title: 高可用性および障害復旧の展開
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 21007bad-62ce-4553-98e0-02aaa1345781
description: Skype for Business Server は、サーバーのプーリング、プールペアリングを使用した障害回復、および AlwaysOn 可用性グループ、データベースのミラーリング、SQL フェールオーバークラスタリングなど、バックエンドサーバーの高可用性の複数のモードを備えた高可用性機能を提供します。
ms.openlocfilehash: cb4d39df7f6a12a14c25533d8c6fb1ae95da24d4
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/07/2019
ms.locfileid: "36240064"
---
# <a name="deploy-high-availability-and-disaster-recovery"></a>高可用性および障害復旧の展開
 
Skype for Business Server は、サーバーのプーリング、プールペアリングを使用した障害回復、および AlwaysOn 可用性グループ、データベースのミラーリング、SQL フェールオーバークラスタリングなど、バックエンドサーバーの高可用性の複数のモードを備えた高可用性機能を提供します。 
  
高可用性とは、1つまたは複数のサーバーが停止した場合でも、Skype for Business Server サービスが利用可能であることを確認することを意味します。災害復旧とは、自然災害または人的災害の発生時にサービスを継続させ、できるだけ多くのデータを可能な限り維持することを意味します。
  
このセクションでは、これらの機能の展開方法について説明し、別のサーバーの役割のいくつかに対する高可用性と障害復旧に使用できる手順を取り上げます。

> [!NOTE]
> SQL ミラーリングは、Skype for Business Server 2015 では使用できますが、Skype for Business Server 2019 ではサポートされなくなりました。 AlwaysOn 可用性グループ、AlwaysOn フェールオーバークラスターインスタンス (FCI)、SQL フェールオーバークラスタリングの各方法は、Skype for Business Server 2019 で推奨されます。
  
## <a name="related-sections"></a>関連セクション

[Skype for Business Server で高可用性と障害回復を計画する](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)
  
## <a name="see-also"></a>関連項目

[Skype for Business Server のバックエンドサーバーに AlwaysOn 可用性グループを展開する](alwayson-availability-group.md)

[Skype for Business Server での障害回復用にペアリングされたフロントエンドプールの展開](front-end-pools-for-disaster-recovery.md)
  
[Skype for Business Server 2015 でバックエンド サーバーの高可用性を実現するための SQL ミラーリングの展開](sql-mirroring-for-high-availability.md)
  
