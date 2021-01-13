---
title: 高可用性および障害回復の展開
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 21007bad-62ce-4553-98e0-02aaa1345781
description: Skype for Business Server は、サーバー プールでの高可用性、プールペアリングによる障害復旧、および AlwaysOn 可用性グループ、データベース ミラーリング、SQL フェールオーバー クラスタリングなど、いくつかのモードのバック エンド サーバー高可用性を提供します。
ms.openlocfilehash: 68baae183ff45571e38e922035d287e733bcc930
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830617"
---
# <a name="deploy-high-availability-and-disaster-recovery"></a>高可用性および障害回復の展開
 
Skype for Business Server は、サーバー プールでの高可用性、プールペアリングによる障害復旧、および AlwaysOn 可用性グループ、データベース ミラーリング、SQL フェールオーバー クラスタリングなど、いくつかのモードのバック エンド サーバー高可用性を提供します。 
  
高可用性とは、1 つ以上のサーバーがダウンした場合でも、Skype for Business Server サービスを確実に利用できる状態を指します。障害復旧とは、自然または人が引き起こした障害が発生した場合にサービスを維持し、災害前からのデータをできる限り多く保持することです。
  
このセクションでは、これらの機能を展開する方法について説明します。また、他のサーバーの役割の一部に対して、高可用性と障害復旧のために実行できる手順も説明します。

> [!NOTE]
> SQLミラーリングは Skype for Business Server 2015 で使用できますが、Skype for Business Server 2019 ではサポートされなくなりました。 Skype for Business Server 2019 では、AlwaysOn 可用性グループ、AlwaysOn フェールオーバー クラスター インスタンス (FCI)、および SQL フェールオーバー クラスタリングの方法が推奨されます。
  
## <a name="related-sections"></a>関連情報

[Skype for Business Server で高可用性と障害復旧を計画する](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)
  
## <a name="see-also"></a>関連項目

[Skype for Business Server のバック エンド サーバーに AlwaysOn 可用性グループを展開する](alwayson-availability-group.md)

[Skype for Business Server で障害復旧用のペアのフロント エンド プールを展開する](front-end-pools-for-disaster-recovery.md)
  
[Deploy SQL mirroring for Back End Server high availability in Skype for Business Server 2015](sql-mirroring-for-high-availability.md)
  
