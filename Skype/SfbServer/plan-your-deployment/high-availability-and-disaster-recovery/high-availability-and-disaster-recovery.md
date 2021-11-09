---
title: 高可用性と障害復旧の計画を立Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.custom:
- ms.lync.plan.HighAvailabilityType
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 3543eb40-54f4-49ef-a058-03aceed4773a
description: Skype for Business Serverでは、サーバー プール、プールのペアリングによる障害復旧、および AlwaysOn 可用性グループ、データベース ミラーリング、SQL フェールオーバー クラスタリングなど、いくつかのモードのバック エンド サーバー高可用性を提供します。
ms.openlocfilehash: 37baa5627ef638c0a6835053bca9094564359d1a
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/08/2021
ms.locfileid: "60828690"
---
# <a name="plan-for-high-availability-and-disaster-recovery-in-skype-for-business-server"></a>高可用性と障害復旧の計画を立Skype for Business Server
 
Skype for Business Serverでは、サーバー プール、プールのペアリングによる障害復旧、および AlwaysOn 可用性グループ、データベース ミラーリング、SQL フェールオーバー クラスタリングなど、いくつかのモードのバック エンド サーバー高可用性を提供します。 
  
高可用性とは、1 つ以上のサーバーがダウンSkype for Business Serverサービスを確実に利用できる状態を指します。 障害復旧とは、自然災害や人による災害が発生した場合にサービスを維持し、可能な限り災害前のデータを保持することです。
  
以前のバージョンの Lync Server と同様に、サーバーサーバーのほとんどの役割の主な高可用性機能は、プールによるサーバー Skype for Business Server冗長性です。 あるサーバーの役割を実行しているサーバーが失敗すると、プール内で同じサーバーの役割を実行している別のサーバーがそのサーバーの負荷を引き継ぎます。 これはフロントエンド サーバー、エッジ サーバー、仲介サーバー、およびディレクターに適用されます。
  
Skype for Business Serverフロントエンド プールの障害復旧オプションも提供します。 異なる地理的領域に 2 つのプールをセットアップして、互いにバックアップとして機能することができます。 次に、プールまたはサイト全体がダウンしている場合、バックアップ プールは引き続き両方のサイトのユーザーにサービスを提供できます。
  
Skype for Business Serverは、SQL ミラーリング、AlwaysOn 可用性グループ、AlwaysOn フェールオーバー クラスター インスタンス (FCI)、および SQL フェールオーバー クラスタリングの 4 つのモードをサポートします。
  
> [!NOTE]
> SQLミラーリングは 2015 年Skype for Business Server使用できますが、2019 年Skype for Business Serverではサポートされていません。 AlwaysOn 可用性グループ、AlwaysOn フェールオーバー クラスター インスタンス (FCI)、および SQL フェールオーバー クラスタリング方法は、2019 年Skype for Business Serverです。

> [!NOTE]
> AlwaysOn 可用性グループは、常設チャット サーバーではサポートされていません。 
  
このセクションでは、これらの機能について説明し、他のサーバーの役割の一部に対して高可用性と障害復旧のために実行できる手順について説明します。 
  
## <a name="see-also"></a>関連項目

[フロントエンド プールの高可用性と管理](high-availability.md)
  
[フロントエンド プールの障害復旧 (Skype for Business Server](disaster-recovery.md)
  
[プールの障害時のユーザー エクスペリエンスSkype for Business Server](user-experience.md)
  
[バック エンド サーバーの高可用性 (Skype for Business Server](back-end-server.md)
  
[ファイル共有の高可用性 (Skype for Business Server](file-sharing.md)
