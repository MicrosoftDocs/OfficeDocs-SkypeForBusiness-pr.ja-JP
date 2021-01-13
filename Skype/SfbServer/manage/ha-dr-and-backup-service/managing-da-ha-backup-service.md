---
title: 障害復旧、高可用性、およびバックアップ サービスの管理
ms.reviewer: ''
author: cichur
ms.author: v-cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 障害復旧操作の手順と、ペアのフロント エンド プールのデータを同期するバックアップ サービスを維持する手順について説明します。
ms.openlocfilehash: e486a71203b64b4fc351888869ac64a24689ba7b
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817157"
---
# <a name="managing-skype-for-business-server-disaster-recovery-high-availability-and-backup-service"></a>Skype for Business Server の障害復旧、高可用性、およびバックアップ サービスの管理

このセクションでは、障害復旧操作の手順と、ペアのフロント エンド プール内のデータを同期するバックアップ サービスを維持するための手順について説明します。

障害回復の手順は、フェールオーバーとフェールバックのどちらも、手動によるものです。障害が発生した場合、管理者はフェールオーバーの手順を手動で開始する必要があります。プール修復後のフェールバックにも同じことが当てはまります。

このセクションの障害復旧手順では、以下を前提とします。

  - 「高可用性と障害復旧の計画」で説明するように、ペアのフロント エンド プールが異なるサイト [に展開されている](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)。 バックアップ サービスは、ペアになったプールの同期を保つためにこれらのプール上で実行されています。

  - 中央管理ストアがいずれかのプールでホストされている場合、そのストアはペアのプールの両方にインストールされ、実行されます。これらのプールの 1 つはアクティブ マスターをホストし、もう 1 つはスタンバイをホストするプールです。

> [!IMPORTANT]
> 以下の手順では、影響を受けるユーザーのリダイレクト元になるプールではなく、障害の影響を受けるプールの完全修飾 FQDN を PoolFQDN ** パラメーターが参照しています。影響を受ける同じユーザー群が同じ場合、このパラメーターはフェールオーバーとフェールバックの各コマンドレットで同じプール (つまり、ユーザーがフェールオーバー前に最初に所属していたプール) を参照します。<BR><br>たとえば、プール P1 に所属していたすべてのユーザーがバックアップ プール P2 にフェールオーバーされた場合を想定します。 管理者が P2 によって現在サービスを受け取っているすべてのユーザーを P1 によって処理される移動する場合、管理者は次の手順を実行する必要があります。 
> <OL>
> <LI>
> <P>フェールバック コマンドレットを使用して、当初 P1 にホームだったすべてのユーザーを P2 から P1 にフェールバックします。 この場合、PoolFQDN ** は P1 の FQDN になります。</P>
> <LI>
> <P>フェールオーバー コマンドレットを使用して、当初 P2 から P1 にいたすべてのユーザーをフェールオーバーします。 この場合、PoolFQDN は P2 の FQDN になります。</P>
> <LI>
> <P>後で管理者が P2 ユーザーを P2 にフェールバックする場合、PoolFQDN は P2 の FQDN になります。</P></LI></OL><br>プールの整合性を維持するには、上記の手順 1 を手順 2 の前に実行する必要があります。 手順 1 の前に手順 2 を実行すると、手順 2 のコマンドレットは失敗します。


## <a name="see-also"></a>関連項目

[高可用性と障害復旧を計画する](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md) 
  
