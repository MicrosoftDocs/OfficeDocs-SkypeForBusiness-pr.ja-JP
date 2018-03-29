---
title: Skype for Business Server 2015 での高可用性および障害復旧の計画
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 1/29/2018
ms.audience: ITPro
ms.topic: conceptual
f1_keywords:
- ms.lync.plan.HighAvailabilityType
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 3543eb40-54f4-49ef-a058-03aceed4773a
description: Skype ビジネス サーバーのサーバーのプール、プールの組み合わせ、およびバック エンド サーバーの高可用性、AlwaysOn 可用性グループ、データベース ミラーリングは、SQL フェールオーバー クラスタ リングなどのいくつかのモードでの災害復旧と高可用性を提供します。
ms.openlocfilehash: e2e433112146e3be771abb12ef50e09749e8e325
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="plan-for-high-availability-and-disaster-recovery-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 での高可用性および障害復旧の計画
 
Skype ビジネス サーバーのサーバーのプール、プールの組み合わせ、およびバック エンド サーバーの高可用性、AlwaysOn 可用性グループ、データベース ミラーリングは、SQL フェールオーバー クラスタ リングなどのいくつかのモードでの災害復旧と高可用性を提供します。 
  
高可用性は、1 つまたは複数のサーバーがダウンした場合でも、ビジネス サーバー サービスの Skype が利用可能であることを確認することを指します。 障害復旧とは、自然災害または人災が発生した場合であってもサービスの稼働を維持し、災害前からのデータを可能な限り多く維持することです。
  
Lync Server の以前のバージョンのように Skype ビジネス サーバー用のほとんどのサーバーの役割の主な高可用性機能はプールを使用してサーバーの冗長性 特定のサーバーの役割を実行するサーバーで障害が発生した場合は、プール内の同じ役割を実行する他のサーバーがそのサーバーの負荷を引き受けます。 同じことが、フロントエンド サーバー、エッジ サーバー、仲介サーバー、およびディレクターでも実行されます。
  
ビジネス サーバーの Skype は、リカバリ ・ オプションのフロント エンド プールの障害も提供します。 互いのバックアップとして機能するように、2 つのプールを別々の地理的地域にセットアップできます。 これによって、プールまたはサイト全体を停止させた場合に、バックアップ プールが両方のサイトのユーザーにサービスを継続して提供できます。
  
Skype ビジネス サーバーのでは、バック エンド サーバーの高可用性の 4 つのモードもがサポートされています: データベース ミラーリング、AlwaysOn 可用性グループ、AlwaysOn フェールオーバー クラスター インスタンス (FCI)、および SQL のフェールオーバー クラスタ リングします。
  
> [!NOTE]
> AlwaysOn 可用性グループは、永続的なチャット サーバーではサポートされていません。 
  
このセクションでは、これらの機能について説明し、別のサーバーの役割のいくつかに対する高可用性と障害復旧に使用できる手順を取り上げます。 
  
## <a name="see-also"></a>関連項目

#### 

[フロント エンド プールの高可用性と管理](high-availability.md)
  
[ビジネス サーバー 2015 の前面の Skype で最後のプール災害復旧](disaster-recovery.md)
  
[ビジネス サーバー 2015 の Skype でのプールの障害発生時にユーザーの操作性](user-experience.md)
  
[ビジネス サーバー 2015 の Skype でのバック エンド サーバー高可用性](back-end-server.md)
  
[ビジネス サーバー 2015 の Skype での高可用性の共有ファイル](file-sharing.md)

