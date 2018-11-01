---
title: 'Lync Server 2013: 高可用性および障害復旧のサポート'
TOCTitle: 高可用性および障害復旧のサポート
ms:assetid: 47e77e85-c7c3-4ade-8db7-a34c71aeafd7
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ204866(v=OCS.15)
ms:contentKeyID: 48271971
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 での高可用性および障害復旧のサポート

 

_**トピックの最終更新日:** 2012-09-25_

Lync Server 2013 は、プーリングによるサーバー冗長性を使用した高可用性を備えています。特定のサーバーの役割を実行するサーバーで障害が発生した場合は、プール内の同じ役割を実行する他のサーバーがそのサーバーの負荷を引き受けます。同じことが、フロントエンド サーバー、エッジ サーバー、仲介サーバー、およびディレクターでも実行されます。サーバーの役割の詳細については、「[Lync Server 2013 のサーバーの役割](lync-server-2013-server-roles.md)」を参照してください。

また Lync Server 2013 は、プール ペアリングを有効化して障害復旧手段を提供します。このトポロジを展開する場合、フロントエンド プールのペアを指定します。ペアの各プールはそれぞれ個別のデータ センターと個別の地理的地域に配置されています。1 つのプールまたはサイトがダウンすると、そのプールのユーザーを、ペアの別のプールを利用するようにリダイレクトすることができるため、サービスの中断を最小限にすることができます。

Lync Server 2013 は、バック エンド サーバーの高可用性もサポートしています。これはオプションのトポロジです。このトポロジでは、1 つのフロントエンド プールに対して 2 つのバック エンド サーバーを展開し、バック エンド サーバーで実行されているすべての Lync データベースに SQL Server の同期ミラーリングをセットアップします。

プール ペアリングとバック エンド サーバーのミラーリングの詳細については、「[Lync Server 2013 での高可用性および障害復旧の計画](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)」を参照してください。

## 関連項目

#### 概念

[Lync Server 2013 のサーバーの役割](lync-server-2013-server-roles.md)  
[Lync Server 2013 での高可用性および障害復旧の計画](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)

