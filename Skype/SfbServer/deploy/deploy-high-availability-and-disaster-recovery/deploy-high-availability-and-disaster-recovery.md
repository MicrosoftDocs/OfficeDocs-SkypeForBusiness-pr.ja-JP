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
ms.localizationpriority: medium
ms.assetid: 21007bad-62ce-4553-98e0-02aaa1345781
description: Skype for Business Serverでは、サーバー プール、プールのペアリングによる障害復旧、および AlwaysOn 可用性グループ、データベース ミラーリング、SQL フェールオーバー クラスタリングなど、いくつかのモードのバック エンド サーバー高可用性を提供します。
ms.openlocfilehash: 168648150a249c92e4b56d4e9d335fbc864cadd3
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2021
ms.locfileid: "58598141"
---
# <a name="deploy-high-availability-and-disaster-recovery"></a>高可用性および障害回復の展開
 
Skype for Business Serverでは、サーバー プール、プールのペアリングによる障害復旧、および AlwaysOn 可用性グループ、データベース ミラーリング、SQL フェールオーバー クラスタリングなど、いくつかのモードのバック エンド サーバー高可用性を提供します。 
  
高可用性とは、1 つ以上のサーバーがダウンSkype for Business Serverサービスを確実に利用できる状態を指します。障害復旧とは、自然災害や人による災害が発生した場合にサービスを維持し、可能な限り災害前のデータを保持することです。
  
このセクションでは、これらの機能を展開する方法について説明します。また、他のサーバーの役割の一部に対して高可用性と障害復旧のために実行できる手順も説明します。

> [!NOTE]
> SQLミラーリングは 2015 年Skype for Business Server使用できますが、2019 年Skype for Business Serverではサポートされていません。 AlwaysOn 可用性グループ、AlwaysOn フェールオーバー クラスター インスタンス (FCI)、および SQL フェールオーバー クラスタリング方法は、2019 年Skype for Business Serverです。
  
## <a name="related-sections"></a>関連情報

[高可用性と障害復旧の計画を立Skype for Business Server](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)
  
## <a name="see-also"></a>関連項目

[サーバー内のバック エンド サーバーに AlwaysOn 可用性グループを展開Skype for Business Server](alwayson-availability-group.md)

[障害復旧用にペアのフロント エンド プールを展開Skype for Business Server](front-end-pools-for-disaster-recovery.md)
  
[2015 SQLでバック エンド サーバーの高可用性のミラーリングをSkype for Business Serverする](sql-mirroring-for-high-availability.md)
  
