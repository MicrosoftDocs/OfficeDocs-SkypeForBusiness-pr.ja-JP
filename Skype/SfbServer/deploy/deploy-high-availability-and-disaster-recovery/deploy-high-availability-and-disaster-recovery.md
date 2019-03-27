---
title: 高可用性および障害復旧の展開
ms.reviewer: ''
ms.author: heidip
author: microsoftheidi
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 21007bad-62ce-4553-98e0-02aaa1345781
description: Skype ビジネス サーバーのサーバーのプール、プールの組み合わせ、およびバック エンド サーバーの高可用性、AlwaysOn 可用性グループ、データベース ミラーリングは、SQL フェールオーバー クラスタ リングなどのいくつかのモードでの災害復旧と高可用性を提供します。
ms.openlocfilehash: bbd3c4092962e757a7565f1da054c82438a79ded
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30876776"
---
# <a name="deploy-high-availability-and-disaster-recovery"></a>高可用性および障害復旧の展開
 
Skype ビジネス サーバーのサーバーのプール、プールの組み合わせ、およびバック エンド サーバーの高可用性、AlwaysOn 可用性グループ、データベース ミラーリングは、SQL フェールオーバー クラスタ リングなどのいくつかのモードでの災害復旧と高可用性を提供します。 
  
高可用性は、1 つまたは複数のサーバーがダウンした場合でも、ビジネス サーバー サービスの Skype が利用可能であることを確認することを指します。災害復旧とは、自然または人間による障害が発生した場合、可能な限り障害発生以前から多くのデータを保持し、保持するサービスです。
  
このセクションでは、これらの機能の展開方法について説明し、別のサーバーの役割のいくつかに対する高可用性と障害復旧に使用できる手順を取り上げます。

> [!NOTE]
> SQL ミラーリング ビジネス サーバー 2015 の Skype で利用できるが、ビジネス サーバー 2019 の Skype でサポートされていません。 AlwaysOn 可用性グループ、AlwaysOn フェールオーバー クラスター インスタンス (FCI)、および SQL フェールオーバー クラスタ リング手法は、ビジネス サーバー 2019 の Skype で優先します。
  
## <a name="related-sections"></a>関連項目

[ビジネスのサーバーに、Skype での高可用性と災害復旧を計画します。](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)
  
## <a name="see-also"></a>関連項目

[ビジネス サーバーの Skype でのバック エンド サーバー上の AlwaysOn 可用性グループを展開します。](alwayson-availability-group.md)

[ビジネス サーバーの Skype での災害復旧のための一対のフロント エンド プールを展開します。](front-end-pools-for-disaster-recovery.md)
  
[Skype for Business Server 2015 でバックエンド サーバーの高可用性を実現するための SQL ミラーリングの展開](sql-mirroring-for-high-availability.md)
  
