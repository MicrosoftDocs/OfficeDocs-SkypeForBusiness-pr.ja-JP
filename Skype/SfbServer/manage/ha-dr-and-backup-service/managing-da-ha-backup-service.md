---
title: 災害復旧、高可用性、およびバックアップ サービスの管理
ms.reviewer: ''
author: heidip
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: ペアのフロント エンド プール内のデータを同期しているバックアップ サービスを維持するためだけでなく、災害リカバリ ・ オペレーションの手順について説明します。
ms.openlocfilehash: 103e0aa274e40fd997981bd6de595ceca089b710
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30892414"
---
# <a name="managing-skype-for-business-server-disaster-recovery-high-availability-and-backup-service"></a>Business Server の災害復旧、高可用性、およびバックアップ サービスの Skype を管理します。

このセクションでは、ペアのフロント エンド プール内のデータを同期しているバックアップ サービスを維持するためだけでなく、災害リカバリ ・ オペレーションの手順を説明します。

フェールオーバーとフェールバックの両方に、障害回復手順は、手動です。 障害がある場合は、管理者はフェイル オーバー手順を手動で呼び出す必要があります。 プールが修復された後、同じはフェイル バックに適用されます。

ここでディザスタ リカバリの手順は、以下と仮定します。

  - [高可用性と災害復旧の計画](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)で説明したように別のサイトにあるペアのフロント エンド プールを使用した展開があります。 これらのペアになったプールにそれらを同期させてのバックアップ サービスを実行するとします。

  - 中央管理ストアがいずれかのプールでホストされている場合は、作業中のマスターをホストしているこれらのプールと、スタンバイ状態をホストしている他のプールの 1 つで、対になったプールの両方にインストールして実行します。

> [!IMPORTANT]
> 次の手順で、 *PoolFQDN*パラメーターは、災害の影響を受けるプールの FQDN を参照からリダイレクトされるユーザーに影響をプールではありません。 影響を受けるユーザーの同じセットのフェールオーバーとフェールバックの両方のコマンドレット (つまり、最初にフェールオーバーする前にユーザーをホーム サーバー プール) で同じプールを指します。<BR><br>たとえば、バックアップのプールでは、P2 を P1 がフェイル オーバー ・ プール上のすべてのユーザーがホーム サーバーの場合を想定しています。 管理者が現在 P2 が P1 でサービスがサービスを提供するすべてのユーザーを移動したい場合、管理者は次の手順に従う必要があります。 
> <OL>
> <LI>
> <P>失敗は、もともと所属していたユーザーに P1、P2 から P1 のすべてをバックアップ、フェイル バックのコマンドレットを使用します。 *PoolFQDN*は、この例では、P1 の FQDN です。</P>
> <LI>
> <P>フェイル オーバー、もともと所属していたユーザーに P1、P2 のすべてのフェイル オーバーのコマンドレットを使用します。 このケースで、PoolFQDN は、P2 の FQDN です。</P>
> <LI>
> <P>後で、管理者は P2 に P2 ユーザーのフェイル バックしたいと考えていると、PoolFQDN が P2 の FQDN です。</P></LI></OL><br>プールの整合性を保持するために 2 の手順の前に、上記の手順 1 を実行する必要が注意してください。 手順 2 手順 1 の前にしようとすると、手順 2 のコマンドレットは失敗します。


## <a name="see-also"></a>関連項目

[高可用性および障害復旧の計画](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md) 
  
