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
description: 障害復旧操作の手順と、ペアのフロントエンド プール内のデータを同期するバックアップ サービスの保守について説明します。
ms.openlocfilehash: a6740f5ebc0cc05982a5ad14efb5b2c10a8e06c22124aae331725d4c74a5aac2
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "54336657"
---
# <a name="managing-skype-for-business-server-disaster-recovery-high-availability-and-backup-service"></a>障害復旧Skype for Business Server高可用性、およびバックアップ サービスの管理

このセクションでは、障害復旧操作の手順と、ペアのフロント エンド プール内のデータを同期するバックアップ サービスを維持するための手順について説明します。

障害回復の手順は、フェールオーバーとフェールバックのどちらも、手動によるものです。障害が発生した場合、管理者はフェールオーバーの手順を手動で開始する必要があります。プール修復後のフェールバックにも同じことが当てはまります。

このセクションの障害復旧手順では、次の操作を前提とします。

  - 「高可用性と障害復旧の計画」の説明に従って、異なるサイトにあるペアのフロントエンド プールを使用した [展開があります](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)。 バックアップ サービスは、ペアになったプールの同期を保つためにこれらのプール上で実行されています。

  - 中央管理ストアがいずれかのプールでホストされている場合、そのストアは、アクティブ マスターをホストするプールとスタンバイをホストする他のプールのいずれかと、ペアのプールの両方にインストールされ、実行されます。

> [!IMPORTANT]
> 以下の手順では、影響を受けるユーザーのリダイレクト元になるプールではなく、障害の影響を受けるプールの完全修飾 FQDN を PoolFQDN ** パラメーターが参照しています。影響を受ける同じユーザー群が同じ場合、このパラメーターはフェールオーバーとフェールバックの各コマンドレットで同じプール (つまり、ユーザーがフェールオーバー前に最初に所属していたプール) を参照します。<BR><br>たとえば、プール P1 に所属していたすべてのユーザーがバックアップ プール P2 にフェールオーバーされた場合を想定します。 管理者が P2 によって現在サービスを受け取っているすべてのユーザーを P1 によってサービスに移動する場合、管理者は次の手順を実行する必要があります。 
> <OL>
> <LI>
> <P>フェールバック コマンドレットを使用して、P2 から P1 に P1 に最初にホームだったすべてのユーザーをフェールバックします。 この場合、PoolFQDN ** は P1 の FQDN になります。</P>
> <LI>
> <P>フェールオーバー コマンドレットを使用して、P2 から P1 に元々ホームだったすべてのユーザーをフェールオーバーします。 この場合、PoolFQDN は P2 の FQDN になります。</P>
> <LI>
> <P>管理者が後でそれらの P2 ユーザーを P2 にフェールバックする場合、PoolFQDN は P2 の FQDN になります。</P></LI></OL><br>プールの整合性を維持するには、手順 2 の前に上記の手順 1 を実行する必要があります。 手順 1 の前に手順 2 を実行すると、手順 2 コマンドレットは失敗します。


## <a name="see-also"></a>関連項目

[高可用性と障害復旧の計画](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md) 
  
