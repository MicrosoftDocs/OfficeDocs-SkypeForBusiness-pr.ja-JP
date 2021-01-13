---
title: Skype for Business Server で高可用性と障害復旧を計画する
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.custom:
- ms.lync.plan.HighAvailabilityType
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 3543eb40-54f4-49ef-a058-03aceed4773a
description: Skype for Business Server は、サーバー プールでの高可用性、プールペアリングによる障害復旧、および AlwaysOn 可用性グループ、データベース ミラーリング、SQL フェールオーバー クラスタリングなど、いくつかのモードのバック エンド サーバー高可用性を提供します。
ms.openlocfilehash: 61b720bc9dce5bc8dc54a6c493429b0a3c9b27d2
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802817"
---
# <a name="plan-for-high-availability-and-disaster-recovery-in-skype-for-business-server"></a>Skype for Business Server で高可用性と障害復旧を計画する
 
Skype for Business Server は、サーバー プールでの高可用性、プールペアリングによる障害復旧、および AlwaysOn 可用性グループ、データベース ミラーリング、SQL フェールオーバー クラスタリングなど、いくつかのモードのバック エンド サーバー高可用性を提供します。 
  
高可用性とは、1 つ以上のサーバーがダウンした場合でも、Skype for Business Server サービスを確実に利用できる状態を指します。 障害復旧とは、自然または人が引き起こした障害が発生した場合にサービスを維持し、災害前からのデータをできる限り多く保持することです。
  
以前のバージョンの Lync Server と同様に、Skype for Business Server のほとんどのサーバーの役割の主な高可用性機能は、プールによるサーバーの冗長性です。 あるサーバーの役割を実行しているサーバーが失敗すると、プール内で同じサーバーの役割を実行している別のサーバーがそのサーバーの負荷を引き継ぎます。 これはフロントエンド サーバー、エッジ サーバー、仲介サーバー、およびディレクターに適用されます。
  
Skype for Business Server には、フロントエンド プールの障害復旧オプションも用意されています。 地理的に異なる地域に 2 つのプールを設定して、互いにバックアップとして機能することができます。 その後、プールまたはサイト全体がダウンした場合でも、バックアップ プールは両方のサイトのユーザーにサービスを提供し続ける可能性があります。
  
また、Skype for Business Server は、SQL ミラーリング、AlwaysOn 可用性グループ、AlwaysOn フェールオーバー クラスター インスタンス (FCI)、および SQL フェールオーバー クラスタリングという 4 つのモードの高可用性をサポートしています。
  
> [!NOTE]
> SQLミラーリングは Skype for Business Server 2015 で使用できますが、Skype for Business Server 2019 ではサポートされなくなりました。 Skype for Business Server 2019 では、AlwaysOn 可用性グループ、AlwaysOn フェールオーバー クラスター インスタンス (FCI)、および SQL フェールオーバー クラスタリングの方法が優先されます。

> [!NOTE]
> AlwaysOn 可用性グループは、常設チャット サーバーではサポートされていません。 
  
このセクションでは、これらの機能について説明します。また、他のサーバーの役割の一部に対して、高可用性と障害復旧のために実行できる手順も説明します。 
  
## <a name="see-also"></a>関連項目

[フロントエンド プールの高可用性と管理](high-availability.md)
  
[Skype for Business Server でのフロントエンド プールの障害復旧](disaster-recovery.md)
  
[Skype for Business Server でのプール障害時のユーザー エクスペリエンス](user-experience.md)
  
[Skype for Business Server でのバック エンド サーバーの高可用性](back-end-server.md)
  
[Skype for Business Server でのファイル共有の高可用性](file-sharing.md)
