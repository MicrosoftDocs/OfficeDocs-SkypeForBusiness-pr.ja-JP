---
title: 障害回復、高可用性、バックアップサービスの管理
ms.reviewer: ''
author: lanachin
ms.author: v-lanac
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 障害回復操作の手順、およびペアリングされたフロントエンドプールのデータを同期するバックアップサービスの維持について説明します。
ms.openlocfilehash: 9664a7d9d48ca084232e2a0473a15d29d970cea6
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34303899"
---
# <a name="managing-skype-for-business-server-disaster-recovery-high-availability-and-backup-service"></a>Skype for Business Server の災害復旧、高可用性、バックアップサービスの管理

このセクションには、障害回復操作の手順に加えて、ペアリングされたフロントエンドプールのデータを同期するバックアップサービスを管理するための手順が含まれています。

フェールオーバーとフェールバックの両方の障害回復手順は手動で行うことができます。 障害が発生した場合、管理者はフェールオーバー手順を手動で呼び出す必要があります。 プールが修復された後も、フェイルバックにも同じことが適用されます。

このセクションの障害回復手順では、次のことを前提としています。

  - [高可用性と障害復旧の計画](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)に記載されているように、複数のフロントエンドプールを使用して、さまざまなサイトに存在する展開を利用できます。 これらのペアのプールでバックアップサービスが実行されているため、同期されません。

  - 中央管理ストアがいずれかのプールでホストされている場合は、これらのペアのプールの両方にインストールされて実行され、アクティブなマスターをホストしているプールと、スタンバイをホストしている他のプールのどちらかになります。

> [!IMPORTANT]
> 次の手順では、 *Poolfqdn*パラメーターが、障害によって影響を受けるプールの fqdn を示しますが、影響を受けるユーザーがリダイレクトされるプールには関係ありません。 影響を受けているユーザーの同じセットの場合、フェールオーバーとフェールバックの両方のコマンドレット (つまり、フェールオーバー前に最初にユーザーをホームにしたプール) で同じプールを参照します。<BR><br>たとえば、プール P1 に所属しているすべてのユーザーがバックアッププール (P2) にフェールオーバーした場合を想定します。 管理者が、現在 P2 で処理されているすべてのユーザーを P1 で処理するようにする場合は、管理者は次の手順を実行する必要があります。 
> <OL>
> <LI>
> <P>フェールバックコマンドレットを使用して、最初に P1 をホームにしたユーザーをすべて P2 から P1 にフェールバックします。 この場合、 *Poolfqdn*は P1's fqdn です。</P>
> <LI>
> <P>フェールオーバーコマンドレットを使用して、最初に P2 でホームに所属していたすべてのユーザーをフェールオーバーします。 この場合、PoolFQDN は P2's FQDN です。</P>
> <LI>
> <P>後で管理者が p2 に戻すようにしたい場合は、PoolFQDN は P2's FQDN です。</P></LI></OL><br>上記の手順1では、手順2を実行してプールの整合性を維持する必要があります。 手順1より前の手順2を実行した場合は、手順2のコマンドレットが失敗します。


## <a name="see-also"></a>関連項目

[高可用性および障害復旧の計画](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md) 
  
