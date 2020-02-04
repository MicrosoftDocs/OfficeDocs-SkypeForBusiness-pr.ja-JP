---
title: Skype for Business Server で高可用性と障害回復を計画する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
f1.keywords:
- ms.lync.plan.HighAvailabilityType
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 3543eb40-54f4-49ef-a058-03aceed4773a
description: Skype for Business Server は、サーバーのプーリング、プールペアリングを使用した障害回復、および AlwaysOn 可用性グループ、データベースのミラーリング、SQL フェールオーバークラスタリングなど、バックエンドサーバーの高可用性の複数のモードを備えた高可用性機能を提供します。
ms.openlocfilehash: 31059936249aa4e691f3e6b4b467841fd66a04ea
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2020
ms.locfileid: "41695972"
---
# <a name="plan-for-high-availability-and-disaster-recovery-in-skype-for-business-server"></a>Skype for Business Server で高可用性と障害回復を計画する
 
Skype for Business Server は、サーバーのプーリング、プールペアリングを使用した障害回復、および AlwaysOn 可用性グループ、データベースのミラーリング、SQL フェールオーバークラスタリングなど、バックエンドサーバーの高可用性の複数のモードを備えた高可用性機能を提供します。 
  
高可用性とは、1つまたは複数のサーバーが停止した場合でも、Skype for Business Server サービスが利用可能であることを確認することを意味します。 Disaster recovery refers to keeping services going in the event of a natural or human-caused disaster, and preserving as much data from before the disaster as possible.
  
以前のバージョンの Lync Server と同じように、Skype for Business Server のほとんどのサーバーの役割について、高可用性の主な機能は、プールによるサーバーの冗長性です。 特定のサーバーの役割を実行するサーバーで障害が発生した場合は、プール内の同じ役割を実行する他のサーバーがそのサーバーの負荷を引き受けます。 同じことが、フロントエンド サーバー、エッジ サーバー、仲介サーバー、およびディレクターでも実行されます。
  
Skype for Business Server では、フロントエンドプールの障害回復オプションも提供されています。 互いのバックアップとして機能するように、2 つのプールを別々の地理的地域にセットアップできます。 これによって、プールまたはサイト全体を停止させた場合に、バックアップ プールが両方のサイトのユーザーにサービスを継続して提供できます。
  
Skype for Business Server では、バックエンドサーバーでの高可用性の4つのモード (SQL ミラーリング、AlwaysOn 可用性グループ、AlwaysOn フェールオーバークラスターインスタンス (FCI)、SQL フェールオーバークラスタリング) もサポートされています。
  
> [!NOTE]
> SQL ミラーリングは、Skype for Business Server 2015 では使用できますが、Skype for Business Server 2019 ではサポートされなくなりました。 AlwaysOn 可用性グループ、AlwaysOn フェールオーバークラスターインスタンス (FCI)、SQL フェールオーバークラスタリングの各方法は、Skype for Business Server 2019 で推奨されます。

> [!NOTE]
> AlwaysOn 可用性グループは、常設チャットサーバーではサポートされていません。 
  
このセクションでは、これらの機能について説明し、別のサーバーの役割のいくつかに対する高可用性と障害復旧に使用できる手順を取り上げます。 
  
## <a name="see-also"></a>関連項目

[フロントエンド プールの高可用性と管理](high-availability.md)
  
[Skype for Business Server のフロントエンドプールの障害回復](disaster-recovery.md)
  
[Skype for Business Server でのプール障害時のユーザーエクスペリエンス](user-experience.md)
  
[Skype for Business Server のバックエンドサーバーの高可用性](back-end-server.md)
  
[Skype for Business Server でのファイル共有の高可用性](file-sharing.md)
