---
title: トポロジの公開での CMS の選択ページ
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.PublishTopologySelectCmsPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: df447066-2840-431b-bc4e-acf8aa692d71
ROBOTS: NOINDEX, NOFOLLOW
description: トポロジ ビルダーを使用して構成したトポロジを公開します。 中央管理ストアを保持する役割を担うフロント エンド サーバーまたはフロントエンド プールを一覧から選択する必要があります。 このロールを保持できるフロントエンド サーバーまたはフロントエンド プールは 1 つのみです。
ms.openlocfilehash: d4af4756dc42c54790ee1120b418eb5e6a349387
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49822187"
---
# <a name="publish-topology-select-cms-page"></a>トポロジの公開での CMS の選択ページ
 
トポロジ ビルダーを使用して構成したトポロジを公開します。 中央管理ストアを保持する役割を担うフロント エンド サーバーまたはフロントエンド プールを一覧から選択する必要があります。 このロールを保持できるフロントエンド サーバーまたはフロントエンド プールは 1 つのみです。 
  
### <a name="about-the-central-management-server"></a>中央管理サーバーについて
中央管理サーバーは単一のマスター/複数レプリカ システムで、データベースの読み取り/書き込みコピーは、中央管理サーバーを含むフロントエンド サーバーによって保持されます。 中央管理サーバーを含むフロントエンド サーバーを含むトポロジ内の各コンピューターには、セットアップおよび展開時に、コンピューターにインストールされた SQL Server データベース (既定では RTCLOCAL という名前) の中央管理ストア データの読み取り専用コピーがあります。 ローカル データベースは、すべてのコンピューターでサービスとして実行される Lync Server レプリカ レプリケーター エージェントを使用してレプリカの更新を受信します。 中央管理サーバーとローカル レプリカ上の実際のデータベースの名前は、xds.mdf ファイルと xds.ldf ファイルで構成される XDS です。 マスター データベースの場所は、Active Directory ドメイン サービスのサービス コントロール ポイント (SCP) によって参照されます。 中央管理サーバーを使用して Lync Server を管理および構成するツールはすべて、SCP を使用して中央管理ストアを検索します。
  
## <a name="see-also"></a>関連項目

[Move-CsManagementServer](https://docs.microsoft.com/powershell/module/skype/move-csmanagementserver?view=skype-ps)
