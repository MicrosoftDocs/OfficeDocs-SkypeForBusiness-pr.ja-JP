---
title: トポロジの公開での CMS の選択ページ
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.PublishTopologySelectCmsPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: df447066-2840-431b-bc4e-acf8aa692d71
ROBOTS: NOINDEX, NOFOLLOW
description: トポロジビルダーを使用して構成したトポロジを公開します。 フロントエンドサーバーまたはフロントエンドプールが、中央管理ストアを保持する役割を持つことを示すリストから選択するように求められます。 この役割は、1つのフロントエンドサーバーまたはフロントエンドプールでいつでも保持できます。
ms.openlocfilehash: e56597a1380f908c7abdb49b9b88edd7ad249870
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34277882"
---
# <a name="publish-topology-select-cms-page"></a>トポロジの公開での CMS の選択ページ
 
トポロジビルダーを使用して構成したトポロジを公開します。 フロントエンドサーバーまたはフロントエンドプールが、中央管理ストアを保持する役割を持つことを示すリストから選択するように求められます。 この役割は、1つのフロントエンドサーバーまたはフロントエンドプールでいつでも保持できます。 
  
### <a name="about-the-central-management-server"></a>サーバーの全体管理サーバーについて
サーバーの全体管理サーバーは、1つのマスター/マルチレプリカシステムです。このシステムでは、データベースの読み取り/書き込みのコピーが、中央管理サーバーを含むフロントエンドサーバーによって保持されています。 トポロジ内の各コンピューターには、サーバーを含むフロントエンドサーバーを含む、セットアップ時にコンピューターにインストールされた、SQL Server データベースの中央管理ストアデータの読み取り専用コピーがあります (既定では、RTCLOCAL という名前が付いています)。デプロイメント. ローカルデータベースは、すべてのコンピューターでサービスとして実行される Lync Server Replica Replicator エージェントを介して、レプリカの更新を受信します。 サーバーの全体管理サーバー上の実際のデータベースの名前とローカルレプリカは XDS で、これらは xds と xds のファイルで構成されます。 Master データベースの場所は、Active Directory ドメインサービスのサービスコントロールポイント (SCP) によって参照されます。 一元管理サーバーを使用して Lync Server を管理および構成するすべてのツール SCP を使用して、中央管理ストアを検索します。
  
## <a name="see-also"></a>関連項目

[CsManagementServer の移動](https://docs.microsoft.com/powershell/module/skype/move-csmanagementserver?view=skype-ps)
