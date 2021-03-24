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
description: トポロジ ビルダーを使用して構成したトポロジを公開します。 サーバーの全体管理ストアを保持する役割を担うフロント エンド サーバーまたはフロント エンド プールを一覧から選択する必要があります。 この役割をいつでも保持できるのは、フロント エンド サーバーまたはフロントエンド プールの 1 つのみです。
ms.openlocfilehash: fe3e7ed8c0a58b0547ede0eb02f0ea476bce94bc
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51096883"
---
# <a name="publish-topology-select-cms-page"></a>トポロジの公開での CMS の選択ページ
 
トポロジ ビルダーを使用して構成したトポロジを公開します。 サーバーの全体管理ストアを保持する役割を担うフロント エンド サーバーまたはフロント エンド プールを一覧から選択する必要があります。 この役割をいつでも保持できるのは、フロント エンド サーバーまたはフロントエンド プールの 1 つのみです。 
  
### <a name="about-the-central-management-server"></a>サーバーの全体管理について
中央管理サーバーは単一のマスター/複数レプリカ システムで、データベースの読み取り/書き込みコピーは、中央管理サーバーを含むフロントエンド サーバーによって保持されます。 サーバーの全体管理サーバーを含むフロントエンド サーバーを含むトポロジ内の各コンピューターには、セットアップと展開中に、SQL Server データベース (既定では RTCLOCAL という名前) の中央管理ストア データの読み取り専用コピーがインストールされます。 ローカル データベースは、すべてのコンピューターでサービスとして実行される Lync Server レプリカ レプリケーター エージェントを使用してレプリカ更新プログラムを受信します。 サーバーの全体管理サーバーとローカル レプリカ上の実際のデータベースの名前は、xds.mdf ファイルと xds.ldf ファイルで構成される XDS です。 マスター データベースの場所は、Active Directory ドメイン サービスのサービス コントロール ポイント (SCP) によって参照されます。 サーバーの全体管理サーバーを使用して Lync Server を管理および構成するツールはすべて、SCP を使用して中央管理ストアを検索します。
  
## <a name="see-also"></a>関連項目

[Move-CsManagementServer](/powershell/module/skype/move-csmanagementserver?view=skype-ps)